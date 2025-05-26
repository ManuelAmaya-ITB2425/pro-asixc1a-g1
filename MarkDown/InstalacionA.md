# ☁️ Creación de la Instancia y Configuración de Servicios

## 1. 🧱 Creación de la Instancia

Instalaremos todos los servicios en una misma máquina, ya que no es necesario más y nos quedará 1 de repuesto por si hay que instalar más servicios.

Entramos a AWS y iniciamos una instancia, selecciono la AMI Ubuntu Server 22.04 LTS, la cual es perfecta para instalar todos los servicios.

<p align="center">
  <img src="../img/Instalacion1.png" alt="Iniciar instancia" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Instalacion2.png" alt="Ubuntu" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

Tipo t3.medium para que los 3 servicios funcionen bien sin ningún error y con 20 GB (SSD gp2) para que tenga suficiente almacenamiento para todos los servicios.

<p align="center">
  <img src="../img/Instalacion3.png" alt="Tipo de instancia" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>


## 2. 🔐 Configuración de los Security Groups

Para los security groups los configuro de la siguiente manera:

TCP 22 – SSH (acceso remoto)

TCP 80 – HTTP (acceso web general)

TCP 8000 – Streaming de audio (Icecast)

TCP 1935 – Streaming de vídeo (RTMP)

<p align="center">
  <img src="../img/Instalacion4.png" alt="Puertos" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Instalacion5.png" alt="Puertos" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>


## 3. 🎧 Instalación del Icecast

Una vez creada la instancia, con todos los permisos y el vockey.pem descargado y con los permisos necesarios. Me conecto por SSH a la IP pública. Una vez dentro, hago un update y un upgrade e instalo las dependencias del Icecast2.

<p align="center">
  <img src="../img/Instalacion6.png" alt="SSH" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Instalacion7.png" alt="Welcome" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Instalacion8.png" alt="UpgradeUpdate" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Instalacion9.png" alt="Instal" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>


## 4. ⚙️ Configuración del Icecast

Selecciono no en las dos opciones así puedo configurarlo a mi manera.

<p align="center">
  <img src="../img/Instalacion10.png" alt="Icecast" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Instalacion11.png" alt="Icecast" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

Para configurarlo entro en `sudo nano /etc/icecast2/icecast.xml`.

En el hostname pongo la IP pública 52.90.218.245, cambio las contraseñas del source y del admin a stream123 y admin123, cambio los sources de 2 a 5.

<p align="center">
  <img src="../img/Instalacion12.png" alt="Icecast" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Instalacion13.png" alt="Icecast" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Instalacion14.png" alt="Icecast" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>


Habilito el Icecast2 y miro si está funcionando correctamente con un `systemctl status`. Y desde un navegador entro a `http://52.90.218.245:8000` para comprobar si funciona.

<p align="center">
  <img src="../img/Instalacion15.png" alt="Systemctl" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

---

## 5. Instalación RTMP (Video)

Instalo el NGINX + el RTMP, luego entro al `/etc/nginx/nginx.conf` y al final del archivo añado la configuración de rtmp.

<p align="center">
  <img src="../img/Instalacion16.png" alt="Video" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Instalacion17.png" alt="Video" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

Luego creo el directorio de videos y le doy permisos, reinicio el nginx y compruebo si funciona todo.

<p align="center">
  <img src="../img/Instalacion18.png" alt="Video" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Instalacion19.png" alt="Video" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

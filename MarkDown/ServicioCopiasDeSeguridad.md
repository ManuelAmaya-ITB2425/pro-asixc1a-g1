
# ☁️ Explicación de Duplicati

Duplicati se presenta como una solución gratuita y de código abierto para tus copias de seguridad.  
Con ella, puedes programar y automatizar backups cifrados de tus archivos, ya sea en la nube o en servidores, tanto remotos como locales.

---

# 🚀 Lanzamiento de la instancia en AWS

Entramos a AWS y iniciamos una instancia, selecciono la **Ubuntu Server 24.04 LTS**, la cual es perfecta para instalar este servicio.  

![PHOTTTO1](../img/PHOTTTO1.png)

Tipo **t3.micro** porque para este servicio no hacen falta muchos recursos.

![PHOTTTO2](../img/PHOTTTO2.png)

---

# 🔐 Reglas de seguridad para Duplicati

Se muestran las reglas de grupo de seguridad para acceder vía **SSH** y al puerto web de **Duplicati**.

![PHOTTTO3](../img/PHOTTTO3.png)

---

# 🔄 Actualización del sistema y dependencias

## Hago un update

![PHOTTTO3](../img/PHOTTTO4.png)

## Instalo el mono runtime

![PHOTTTO3](../img/PHOTTTO5.png)

---

# 📦 Instalación del servicio Duplicati

## Descargo el duplicati

![PHOTTTO3](../img/PHOTTTO6.png)

## Descomprimo  e instalo el archivo

![PHOTTTO3](../img/PHOTTTO7.png)

## Instalo el Net-Tools

![PHOTTTO4](../img/PHOTTTO8.png)

## Edición del archivo de configuración del servicio

```bash
sudo nano /etc/systemd/system/duplicati.service
```

![PHOTTTO3](../img/PHOTTTO9.png)

---

# ⚙️ Comprobación del servicio

## Vemos que funciona y que el servicio está en marcha

![PHOTTTO5](../img/PHOTTTO10.png)

## Podemos usar el servicio desde la web

![PHOTTTO6](../img/PHOTTTO11.png)

---

# 🔁 Prueba de copia de seguridad

## Parámetros generales



---

## Creamos el directorio para guardar la copia

![PHOTTTO7](../img/PHOTTTO12.png)

![PHOTTTO3](../img/PHOTTTO13.png)

## Aqui podemos ver que en este directorio no hay nada guardado

![PHOTTTO3](../img/PHOTTTO14.png)

---
## Ahora escojo el directorio para guardar el backup

![PHOTTTO3](../img/PHOTTTO15.png)

## Escogemos el destino y probamos la conexión

![PHOTTTO8](../img/PHOTTTO27.png)

---

## Escogemos los datos de origen

![PHOTTTO9](../img/PHOTTTO18.png)

---

## Programamos la planificación de backups

![PHOTTTO10](../img/PHOTTTO19.png)

---

## Definimos el tamaño del volumen y la política de retención

![PHOTTTO11](../img/PHOTTTO20.png)

---

# ✅ Validación de la copia de seguridad

Ya está bien configurado el backup, ahora podemos ver que funciona porque aparece la próxima copia programada.  
También podemos **forzar una copia manualmente**.

## Copia programada a las 13:00

![PHOTTTO12](../img/PHOTTTO21.png)

## Ejecución manual y comprobación

![PHOTTTO12](../img/PHOTTTO22.png)

## Ahora volvemos a ver si hay archivos o datos en el directorio donde se guardan los backups

![PHOTTTO12](../img/PHOTTTO23.png)

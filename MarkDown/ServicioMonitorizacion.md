
# 📈 Explicación rápida de Prometheus

Prometheus es una herramienta de alerta y supervisión pensada para tomar mediciones a tiempo real de sistemas, servidores, contenedores, bases de datos y aplicaciones.

Recopila métricas como:

- Consumo de CPU  
- Memoria RAM  
- Espacio de disco duro  
- Solicitudes HTTP  
- Estado de los servicios  
- Latencias  

Prometheus sirve para:

- Supervisar servicios y servidores de manera ininterrumpida  
- Detectar fallos o caídas rápidamente  
- Analizar patrones de uso (carga, tráfico, rendimiento)  
- Tomar decisiones basadas en datos (optimización de recursos)

---

# ⚙️ Configuración de la instancia
 🧱 Creación de la Instancia

Entramos a AWS y iniciamos una instancia, selecciono la AMI Ubuntu Server 22.04 LTS, la cual es perfecta para instalar este servicio.

![BURRATA1](../img/BURRATA1.png)

Tipo t3.small porque para este servicio no hacen falta muchos recursos.

![BURRATA2](../img/BURRATA2.png)

Se muestran las reglas de grupo de seguridad para acceder vía SSH y al puerto web de Prometheus.

![PHOTTO1](../img/PHOTTO1.png)

![PHOTTO2](../img/PHOTTO2.png)

---

# 🛠️ Instalación de Prometheus

## 👤 Creo usuario Prometheus y sus carpetas

![PHOTTO3](../img/PHOTTO3.png)

## 📥 Descargo Prometheus

![PHOTTO4](../img/PHOTTO4.png)

## 📦 Lo instalo

![PHOTTO5](../img/PHOTTO5.png)

---

# 🧩 Configuración final y creación del servicio

![PHOTTO6](../img/PHOTTO6.png)

## ✏️ Creo y edito el archivo del servicio de Prometheus

Ruta del archivo: `/etc/systemd/system/prometheus.service`

![PHOTTO7](../img/PHOTTO7.png)

## ▶️ Activamos y comprobamos que funciona

![PHOTTO8](../img/PHOTTO8.png)

---

# 🌐 Acceso desde navegador

Prometheus se muestra correctamente accediendo desde el navegador.

![PHOTTO9](../img/PHOTTO9.png)

---

# 🧪 Ejecución de comandos para ver métricas

## ⌛ Tiempo de ejecución de una consulta:

Comando:

```prometheus
prometheus_engine_query_duration_seconds
```

![PHOTTO10](../img/PHOTTO10.png)

---

## 📊 Número de series activas en memoria:

Comando:

```prometheus
prometheus_tsdb_head_series
```

![PHOTTO11](../img/PHOTTO11.png)

---

## 🧩 Número de "chunks" de datos en la base de datos:

Comando:

```prometheus
prometheus_tsdb_head_chunks
```

![PHOTTO12](../img/PHOTTO12.png)

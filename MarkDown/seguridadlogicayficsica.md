# Seguridad física y lógica

## Seguridad física

### Control de acceso
- Acceso restringido, con tarjetas de identificación (RFID), solo podrá entrar personal autorizado, sin ángulo muerto.  
- Registro de entrada y salida de la sala, con fecha y hora.  
- Puertas metálicas.  
- Cristal reforzado que sea translúcido.  

*Imagen: Control de acceso*

---

### Videovigilancia
- Cámaras de alta resolución con visión nocturna.  
- Cobertura de entrada y salida, los pasillos interiores y armarios.  
- Una alarma silenciosa que avise de algún movimiento de acceso no autorizado.  
- Monitorización en tiempo real.  
- Grabación 24/7, almacenada en servidores locales/externos, por si acaso hay algún sabotaje.  

*Imagen: Sistema de videovigilancia*

---

### Sistemas de incendios
- Paredes reforzadas con material ignífugo y aislante.  
- Sensores de humo, movimiento, humedad y temperatura repartidos por toda la sala.  
- Sistema de extinción sin agua, con gas inerte FM-200 o Novec 1230.  
- Sistema de alarma sonora y visual en caso de incendio.  

*Imagen: Sistema de incendios*

---

### Vías de evacuación
- Salida de emergencia con señalización de luces LED e indicaciones fotoluminiscentes.  
- Formación periódica del personal, para que tengan conocimiento de las salidas de emergencia y cómo actuar en caso de incendio.  
- Plan de evacuación visible en puntos estratégicos.  
- Diagramas, planos y fotografías de toda la seguridad física incorporada.  

*Imagen: Vías de evacuación*

---

## Seguridad lógica

### Restricción de acceso por autorización
- Gestión de usuarios centralizada a través de Active Directory.  
- Políticas de contraseñas seguras con caducidad periódica y bloqueo tras intentos fallidos.  

*Imagen: Gestión de usuarios y contraseñas*

---

### Firewalls
- Se tendrá el control de puertos, protocolos, IPs sospechosas, ataques de denegación de servicio (DDoS), aplicaciones no autorizadas.  
- Se hará uso de listas negras y blancas, así se define quién puede o no acceder a la red.  

*Imagen: Firewall*

---

### Monitorización
- Monitorización activa 24/7.  
- Monitorización del tráfico de red, accesos de usuario, estado de servidores y servicios, temperatura, energía y otros parámetros ambientales, integrándose con sensores físicos del CPD.  

*Imagen: Monitorización del sistema*

---

### Copias de seguridad / Backups
- Backups automáticos diarios, se harán copias completas e incrementales semanales.  
- Las copias se guardarán remotamente en la nube y localmente en servidores separados del CPD.  
- Pruebas de restauración periódicas.  
- Los datos se cifrarán durante la copia y en reposo, para garantizar la confidencialidad.  

*Imagen: Backups y almacenamiento seguro*

---

### RAIDs
- RAID 10 para bases de datos críticas. Combina lo mejor del RAID 0 y RAID 1, seguridad y velocidad, tolerante a fallos, ya que si se rompe un disco sigue funcionando y muy rápido para lectura y escritura.  
- RAID 6 para sistemas de archivos compartidos, ya que puede fallar hasta 2 veces al mismo tiempo sin pérdida de datos. Pierdes más espacio en comparación con el RAID 5, pero ganas más seguridad.  

*Imagen: Sistema RAID*

---

## Prevención de riesgos laborales

### Medidas aplicadas en materia de la prevención de RRLL en el CPD:
- **Instalación eléctrica segura**, el sistema eléctrico cumple la normativa REBT (Reglamento Electrónico de Baja Tensión). Separación clara entre cableado eléctrico y de datos, para evitar interferencias o riesgos de circuitos.  
- **Sistema contra incendios**, con detectores de humo y calor. Extintores manuales homologados en cada acceso. Señalización clara de la salida de emergencia y acceso a extintores. Sistema automático de extinción de incendios con gas inerte.  
- **Formación y protocolos de emergencia**, los técnicos que entren al CPD recibirán una formación básica y los protocolos de evacuación. Se realizan simulacros anuales para practicar cómo actuar en caso de incendios. Códigos QR y manuales con el procedimiento de actuación en puntos estratégicos.  
- **Espacio ordenado y libre de obstáculos**, cableado bajo tierra y por el falso techo. Los espacios y pasillos entre racks tienen las medidas mínimas reglamentarias.  
- **Control ambiental y confort**, la temperatura y humedad están controladas. Iluminación LED adecuada y antideslumbrante para evitar fatiga visual. Niveles sonoros se mantienen en los límites aceptables para la vida laboral.  

*Imagen: Prevención de riesgos laborales en el CPD*

# 🧩 Distribución de Servicios en los 8 Servidores

---

## 🔸 Servidor 1 – 🧑‍💻 Web + 🎧 Audio

- **VM Web 1**: Frontend principal (Node.js, Nginx…)
- **VM Audio**: Servicio de audio en streaming o llamadas (tipo Jitsi)

**💡 Por qué juntos:**
- El audio usa ancho de banda pero poca CPU.
- El frontend responde rápido si está bien cacheado.
- Ambos pueden convivir sin molestarse.

🔳 **IMAGEN RECOMENDADA:** Esquema de servidor con dos VMs, una para frontend y otra para audio, compartiendo recursos.  

---

## 🔸 Servidor 2 – 📹 Vídeo + 🌐 Web 2

- **VM Vídeo**: Streaming/transcodificación (OBS, WebRTC…)
- **VM Web 2**: Microservicio o backend secundario

**💡 Por qué:**
- El vídeo necesita CPU/disco, así que se le da prioridad.
- Se aprovechan recursos sobrantes con una web ligera.

🔳 **IMAGEN RECOMENDADA:** Diagrama con uso intensivo de CPU por parte del vídeo y carga moderada web.  

---

## 🔸 Servidor 3 – 💾 BBDD 1 + BBDD 2

- **VM Galera Node 1** (MySQL/MariaDB)
- **VM Galera Node 2** (MySQL/MariaDB)

**💡 Por qué 2 nodos aquí:**
- Baja latencia entre nodos en el mismo host.
- Replicación síncrona y rendimiento con RAID 10 o SSDs.

🔳 **IMAGEN RECOMENDADA:** Arquitectura de clúster Galera con dos nodos locales y un tercer nodo externo opcional.  

---

## 🔸 Servidor 4 – 🔀 API Gateway + Web 3 + Balanceo

- **VM API Gateway** (HAProxy, Kong…)
- **VM Web 3**: Escalado del frontend
- **VM Balanceador / Proxy reverso**

**💡 Por qué:**
- Gestiona tráfico, cachea, distribuye y filtra.
- Red intensiva, CPU moderada.

🔳 **IMAGEN RECOMENDADA:** Diagrama de red mostrando balanceo de tráfico y distribución a otros servidores.  

---

## 🔸 Servidor 5 – 📈 Monitorización + Logs

- **VM Monitorización**: Prometheus, Grafana…
- **VM Logs**: ELK, Loki, Graylog…

**💡 Por qué:**
- Requiere mucha escritura en disco.
- CPU ligera pero constante.

🔳 **IMAGEN RECOMENDADA:** Panel con gráficas de monitorización y flujo de logs centralizado.  

---

## 🔸 Servidor 6 – 🔒 Seguridad / SIEM

- **VM Wazuh / Suricata / Firewall**
- **VM Control de acceso / IDS**

**💡 Por qué:**
- Procesa eventos y tráfico en tiempo real.
- Aislamiento total para reforzar la seguridad.

🔳 **IMAGEN RECOMENDADA:** Esquema de flujo de logs y eventos a través de un SIEM y firewall virtual.  

---

## 🔸 Servidor 7 – 🗃️ Backups + NAS/SAN Client

- **VM Backup Manager** (Veeam, Duplicati…)
- **VM Cliente NAS/SAN** (iSCSI/NFS)

**💡 Por qué:**
- Acceso a disco intensivo, poca CPU.
- Conectado a red rápida 10 GbE para restauraciones rápidas.

🔳 **IMAGEN RECOMENDADA:** Flujo de backup hacia NAS/SAN y restauración rápida desde almacenamiento.  

---

## 🔸 Servidor 8 – 🧪 Testing + Infra básica

- **VM Infra**: LDAP, DNS, DHCP, NTP
- **VM Testing**: Entorno de pruebas / staging

**💡 Por qué:**
- Servicios esenciales poco pesados.
- Permite validar cambios sin afectar producción.

🔳 **IMAGEN RECOMENDADA:** Gráfico con separación clara entre producción e infraestructura básica/test.  

---

## 🔄 Servidores 9 y 10 – 🔁 Reserva (N+1)

- **Modo espera**, activación automática si otro servidor cae.
- Migración en vivo o ejecución de servicios críticos al vuelo.

🔳 **IMAGEN RECOMENDADA:** Diagrama de failover con migración activa entre nodos de reserva.  

---

# 🧠 Consideraciones Finales

- 🔄 Balance entre CPU, RAM, disco y red para evitar cuellos.
- 🧱 Agrupación lógica: servicios compatibles sin competir.
- 🛡️ Seguridad: SIEM y BBDD aislados.
- 📈 Escalabilidad sin tocar hardware.
- 🔌 Conectividad redundante con 2 NICs por servidor.

🔳 **IMAGEN RECOMENDADA:** Diagrama general del CPD con relaciones entre servidores, tráfico, seguridad y redundancia.


<p align="center" style="margin-top: 40px;">
  <a href="./sostenibilidad.md" style="text-decoration: none; margin-right: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #2196F3; color: white; border: none;">
      ⬅️ Página anterior
    </button>
  </a>

  <a href="../README.md" style="text-decoration: none; margin-right: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #2196F3; color: white; border: none;">
      | 🏠 Inicio |
    </button>
  </a>
  
  <a href="./proveidorsdelnuvol.md" style="text-decoration: none; margin-left: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #4CAF50; color: white; border: none;">
      Página siguiente ➡️
    </button>
  </a>
</p>

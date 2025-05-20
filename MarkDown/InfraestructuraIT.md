# 🖥️ Infraestructura IT del CPD

## 1. 🖧 Servidores

Tendremos **12 servidores de producción** y **2 de reserva** (política N+1) para asegurar la continuidad:

- 🔹 **Modelo**: HPE ProLiant DL380 Gen10  
- 🔹 **CPU**: 2× Intel Xeon Silver 4216 (16 c / 32 h)  
- 🔹 **RAM**: 512 GB DDR4 (8×64 GB RDIMM)  
- 🔹 **Arranque**: 4× NVMe 1,6 TB en RAID 1+0  
- 🔹 **Datos**: 8× SAS 12 TB @ 10 000 rpm en RAID 6  
- 🔹 **Virtualización**: VMware vSphere HA (7 hosts activos + 1 nodo vSAN)  
- 🔹 **Redundancia**: migración automática de VM si un host falla

**Funcionamiento**  
1. Cada servidor arranca en milisegundos desde NVMe y monta las VM y bases de datos sobre los discos SAS.  
2. El hipervisor ESXi monitoriza la salud de cada nodo; ante un fallo realiza **fail-over** en < 10 s.  
3. El almacenamiento distribuido vSAN replica bloques en múltiples nodos, garantizando tolerancia a pérdidas de disco o servidor.

<p align="center">
  <img src="../img/Servidores.png" alt="Servidores" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

---

## 2. 🧩 Patch Panels

Agrupan y organizan todos los enlaces de fibra y cobre:

- 🔌 **Fibra OM4 (LC Duplex)**  
  - Patch panel de 12 fibras (U5)  
  - Troncales de 4× 10 Gbps a switches de distribución  
- 🔌 **Cobre Cat6A (RJ-45)**  
  - Patch panel de 48 puertos (U6)  
  - Conexiones de gestión, consola y enlaces de respaldo (1 Gbps)  
- 🔌 **Etiquetado**: TIA-606-B en ambos extremos  
- 🔌 **Canalización**: bandejas horizontales/verticales separando fibra y cobre

**Conexión típica**  


<p align="center">
  <img src="../img/PatchPanels.png" alt="Patch Panels" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

---

## 3. 🌐 Switches

**Arquitectura en tres capas** para máxima resiliencia y rendimiento:

1. **Core (U5)**  
   - 2× Cisco Catalyst 9500–24Q en stack activo-activo  
   - 24× QSFP+ @ 40 Gbps  
   - LACP (agregación) + VRRP (gateway redundante)

2. **Distribución (U7)**  
   - 2× Cisco Catalyst 9300–48UX  
   - 48× 1 Gbps PoE+ + 4× 10 Gbps uplinks al Core  
   - ACLs para aislar VLANs; QoS para priorizar VoIP/ERP

3. **Acceso**  
   - ~160× Cisco Catalyst 9200–24P (1 Gbps) en armarios de planta  
   - Despliegue en parejas activo-reserva  
   - Conectan PCs, VoIP y cámaras de vigilancia

**Topología de tráfico**  


<p align="center">
  <img src="../img/Switches.png" alt="Switches" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

---

## 4. 🔌 Alimentación y Refrigeración

- 🔋 **UPS N+1** (2 kVA módulos intercambiables en caliente, U22–U24)  
- 🔌 **PDU frontales y traseras** (U1–U2), en circuitos independientes  
- ❄️ **Pasillo frío/pasillo caliente**:  
  - Frío entra por el frente; caliente sale por detrás  
  - Rejillas en suelo técnico (40 cm) y techo falso dirigen el aire  
- 🌡️ **Monitorización ambiental**: sensores de temperatura, humedad y humo conectados a BMS con alertas SMS/Email

---

## 5. 🗄️ Diseño de Rack (42 U)

```text
┌────────────────────────────────────────────┐
│ U1–U2   PDU frontales/traseras             │
│ U3–U4   Bandejas gestión de cableado       │
│ U5      Patch panel fibra OM4              │
│ U6      Patch panel cobre Cat6A            │
│ U7      Switches Distribución (9300)       │
│ U8      Bandejas horizontales              │
│ U9–U18  10× Servidores (prod + vSAN)       │
│ U19–U20 2× Servidores de reserva           │
│ U21     Switch Acceso (9200)               │
│ U22–U24 Módulos UPS (2 kVA, N+1)           │
│ U25     Consola KVM                        │
│ U26–U42 Espacio libre para ampliaciones    │
└────────────────────────────────────────────┘

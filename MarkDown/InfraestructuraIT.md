# 🖥️ Infraestructura IT del CPD

## 1. 🖧 Servidores  
Tendremos **12 servidores de producción** y **2 de reserva** (política N+1) para asegurar la continuidad:

- 🔹 **Modelo**: HPE ProLiant DL380 Gen10  
- 🔹 **CPU**: 2× Intel Xeon Silver 4216 (16 c / 32 h)  
- 🔹 **RAM**: 512 GB DDR4 (8×64 GB RDIMM)  
- 🔹 **Arranque**: 4× NVMe 1,6 TB en RAID 1+0  
- 🔹 **Datos**: 8× SAS 12 TB @ 10 000 rpm en RAID 6  
- 🔹 **Virtualización**: VMware vSphere HA (7 hosts activos + 1 nodo vSAN)  
- 🔹 **Redundancia**: migración automática de VMs si un host falla  

**Funcionamiento**  
1. Arranque ultra-rápido desde NVMe.  
2. Hipervisor ESXi monitoriza salud y ejecuta fail-over en < 10 s.  
3. vSAN replica datos en varios nodos para tolerancia a fallos.

<p align="center">
  <img src="../img/Servidores.png" alt="Servidores" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

## 2. 🧩 Patch Panels  
Organización y terminación de enlaces de fibra y cobre:

- 🔌 **Fibra OM4 (LC Duplex)**  
  - Patch panel 12 fibras (U5)  
  - Troncales 4× 10 Gbps a switches de distribución  
- 🔌 **Cobre Cat6A (RJ-45)**  
  - Patch panel 48 puertos (U6)  
  - Conexiones de gestión, consola y backup (1 Gbps)  
- 🔌 **Etiquetado**: TIA-606-B en ambos extremos  
- 🔌 **Canalización**: bandejas horizontales/verticales separando fibra y cobre  

**Conexión típica**  

<p align="center">
  <img src="../img/PatchPanels.png" alt="Patch Panels" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

## 3. 🌐 Switches  
Arquitectura en tres capas para máxima resiliencia:

1. **Core (U5)**  
   - 2× Cisco Catalyst 9500–24Q en stack activo-activo  
   - 24× QSFP+ @ 40 Gbps  
   - LACP + VRRP  

2. **Distribución (U7)**  
   - 2× Cisco Catalyst 9300–48UX  
   - 48× 1 Gbps PoE+ + 4× 10 Gbps uplinks al Core  
   - ACLs y QoS  

3. **Acceso**  
   - ~160× Cisco Catalyst 9200–24P (1 Gbps) en armarios de planta  
   - Pares activo-reserva  
   - Conecta PCs, VoIP y cámaras  

**Topología de tráfico**  

<p align="center">
  <img src="../img/Switches.png" alt="Switches" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

## 4. 🔌 Alimentación y Refrigeración  

- 🔋 **UPS N+1** (2 kVA módulos intercambiables, U22–U24)  
- 🔌 **PDU frontales/traseras** (U1–U2), circuitos independientes  
- ❄️ **Pasillo frío/pasillo caliente**: aire frío al frente, caliente atrás  
- 🌡️ **Monitorización**: sensores de temperatura, humedad y humo con alertas SMS/Email  

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
│ U22–U24 UPS (2 kVA, N+1)                   │
│ U25     Consola KVM                        │
│ U26–U42 Espacio libre para ampliaciones    │
└────────────────────────────────────────────┘

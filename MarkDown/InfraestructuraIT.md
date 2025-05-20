# 🖥️ Infraestructura IT del CPD

## 1. 🖧 Servidores

Contaremos con **12 servidores de producción** y **2 de reserva** (política N+1) para garantizar continuidad de servicio.

- 🔹 **Modelo**: HPE ProLiant DL380 Gen10  
- 🔹 **CPU**: 2× Intel Xeon Silver 4216 (16 c / 32 h)  
- 🔹 **RAM**: 512 GB DDR4 (8×64 GB RDIMM)  
- 🔹 **Arranque**: 4× NVMe 1,6 TB  
- 🔹 **Datos**: 8× SAS 12 TB 10 K RPM  
- 🔹 **Virtualización**: VMware vSphere HA sobre un clúster de 7 hosts activos + 1 nodo vSAN  
- 🔹 **Redundancia**: Si un servidor falla, las VM migran al siguiente sin corte

<p align="center">
  <img src="../img/Servidores.png" alt="Servidores" width="40%" style="border: 1px solid #ccc; border-radius: 8px;" />
</p>

---

## 2. 🧩 Patch Panels

Organización y terminación de enlaces de fibra y cobre según norma **TIA-568**:

- 🔌 **Fibra OM4 (LC duplex)**: Patch panel 12 fibras  
- 🔌 **Cobre Cat6A (RJ-45)**: Patch panel 48 puertos  
- 🔌 **Etiquetado**: Conforme a TIA-606-B, con código en ambos extremos  
- 🔌 **Gestión de cableado**: Bandejas horizontales y verticales para separar fibra y cobre

<p align="center">
  <img src="../img/PatchPanels.png" alt="Patch Panels" width="40%" style="border: 1px solid #ccc; border-radius: 8px;" />
</p>

---

## 3. 🌐 Switches

Diseño en **tres capas** para máxima escalabilidad y resiliencia:

1. **Core**  
   - Cisco Catalyst 9500–24Q (stack activo-activo)  
   - 24× QSFP+ a 40 Gbps  
   - VRRP y LACP para redundancia de gateway y enlace

2. **Distribución**  
   - Cisco Catalyst 9300–48UX  
   - 48× 1 GbE PoE+ + 4× 10 GbE uplinks al Core  
   - ACLs y QoS para segmentar y priorizar tráfico

3. **Acceso**  
   - Cisco Catalyst 9200–24P (1 GbE)  
   - Despliegue en pares activo-reserva en armarios de planta  
   - Conecta PCs, VoIP y cámaras

<p align="center">
  <img src="../img/Switches.png" alt="Switches" width="40%" style="border: 1px solid #ccc; border-radius: 8px;" />
</p>

---

## 4. 🔌 Alimentación y Refrigeración

- 🔋 **SAI/UPS** en configuración N+1, módulos intercambiables en caliente  
- 🔌 **PDU frontales y traseras** por rack, en circuitos independientes  
- ❄️ **Pasillo frío/pasillo caliente**: aire frío al frente, caliente por detrás  
- 🌡️ **Monitoreo ambiental**: sensores de temperatura, humedad y detección de humo  

---

## 5. 🗄️ Diseño de Racks (42 U)

```text
┌──────────────────────────────────────────┐
│ U1–U2   PDU frontales y traseras        │
│ U3–U4   Bandejas gestión de cableado    │
│ U5      Patch panel fibra OM4           │
│ U6      Patch panel cobre Cat6A         │
│ U7      Switches de Distribución (9300) │
│ U8      Bandejas horizontales           │
│ U9–U18  10× Servidores (prod + vSAN)    │
│ U19–U20 Servidores de reserva           │
│ U21     Switch Acceso (9200)            │
│ U22–U24 Módulos UPS (N+1)               │
│ U25     Consola KVM                     │
│ U26–U42 Espacio para futuras ampliaciones│
└──────────────────────────────────────────┘


# 🖥️ Infraestructura IT del CPD

## 1. 🖧 Servidores

Tendremos **12 servidores de producción** y **2 de reserva** (política N+1) para asegurar la continuidad. Cada rack alojará:

- 🔹 **Modelo**: HPE ProLiant DL380 Gen10  
- 🔹 **CPU**: 2× Intel Xeon Silver 4216 (16 c / 32 h)  
- 🔹 **RAM**: 512 GB DDR4 (8×64 GB RDIMM)  
- 🔹 **Arranque**: 4× NVMe 1,6 TB en RAID 1+0  
- 🔹 **Datos**: 8× SAS 12 TB @10 000 rpm en RAID 6  

**Cómo funciona**:  
Cada servidor arranca rápido desde NVMe y guarda los VMs y bases de datos en los SAS. Un hipervisor (VMware ESXi) coordina un clúster de 7 nodos activos + 1 vSAN, detecta fallos en < 10 s y mueve automáticamente las VM al siguiente host.

<p align="center">
  <img src="../img/Servidores.png" alt="Servidores" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

---

## 2. 🧩 Patch Panels

Organizan y terminan todos los cables de fibra y cobre:

- 🔌 **Fibra OM4 (LC Duplex)**  
  - Patch panel de 12 fibras, montado en U5  
  - Troncales 4×10 Gbps hacia switches de distribución  

- 🔌 **Cobre Cat6A (RJ-45)**  
  - Patch panel de 48 puertos, montado en U6  
  - Conexiones de gestión y consola (1 Gbps)  

**Conexión**:  
Los servidores usan transceivers SFP+ duales: dos enlaces de 10 Gbps (datos + backup) a panel OM4. Cada puerto del panel está numerado y etiquetado en ambos extremos, siguiendo TIA-606-B.

<p align="center">
  <img src="../img/PatchPanels.png" alt="Patch Panels" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

---

## 3. 🌐 Switches

Arquitectura de red en tres niveles:

1. **Core (U5)**  
   - 2× Cisco Catalyst 9500–24Q en stack activo-activo  
   - 24× QSFP+ a 40 Gbps  
   - LACP para agregación y VRRP para gateway  

2. **Distribución (U7)**  
   - 2× Cisco Catalyst 9300–48UX  
   - 48× 1 Gbps PoE+ + 4× 10 Gbps uplinks al Core  
   - ACLs para aislar VLANs y QoS para priorizar VoIP/ERP  

3. **Acceso (fuera rack)**  
   - 160× Cisco Catalyst 9200–24P (1 Gbps)  
   - Despliegue en parejas activo-reserva por armario de planta  
   - Conectan PCs, teléfonos IP y cámaras  

**Topología**:  

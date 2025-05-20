## 1. Implementación de sonidos e imágenes en la nube

### 1.1 Requisitos técnicos de los servicios

- **Servidor de audio (0375.7):**  
  Retransmisión al instante con pruebas de amplitud de onda.

- **Servidor de vídeo (0375.8):**  
  Retransmisión en directo y a la carta, con avales de calidad.

- **Pruebas de red:**  
  Indispensables para evitar saturaciones y asegurar una experiencia fluida para el usuario.

---

### 1.2 Comparació de gestors de núvol segons rendiment i atencions

| **Logos** | **Gestor**         | **Eficiència energètica**              | **Solució d’àudio i vídeo**           | **Revisió de xarxa**                  | **Altres avantatges**                                   |
|:--:|--------------------|------------------------------------------|----------------------------------------|----------------------------------------|----------------------------------------------------------|
| <img src="../img/AWS.png" height="20">         | **Amazon AWS**     | PUE 1.14, 85% renovable                | AWS Elemental MediaLive               | Amazon CloudWatch                     | Múltiples zones accessibles                              |
| <img src="../img/Azure.png" height="20">       | **Microsoft Azure**| PUE 1.125, 100% renovable el 2025     | Azure Media Services                  | Azure Monitor                         | Integració òptima amb Windows Server                     |
| <img src="../img/ovhcloud.png" height="20">    | **OVHcloud**       | PUE 1.09, refrigeració líquida         | Servidors dedicats i Cloud Public     | Grafana, Metrics                      | CPD a Europa i més econòmic                              |
| <img src="../img/googlecloud.png" height="20"> | **Google Cloud**   | PUE 1.10, 100% renovable               | Transcoder API, Live Stream API       | Network Intelligence Center           | Molt adaptable                                           |

---

### 1.3 Propuesta de ubicación del CPD

**Solución sugerida:** Google Cloud Platform

#### Componentes propuestos:

| **Servicio**               | **Descripción**                                                         |
|---------------------------|-------------------------------------------------------------------------|
| **Compute Engine**        | Infraestructura para ubicar servidores virtuales                        |
| **Transcoder API**        | Transcodificación de vídeo al instante                                  |
| **Cloud CDN**             | Reparto de contenido global para aminorar la latencia                   |
| **Network Intelligence Center** | Análisis de amplitud de onda y prevención de caídas de red          |

#### Beneficios:

- Rendimiento energético máximo.
- Cumplimiento de fines medioambientales.
- Capacidad de revisión de red y crecimiento automático.
- Aval de calidad en la retransmisión de audio y vídeo.

---

## 2. Conclusiones

En este proyecto abordamos dos líneas principales:

- **Infraestructura Cloud (CPD):**  
  Se analizaron distintos gestores de nube atendiendo al rendimiento energético, sostenibilidad y capacidad para brindar servicios exigentes como la retransmisión de audio y vídeo.  
  **Google Cloud Platform** fue seleccionado como la mejor opción gracias a sus herramientas específicas, su escalabilidad automática y su fuerte compromiso medioambiental.
- **Nivel técnico y medioambiental:**  
  El plan asegura un funcionamiento eficaz, calidad de servicio y responsabilidad con el medio ambiente. Esta infraestructura, junto con su enfoque en eficiencia y escalabilidad, es ideal para una empresa tecnológica que busque adaptarse a los retos actuales del sector informático.
<img src="../img/conclusionaws.png" height="500">
---

<p align="center" style="margin-top: 40px;">
  <a href="./implementacionCPD.md" style="text-decoration: none; margin-right: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #2196F3; color: white; border: none;">
      ⬅️ Página anterior
    </button>
  </a>

  <a href="../README.md" style="text-decoration: none; margin-right: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #2196F3; color: white; border: none;">
      | 🏠 Inicio |
    </button>
  </a>
  
  <a href="../README.md" style="text-decoration: none; margin-left: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #4CAF50; color: white; border: none;">
      Página siguiente ➡️
    </button>
  </a>
</p>

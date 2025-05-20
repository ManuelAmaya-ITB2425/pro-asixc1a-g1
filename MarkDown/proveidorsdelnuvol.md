## 1. Implementación de sonidos e imágenes en la nube

### 1.1 Requisitos técnicos de los servicios

- **Servidor de audio (0375.7):**  
  Retransmisión al instante con pruebas de amplitud de onda.

- **Servidor de vídeo (0375.8):**  
  Retransmisión en directo y a la carta, con avales de calidad.

- **Pruebas de red:**  
  Indispensables para evitar saturaciones y asegurar una experiencia fluida para el usuario.

---

### 1.2 Comparación de gestores de nube según rendimiento y atenciones

     |               | **Gestor**        | **Eficiencia energética**              | **Solución de audio y vídeo**     | **Revisión de red**              | **Otras ventajas**                                  |
     |---------------|------------------|----------------------------------------|-----------------------------------|----------------------------------|------------------------------------------------------|
     |               | **Google Cloud** | PUE 1.10, 100% renovable               | Transcoder API, Live Stream API  | Network Intelligence Center      | Muy adaptable                                           |
     |               | **Amazon AWS**   | PUE 1.14, 85% renovable                | AWS Elemental MediaLive          | Amazon CloudWatch                | Múltiples zonas accesibles                             |
     |               | **Microsoft Azure** | PUE 1.125, 100% renovable en 2025  | Azure Media Services             | Azure Monitor                    | Óptima integración con Windows Server                  |
     |               | **OVHcloud**     | PUE 1.09, refrigeración líquida        | Servidores dedicados y Cloud Public | Grafana, Metrics             | CPD en Europa y más económico                          |

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

---

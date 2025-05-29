# Documentación del Sistema de Gestión de Base de Datos Empresarial con Chatbot en Telegram

## Descripción General
El sistema consiste en una base de datos PostgreSQL alojada en un servidor Linux dentro de un CPD (Centro de Procesamiento de Datos), accesible a través de un chatbot de Telegram llamado "Zerobot". Este bot permite realizar operaciones CRUD sobre la base de datos de recursos humanos con controles de acceso basados en departamentos.

## Arquitectura del Sistema
### Componentes Principales
- **Servidor Linux**  
  - Sistema operativo: Ubuntu  
  - PostgreSQL 16 instalado  
  - Configuración de red para acceso seguro  

- **Base de Datos PostgreSQL**  
  - Esquema relacional con tablas para usuarios, departamentos y grupos  
  - Relaciones muchos-a-muchos entre usuarios y grupos  

- **Chatbot Zerobot**  
  - Desarrollado en Python con `python-telegram-bot`  
  - Conexión directa a PostgreSQL  
  - Autenticación por sesiones  

## Estructura de la Base de Datos
### Tablas Principales
| Tabla            | Descripción                              | Campos Clave                          |
|------------------|------------------------------------------|---------------------------------------|
| `departamentos`  | Departamentos de la empresa              | `id` (PK), `nombre`                   |
| `usuarios`       | Información de empleados                 | `id` (PK), `departamento_id` (FK), etc. |
| `grupos`         | Grupos de acceso/permisos                | `id` (PK), `nombre`                   |
| `usuarios_grupos`| Relación usuarios-grupos (M:N)           | `usuario_id` (FK), `grupo_id` (FK)    |

## Funcionalidades del Chatbot Zerobot
### Autenticación
1. **Flujo**:  
   - Comando `/start` → Ingresar ID → Contraseña global  
   - Verificación en BD → Creación de sesión  

2. **Control de Acceso**:  
   - Departamentos tienen permisos específicos  
   - Admin (ID 0) tiene acceso total  

### Comandos Disponibles
#### Consultas
| Comando                  | Descripción                                  |
|--------------------------|----------------------------------------------|
| `/usuario <id>`          | Detalles completos de un usuario             |
| `/usuarios`              | Lista todos los usuarios                     |
| `/buscar <texto>`        | Busca por nombre, email o puesto             |
| `/departamentos`         | Lista departamentos                          |

#### Modificaciones (Acceso Restringido)
| Comando                          | Departamentos Autorizados |
|----------------------------------|---------------------------|
| `/agregar_usuario`               | 1, 0                      |
| `/asignar_grupo`                 | 1, 0                      |
| `/cambiar_estado <id> <estado>`  | 1, 0                      |

## Permisos por Departamento
| Departamento         | ID  | Comandos Accesibles                           |
|----------------------|-----|------------------------------------------------|
| Desarrollo           | 1   | `/usuario`, `/agregar_usuario`, `/asignar_grupo` |
| Admin                | 0   | **Todos los comandos**                         |

## Seguridad
- **Autenticación**:  
  - Contraseña global + verificación de estado  
  - Sesiones temporales  

- **Protección de Datos**:  
  - Contraseñas ocultas en respuestas  
  - Validación básica contra inyección SQL  

## Requisitos
```bash
# Servidor
- Ubuntu + PostgreSQL 16+
- Python 3.8+ con librerías:
  - python-telegram-bot
  - psycopg2

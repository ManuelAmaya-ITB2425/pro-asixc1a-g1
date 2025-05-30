# Documentación del Sistema de Alertas con auditd + Fail2ban + Telegram

## 1. Introducción

En este documento se explica el proceso completo para monitorizar cambios en el sistema con `auditd`, enviar alertas por Telegram y gestionar bloqueos con `fail2ban`.

---

## 2. Archivos modificados y creados

### 2.1 Scripts Bash

- `/etc/fail2ban/audit_telegram.sh`

> **Función:** Script que lee `/var/log/audit/audit.log` para detectar eventos con la clave `hosts-watch` y envía mensajes a Telegram.

<p align="center">
  <img src="../../img/S6 - Seguridad/etc-fail2ban-audit_telegram.sh.png" alt="Plano edificio" width="55%" style="border: 1px solid #ccc; border-radius: 8px;" />
</p>

---

### 2.2 Configuración de auditd

- `/etc/audit/rules.d/audit.rules`

> **Función:** Definición de reglas para monitorizar archivos sensibles (ejemplo: `/etc/hosts`).

<p align="center">
  <img src="../../img/S6 - Seguridad/etc-audit-rules.d-audit.rules.png" alt="Plano edificio" width="55%" style="border: 1px solid #ccc; border-radius: 8px;" />
</p>

- `/var/log/audit/audit.log`

> **Función:** Archivo de log donde auditd guarda eventos.

---

### 2.3 Configuración de fail2ban (opcional)

- `/etc/fail2ban/jail.local`

> **Función:** Configuración de jails para proteger servicios (ej. ssh) y bloqueo de IPs.

<p align="center">
  <img src="../../img/S6 - Seguridad/bot.py1.png" alt="Plano edificio" width="55%" style="border: 1px solid #ccc; border-radius: 8px;" />

  
  <img src="../../img/S6 - Seguridad/bot.py2.png" alt="Plano edificio" width="55%" style="border: 1px solid #ccc; border-radius: 8px;" />

  
  <img src="../../img/S6 - Seguridad/bot.py3.png" alt="Plano edificio" width="55%" style="border: 1px solid #ccc; border-radius: 8px;" />
</p>

- `/etc/fail2ban/action.d/telegram.conf` (si se creó)

> **Función:** Acción personalizada para enviar alertas por Telegram.

> **Captura:**  
> Contenido de la acción con `cat /etc/fail2ban/action.d/telegram.conf`
<p align="center">
  <img src="../../img/S6 - Seguridad/etc-fail2ban-action.d-telegram.conf.png" alt="Plano edificio" width="55%" style="border: 1px solid #ccc; border-radius: 8px;" />
</p>

---

### 2.4  Script Python del Bot

- `/etc/fail2ban/bot.py`

> **Función:** Script en Python que envía mensajes directos al chat de Telegram mediante la API del bot. Utilizado para pruebas iniciales o como parte de una automatización.

<p align="center">
  <img src="../../img/S6 - Seguridad/etc-fail2ban-action.d-telegram.conf.png" alt="Plano edificio" width="55%" style="border: 1px solid #ccc; border-radius: 8px;" />
</p>
---

## 3. Comandos útiles para comprobar el sistema

- Buscar eventos recientes:  
```bash
sudo ausearch -k hosts-watch --start recent

# Documentación del Sistema de Alertas con auditd + Fail2ban + Telegram

## 1. Introducción

En este documento se explica el proceso completo para monitorizar cambios en el sistema con `auditd`, enviar alertas por Telegram y gestionar bloqueos con `fail2ban`.

---

## 2. Archivos modificados y creados

### 2.1 Scripts Bash

- `/etc/fail2ban/audit_telegram.sh`

> **Función:** Script que lee `/var/log/audit/audit.log` para detectar eventos con la clave `hosts-watch` y envía mensajes a Telegram.

> **Captura:**  
> Captura del contenido del script `audit_telegram.sh` usando `cat /etc/fail2ban/audit_telegram.sh`

---

### 2.2 Configuración de auditd

- `/etc/audit/rules.d/audit.rules`

> **Función:** Definición de reglas para monitorizar archivos sensibles (ejemplo: `/etc/hosts`).

> **Captura:**  
> Mostrar las reglas con `cat /etc/audit/rules.d/audit.rules`

- `/var/log/audit/audit.log`

> **Función:** Archivo de log donde auditd guarda eventos.

> **Captura:**  
> Captura de un ejemplo de evento detectado (usa `ausearch -k hosts-watch --start recent`).

---

### 2.3 Configuración de fail2ban (opcional)

- `/etc/fail2ban/jail.local`

> **Función:** Configuración de jails para proteger servicios (ej. ssh) y bloqueo de IPs.

> **Captura:**  
> Mostrar las jails configuradas con `cat /etc/fail2ban/jail.local`

- `/etc/fail2ban/action.d/telegram.conf` (si se creó)

> **Función:** Acción personalizada para enviar alertas por Telegram.

> **Captura:**  
> Contenido de la acción con `cat /etc/fail2ban/action.d/telegram.conf`

---

### 2.4 Automatización del Script

- Configuración de cron o systemd para ejecutar automáticamente el script.

> **Captura:**  
> Si se usó cron, mostrar el contenido con `crontab -l` o el archivo específico en `/etc/cron.d/`.

> Si se usó systemd, mostrar el archivo `.service` y estado con `systemctl status audit-telegram.service`.

---

## 3. Comandos útiles para comprobar el sistema

- Buscar eventos recientes:  
```bash
sudo ausearch -k hosts-watch --start recent

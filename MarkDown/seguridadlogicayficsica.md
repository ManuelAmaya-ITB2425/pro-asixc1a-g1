# 1.4 - Seguretat física i lògica

## Seguretat física

### Control d’accés
- Accés restringit, amb targetes d'identificació (RFID), sols podrà entrar personal autoritzat, sense angle 
  mort. 
- Registre d’entrada i sortida de la sala, amb data i hora.
- Portes metàl·liques.
- Vidre reforçat que sigui translúcid.

### Videovigilància
- Càmeres d’alta resolució amb visió nocturna.
- Cobertura d’entrada i sortida, passadissos interiors i armaris.
- Alarma silenciosa per accés no autoritzat.
- Monitoratge a temps real.
- Gravació 24/7 emmagatzemada en servidors locals i/o externs.

### Sistemes d’incendis
- Parets reforçades amb material ignífug i aïllant.
- Sensors de fum, moviment, humitat i temperatura repartits per la sala.
- Sistema d’extinció sense aigua: gas inert FM-200 o Novec 1230.
- Sistema d’alarma sonor i visual en cas d’incendi.

### Vies d'evacuació
- Sortida d’emergència amb senyalització LED i indicacions fotoluminescents.
- Formació periòdica del personal sobre com actuar en cas d’emergència.
- Pla d’evacuació visible en punts estratègics.
- Diagrames, planells i fotografies de tota la seguretat física incorporada.

---

## Seguretat lògica

### Restricció d’accés per autorització
- Gestió d’usuaris centralitzada amb **Active Directory**.
- Polítiques de contrasenyes segures amb caducitat periòdica.
- Bloqueig després d’intents fallits.

### Firewalls
- Control de ports, protocols, IPs sospitoses, atacs DDoS, aplicacions no autoritzades.
- Llistes negres i blanques per controlar l’accés a la xarxa.

### Monitoratge
- Monitoratge actiu 24/7.
- Monitoratge de tràfic de xarxa, accessos d’usuari, estat de servidors i serveis, temperatura, energia, etc.
- Integració amb sensors físics del CPD.

### Còpies de seguretat / Backups
- Backups automàtics diaris.
- Còpies completes i incrementals setmanals.
- Còpies guardades remotament (núvol) i localment en servidors separats.
- Proves de restauració periòdiques.
- Xifrat de dades durant la còpia i en repòs.

### RAIDs
- **RAID 10** per bases de dades crítiques: seguretat i velocitat, tolerància a falles.
- **RAID 6** per sistemes de fitxers compartits: pot fallar fins a 2 discos sense pèrdua de dades.

---

## Prevenció de riscos laborals

### Mesures aplicades al CPD:
- **Instal·lació elèctrica segura** segons normativa REBT. Separació de cablejat elèctric i de dades.
- **Sistema contra incendis** amb detectors de fum i calor. Extintors manuals homologats. Senyalització clara d’emergències. Sistema automàtic amb gas inert.
- **Formació i protocols d’emergència**: formació bàsica als tècnics, simulacres anuals, codis QR i manuals amb procediments visibles.
- **Espai ordenat i lliure d’obstacles**: cablejat sota terra i al fals sostre, espais mínims entre racks.
- **Control ambiental i confort**: temperatura i humitat controlades, il·luminació LED antienlluernament, soroll dins dels límits laborals.


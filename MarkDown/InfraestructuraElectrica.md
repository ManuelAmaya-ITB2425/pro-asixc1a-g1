# 🔢 Cálculo del consumo estimado del sistema

Primero calculamos el CONSUMO ESTIMADO DEL SISTEMA:  
Número de servidores activos: 1  
Consumo estimado por servidor: un servidor consume 700 W de media y con mucha carga, puede llegar a picos de 1000 W, por esta razón pondremos un margen de seguridad del 20%, para que los SAI puedan aguantar los servidores cuando estos están a máxima carga.

**Consumo total:**  
10 Servidores x 700 W = 7 kW

**Margen de seguridad del 20% para compensar picos de consumo y garantir eficiencia:**  
7 kW x 1,2 = 8,4 kW  
**Energía necesaria para 3 horas:**  
8,4 kW x 3 h = 25,2 kWh  

Así que necesitaremos un sistema de SAI que nos proporcione **25,2 KWh** para que los servidores puedan funcionar por 3 horas sin electricidad, teniendo en cuenta los picos de consumo que pueden suceder al tener los servidores a máxima carga.

<p align="center">
  <img src="../img/BIBI1.png" alt="Racks" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>
---

# 🔋 Especificaciones del sistema SAI necesario

Así que tendremos que buscar sistemas SAI de estas especificaciones:

- 6 kVA  
- Factor de potencia realmente utilizada de 0,9 o 90%  
- 5 kW por SAI  

**El que coincide con estas especificaciones es este, es perfecto para nosotros:**  
SAI Lapara 6000VA / 6000W (Este proporciona 1 KW más de los que necesitamos, pero va bien para asegurar cuando se pongan a máxima carga todos los servidores).

<p align="center">
  <img src="../img/BIBI2.png" alt="Racks" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>
---

# 💰 Coste estimado del sistema SAI

Ahora mismo el precio de este Sistema SAI es de unos **1.647,09 €**,  
y si compramos **5**, el costo total sería unos **8.235,45 €**.

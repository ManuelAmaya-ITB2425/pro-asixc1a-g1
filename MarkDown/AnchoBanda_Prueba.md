## 7. 📶 Comprobación Ancho de Banda

Descargo en iperf3 para hacer las comprobaciones, e inicio el servidor con `iperf3 -s`. Luego desde otra maquina (cliente) hago las comprobaciones.  
El puerto 5201 tiene que estar abierto para que cualquiera pueda verlo, así se puede comunicar la instancia con cualquier cliente.

<p align="center">
  <img src="../img/Ancho1.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Ancho2.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Ancho3.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

---

Desde el cliente (iPhone, pero puede ser cualquiera) uso una aplicación para hacer el test, pongo la IP pública mientras el comando `iperf3 -s` está ejecutándose en la instancia y vemos la velocidad de ancho de banda.

<p align="center">
  <img src="../img/Ancho4.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Ancho5.png" alt="Video" width="40%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center" style="margin-top: 40px;">
  <a href="./AudioVideo_Prueba.md" style="text-decoration: none; margin-right: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #2196F3; color: white; border: none;">
      ⬅️ Página anterior
    </button>
  </a>
  
  <a href="../README.md" style="text-decoration: none; margin-right: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #2196F3; color: white; border: none;">
      | 🏠 Inicio |
    </button>
  </a>
  
  <a href="./Infraestructuraelectrica.md" style="text-decoration: none; margin-left: 20px;">
    <button style="padding: 10px 20px; font-size: 16px; border-radius: 6px; background-color: #4CAF50; color: white; border: none;">
      Página siguiente ➡️
    </button>
  </a>
</p>


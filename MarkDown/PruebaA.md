## 6. 🔊 Prueba de Audio y video

Para emitir el audio uso el FFMPEG, desde la misma consola conectada a la instancia.

Primero descargo 2 archivos, 1 en mp3 (audio) y otro en mp4 (video) para hacer las pruebas, las meto en el mismo archivo donde esta mi vockey, y los muevo a la instancia con este comando: scp -i vockey2.pem cancion.mp3 ubuntu@52.90.218.245:~

<p align="center">
  <img src="../img/Prueba1.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Prueba2.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>
---

### 🎧 Emito el audio

<p align="center">
  <img src="../img/Prueba3.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Prueba4.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

Entro a http://54.81.111.199:8000/stream. Y compruebo que funciona el mp3 que he subido.

<p align="center">
  <img src="../img/Prueba5.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Prueba6.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>
---

### 📹 Emito el Video

Igual que con el audio, descargo un mp4 de prueba y lo subo al AWS, y ejecuto el comando para que se emita.

Despues entro a rtmp://54.224.139.37/live/stream desde VLC player.

Y se ve el video correctamente.rtmp://54.224.139.37/live/stream

<p align="center">
  <img src="../img/Prueba7.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Prueba8.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

<p align="center">
  <img src="../img/Prueba9.png" alt="Video" width="70%" style="border:1px solid #ccc; border-radius:8px;" />
</p>

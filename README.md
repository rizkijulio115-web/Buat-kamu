# Buat-kamu
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Untuk Kamu 🌈💖</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&family=Dancing+Script:wght@700&display=swap');
    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: linear-gradient(135deg, #ffe6f7, #fff9c4, #ccf5ff);
      font-family: 'Poppins', sans-serif;
      color: #444;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      text-align: center;
      overflow: hidden;
      transition: background 1s ease;
    }

    h1 {
      font-family: 'Dancing Script', cursive;
      font-size: 2.5em;
      color: #ff4d6d;
      margin-bottom: 20px;
      animation: fadeIn 1.5s ease;
    }

    p {
      font-size: 1.1em;
      color: #555;
      max-width: 500px;
      margin: 10px auto 30px;
      animation: fadeIn 2s ease;
    }

    img {
      width: 230px;
      height: 230px;
      object-fit: cover;
      border-radius: 50%;
      box-shadow: 0 0 20px rgba(0,0,0,0.1);
      margin-bottom: 20px;
      animation: bounceIn 1.2s ease;
    }

    button {
      background: #ff85a1;
      border: none;
      color: white;
      padding: 12px 25px;
      border-radius: 30px;
      cursor: pointer;
      font-size: 1em;
      transition: 0.3s;
      box-shadow: 0 4px 10px rgba(255, 77, 109, 0.4);
      margin-top: 10px;
    }

    button:hover {
      transform: scale(1.1);
      background: #ff4d6d;
    }

    #surat, #pesan {
      display: none;
      animation: fadeIn 1.5s ease;
    }

    #surat p {
      white-space: pre-wrap;
      font-size: 1.1em;
      line-height: 1.6;
      color: #444;
      margin-bottom: 30px;
    }

    /* Animasi love */
    .love {
      position: absolute;
      color: #ff4d6d;
      font-size: 24px;
      animation: floatLove 5s linear infinite;
      opacity: 0.7;
    }

    @keyframes floatLove {
      0% { transform: translateY(0) scale(1); opacity: 1; }
      100% { transform: translateY(-800px) scale(0.5); opacity: 0; }
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes bounceIn {
      0% { transform: scale(0); opacity: 0; }
      60% { transform: scale(1.2); opacity: 1; }
      100% { transform: scale(1); }
    }

    #pesan h2 {
      font-family: 'Dancing Script', cursive;
      font-size: 2em;
      color: #ff4d6d;
      animation: fadeText 3s infinite alternate;
    }

    @keyframes fadeText {
      from { opacity: 0.3; }
      to { opacity: 1; }
    }

    #musicButton {
      background: #fff;
      color: #ff4d6d;
      font-weight: bold;
      padding: 10px 20px;
      border-radius: 25px;
      box-shadow: 0 3px 10px rgba(0,0,0,0.2);
      margin-bottom: 15px;
      transition: all 0.3s ease;
    }

    #musicButton:hover {
      background: #ff4d6d;
      color: white;
    }
  </style>
</head>
<body>

  <!-- Tombol Musik -->
  <button id="musicButton" onclick="toggleMusic()">🎵 Putar Musik</button>
  <audio id="bgMusic" loop>
    <source src="https://cdn.pixabay.com/audio/2022/10/03/audio_3a51e9b4aa.mp3" type="audio/mp3">
  </audio>

  <!-- Bagian Foto & Pembuka -->
  <div id="awal">
    <img src="foto-kamu.jpg" alt="Foto Kamu">
    <h1>Hai Kamu 🌼</h1>
    <p>Aku cuma mau bilang sesuatu yang udah lama aku simpan di hati...</p>
    <button onclick="tampilkanSurat()">Buka 💌</button>
  </div>

  <!-- Bagian Surat -->
  <div id="surat">
    <h1>Surat Cinta Buat Kamu 💖</h1>
    <p id="isiSurat">
      (Tulis isi surat cinta kamu di sini 😌  
      Misal:  
      “Aku gak tahu gimana caranya jelasin,  
      tapi setiap kali inget kamu, dunia rasanya lebih cerah...”)
    </p>
    <button onclick="tampilkanPesan()">Lanjut 👉</button>
  </div>

  <!-- Bagian Pesan Akhir -->
  <div id="pesan">
    <h2 id="teksAkhir">Kamu Selalu Jadi Warna Cerah di Hari-Hariku 🌈💞</h2>
  </div>

  <script>
    const music = document.getElementById('bgMusic');
    const musicButton = document.getElementById('musicButton');
    let isPlaying = false;

    function toggleMusic() {
      if (isPlaying) {
        music.pause();
        musicButton.textContent = "🎵 Putar Musik";
      } else {
        music.play();
        musicButton.textContent = "⏸️ Hentikan Musik";
      }
      isPlaying = !isPlaying;
    }

    function tampilkanSurat() {
      document.getElementById('awal').style.display = 'none';
      document.getElementById('surat').style.display = 'block';
    }

    function tampilkanPesan() {
      document.getElementById('surat').style.display = 'none';
      document.getElementById('pesan').style.display = 'block';
      mulaiLove();
    }

    function mulaiLove() {
      setInterval(() => {
        const love = document.createElement('div');
        love.classList.add('love');
        love.innerHTML = '💖';
        love.style.left = Math.random() * 100 + 'vw';
        love.style.fontSize = Math.random() * 20 + 20 + 'px';
        document.body.appendChild(love);
        setTimeout(() => love.remove(), 5000);
      }, 300);
    }
  </script>
</body>
</html>

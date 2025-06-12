<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Para Greisy 💕</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background-color: #ffe6f0;
      text-align: center;
      margin: 0;
      padding: 0;
      overflow: hidden;
    }

    h1 {
      font-size: 2em;
      color: #d6336c;
      margin-top: 100px;
    }

    #botones {
      margin-top: 40px;
    }

    button {
      padding: 15px 30px;
      font-size: 1em;
      margin: 10px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: 0.3s ease;
    }

    #si {
      background-color: #28a745;
      color: white;
    }

    #no {
      background-color: #dc3545;
      color: white;
      position: absolute;
    }

    #nueva-interfaz {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      background-image: url('https://i.postimg.cc/PJ7YmBn6/Imagen-de-Whats-App-2025-06-12-a-las-01-25-32-bc97681b.jpg');
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      text-align: center;
      padding: 20px;
      position: relative;
      overflow: hidden;
    }

    #nueva-interfaz h2 {
      font-size: 2em;
      color: #ffffff;
      margin-bottom: 20px;
      text-shadow: 2px 2px 4px #000;
    }

    #nueva-interfaz img {
      width: 150px;
      margin-top: 20px;
    }

    .corazon {
      position: absolute;
      color: #ff69b4;
      font-size: 2em;
      animation: caer 4s linear infinite;
      user-select: none;
    }

    @keyframes caer {
      0% {
        transform: translateY(-100px) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(100vh) rotate(360deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <div id="pantalla-inicial">
    <h1>GREISY ¿QUIERES SER MI NOVIA?</h1>
    <div id="botones">
      <button id="si">Sí</button>
      <button id="no">No</button>
    </div>
  </div>

  <div id="nueva-interfaz">
    <h2>GRACIAS POR ACEPTAR MELONCITO 💖</h2>
    <img src="https://media.tenor.com/KHPRspxWvuwAAAAi/yellow-dragon-nailong.gif" alt="Dino Kuning">
  </div>

  <!-- 🎵 MÚSICA DE VOCAROO -->
  <audio id="musica-romantica" loop>
    <source src="https://media.vocaroo.com/mp3/16SroHediQcE" type="audio/mpeg">
    Tu navegador no soporta audio.
  </audio>

  <script>
    const btnNo = document.getElementById('no');
    const btnSi = document.getElementById('si');
    const pantallaInicial = document.getElementById('pantalla-inicial');
    const nuevaInterfaz = document.getElementById('nueva-interfaz');
    const musica = document.getElementById('musica-romantica');
    let yaAceptado = false;

    btnNo.addEventListener('mouseover', () => {
      const maxX = window.innerWidth - btnNo.offsetWidth;
      const maxY = window.innerHeight - btnNo.offsetHeight;
      const randomX = Math.floor(Math.random() * maxX);
      const randomY = Math.floor(Math.random() * maxY);
      btnNo.style.left = randomX + 'px';
      btnNo.style.top = randomY + 'px';
    });

    btnSi.addEventListener('click', () => {
      if (yaAceptado) return;
      yaAceptado = true;

      pantallaInicial.style.display = 'none';
      nuevaInterfaz.style.display = 'flex';

      musica.play().catch((e) => {
        console.log("Audio bloqueado por el navegador:", e);
      });

      for (let i = 0; i < 50; i++) {
        const corazon = document.createElement('div');
        corazon.classList.add('corazon');
        corazon.innerText = '💖';
        corazon.style.left = Math.random() * 100 + 'vw';
        corazon.style.fontSize = (Math.random() * 20 + 10) + 'px';
        corazon.style.animationDuration = (Math.random() * 2 + 3) + 's';
        nuevaInterfaz.appendChild(corazon);

        setTimeout(() => {
          corazon.remove();
        }, 5000);
      }
    });
  </script>

</body>
</html>

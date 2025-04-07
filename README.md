<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>開光聖路｜互動導覽牆</title>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      background: #fdf7ec url('https://i.imgur.com/3k7x1bR.jpg') center/cover no-repeat;
      font-family: 'Noto Serif TC', serif;
      color: #3e2c1c;
    }
    .overlay {
      background-color: rgba(255, 247, 230, 0.85);
      padding: 3rem;
      min-height: 100vh;
    }
    .dialogue-box {
      background: url('https://i.imgur.com/j6RnD8k.png') center/cover;
      border: 3px solid #a97c50;
      border-radius: 16px;
      padding: 2rem;
      max-width: 900px;
      margin: 3rem auto;
      box-shadow: 0 6px 20px rgba(0,0,0,0.3);
      animation: glowIn 2s ease-in-out;
    }
    .dialogue-box p {
      font-size: 1.5rem;
      line-height: 2.2;
    }
    .choice {
      text-align: center;
      margin-top: 1.5rem;
    }
    .choice button {
      font-family: 'Noto Serif TC', serif;
      background-color: #fff4dd;
      border: 2px solid #a97c50;
      padding: 0.6rem 1.5rem;
      margin: 0.5rem;
      border-radius: 10px;
      font-size: 1.2rem;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    .choice button:hover {
      background-color: #ffe4b2;
      transform: scale(1.05);
    }
    @keyframes glowIn {
      from { opacity: 0; filter: brightness(0.5); }
      to { opacity: 1; filter: brightness(1); }
    }
  </style>
</head>
<body>
  <audio id="bgm" autoplay loop>
    <source src="https://cdn.pixabay.com/download/audio/2023/04/15/audio_d4e5733f7a.mp3" type="audio/mpeg">
  </audio>
  <audio id="voice1" src="https://cdn.pixabay.com/download/audio/2023/03/30/audio_72b97d91d4.mp3"></audio>
  <audio id="voice2" src="https://cdn.pixabay.com/download/audio/2022/11/21/audio_43e8d4bc84.mp3"></audio>

  <div class="overlay">
    <div class="dialogue-box" id="scene1">
      <p>📜「手執桃枝分世界，金鎗打開五岳門。打開路途萬里路，拜請中壇來點靈。」</p>
      <p>🧒【楊州童子】：「哪吒太子已現身相助，善信準備啟程否？」</p>
      <div class="choice">
        <button onclick="nextScene()">我已準備好，請引路 ➤</button>
        <button onclick="playVoice(1)">等等，我尚有疑問。</button>
      </div>
    </div>

    <div class="dialogue-box" style="display: none;" id="scene2">
      <p>🌫️「陰府路上速起程，急急轉身出壇門。值年太歲把關隘，獻錢獻紙買路過。」</p>
      <p>🚪【門神】：「若欲通行，需祭銀火紙以表誠意。」</p>
    </div>
  </div>

  <script>
    function nextScene() {
      document.getElementById('scene1').style.display = 'none';
      document.getElementById('scene2').style.display = 'block';
      playVoice(2);
    }

    function playVoice(index) {
      const voice = document.getElementById('voice' + index);
      if (voice) voice.play();
    }
  </script>
</body>
</html>


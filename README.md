# Surprise_From_MySide

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>A Special Surprise For You ❤️</title>
  <style>
    :root {
      /* Aesthetic Rose Pink & Masculine Slate Blue Theme */
      --pink-primary: #ff758f;
      --pink-dark: #ff4d6d;
      --pink-light: #fff0f3;
      --blue-primary: #2b4c7e;
      --blue-hover: #4a6fa5;
      --text: #2b2d42;
      --card-bg: rgba(255, 255, 255, 0.92); /* Semi-transparent white to see watermark */
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      padding: 20px;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      position: relative;
      background-color: var(--pink-light);
      color: var(--text);
      overflow-x: hidden;
    }

    /* Beautiful Love Watermark Background Layer */
    body::before {
      content: "";
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      opacity: 0.12; /* Keeps it subtle so it doesn't distract */
      /* Uses your first picture link as a beautiful repeating background watermark pattern */
      background-image: url('https://i.postimg.cc/SJmRZpSX/IMG-0902.jpg');
      background-size: 250px;
      background-position: center;
      filter: grayscale(30%);
    }

    /* Interactive Dashboard Container */
    .dashboard {
      max-width: 500px;
      width: 100%;
      background: var(--card-bg);
      border-radius: 30px;
      box-shadow: 0 15px 35px rgba(255, 117, 143, 0.2), 0 10px 20px rgba(43, 76, 126, 0.1);
      padding: 35px;
      box-sizing: border-box;
      text-align: center;
      margin-top: 20px;
      border: 2px solid rgba(255, 255, 255, 0.6);
      backdrop-filter: blur(8px); /* Premium frosted-glass style overlay */
      position: relative;
    }

    h1 {
      font-size: 2.3rem;
      margin-bottom: 5px;
      color: var(--blue-primary);
      text-shadow: 1px 1px 2px rgba(255, 117, 143, 0.3);
    }

    h1 span {
      color: var(--pink-dark);
    }

    .subtitle {
      font-size: 1.1rem;
      margin-bottom: 30px;
      color: var(--blue-hover);
      font-style: italic;
    }

    /* Memory Button Styling (Pink with Blue hover element) */
    .gallery-btn {
      display: inline-block;
      background: linear-gradient(135deg, var(--pink-primary), var(--pink-dark));
      color: white;
      text-decoration: none;
      padding: 16px 30px;
      font-size: 1.1rem;
      font-weight: bold;
      border-radius: 50px;
      box-shadow: 0 6px 18px rgba(255, 77, 109, 0.3);
      transition: all 0.3s ease;
      margin-bottom: 35px;
      width: 85%;
      border: none;
      cursor: pointer;
    }

    .gallery-btn:hover {
      background: linear-gradient(135deg, var(--blue-hover), var(--blue-primary));
      transform: translateY(-3px);
      box-shadow: 0 8px 22px rgba(43, 76, 126, 0.3);
    }

    /* Photo Gallery */
    .gallery-container {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.6s cubic-bezier(0.4, 0, 0.2, 1);
      margin-bottom: 20px;
    }

    .gallery-container.open {
      max-height: 1200px;
    }

    .photo-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px;
      padding: 10px 0 30px 0;
    }

    .photo-item {
      width: 100%;
      height: 160px;
      object-fit: cover;
      border-radius: 16px;
      border: 4px solid white;
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.08);
      transition: transform 0.3s ease;
    }

    .photo-item:hover {
      transform: scale(1.04) rotate(1deg);
    }

    .photo-item:nth-child(5) {
      grid-column: span 2;
      height: 230px;
    }

    /* Spin the Wheel Section */
    .wheel-section {
      border-top: 2px dashed rgba(255, 117, 143, 0.4);
      padding-top: 35px;
      position: relative;
    }

    h2 {
      font-size: 1.4rem;
      margin-bottom: 25px;
      color: var(--blue-primary);
    }

    .wheel-container {
      position: relative;
      width: 300px;
      height: 300px;
      margin: 0 auto 30px auto;
    }

    /* Sleek Pointer Indicator */
    .pointer {
      position: absolute;
      top: -18px;
      left: 50%;
      transform: translateX(-50%);
      width: 0;
      height: 0;
      border-left: 15px solid transparent;
      border-right: 15px solid transparent;
      border-top: 28px solid var(--pink-dark);
      z-index: 10;
      filter: drop-shadow(0 3px 5px rgba(0,0,0,0.15));
    }

    /* Rebalanced Rose Pink & Blue Alternating Slices */
    .wheel {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      border: 8px solid var(--blue-primary);
      position: relative;
      overflow: hidden;
      transition: transform 4s cubic-bezier(0.1, 1, 0.1, 1);
      box-sizing: border-box;
      box-shadow: 0 8px 25px rgba(43, 76, 126, 0.2);
      background: conic-gradient(
        var(--pink-primary) 0deg 72deg, 
        var(--blue-hover) 72deg 144deg, 
        var(--pink-dark) 144deg 216deg, 
        var(--blue-primary) 216deg 288deg,
        #f4a261 288deg 360deg      /* Soft secondary sunset accent */
      );
    }

    .slice-label {
      position: absolute;
      width: 50%;
      height: 50%;
      transform-origin: bottom right;
      bottom: 50%;
      right: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      box-sizing: border-box;
      padding-left: 20px;
      padding-bottom: 50px;
      font-weight: bold;
      color: white;
      font-size: 0.8rem;
      text-shadow: 1px 1px 3px rgba(0,0,0,0.6);
      text-align: center;
      line-height: 1.2;
    }

    .label1 { transform: rotate(36deg); }
    .label2 { transform: rotate(108deg); }
    .label3 { transform: rotate(180deg); }
    .label4 { transform: rotate(252deg); }
    .label5 { transform: rotate(324deg); }

    /* Blue Spin Button */
    .spin-btn {
      background: linear-gradient(135deg, var(--blue-hover), var(--blue-primary));
      color: white;
      border: none;
      padding: 14px 40px;
      font-size: 1.05rem;
      font-weight: bold;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(43, 76, 126, 0.3);
      transition: all 0.2s ease;
    }

    .spin-btn:hover {
      background: linear-gradient(135deg, var(--pink-dark), var(--pink-primary));
      box-shadow: 0 6px 18px rgba(255, 77, 109, 0.3);
      transform: scale(1.03);
    }

    .spin-btn:disabled {
      background: #cbd5e1;
      color: #94a3b8;
      cursor: not-allowed;
      box-shadow: none;
      transform: none;
    }

    .result-display {
      margin-top: 25px;
      font-size: 1.35rem;
      font-weight: bold;
      color: var(--pink-dark);
      min-height: 35px;
      animation: pulse 1.5s infinite alternate;
    }
  </style>
</head>
<body>

  <div class="dashboard">
    <!-- Theme Title -->
    <h1>I Love You So Much! <span>❤️</span></h1>
    <p class="subtitle">A special dashboard built just for you...</p>

    <!-- Interactive Memories Button -->
    <button class="gallery-btn" onclick="toggleGallery()">✨ Our Favorite Memories ✨</button>

    <!-- Photo Gallery Grid with Your Images -->
    <div class="gallery-container" id="photoGallery">
      <div class="photo-grid">
        <img class="photo-item" src="https://i.postimg.cc/SJmRZpSX/IMG-0902.jpg" alt="Memory 1">
        <img class="photo-item" src="https://i.postimg.cc/ppPr0tWh/IMG-0903.jpg" alt="Memory 2">
        <img class="photo-item" src="https://i.postimg.cc/tY9JrHqV/IMG-0904.jpg" alt="Memory 3">
        <img class="photo-item" src="https://i.postimg.cc/HVTnSCY8/IMG-0905.jpg" alt="Memory 4">
        <img class="photo-item" src="https://i.postimg.cc/TpT1kXdK/IMG-0906.jpg" alt="Memory 5">
      </div>
    </div>

    <!-- Spin the Wheel Section -->
    <div class="wheel-section">
      <h2>Let's let fate decide what should we plan... 🤭</h2>
      
      <div class="wheel-container">
        <div class="pointer"></div>
        <div class="wheel" id="luckyWheel">
          <div class="slice-label label1">Romantic Dinner 🌹</div>
          <div class="slice-label label2">Weekend Gateway 🚗</div>
          <div class="slice-label label3">Hookah Beach 🏖️</div>
          <div class="slice-label label4">Movie Night In 🍿</div>
          <div class="slice-label label5">Long Drive 🛣️</div>
        </div>
      </div>

      <button class="spin-btn" id="spinButton" onclick="spinTheWheel()">Spin the Wheel!</button>
      <div class="result-display" id="resultMessage"></div>
    </div>
  </div>

  <script>
    function toggleGallery() {
      const gallery = document.getElementById('photoGallery');
      gallery.classList.toggle('open');
    }

    let currentRotation = 0;

    function spinTheWheel() {
      const wheel = document.getElementById('luckyWheel');
      const button = document.getElementById('spinButton');
      const result = document.getElementById('resultMessage');

      button.disabled = true;
      result.innerText = "Spinning...";

      // Matches options to your 5 sectors perfectly (mapped to rotation angles)
      const options = [
        "Romantic Dinner 🌹",
        "Long Drive 🛣️",
        "Movie Night In 🍿",
        "Hookah Beach 🏖️",
        "Weekend Gateway 🚗"
      ];

      const randomIndex = Math.floor(Math.random() * 5);
      const sliceDegrees = randomIndex * 72;
      const minimumSpins = 1800; 
      
      currentRotation += minimumSpins + sliceDegrees;
      wheel.style.transform = `rotate(${currentRotation}deg)`;

      setTimeout(() => {
        result.innerText = `🎉 Fate has chosen: ${options[randomIndex]}!`;
        button.disabled = false;
      }, 4000);
    }
  </script>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Be My Valentine?</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
      color: #fff;
      text-align: center;
    }

    .card {
      width: 100%;
      max-width: 360px;
      background: rgba(255, 255, 255, 0.15);
      border-radius: 20px;
      padding: 30px 20px 40px;
      box-shadow: 0 15px 40px rgba(0, 0, 0, 0.25);
      position: relative;
      overflow: hidden;
    }

    .gif {
      width: 160px;
      margin: 0 auto 15px;
    }

    .gif img {
      width: 100%;
      height: auto;
    }

    h1 {
      font-size: 2.1rem;
      margin: 10px 0;
    }

    h2 {
      font-weight: 400;
      font-size: 1.2rem;
      margin-bottom: 20px;
    }

    p {
      font-size: 1rem;
      line-height: 1.5;
      margin-bottom: 22px;
    }

    .buttons {
      position: relative;
      height: 100px;
      margin-top: 10px;
    }

    button {
      border: none;
      border-radius: 30px;
      padding: 12px 22px;
      font-size: 1rem;
      cursor: pointer;
      white-space: nowrap;
      transition: transform 0.2s ease;
    }

    #yesBtn {
      background-color: #ff2f68;
      color: white;
      transform: scale(1);
    }

    #noBtn {
      background-color: #ffffff;
      color: #ff2f68;
      position: absolute;
      left: 55%;
      top: 10px;
    }
  </style>
</head>
<body>
  <div class="card">
    <div class="gif">
      <img src="cute-love-bear-roses-ou7zho5oosxnpo6k.gif" alt="Cute bear with flowers">
    </div>

    <h1>Be My Valentine?</h1>
    <h2>Hey, Diana</h2>

    <p>
      Valentine’s Day plans?<br>
      Food, laughs, and a very good decision 😌
    </p>

    <p>
      📅 February 14<br />
      📍 In Rai
    </p>

    <div class="buttons">
      <button id="yesBtn">Yes 💖</button>
      <button id="noBtn">No 🙃</button>
    </div>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");

    let escapeCount = 0;
    let yesScale = 1;

    const sassyTexts = [
      "No 🙃",
      "Are you sure?",
      "Wrong choice 😏",
      "Try again",
      "Almost clicked yes",
      "Furi Curent"
    ];

    function moveNoButton() {
      escapeCount++;

      // Grow YES button
      yesScale += 0.15;
      yesBtn.style.transform = `scale(${yesScale})`;

      // Move NO button
      const card = document.querySelector(".card");
      const maxX = card.clientWidth - noBtn.clientWidth;
      const maxY = card.clientHeight - noBtn.clientHeight;

      const x = Math.random() * maxX;
      const y = Math.random() * maxY;

      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;

      // Update NO text
      const textIndex = Math.min(escapeCount, sassyTexts.length - 1);
      noBtn.textContent = sassyTexts[textIndex];
    }

    noBtn.addEventListener("mouseover", moveNoButton);
    noBtn.addEventListener("touchstart", moveNoButton);

    yesBtn.addEventListener("click", () => {
      document.body.innerHTML = `
        <div style="
          min-height:100vh;
          display:flex;
          align-items:center;
          justify-content:center;
          background:linear-gradient(135deg,#ff758c,#ff7eb3);
          color:white;
          font-family:system-ui;
          text-align:center;
          padding:20px;">
          <div>
            <h1>Perfect choice 💘</h1>
            <p style="font-size:1.3rem; margin-top:15px;">
              Mac and Cheese la mine<br>
              plus desert (EU) 😌
            </p>
          </div>
        </div>
      `;
    });
  </script>
</body>
</html>

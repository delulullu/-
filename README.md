<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For You</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      background: linear-gradient(to right, #fdfbfb, #ebedee);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-family: 'Poppins', sans-serif;
      text-align: center;
      overflow: hidden;
    }

    h1 {
      color: #333;
      margin-bottom: 40px;
      padding: 0 20px;
      font-size: 5vw;
      max-width: 90%;
    }

    .buttons {
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 15px;
    }

    button {
      font-size: 5vw;
      padding: 12px 24px;
      min-width: 150px;
      max-width: 250px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s ease;
      box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    }

    #yes {
      background-color: #7ed6df;
      color: #fff;
    }

    #no {
      background-color: #dff9fb;
      color: #130f40;
      position: absolute;
    }
  </style>
</head>
<body>

  <h1>Will you promise me to do your best and not be sad no matter what happens?</h1>

  <div class="buttons">
    <button id="yes">Yes</button>
    <button id="no">No</button>
  </div>

  <script>
    const noBtn = document.getElementById('no');
    const yesBtn = document.getElementById('yes');

    function moveButton() {
      const screenPadding = 20; // avoid going outside screen
      const i = Math.random() * (window.innerWidth - noBtn.offsetWidth - screenPadding);
      const j = Math.random() * (window.innerHeight - noBtn.offsetHeight - screenPadding);
      noBtn.style.left = i + 'px';
      noBtn.style.top = j + 'px';
    }

    noBtn.addEventListener('mouseover', moveButton); // for computer
    noBtn.addEventListener('touchstart', function(e) {
      e.preventDefault(); // prevent accidental tap
      moveButton();
    }, { passive: false }); // important for touch screens
    
    yesBtn.addEventListener('click', () => {
      document.body.innerHTML = `
        <h1 style="color:#6D214F; padding: 20px; font-size: 6vw;">
          I knew you'd say yes.<br><br>
          I believe in you so much.<br><br>
          I love you.
        </h1>
      `;
    });
  </script>

</body>
</html>

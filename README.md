<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Old Friends Meet Up v1</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #1e3c72, #2a5298);
      color: white;
      text-align: center;
      padding: 50px;
    }
    .card {
      background: rgba(255, 255, 255, 0.1);
      border-radius: 15px;
      padding: 30px;
      max-width: 600px;
      margin: auto;
      box-shadow: 0px 4px 15px rgba(0,0,0,0.3);
    }
    h1 {
      font-size: 2.5em;
      margin-bottom: 10px;
    }
    h2 {
      margin: 8px 0;
    }
    .btn {
      background: #ffcc00;
      color: #333;
      padding: 12px 25px;
      border: none;
      border-radius: 8px;
      font-size: 1.1em;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
      margin-top: 20px;
    }
    .btn:hover {
      background: #ffaa00;
    }
    #countdown {
      font-size: 1.5em;
      margin: 20px 0;
      font-weight: bold;
    }
    .flags {
      margin-top: 30px;
    }
    textarea {
      width: 80%;
      height: 100px;
      border-radius: 8px;
      border: none;
      padding: 10px;
      font-size: 1em;
      resize: none;
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>🎉 Old Friends Meet Up v1 🎉</h1>
    <p>Let’s catch up, share memories, and reconnect!</p>
    <h2>📅 Date: Saturday, October 12th, 2025</h2>
    <h2>🕒 Time: 7:00 PM EST</h2>
    <h2>📍 Location: Online (Zoom)</h2>

    <div id="countdown">Loading countdown...</div>

    <a class="btn" href="https://zoom.us/j/your-zoom-link" target="_blank">Join Zoom Call</a>

    <p>RSVP here: <a href="https://forms.gle/your-google-form" target="_blank" style="color:#ffcc00;">Google Form</a></p>

    <div class="flags">
      <h2>🌍 Represent Your Country!</h2>
      <p>Add your flag emoji below so we can see where everyone is joining from:</p>
      <textarea placeholder="🇺🇸 🇬🇧 🇳🇬 🇨🇦 ..."></textarea>
    </div>
  </div>

  <script>
    // Countdown Timer
    const eventDate = new Date("Oct 12, 2025 19:00:00 EST").getTime();

    const countdownFunction = setInterval(() => {
      const now = new Date().getTime();
      const distance = eventDate - now;

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById("countdown").innerHTML = 
        `${days}d ${hours}h ${minutes}m ${seconds}s until the meetup!`;

      if (distance < 0) {
        clearInterval(countdownFunction);
        document.getElementById("countdown").innerHTML = "The meetup has started! 🎉";
      }
    }, 1000);
  </script>
</body>
</html>

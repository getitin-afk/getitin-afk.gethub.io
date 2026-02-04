<html lang="en">
<head>
<meta charset="UTF-8">
<title>From getitin</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  * { box-sizing: border-box; }

  body {
    margin: 0;
    min-height: 100vh;
    font-family: "Times New Roman", Times, serif;
    background: linear-gradient(135deg, #ffb6c1, #ffc0cb);
    color: #4b0033;
  }

  .screen {
    min-height: 100vh;
    padding: 24px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  h1, h2 {
    text-align: center;
    color: #8b004f;
  }

  input, button {
    width: 100%;
    max-width: 400px;
    padding: 12px;
    border-radius: 16px;
    border: none;
    font-family: "Times New Roman";
    font-size: 16px;
    margin-top: 10px;
  }

  button {
    background: #ff69b4;
    color: white;
    cursor: pointer;
  }

  /* HOME CARD */
  .home-card {
    background: rgba(255,255,255,0.85);
    border-radius: 26px;
    padding: 26px;
    max-width: 600px;
    width: 100%;
    box-shadow: 0 10px 35px rgba(0,0,0,0.15);
  }

  /* Tabs */
  .tabs {
    display: flex;
    gap: 10px;
    margin: 20px 0;
  }

  .tab {
    flex: 1;
    padding: 10px;
    border-radius: 18px;
    background: #ff69b4; /* Pink background */
    text-align: center;
    cursor: pointer;
    font-size: 14px;
    color: white; /* White text */
    transition: background 0.3s;
  }

  .tab:hover {
    background: #ff85c1; /* Lighter pink on hover */
  }

  .tab.active {
    background: #d63f7f; /* Darker pink for active tab */
  }

  .content {
    display: none;
    background: rgba(255,255,255,0.85);
    border-radius: 22px;
    padding: 20px;
    max-height: 60vh;
    overflow-y: auto;
    font-size: 17px;
    line-height: 1.5;
  }

  .content.active { display: block; }

  audio {
    width: 100%;
    margin-top: 10px;
  }

  .gallery {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
    margin-top: 14px;
  }

  .gallery img {
    width: 100%;
    height: 180px;
    object-fit: cover;
    border-radius: 16px;
  }
</style>
</head>

<body>

<!-- PASSWORD SCREEN -->
<div id="login" class="screen">
  <h1>Who Named Your Boobs >3</h1>
  <input id="answer" placeholder="type here…">
  <button onclick="unlock()">Submit</button>
</div>

<!-- HOME SCREEN -->
<div id="home" class="screen" style="display:none;">
  <div class="home-card">

    <h2>Welcome baby girl 💗</h2>
    <p style="text-align:center;">Enjoy your stay</p>

    <div class="tabs">
      <div class="tab" onclick="show('love', this)">💌 Love Letter??</div>
      <div class="tab" onclick="show('music', this)">🎶 Music</div>
      <div class="tab" onclick="show('notes', this)">📝 Notes</div>
      <div class="tab" onclick="show('gallery', this)">🖼 Gallery</div>
    </div>

    <!-- Love Letter?? -->
    <div id="love" class="content">
      since you didnt want any valentines gift this is what i thought of.
      You know you could always send me selfies of michael and Felix any day
      that you want. XoXo
    </div>

    <!-- MUSIC -->
    <div id="music" class="content">
      <strong>No Guidance — Drake ft Chris Brown</strong>
      <audio controls>
        <source src="jayy/no-guidance.mp3" type="audio/mpeg">
      </audio>

      <br><br>

      <strong>WGFT — Gunna</strong>
      <audio controls>
        <source src="jayy/wgft.mp3" type="audio/mpeg">
      </audio>
    </div>

    <!-- Notes -->
    <div id="notes" class="content">
      you know we can always touch, kiss, cuddle and do the other stuff
      right as friends of course... >3
    </div>

    <!-- Gallery -->
    <div id="gallery" class="content">
      <strong>our To-Do list ❤️</strong>
      <div class="gallery">
        <img src="jayy/image1.jpg">
        <img src="jayy/image2.jpg">
        <img src="jayy/image3.jpg">
        <img src="jayy/image4.jpg">
        <img src="jayy/image5.jpg">
        <img src="jayy/image6.jpg">
        <img src="jayy/image7.jpg">
      </div>
    </div>

  </div>
</div>

<script>
  function unlock() {
    const ans = document.getElementById("answer").value.toLowerCase().trim();
    if (ans === "michael") {
      document.getElementById("login").style.display = "none";
      document.getElementById("home").style.display = "flex";
    } else {
      alert("wrong answer 😏");
    }
  }

  function show(id, tabElement) {
    // Show content
    document.querySelectorAll(".content").forEach(c => c.classList.remove("active"));
    document.getElementById(id).classList.add("active");

    // Highlight active tab
    document.querySelectorAll(".tab").forEach(t => t.classList.remove("active"));
    tabElement.classList.add("active");
  }
</script>

</body>
</html>


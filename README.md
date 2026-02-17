<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>I Love You</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #111;
      color: #fff;
      text-align: center;
      padding: 20px;
    }
    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      margin-top: 20px;
    }
    .card {
      position: relative;
      width: 280px;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 8px 20px rgba(0,0,0,0.4);
      background: #000;
    }
    .card img {
      width: 100%;
      display: block;
    }
    .overlay {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      padding: 12px;
      background: linear-gradient(to top, rgba(0,0,0,0.85), rgba(0,0,0,0));
      text-align: left;
    }
    .overlay h2 {
      margin: 0;
      font-size: 20px;
      color: #ff4b7a;
    }
    .overlay p {
      margin: 4px 0 0;
      font-size: 14px;
      line-height: 1.4;
    }
    h1 {
      color: #ff4b7a;
      letter-spacing: 2px;
    }
  </style>
</head>
<body>

  <h1>I LOVE YOU ❤️</h1>
  <p>You are brilliant, beautiful, and endlessly inspiring.</p>

  <div class="gallery">
    <div class="card">
      <img src="image1.jpg" alt="">
      <div class="overlay">
        <h2>I love you</h2>
        <p>Your dedication and strength shine so brightly.</p>
      </div>
    </div>

    <div class="card">
      <img src="image2.jpg" alt="">
      <div class="overlay">
        <h2>I love you</h2>
        <p>Your beauty and confidence light up every space.</p>
      </div>
    </div>

    <div class="card">
      <img src="image3.jpg" alt="">
      <div class="overlay">
        <h2>I love you</h2>
        <p>Your passion and grace make you unforgettable.</p>
      </div>
    </div>
  </div>

</body>
</html>

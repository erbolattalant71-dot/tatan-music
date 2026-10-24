
<!DOCTYPE html>
<html lang="kk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#080808">
  <title>Graduation — Музыка таңдаңыз</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      min-height: 100vh;
      min-height: 100dvh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
      background: #080808;
      color: #f5f5f5;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI",
                   Roboto, Arial, sans-serif;
    }

    .container {
      width: 100%;
      max-width: 420px;
      text-align: center;
    }

    .label {
      margin-bottom: 18px;
      color: #888;
      font-size: 11px;
      letter-spacing: 4px;
      text-transform: uppercase;
    }

    h1 {
      margin-bottom: 12px;
      font-size: clamp(32px, 8vw, 46px);
      font-weight: 600;
      letter-spacing: -1.5px;
    }

    .subtitle {
      margin-bottom: 38px;
      color: #999;
      font-size: 14px;
      line-height: 1.7;
    }

    .album {
      margin-bottom: 28px;
      padding: 23px 20px;
      border: 1px solid #292929;
      border-radius: 18px;
      background: #111;
    }

    .album-icon {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 68px;
      height: 68px;
      margin: 0 auto 16px;
      border-radius: 14px;
      background: linear-gradient(145deg, #292929, #101010);
      color: #fff;
      font-size: 27px;
    }

    .album-title {
      margin-bottom: 7px;
      font-size: 20px;
      font-weight: 600;
    }

    .album-description {
      color: #888;
      font-size: 12px;
    }

    .section-title {
      margin-bottom: 15px;
      color: #888;
      font-size: 11px;
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    .music-links {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    .music-button {
      display: flex;
      align-items: center;
      justify-content: space-between;
      width: 100%;
      min-height: 58px;
      padding: 0 20px;
      border: 1px solid #303030;
      border-radius: 14px;
      background: #121212;
      color: #f5f5f5;
      text-decoration: none;
      font-size: 15px;
      font-weight: 500;
      transition: background 0.2s, border-color 0.2s,
                  transform 0.2s;
    }

    .music-button:hover {
      background: #1d1d1d;
      border-color: #666;
      transform: translateY(-2px);
    }

    .button-left {
      display: flex;
      align-items: center;
      gap: 13px;
    }

    .platform-icon {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 28px;
      height: 28px;
      border-radius: 8px;
      background: #242424;
      color: #fff;
      font-size: 13px;
      font-weight: 700;
    }

    .arrow {
      color: #777;
      font-size: 19px;
    }

    .footer {
      margin-top: 36px;
      color: #666;
      font-size: 11px;
      line-height: 1.8;
      letter-spacing: 1px;
    }

    .footer span {
      color: #999;
    }

    @media (max-width: 360px) {
      body {
        padding: 18px;
      }

      .album {
        padding: 20px 15px;
      }

      .music-button {
        padding: 0 15px;
      }
    }
  </style>
</head>

<body>
  <main class="container">
    <div class="label">Бір ән · Өзің таңда</div>

    <h1>Graduation</h1>

    <p class="subtitle">
      Музыканы таңдаңыз.<br>
      Әнді өзіңізге ыңғайлы платформада тыңдаңыз.
    </p>

    <section class="album">
      <div class="album-icon">♫</div>
      <div class="album-title">Graduation</div>
      <div class="album-description">
        Ән · Музыка сілтемесі
      </div>
    </section>

    <div class="section-title">Платформаны таңдаңыз</div>

    <nav class="music-links">
      <a
        class="music-button"
        href="https://music.apple.com/kz/album/graduation/1451901307"
        target="_blank"
        rel="noopener noreferrer"
      >
        <span class="button-left">
          <span class="platform-icon">♫</span>
          <span>Apple Music</span>
        </span>
        <span class="arrow">↗</span>
      </a>

      <a
        class="music-button"
        href="https://open.spotify.com/album/4SZko61aMnmgvNhfhgTuD3?si=jra0XHNqT66WVvyB_70Ffg"
        target="_blank"
        rel="noopener noreferrer"
      >
        <span class="button-left">
          <span class="platform-icon">S</span>
          <span>Spotify</span>
        </span>
        <span class="arrow">↗</span>
      </a>
    </nav>

    <footer class="footer">
      <div>Музыка сүйер қауымға арналады</div>
      <div><span>Жақындат · Таңда · Тыңда</span></div>
    </footer>
  </main>
</body>
</html>


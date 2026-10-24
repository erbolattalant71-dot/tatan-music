<!DOCTYPE html>
<html lang="kk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#080808">
  <title>Музыканы таңдаңыз</title>
  <style>
    :root { color-scheme: dark; }
    * { box-sizing: border-box; }
    body {
      margin: 0; min-height: 100vh; display: grid; place-items: center;
      padding: 28px 18px; background:
      radial-gradient(ellipse at 50% 0%, #252525 0%, #101010 36%, #070707 75%);
      color: #f6f6f6; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }
    .page { width: 100%; max-width: 420px; }
    .mark {
      width: 66px; height: 66px; margin: 0 auto 22px; border-radius: 22px;
      display: grid; place-items: center; background: #f3f3f3; color: #090909;
      font-size: 28px; box-shadow: 0 10px 38px #0008;
    }
    .eyebrow { text-align: center; color: #8c8c8c; font-size: 11px; letter-spacing: .20em; text-transform: uppercase; }
    h1 { text-align: center; margin: 10px 0 8px; font-size: clamp(28px, 8vw, 36px); letter-spacing: -.045em; font-weight: 650; }
    .sub { text-align: center; color: #9b9b9b; font-size: 14px; margin: 0 0 30px; }
    .track {
      border: 1px solid #2b2b2b; border-radius: 20px; padding: 18px;
      background: linear-gradient(145deg, #1a1a1a, #101010); margin-bottom: 18px;
    }
    .track-label { color: #777; font-size: 10px; letter-spacing: .15em; text-transform: uppercase; }
    .track-name { font-size: 17px; margin-top: 7px; font-weight: 600; }
    .track-hint { font-size: 12px; color: #858585; margin-top: 5px; line-height: 1.5; }
    .apps { display: grid; gap: 10px; }
    a.app {
      min-height: 66px; display: flex; align-items: center; gap: 13px;
      padding: 12px 15px; border: 1px solid #292929; border-radius: 17px;
      color: #f5f5f5; text-decoration: none; background: #121212;
      transition: transform .15s ease, border-color .15s ease, background .15s ease;
    }
    a.app:hover, a.app:focus-visible { border-color: #646464; background: #1b1b1b; transform: translateY(-1px); outline: none; }
    .app-icon { width: 39px; height: 39px; flex: 0 0 39px; display: grid; place-items: center; border-radius: 12px; font-weight: 700; font-size: 19px; }
    .apple { background: linear-gradient(145deg, #ff7a8b, #b91f52); }
    .spotify { background: #1ed760; color: #071a0c; }
    .other { background: #292929; color: #eee; }
    .app-text { flex: 1; min-width: 0; }
    .app-title { font-size: 14px; font-weight: 600; }
    .app-desc { margin-top: 4px; font-size: 11px; color: #888; }
    .arrow { color: #777; font-size: 20px; padding-left: 6px; }
    .foot { text-align: center; color: #656565; font-size: 11px; line-height: 1.7; margin-top: 24px; }
    .foot span { color: #aaa; }
    .error { color: #e9a5a5; font-size: 12px; text-align: center; margin-top: 12px; display:none; }
  </style>
</head>
<body>
  <main class="page">
    <div class="mark" aria-hidden="true">♫</div>
    <div class="eyebrow">Бір ән · Өзің таңда</div>
    <h1>Музыканы таңдаңыз.</h1>
    <p class="sub">Әнді өзіңізге ыңғайлы платформада тыңдаңыз.</p>

    <section class="track" aria-label="Таңдалған ән">
      <div class="track-label">Ән · Музыка сілтемесі</div>
      <div class="track-name" id="trackName">Ән атауы</div>
      <div class="track-hint" id="trackHint">Төменнен музыка сервисін таңдап, әнді ашыңыз.</div>
    </section>

    <nav class="apps" aria-label="Музыка сервисін таңдаңыз">
      <a class="app" id="appleBtn" href="#" target="_blank" rel="noopener noreferrer">
        <span class="app-icon apple">♪</span>
        <span class="app-text"><span class="app-title">Apple Music</span><br><span class="app-desc">Әнді ашу</span></span>
        <span class="arrow">↗</span>
      </a>
      <a class="app" id="spotifyBtn" href="#" target="_blank" rel="noopener noreferrer">
        <span class="app-icon spotify">≋</span>
        <span class="app-text"><span class="app-title">Spotify</span><br><span class="app-desc">Әнді ашу</span></span>
        <span class="arrow">↗</span>
      </a>
      <a class="app" id="otherBtn" href="#" target="_blank" rel="noopener noreferrer">
        <span class="app-icon other">＋</span>
        <span class="app-text"><span class="app-title" id="otherLabel">Басқа платформа</span><br><span class="app-desc">Әнді ашу</span></span>
        <span class="arrow">↗</span>
      </a>
    </nav>
    <p class="error" id="errorMsg">Бұл платформаның сілтемесі әлі қосылмаған. Алдымен веб-беттегі сілтемені өзгертіңіз.</p>
    <footer class="foot">Музыка сүйер қауымға арналады<br><span>Жақындат · Таңда · Тыңда</span></footer>
  </main>

  <script>
    /*
      БАПТАУ: Төмендегі мәндерді әр платформадағы БІР ӘННІҢ сілтемелерімен ауыстырыңыз.
      Сілтемелерді тырнақша ішінде қалдырыңыз.
    */
    const MUSIC = {
      title: "Graduation— Kanye West",
      appleMusic: "https://music.apple.com/kz/album/graduation/1451901307",
      spotify: "https://open.spotify.com/album/4SZko61aMnmgvNhfhgTuD3?si=jra0XHNqT66WVvyB_70Ffg",
      otherName: "Yandex Music",
      other: "https://example.com/"
    };

    document.title = MUSIC.title + " · Музыканы таңдаңыз";
    document.getElementById("trackName").textContent = MUSIC.title;
    document.getElementById("appleBtn").href = MUSIC.appleMusic;
    document.getElementById("spotifyBtn").href = MUSIC.spotify;
    document.getElementById("otherBtn").href = MUSIC.other;
    document.getElementById("otherLabel").textContent = MUSIC.otherName;

    function isPlaceholder(url) {
      return !url || url === "https://music.apple.com/" ||
        url === "https://open.spotify.com/" || url === "https://example.com/";
    }
    [["appleBtn", MUSIC.appleMusic], ["spotifyBtn", MUSIC.spotify], ["otherBtn", MUSIC.other]]
      .forEach(([id, url]) => {
        document.getElementById(id).addEventListener("click", function (event) {
          if (isPlaceholder(url)) {
            event.preventDefault();
            document.getElementById("errorMsg").style.display = "block";
          }
        });
      });
  </script>
</body>
</html>

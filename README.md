<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>🌸 Magical Horizon - Sunshine Days Archive 🌸</title>

<!-- Pixel font -->
<link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap" rel="stylesheet" />

<style>
  /* --- BASE STYLES --- */
  @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

  body {
    margin: 0; padding: 30px;
    background: linear-gradient(135deg, #ffd1dc 25%, #ffe6f0 75%);
    font-family: 'Press Start 2P', cursive, monospace;
    color: #7a2e82;
    user-select: none;
    overflow-x: hidden;
  }

  /* Stars and sun decorations in background */
  body::before, body::after {
    content: '';
    position: fixed;
    pointer-events: none;
    z-index: 0;
  }
  body::before {
    top: 15vh; left: 5vw;
    width: 180px; height: 180px;
    background:
      radial-gradient(circle at 50% 50%, #ffceeb 30%, transparent 70%),
      repeating-radial-gradient(circle at center, #ffb6ce 0 5px, transparent 5px 10px);
    border-radius: 50%;
    box-shadow: 0 0 20px 6px #ffc0de;
  }
  body::after {
    bottom: 20vh; right: 5vw;
    width: 120px; height: 120px;
    background:
      radial-gradient(circle at 40% 40%, #fff1f8 30%, transparent 70%),
      repeating-radial-gradient(circle at center, #ff9ccc 0 3px, transparent 3px 7px);
    border-radius: 50%;
    box-shadow: 0 0 18px 5px #ffa1cc;
  }

  #container {
    position: relative;
    max-width: 960px;
    margin: 0 auto;
    background: #fff0f7;
    border: 6px solid #ff8fbc;
    border-radius: 20px;
    padding: 25px 40px 50px 40px;
    box-shadow: 0 0 25px #ffbfd7;
    z-index: 1;
  }

  header {
    text-align: center;
    font-size: 1.6rem;
    margin-bottom: 30px;
    color: #d64161;
    text-shadow: 2px 2px 0 #fff;
  }

  #banner {
    text-align: center;
    margin-bottom: 30px;
  }
  #banner img {
    width: 260px;
    image-rendering: pixelated;
    border: 5px solid #ff7fbf;
    border-radius: 16px;
    box-shadow: 0 0 15px #ffaad2;
  }

  nav {
    background: #ffd1dc;
    border: 4px dashed #ff6ea7;
    border-radius: 14px;
    padding: 20px 30px;
    margin-bottom: 30px;
  }

  nav ul {
    list-style: none;
    padding-left: 0;
    margin: 0;
  }

  nav > ul > li {
    font-size: 1rem;
    margin-bottom: 14px;
  }

  nav > ul > li > span {
    cursor: pointer;
    border: 3px solid #ff6ea7;
    background: #fff0f7;
    color: #d64161;
    display: inline-block;
    padding: 12px 20px;
    border-radius: 14px;
    transition: background 0.3s, color 0.3s;
    user-select: none;
  }

  nav > ul > li > span:hover {
    background: #ff7fbf;
    color: white;
  }

  .submenu {
    margin-top: 10px;
    margin-left: 22px;
    display: none;
  }

  .submenu li {
    font-size: 0.8rem;
    padding: 10px 16px;
    margin-bottom: 10px;
    border-radius: 12px;
    border: 2px solid #ff9ecf;
    background: #ffe4f2;
    color: #c83274;
    cursor: pointer;
    transition: background 0.25s;
    user-select: none;
  }

  .submenu li:hover {
    background: #ffb4d8;
  }

  main#content {
    min-height: 200px;
    border: 3px dotted #ff6ea7;
    border-radius: 14px;
    background: #fff0f7;
    padding: 25px;
    font-size: 1rem;
    color: #9f2e6f;
    box-shadow: inset 0 0 12px #ff9ecf;
    text-shadow:
      1px 1px #ffbad2,
      2px 2px #ff8fbf;
    line-height: 1.4;
    user-select: text;
  }

  button#translateBtn {
    margin-top: 30px;
    background: #ff6ea7;
    border: none;
    padding: 14px 32px;
    font-family: 'Press Start 2P', cursive;
    font-size: 0.75rem;
    color: white;
    border-radius: 28px;
    cursor: pointer;
    transition: background 0.3s;
    user-select: none;
  }

  button#translateBtn:hover {
    background: #ff2d94;
  }

  /* Dropdown for translation */
  #langMenu {
    display: none;
    margin-top: 15px;
  }

  #langMenu button {
    margin: 6px 8px 0 0;
    padding: 10px 20px;
    border: none;
    border-radius: 22px;
    background: #ff9ecf;
    color: #7a2e82;
    font-family: 'Press Start 2P', cursive;
    cursor: pointer;
    transition: background 0.3s;
    user-select: none;
  }

  #langMenu button:hover {
    background: #ff6ea7;
    color: white;
  }

  /* Fake comments section */
  #comments {
    margin-top: 40px;
    background: #ffe4f2;
    border-radius: 20px;
    border: 3px solid #ff6ea7;
    padding: 20px 30px;
    font-size: 0.8rem;
    color: #c83274;
    max-height: 240px;
    overflow-y: auto;
  }

  #comments h3 {
    text-align: center;
    font-size: 1rem;
    margin-bottom: 18px;
    text-shadow: 1px 1px #ffbad2;
  }

  .comment {
    margin-bottom: 18px;
    border-bottom: 1px dashed #ff9ecf;
    padding-bottom: 12px;
  }

  .comment:last-child {
    border-bottom: none;
  }

  .comment .username {
    font-weight: 700;
    cursor: pointer;
    color: #d64161;
    text-shadow: 1px 1px #fff;
  }

  .comment .date {
    font-size: 0.7rem;
    color: #b14a7f;
    margin-left: 6px;
  }

  .comment .text {
    margin-top: 6px;
    line-height: 1.3;
  }

  /* Modal for user profile */
  #profileModal {
    display: none;
    position: fixed;
    z-index: 100;
    left: 0; top: 0;
    width: 100vw; height: 100vh;
    background: rgba(255, 0, 144, 0.75);
    backdrop-filter: blur(3px);
    color: white;
    font-family: 'Press Start 2P', cursive;
    text-align: center;
    padding-top: 20vh;
  }
  #profileModal button {
    margin-top: 20px;
    background: #ff7fbf;
    border: none;
    border-radius: 25px;
    padding: 10px 22px;
    font-size: 0.8rem;
    cursor: pointer;
    color: white;
  }
</style>
</head>
<body>

<div id="container">

  <header>🌸 Magical Horizon - Sunshine Days Archive 🌸</header>

  <div id="banner">
    <img src="https://rentry.co/og6rf/raw" alt="Pixel cute gif" />
  </div>

  <nav>
    <ul>
      <!-- Seasons with clickable toggles -->
      <li><span onclick="toggleSubmenu('s1')">Season 1</span>
        <ul id="s1" class="submenu">
          <li><a href="ep1.html">Episode 1: The Beginning</a></li>
          <li><a href="ep2.html">Episode 2: Dream Chaser</a></li>
          <li><a href="ep3.html">Episode 3: Lost Memories</a></li>
        </ul>
      </li>

      <li><span onclick="toggleSubmenu('s2')">Season 2</span>
        <ul id="s2" class="submenu">
          <li><a href="ep4.html">Episode 1: New Horizons</a></li>
          <li><a href="ep5.html">Episode 2: The Encounter</a></li>
          <li><a href="ep6.html">Episode 3: Shadow Play</a></li>
        </ul>
      </li>

      <li><span onclick="toggleSubmenu('s3')">Season 3</span>
        <ul id="s3" class="submenu">
          <li><a href="ep7.html">Episode 1: Secrets Unveiled</a></li>
          <li><a href="ep8.html">Episode 2: The Rift</a></li>
          <li><a href="ep9.html">Episode 3: Final Stand</a></li>
        </ul>
      </li>

      <li><span onclick="toggleSubmenu('s4')">Season 4</span>
        <ul id="s4" class="submenu">
          <li><a href="ep10.html">Episode 1: New Dawn</a></li>
          <li><a href="ep11.html">Episode 2: Rising Sun</a></li>
          <li><a href="ep12.html">Episode 3: Eternal Light</a></li>
        </ul>
      </li>
    </ul>
  </nav>

  <main id="content">
    <p id="errorMsg" style="font-weight:bold; text-align:center; color:#d64161;">
      This site was closed in late 2014. 😢
    </p>
    <p style="text-align:center; font-size:0.9rem; margin-top:10px; color:#a13d69;">
      Sorry, no more episodes or profiles can be accessed. Thank you for your understanding!
    </p>
  </main>

  <button id="translateBtn" onclick="toggleLangMenu()">🌐 Translate</button>
  <div id="langMenu" aria-label="Language menu">
    <button onclick="translatePage('en')">English</button>
    <button onclick="translatePage('fr')">Français</button>
    <button onclick="translatePage('ja')">日本語</button>
    <button onclick="translatePage('zh')">中文</button>
    <button onclick="translatePage('es')">Español</button>
  </div>

  <!-- Fake comments -->
  <section id="comments">
    <h3>Fan Comments (2014)</h3>
    <div class="comment">
      <span class="username" onclick="showProfile('UserPixel')">UserPixel</span>
      <span class="date"> - Dec 28, 2014</span>
      <p class="text">Such a magical site! Brought me back to my childhood every time. 💖</p>
    </div>
    <div class="comment">
      <span class="username" onclick="showProfile('KawaiiChan')">KawaiiChan</span>
      <span class="date"> - Nov 11, 2014</span>
      <p class="text">I loved all the pixel art and the cute episodes. So nostalgic! ⭐⭐⭐⭐</p>
    </div>
    <div class="comment">
      <span class="username" onclick="showProfile('RetroSun')">RetroSun</span>
      <span class="date"> - Oct 05, 2014</span>
      <p class="text">Wish the site never closed... but grateful for the memories. 🌞🌟</p>
    </div>
  </section>

</div>

<!-- Profile modal -->
<div id="profileModal" role="dialog" aria-modal="true" aria-labelledby="modalTitle">
  <h2 id="modalTitle">User Profile</h2>
  <p id="profileText">Sorry, viewing profiles is not possible right now. 😔</p>
  <button onclick="closeProfile()">Close</button>
</div>

<script>
  // Toggle season submenu
  function toggleSubmenu(id) {
    const submenu = document.getElementById(id);
    if (submenu.style.display === 'block') {
      submenu.style.display = 'none';
    } else {
      submenu.style.display = 'block';
    }
  }

  // Translate texts dictionary
  const translations = {
    en: {
      errorMain: "This site was closed in late 2014. 😢",
      errorSub: "Sorry, no more episodes or profiles can be accessed. Thank you for your understanding!",
      commentsTitle: "Fan Comments (2014)",
      comment1: "Such a magical site! Brought me back to my childhood every time. 💖",
      comment2: "I loved all the pixel art and the cute episodes. So nostalgic! ⭐⭐⭐⭐",
      comment3: "Wish the site never closed... but grateful for the memories. 🌞🌟",
      profileMsg: "Sorry, viewing profiles is not possible right now. 😔"
    },
    fr: {
      errorMain: "Ce site a fermé fin 2014. 😢",
      errorSub: "Désolé, plus aucun épisode ou profil n'est accessible. Merci de votre compréhension !",
      commentsTitle: "Commentaires des fans (2014)",
      comment1: "Un site magique ! Il me ramenait toujours en enfance. 💖",
      comment2: "J'adorais tous les pixels art et les épisodes mignons. Tellement nostalgique ! ⭐⭐⭐⭐",
      comment3: "J'aurais aimé que le site ne ferme jamais... mais je suis reconnaissant pour les souvenirs. 🌞🌟",
      profileMsg: "Désolé, voir les profils n'est pas possible pour le moment. 😔"
    },
    ja: {
      errorMain: "このサイトは2014年末に閉鎖されました。😢",
      errorSub: "申し訳ありませんが、これ以上エピソードやプロフィールはアクセスできません。ご理解ありがとうございます！",
      commentsTitle: "ファンのコメント (2014)",
      comment1: "とても魔法のようなサイト！いつも子供時代に戻った気分になりました。💖",
      comment2: "ピクセルアートと可愛いエピソードが大好きでした。懐かしい！⭐⭐⭐⭐",
      comment3: "サイトが閉鎖されなければよかったのに…でも思い出には感謝です。🌞🌟",
      profileMsg: "申し訳ありませんが、プロフィールの閲覧は現在できません。😔"
    },
    zh: {
      errorMain: "本站于2014年底关闭。😢",
      errorSub: "抱歉，无法再访问更多剧集或用户资料。感谢您的理解！",
      commentsTitle: "粉丝评论 (2014)",
      comment1: "这是一个神奇的网站！每次都让我回到童年。💖",
      comment2: "我喜欢所有像素艺术和可爱的剧集。好怀旧！⭐⭐⭐⭐",
      comment3: "希望网站永远不关闭……但感激那些回忆。🌞🌟",
      profileMsg: "抱歉，当前无法查看用户资料。😔"
    },
    es: {
      errorMain: "Este sitio cerró a finales de 2014. 😢",
      errorSub: "Lo siento, no se pueden acceder a más episodios o perfiles. ¡Gracias por tu comprensión!",
      commentsTitle: "Comentarios de fans (2014)",
      comment1: "¡Un sitio mágico! Me hacía volver a mi infancia cada vez. 💖",
      comment2: "Me encantó todo el arte pixelado y los episodios lindos. ¡Muy nostálgico! ⭐⭐⭐⭐",
      comment3: "Ojalá el sitio nunca cerrara... pero agradecido por los recuerdos. 🌞🌟",
      profileMsg: "Lo siento, ver perfiles no es posible ahora mismo. 😔"
    }
  };

  // Toggle translation menu
  function toggleLangMenu() {
    const menu = document.getElementById('langMenu');
    menu.style.display = menu.style.display === 'block' ? 'none' : 'block';
  }

  // Translate entire page content
  function translatePage(lang) {
    document.getElementById('errorMsg').textContent = translations[lang].errorMain;
    document.querySelector('#content p:nth-child(2)').textContent = translations[lang].errorSub;
    document.querySelector('#comments h3').textContent = translations[lang].commentsTitle;

    // Update comments text
    const commentTexts = document.querySelectorAll('#comments .comment .text');
    commentTexts[0].textContent = translations[lang].comment1;
    commentTexts[1].textContent = translations[lang].comment2;
    commentTexts[2].textContent = translations[lang].comment3;

    // Profile modal text
    document.getElementById('profileText').textContent = translations[lang].profileMsg;
  }

  // Fake user profile modal
  function showProfile(username) {
    const modal = document.getElementById('profileModal');
    modal.style.display = 'block';
  }
  function closeProfile() {
    document.getElementById('profileModal').style.display = 'none';
  }
</script>

</body>
</html>

<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Magical Horizon ♥ Sunshine Days Archive</title>
  <style>
    /* Import pixel font */
    @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');
    body {
      background: #ffe4e1 url('https://rentry.co/static/pixel-heart.gif') repeat;
      margin: 0;
      padding: 20px;
      font-family: 'Press Start 2P', monospace;
      color: #330033;
    }
    header {
      text-align: center;
      font-size: 24px;
      color: #ff3399;
      margin-bottom: 10px;
    }
    /* Pink pixel nav */
    nav {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      margin-bottom: 20px;
    }
    .btn {
      background: #ffccff;
      border: 4px solid #ff99cc;
      padding: 8px 12px;
      cursor: pointer;
      text-align: center;
    }
    .btn:hover {
      background: #ff99cc;
    }
    /* Content area */
    #content {
      background: #ffffff;
      border: 4px solid #ff99cc;
      padding: 20px;
      min-height: 200px;
      position: relative;
    }
    /* Episode list dropdown */
    .episode-list {
      list-style: none;
      padding-left: 0;
      margin: 0;
    }
    .episode-list li {
      margin: 4px 0;
      cursor: pointer;
      color: #330033;
    }
    .episode-list li:hover {
      color: #ff3399;
    }
    /* Translate button */
    .translate-btn {
      position: absolute;
      top: 10px;
      right: 10px;
      background: #ffccff;
      border: 2px solid #ff99cc;
      padding: 6px;
      font-size: 12px;
      cursor: pointer;
    }
  </style>
</head>
<body>

<header>
    🌸 Magical Horizon - Sunshine Days Archive 🌸
  </header>

<nav>
    <div class="btn" onclick="showSeason(1)">Season 1</div>
    <div class="btn" onclick="showSeason(2)">Season 2</div>
    <div class="btn" onclick="showSeason(3)">Season 3</div>
    <div class="btn" onclick="showSeason(4)">Season 4</div>
  </nav>

<div id="content">
    <button class="translate-btn" onclick="toggleLang()">EN⇄JP</button>
    <p id="main-text-ja">
      ようこそ！このサイトは「Sunshine Days」のアーカイブです。<br>
      このサイトは2014年に閉鎖されましたが、ファンが内容を保存しています。(^_−)☆<br>
    </p>
    <p id="main-text-en" style="display:none;">
      Welcome! This is an archive for "Sunshine Days".<br>
      The original site closed in 2014 but fans saved its memory. (^_−)☆<br>
    </p>
    <div>
      <img src="https://rentry.co/static/pixel-girl.gif" alt="pixel girl" style="width:200px; margin:20px auto; display:block;">
    </div>
<ul id="episodes" class="episode-list" style="display:none;"></ul>
</div>

<script>
  const seasons = {
    1: [
      'Episode 1: The Beginning',
      'Episode 2: Lost Memories',
      'Episode 3: The Secret',
      'Episode 4: Blooming Heart',
      'Episode 5: Shadows',
      'Episode 6: The Pact',
      'Episode 7: Forbidden Magic',
      'Episode 8: The Betrayal',
      'Episode 9: Last Hope',
      'Episode 10: Rebirth',
      'Episode 11: Farewell',
      'Episode 12: The End'
    ],
    2: [],
    3: [],
    4: []
  };
  let currentLang = 'ja';

  function showSeason(n) {
    const eps = seasons[n];
    const ul = document.getElementById('episodes');
    ul.innerHTML = '';
    if (eps.length === 0) {
      ul.innerHTML = '<li>Uh oh… nothing anymore! (・_・;)</li>';
    } else {
      eps.forEach(e => {
        const li = document.createElement('li');
        li.textContent = e;
        li.onclick = () => showContent(e);
        ul.appendChild(li);
      });
    }
    ul.style.display = 'block';
  }

  function showContent(title) {
    const txt = currentLang === 'ja'
      ? `<h2>${title}</h2><p>このエピソードは今はもうありません…(・_・;)</p>`
      : `<h2>${title}</h2><p>This episode is no longer available… (・_・;)</p>`;
    document.getElementById('content').innerHTML = txt;
  }

  function toggleLang() {
    const ja = document.getElementById('main-text-ja');
    const en = document.getElementById('main-text-en');
    currentLang = (currentLang === 'ja' ? 'en' : 'ja');
    ja.style.display = currentLang === 'ja' ? 'block' : 'none';
    en.style.display = currentLang === 'en' ? 'block' : 'none';
  }
</script>

</body>
</html>

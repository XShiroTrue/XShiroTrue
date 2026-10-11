<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Speed ♪ Developer & Designer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600;900&family=Zen+Maru+Gothic:wght@400;500;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#061320; --bg2:#0a2233; --panel:rgba(10,38,54,.78); --line:#1f5a6b;
  --text:#e6fffd; --muted:#8fd3d0; --teal:#39c5bb; --cyan:#7ff5ee; --pink:#ff4fa3;
  --grad:linear-gradient(135deg,#39c5bb,#7ff5ee 55%,#b9fffa);
}
*,*::before,*::after{box-sizing:border-box}
html{scroll-behavior:smooth}
body{
  margin:0;color:var(--text);line-height:1.75;
  font-family:"Zen Maru Gothic","Hiragino Maru Gothic ProN",system-ui,sans-serif;
  background:
    radial-gradient(900px 500px at 50% -10%,rgba(57,197,187,.35),transparent 70%),
    linear-gradient(rgba(57,197,187,.06) 1px,transparent 1px) 0 0/100% 38px,
    linear-gradient(90deg,rgba(57,197,187,.06) 1px,transparent 1px) 0 0/38px 100%,
    var(--bg);
  background-attachment:fixed;
  overflow-x:hidden;
  padding:env(safe-area-inset-top,0px) 0 env(safe-area-inset-bottom,0px);
}
a{color:var(--cyan)} a:hover{color:var(--pink)}
:focus-visible{outline:2px solid var(--pink);outline-offset:3px;border-radius:6px}
.wrap{max-width:820px;margin:0 auto;padding:0 22px;position:relative;z-index:2}

/* sparkles */
.spark{position:fixed;z-index:1;color:var(--cyan);pointer-events:none;animation:tw 3.2s ease-in-out infinite;opacity:0}
@keyframes tw{0%,100%{opacity:0;transform:scale(.4) rotate(0)}50%{opacity:.9;transform:scale(1) rotate(45deg)}}
.pop{position:fixed;z-index:50;pointer-events:none;font-size:22px;color:var(--pink);animation:pop 1s ease-out forwards}
@keyframes pop{to{transform:translateY(-70px) rotate(25deg);opacity:0}}

/* top bar */
.bar{display:flex;justify-content:space-between;gap:12px;padding:16px 0;font-family:Orbitron,sans-serif;font-size:.72rem;color:var(--muted);letter-spacing:.12em}
.bar b{color:var(--teal)}

/* hero */
.hero{position:relative;text-align:center;padding:56px 0 30px}
.tails{position:absolute;inset:0;width:100%;height:100%;z-index:0;pointer-events:none}
.tails path.r{fill:none;stroke:url(#tg);stroke-width:26;stroke-linecap:round;opacity:.5;
  animation:sway 6s ease-in-out infinite;transform-origin:50% 0}
.tails path.r2{animation-delay:-3s}
@keyframes sway{0%,100%{transform:rotate(-1.2deg)}50%{transform:rotate(1.2deg)}}
.hero>*:not(svg){position:relative;z-index:1}
.kana{font-size:.95rem;color:var(--pink);letter-spacing:.5em;font-weight:700}
h1{
  font-family:Orbitron,sans-serif;font-weight:900;margin:6px 0 4px;
  font-size:clamp(3rem,14vw,6.6rem);letter-spacing:.04em;line-height:1;
  background:var(--grad);-webkit-background-clip:text;background-clip:text;color:transparent;
  filter:drop-shadow(4px 4px 0 rgba(255,79,163,.85)) drop-shadow(0 0 22px rgba(57,197,187,.6));
}
.sub{font-size:1.1rem;max-width:34ch;margin:12px auto 26px;color:var(--text)}
.btns{display:flex;justify-content:center;flex-wrap:wrap;gap:12px}
.btn{
  padding:11px 26px;font-weight:700;text-decoration:none;color:var(--teal);
  border:2px solid var(--teal);border-radius:999px;background:rgba(6,19,32,.6);
  transition:transform .15s,box-shadow .15s;
}
.btn.fill{background:var(--teal);color:#032028;box-shadow:0 0 0 0 rgba(255,79,163,.0)}
.btn:hover{transform:translateY(-2px);border-color:var(--pink);color:var(--pink);box-shadow:0 6px 0 var(--pink)}
.btn.fill:hover{background:var(--pink);color:#fff}

/* player */
.player{
  margin:38px auto 0;max-width:460px;text-align:left;padding:16px 18px;
  background:var(--panel);border:1.5px solid var(--line);border-radius:18px;
  backdrop-filter:blur(6px);box-shadow:0 0 28px rgba(57,197,187,.25);
  display:grid;grid-template-columns:auto 1fr;gap:14px;align-items:center;
}
.disc{
  width:62px;height:62px;border-radius:50%;
  background:conic-gradient(from 0deg,#39c5bb,#ff4fa3,#7ff5ee,#39c5bb);
  display:grid;place-items:center;animation:spin 6s linear infinite;
}
.disc::after{content:"";width:16px;height:16px;border-radius:50%;background:var(--bg)}
@keyframes spin{to{transform:rotate(360deg)}}
.np{font-size:.7rem;color:var(--pink);font-weight:700;letter-spacing:.14em;font-family:Orbitron,sans-serif}
.song{font-weight:700;margin:0}
.prog{height:6px;border-radius:99px;background:#12384a;margin-top:8px;overflow:hidden}
.prog i{display:block;height:100%;width:40%;background:var(--grad);border-radius:99px;animation:run 14s linear infinite}
@keyframes run{from{width:4%}to{width:100%}}

/* sections */
section{padding:36px 0}
h2{
  font-family:Orbitron,sans-serif;font-size:1.25rem;margin:0 0 18px;color:var(--cyan);
  display:flex;align-items:center;gap:12px;letter-spacing:.06em;
}
h2::after{content:"";flex:1;height:2px;background:linear-gradient(90deg,var(--teal),transparent)}
.card{
  background:var(--panel);border:1.5px solid var(--line);border-radius:18px;padding:22px;
  clip-path:polygon(0 0,calc(100% - 22px) 0,100% 22px,100% 100%,22px 100%,0 calc(100% - 22px));
  border-radius:0;
}
.about{margin:0;padding:0;list-style:none;display:grid;gap:10px}
.about li::before{content:"♪ ";color:var(--pink)}

.skills{display:grid;gap:14px}
.sk{display:grid;grid-template-columns:110px 1fr;gap:12px;align-items:center;font-weight:500}
.meter{height:12px;border-radius:99px;background:#0f3041;border:1px solid var(--line);overflow:hidden}
.meter i{display:block;height:100%;border-radius:99px;background:var(--grad);box-shadow:0 0 12px var(--teal)}
.note{margin:14px 0 0;font-size:.8rem;color:var(--muted)}

.chips{display:flex;flex-wrap:wrap;gap:10px;padding:0;margin:0;list-style:none}
.chips li{padding:5px 15px;border-radius:99px;border:1.5px solid var(--teal);font-size:.88rem;font-weight:500;background:rgba(57,197,187,.1)}
.chips li:nth-child(3n){border-color:var(--pink);background:rgba(255,79,163,.1)}

.tracks{list-style:none;margin:0;padding:0}
.tracks li{
  display:grid;grid-template-columns:34px 1fr auto;gap:4px 14px;align-items:center;
  padding:14px 8px;border-bottom:1px dashed var(--line);border-radius:10px;
}
.tracks li:hover{background:rgba(57,197,187,.1)}
.tracks .n{font-family:Orbitron,sans-serif;color:var(--pink);font-size:.9rem}
.tracks h3{margin:0;font-size:1.02rem}
.tracks p{margin:0;grid-column:2;color:var(--muted);font-size:.9rem}
.tracks .tag{grid-column:3;grid-row:1/3;font-size:.8rem;color:var(--teal)}
@media (max-width:520px){
  .sk{grid-template-columns:1fr}
  .tracks li{grid-template-columns:30px 1fr}
  .tracks .tag{grid-column:2;grid-row:auto}
}

footer{text-align:center;padding:40px 22px 60px;color:var(--muted)}
footer .links{display:flex;justify-content:center;flex-wrap:wrap;gap:20px;margin:0 0 18px;font-weight:700}
footer .big{font-family:Orbitron,sans-serif;color:var(--pink);font-size:1.3rem;letter-spacing:.2em}

@media (prefers-reduced-motion:reduce){
  *{animation:none!important;scroll-behavior:auto!important}
  .spark{opacity:.6}
}
</style>
</head>
<body>

<main class="wrap">
  <div class="bar"><span><b>KENCHIRO</b> // PROFILE.EXE</span><span>♪ 39 ONLINE</span></div>

  <header class="hero">
    <svg class="tails" viewBox="0 0 820 520" preserveAspectRatio="none" aria-hidden="true">
      <defs><linearGradient id="tg" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0" stop-color="#7ff5ee"/><stop offset="1" stop-color="#39c5bb" stop-opacity=".1"/>
      </linearGradient></defs>
      <path class="r" d="M70 20 C-20 120 140 200 40 320 C-10 390 80 450 30 520"/>
      <path class="r r2" d="M750 20 C840 120 680 200 780 320 C830 390 740 450 790 520"/>
      <circle cx="70" cy="20" r="16" fill="#ff4fa3"/><circle cx="750" cy="20" r="16" fill="#ff4fa3"/>
    </svg>

    <div class="kana">ミ ク カ ラ ー</div>
    <h1>SPEED</h1>
    <p class="sub">I design and code for the web. Bored? I build. Deadline? I build faster.</p>
    <div class="btns">
      <a class="btn fill" href="#projects">Play my projects</a>
      <a class="btn" href="#connect">Say hi</a>
    </div>

    <div class="player" aria-label="Now playing">
      <div class="disc"></div>
      <div>
        <div class="np">NOW CODING</div>
        <p class="song">Bored_at_2AM_final_v2.mp3</p>
        <div class="prog"><i></i></div>
      </div>
    </div>
  </header>

  <section id="about">
    <h2>About me</h2>
    <div class="card">
      <ul class="about">
        <li>I mainly work on design: bright colors, clean layouts, interfaces with personality.</li>
        <li>I code for fun when I'm bored, and out of necessity for school work.</li>
        <li>I'm learning Laravel, networking, and better UI/UX.</li>
        <li>I also make anime and gaming fan projects.</li>
      </ul>
    </div>
  </section>

  <section id="skills">
    <h2>Status screen</h2>
    <div class="card">
      <div class="skills">
        <div class="sk"><span>Design</span><div class="meter"><i style="width:90%"></i></div></div>
        <div class="sk"><span>Front-end</span><div class="meter"><i style="width:75%"></i></div></div>
        <div class="sk"><span>Laravel</span><div class="meter"><i style="width:55%"></i></div></div>
        <div class="sk"><span>Networking</span><div class="meter"><i style="width:45%"></i></div></div>
      </div>
      <p class="note">Bars are placeholders. Change the width values to match your real level.</p>
    </div>
  </section>

  <section id="stack">
    <h2>Equipment</h2>
    <ul class="chips">
      <li>HTML</li><li>CSS</li><li>JavaScript</li><li>PHP</li><li>Laravel</li><li>Figma</li><li>Git</li><li>VS Code</li>
    </ul>
  </section>

  <section id="projects">
    <h2>Track list</h2>
    <div class="card">
      <ol class="tracks">
        <li><span class="n">01</span><h3><a href="https://github.com/YOUR_USERNAME/project-one">Project One</a></h3><span class="tag">HTML · CSS · JS</span><p>A short line about your best design project.</p></li>
        <li><span class="n">02</span><h3><a href="https://github.com/YOUR_USERNAME/laravel-auth">Laravel Auth App</a></h3><span class="tag">Laravel · PHP</span><p>Sign up and login with form validation.</p></li>
        <li><span class="n">03</span><h3><a href="https://github.com/YOUR_USERNAME/project-three">Project Three</a></h3><span class="tag">Your stack</span><p>Something you built just because you were bored.</p></li>
      </ol>
    </div>
  </section>
</main>

<footer id="connect">
  <div class="links">
    <a href="https://github.com/YOUR_USERNAME">GitHub</a>
    <a href="mailto:your@email.com">Email</a>
    <a href="https://discord.com/users/YOUR_ID">Discord</a>
  </div>
  <div class="big">3 9 ♪ THANK YOU</div>
</footer>

<script>
(function(){
  // twinkling sparkles
  var glyphs=['✦','✧','♪','♫','★'];
  for(var i=0;i<16;i++){
    var s=document.createElement('span');
    s.className='spark';
    s.textContent=glyphs[i%glyphs.length];
    s.style.left=(Math.random()*96)+'%';
    s.style.top=(Math.random()*92)+'%';
    s.style.fontSize=(10+Math.random()*16)+'px';
    s.style.animationDelay=(-Math.random()*3.2)+'s';
    document.body.appendChild(s);
  }
  // notes pop where you click
  document.addEventListener('click',function(e){
    var p=document.createElement('span');
    p.className='pop';
    p.textContent=['♪','♫','✦'][Math.floor(Math.random()*3)];
    p.style.left=e.clientX+'px';
    p.style.top=e.clientY+'px';
    document.body.appendChild(p);
    setTimeout(function(){p.remove()},1000);
  });
})();
</script>
</body>
</html>

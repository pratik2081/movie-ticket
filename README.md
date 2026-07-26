
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kalee, a movie's calling 🎬</title>
<meta name="description" content="A little movie date invitation for Kalee.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Dancing+Script:wght@600;700&family=Poppins:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --maroon:#5E0F1C;
    --maroon-deep:#3D0A13;
    --gold:#F4B942;
    --cream:#FFF6E9;
    --pink:#FF6B81;
    --ink:#2B1014;
    --display:'Bebas Neue', sans-serif;
    --script:'Dancing Script', cursive;
    --body:'Poppins', sans-serif;
  }

  *{ box-sizing:border-box; }
  @media (prefers-reduced-motion: reduce){
    *{ animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition-duration:0.001ms !important; }
  }

  body{
    margin:0;
    min-height:100vh;
    background:
      radial-gradient(circle at 20% 10%, rgba(244,185,66,0.10), transparent 45%),
      radial-gradient(circle at 85% 85%, rgba(255,107,129,0.12), transparent 45%),
      var(--maroon-deep);
    color:var(--cream);
    font-family:var(--body);
    display:flex;
    align-items:center;
    justify-content:center;
    padding:32px 16px;
    overflow-x:hidden;
  }

  .stage{
    max-width:520px;
    width:100%;
    text-align:center;
  }

  /* ---------- MARQUEE ---------- */
  .marquee{
    border:3px solid var(--gold);
    border-radius:14px;
    padding:10px 18px;
    display:inline-flex;
    align-items:center;
    gap:10px;
    background:rgba(0,0,0,0.15);
    margin-bottom:28px;
    position:relative;
  }
  .marquee .bulb{
    width:8px; height:8px;
    border-radius:50%;
    background:var(--gold);
    box-shadow:0 0 6px 2px rgba(244,185,66,0.7);
    animation:blink 1.4s infinite ease-in-out;
  }
  .marquee .bulb:nth-child(odd){ animation-delay:0.3s; }
  .marquee span.txt{
    font-family:var(--display);
    letter-spacing:0.12em;
    font-size:0.9rem;
    color:var(--gold);
  }
  @keyframes blink{
    0%, 100%{ opacity:0.3; }
    50%{ opacity:1; }
  }

  h1.headline{
    font-family:var(--script);
    font-size:clamp(2.1rem, 8vw, 3.1rem);
    color:var(--cream);
    margin:0 0 8px;
    line-height:1.15;
  }
  h1.headline .name{
    color:var(--gold);
  }

  p.subline{
    font-size:1rem;
    color:rgba(255,246,233,0.82);
    max-width:38ch;
    margin:0 auto 34px;
  }

  /* ---------- TICKET ---------- */
  .ticket{
    display:flex;
    background:var(--cream);
    color:var(--ink);
    border-radius:12px;
    overflow:hidden;
    box-shadow:0 24px 50px -20px rgba(0,0,0,0.55);
    margin:0 auto 36px;
    text-align:left;
    position:relative;
    animation:riseIn 0.8s ease-out both;
  }
  @keyframes riseIn{
    from{ opacity:0; transform:translateY(18px); }
    to{ opacity:1; transform:translateY(0); }
  }
  .ticket-main{
    flex:1;
    padding:22px 20px;
  }
  .ticket-main .brand{
    font-family:var(--display);
    letter-spacing:0.1em;
    font-size:0.72rem;
    color:var(--maroon);
    opacity:0.75;
  }
  .ticket-main h2{
    font-family:var(--display);
    font-size:1.6rem;
    letter-spacing:0.02em;
    margin:6px 0 12px;
    color:var(--maroon);
  }
  .ticket-row{
    display:flex;
    justify-content:space-between;
    font-size:0.8rem;
    padding:5px 0;
    border-top:1px dashed rgba(43,16,20,0.2);
  }
  .ticket-row:first-of-type{ border-top:none; }
  .ticket-row .lbl{
    text-transform:uppercase;
    letter-spacing:0.05em;
    color:rgba(43,16,20,0.55);
    font-size:0.68rem;
  }
  .ticket-row .val{ font-weight:600; }

  .ticket-stub{
    width:76px;
    flex-shrink:0;
    background:var(--maroon);
    color:var(--cream);
    display:flex;
    align-items:center;
    justify-content:center;
    position:relative;
    border-left:2px dashed rgba(255,246,233,0.45);
  }
  .ticket-stub span{
    font-family:var(--display);
    letter-spacing:0.15em;
    font-size:0.85rem;
    writing-mode:vertical-rl;
    transform:rotate(180deg);
  }
  .ticket::before, .ticket::after{
    content:'';
    position:absolute;
    width:18px; height:18px;
    background:var(--maroon-deep);
    border-radius:50%;
    top:50%;
    transform:translateY(-50%);
  }
  .ticket::before{ left:calc(100% - 76px - 9px); }
  .ticket::after{ left:calc(100% - 76px - 9px); display:none; }

  /* ---------- ASK ---------- */
  .ask-wrap{
    position:relative;
    min-height:110px;
  }
  .ask-caption{
    font-size:0.92rem;
    color:var(--gold);
    min-height:22px;
    margin-bottom:16px;
    font-weight:500;
  }
  .buttons{
    display:flex;
    justify-content:center;
    gap:18px;
    position:relative;
    min-height:64px;
  }
  .btn{
    font-family:var(--body);
    font-weight:600;
    border:none;
    border-radius:999px;
    padding:14px 28px;
    font-size:1rem;
    cursor:pointer;
    transition:transform 0.18s ease, background 0.15s ease;
  }
  .btn:active{ transform:translateY(1px); }
  .btn-yes{
    background:var(--pink);
    color:#fff;
    box-shadow:0 10px 24px -10px rgba(255,107,129,0.7);
  }
  .btn-yes:hover{ background:#ff8397; }
  .btn-no{
    background:transparent;
    color:rgba(255,246,233,0.75);
    border:1.5px solid rgba(255,246,233,0.4);
    position:relative;
  }
  .btn-no.dodging{
    position:absolute;
  }
  :focus-visible{ outline:3px solid var(--gold); outline-offset:3px; }

  /* ---------- YAY OVERLAY ---------- */
  .yay{
    display:none;
    margin-top:8px;
    animation:popIn 0.4s ease-out both;
  }
  .yay.show{ display:block; }
  @keyframes popIn{
    from{ opacity:0; transform:scale(0.85); }
    to{ opacity:1; transform:scale(1); }
  }
  .yay h3{
    font-family:var(--script);
    font-size:2rem;
    color:var(--gold);
    margin:0 0 8px;
  }
  .yay p{
    color:rgba(255,246,233,0.85);
    font-size:0.95rem;
    max-width:36ch;
    margin:0 auto;
  }

  .hearts{
    position:fixed;
    inset:0;
    pointer-events:none;
    overflow:hidden;
    z-index:5;
  }
  .heart{
    position:absolute;
    top:-40px;
    font-size:1.4rem;
    animation:fall linear forwards;
  }
  @keyframes fall{
    to{ transform:translateY(110vh) rotate(180deg); opacity:0.2; }
  }

  footer.made{
    margin-top:36px;
    font-size:0.78rem;
    color:rgba(255,246,233,0.5);
  }

  @media (max-width:400px){
    .ticket{ flex-direction:column; }
    .ticket-stub{ width:100%; padding:10px 0; border-left:none; border-top:2px dashed rgba(255,246,233,0.45); }
    .ticket-stub span{ writing-mode:horizontal-tb; transform:none; }
    .ticket::before{ display:none; }
    .buttons{ flex-wrap:wrap; }
  }
</style>
</head>
<body>

<div class="hearts" id="heartsLayer" aria-hidden="true"></div>

<div class="stage">
  <div class="marquee">
    <span class="bulb"></span><span class="bulb"></span>
    <span class="txt">NOW SHOWING</span>
    <span class="bulb"></span><span class="bulb"></span>
  </div>

  <h1 class="headline">Hey <span class="name">Kalee</span>, got plans this weekend? 🎬</h1>
  <p class="subline">I was thinking... you, me, a big screen, and way too much popcorn.</p>

  <div class="ticket">
    <div class="ticket-main">
      <div class="brand">ADMIT TWO &bull; ONE NIGHT ONLY</div>
      <h2>Dipti &amp; Me</h2>
      <div class="ticket-row"><span class="lbl">Feature</span><span class="val">A Movie Date 🍿</span></div>
      <div class="ticket-row"><span class="lbl">Showtime</span><span class="val">Whenever you're free</span></div>
      <div class="ticket-row"><span class="lbl">Seats</span><span class="val">Right next to each other</span></div>
      <div class="ticket-row"><span class="lbl">Snacks</span><span class="val">On me 😊</span></div>
    </div>
    <div class="ticket-stub"><span>KALEE ❤</span></div>
  </div>

  <div class="ask-wrap">
    <div class="ask-caption" id="askCaption">So... will you go to the movies with me?</div>
    <div class="buttons" id="buttonRow">
      <button class="btn btn-yes" id="yesBtn" style="font-size:1rem;">Yes! 🎉</button>
      <button class="btn btn-no" id="noBtn">Hmm, no</button>
    </div>
  </div>

  <div class="yay" id="yay">
    <h3>Yay! It's a date 🎟️💕</h3>
    <p>I'll text you the details, Kalee. Can't wait to sit next to you in the dark and steal your popcorn.</p>
  </div>

  <footer class="made">made with ❤️ just for you, Kalee</footer>
</div>

<script>
  const noBtn = document.getElementById('noBtn');
  const yesBtn = document.getElementById('yesBtn');
  const buttonRow = document.getElementById('buttonRow');
  const askCaption = document.getElementById('askCaption');
  const yay = document.getElementById('yay');
  const heartsLayer = document.getElementById('heartsLayer');

  const teases = [
    "Are you sure? 🥺",
    "C'mon, it's just popcorn and a movie!",
    "Kalee, think about it...",
    "Last chance to say yes 👀",
    "The 'no' button is getting shy...",
    "Okay but 'yes' looks so much better on you",
    "I'll even let you pick the movie 🎬"
  ];
  let teaseIndex = 0;
  let scale = 1;
  const reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

  function dodge(){
    if (reduceMotion) return; // keep it simple and static for reduced-motion users
    const rowRect = buttonRow.getBoundingClientRect();
    const btnRect = noBtn.getBoundingClientRect();
    const maxX = rowRect.width - btnRect.width;
    const maxY = 90;

    if (!noBtn.classList.contains('dodging')) {
      noBtn.classList.add('dodging');
      noBtn.style.left = (btnRect.left - rowRect.left) + 'px';
      noBtn.style.top = '0px';
    }

    const newX = Math.max(0, Math.random() * maxX);
    const newY = Math.max(0, Math.random() * maxY - 20);
    noBtn.style.left = newX + 'px';
    noBtn.style.top = newY + 'px';

    askCaption.textContent = teases[teaseIndex % teases.length];
    teaseIndex++;

    scale = Math.min(scale + 0.08, 1.9);
    yesBtn.style.transform = `scale(${scale})`;
  }

  noBtn.addEventListener('mouseenter', dodge);
  noBtn.addEventListener('touchstart', (e) => { e.preventDefault(); dodge(); }, { passive:false });
  noBtn.addEventListener('click', (e) => { e.preventDefault(); dodge(); });

  function spawnHearts(){
    const symbols = ['❤️','💕','🎬','🍿','💗'];
    for (let i = 0; i < 26; i++){
      const el = document.createElement('div');
      el.className = 'heart';
      el.textContent = symbols[Math.floor(Math.random() * symbols.length)];
      el.style.left = Math.random() * 100 + 'vw';
      el.style.animationDuration = (2.5 + Math.random() * 2) + 's';
      el.style.animationDelay = (Math.random() * 0.6) + 's';
      heartsLayer.appendChild(el);
      setTimeout(() => el.remove(), 5000);
    }
  }

  yesBtn.addEventListener('click', () => {
    yay.classList.add('show');
    document.querySelector('.ask-wrap').style.display = 'none';
    if (!reduceMotion) spawnHearts();
  });
</script>

</body>
</html>

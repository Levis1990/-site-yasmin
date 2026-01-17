[index.html](https://github.com/user-attachments/files/24692224/index.html)
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Levi 💍💍 Yasmin</title>
    <link rel="stylesheet" href="style.css" />
  </head>

  <body>
    <!-- ABERTURA -->
    <div id="intro" class="intro" aria-hidden="false">
      <div class="intro-card">
        <p class="intro-small">Para</p>
        <h1 class="intro-title">Yasmin Pires Lopez  💖 </h1>
        <p class="intro-text">
          Eu fiz esse site com carinho…<br />
          Espero que goste. 💌
        </p>

        <button id="enterBtn" class="btn btn-love" type="button">
          Entrar  💖 
          <span class="btn-shine" aria-hidden="true"></span>
        </button>

        <p class="intro-hint">Dica clique para abrir com transição ✨</p>
      </div>
    </div>

    <!-- brilhos do fundo -->
    <div class="glow glow-1"></div>
    <div class="glow glow-2"></div>

    <!-- camada de efeitos -->
    <div id="effects-layer" aria-hidden="true"></div>

    <header>
      <div class="header-wrap">
        <h1>Levi & Yasmin 💖</h1>
        <p class="subtitle">Um site feito com amor, só pra você.</p>

        <nav>
          <a href="#inicio">Início</a>
          <a href="#mensagem">Mensagem</a>
          <a href="#historia">Nossa História</a>
          <a href="#carta">Carta</a>
          <a href="#musica">Música</a>
          <a href="#final">Final</a>
        </nav>
      </div>
    </header>

    <!-- PAGE começa escondida e aparece quando clicar Entrar -->
    <main id="page" class="page page--hidden">
      <!-- CONTADOR -->
      <section id="inicio" class="hero">
        <p class="hero-top">Para <strong>Yasmin Pires Lopez</strong> 🌷</p>

        <div class="counter-card">
          <p class="counter-label">Estamos juntinhos há</p>

          <div class="counter-number">
            <span id="daysCount">0</span>
            <span class="counter-days">dias</span>
          </div>

          <div class="counter-extra">
            <div class="time-box">
              <span id="hoursCount">00</span>
              <small>horas</small>
            </div>
            <div class="time-box">
              <span id="minutesCount">00</span>
              <small>min</small>
            </div>
            <div class="time-box">
              <span id="secondsCount">00</span>
              <small>seg</small>
            </div>
          </div>

          <p class="counter-since">desde 18/05/2024 💞</p>

          <div class="hero-badges">
            <span class="badge">💖 EU TE AMO</span>
            <span class="badge">🌷 I LOVE YOU</span>
            <span class="badge">✨ 
            ICH LIEBE DICH</span>
          </div>
        </div>
      </section>

      <!-- MENSAGEM -->
      <section id="mensagem" class="card glass center">
        <h2 id="tituloMensagem">OIII MINHA TULIPINHAAAA 💖</h2>
        <p id="textoMensagem">
          Clique no botão e eu vou te mostrar uma mensagem bem especial… 💌
        </p>

        <button id="meuBotao" class="btn" type="button">
          Para voce 💖
          <span class="btn-shine" aria-hidden="true"></span>
        </button>
      </section>

      <!-- NOSSA HISTÓRIA -->
      <section id="historia" class="card glass">
        <h2>Nossa História 💞</h2>

        <div class="grid-3">
          <article class="mini glass-soft">
            <h3>🌷 O começo</h3>
            <p>
              Em 18/05/2024, numa sexta-feira eu conheci você… e desde então, meus dias ganharam
              outro brilho. Se tornaram maravilhosos, eu vivi e vivo uma felicidade imensa.[style.css](https://github.com/user-attachments/files/24692225/style.css):root {
  --bg1: #ff4d6d;
  --bg2: #7b2cbf;
  --bg3: #3a86ff;

  --glass: rgba(0, 0, 0, 0.28);
  --glassSoft: rgba(255, 255, 255, 0.1);
  --border: rgba(255, 255, 255, 0.16);[script.js](https://github.com/user-attachments/files/24692226/script.js)console.log("JavaScript Funcionando!");

// =====================
// 1) CONTADOR COMPLETO
// =====================
const daysEl = document.getElementById("daysCount");
const hoursEl = document.getElementById("hoursCount");
const minutesEl = document.getElementById("minutesCount");
const secondsEl = document.getElementById("secondsCount");

// 18/05/2024 00:00:00 (mês no JS é 0-11, então maio = 4)
const startDate = new Date(2024, 4, 18, 0, 0, 0);

function pad2(n) {
  return String(n).padStart(2, "0");
}

function atualizarContador() {
  const now = new Date();
  const diffMs = now.getTime() - startDate.getTime();

  const totalSeconds = Math.floor(diffMs / 1000);

  const days = Math.floor(totalSeconds / (60 * 60 * 24)) + 1;
  const rest = totalSeconds % (60 * 60 * 24);

  const hours = Math.floor(rest / (60 * 60));
  const rest2 = rest % (60 * 60);

  const minutes = Math.floor(rest2 / 60);
  const seconds = rest2 % 60;

  if (daysEl) daysEl.textContent = String(days);
  if (hoursEl) hoursEl.textContent = pad2(hours);
  if (minutesEl) minutesEl.textContent = pad2(minutes);
  if (secondsEl) secondsEl.textContent = pad2(seconds);
}

atualizarContador();
setInterval(atualizarContador, 1000);

// =====================
// 2) EFEITOS (FLORES + CORAÇÕES)
// =====================
const effectsLayer = document.getElementById("effects-layer");
const flores = ["🌸", "🌺","💍", "🌷", "💐", "🌹"];
const coracoes = ["❤️", "💖", "💘","💍", "💞", "💕"];

function soltarFlores(qtd = 18) {
  if (!effectsLayer) return;

  for (let n = 0; n < qtd; n++) {
    const el = document.createElement("div");
    el.className = "flower";
    el.textContent = flores[Math.floor(Math.random() * flores.length)];
    el.style.left = `${Math.random() * 100}vw`;
    el.style.fontSize = `${18 + Math.random() * 22}px`;
    el.style.animationDelay = `${Math.random() * 0.25}s`;

    effectsLayer.appendChild(el);
    setTimeout(() => el.remove(), 2400);
  }
}

function subirCoracoes(qtd = 24) {
  if (!effectsLayer) return;

  for (let n = 0; n < qtd; n++) {
    const el = document.createElement("div");
    el.className = "heart";
    el.textContent = coracoes[Math.floor(Math.random() * coracoes.length)];
    el.style.left = `${Math.random() * 100}vw`;
    el.style.fontSize = `${18 + Math.random() * 26}px`;
    el.style.animationDelay = `${Math.random() * 0.25}s`;

    effectsLayer.appendChild(el);
    setTimeout(() => el.remove(), 2600);
  }
}

// =====================
// 3) DIGITAÇÃO (MENSAGENS)
// =====================
const botao = document.getElementById("meuBotao");
const titulo = document.getElementById("tituloMensagem");
const texto = document.getElementById("textoMensagem");

const mensagens = [
  "MEU AMOR, você é a melhor parte do meu dia 💛",
  "Eu escolho você — hoje e sempre 💞",
  "Seu sorriso é meu lugar favorito 🌷",
  "Com você, tudo fica mais bonito ✨",
  "Você tem o meu coração todinho ❤️",
  "Se eu pudesse, eu te daria o mundo… mas fiz um site 😍",
];

let idx = 0;
let typingLock = false;

function digitar(elemento, mensagem, velocidade = 22) {
  typingLock = true;
  elemento.textContent = "";
  let i = 0;

  const timer = setInterval(() => {
    elemento.textContent += mensagem[i];
    i++;

    if (i >= mensagem.length) {
      clearInterval(timer);
      typingLock = false;
    }
  }, velocidade);
}

function trocarMensagem() {
  if (typingLock) return;

  idx = (idx + 1) % mensagens.length;
  digitar(titulo, mensagens[idx], 22);
  texto.textContent = "Clica de novo pra ver outra mensagem 💌";
}

// =====================
// 4) ABERTURA + TRANSIÇÃO
// =====================
const intro = document.getElementById("intro");
const enterBtn = document.getElementById("enterBtn");
const page = document.getElementById("page");

function abrirSite() {
  if (intro) {
    intro.classList.add("intro--hide");
    intro.setAttribute("aria-hidden", "true");
  }

  if (page) {
    page.classList.remove("page--hidden");
  }

  // efeito inicial ao entrar
  subirCoracoes(28);
  soltarFlores(18);

  // rola para o começo
  window.scrollTo({ top: 0, behavior: "smooth" });
}

if (enterBtn) {
  enterBtn.addEventListener("click", abrirSite);
}

// =====================
// 5) FINAL (SIM / NÃO)
// =====================
const btnSim = document.getElementById("btnSim");
const btnNao = document.getElementById("btnNao");
const finalMsg = document.getElementById("finalMsg");

if (btnNao) {
  btnNao.addEventListener("click", () => {
    if (finalMsg)
      finalMsg.textContent = "Opa 😅 esse botão não vale! Tenta o SIM 💖";
    subirCoracoes(18);
  });
}

if (btnSim) {
  btnSim.addEventListener("click", () => {
    if (finalMsg)
      finalMsg.textContent =
        "OHHHHH 💍💖 Eu te amo TANTO,MEU AMORZINHOOOOOO! 😍";
    subirCoracoes(60);
    soltarFlores(45);
  });
}

// =====================
// 6) CLIQUE NA MENSAGEM
// =====================
if (botao) {
  botao.addEventListener("click", () => {
    trocarMensagem();
    soltarFlores(20);
    subirCoracoes(28);
  });
}

// Mensagem inicial com digitação (fica lindo)
if (titulo) {
  digitar(titulo, "OIIII, MINHA LINDAAAAAAA 💍", 25);
}


  --text: #f7f7fb;
  --muted: rgba(255, 255, 255, 0.85);

  --shadow: 0 18px 50px rgba(0, 0, 0, 0.35);
  --shadow2: 0 10px 30px rgba(0, 0, 0, 0.28);
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
  color: var(--text);
  min-height: 100vh;

  background: radial-gradient(
      1000px 600px at 20% 10%,
      rgba(255, 255, 255, 0.18),
      transparent 55%
    ),
    radial-gradient(
      900px 600px at 80% 30%,
      rgba(255, 255, 255, 0.12),
      transparent 60%
    ),
    linear-gradient(120deg, var(--bg1), var(--bg2), var(--bg3));
}

/* BRILHOS */
.glow {
  position: fixed;
  width: 420px;
  height: 420px;
  border-radius: 50%;
  filter: blur(45px);
  opacity: 0.35;
  z-index: 0;
  pointer-events: none;
}
.glow-1 {
  background: rgba(255, 255, 255, 0.35);
  top: -140px;
  left: -140px;
}
.glow-2 {
  background: rgba(255, 255, 255, 0.24);
  bottom: -160px;
  right: -160px;
}

/* ABERTURA */
.intro {
  position: fixed;
  inset: 0;
  z-index: 2000;
  display: grid;
  place-items: center;
  padding: 18px;
  background: rgba(0, 0, 0, 0.55);
  backdrop-filter: blur(12px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}

.intro-card {
  width: min(540px, 92vw);
  border-radius: 26px;
  padding: 26px 18px;
  text-align: center;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.16);
  box-shadow: 0 18px 55px rgba(0, 0, 0, 0.45);
  transform: translateY(6px);
  animation: introPop 0.7s ease-out forwards;
}

@keyframes introPop {
  to {
    transform: translateY(0);
  }
}

.intro-title {
  margin: 6px 0 10px;
  font-size: clamp(26px, 6vw, 40px);
}

.intro-small {
  margin: 0;
  opacity: 0.9;
  font-weight: 900;
}

.intro-text {
  margin: 0 0 14px;
  opacity: 0.92;
  line-height: 1.5;
}

.intro-hint {
  margin: 14px 0 0;
  opacity: 0.85;
  font-size: 13px;
}

.intro--hide {
  opacity: 0;
  transform: scale(1.02);
  pointer-events: none;
}

/* Transição do site ao entrar */
.page {
  position: relative;
  z-index: 1;
  transition: opacity 0.8s ease, filter 0.8s ease, transform 0.8s ease;
}
.page--hidden {
  opacity: 0;
  filter: blur(8px);
  transform: translateY(12px);
  pointer-events: none;
}

/* HEADER */
header {
  position: sticky;
  top: 0;
  z-index: 50;
  background: rgba(0, 0, 0, 0.26);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.header-wrap {
  width: min(980px, 92vw);
  margin: 0 auto;
  padding: 18px 0 16px;
  text-align: center;
}

header h1 {
  margin: 0;
  font-size: 26px;
  letter-spacing: 0.4px;
}

.subtitle {
  margin: 6px 0 10px;
  opacity: 0.9;
}

header nav {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  justify-content: center;
}

header nav a {
  color: var(--text);
  text-decoration: none;
  font-weight: 900;
  padding: 9px 12px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.12);
  transition: transform 0.18s, background 0.18s;
}

header nav a:hover {
  transform: translateY(-1px);
  background: rgba(255, 255, 255, 0.16);
}

/* MAIN */
main {
  width: min(980px, 92vw);
  margin: 0 auto;
  padding: 28px 0 50px;
}

section {
  margin: 22px 0 40px;
}

/* COMPONENTES */
.card {
  border-radius: 24px;
  padding: 26px 18px;
  box-shadow: var(--shadow2);
}

.glass {
  background: var(--glass);
  border: 1px solid var(--border);
  backdrop-filter: blur(10px);
}

.glass-soft {
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.14);
  backdrop-filter: blur(10px);
}

.center {
  text-align: center;
}

h2 {
  margin: 0 0 10px;
  font-size: clamp(22px, 4.6vw, 34px);
}

.muted {
  margin: 0;
  color: var(--muted);
}

/* CONTADOR */
.hero {
  display: grid;
  gap: 14px;
}

.hero-top {
  margin: 0;
  opacity: 0.95;
}

.counter-card {
  padding: 26px 18px;
  border-radius: 26px;
  background: rgba(0, 0, 0, 0.26);
  border: 1px solid rgba(255, 255, 255, 0.14);
  box-shadow: var(--shadow);
  text-align: center;
}

.counter-label {
  margin: 0;
  opacity: 0.95;
  font-weight: 900;
}

.counter-number {
  margin: 10px 0 6px;
  display: flex;
  justify-content: center;
  align-items: baseline;
  gap: 10px;
  flex-wrap: wrap;
}

#daysCount {
  font-size: clamp(62px, 10vw, 98px);
  font-weight: 900;
  letter-spacing: 1px;
  text-shadow: 0 16px 36px rgba(0, 0, 0, 0.35);
}

.counter-days {
  font-size: clamp(22px, 3.8vw, 34px);
  font-weight: 900;
  opacity: 0.95;
}

.counter-extra {
  margin: 10px auto 0;
  display: flex;
  justify-content: center;
  gap: 12px;
  flex-wrap: wrap;
}

.time-box {
  min-width: 92px;
  padding: 12px 14px;
  border-radius: 16px;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.14);
  box-shadow: var(--shadow2);
}

.time-box span {
  display: block;
  font-size: 28px;
  font-weight: 900;
  letter-spacing: 0.4px;
}

.time-box small {
  opacity: 0.9;
  font-weight: 900;
}

.counter-since {
  margin: 12px 0 0;
  opacity: 0.9;
}

.hero-badges {
  margin-top: 14px;
  display: flex;
  justify-content: center;
  gap: 10px;
  flex-wrap: wrap;
}

.badge {
  padding: 10px 14px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.12);
  border: 1px solid rgba(255, 255, 255, 0.14);
}

/* BOTÕES */
.btn {
  margin-top: 18px;
  border: none;
  cursor: pointer;
  padding: 14px 22px;
  border-radius: 16px;
  font-size: 16px;
  font-weight: 900;
  color: #111;
  background: #fff;
  position: relative;
  overflow: hidden;
  box-shadow: 0 16px 40px rgba(0, 0, 0, 0.42);
  transition: transform 0.2s, box-shadow 0.2s, opacity 0.2s;
}

.btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 22px 55px rgba(0, 0, 0, 0.5);
}

.btn:active {
  transform: translateY(0px);
}

.btn-soft {
  background: rgba(255, 255, 255, 0.82);
}

.btn-love {
  background: #fff;
}

.btn-shine {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    110deg,
    transparent 0%,
    rgba(255, 255, 255, 0.35) 40%,
    transparent 65%
  );
  transform: translateX(-120%);
  transition: transform 0.7s;
}

.btn:hover .btn-shine {
  transform: translateX(120%);
}

/* HISTÓRIA */
.grid-3 {
  display: grid;
  gap: 14px;
  margin-top: 14px;
}

.mini {
  padding: 16px;
  border-radius: 18px;
}

.mini h3 {
  margin: 0 0 8px;
}

.mini p {
  margin: 0;
  opacity: 0.92;
  line-height: 1.45;
}

/* CARTA */
.love-note {
  margin-top: 12px;
  padding: 18px;
  border-radius: 20px;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.14);
}

.note-title {
  margin: 0 0 10px;
  font-weight: 900;
  font-size: 18px;
}

.note-body {
  margin: 0;
  line-height: 1.6;
  opacity: 0.95;
}

.note-sign {
  margin-top: 14px;
  text-align: right;
  opacity: 0.95;
  font-weight: 900;
}

/* FINAL */
.final-actions {
  margin-top: 14px;
  display: flex;
  gap: 12px;
  justify-content: center;
  flex-wrap: wrap;
}

.final-msg {
  margin: 16px 0 0;
  font-weight: 900;
  font-size: 18px;
}

/* FOOTER */
footer {
  text-align: center;
  padding: 18px;
  opacity: 0.92;
}

/* RESPONSIVO */
@media (min-width: 800px) {
  .grid-3 {
    grid-template-columns: repeat(3, 1fr);
  }
}

/* EFEITOS */
#effects-layer {
  position: fixed;
  inset: 0;
  pointer-events: none;
  overflow: hidden;
  z-index: 999;
}

.flower {
  position: absolute;
  top: -40px;
  font-size: 26px;
  filter: drop-shadow(0 10px 14px rgba(0, 0, 0, 0.25));
  animation: fall 2.1s ease-in forwards;
}

.heart {
  position: absolute;
  bottom: -40px;
  font-size: 24px;
  filter: drop-shadow(0 10px 14px rgba(0, 0, 0, 0.25));
  animation: rise 2.2s ease-out forwards;
}

@keyframes fall {
  0% {
    transform: translateY(-30px) rotate(0deg);
    opacity: 0;
  }
  15% {
    opacity: 1;
  }
  100% {
    transform: translateY(110vh) rotate(240deg);
    opacity: 0;
  }
}

@keyframes rise {
  0% {
    transform: translateY(30px) scale(0.95);
    opacity: 0;
  }
  20% {
    opacity: 1;
  }
  100% {
    transform: translateY(-110vh) scale(1.35);
    opacity: 0;
  }
}

            </p>
          </article>

          <article class="mini glass-soft">
            <h3>💖 O que eu amo</h3>
            <p>
              Eu amo seu sorriso, seu jeitinho e como você transforma momentos
              simples em memórias. Amo quando voce briga comigo, adoro quando voce me tira varias risadas, quando voce enche eu de beijinhos.
            </p>
          </article>

          <article class="mini glass-soft">
            <h3>✨ O que eu quero</h3>
            <p>
              Eu quero estar com você em cada fase, cuidar de você e construir
              um “nós” cada dia mais forte. Construir uma familia, nos casarmos e termos aquela casa que sempre sonhamos, esse e o meu maior sonho.
            </p>
          </article>
        </div>
      </section>

      <!-- CARTA -->
      <section id="carta" class="card glass">
        <h2>Uma carta pra você 💌</h2>

        <div class="love-note">
          <p class="note-title">Meu amor…</p>
          <p class="note-body">
            Eu fiz esse site porque queria lhe trazer algo diferente... algo que eu pensei que voce gostaria
            <br /><br />
            Você é a minha princesa, com quem eu irei passar o resto da minha vida com voce, ao seu lado, te amando cada segundo mais. Tudo na minha vida, meus atos, se remetem a voce, eu tenho um orgulho imenso de quem eu conquistei (VOCE)            <br />
            Quando eu penso em “felicidade”, vem os momentos de risada, brincadeiras que nos fazemos juntos.Nao so momentos de brincadeiras e de risadas, mas tambem os momentos ruins que temos tambem.
            <br /><br />
            Obrigado por existir em minha vida. Eu te amo. 💖
          </p>

          <div class="note-sign">
            <span>— Levi 💖</span>
          </div>
        </div>
      </section>

      <!-- MÚSICA -->
      <section id="musica" class="card glass">
        <h2>Eu Escolhi Para Voce🎵</h2>
        <p class="muted">I Wanna Be Yours — Arctic Monkeys</p>

        <div class="embed">
          <iframe
            style="border-radius: 16px"
            src="https://open.spotify.com/embed/track/5XeFesFbtLpXzIVDNQP22n"
            width="100%"
            height="152"
            frameborder="0"
            allow="
              autoplay;
              clipboard-write;
              encrypted-media;
              fullscreen;
              picture-in-picture;
            "
            loading="lazy"
            title="Spotify - I Wanna Be Yours"
          ></iframe>
        </div>
      </section>

      <!-- FINAL -->
      <section id="final" class="card glass center final">
        <h2>Meu amor eu ja sei mas… você quer ser minha pessoa pra vida toda? 💍💖</h2>
        <p class="muted">Se você apertar SIM, vai chover amor aqui 😍</p>

        <div class="final-actions">
          <button id="btnSim" class="btn btn-love" type="button">
            SIM 💍💍
            <span class="btn-shine" aria-hidden="true"></span>
          </button>

          <button id="btnNao" class="btn btn-soft" type="button">
            
            <span class="btn-shine" aria-hidden="true"></span>
          </button>
        </div>

        <p id="finalMsg" class="final-msg" aria-live="polite"></p>
      </section>
    </main>

    <footer>
      <p>Feito com amor pelo seu vivi💖</p>
    </footer>

    <script src="script.js"></script>
  </body>
</html>

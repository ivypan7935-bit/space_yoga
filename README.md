# space_yoga[index.html.html](https://github.com/user-attachments/files/26259553/index.html.html)
<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>妳現在最需要的是哪一道光？｜SPACE 女人圈</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@300;400;500&family=Noto+Sans+TC:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #f7f2ea;
    --cream2: #f0ead9;
    --green: #6b9970;
    --green-dark: #3d6b42;
    --green-light: #e8f0e6;
    --brown: #3a2e22;
    --brown-mid: #6b5a48;
    --brown-light: #a09070;
    --white: #fdfaf5;
    --border: rgba(107,153,112,0.2);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--cream);
    font-family: 'Noto Sans TC', sans-serif;
    color: var(--brown);
    min-height: 100vh;
    overflow-x: hidden;
  }

  .bg-deco {
    position: fixed; inset: 0; pointer-events: none; z-index: 0;
    overflow: hidden;
  }
  .bg-deco::before {
    content: '';
    position: absolute;
    top: -80px; right: -80px;
    width: 400px; height: 400px;
    border-radius: 50%;
    background: rgba(107,153,112,0.07);
  }
  .bg-deco::after {
    content: '';
    position: absolute;
    bottom: -60px; left: -60px;
    width: 300px; height: 300px;
    border-radius: 50%;
    background: rgba(107,153,112,0.05);
  }

  .container {
    position: relative; z-index: 1;
    max-width: 520px;
    margin: 0 auto;
    padding: 0 20px;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }

  .header {
    padding: 28px 0 0;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .logo {
    font-family: 'Noto Serif TC', serif;
    font-size: 13px;
    letter-spacing: 3px;
    color: var(--green);
    font-weight: 300;
  }
  .header-date {
    font-size: 11px;
    letter-spacing: 1px;
    color: var(--brown-light);
  }

  .progress-wrap {
    padding: 16px 0 0;
    display: none;
  }
  .progress-wrap.show { display: block; }
  .progress-track {
    height: 2px;
    background: var(--border);
    border-radius: 2px;
    overflow: hidden;
  }
  .progress-fill {
    height: 100%;
    background: var(--green);
    border-radius: 2px;
    transition: width 0.5s ease;
    width: 0%;
  }
  .progress-label {
    font-size: 10px;
    color: var(--brown-light);
    margin-top: 6px;
    letter-spacing: 1px;
  }

  .screen { display: none; flex: 1; }
  .screen.active { display: flex; flex-direction: column; }

  /* ── INTRO ── */
  .intro-wrap {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 40px 0 60px;
  }
  .leaf-icon {
    width: 56px; height: 56px;
    margin-bottom: 24px;
  }
  .intro-tag {
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--green);
    margin-bottom: 12px;
  }
  .intro-title {
    font-family: 'Noto Serif TC', serif;
    font-size: 32px;
    font-weight: 300;
    line-height: 1.45;
    color: var(--brown);
    margin-bottom: 8px;
  }
  .intro-en {
    font-size: 11px;
    letter-spacing: 2px;
    color: var(--brown-light);
    margin-bottom: 28px;
  }
  .intro-desc {
    font-size: 14px;
    line-height: 1.8;
    color: var(--brown-mid);
    margin-bottom: 40px;
    max-width: 340px;
  }
  .intro-units {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 40px;
  }
  .unit-tag {
    background: var(--green-light);
    border: 0.5px solid rgba(107,153,112,0.3);
    border-radius: 20px;
    padding: 4px 12px;
    font-size: 10px;
    letter-spacing: 1.5px;
    color: var(--green-dark);
  }
  .start-btn {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: var(--green);
    color: var(--white);
    border: none;
    border-radius: 30px;
    padding: 14px 32px;
    font-family: 'Noto Sans TC', sans-serif;
    font-size: 14px;
    letter-spacing: 1px;
    cursor: pointer;
    transition: background 0.2s, transform 0.15s;
    align-self: flex-start;
  }
  .start-btn:hover { background: var(--green-dark); transform: translateY(-1px); }
  .start-btn svg { transition: transform 0.2s; }
  .start-btn:hover svg { transform: translateX(3px); }

  /* ── QUESTION ── */
  .q-wrap {
    flex: 1;
    padding: 32px 0 40px;
    display: flex;
    flex-direction: column;
  }
  .q-tag {
    font-size: 10px;
    letter-spacing: 2.5px;
    color: var(--green);
    margin-bottom: 8px;
  }
  .q-text {
    font-family: 'Noto Serif TC', serif;
    font-size: 20px;
    font-weight: 300;
    line-height: 1.6;
    color: var(--brown);
    margin-bottom: 28px;
  }
  .opts {
    display: flex;
    flex-direction: column;
    gap: 10px;
    flex: 1;
  }
  .opt-btn {
    background: var(--white);
    border: 0.5px solid var(--border);
    border-radius: 14px;
    padding: 14px 16px;
    text-align: left;
    cursor: pointer;
    font-family: 'Noto Sans TC', sans-serif;
    font-size: 13px;
    color: var(--brown);
    line-height: 1.55;
    transition: all 0.18s;
    display: flex;
    align-items: flex-start;
    gap: 10px;
  }
  .opt-btn:hover {
    background: var(--green-light);
    border-color: rgba(107,153,112,0.4);
    transform: translateX(3px);
  }
  .opt-btn.selected {
    background: var(--green-light);
    border-color: var(--green);
    color: var(--green-dark);
  }
  .opt-letter {
    font-size: 11px;
    font-weight: 500;
    color: var(--green);
    min-width: 16px;
    padding-top: 1px;
    letter-spacing: 0.5px;
  }
  .opt-btn.selected .opt-letter { color: var(--green-dark); }

  .nav-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 28px;
  }
  .nav-back {
    background: none;
    border: 0.5px solid var(--border);
    border-radius: 20px;
    padding: 9px 20px;
    font-size: 12px;
    color: var(--brown-light);
    cursor: pointer;
    font-family: 'Noto Sans TC', sans-serif;
    transition: all 0.18s;
  }
  .nav-back:hover { border-color: var(--green); color: var(--green-dark); }
  .nav-back:disabled { opacity: 0.3; cursor: default; pointer-events: none; }
  .nav-next {
    background: var(--green);
    border: none;
    border-radius: 20px;
    padding: 10px 24px;
    font-size: 12px;
    color: var(--white);
    cursor: pointer;
    font-family: 'Noto Sans TC', sans-serif;
    letter-spacing: 0.5px;
    transition: all 0.18s;
    opacity: 0.4;
    pointer-events: none;
  }
  .nav-next.ready { opacity: 1; pointer-events: all; }
  .nav-next.ready:hover { background: var(--green-dark); transform: translateY(-1px); }

  /* ── RESULT ── */
  .result-wrap {
    flex: 1;
    padding: 40px 0 60px;
    display: flex;
    flex-direction: column;
  }
  .result-tag {
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--green);
    margin-bottom: 6px;
  }
  .result-unit {
    font-size: 15px;
    letter-spacing: 2px;
    color: var(--green-dark);
    margin-bottom: 10px;
    font-weight: 500;
  }
  .result-title {
    font-family: 'Noto Serif TC', serif;
    font-size: 28px;
    font-weight: 400;
    line-height: 1.5;
    color: var(--brown);
    margin-bottom: 20px;
  }

  .result-card {
    background: var(--white);
    border: 0.5px solid var(--border);
    border-radius: 20px;
    padding: 22px 20px;
    margin-bottom: 16px;
  }
  .result-desc {
    font-size: 14px;
    line-height: 1.85;
    color: var(--brown-mid);
    margin-bottom: 16px;
  }
  .result-divider {
    height: 0.5px;
    background: var(--border);
    margin: 16px 0;
  }
  .result-teacher-label {
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--green);
    margin-bottom: 6px;
  }
  .result-teacher {
    font-size: 13px;
    color: var(--brown);
    line-height: 1.6;
  }

  .result-note {
    font-size: 13px;
    color: var(--brown-mid);
    line-height: 1.7;
    text-align: center;
    padding: 16px;
    border-top: 0.5px solid var(--border);
    border-bottom: 0.5px solid var(--border);
    margin-bottom: 28px;
  }

  .cta-btn {
    display: block;
    width: 100%;
    background: var(--green);
    color: var(--white);
    border: none;
    border-radius: 14px;
    padding: 16px;
    font-family: 'Noto Sans TC', sans-serif;
    font-size: 14px;
    letter-spacing: 1px;
    cursor: pointer;
    text-align: center;
    margin-bottom: 12px;
    transition: all 0.2s;
    text-decoration: none;
  }
  .cta-btn:hover { background: var(--green-dark); transform: translateY(-1px); }

  .info-row {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 8px;
    margin-bottom: 24px;
  }
  .info-cell {
    background: var(--cream2);
    border-radius: 10px;
    padding: 10px 8px;
    text-align: center;
  }
  .info-label {
    font-size: 9px;
    letter-spacing: 1px;
    color: var(--brown-light);
    margin-bottom: 4px;
  }
  .info-val {
    font-size: 12px;
    font-weight: 500;
    color: var(--brown);
  }

  .reset-btn {
    background: none;
    border: none;
    font-size: 12px;
    color: var(--brown-light);
    cursor: pointer;
    text-decoration: underline;
    font-family: 'Noto Sans TC', sans-serif;
    display: block;
    margin: 0 auto;
  }
  .reset-btn:hover { color: var(--green); }

  .footer {
    padding: 24px 0;
    text-align: center;
    font-size: 10px;
    color: var(--brown-light);
    letter-spacing: 1px;
    border-top: 0.5px solid var(--border);
    margin-top: auto;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .screen.active { animation: fadeUp 0.4s ease both; }
</style>
</head>
<body>

<div class="bg-deco"></div>

<div class="container">
  <div class="header">
    <div class="logo">SPACE</div>
    <div class="header-date">2026.7.25 — 7.26</div>
  </div>

  <div class="progress-wrap" id="progress-wrap">
    <div class="progress-track">
      <div class="progress-fill" id="progress-fill"></div>
    </div>
    <div class="progress-label" id="progress-label"></div>
  </div>

  <!-- INTRO -->
  <div class="screen active" id="screen-intro">
    <div class="intro-wrap">
      <svg class="leaf-icon" viewBox="0 0 56 56" fill="none" xmlns="http://www.w3.org/2000/svg">
        <ellipse cx="28" cy="32" rx="16" ry="20" fill="#c8ddc8" opacity="0.5"/>
        <ellipse cx="28" cy="32" rx="9" ry="14" fill="#6b9970" opacity="0.4"/>
        <line x1="28" y1="12" x2="28" y2="52" stroke="#3d6b42" stroke-width="1.2" stroke-linecap="round"/>
        <line x1="28" y1="26" x2="20" y2="33" stroke="#3d6b42" stroke-width="0.9" stroke-linecap="round"/>
        <line x1="28" y1="36" x2="36" y2="42" stroke="#3d6b42" stroke-width="0.9" stroke-linecap="round"/>
      </svg>
      <div class="intro-tag">SPACE 女人圈</div>
      <div class="intro-title">妳現在最需要的<br>是哪一道光？</div>
      <div class="intro-en">Rise in Your Light</div>
      <div class="intro-desc">在角色與期待之間奔波的妳，是否也渴望一次真正回到自己的時刻？<br><br>5 個問題，找到屬於妳的身心旅程入口。</div>
      <div class="intro-units">
        <span class="unit-tag">Release</span>
        <span class="unit-tag">Receive</span>
        <span class="unit-tag">Reconnect</span>
        <span class="unit-tag">Rise</span>
        <span class="unit-tag">Illuminate</span>
      </div>
      <button class="start-btn" onclick="startQuiz()">
        開始測驗
        <svg width="14" height="14" viewBox="0 0 14 14" fill="none"><path d="M3 7h8M8 4l3 3-3 3" stroke="white" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </button>
    </div>
  </div>

  <!-- QUESTIONS -->
  <div class="screen" id="screen-q">
    <div class="q-wrap">
      <div class="q-tag" id="q-tag">SPACE 女人圈測驗</div>
      <div class="q-text" id="q-text"></div>
      <div class="opts" id="q-opts"></div>
      <div class="nav-row">
        <button class="nav-back" id="btn-back" onclick="prevQ()" disabled>← 上一題</button>
        <button class="nav-next" id="btn-next" onclick="nextQ()">下一題 →</button>
      </div>
    </div>
  </div>

  <!-- RESULT -->
  <div class="screen" id="screen-result">
    <div class="result-wrap">
      <div class="result-tag">妳的測驗結果</div>
      <div class="result-unit" id="r-unit"></div>
      <div class="result-title" id="r-title"></div>
      <div class="result-card">
        <div class="result-desc" id="r-desc"></div>
      </div>
      <div class="result-note">無論妳從哪裡開始，這五段旅程都會一路陪伴妳。<br>Release → Receive → Reconnect → Rise → Illuminate</div>
      <div class="info-row">
        <div class="info-cell">
          <div class="info-label">課程日期</div>
          <div class="info-val">7/25–7/26</div>
        </div>
        <div class="info-cell">
          <div class="info-label">早鳥截止</div>
          <div class="info-val">6/24</div>
        </div>
        <div class="info-cell">
          <div class="info-label">地點</div>
          <div class="info-val">明曜旗艦館</div>
        </div>
      </div>
      <a class="cta-btn" href="https://space.yoga.tw" target="_blank">把這兩天留給自己 → 立即報名</a>
      <button class="reset-btn" onclick="resetQuiz()">重新測驗</button>
    </div>
  </div>

  <div class="footer">SPACE · 女人圈 · 拾光 Rise in Your Light</div>
</div>

<script>
const questions = [
  {
    text: '最近一次獨處，妳做了什麼？',
    opts: [
      { l: 'A', t: '發呆，但腦子還是停不下來', v: 'A' },
      { l: 'B', t: '滑手機，其實不知道在找什麼', v: 'B' },
      { l: 'C', t: '想聯絡某人，卻不知道說什麼', v: 'C' },
      { l: 'D', t: '想動一動，卻提不起勁', v: 'D' },
      { l: 'E', t: '有很多感受，說不清楚是什麼', v: 'E' }
    ]
  },
  {
    text: '別人問「最近還好嗎？」妳通常怎麼回？',
    opts: [
      { l: 'A', t: '「還好啊」（但其實不太好）', v: 'A' },
      { l: 'B', t: '「有點累，但撐著」', v: 'B' },
      { l: 'C', t: '「不知道耶，說不上來」', v: 'C' },
      { l: 'D', t: '「想做些什麼，但沒有力氣」', v: 'D' },
      { l: 'E', t: '「有點複雜，一時說不清楚」', v: 'E' }
    ]
  },
  {
    text: '這個週末完全屬於妳，妳最想要的是？',
    opts: [
      { l: 'A', t: '什麼都不做，就只是放空', v: 'A' },
      { l: 'B', t: '被好好照顧一下', v: 'B' },
      { l: 'C', t: '找個人真正聊聊', v: 'C' },
      { l: 'D', t: '讓身體動起來、感受活著', v: 'D' },
      { l: 'E', t: '把心裡某個東西說出來', v: 'E' }
    ]
  },
  {
    text: '妳最近常常有一種感覺是？',
    opts: [
      { l: 'A', t: '身體很緊，肩膀一直放不下來', v: 'A' },
      { l: 'B', t: '需要有人幫我，但開不了口', v: 'B' },
      { l: 'C', t: '跟自己有點陌生，不知道要什麼', v: 'C' },
      { l: 'D', t: '想衝、卻感覺被什麼東西卡住', v: 'D' },
      { l: 'E', t: '有些感受悶著，一直沒說出口', v: 'E' }
    ]
  },
  {
    text: '如果給自己一句話，妳最需要聽到哪一句？',
    opts: [
      { l: 'A', t: '「妳可以放下了。」', v: 'A' },
      { l: 'B', t: '「妳值得被好好照顧。」', v: 'B' },
      { l: 'C', t: '「回來找自己吧。」', v: 'C' },
      { l: 'D', t: '「妳的力量還在，只是需要被喚醒。」', v: 'D' },
      { l: 'E', t: '「妳的感受值得被看見。」', v: 'E' }
    ]
  }
];

const results = {
  A: {
    unit: 'Release · 釋放',
    title: '妳需要的，是一個真正放下的出口',
    desc: '肩膀扛太久了，是時候讓身體先鬆開。'
  },
  B: {
    unit: 'Receive · 接受',
    title: '妳需要的，是允許自己被照顧',
    desc: '不是再努力一點，而是停下來，感受已經在的支持。'
  },
  C: {
    unit: 'Reconnect · 重連',
    title: '妳需要的，是回到自己',
    desc: '在所有關係與角色之間，有一個人一直在等妳——就是妳自己。'
  },
  D: {
    unit: 'Rise · 昇起',
    title: '妳需要的，是重新感受身體裡的力量',
    desc: '不是用力撐，而是讓內在的能量自然昇起。'
  },
  E: {
    unit: 'Illuminate · 綻放',
    title: '妳需要的，是一個讓感受被看見的空間',
    desc: '那些說不清楚的，都值得被好好承接。'
  }
};

let currentQ = 0;
const answers = [null, null, null, null, null];

function startQuiz() {
  showScreen('screen-q');
  document.getElementById('progress-wrap').classList.add('show');
  renderQ(0);
}

function renderQ(idx) {
  currentQ = idx;
  const q = questions[idx];
  document.getElementById('q-tag').textContent = `0${idx + 1} / 05　SPACE 女人圈測驗`;
  document.getElementById('q-text').textContent = q.text;
  const optsEl = document.getElementById('q-opts');
  optsEl.innerHTML = '';
  q.opts.forEach(o => {
    const btn = document.createElement('button');
    btn.className = 'opt-btn' + (answers[idx] === o.v ? ' selected' : '');
    btn.innerHTML = `<span class="opt-letter">${o.l}</span><span>${o.t}</span>`;
    btn.onclick = () => selectOpt(idx, o.v, btn);
    optsEl.appendChild(btn);
  });
  document.getElementById('btn-back').disabled = idx === 0;
  const nextBtn = document.getElementById('btn-next');
  nextBtn.textContent = idx === 4 ? '看結果 →' : '下一題 →';
  nextBtn.className = 'nav-next' + (answers[idx] ? ' ready' : '');
  updateProgress(idx);
}

function selectOpt(qIdx, val, btn) {
  answers[qIdx] = val;
  document.querySelectorAll('#q-opts .opt-btn').forEach(b => b.classList.remove('selected'));
  btn.classList.add('selected');
  document.getElementById('btn-next').classList.add('ready');
}

function nextQ() {
  if (!answers[currentQ]) return;
  if (currentQ === 4) { showResult(); return; }
  renderQ(currentQ + 1);
}

function prevQ() {
  if (currentQ === 0) return;
  renderQ(currentQ - 1);
}

function showResult() {
  const cnt = { A: 0, B: 0, C: 0, D: 0, E: 0 };
  answers.forEach(a => { if (a) cnt[a]++; });
  const top = Object.entries(cnt).sort((a, b) => b[1] - a[1])[0][0];
  const r = results[top];
  document.getElementById('r-unit').textContent = r.unit;
  document.getElementById('r-title').textContent = r.title;
  document.getElementById('r-desc').textContent = r.desc;
  document.getElementById('progress-wrap').classList.remove('show');
  showScreen('screen-result');
}

function resetQuiz() {
  answers.fill(null);
  currentQ = 0;
  document.getElementById('progress-wrap').classList.remove('show');
  showScreen('screen-intro');
}

function showScreen(id) {
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  window.scrollTo(0, 0);
}

function updateProgress(idx) {
  const pct = ((idx + 1) / 6) * 100;
  document.getElementById('progress-fill').style.width = pct + '%';
  document.getElementById('progress-label').textContent = `${idx + 1} / 5`;
}
</script>
</body>
</html>

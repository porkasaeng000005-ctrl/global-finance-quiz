[global_finance_quiz.html](https://github.com/user-attachments/files/22363646/global_finance_quiz.html)[Uploading global<!doctype html>
<html lang="th">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>เกมถามตอบ: ระบบการเงินโลก</title>
  <style>
    :root{--bg:#f8fbff;--card:#ffffff;--accent:#0ea5e9;--muted:#6b7280;}
    *{box-sizing:border-box}
    body{margin:0;font-family:Inter,ui-sans-serif,system-ui,-apple-system,"Segoe UI",Roboto,"Helvetica Neue",Arial;background:linear-gradient(180deg,var(--bg),#fff);color:#0f172a;min-height:100vh;display:flex;align-items:center;justify-content:center;padding:24px}
    .card{width:100%;max-width:900px;background:var(--card);border-radius:14px;box-shadow:0 8px 28px rgba(2,6,23,0.08);padding:28px}
    header{display:flex;justify-content:space-between;align-items:flex-start;gap:12px}
    h1{margin:0;font-size:22px}
    p.sub{margin:6px 0 0;color:var(--muted);font-size:13px}
    .meta{text-align:right;color:var(--muted);font-size:13px}
    .question{margin-top:18px;font-weight:600;font-size:18px;display:flex;justify-content:space-between;align-items:center}
    .options{margin-top:14px;display:grid;gap:10px}
    .opt{padding:12px;border-radius:10px;border:1px solid #e6eef6;background:#fff;cursor:pointer;display:flex;justify-content:space-between;align-items:center}
    .opt.selected{background:#eff8ff;border-color:var(--accent)}
    .opt.disabled{opacity:0.45;text-decoration:line-through;cursor:not-allowed}
    .controls{margin-top:18px;display:flex;justify-content:space-between;align-items:center;gap:12px}
    button{border:0;padding:10px 14px;border-radius:8px;cursor:pointer;font-weight:600}
    .btn-primary{background:var(--accent);color:white}
    .btn-ghost{background:#fff;border:1px solid #e6eef6}
    .hint{background:#fffbeb;border:1px solid #fde68a;color:#794c0a}
    .result{padding:18px;text-align:center}
    ol{padding-left:18px}
    .answers{margin-top:16px}
    footer{margin-top:18px;color:var(--muted);font-size:12px}
    @media (max-width:600px){.question{font-size:16px}}
  </style>
</head>
<body>
  <div class="card" role="application" aria-label="Global Finance Quiz Game">
    <header>
      <div>
        <h1>เกมถามตอบ: ระบบการเงินโลก</h1>
        <p class="sub">ตอบคำถามเพื่อทดสอบความรู้จากรายงานที่ให้มา</p>
      </div>
      <div class="meta">
        <div id="progress">คำถาม 1 / 10</div>
        <div id="score">คะแนน: 0</div>
      </div>
    </header>

    <main id="game">
      <div class="question">
        <div id="qtext">...</div>
        <div style="color:var(--muted)" id="timer">30s</div>
      </div>

      <div class="options" id="options"></div>

      <div class="controls">
        <div style="display:flex;gap:8px">
          <button id="hintBtn" class="hint">ใช้คำใบ้ (0)</button>
          <button id="submitBtn" class="btn-primary" disabled>ตอบ</button>
        </div>
        <div id="remaining" style="color:var(--muted)"></div>
      </div>
    </main>

    <section id="resultSection" style="display:none" class="result">
      <h2 id="finalTitle">ผลลัพธ์ของคุณ</h2>
      <p id="finalScore" style="font-size:18px;margin:8px 0">คุณได้คะแนน 0 / 10</p>
      <div style="display:flex;gap:8px;justify-content:center">
        <button id="restartBtn" class="btn-primary">เล่นอีกครั้ง</button>
        <button id="topBtn" class="btn-ghost">กลับขึ้นบน</button>
      </div>

      <div class="answers">
        <h3 style="text-align:left;margin-top:18px">เฉลยคำถาม</h3>
        <ol id="answersList"></ol>
      </div>
    </section>

    <footer>เกมนี้สร้างจากเนื้อหาในรายงาน \"ระบบการเงินโลก\" — ใช้เพื่อการศึกษาเท่านั้น</footer>
  </div>

<script>
(function(){
  const questions = [
    {
      id:1,
      q:'บทบาทหลักของ IMF (กองทุนการเงินระหว่างประเทศ) คืออะไร?',
      options:['ให้สินเชื่อระยะยาวแก่ธุรกิจเอกชน','รักษาเสถียรภาพทางการเงินและให้ความช่วยเหลือทางการเงินแก่ประเทศที่เผชิญวิกฤต','ออกธนบัตรและเหรียญของแต่ละประเทศ','เป็นตลาดซื้อขายหุ้นระหว่างประเทศ'],
      a:1
    },
    {
      id:2,
      q:'ธนาคารโลก (World Bank) เน้นบทบาทด้านใดมากที่สุด?',
      options:['การพัฒนาในระยะยาวและลดความยากจน','การกำหนดอัตราดอกเบี้ยระยะสั้น','การออกบัตรเครดิตทั่วโลก','เป็นผู้ตรวจสอบบัญชีระหว่างประเทศ'],
      a:0
    },
    {
      id:3,
      q:'ตลาดเงิน (Money Market) มีลักษณะอย่างไร?',
      options:['ตราสารมีอายุเกิน 10 ปี','ตราสารระยะสั้น (อายุไม่เกิน 1 ปี) เพื่อรักษาสภาพคล่อง','เป็นตลาดหุ้นสำหรับบริษัทขนาดเล็ก','เป็นตลาดซื้อขายอสังหาริมทรัพย์'],
      a:1
    },
    {
      id:4,
      q:'ตัวอย่างตราสารในตลาดเงินข้อใดคือ \"T-bill\" (ตั๋วเงินคลัง)?',
      options:['พันธบัตรรัฐบาลระยะยาว 20 ปี','ตราสารหนีระยะสั้นที่ไม่จ่ายดอกเบี้ยเป็นงวด แต่ขายด้วยส่วนลด','หุ้นสามัญ','ใบรับฝากเงิน (CD)'],
      a:1
    },
    {
      id:5,
      q:'ข้อใดคือหน้าที่สำคัญของธนาคารกลาง?',
      options:['กำหนดและดำเนินนโยบายการเงิน ควบคุมปริมาณเงิน และเป็น Lender of Last Resort','จัดตั้งกองทุนรวมเพื่อประชาชนทั่วไป','ออกหุ้นของรัฐวิสาหกิจ','บริหารการส่งเสริมการท่องเที่ยว'],
      a:0
    },
    {
      id:6,
      q:'ระบบชำระเงินไร้รอยต่อระหว่างประเทศ (Cross-border seamless payment) เช่น PromptPay-PayNow มีประโยชน์อย่างไร?',
      options:['ทำให้การโอนเงินข้ามประเทศช้าขึ้น','ช่วยให้โอนเงินข้ามพรมแดนเร็ว สะดวก และมีค่าธรรมเนียมต่ำกว่าแบบเดิม','ลดความปลอดภัยในการชำระเงิน','ทำให้ต้องพกเงินสดมากขึ้น'],
      a:1
    },
    {
      id:7,
      q:'อะไรคือ Repurchase Agreement (Repo)?',
      options:['สัญญาขายหลักทรัพย์แล้วสัญญาซื้อคืนในอนาคตเพื่อกู้ยืมระยะสั้น','การออกหุ้นเพิ่มทุน','การแลกเปลี่ยนสกุลเงินทันที','ตราสารหนี้ที่ไม่มีหลักประกัน'],
      a:0
    },
    {
      id:8,
      q:'บทบาทหลักของ BIS (Bank for International Settlements) คืออะไร?',
      options:['เป็นศูนย์กลางของธนาคารกลางทั่วโลกและช่วยกำหนดมาตรฐานการเงิน','เป็นธนาคารพาณิชย์ขนาดใหญ่ที่สุด','ออกสกุลเงินดิจิทัลสำหรับประเทศสมาชิก','ให้สินเชื่อบุคคลทั่วไป'],
      a:0
    },
    {
      id:9,
      q:'ข้อใดเป็นตัวอย่างของตลาดทุน (Capital Market)?',
      options:['ตลาดพันธบัตรรัฐบาลระยะสั้น','ตลาดหุ้น (Stock Exchange) และการออกพันธบัตรระยะยาว','ตลาดฝากประจำของธนาคาร','ตลาดแลกเปลี่ยนเงินตราต่างประเทศ (Forex) เท่านั้น'],
      a:1
    },
    {
      id:10,
      q:'ขั้นตอนการชำระเงินผ่านบัตร (เช่น Visa) ขั้นแรกคืออะไร?',
      options:['Authorization — เครื่องรูดบัตรส่งคำขออนุมัติไปยังธนาคารผู้รับ','การแปลงค่าเงินและอนุมัติ','การถอนเงินจากตู้ ATM','การคืนเงิน (Refund)'],
      a:0
    }
  ];

  let index = 0, selected = null, score = 0, usedHints = 0, timer = 30, timerId = null, isPlaying = true;

  const qtext = document.getElementById('qtext');
  const optionsDiv = document.getElementById('options');
  const progress = document.getElementById('progress');
  const scoreDiv = document.getElementById('score');
  const timerDiv = document.getElementById('timer');
  const submitBtn = document.getElementById('submitBtn');
  const hintBtn = document.getElementById('hintBtn');
  const remaining = document.getElementById('remaining');
  const resultSection = document.getElementById('resultSection');
  const finalScore = document.getElementById('finalScore');
  const answersList = document.getElementById('answersList');
  const restartBtn = document.getElementById('restartBtn');
  const topBtn = document.getElementById('topBtn');

  function startTimer(){
    clearInterval(timerId);
    timer = 30;
    timerDiv.textContent = timer + 's';
    timerId = setInterval(()=>{
      timer--;
      timerDiv.textContent = timer + 's';
      if(timer<=0){ clearInterval(timerId); handleNext(); }
    },1000);
  }

  function render(){
    const q = questions[index];
    progress.textContent = 'คำถาม ' + (index+1) + ' / ' + questions.length;
    scoreDiv.textContent = 'คะแนน: ' + score;
    remaining.textContent = (questions.length - index - 1) + ' คำถามถัดไป';
    qtext.textContent = q.q;
    optionsDiv.innerHTML = '';
    q.options.forEach((opt,i)=>{
      const btn = document.createElement('button');
      btn.className = 'opt';
      btn.type='button';
      btn.innerHTML = '<span style="font-weight:600">'+String.fromCharCode(65+i)+'. '+opt+'</span><span></span>';
      if(selected===i) btn.classList.add('selected');
      // if hint used, disable one wrong option deterministically
      const hideWrong = (usedHints>0) && (i!==q.a) && (i===0) && (usedHints%2===1);
      if(hideWrong) btn.classList.add('disabled');
      btn.disabled = hideWrong;
      btn.addEventListener('click', ()=>{
        if(btn.disabled) return;
        selected = i;
        document.querySelectorAll('.opt').forEach(el=>el.classList.remove('selected'));
        btn.classList.add('selected');
        submitBtn.disabled = false;
      });
      optionsDiv.appendChild(btn);
    });
    submitBtn.disabled = true;
    selected = null;
    startTimer();
  }

  function handleSubmit(){
    if(selected===null){
      // try to find selected element
      const sel = document.querySelector('.opt.selected');
      if(sel){
        const all = Array.from(document.querySelectorAll('.opt'));
        selected = all.indexOf(sel);
      } else return;
    }
    const q = questions[index];
    if(selected === q.a) score++;
    // move next
    handleNext();
  }

  function handleNext(){
    clearInterval(timerId);
    index++;
    if(index < questions.length){
      selected = null;
      render();
    } else {
      showResult();
    }
  }

  function handleHint(){
    usedHints++;
    hintBtn.textContent = 'ใช้คำใบ้ ('+usedHints+')';
    // re-render to apply hint disabling rule
    render();
  }

  function showResult(){
    isPlaying = false;
    resultSection.style.display = 'block';
    document.getElementById('game').style.display = 'none';
    finalScore.textContent = 'คุณได้คะแนน ' + score + ' / ' + questions.length;
    // populate answers
    answersList.innerHTML = '';
    questions.forEach(q=>{
      const li = document.createElement('li');
      li.innerHTML = '<div style=\"font-weight:600;margin-bottom:4px\">'+q.q+'</div>' +
        '<div style=\"color:var(--muted)\">คำตอบที่ถูกต้อง: ' + String.fromCharCode(65+q.a) + '. ' + q.options[q.a] + '</div>';
      answersList.appendChild(li);
    });
  }

  function resetGame(){
    index = 0; selected = null; score = 0; usedHints = 0; isPlaying = true;
    document.getElementById('game').style.display = 'block';
    resultSection.style.display = 'none';
    hintBtn.textContent = 'ใช้คำใบ้ (0)';
    render();
  }

  // attach handlers
  submitBtn.addEventListener('click', ()=>{
    // determine selected index from DOM
    const sel = document.querySelector('.opt.selected');
    if(sel){
      const all = Array.from(document.querySelectorAll('.opt'));
      selected = all.indexOf(sel);
    }
    if(selected===null) return;
    handleSubmit();
  });

  hintBtn.addEventListener('click', handleHint);
  restartBtn.addEventListener('click', resetGame);
  topBtn.addEventListener('click', ()=>window.scrollTo({top:0,behavior:'smooth'}));

  // keyboard accessibility: 1-4 select options, Enter submits
  window.addEventListener('keydown', (e)=>{
    const k = e.key;
    if(k>='1' && k<='4'){
      const idx = parseInt(k,10)-1;
      const opts = document.querySelectorAll('.opt');
      if(opts[idx] && !opts[idx].disabled){
        opts[idx].click();
      }
    }
    if(k==='Enter'){
      document.getElementById('submitBtn').click();
    }
  });

  // initial render
  render();

})();
</script>
</body>
</html>
_finance_quiz.html…]()

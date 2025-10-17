<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Frontline Group of Schools — Agbor</title>
  <meta name="description" content="Frontline Group of Schools, Agbor — Education is a Necessity. Admissions, news, staff, facilities and contact." />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">  <style>
    /* -------------------------------------------------------------
       Frontline Group of Schools — Single-file demo
       - How to split: copy <style> into styles.css and the <script> into jarvis.js
       - This file contains: responsive layout, nav, hero, sections, staff, news, contact, and a small "Jarvis" assistant
       ------------------------------------------------------------- */

    :root{
      --bg:#0f1724; /* deep navy */
      --card:#0b1220;
      --muted:#94a3b8;
      --accent:#ef6c00; /* warm orange */
      --glass: rgba(255,255,255,0.04);
      --radius:14px;
      --max-width:1100px;
      --shadow: 0 6px 20px rgba(2,6,23,0.6);
      font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
      color-scheme: dark;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#061028 0%, #0a1530 100%);color:#e6eef8}
    a{color:inherit;text-decoration:none}

    .container{max-width:var(--max-width);margin:0 auto;padding:28px}

    header{backdrop-filter: blur(6px);background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:12px;padding:10px 14px;margin:10px 0;display:flex;align-items:center;justify-content:space-between;gap:12px}
    .brand{display:flex;align-items:center;gap:12px}
    .logo{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,#0ea5a2,#7c3aed);display:flex;align-items:center;justify-content:center;font-weight:700;font-size:18px;box-shadow:var(--shadow)}
    .brand h1{font-size:18px;margin:0}
    nav{display:flex;gap:10px;align-items:center}
    nav a{padding:8px 12px;border-radius:10px;font-weight:600;color:var(--muted)}
    nav a:hover{background:var(--glass);color:#fff}

    .hero{display:grid;grid-template-columns:1fr 420px;gap:20px;align-items:center;margin-top:18px}
    .hero .panel{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:22px;border-radius:16px;box-shadow:var(--shadow)}
    .hero h2{margin:0 0 8px;font-size:28px}
    .motto{color:var(--accent);font-weight:700}
    .quickstats{display:flex;gap:12px;margin-top:14px}
    .stat{background:rgba(255,255,255,0.02);padding:12px;border-radius:12px;min-width:110px;text-align:center}
    .stat b{display:block;font-size:18px}

    /* Cards grid */
    .grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:18px}
    .card{background:var(--card);padding:16px;border-radius:12px}

    /* Staff list */
    .staff-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:12px}
    .teacher{display:flex;gap:12px;align-items:center;padding:12px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.015), rgba(255,255,255,0.01))}
    .avatar{width:56px;height:56px;border-radius:10px;background:linear-gradient(135deg,#2563eb,#06b6d4);display:flex;align-items:center;justify-content:center;font-weight:700}

    /* News / Accordion */
    details{background:var(--card);padding:12px;border-radius:10px}

    /* Contact */
    form{display:grid;gap:10px}
    input,textarea,select{padding:10px;border-radius:8px;border:none;background:rgba(255,255,255,0.02);color:inherit}
    button.primary{background:var(--accent);border:none;padding:10px 14px;border-radius:10px;font-weight:700;color:#051018}

    footer{margin-top:26px;padding:18px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.00));display:flex;justify-content:space-between;gap:12px}

    /* Jarvis assistant */
    .jarvis-fab{position:fixed;right:22px;bottom:22px;width:64px;height:64px;border-radius:999px;background:linear-gradient(135deg,#ef6c00,#f59e0b);display:flex;align-items:center;justify-content:center;font-size:22px;box-shadow:0 10px 30px rgba(239,108,0,0.18);cursor:pointer}
    .jarvis-panel{position:fixed;right:22px;bottom:100px;width:360px;max-width:calc(100% - 48px);background:linear-gradient(180deg,#071026, #071827);border-radius:14px;padding:12px;box-shadow:0 20px 50px rgba(2,6,23,0.6);display:flex;flex-direction:column;gap:10px}
    .jarvis-messages{height:280px;overflow:auto;padding:8px;display:flex;flex-direction:column;gap:8px}
    .message{max-width:82%;padding:8px;border-radius:10px}
    .message.user{align-self:flex-end;background:rgba(255,255,255,0.05)}
    .message.bot{align-self:flex-start;background:rgba(255,255,255,0.02)}
    .jarvis-input{display:flex;gap:8px}
    .jarvis-input input{flex:1}

    /* Responsiveness */
    @media (max-width:900px){
      .hero{grid-template-columns:1fr}
      .grid{grid-template-columns:repeat(2,1fr)}
    }
    @media (max-width:560px){
      .grid{grid-template-columns:repeat(1,1fr)}
      nav{display:none}
      header{padding:12px}
    }
  </style></head>
<body>
  <div class="container">
    <header aria-label="Top navigation">
      <div class="brand">
        <div class="logo">FG</div>
        <div>
          <h1>Frontline Group of Schools — Agbor</h1>
          <div style="font-size:12px;color:var(--muted)">Motto: <span class="motto">Education is a Necessity</span></div>
        </div>
      </div><nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#staff">Staff</a>
    <a href="#news">News</a>
    <a href="#facilities">Facilities</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<main>
  <section id="home" class="hero">
    <article class="panel">
      <h2>Welcome to Frontline Group of Schools — Agbor</h2>
      <p style="color:var(--muted);margin-top:6px">A family-focused private school committed to academic excellence, character formation and practical skills development.</p>

      <div class="quickstats" aria-hidden>
        <div class="stat"><div style="font-size:12px;color:var(--muted)">Students</div><b id="stat-students">640</b></div>
        <div class="stat"><div style="font-size:12px;color:var(--muted)">Staff</div><b id="stat-staff">37</b></div>
        <div class="stat"><div style="font-size:12px;color:var(--muted)">Passing Rate</div><b id="stat-pass">100%</b></div>
      </div>

      <div style="margin-top:14px;display:flex;gap:8px">
        <a class="primary" href="#admissions" style="background:transparent;border:1px solid rgba(255,255,255,0.04);padding:10px 12px;border-radius:10px;color:var(--muted)">Admissions</a>
        <a class="primary" href="#contact" style="background:var(--accent);color:#051018">Contact Us</a>
      </div>

    </article>

    <aside class="panel" aria-labelledby="panel-title">
      <h3 id="panel-title">Quick Contact</h3>
      <p style="color:var(--muted);">Address: <br/><strong id="school-address">23 &amp; 37 Martin Street, Agbor (Near St. Joseph Catholic Church)</strong></p>
      <p style="color:var(--muted);">Phone: <a id="school-phone" href="tel:+2349011744586">+234 901 174 4586</a></p>

      <div style="margin-top:10px">
        <strong>Proprietor</strong>
        <div id="proprietor">Deacon Sunny Osuhon</div>
        <strong style="margin-top:8px;display:block">Head Teacher</strong>
        <div id="headteacher">Mrs. Osuhon Marian</div>
      </div>
    </aside>
  </section>

  <section id="about" class="grid" aria-label="About the school">
    <div class="card">
      <h3>About Us</h3>
      <p style="color:var(--muted)">Frontline Group of Schools, Agbor is a private school known for strong moral values and academic achievement. In 2025 the PTA praised the school for achieving 100% pass rate in all external examinations (WAEC, NECO, BECE for JSS3, Cognitive for Primary 6). The school combines classroom learning with practical skill acquisition programmes such as perfume and liquid soap making.</p>
    </div>

    <div class="card">
      <h3>Vision &amp; Mission</h3>
      <p style="color:var(--muted)"><strong>Vision:</strong> To be a leading centre of excellence producing disciplined, skilled and God-fearing graduates.<br/><strong>Mission:</strong> Provide a balanced education that combines academic rigor, vocational skills and character formation.</p>
    </div>

    <div class="card">
      <h3>Fast Facts</h3>
      <ul style="color:var(--muted);margin:8px 0;padding-left:18px">
        <li>Student population (2025): <strong>640</strong></li>
        <li>Graduating students (2025): <strong>173</strong> (30 Nursery 3, 45 Primary 6, 40 JSS3, 58 SS3)</li>
        <li>Qualified staff: <strong>37</strong></li>
        <li>Official motto: <em>Education is a Necessity</em></li>
      </ul>
    </div>
  </section>

  <section id="staff" style="margin-top:18px">
    <h3>Our Staff &amp; Leadership</h3>
    <div class="staff-grid">
      <div class="teacher">
        <div class="avatar">DS</div>
        <div>
          <div style="font-weight:700">Deacon Sunny Osuhon</div>
          <div style="font-size:13px;color:var(--muted)">Proprietor</div>
        </div>
      </div>

      <div class="teacher">
        <div class="avatar">MO</div>
        <div>
          <div style="font-weight:700">Mrs. Osuhon Marian</div>
          <div style="font-size:13px;color:var(--muted)">Head Teacher (Primary 6 teacher)</div>
        </div>
      </div>

      <div class="teacher">
        <div class="avatar">RC</div>
        <div>
          <div style="font-weight:700">Rev. Richard Ijeagun</div>
          <div style="font-size:13px;color:var(--muted)">PTA Chairman (Also chaired 2025 graduation)</div>
        </div>
      </div>

      <div class="teacher">
        <div class="avatar">YO</div>
        <div>
          <div style="font-weight:700">Mr. Chiyem Ojei (Yoriyori)</div>
          <div style="font-size:13px;color:var(--muted)">PTA Vice Chairman</div>
        </div>
      </div>

    </div>
  </section>

  <section id="news" style="margin-top:18px">
    <h3>Latest News</h3>
    <div style="display:grid;gap:8px">
      <details open>
        <summary style="font-weight:700">July 2025 — PTA praises 100% pass rate &amp; graduation highlights</summary>
        <div style="color:var(--muted);margin-top:8px">The PTA celebrated Frontline's academic achievements, applauding the 100% pass rate across public examinations and expressing gratitude. Infrastructure and skill-acquisition programmes were highlighted as drivers for student success.</div>
      </details>

      <details>
        <summary style="font-weight:700">Skill programmes introduced (Perfume &amp; Liquid Soap Making)</summary>
        <div style="color:var(--muted);margin-top:8px">A hands-on programme to equip students with vocational skills that can generate income and encourage entrepreneurship.</div>
      </details>

      <details>
        <summary style="font-weight:700">School growth &amp; student body (2025)</summary>
        <div style="color:var(--muted);margin-top:8px">Frontline Group of Schools has grown to serve up to 640 students across its sections — Nursery, Primary, JSS and SSS — while investing in infrastructure and staff development.</div>
      </details>
    </div>
  </section>

  <section id="facilities" style="margin-top:18px">
    <h3>Facilities &amp; Programmes</h3>
    <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:10px;margin-top:8px">
      <div class="card">
        <strong>Classrooms &amp; Labs</strong>
        <p style="color:var(--muted);margin:6px 0">Modern classrooms and science labs for practical lessons.</p>
      </div>
      <div class="card">
        <strong>Skill-Acquisition Labs</strong>
        <p style="color:var(--muted);margin:6px 0">Workshops for perfume and liquid soap making and other vocational skills.</p>
      </div>
      <div class="card">
        <strong>Play &amp; Sports</strong>
        <p style="color:var(--muted);margin:6px 0">Facilities for physical development including games and training.</p>
      </div>
    </div>
  </section>

  <section id="admissions" style="margin-top:18px">
    <h3>Admissions</h3>
    <div class="card">
      <p style="color:var(--muted)">We admit students into Nursery, Primary, Junior Secondary and Senior Secondary. Admissions prioritise character, academic promise and parental support. Please contact the school office for the admissions schedule, fees and required documents.</p>
      <ul style="color:var(--muted);margin-top:8px;padding-left:18px">
        <li>Contact the admissions office via phone or visit the school.</li>
        <li>Bring birth certificate, previous school records, and passport photographs.</li>
      </ul>
    </div>
  </section>

  <section id="contact" style="margin-top:18px">
    <h3>Contact &amp; Visit</h3>
    <div style="display:grid;grid-template-columns:1fr 360px;gap:12px">
      <div class="card">
        <h4>Send a message</h4>
        <form id="contactForm" onsubmit="return false">
          <input id="cname" placeholder="Your full name" required />
          <input id="cemail" placeholder="Email or phone" required />
          <textarea id="cmessage" rows="4" placeholder="How can we help?" required></textarea>
          <div style="display:flex;gap:8px">
            <button class="primary" id="sendBtn">Send Message</button>
            <button type="button" id="saveLocal">Save Locally</button>
          </div>
          <div id="contactResult" style="margin-top:8px;color:var(--muted)"></div>
        </form>
      </div>

      <aside class="card">
        <h4>Visit Us</h4>
        <p style="color:var(--muted)">23 &amp; 37 Martin Street, Agbor (near St. Joseph Catholic Church)<br/>Open Monday — Friday: 8:00am — 3:30pm</p>
        <p style="color:var(--muted)"><strong>Phone:</strong> <a id="phone2" href="tel:+2349011744586">+234 901 174 4586</a></p>
      </aside>
    </div>
  </section>

</main>

<footer>
  <div>
    <strong>Frontline Group of Schools — Agbor</strong>
    <div style="font-size:13px;color:var(--muted)">23 &amp; 37 Martin Street, Agbor • Motto: Education is a Necessity</div>
  </div>

  <div style="text-align:right;color:var(--muted)">
    <div>Proprietor: Deacon Sunny Osuhon</div>
    <div style="font-size:13px;margin-top:8px">PTA Chairman: Rev. Richard Ijeagun • PTA Vice Chairman: Mr. Chiyem Ojei</div>
  </div>
</footer>

  </div>  <!-- Jarvis Assistant (simple, local-only) -->  <div id="jarvisFab" class="jarvis-fab" title="Open Jarvis assistant">🤖</div>
  <div id="jarvisPanel" class="jarvis-panel" style="display:none" role="dialog" aria-label="Jarvis assistant">
    <div style="display:flex;justify-content:space-between;align-items:center">
      <strong>Jarvis — Frontline Assistant</strong>
      <button id="jarvisClose" aria-label="Close Jarvis" style="background:none;border:none;color:var(--muted);font-weight:700">✕</button>
    </div>
    <div class="jarvis-messages" id="jarvisMessages" aria-live="polite"></div>
    <div class="jarvis-input">
      <input id="jarvisInput" placeholder="Ask Jarvis: fees, admissions, address, staff..." />
      <button id="jarvisSend">Ask</button>
    </div>
    <div style="font-size:12px;color:var(--muted)">Tip: teach Jarvis by typing "teach: question => answer"</div>
  </div>  <script>
    /* ------------------ Embedded school data (from memory) ------------------ */
    const SCHOOL = {
      name: 'Frontline Group of Schools, Agbor',
      motto: 'Education is a Necessity',
      address: '23 & 37 Martin Street, Agbor (near St. Joseph Catholic Church)',
      phone: '+2349011744586',
      proprietor: 'Deacon Sunny Osuhon',
      headteacher: 'Mrs. Osuhon Marian',
      ptaChair: 'Rev. Richard Ijeagun',
      ptaVice: 'Mr. Chiyem Ojei (Yoriyori)',
      students2025: 640,
      staffCount: 37,
      passingRate: '100%',
      graduating2025: 173,
      skillPrograms: ['Perfume making','Liquid soap making'],
      note: 'School celebrated 100% pass rate in 2025 across WAEC, NECO, BECE and Cognitive (Primary 6).'
    };

    /* Populate DOM with dynamic values */
    document.getElementById('stat-students').textContent = SCHOOL.students2025;
    document.getElementById('stat-staff').textContent = SCHOOL.staffCount;
    document.getElementById('stat-pass').textContent = SCHOOL.passingRate;
    document.getElementById('school-address').textContent = SCHOOL.address;
    document.getElementById('school-phone').textContent = SCHOOL.phone;
    document.getElementById('school-phone').href = 'tel:' + SCHOOL.phone.replace(/\s+/g,'');
    document.getElementById('proprietor').textContent = SCHOOL.proprietor;
    document.getElementById('headteacher').textContent = SCHOOL.headteacher;
    document.getElementById('phone2').href = 'tel:' + SCHOOL.phone.replace(/\s+/g,'');

    /* ------------------ Contact form behavior (frontend-only) ------------------ */
    const contactForm = document.getElementById('contactForm');
    const sendBtn = document.getElementById('sendBtn');
    const saveLocalBtn = document.getElementById('saveLocal');
    const contactResult = document.getElementById('contactResult');

    sendBtn.addEventListener('click', () => {
      const name = document.getElementById('cname').value.trim();
      const email = document.getElementById('cemail').value.trim();
      const message = document.getElementById('cmessage').value.trim();
      if(!name || !email || !message){ contactResult.textContent = 'Please complete all fields.'; return; }
      // Simulate send — in production replace with API call
      contactResult.textContent = 'Message saved locally and shown below (this demo does not send email).';
      saveMessageLocally({name,email,message,ts:new Date().toISOString()});
    });

    saveLocalBtn.addEventListener('click', ()=>{
      const name = document.getElementById('cname').value.trim();
      const email = document.getElementById('cemail').value.trim();
      const message = document.getElementById('cmessage').value.trim();
      if(!name || !email || !message){ contactResult.textContent = 'Please complete all fields.'; return; }
      saveMessageLocally({name,email,message,ts:new Date().toISOString()});
      contactResult.textContent = 'Saved to browser storage.';
    });

    function saveMessageLocally(obj){
      const key = 'fg_messages_v1';
      const cur = JSON.parse(localStorage.getItem(key) || '[]');
      cur.push(obj);
      localStorage.setItem(key, JSON.stringify(cur));
    }

    /* ------------------ Jarvis assistant ------------------ */
    const fab = document.getElementById('jarvisFab');
    const panel = document.getElementById('jarvisPanel');
    const closeBtn = document.getElementById('jarvisClose');
    const messagesEl = document.getElementById('jarvisMessages');
    const inputEl = document.getElementById('jarvisInput');
    const sendEl = document.getElementById('jarvisSend');

    function showPanel(){ panel.style.display='flex'; inputEl.focus(); }
    function hidePanel(){ panel.style.display='none'; }

    fab.addEventListener('click',()=>{
      if(panel.style.display === 'none' || panel.style.display === '') showPanel(); else hidePanel();
    });
    closeBtn.addEventListener('click', hidePanel);

    function appendMessage(text, who='bot'){
      const div = document.createElement('div');
      div.className = 'message ' + (who==='user'? 'user' : 'bot');
      div.textContent = text;
      messagesEl.appendChild(div);
      messagesEl.scrollTop = messagesEl.scrollHeight;
    }

    // Load any 'taught' responses saved by the user
    const LEARN_KEY = 'fg_jarvis_learn_v1';
    function loadLearned(){
      try{# Frontline-Group-of-school-s-
Education 

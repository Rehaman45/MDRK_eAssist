<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MD RK eAssist</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@600;800&family=Poppins:wght@400;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #0d6efd;
      --secondary: #00c9a7;
      --accent: #ffb400;
      --bg: #f8f9fa;
      --card-bg: #ffffff;
      --header-bg: linear-gradient(90deg, #0d6efd 60%, #00c9a7 100%);
      --footer-bg: #343a40;
      --shadow: 0 8px 24px rgba(13,110,253,0.12);
      --radius: 18px;
    }
    html { scroll-behavior: smooth; }
    body {
      font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0; padding: 0;
      background: var(--bg); color: #222;
    }
    header.hero {
      background: var(--header-bg);
      color: white;
      padding: 3.2rem 1rem 2.2rem 1rem;
      text-align: center;
      position: relative;
      overflow: hidden;
      animation: gradientMove 6s linear infinite alternate;
    }
    @keyframes gradientMove {
      0% { background-position: 0% 50%; }
      100% { background-position: 100% 50%; }
    }
    header.hero::before, header.hero::after {
      content: "";
      position: absolute;
      border-radius: 50%;
      opacity: 0.18;
      pointer-events: none;
      animation: float 7s ease-in-out infinite alternate;
      z-index: 0;
    }
    header.hero::before {
      top: -120px; right: -100px;
      width: 350px; height: 350px;
      background: radial-gradient(circle, #00c9a7 0%, transparent 70%);
      animation-delay: 0.5s;
    }
    header.hero::after {
      bottom: -90px; left: -80px;
      width: 230px; height: 230px;
      background: radial-gradient(circle, #ffb400 0%, transparent 70%);
      animation-delay: 2s;
    }
    @keyframes float {
      to { transform: translateY(30px) scale(1.08);}
    }
    .hero h1 {
      font-family: 'Montserrat', sans-serif;
      font-size: 3.3rem;
      margin-bottom: 0.4rem;
      letter-spacing: 2px;
      font-weight: 800;
      z-index: 2; position: relative;
      text-shadow: 2px 4px 24px rgba(13,110,253,0.12);
      animation: fadeInDown 1.1s cubic-bezier(.35,1.44,.7,1.01);
    }
    @keyframes fadeInDown {
      from {opacity:0; transform:translateY(-40px);}
      to {opacity:1; transform:translateY(0);}
    }
    .tagline {
      font-size: 1.4rem;
      font-style: italic;
      font-weight: 600;
      color: var(--accent);
      margin-bottom: 1rem;
      z-index: 2; position: relative;
      animation: fadeInUp 1.5s;
    }
    @keyframes fadeInUp {
      from {opacity:0; transform:translateY(40px);}
      to {opacity:1; transform:translateY(0);}
    }
    .hero-contact {
      font-weight: 500;
      margin-top: 0.5rem;
      z-index: 2; position: relative;
      font-size: 1.1rem;
      letter-spacing: 1.2px;
      animation: fadeIn 2s;
    }
    @keyframes fadeIn { from { opacity:0; } to { opacity:1; } }

    /* Services Section */
    section {
      padding: 2.5rem 1rem;
      text-align: center;
      position: relative;
    }
    section h2 {
      font-size: 2.2rem;
      font-family: 'Montserrat', sans-serif;
      color: var(--primary);
      margin-bottom: 2rem;
      letter-spacing: 1px;
      position: relative;
      display: inline-block;
      padding-bottom: 0.3rem;
      border-bottom: 3px solid var(--accent);
      background: linear-gradient(90deg, #0d6efd11 60%, #00c9a711 100%);
      border-radius: 8px;
      transition: border-bottom-color 0.4s;
      animation: pulseGlow 2.2s infinite alternate;
    }
    @keyframes pulseGlow {
      from { border-bottom-color: var(--accent);}
      to { border-bottom-color: var(--primary);}
    }
    .services {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 2.2rem;
      margin-top: 1.5rem;
      z-index: 1;
      position: relative;
    }
    .card {
      background: var(--card-bg);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 2.2rem 1.2rem 1.8rem 1.2rem;
      width: 260px;
      transition: transform .22s, box-shadow .22s, border-top .3s;
      border-top: 4px solid var(--primary);
      position: relative;
      cursor:pointer;
      overflow: hidden;
      animation: popIn 1.2s;
    }
    @keyframes popIn {
      from {transform: scale(0.8); opacity:0;}
      to {transform: scale(1); opacity:1;}
    }
    .card:hover {
      transform: translateY(-9px) scale(1.06) rotate(-1deg);
      box-shadow: 0 16px 32px rgba(0,201,167,0.13);
      border-top: 4px solid var(--accent);
      z-index: 2;
    }
    .card h3 {
      color: var(--primary);
      font-size: 1.33rem;
      margin-bottom: 0.7rem;
      font-weight: 700;
      letter-spacing: 1px;
      transition: color 0.25s;
    }
    .card:hover h3 { color: var(--accent);}
    .card p {
      font-size: 1.07rem;
      color: #555;
      min-height: 48px;
    }
    .card .emoji {
      font-size: 2.5rem;
      margin-bottom: 0.4rem;
      display: block;
      animation: bounce 2s infinite alternate;
    }
    @keyframes bounce {
      from {transform: translateY(0);}
      to {transform: translateY(-10px);}
    }
    .service-highlight {
      background: linear-gradient(90deg, #0d6efd11 60%, #ffb40022 100%);
      border-radius: 8px;
      margin: 0.7rem 0 0.4rem 0;
      padding: 0.2rem 0 0.2rem 0;
      color: var(--secondary);
      font-weight: 600;
      font-size: 0.98rem;
      letter-spacing: 0.5px;
      animation: highlightFade 2.8s infinite alternate;
    }
    @keyframes highlightFade {
      from { background: #e3f7f6; }
      to { background: #fffbe2; }
    }
    .price-btn {
      background: linear-gradient(90deg, var(--accent) 60%, var(--primary) 100%);
      color: white;
      border: none;
      font-weight: 700;
      padding: 0.6rem 1.4rem;
      border-radius: 6px;
      margin-top: 1.2rem;
      font-size: 1.07rem;
      cursor: pointer;
      box-shadow: 0 1px 8px rgba(13,110,253,0.08);
      transition: background 0.16s, color 0.12s, transform 0.14s;
      outline: none;
      animation: pulseBtn 1.4s infinite alternate;
    }
    .price-btn:hover {
      background: linear-gradient(90deg, var(--primary) 70%, var(--accent) 100%);
      color: #212;
      transform: scale(1.05);
    }
    @keyframes pulseBtn {
      from { box-shadow: 0 1px 8px rgba(255,180,0,0.17);}
      to { box-shadow: 0 5px 18px rgba(13,110,253,0.18);}
    }
    /* Modal Styling */
    .modal-backdrop {
      display: none;
      position: fixed; left:0; top:0; width:100vw; height:100vh;
      background: rgba(44,62,80,0.45);
      z-index: 99;
      align-items: center; justify-content: center;
    }
    .modal-backdrop.active { display: flex; }
    .modal {
      background: #fff;
      border-radius: 16px;
      max-width: 95vw;
      width: 340px;
      padding: 2.2rem 1.1rem 1.2rem 1.1rem;
      box-shadow: 0 6px 32px rgba(13,110,253,0.14);
      text-align: center;
      position: relative;
      animation: popIn 0.5s;
    }
    .modal h4 {
      margin-top: 0; color: var(--primary); font-size: 1.28rem;
      font-family: 'Montserrat',sans-serif;
    }
    .modal p { margin: 1.1rem 0 1.6rem 0; font-size: 1.08rem; }
    .modal .btn {
      background: linear-gradient(90deg, var(--primary), var(--secondary));
      color: white; padding: 0.8rem 1.8rem;
      border: none; border-radius: 8px;
      font-size: 1.08rem;
      text-decoration: none;
      display: inline-block;
      margin-top: 0.5rem;
      font-weight: 700;
      box-shadow: 0 2px 10px rgba(13,110,253,0.08);
      transition: background 0.15s, transform 0.13s;
      cursor: pointer;
    }
    .modal .btn:hover {
      background: linear-gradient(90deg, var(--secondary) 70%, var(--accent) 100%);
      color: #111;
      transform: scale(1.03);
    }
    .modal .close-modal {
      position: absolute; top:13px; right:19px;
      font-size: 1.4em; color: #bbb; background: none;
      border: none; cursor: pointer; font-weight: bold;
      transition: color 0.2s;
    }
    .modal .close-modal:hover { color: #e74c3c; }
    /* Chatbot Button */
    .chatbot-btn {
      position: fixed;
      bottom: 30px;
      right: 30px;
      z-index: 130;
      background: linear-gradient(90deg, var(--primary), var(--secondary));
      color: white;
      border: none;
      border-radius: 50%;
      width: 65px;
      height: 65px;
      font-size: 2rem;
      box-shadow: 0 8px 24px rgba(13,110,253,0.18);
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      animation: pulseChat 2s infinite alternate;
      transition: background 0.2s;
    }
    @keyframes pulseChat {
      from { box-shadow: 0 8px 24px rgba(13,110,253,0.18);}
      to { box-shadow: 0 12px 34px rgba(0,201,167,0.22);}
    }
    .chatbot-btn:hover {
      background: linear-gradient(90deg, var(--secondary), var(--primary));
      color: var(--accent);
    }
    /* Chatbot Modal */
    .chatbot-modal-backdrop {
      display: none;
      position: fixed; left:0; top:0; width:100vw; height:100vh;
      background: rgba(44,62,80,0.12);
      z-index: 150;
      align-items: flex-end; justify-content: flex-end;
    }
    .chatbot-modal-backdrop.active { display: flex; }
    .chatbot-modal {
      width: 340px; max-width: 98vw;
      height: 440px; max-height: 90vh;
      background: #fff;
      border-radius: 18px 18px 0 0;
      box-shadow: 0 6px 32px rgba(13,110,253,0.14);
      margin: 0 20px 18px 0;
      display: flex;
      flex-direction: column;
      overflow: hidden;
      animation: popIn 0.7s;
      position: relative;
    }
    .chatbot-header {
      background: var(--primary);
      color: white;
      padding: 1rem;
      font-family: 'Montserrat',sans-serif;
      font-size: 1.15rem;
      font-weight: 700;
      display: flex; align-items: center;
      justify-content: space-between;
    }
    .chatbot-close {
      font-size: 1.3em; color: #fff; background: none; border: none;
      cursor: pointer; font-weight: bold; margin-left: 12px; opacity: 0.85;
      transition: color 0.2s;
    }
    .chatbot-close:hover { color: #ffb400; }
    .chatbot-body {
      flex: 1 1 auto;
      background: #f8f9fa;
      padding: 1rem;
      overflow-y: auto;
      font-size: 1.01rem;
    }
    .chatbot-message {
      margin-bottom: 1rem;
      display: flex;
      align-items: flex-end;
    }
    .chatbot-message.user {
      justify-content: flex-end;
    }
    .chatbot-message .bubble {
      padding: 0.7em 1em;
      border-radius: 16px;
      max-width: 70%;
      box-shadow: 0 2px 12px rgba(13,110,253,0.05);
      word-break: break-word;
      font-size: 1.03em;
    }
    .chatbot-message.bot .bubble {
      background: #e9ecef;
      color: #222;
      border-radius: 16px 16px 16px 3px;
    }
    .chatbot-message.user .bubble {
      background: var(--primary);
      color: white;
      border-radius: 16px 16px 3px 16px;
    }
    .chatbot-footer {
      background: #fff;
      padding: 0.7rem 1rem;
      display: flex;
      border-top: 1px solid #eee;
      align-items: center;
    }
    .chatbot-input {
      flex: 1 1 auto;
      padding: 0.6em 1em;
      border-radius: 15px;
      border: 1px solid #ddd;
      font-size: 1em;
    }
    .chatbot-send {
      margin-left: 0.6rem;
      background: var(--primary);
      color: #fff;
      border: none;
      border-radius: 50%;
      width: 36px;
      height: 36px;
      cursor: pointer;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.4em;
      transition: background 0.15s;
    }
    .chatbot-send:hover { background: var(--secondary);}
    .contact {
      background: #e9ecef;
      padding: 2.5rem 1rem 2rem 1rem;
      border-radius: var(--radius);
      box-shadow: 0 2px 18px rgba(52,58,64,0.06);
      margin: 2rem auto 2.5rem auto;
      max-width: 520px;
      position: relative;
    }
    .contact h2 {
      color: var(--primary);
      margin-bottom: 1.1rem;
      border-bottom: none;
      background: none;
      padding-bottom: 0;
    }
    .contact p {
      font-size: 1.13rem;
      margin-bottom: 1.2rem;
      color: #333;
    }
    .btn {
      background: linear-gradient(90deg, var(--primary), var(--secondary));
      color: white;
      padding: 0.9rem 2.1rem;
      border: none;
      border-radius: 8px;
      font-size: 1.13rem;
      text-decoration: none;
      display: inline-block;
      margin-top: 0.5rem;
      font-weight: 700;
      box-shadow: 0 2px 10px rgba(13,110,253,0.08);
      transition: background 0.15s, transform 0.13s;
      cursor: pointer;
    }
    .btn:hover {
      background: linear-gradient(90deg, var(--secondary) 70%, var(--accent) 100%);
      transform: translateY(-3px) scale(1.03);
      color: #222;
    }
    .live-chat {
      margin-top:1.1rem;
      font-size: 1.06rem;
      color: var(--primary);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.6rem;
      font-weight: 600;
      animation: blinkChat 2s infinite alternate;
    }
    .live-support-badge {
      display: inline-flex;
      align-items: center;
      background: var(--secondary);
      color: #fff;
      font-weight: 700;
      font-size: 1em;
      border-radius: 15px;
      padding: 0.3em 1em;
      margin-left: 0.6em;
      animation: pulseBtn 2s infinite alternate;
    }
    .live-support-badge .dot {
      width: 10px; height: 10px;
      background: #00ff60;
      border-radius: 50%;
      display: inline-block;
      margin-right: 7px;
      border: 2px solid #fff;
      box-shadow: 0 0 8px #00ff60;
      animation: blinkDot 1.2s infinite alternate;
    }
    @keyframes blinkDot {
      from { opacity: 0.7;}
      to { opacity: 1;}
    }
    @media (max-width: 900px) {
      .services { flex-direction: column; align-items: center;}
      .card { width: 100%; max-width: 340px;}
    }
    @media (max-width: 650px) {
      .hero h1 { font-size: 2.3rem;}
      section h2 { font-size: 1.45rem;}
      .services { gap: 1.2rem;}
      .contact { padding: 1.3rem 0.7rem;}
      .chatbot-modal { width:98vw; height:65vh; margin: 0 1vw 11vw 0;}
    }
  </style>
</head>
<body>
  <header class="hero">
    <h1>MD RK eAssist</h1>
    <p class="tagline">Your One-Stop Solution for Govt. & Career Services</p>
    <div class="hero-contact">📞 <a href="tel:+917997594485" style="color:#fff;text-decoration:underline;">+91 79975 94485</a> &nbsp;|&nbsp; 📲 DM to Get Started</div>
    <div class="live-support-badge"><span class="dot"></span> 24/7 Live Support</div>
  </header>

  <section id="services">
    <h2>Our Services</h2>
    <div class="services">
      <div class="card" data-service="Passport Applications">
        <span class="emoji">🛂</span>
        <h3>Passport Applications</h3>
        <div class="service-highlight">New & Renewal</div>
        <p>Apply for passports or renewals with expert guidance and hassle-free documentation.</p>
        <button class="price-btn" onclick="showPrice('Passport Applications')">Know Price</button>
      </div>
      <div class="card" data-service="Driving License">
        <span class="emoji">🚗</span>
        <h3>Driving License</h3>
        <div class="service-highlight">Learner & Permanent</div>
        <p>End-to-end help in applying or renewing your driving license with minimal paperwork.</p>
        <button class="price-btn" onclick="showPrice('Driving License')">Know Price</button>
      </div>
      <div class="card" data-service="PAN Card">
        <span class="emoji">💳</span>
        <h3>PAN Card</h3>
        <div class="service-highlight">Apply & Corrections</div>
        <p>Quick PAN card application, corrections, and tracking – all in one place.</p>
        <button class="price-btn" onclick="showPrice('PAN Card')">Know Price</button>
      </div>
      <div class="card" data-service="Scholarships">
        <span class="emoji">🎓</span>
        <h3>Scholarships</h3>
        <div class="service-highlight">All India Students</div>
        <p>Personalized support in applying for national & state-level scholarships across India.</p>
        <button class="price-btn" onclick="showPrice('Scholarships')">Know Price</button>
      </div>
      <div class="card" data-service="Job Applications">
        <span class="emoji">💼</span>
        <h3>Job Applications</h3>
        <div class="service-highlight">Govt. & IT Jobs</div>
        <p>Government and IT job application support, resume creation, and career guidance.</p>
        <button class="price-btn" onclick="showPrice('Job Applications')">Know Price</button>
      </div>
    </div>
  </section>

  <!-- Modal for Price WhatsApp -->
  <div class="modal-backdrop" id="modal-backdrop" onclick="closeModal(event)">
    <div class="modal" id="modal-box" onclick="event.stopPropagation()">
      <button class="close-modal" onclick="closeModal(event)">&times;</button>
      <h4 id="modal-title">Direct Pricing Enquiry</h4>
      <p id="modal-desc">
        To know the exact price for <span id="modal-service" style="color:var(--primary);font-weight:700;"></span>, message us directly on WhatsApp for instant response and personalized assistance!
      </p>
      <a id="modal-whatsapp" class="btn" href="https://wa.me/917997594485?text=Hi%2C%20I%20want%20to%20know%20the%20price%20for%20" target="_blank">
        📲 Message on WhatsApp
      </a>
      <div class="live-chat">
        <span style="font-size:1.2em;">💬</span> Direct Conversation | Fast Reply
      </div>
    </div>
  </div>

  <section class="contact" id="contact">
    <h2>Contact Us</h2>
    <p>No more stress. No more waiting. Just results.<br>
      <span style="color: var(--primary); font-weight: 600;">Get personalized assistance today!</span>
    </p>
    <a href="https://wa.me/917997594485" class="btn" target="_blank">📲 Message on WhatsApp</a>
    <div class="live-chat">
      <span>🟢</span> Live WhatsApp Chat, Instant AI-powered Response!
    </div>
    <div style="margin-top:1.3rem;font-size:0.98rem;color:#666;">
      <span style="font-size:1.2em;color:var(--accent);vertical-align:middle;">⏰</span>
      <span>Always Available • 24/7 Support</span>
    </div>
  </section>

  <footer>
    <p>© 2025 MD RK eAssist | Designed with <span class="footer-heart">❤️</span> by Your Partner</p>
  </footer>

  <!-- AI Chatbot Floating Button -->
  <button class="chatbot-btn" id="chatbotBtn" title="24/7 AI Chat">
    🤖
  </button>
  <!-- Chatbot Modal -->
  <div class="chatbot-modal-backdrop" id="chatbotModalBackdrop">
    <div class="chatbot-modal">
      <div class="chatbot-header">
        <span>Live eAssist AI Support</span>
        <button class="chatbot-close" onclick="closeChatbot()">&times;</button>
      </div>
      <div class="chatbot-body" id="chatbotBody">
        <div class="chatbot-message bot"><div class="bubble">👋 Hi! I’m your 24/7 eAssist AI. How can I help you today?<br>
        <small style="color:#00c9a7">Try: "What documents do I need for a passport?"</small></div></div>
      </div>
      <form class="chatbot-footer" onsubmit="sendChat(event)">
        <input type="text" id="chatbotInput" class="chatbot-input" placeholder="Type your question..." autocomplete="off" />
        <button type="submit" class="chatbot-send" title="Send"><span>➤</span></button>
      </form>
    </div>
  </div>

  <script>
    // Modal for WhatsApp Price
    function showPrice(service) {
      document.getElementById('modal-service').innerText = service;
      document.getElementById('modal-title').innerText = "Know the Price Instantly!";
      document.getElementById('modal-desc').innerHTML =
        'To know the exact price for <span style="color:var(--primary);font-weight:700;">' + service + '</span>, message us directly on WhatsApp for instant response and personalized assistance!';
      let waLink = 'https://wa.me/917997594485?text=' +
        encodeURIComponent('Hi, I want to know the price for ' + service + '. Please provide details.');
      document.getElementById('modal-whatsapp').href = waLink;
      document.getElementById('modal-backdrop').classList.add('active');
      document.body.style.overflow = 'hidden';
    }
    function closeModal(e) {
      document.getElementById('modal-backdrop').classList.remove('active');
      document.body.style.overflow = '';
    }
    // Keyboard Escape key closes modal
    window.addEventListener('keydown', function(e){
      if(e.key === "Escape") closeModal();
    });

    // AI Chatbot UI (Simulated)
    const chatbotBtn = document.getElementById('chatbotBtn');
    const chatbotModalBackdrop = document.getElementById('chatbotModalBackdrop');
    const chatbotBody = document.getElementById('chatbotBody');
    const chatbotInput = document.getElementById('chatbotInput');

    chatbotBtn.onclick = () => {
      chatbotModalBackdrop.classList.add('active');
      chatbotInput.focus();
    };

    function closeChatbot() {
      chatbotModalBackdrop.classList.remove('active');
    }

    function sendChat(e) {
      e.preventDefault();
      const msg = chatbotInput.value.trim();
      if (!msg) return;
      addChatMessage('user', msg);
      chatbotInput.value = '';
      setTimeout(() => {
        addChatMessage('bot', aiReply(msg));
      }, 900);
      chatbotBody.scrollTop = chatbotBody.scrollHeight;
    }

    function addChatMessage(sender, text) {
      const msgDiv = document.createElement('div');
      msgDiv.className = 'chatbot-message ' + sender;
      const bubble = document.createElement('div');
      bubble.className = 'bubble';
      bubble.innerText = text;
      msgDiv.appendChild(bubble);
      chatbotBody.appendChild(msgDiv);
      chatbotBody.scrollTop = chatbotBody.scrollHeight;
    }

    // Simulated AI reply logic
    function aiReply(input) {
      input = input.toLowerCase();
      if(input.includes('passport')) {
        return "For a passport application, you'll need proof of identity, address, and date of birth documents. Message us on WhatsApp for a personalized checklist and instant quote!";
      }
      if(input.includes('pan card')) {
        return "For PAN card application or correction, you need proof of identity, address, and a passport-sized photo. Want exact pricing? Tap 'Know Price' above or message us on WhatsApp!";
      }
      if(input.includes('scholarship')) {
        return "India-wide scholarships often need marksheets, ID, income certificate, and passport-sized photos. We’ll help you sort all paperwork, just ask!";
      }
      if(input.includes('job')) {
        return "For Govt. or IT job applications, we help with forms, documentation, and resume. Send us your requirements for fast support!";
      }
      if(input.includes('price') || input.includes('cost')) {
        return "For transparent pricing, use the 'Know Price' button or message us on WhatsApp for instant response!";
      }
      if(input.includes('documents')) {
        return "Tell us your service (e.g., Passport, PAN, License) and we'll send a custom document checklist!";
      }
      if(input.includes('hello') || input.includes('hi')) {
        return "Hello! 👋 How may I assist you today? Ask about any service, pricing, or documentation!";
      }
      return "I'm here 24/7 to assist with any queries about our services, pricing, or process. For urgent help or document uploads, click 'Message on WhatsApp'!";
    }
  </script>
</body>
</html>

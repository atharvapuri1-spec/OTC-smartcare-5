otc-smartcare/
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>OTC SmartCare | Pharmacist Guided Self-Care</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<header class="hero">
  <h1>OTC SmartCare</h1>
  <p>Pharmacist-guided OTC medicine support for safe self-care</p>

  <div class="lang-toggle">
    <button onclick="setLanguage('en')">EN</button>
    <button onclick="setLanguage('hi')">हिंदी</button>
  </div>

  <a href="#guidance" class="btn">Get OTC Guidance</a>
</header>

<nav>
  <a href="#about">About</a>
  <a href="#how">How It Works</a>
  <a href="#guidance">OTC Guidance</a>
  <a href="#pharmacy">Pharmacies</a>
  <a href="#contact">Contact</a>
</nav>

<section id="about">
  <h2 id="aboutTitle">Why OTC SmartCare?</h2>
  <p id="aboutText">
    OTC SmartCare is a pharmacist-led digital health platform that helps
    people choose safe over-the-counter medicines and avoid harmful
    self-medication.
  </p>
</section>

<section id="how" class="light">
  <h2 id="howTitle">How It Works</h2>
  <div class="steps">
    <div id="s1">1️⃣ Select your symptom</div>
    <div id="s2">2️⃣ Receive OTC guidance</div>
    <div id="s3">3️⃣ Follow safety instructions</div>
    <div id="s4">4️⃣ Visit doctor if required</div>
  </div>
</section>

<section id="guidance">
  <h2 id="guideTitle">Get OTC Guidance</h2>

  <form id="otcForm">
    <label id="ageLabel">Age</label>
    <input type="number" id="age" required>

    <label id="symptomLabel">Select Symptom</label>
    <select id="symptom" required>
      <option value="">--Select--</option>
      <option value="fever">Fever</option>
      <option value="headache">Headache</option>
      <option value="acidity">Acidity</option>
      <option value="cold">Cold & Cough</option>
      <option value="diarrhea">Diarrhea</option>
      <option value="allergy">Allergy</option>
    </select>

    <button type="submit" id="btnText">Get Guidance</button>
  </form>

  <div id="result"></div>
</section>

<section id="pharmacy" class="light">
  <h2>For Pharmacies</h2>
  <p>
    Pharmacies can place a QR code at the counter. Customers scan it to get
    safe OTC guidance instantly, improving trust and repeat visits.
  </p>

  <img
    src="https://api.qrserver.com/v1/create-qr-code/?size=180x180&data=https://otc-smartcare.netlify.app"
    alt="OTC SmartCare QR Code">

  <a class="btn" href="https://wa.me/919022598592">Partner on WhatsApp</a>
</section>

<section id="contact">
  <h2>Contact</h2>
  <p>📞 WhatsApp: <a href="https://wa.me/919022598592">+91 9022598592</a></p>
  <p>📧 Email: puriatharva456@gmail.com</p>
</section>

<footer>
  <p>
    Disclaimer: Educational information only. This is not a diagnosis or
    prescription. Consult a doctor if symptoms persist.
  </p>
  <p>© 2025 OTC SmartCare</p>
</footer>

<a href="https://wa.me/919022598592" class="whatsapp-float">💬</a>

<script src="script.js"></script>
</body>
</html>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f5ffff;
  color: #003333;
}

.hero {
  background: #008080;
  color: white;
  padding: 40px 20px;
  text-align: center;
}

.lang-toggle button {
  margin: 5px;
  padding: 5px 10px;
  border: none;
  cursor: pointer;
}

.btn {
  display: inline-block;
  background: white;
  color: #008080;
  padding: 10px 20px;
  margin-top: 15px;
  text-decoration: none;
  font-weight: bold;
  border-radius: 5px;
}

nav {
  background: #006666;
  text-align: center;
  padding: 10px;
}

nav a {
  color: white;
  margin: 10px;
  text-decoration: none;
}

section {
  padding: 25px;
  max-width: 900px;
  margin: auto;
}

.light {
  background: #e8fafa;
}

.steps div {
  margin: 8px 0;
}

form label {
  display: block;
  margin-top: 10px;
}

input, select, button {
  width: 100%;
  padding: 8px;
  margin-top: 5px;
}

button {
  background: #008080;
  color: white;
  border: none;
  margin-top: 15px;
}

#result {
  margin-top: 20px;
  padding: 15px;
  background: #fff3cd;
  border-left: 5px solid #ff9800;
}

footer {
  background: #006666;
  color: white;
  text-align: center;
  padding: 15px;
  font-size: 14px;
}

/* Floating WhatsApp */
.whatsapp-float {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: #25d366;
  color: white;
  font-size: 28px;
  padding: 12px 15px;
  border-radius: 50%;
  text-decoration: none;
}
document.getElementById("otcForm").addEventListener("submit", function (e) {
  e.preventDefault();

  const age = document.getElementById("age").value;
  const symptom = document.getElementById("symptom").value;

  let msg = "";

  if (symptom === "fever")
    msg = "Paracetamol 500 mg every 6–8 hours. ⚠️ Doctor if fever > 3 days.";

  if (symptom === "headache")
    msg = "Paracetamol preferred. ⚠️ Severe headache → doctor.";

  if (symptom === "acidity")
    msg = "Antacids may help. ⚠️ Chest pain → doctor.";

  if (symptom === "cold")
    msg = "Antihistamines & rest. ⚠️ Breathing issue → doctor.";

  if (symptom === "diarrhea")
    msg = "ORS only. ⚠️ If diarrhea > 2 days → doctor.";

  if (symptom === "allergy")
    msg = "Antihistamines. ⚠️ Swelling or breathing issue → emergency.";

  document.getElementById("result").innerHTML =
    "<strong>OTC Guidance:</strong><br>" +
    msg +
    "<br><br><em>This is not a medical diagnosis.</em>";

  /* Google Form data capture */
  fetch("PASTE_GOOGLE_FORM_URL_HERE", {
    method: "POST",
    mode: "no-cors",
    headers: { "Content-Type": "application/x-www-form-urlencoded" },
    body:
      "entry.1111111111=" + age +
      "&entry.2222222222=" + symptom
  });
});

/* Language Toggle */
function setLanguage(lang) {
  if (lang === "hi") {
    document.querySelector(".hero p").innerText =
      "सुरक्षित स्व-देखभाल के लिए फार्मासिस्ट द्वारा मार्गदर्शन";
    document.getElementById("guideTitle").innerText = "OTC मार्गदर्शन";
    document.getElementById("btnText").innerText = "मार्गदर्शन प्राप्त करें";
  } else {
    location.reload();
  }
}

<!DOCTYPE html>
<html lang="uz">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AnemiMap — Anemiya yordam platformasi</title>

  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f4f8fb;
      color: #222;
    }

    header {
      background: #b71c1c;
      color: white;
      padding: 25px;
      text-align: center;
    }

    header h1 {
      margin: 0;
      font-size: 32px;
    }

    header p {
      margin-top: 8px;
    }

    .container {
      max-width: 900px;
      margin: 30px auto;
      padding: 20px;
    }

    .card {
      background: white;
      padding: 25px;
      margin-bottom: 20px;
      border-radius: 15px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.08);
    }

    h2 {
      color: #b71c1c;
    }

    input {
      width: 90%;
      padding: 12px;
      margin: 8px 0;
      border: 1px solid #ccc;
      border-radius: 8px;
    }

    button {
      background: #b71c1c;
      color: white;
      border: none;
      padding: 13px 25px;
      border-radius: 8px;
      cursor: pointer;
      font-size: 16px;
    }

    button:hover {
      background: #8e0000;
    }

    #result {
      margin-top: 20px;
      padding: 15px;
      border-radius: 10px;
      background: #fff3f3;
      display: none;
    }

    footer {
      text-align: center;
      padding: 20px;
      background: #222;
      color: white;
      margin-top: 30px;
    }
  </style>
</head>

<body>

<header>
  <h1>🩸 AnemiMap</h1>
  <p>Anemiyani erta aniqlash va tibbiy yordamga yo‘naltirish platformasi</p>
</header>

<div class="container">

  <div class="card">
    <h2>🩺 Holatimni tekshirish</h2>
    <p>Gemoglobin ko‘rsatkichingizni kiriting:</p>

    <input type="number" id="hb" placeholder="Masalan: 95">

    <br><br>

    <button onclick="checkAnemia()">Tekshirish</button>

    <div id="result"></div>
  </div>

  <div class="card">
    <h2>📍 AnemiMap xaritasi</h2>
    <p>
      Sizga yaqin tibbiyot muassasalari va mutaxassislarni
      topishga yordam beruvchi xarita funksiyasi.
    </p>

    <button onclick="findDoctor()">Shifokor topish</button>

    <div id="doctorResult"></div>
  </div>

  <div class="card">
    <h2>💡 Anemiya haqida</h2>
    <p>
      Anemiya — qonda gemoglobin yoki eritrotsitlar miqdorining
      kamayishi bilan bog‘liq holat.
    </p>

    <p>
      AnemiMap foydalanuvchiga holatini dastlabki baholash,
      ma’lumot olish va shifokorga murojaat qilish yo‘nalishini
      topishda yordam beradi.
    </p>
  </div>

</div>

<footer>
  © 2026 AnemiMap | Smart anemia support platform
</footer>

<script>

function checkAnemia() {

  let hb = Number(document.getElementById("hb").value);
  let result = document.getElementById("result");

  result.style.display = "block";

  if (!hb) {
    result.innerHTML = "⚠️ Iltimos, gemoglobin qiymatini kiriting.";
    return;
  }

  if (hb < 80) {
    result.innerHTML =
      "🔴 Gemoglobin juda past ko‘rsatkichda. Tezroq shifokorga murojaat qilish tavsiya etiladi.";
  }

  else if (hb < 110) {
    result.innerHTML =
      "🟠 Gemoglobin past bo‘lishi mumkin. Tibbiy ko‘rikdan o‘tish tavsiya etiladi.";
  }

  else {
    result.innerHTML =
      "🟢 Kiritilgan qiymat bo‘yicha anemiya xavfi yuqori ko‘rinmaydi. Aniq baholash uchun shifokor ko‘rigidan o‘ting.";
  }
}

function findDoctor() {

  document.getElementById("doctorResult").innerHTML =
    "<br>📍 Tez orada sizga yaqin shifokor va tibbiyot muassasalarini ko‘rsatish funksiyasi ishga tushiriladi.";

}

</script>

</body>
</html>

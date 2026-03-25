<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Agencia de Modelos - Videos Musicales</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      background: linear-gradient(135deg, #0b0b0f, #1a0033);
      color: #fff;
    }

    header {
      padding: 30px;
      text-align: center;
      background: rgba(0,0,0,0.9);
      border-bottom: 2px solid #d4af37;
    }

    header h1 {
      margin: 0;
      font-size: 36px;
      background: linear-gradient(90deg, #d4af37, #ff4ecd);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    header p {
      color: #bbb;
    }

    .container {
      padding: 20px;
      max-width: 1200px;
      margin: auto;
    }

    .filters {
      margin-bottom: 20px;
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
    }

    .filters input {
      padding: 10px;
      border-radius: 8px;
      border: none;
      outline: none;
      background: #111;
      color: #fff;
      border: 1px solid #333;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 25px;
    }

    .card {
      background: linear-gradient(145deg, #111, #1c1c2e);
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 10px 25px rgba(0,0,0,0.8);
      transition: all 0.3s ease;
      border: 1px solid rgba(255,255,255,0.05);
    }

    .card:hover {
      transform: translateY(-10px) scale(1.03);
      box-shadow: 0 15px 40px rgba(255, 78, 205, 0.3);
    }

    .card img {
      width: 100%;
      height: 320px;
      object-fit: cover;
    }

    .card-content {
      padding: 15px;
      text-align: center;
    }

    .card h3 {
      margin: 10px 0 5px;
      font-size: 20px;
      color: #fff;
    }

    .card p {
      margin: 5px 0;
      font-size: 14px;
      color: #aaa;
    }

    .social a {
      display: inline-block;
      margin: 6px;
      padding: 6px 12px;
      border-radius: 20px;
      background: linear-gradient(90deg, #ff4ecd, #d4af37);
      color: #000;
      font-size: 12px;
      text-decoration: none;
      font-weight: bold;
      transition: 0.3s;
    }

    .social a:hover {
      opacity: 0.8;
    }

    .form-section {
      margin-top: 50px;
      background: linear-gradient(145deg, #111, #1c1c2e);
      padding: 25px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.7);
    }

    .form-section h2 {
      text-align: center;
      background: linear-gradient(90deg, #d4af37, #ff4ecd);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .form-group {
      margin-bottom: 12px;
    }

    .form-group input {
      width: 100%;
      padding: 12px;
      border-radius: 8px;
      border: none;
      background: #0f0f18;
      color: #fff;
      border: 1px solid #333;
    }

    button {
      width: 100%;
      padding: 14px;
      background: linear-gradient(90deg, #ff4ecd, #d4af37);
      border: none;
      border-radius: 10px;
      color: #000;
      font-weight: bold;
      cursor: pointer;
      font-size: 16px;
      transition: 0.3s;
    }

    button:hover {
      transform: scale(1.03);
      opacity: 0.9;
    }

    footer {
      text-align: center;
      padding: 20px;
      background: #000;
      margin-top: 30px;
      color: #888;
    }
  </style>
</head>
<body>

<header>
  <h1>Agencia de Modelos</h1>
  <p>Contrata talento premium para videos musicales</p>
</header>

<div class="container">

  <div class="filters">
    <input type="text" id="searchName" placeholder="Buscar por nombre...">
    <input type="text" id="searchCity" placeholder="Buscar por ciudad...">
  </div>

  <div class="grid" id="modelGrid">

    <div class="card" data-name="Camila" data-city="Santiago">
      <img src="https://via.placeholder.com/300x400">
      <div class="card-content">
        <h3>Camila</h3>
        <p>Edad: 23</p>
        <p>Santiago</p>
        <div class="social">
          <a href="#">Instagram</a>
        </div>
      </div>
    </div>

    <div class="card" data-name="Valentina" data-city="Valparaiso">
      <img src="https://via.placeholder.com/300x400">
      <div class="card-content">
        <h3>Valentina</h3>
        <p>Edad: 25</p>
        <p>Valparaíso</p>
        <div class="social">
          <a href="#">Instagram</a>
        </div>
      </div>
    </div>

  </div>

  <div class="form-section">
    <h2>Únete como modelo</h2>
    <div class="form-group">
      <input type="text" id="name" placeholder="Nombre">
    </div>
    <div class="form-group">
      <input type="number" id="age" placeholder="Edad">
    </div>
    <div class="form-group">
      <input type="text" id="city" placeholder="Ciudad">
    </div>
    <div class="form-group">
      <input type="text" id="image" placeholder="URL de tu foto">
    </div>
    <div class="form-group">
      <input type="text" id="instagram" placeholder="Link de Instagram">
    </div>
    <button onclick="addModel()">Agregar perfil</button>
  </div>

</div>

<footer>
  © 2026 Agencia de Modelos
</footer>

<script>
function addModel() {
  const name = document.getElementById('name').value;
  const age = document.getElementById('age').value;
  const city = document.getElementById('city').value;
  const image = document.getElementById('image').value;
  const instagram = document.getElementById('instagram').value;

  const card = document.createElement('div');
  card.className = 'card';
  card.setAttribute('data-name', name.toLowerCase());
  card.setAttribute('data-city', city.toLowerCase());

  card.innerHTML = `
    <img src="${image}">
    <div class="card-content">
      <h3>${name}</h3>
      <p>Edad: ${age}</p>
      <p>${city}</p>
      <div class="social">
        <a href="${instagram}" target="_blank">Instagram</a>
      </div>
    </div>
  `;

  document.getElementById('modelGrid').appendChild(card);
}

const searchName = document.getElementById('searchName');
const searchCity = document.getElementById('searchCity');

searchName.addEventListener('input', filterModels);
searchCity.addEventListener('input', filterModels);

function filterModels() {
  const nameValue = searchName.value.toLowerCase();
  const cityValue = searchCity.value.toLowerCase();
  const cards = document.querySelectorAll('.card');

  cards.forEach(card => {
    const name = card.getAttribute('data-name');
    const city = card.getAttribute('data-city');

    if (name.includes(nameValue) && city.includes(cityValue)) {
      card.style.display = 'block';
    } else {
      card.style.display = 'none';
    }
  });
}
</script>

</body>
</html>

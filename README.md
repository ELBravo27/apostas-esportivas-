[index.html.txt](https://github.com/user-attachments/files/24424134/index.html.txt)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Análise Estatística de Futebol</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #0f172a;
      color: #e5e7eb;
      margin: 0;
      padding: 0;
    }
    header {
      background: #020617;
      padding: 20px;
      text-align: center;
    }
    header h1 {
      color: #38bdf8;
    }
    section {
      padding: 20px;
      max-width: 900px;
      margin: auto;
    }
    .card {
      background: #020617;
      padding: 20px;
      border-radius: 8px;
      margin-bottom: 20px;
    }
    button {
      background: #38bdf8;
      border: none;
      padding: 10px 15px;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
    }
    button:hover {
      background: #0ea5e9;
    }
    footer {
      text-align: center;
      padding: 15px;
      font-size: 12px;
      background: #020617;
      color: #94a3b8;
    }
    .alerta {
      background: #1e293b;
      padding: 10px;
      border-left: 4px solid #38bdf8;
      margin-bottom: 20px;
      font-size: 14px;
    }
  </style>
</head>
<body>

<header>
  <h1>📊 Análise Estatística de Futebol</h1>
  <p>Probabilidades e dados para fins educacionais</p>
</header>

<section>

  <div class="alerta">
    ⚠️ Este site é apenas para estudo e análise estatística.
    Não oferece apostas, dicas de apostas ou garantias de resultados.
  </div>

  <div class="card">
    <h2>Jogo em análise</h2>
    <p><strong>Time A</strong> x <strong>Time B</strong></p>
    <button onclick="analisar()">Analisar jogo</button>
  </div>

  <div class="card" id="resultado">
    <h2>Resultado da Análise</h2>
    <p>Clique em "Analisar jogo" para gerar os dados.</p>
  </div>

</section>

<footer>
  Projeto educacional • Estatística e Programação • Gratuito
</footer>

<script>
function analisar() {
  const golsTimeA = Math.random() * 2;
  const golsTimeB = Math.random() * 2;

  const probVitoriaA = Math.round((golsTimeA / (golsTimeA + golsTimeB)) * 100);
  const probVitoriaB = 100 - probVitoriaA;

  const probGolProx10 = Math.floor(Math.random() * 30) + 5;

  document.getElementById("resultado").innerHTML = `
    <h2>Resultado da Análise</h2>
    <p>📈 Probabilidade estimada de vitória:</p>
    <ul>
      <li>Time A: <strong>${probVitoriaA}%</strong></li>
      <li>Time B: <strong>${probVitoriaB}%</strong></li>
    </ul>
    <p>⚽ Chance de ocorrer um gol nos próximos 10 minutos:</p>
    <p><strong>${probGolProx10}%</strong></p>
    <p style="font-size:12px;color:#94a3b8;">
      Cálculos baseados em dados simulados para fins educacionais.
    </p>
  `;
}
</script>

</body>
</html>

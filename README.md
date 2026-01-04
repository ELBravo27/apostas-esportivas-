<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Análise Estatística de Futebol ao Vivo</title>

  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #0f172a;
      color: #e5e7eb;
    }

    header {
      background-color: #020617;
      padding: 20px;
      text-align: center;
    }

    header h1 {
      margin: 0;
      color: #38bdf8;
    }

    section {
      max-width: 900px;
      margin: auto;
      padding: 20px;
    }

    .alerta {
      background: #1e293b;
      border-left: 4px solid #38bdf8;
      padding: 10px;
      font-size: 14px;
      margin-bottom: 20px;
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
      font-weight: bold;
      cursor: pointer;
      margin-top: 10px;
    }

    button:hover {
      background: #0ea5e9;
    }

    footer {
      background: #020617;
      text-align: center;
      font-size: 12px;
      padding: 15px;
      color: #94a3b8;
    }
  </style>
</head>

<body>

<header>
  <h1>📊 Análise Estatística de Futebol</h1>
  <p>Simulação ao vivo • Projeto educacional</p>
</header>

<section>

  <div class="alerta">
    ⚠️ Este site realiza apenas análises estatísticas simuladas.
    Não oferece apostas, dicas de apostas ou garantias de resultados.
  </div>

  <div class="card">
    <h2>Jogo em andamento</h2>
    <p><strong>Time A</strong> x <strong>Time B</strong></p>
  </div>

  <div class="card" id="resultado">
    <h2>Carregando dados ao vivo...</h2>
    <p>A simulação começa automaticamente.</p>
  </div>

</section>

<footer>
  Projeto gratuito • Estatística • Programação • Educacional
</footer>

<script>
/* ============================
   SIMULAÇÃO DE JOGO AO VIVO
   ============================ */

let minuto = 0;
let ataquesA = 0;
let ataquesB = 0;
let intervalo = null;

/* Calcula probabilidade estimada de gol */
function calcularProbabilidadeGol() {
  const fatorTempo = minuto / 90;
  const fatorAtaques = (ataquesA + ataquesB) / 120;

  let prob = Math.round((fatorTempo + fatorAtaques) * 50);

  if (prob > 65) prob = 65;
  if (prob < 5) prob = 5;

  return prob;
}

/* Atualiza o painel */
function atualizarTela() {
  const probGol = calcularProbabilidadeGol();

  document.getElementById("resultado").innerHTML = `
    <h2>📡 Jogo ao vivo (simulação)</h2>
    <p>⏱️ Minuto: <strong>${minuto}</strong></p>
    <p>⚔️ Ataques Time A: <strong>${ataquesA}</strong></p>
    <p>⚔️ Ataques Time B: <strong>${ataquesB}</strong></p>

    <p>⚽ Probabilidade estimada de gol nos próximos minutos:</p>
    <h3>${probGol}%</h3>

    <p style="font-size:12px;color:#94a3b8;">
      Dados simulados • Análise estatística educacional
    </p>
  `;
}

/* Inicia automaticamente */
function iniciarSimulacao() {
  intervalo = setInterval(() => {
    if (minuto >= 90) {
      clearInterval(intervalo);
      return;
    }

    minuto++;
    ataquesA += Math.floor(Math.random() * 3);
    ataquesB += Math.floor(Math.random() * 3);

    atualizarTela();
  }, 5000);
}

iniciarSimulacao();
</script>

</body>
</html>

# Calculadora-MDR
Calculadora para infección por organismos MDR
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Calculadora OMR</title>
  <style>
    body {
      background-color: #121212;
      color: #f1f1f1;
      font-family: Arial, sans-serif;
      padding: 20px;
    }
    h1, h2 {
      color: #80cbc4;
    }
    .section {
      margin-bottom: 40px;
      padding: 20px;
      background-color: #1e1e1e;
      border-radius: 10px;
    }
    label {
      display: block;
      margin: 10px 0 5px;
    }
    input[type="checkbox"] {
      margin-right: 10px;
    }
    button {
      background-color: #26a69a;
      border: none;
      padding: 10px 20px;
      color: white;
      border-radius: 5px;
      cursor: pointer;
      margin-top: 10px;
    }
    button:hover {
      background-color: #2bbbad;
    }
    .result {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Calculadora de Escores OMR</h1>

  <!-- Secciones anteriores (INCREMENT, Giannella, PES, Shorr, DRIP, Tumbarello, GiannellaB, Pseudomonas) -->

  <!-- Acinetobacter Score (riesgo de infección por Acinetobacter baumannii multirresistente) -->
  <div class="section" id="acinetobacter">
    <h2>Score para Acinetobacter baumannii</h2>
    <form id="acinetobacterForm">
      <label><input type="checkbox" name="uci"> Internación en UCI (2 puntos)</label>
      <label><input type="checkbox" name="ventilacion"> Ventilación mecánica (2 puntos)</label>
      <label><input type="checkbox" name="ab_uso"> Uso previo de antibióticos de amplio espectro (2 puntos)</label>
      <label><input type="checkbox" name="procedimiento"> Procedimientos invasivos recientes (1 punto)</label>
      <label><input type="checkbox" name="larga_estancia"> Estancia hospitalaria prolongada (&gt;7 días) (1 punto)</label>
      <label><input type="checkbox" name="colonizacion"> Colonización previa por Acinetobacter (2 puntos)</label>
      <button type="button" onclick="calcularAcinetobacter()">Calcular Score Acinetobacter</button>
      <div class="result" id="acinetobacterResult"></div>
    </form>
  </div>

  <script>
    // Scripts anteriores (INCREMENT, Giannella, PES, Shorr, DRIP, Tumbarello, GiannellaB, Pseudomonas)

    function calcularAcinetobacter() {
      const form = document.getElementById("acinetobacterForm");
      let score = 0;
      if (form.uci.checked) score += 2;
      if (form.ventilacion.checked) score += 2;
      if (form.ab_uso.checked) score += 2;
      if (form.procedimiento.checked) score += 1;
      if (form.larga_estancia.checked) score += 1;
      if (form.colonizacion.checked) score += 2;
      let riesgo = score >= 6 ? "Riesgo alto de infección por Acinetobacter multirresistente." : "Riesgo bajo a moderado.";
      document.getElementById("acinetobacterResult").innerText = `Puntaje total: ${score} → ${riesgo}`;
    }
  </script>
</body>
</html>

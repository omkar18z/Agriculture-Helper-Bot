<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Agriculture Helper — HTML</title>
  <style>
    :root{--bg:#0f1724;--card:#0b1220;--accent:#10b981;--muted:#94a3b8;--glass:rgba(255,255,255,0.03)}
    body{font-family:Inter,ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,Helvetica,Arial;display:flex;align-items:center;justify-content:center;min-height:100vh;margin:0;background:linear-gradient(180deg,#071029 0%, #0b1530 100%);color:#e6eef8}
    .card{width:520px;background:var(--card);border-radius:12px;padding:20px;box-shadow:0 8px 30px rgba(2,6,23,0.6);}
    h1{font-size:20px;margin:0 0 8px;color:#f8fafc}
    p.lead{margin:0 0 16px;color:var(--muted);font-size:13px}
    label{display:block;font-size:13px;color:var(--muted);margin-top:10px}
    input[type=text],select{width:100%;padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:var(--glass);color:inherit;outline:none}
    button{margin-top:14px;width:100%;padding:10px;border-radius:10px;border:0;background:linear-gradient(90deg,var(--accent),#06b6d4);color:#042024;font-weight:600;cursor:pointer}
    pre{background:rgba(255,255,255,0.02);padding:12px;border-radius:8px;margin-top:12px;white-space:pre-wrap;color:#dff7ef}
    .row{display:grid;grid-template-columns:1fr 1fr;gap:10px}
    .small{font-size:12px;color:var(--muted);margin-top:6px}
    footer{margin-top:12px;font-size:12px;color:var(--muted);text-align:right}
  </style>
</head>
<body>
  <div class="card">
    <h1>Agriculture Helper</h1>
    <p class="lead">Enter soil type, crop and season — click Generate Advice to get simple, actionable tips.</p>

    <label for="soil">Soil Type</label>
    <input id="soil" type="text" placeholder="e.g. Loamy, Sandy, Clay" />

    <label for="crop">Crop</label>
    <input id="crop" type="text" placeholder="e.g. Rice, Wheat, Tomato" />

    <label for="season">Season</label>
    <input id="season" type="text" placeholder="e.g. Monsoon, Kharif, Summer" />

    <button id="go">Generate Advice</button>

    <pre id="output">— Advice will appear here —</pre>
    <div class="small">This single-file page reproduces the logic of your original Python Tkinter app.</div>
    <footer>Save this page as <code>agri_helper.html</code> and open in a browser.</footer>
  </div>

  <script>
    function normalize(s){ return (s||"").toString().trim().toLowerCase(); }

    function generateAdvice(soilType, crop, season){
      const s = normalize(soilType);
      const c = normalize(crop);
      const se = normalize(season);

      let watering;
      if (s === 'sandy' || s === 'sandy loam'){
        watering = 'Frequent light watering — sandy soils drain fast.';
      } else if (s === 'clay' || s === 'heavy clay'){
        watering = 'Less frequent, deep watering — clay holds water, avoid waterlogging.';
      } else if (s === 'loamy' || s === 'loam'){
        watering = 'Moderate watering — loam holds moisture well.';
      } else {
        watering = 'Adjust watering based on soil texture.';
      }

      let fertilizer;
      if (c === 'rice'){
        fertilizer = 'Use N-P-K; split nitrogen at tillering and panicle initiation.';
      } else if (c === 'wheat'){
        fertilizer = 'Apply P & K at base; split nitrogen at tillering.';
      } else if (c === 'maize' || c === 'corn'){
        fertilizer = 'High nitrogen needed — apply at planting & knee-high stage.';
      } else if (c === 'tomato' || c === 'potato'){
        fertilizer = 'Balanced NPK; extra potassium during fruit/tuber growth.';
      } else {
        fertilizer = 'Use balanced N-P-K based on soil test.';
      }

      let pests = 'Check pests regularly; follow crop rotation and field cleaning.';
      if (se === 'monsoon' || se === 'kharif') pests += ' Wet season increases fungal diseases.';
      if (se === 'summer') pests += ' Heat increases borers and sucking pests.';
      if (c === 'tomato' || c === 'potato') pests += ' Watch for blight & aphids.';

      let tips = 'Do a soil test; maintain organic matter.';
      if (s === 'clay') tips += ' Improve drainage, add compost.';
      if (s === 'sandy') tips += ' Add compost to retain moisture.';
      if (se === 'kharif' || se === 'monsoon') tips += ' Use disease-tolerant varieties.';

      return { Watering: watering, Fertilizer: fertilizer, Pests: pests, Tips: tips };
    }

    document.getElementById('go').addEventListener('click', ()=>{
      const soil = document.getElementById('soil').value;
      const crop = document.getElementById('crop').value;
      const season = document.getElementById('season').value;

      if (!soil || !crop || !season){
        alert('Please fill all fields!');
        return;
      }

      const advice = generateAdvice(soil, crop, season);
      const text = `- Watering: ${advice.Watering}\n- Fertilizer: ${advice.Fertilizer}\n- Pests: ${advice.Pests}\n- Tips: ${advice.Tips}`;
      document.getElementById('output').textContent = text;
    });
  </script>
</body>
</html>

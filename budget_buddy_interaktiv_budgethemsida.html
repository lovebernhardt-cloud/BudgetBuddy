<!doctype html>
<html lang="sv">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>BudgetBuddy — Din månadsbudget för det du gillar</title>
  <style>
    :root{--bg:#0f1724;--card:#0b1220;--accent:#6ee7b7;--muted:#94a3b8;--glass: rgba(255,255,255,0.03)}
    *{box-sizing:border-box;font-family:Inter,system-ui,Segoe UI,Roboto,Helvetica,Arial,sans-serif}
    body{margin:0;background:linear-gradient(180deg,#071020 0%, #071429 100%);color:#e6eef6;min-height:100vh;display:flex;align-items:center;justify-content:center;padding:24px}
    .app{width:100%;max-width:980px}
    header{display:flex;align-items:center;gap:16px;margin-bottom:18px}
    .logo{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#60a5fa);display:flex;align-items:center;justify-content:center;font-weight:700;color:#022;box-shadow:0 6px 18px rgba(6,9,22,0.6)}
    h1{margin:0;font-size:20px}
    p.lead{margin:0;color:var(--muted);font-size:13px}

    .grid{display:grid;grid-template-columns:1fr 360px;gap:18px}

    .card{background:var(--card);border-radius:14px;padding:16px;box-shadow:0 6px 30px rgba(2,6,23,0.6)}

    .controls label{display:block;font-size:13px;color:var(--muted);margin-bottom:6px}
    .controls input[type=number], .controls input[type=text], .controls select{width:100%;padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:inherit}
    .row{display:flex;gap:8px}
    .btn{display:inline-flex;align-items:center;gap:8px;padding:8px 12px;border-radius:10px;background:var(--glass);border:1px solid rgba(255,255,255,0.04);cursor:pointer}
    .btn.primary{background:linear-gradient(90deg,var(--accent),#60a5fa);color:#022;font-weight:600}
    .categories{margin-top:12px}
    .cat{display:flex;align-items:center;gap:10px;padding:10px;border-radius:10px;background:rgba(255,255,255,0.02);margin-bottom:8px}
    .cat input[type=number]{width:86px}
    .percent{min-width:64px;text-align:right;color:var(--muted);font-size:13px}

    .summary{display:flex;flex-direction:column;gap:10px}
    .summary .line{display:flex;justify-content:space-between;align-items:center}
    .meter{height:10px;background:rgba(255,255,255,0.04);border-radius:10px;overflow:hidden}
    .meter > i{display:block;height:100%;background:linear-gradient(90deg,var(--accent),#60a5fa);width:0%}
    .chart{display:flex;gap:8px;align-items:end;padding-top:12px}
    .bar{flex:1;height:80px;border-radius:6px;background:rgba(255,255,255,0.03);display:flex;align-items:end}
    .bar > span{display:block;width:100%;border-radius:6px 6px 0 0;height:0%;background:linear-gradient(180deg,#60a5fa,var(--accent));}
    .bar-label{font-size:12px;text-align:center;margin-top:6px;color:var(--muted)}

    footer{margin-top:12px;color:var(--muted);font-size:13px}

    @media (max-width:900px){.grid{grid-template-columns:1fr;}.logo{width:48px;height:48px}.card{padding:12px}}
  </style>
</head>
<body>
  <div class="app">
    <header>
      <div class="logo">BB</div>
      <div>
        <h1>BudgetBuddy — Månadens budget för det du gillar</h1>
        <p class="lead">Ange din inkomst och fördela pengar till nöje, fika, sparande och mer — enkelt och snabbt.</p>
      </div>
    </header>

    <div class="grid">
      <div class="card">
        <section class="controls">
          <label for="income">Månadlig inkomst (efter skatt, kr)</label>
          <input id="income" type="number" min="0" value="9000">

          <div style="display:flex;gap:8px;margin-top:10px;align-items:center">
            <div style="flex:1">
              <label>Preset</label>
              <select id="preset">
                <option value="balanced">Balanced — Spar 20%, Nöje 20%</option>
                <option value="saveFirst">Spara först — Spar 30%, Nöje 10%</option>
                <option value="liveNow">Live Now — Spar 5%, Nöje 30%</option>
              </select>
            </div>
            <button class="btn" id="applyPreset">Apply</button>
          </div>

          <div class="categories" id="categories">
            <!-- Categories rendered by JS -->
          </div>

          <div style="display:flex;gap:8px;margin-top:12px">
            <input id="newCatName" type="text" placeholder="Lägg till kategori (t.ex. Konsert)" />
            <button class="btn" id="addCat">Lägg till</button>
          </div>

          <div style="display:flex;gap:8px;margin-top:12px">
            <button class="btn primary" id="calculate">Beräkna budget</button>
            <button class="btn" id="saveBtn">Spara lokalt</button>
            <button class="btn" id="resetBtn">Återställ</button>
          </div>
        </section>
      </div>

      <aside class="card">
        <div class="summary">
          <div class="line"><strong>Total budget</strong><span id="totalDisplay">0 kr</span></div>
          <div class="line"><span>Summa fördelad</span><strong id="allocatedDisplay">0 kr</strong></div>
          <div class="line"><span>Kvar att fördela</span><strong id="leftoverDisplay">0 kr</strong></div>

          <div>
            <label style="font-size:13px;color:var(--muted)">Fördelning</label>
            <div class="meter"><i id="meterFill"></i></div>
          </div>

          <div id="tips" style="font-size:13px;color:var(--muted);padding-top:8px"></div>

          <div style="padding-top:6px">
            <label style="font-size:13px;color:var(--muted)">Grafisk överblick</label>
            <div class="chart" id="chart"></div>
          </div>

          <footer>
            <div>Funktioner: lägg till/ta bort kategorier, presets, spara i din webbläsare och få enkla tips för att nå dina mål.</div>
          </footer>
        </div>
      </aside>
    </div>
  </div>

  <script>
    // Grundkategorier
    const defaultCategories = [
      {id: id(), name: 'Mat & fika', pct: 15},
      {id: id(), name: 'Nöje', pct: 15},
      {id: id(), name: 'Transport', pct: 8},
      {id: id(), name: 'Shopping', pct: 10},
      {id: id(), name: 'Sparande', pct: 20},
      {id: id(), name: 'Övrigt', pct: 12}
    ];

    // DOM
    const incomeEl = document.getElementById('income');
    const categoriesEl = document.getElementById('categories');
    const calculateBtn = document.getElementById('calculate');
    const totalDisplay = document.getElementById('totalDisplay');
    const allocatedDisplay = document.getElementById('allocatedDisplay');
    const leftoverDisplay = document.getElementById('leftoverDisplay');
    const meterFill = document.getElementById('meterFill');
    const chart = document.getElementById('chart');
    const newCatName = document.getElementById('newCatName');
    const addCatBtn = document.getElementById('addCat');
    const saveBtn = document.getElementById('saveBtn');
    const resetBtn = document.getElementById('resetBtn');
    const applyPresetBtn = document.getElementById('applyPreset');
    const presetSelect = document.getElementById('preset');
    const tipsEl = document.getElementById('tips');

    let cats = load() || defaultCategories.map(c=>({...c}));

    function id(){return '_'+Math.random().toString(36).slice(2,9)}

    function renderCategories(){
      categoriesEl.innerHTML = '';
      cats.forEach(c=>{
        const row = document.createElement('div'); row.className='cat'; row.dataset.id=c.id;
        row.innerHTML = `
          <div style="flex:1">
            <input type="text" class="catName" value="${escapeHtml(c.name)}" />
          </div>
          <div style="width:110px;display:flex;gap:8px;align-items:center">
            <input type="number" class="catPct" min="0" max="100" value="${c.pct}" />
            <div class="percent">${c.pct}%</div>
            <button class="btn remove">Ta bort</button>
          </div>
        `;
        categoriesEl.appendChild(row);
      });
      attachListeners();
    }

    function attachListeners(){
      document.querySelectorAll('.cat .catPct').forEach(inp=>{
        inp.oninput = (e)=>{
          const el = e.target; const p = Number(el.value)||0; el.nextElementSibling.textContent = p + '%';
          const row = el.closest('.cat'); const cid = row.dataset.id;
          const cat = cats.find(x=>x.id===cid); if(cat) cat.pct = p; updateCalculated();
        }
      });
      document.querySelectorAll('.cat .catName').forEach(inp=>{
        inp.oninput = (e)=>{ const row = e.target.closest('.cat'); const cid = row.dataset.id; const cat = cats.find(x=>x.id===cid); if(cat) cat.name = e.target.value; renderChart(); }
      });
      document.querySelectorAll('.cat .remove').forEach(btn=>btn.onclick=(e)=>{ const row= e.target.closest('.cat'); const cid=row.dataset.id; cats=cats.filter(x=>x.id!==cid); renderCategories(); updateCalculated(); });
    }

    function updateCalculated(){
      const income = Number(incomeEl.value)||0;
      const sumPct = cats.reduce((s,c)=>s+Number(c.pct||0),0);
      const allocated = Math.round(income * (Math.min(sumPct,100)/100));
      const left = income - allocated;

      totalDisplay.textContent = format(income) + ' kr';
      allocatedDisplay.textContent = format(allocated) + ' kr';
      leftoverDisplay.textContent = format(left) + ' kr';

      meterFill.style.width = Math.min(100, sumPct) + '%';

      // Tips
      if(sumPct > 100) tipsEl.textContent = 'Du har fördelat över 100% — minska en eller flera kategorier.';
      else if(left > 0) tipsEl.textContent = 'Bra! Du har ' + format(left) + ' kr kvar att fördela eller spara.';
      else tipsEl.textContent = 'Du har utnyttjat hela din inkomst — tänk på att ha lite buffert.';

      renderChart();
    }

    function renderChart(){
      chart.innerHTML = '';
      const income = Number(incomeEl.value)||0;
      const maxVal = Math.max(...cats.map(c=>income*(c.pct/100)),1);
      cats.forEach(c=>{
        const val = income*(c.pct/100);
        const bar = document.createElement('div'); bar.className='bar';
        const span = document.createElement('span'); span.style.height = (maxVal? (val/maxVal*100):0) + '%';
        bar.appendChild(span);
        const wrap = document.createElement('div'); wrap.style.flex='1'; wrap.appendChild(bar);
        const label = document.createElement('div'); label.className='bar-label'; label.textContent = `${c.name} (${c.pct}%)\n${format(Math.round(val))} kr`;
        const container = document.createElement('div'); container.style.flex='1'; container.appendChild(bar); container.appendChild(label);
        chart.appendChild(container);
      });
    }

    // Add category
    addCatBtn.onclick = ()=>{
      const name = newCatName.value.trim(); if(!name) return alert('Ange ett namn för kategorin');
      cats.push({id:id(), name, pct:5}); newCatName.value=''; renderCategories(); updateCalculated();
    }

    incomeEl.oninput = ()=>updateCalculated();
    calculateBtn.onclick = ()=>updateCalculated();
    saveBtn.onclick = ()=>{ localStorage.setItem('budgetBuddy_v1', JSON.stringify({income:Number(incomeEl.value)||0, cats})); alert('Sparat lokalt i din webbläsare.'); }
    resetBtn.onclick = ()=>{ if(confirm('Återställa till standardinställningar?')){ cats = defaultCategories.map(c=>({...c, id:id()})); incomeEl.value = 9000; renderCategories(); updateCalculated(); localStorage.removeItem('budgetBuddy_v1'); }}

    function load(){ try{ const raw = localStorage.getItem('budgetBuddy_v1'); if(!raw) return null; const obj = JSON.parse(raw); if(obj.cats) return obj.cats; return null }catch(e){return null} }

    function format(n){ return n.toLocaleString('sv-SE'); }

    function escapeHtml(s){ return s.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;'); }

    // Presets
    applyPresetBtn.onclick = ()=>{
      const p = presetSelect.value;
      if(p==='balanced'){ cats = [
        {id:id(), name:'Sparande', pct:20},
        {id:id(), name:'Nöje', pct:20},
        {id:id(), name:'Mat & fika', pct:15},
        {id:id(), name:'Transport', pct:8},
        {id:id(), name:'Shopping', pct:12},
        {id:id(), name:'Övrigt', pct:10}
      ]; }
      else if(p==='saveFirst'){ cats = [
        {id:id(), name:'Sparande', pct:30},
        {id:id(), name:'Nöje', pct:10},
        {id:id(), name:'Mat & fika', pct:15},
        {id:id(), name:'Transport', pct:5},
        {id:id(), name:'Shopping', pct:10},
        {id:id(), name:'Övrigt', pct:10}
      ]; }
      else if(p==='liveNow'){ cats = [
        {id:id(), name:'Sparande', pct:5},
        {id:id(), name:'Nöje', pct:30},
        {id:id(), name:'Mat & fika', pct:18},
        {id:id(), name:'Transport', pct:7},
        {id:id(), name:'Shopping', pct:15},
        {id:id(), name:'Övrigt', pct:10}
      ]; }
      renderCategories(); updateCalculated();
    }

    // Init
    renderCategories(); updateCalculated();

    // Save state when leaving
    window.addEventListener('beforeunload', ()=>{ try{ localStorage.setItem('budgetBuddy_v1', JSON.stringify({income: Number(incomeEl.value)||0, cats})); }catch(e){} });
  </script>
</body>
</html>

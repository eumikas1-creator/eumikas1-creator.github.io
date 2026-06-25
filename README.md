# eumikas1-creator.github.io
<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Macro II — Plano de Estudo</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@3.19.0/dist/tabler-icons.min.css">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #ffffff;
    --bg-secondary: #f7f7f5;
    --bg-tertiary: #f0efe9;
    --text: #1a1a1a;
    --text-secondary: #6b6b6b;
    --text-tertiary: #a0a0a0;
    --border: rgba(0,0,0,0.1);
    --border-strong: rgba(0,0,0,0.2);
    --green: #1D9E75;
    --green-bg: #E1F5EE;
    --radius-md: 8px;
    --radius-lg: 12px;
    --radius-xl: 16px;
  }

  @media (prefers-color-scheme: dark) {
    :root {
      --bg: #1c1c1c;
      --bg-secondary: #252525;
      --bg-tertiary: #2e2e2e;
      --text: #f0f0f0;
      --text-secondary: #a0a0a0;
      --text-tertiary: #606060;
      --border: rgba(255,255,255,0.1);
      --border-strong: rgba(255,255,255,0.2);
      --green: #2dbd8f;
      --green-bg: #0d3326;
    }
  }

  body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif;
    font-size: 14px;
    background: var(--bg-tertiary);
    color: var(--text);
    line-height: 1.5;
    min-height: 100vh;
  }

  .page {
    max-width: 720px;
    margin: 0 auto;
    padding: 2rem 1.25rem 4rem;
  }

  header {
    margin-bottom: 1.75rem;
  }

  header h1 {
    font-size: 20px;
    font-weight: 600;
    letter-spacing: -0.3px;
  }

  header p {
    font-size: 13px;
    color: var(--text-secondary);
    margin-top: 3px;
  }

  .stats-row {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
    margin-bottom: 1.25rem;
  }

  .stat {
    background: var(--bg);
    border: 0.5px solid var(--border);
    border-radius: var(--radius-lg);
    padding: 12px;
    text-align: center;
  }

  .stat-num {
    font-size: 22px;
    font-weight: 600;
    letter-spacing: -0.5px;
  }

  .stat-label {
    font-size: 11px;
    color: var(--text-secondary);
    margin-top: 2px;
  }

  .prog-wrap {
    background: var(--border);
    border-radius: 100px;
    height: 5px;
    margin-bottom: 1.25rem;
    overflow: hidden;
  }

  .prog-fill {
    height: 5px;
    border-radius: 100px;
    background: var(--green);
    transition: width 0.35s ease;
  }

  .filters {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
    margin-bottom: 1.25rem;
  }

  .filter-btn {
    font-size: 12px;
    font-family: inherit;
    padding: 5px 13px;
    border-radius: 100px;
    border: 0.5px solid var(--border-strong);
    background: transparent;
    color: var(--text-secondary);
    cursor: pointer;
    transition: all 0.15s;
  }

  .filter-btn:hover { background: var(--bg-secondary); }

  .filter-btn.active {
    background: var(--text);
    color: var(--bg);
    border-color: var(--text);
  }

  .block {
    background: var(--bg);
    border: 0.5px solid var(--border);
    border-radius: var(--radius-lg);
    margin-bottom: 10px;
    overflow: hidden;
  }

  .block-header {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 13px 15px;
    cursor: pointer;
    user-select: none;
    transition: background 0.12s;
  }

  .block-header:hover { background: var(--bg-secondary); }

  .bnum {
    width: 28px;
    height: 28px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 12px;
    font-weight: 600;
    flex-shrink: 0;
  }

  .btitles { flex: 1; min-width: 0; }
  .btitles h3 { font-size: 14px; font-weight: 500; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
  .btitles p { font-size: 11px; color: var(--text-secondary); margin-top: 1px; }

  .bprog { font-size: 11px; color: var(--text-secondary); white-space: nowrap; }

  .bchev {
    font-size: 16px;
    color: var(--text-tertiary);
    transition: transform 0.2s;
    flex-shrink: 0;
  }

  .block-body { border-top: 0.5px solid var(--border); }

  .task-row {
    padding: 11px 15px;
    border-bottom: 0.5px solid var(--border);
    transition: background 0.1s;
  }

  .task-row:last-child { border-bottom: none; }
  .task-row:hover { background: var(--bg-secondary); }
  .task-row.done .task-name { color: var(--text-tertiary); text-decoration: line-through; }

  .task-top { display: flex; align-items: flex-start; gap: 10px; }

  .chk {
    width: 18px;
    height: 18px;
    border-radius: 4px;
    border: 1.5px solid var(--border-strong);
    flex-shrink: 0;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 1px;
    transition: background 0.15s, border-color 0.15s;
    background: transparent;
  }

  .chk:hover { border-color: var(--green); }
  .chk.checked { background: var(--green); border-color: var(--green); }
  .chk i { font-size: 11px; color: #fff; }

  .task-name { font-size: 13px; line-height: 1.45; flex: 1; min-width: 0; }

  .task-meta { display: flex; align-items: center; gap: 7px; margin-top: 5px; flex-wrap: wrap; }

  .tag {
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 100px;
    font-weight: 500;
    letter-spacing: 0.2px;
  }

  .tag-ppt { background: #E6F1FB; color: #0C447C; }
  .tag-wb  { background: #EAF3DE; color: #27500A; }
  .tag-ex  { background: #FAEEDA; color: #633806; }
  .tag-rev { background: #EEEDFE; color: #3C3489; }

  @media (prefers-color-scheme: dark) {
    .tag-ppt { background: #0c2d4f; color: #85B7EB; }
    .tag-wb  { background: #152805; color: #97C459; }
    .tag-ex  { background: #3a2200; color: #EF9F27; }
    .tag-rev { background: #1e1a40; color: #AFA9EC; }
  }

  .task-time { font-size: 11px; color: var(--text-tertiary); }

  .note-area { margin-top: 8px; margin-left: 28px; }

  .note-item {
    display: flex;
    align-items: flex-start;
    gap: 6px;
    background: var(--bg-secondary);
    border-radius: var(--radius-md);
    padding: 7px 10px;
    margin-bottom: 5px;
    font-size: 12px;
    color: var(--text-secondary);
    line-height: 1.5;
  }

  .note-text { flex: 1; white-space: pre-wrap; word-break: break-word; }

  .del-note {
    background: none;
    border: none;
    cursor: pointer;
    color: var(--text-tertiary);
    padding: 0;
    font-size: 13px;
    flex-shrink: 0;
    margin-top: 1px;
    font-family: inherit;
    display: flex;
    align-items: center;
    transition: color 0.12s;
  }

  .del-note:hover { color: #c0392b; }

  .note-input-row {
    display: flex;
    gap: 6px;
    margin-top: 4px;
  }

  .note-input-row input {
    flex: 1;
    font-size: 12px;
    font-family: inherit;
    padding: 6px 10px;
    border-radius: var(--radius-md);
    border: 0.5px solid var(--border-strong);
    background: var(--bg);
    color: var(--text);
    outline: none;
  }

  .note-input-row input:focus { border-color: var(--green); }

  .note-input-row button {
    font-size: 12px;
    font-family: inherit;
    padding: 6px 12px;
    border-radius: var(--radius-md);
    border: 0.5px solid var(--border-strong);
    background: transparent;
    color: var(--text-secondary);
    cursor: pointer;
    white-space: nowrap;
    transition: background 0.12s;
  }

  .note-input-row button:hover { background: var(--bg-secondary); }
  .note-input-row button.save { border-color: var(--green); color: var(--green); }
  .note-input-row button.save:hover { background: var(--green-bg); }

  .add-note-btn {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    font-size: 11px;
    font-family: inherit;
    color: var(--text-tertiary);
    background: none;
    border: none;
    cursor: pointer;
    margin-left: 28px;
    margin-top: 6px;
    padding: 0;
    transition: color 0.12s;
  }

  .add-note-btn:hover { color: var(--text-secondary); }
  .add-note-btn i { font-size: 12px; }

  .empty-msg {
    text-align: center;
    padding: 2rem 0;
    color: var(--text-tertiary);
    font-size: 13px;
  }

  @media (max-width: 480px) {
    .stats-row { grid-template-columns: repeat(2, 1fr); }
    .btitles h3 { font-size: 13px; }
  }
</style>
</head>
<body>
<div class="page">

  <header>
    <h1>Macroeconomia II — Plano de Estudo</h1>
    <p id="subtitle">7 dias · acompanha o teu progresso</p>
  </header>

  <div class="stats-row">
    <div class="stat"><div class="stat-num" id="s-done">0</div><div class="stat-label">concluídas</div></div>
    <div class="stat"><div class="stat-num" id="s-total">0</div><div class="stat-label">tarefas totais</div></div>
    <div class="stat"><div class="stat-num" id="s-pct">0%</div><div class="stat-label">progresso</div></div>
    <div class="stat"><div class="stat-num" id="s-notes">0</div><div class="stat-label">notas</div></div>
  </div>

  <div class="prog-wrap"><div class="prog-fill" id="prog-fill" style="width:0%"></div></div>

  <div class="filters">
    <button class="filter-btn active" onclick="setFilter('all',this)">Tudo</button>
    <button class="filter-btn" onclick="setFilter('pending',this)">Por fazer</button>
    <button class="filter-btn" onclick="setFilter('done',this)">Feitas</button>
    <button class="filter-btn" onclick="setFilter('notes',this)">Com notas</button>
  </div>

  <div id="blocks-container"></div>

</div>

<script>
const BLOCKS = [
  {id:'b1',color:'#E6F1FB',tcolor:'#0C447C',label:'1',title:'Modelo de Solow (SGM 1, 2 e 3)',sub:'Lectures 1–2 · WB 1',tasks:[
    {id:'t1',name:'PPT Lecture 1 — SGM 1: capital, estado estacionário, regra de ouro',tag:'ppt',time:'2h'},
    {id:'t2',name:'PPT Lecture 2 — SGM 3: capital humano, progresso tecnológico, Solow residual',tag:'ppt',time:'2h'},
    {id:'t3',name:'WB 1 completo — SGM 1, 2 e 3: álgebra, diagramas k* e golden rule',tag:'wb',time:'4h'},
    {id:'t4',name:'Revisão: fórmulas-chave, receitas de gráficos, pontos de erro frequentes',tag:'rev',time:'2h'},
  ]},
  {id:'b2',color:'#EAF3DE',tcolor:'#27500A',label:'2',title:'Desafios do Crescimento',sub:'Lecture 3 · WB 2',tasks:[
    {id:'t5',name:'PPT Lecture 3 — WS-PS, produtividade, ciclos, Cerra & Saxena',tag:'ppt',time:'2h'},
    {id:'t6',name:'WB 2 completo — Schumpeter, WS-PS com choques, crescimento com K humano',tag:'wb',time:'3h'},
    {id:'t7',name:'Revisão: diagramas WS-PS e intuição Schumpeteriana',tag:'rev',time:'1h'},
  ]},
  {id:'b3',color:'#FAEEDA',tcolor:'#633806',label:'3',title:'Inflação e Política Monetária',sub:'Lecture 4 · WB 3',tasks:[
    {id:'t8',name:'PPT Lecture 4 — Equação quantitativa, senhoriagem, Fisher, hiperinflação',tag:'ppt',time:'2.5h'},
    {id:'t9',name:'WB 3 completo — Laffer da senhoriagem, g_m*, Fisher, hiperinflação',tag:'wb',time:'3.5h'},
    {id:'t10',name:'Revisão: Laffer, intuição sobre hiperinflação, ligar ao caso russo (Stiglitz)',tag:'rev',time:'2h'},
  ]},
  {id:'b4',color:'#EEEDFE',tcolor:'#3C3489',label:'4',title:'Microfundamentos: Consumo',sub:'Lectures 5–6 · WB 4 parte 1',tasks:[
    {id:'t11',name:'PPT Lecture 5 — Keynes, Fisher intertemporal, ciclo de vida',tag:'ppt',time:'2h'},
    {id:'t12',name:'PPT Lecture 6 — Rendimento permanente, expectativas, restrições de liquidez',tag:'ppt',time:'2h'},
    {id:'t13',name:'WB 4 (consumo) — Fisher, ciclo de vida, rendimento permanente: curvas de indiferença',tag:'wb',time:'3h'},
    {id:'t14',name:'Revisão: distinções Keynes / Fisher / Modigliani / Friedman',tag:'rev',time:'1h'},
  ]},
  {id:'b5',color:'#FBEAF0',tcolor:'#72243E',label:'5',title:'Microfundamentos: Investimento',sub:'Lecture 7 · WB 4 parte 2',tasks:[
    {id:'t15',name:"PPT Lecture 7 — Investimento neoclássico, Tobin's q, VAL, acelerador",tag:'ppt',time:'2.5h'},
    {id:'t16',name:"WB 4 (investimento) — neoclássico, Tobin's q, VAL, acelerador",tag:'wb',time:'3h'},
    {id:'t17',name:'Revisão: ligar consumo + investimento (expectativas inter-temporais)',tag:'rev',time:'1.5h'},
  ]},
  {id:'b6',color:'#E1F5EE',tcolor:'#085041',label:'6',title:'Política Fiscal e Monetária',sub:'Lectures 8–9 · WB 5 parte 1',tasks:[
    {id:'t18',name:'PPT Lecture 8 — Dinâmica da dívida, equivalência ricardiana, Barro 1974',tag:'ppt',time:'2h'},
    {id:'t19',name:'PPT Lecture 9 — IS-MP, regra de Taylor, armadilha de liquidez, Friedman 1968',tag:'ppt',time:'2.5h'},
    {id:'t20',name:'WB 5 (fiscal e monetária) — dívida, IS-MP, Taylor rule, liquidity trap',tag:'wb',time:'3h'},
    {id:'t21',name:'Revisão: política fiscal vs monetária, curto vs longo prazo',tag:'rev',time:'1.5h'},
  ]},
  {id:'b7',color:'#E6F1FB',tcolor:'#0C447C',label:'7',title:'Zona Euro e OCA',sub:'Lectures 9–10 · WB 5 parte 2',tasks:[
    {id:'t22',name:'PPT Lecture 10 — Zona Euro, OCA de Mundell, crise 2008 e crise soberana',tag:'ppt',time:'2.5h'},
    {id:'t23',name:'WB 5 (Zona Euro) — OCA, choques assimétricos, mobilidade do trabalho',tag:'wb',time:'2.5h'},
    {id:'t24',name:'Revisão: OCA e crise da dívida europeia (Baldwin & Giavazzi)',tag:'rev',time:'2h'},
  ]},
  {id:'b8',color:'#FAEEDA',tcolor:'#633806',label:'8',title:'Testes anteriores',sub:'1.º e 2.º teste 2025 e 2026',tasks:[
    {id:'t25',name:'1.º Teste 2025 — resolver sob condições reais, corrigir com guidelines',tag:'ex',time:'1.5h'},
    {id:'t26',name:'1.º Teste 2026 — comparar com 2025: temas que repetem',tag:'ex',time:'1.5h'},
    {id:'t27',name:'2.º Teste 2025 — foco em microfundamentos, fiscal e monetária',tag:'ex',time:'1.5h'},
    {id:'t28',name:'2.º Teste 2026 — identificar pontos fracos antes do exame final',tag:'ex',time:'1.5h'},
    {id:'t29',name:'Análise de erros dos 4 testes — catalogar por tema',tag:'rev',time:'2h'},
  ]},
  {id:'b9',color:'#FAECE7',tcolor:'#993C1D',label:'9',title:'Exames completos',sub:'Final e Recurso 2026',tasks:[
    {id:'t30',name:'Exame Final 2026 — resolver em tempo real (90–120 min)',tag:'ex',time:'2h'},
    {id:'t31',name:'Exame de Recurso 2026 — resolver em tempo real',tag:'ex',time:'2h'},
    {id:'t32',name:'Revisão final de erros e formulário com todas as fórmulas e gráficos-tipo',tag:'rev',time:'2h'},
  ]},
  {id:'b10',color:'#F1EFE8',tcolor:'#444441',label:'10',title:'Revisão geral e simulação final',sub:'Consolidação de toda a matéria',tasks:[
    {id:'t33',name:'Revisão expressa de todos os blocos — todos os gráficos de memória',tag:'rev',time:'2h'},
    {id:'t34',name:'Lista de verificação final: fórmulas, diagramas, autores (Solow, Mundell, Barro, Friedman, Fisher, Tobin)',tag:'rev',time:'1h'},
  ]},
];

const TAG_LABELS = {ppt:'PPT',wb:'WB',ex:'EX',rev:'REV'};
let state = {};
let openBlocks = {};
let showNoteFor = {};
let currentFilter = 'all';

function loadState() {
  try { const s = localStorage.getItem('macro_tracker_v3'); if (s) state = JSON.parse(s); } catch(e) {}
}

function saveState() {
  try { localStorage.setItem('macro_tracker_v3', JSON.stringify(state)); } catch(e) {}
}

function getTask(id) {
  if (!state[id]) state[id] = {done: false, notes: []};
  return state[id];
}

function setFilter(f, btn) {
  currentFilter = f;
  document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  render();
}

function toggleBlock(bid) {
  openBlocks[bid] = !openBlocks[bid];
  render();
}

function toggleTask(tid) {
  const t = getTask(tid);
  t.done = !t.done;
  saveState();
  render();
}

function toggleNoteInput(tid) {
  showNoteFor[tid] = !showNoteFor[tid];
  render();
  if (showNoteFor[tid]) {
    setTimeout(() => { const el = document.getElementById('ni_' + tid); if (el) el.focus(); }, 30);
  }
}

function addNote(tid) {
  const el = document.getElementById('ni_' + tid);
  if (!el || !el.value.trim()) return;
  getTask(tid).notes.push(el.value.trim());
  showNoteFor[tid] = false;
  saveState();
  render();
}

function deleteNote(tid, idx) {
  getTask(tid).notes.splice(idx, 1);
  saveState();
  render();
}

function handleNoteKey(e, tid) {
  if (e.key === 'Enter') addNote(tid);
  if (e.key === 'Escape') { showNoteFor[tid] = false; render(); }
}

function esc(s) {
  return s.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
}

function taskVisible(tid) {
  const s = getTask(tid);
  if (currentFilter === 'all') return true;
  if (currentFilter === 'pending') return !s.done;
  if (currentFilter === 'done') return s.done;
  if (currentFilter === 'notes') return s.notes.length > 0;
  return true;
}

function updateStats() {
  let total = 0, done = 0, notes = 0;
  BLOCKS.forEach(b => b.tasks.forEach(t => {
    total++;
    const s = getTask(t.id);
    if (s.done) done++;
    notes += s.notes.length;
  }));
  document.getElementById('s-done').textContent = done;
  document.getElementById('s-total').textContent = total;
  document.getElementById('s-pct').textContent = Math.round(done / total * 100) + '%';
  document.getElementById('s-notes').textContent = notes;
  document.getElementById('prog-fill').style.width = Math.round(done / total * 100) + '%';
}

function render() {
  updateStats();
  let html = '';

  BLOCKS.forEach(b => {
    const visible = b.tasks.filter(t => taskVisible(t.id));
    if (currentFilter !== 'all' && visible.length === 0) return;

    const done = b.tasks.filter(t => getTask(t.id).done).length;
    const total = b.tasks.length;
    const isOpen = openBlocks[b.id] !== false;
    const allDone = done === total;

    html += `<div class="block">
      <div class="block-header" onclick="toggleBlock('${b.id}')">
        <div class="bnum" style="background:${b.color};color:${b.tcolor}">
          ${allDone ? '<i class="ti ti-check"></i>' : b.label}
        </div>
        <div class="btitles">
          <h3>${esc(b.title)}</h3>
          <p>${esc(b.sub)}</p>
        </div>
        <span class="bprog">${done}/${total}</span>
        <i class="ti ti-chevron-down bchev" style="transform:${isOpen ? 'rotate(180deg)' : 'none'}"></i>
      </div>`;

    if (isOpen) {
      html += `<div class="block-body">`;
      const toShow = currentFilter === 'all' ? b.tasks : visible;

      if (toShow.length === 0) {
        html += `<div class="empty-msg">Nenhuma tarefa nesta vista</div>`;
      } else {
        toShow.forEach(t => {
          const s = getTask(t.id);
          const showInput = showNoteFor[t.id];

          html += `<div class="task-row${s.done ? ' done' : ''}">
            <div class="task-top">
              <div class="chk${s.done ? ' checked' : ''}" onclick="toggleTask('${t.id}')" role="checkbox" aria-checked="${s.done}" tabindex="0" onkeydown="if(event.key===' '||event.key==='Enter')toggleTask('${t.id}')">
                ${s.done ? '<i class="ti ti-check"></i>' : ''}
              </div>
              <div style="flex:1;min-width:0">
                <div class="task-name">${esc(t.name)}</div>
                <div class="task-meta">
                  <span class="tag tag-${t.tag}">${TAG_LABELS[t.tag]}</span>
                  <span class="task-time">${t.time}</span>
                </div>
              </div>
            </div>`;

          if (s.notes.length > 0) {
            html += `<div class="note-area">`;
            s.notes.forEach((n, i) => {
              html += `<div class="note-item">
                <i class="ti ti-pencil" style="font-size:12px;margin-top:2px;flex-shrink:0;color:var(--text-tertiary)"></i>
                <span class="note-text">${esc(n)}</span>
                <button class="del-note" onclick="deleteNote('${t.id}',${i})" title="Apagar nota">
                  <i class="ti ti-x" style="font-size:12px"></i>
                </button>
              </div>`;
            });
            html += `</div>`;
          }

          if (showInput) {
            html += `<div class="note-area">
              <div class="note-input-row">
                <input id="ni_${t.id}" type="text" placeholder="Ex: rever derivação do g_m*, ver slide 12 outra vez…" onkeydown="handleNoteKey(event,'${t.id}')">
                <button class="save" onclick="addNote('${t.id}')">Guardar</button>
                <button onclick="toggleNoteInput('${t.id}')">Cancelar</button>
              </div>
            </div>`;
          } else {
            html += `<button class="add-note-btn" onclick="toggleNoteInput('${t.id}')">
              <i class="ti ti-plus"></i> nota
            </button>`;
          }

          html += `</div>`;
        });
      }
      html += `</div>`;
    }

    html += `</div>`;
  });

  document.getElementById('blocks-container').innerHTML = html;
}

loadState();
BLOCKS.forEach(b => { openBlocks[b.id] = true; });
render();
</script>
</body>
</html>

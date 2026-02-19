<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Mini Pokémon-Style Adventure</title>
<style>
  :root{
    --bg:#0b1220; --panel:#0f1724; --accent:#7dd3fc; --muted:#94a3b8;
    --tile-grass: #1b7a3f; --tile-path: #6b4f2b; --tile-water: #0e4a7a;
    font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  }
  html,body{height:100%; margin:0; background:linear-gradient(180deg,#071024 0%, #0b1220 100%); color:#e6eef6}
  .app{
    max-width:980px; margin:18px auto; padding:18px; display:grid; gap:14px;
    grid-template-columns: 1fr 320px;
  }

  header{
    grid-column:1/-1; display:flex; gap:12px; align-items:center;
  }
  h1{font-size:20px; margin:0; letter-spacing:0.4px}
  .sub{color:var(--muted); font-size:13px}

  /* Game area */
  .game-wrap{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(0,0,0,0.1)); padding:12px; border-radius:12px; box-shadow: 0 6px 24px rgba(2,6,23,0.6);}
  #map{display:grid; grid-template-columns: repeat(12, 48px); grid-auto-rows:48px; gap:2px; width: max-content; margin:8px auto; background:rgba(0,0,0,0.12); padding:6px; border-radius:8px}
  .tile{width:48px; height:48px; display:flex; align-items:center; justify-content:center; font-size:20px; border-radius:6px; user-select:none}
  .tile.path{background:var(--tile-path)}
  .tile.grass{background:linear-gradient(180deg,#2aa55a,#137245); box-shadow: inset 0 -6px 10px rgba(0,0,0,0.18)}
  .tile.water{background:linear-gradient(180deg,#0b6fb0,#064a78)}
  .tile.tree{background:linear-gradient(180deg,#0b3f1f,#063019); box-shadow: inset 0 -6px 12px rgba(0,0,0,0.15)}
  .player{font-size:26px; transform: translateY(-4px)}

  /* Right column panels */
  .panel{background:var(--panel); padding:12px; border-radius:12px; box-shadow: 0 4px 16px rgba(2,6,23,0.6); color:#dff4ff}
  .status-row{display:flex; justify-content:space-between; gap:8px; font-size:14px}
  .stat{background: rgba(255,255,255,0.02); padding:8px; border-radius:8px; width:100%; text-align:center}
  .controls{display:flex; gap:8px; margin-top:12px; align-items:center; flex-wrap:wrap}
  button.btn{background:linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01)); border:1px solid rgba(255,255,255,0.06); color:var(--accent); padding:8px 10px; border-radius:10px; cursor:pointer; font-weight:600}
  button.btn:active{transform:translateY(1px)}
  .log{height:170px; overflow:auto; background:rgba(0,0,0,0.15); padding:8px; border-radius:8px; font-size:13px; color:#e7f8ff}

  /* Battle modal */
  .modal{position:fixed; inset:0; display:flex; align-items:center; justify-content:center; background:linear-gradient(rgba(0,0,0,0.45), rgba(0,0,0,0.6)); visibility:hidden; opacity:0; transition:all .18s}
  .modal.open{visibility:visible; opacity:1}
  .battle{width:720px; max-width:92%; background:linear-gradient(180deg,#0b1530,#071026); padding:18px; border-radius:10px; box-shadow:0 12px 40px rgba(0,0,0,0.6); display:grid; grid-template-columns:1fr 1fr; gap:12px; color:#eaffff}
  .poke-card{background:rgba(255,255,255,0.02); border-radius:10px; padding:10px}
  .poke-sprite{font-size:48px; text-align:center}
  .hpbar{height:10px; background:rgba(255,255,255,0.07); border-radius:8px; overflow:hidden}
  .hpfill{height:100%; background:linear-gradient(90deg,#86efac,#16a34a); width:100%}
  .battle-controls{display:flex; flex-direction:column; gap:8px}
  .btn-action{padding:10px; border-radius:8px; cursor:pointer; border:1px solid rgba(255,255,255,0.06); background:rgba(255,255,255,0.01); color:var(--accent); font-weight:700}

  /* small mobile controls */
  .mobile-controls{display:none; gap:8px; margin-top:8px}
  .dpad{display:grid; grid-template-columns:repeat(3,44px); gap:6px; width:max-content}
  .dpad button{height:44px; border-radius:8px; border:none; background:rgba(255,255,255,0.02); color:var(--accent); font-weight:700}

  @media (max-width:920px){
    .app{grid-template-columns:1fr}
    .mobile-controls{display:flex}
    #map{transform: scale(0.9)}
  }
</style>
</head>
<body>
  <div class="app">
    <header>
      <div>
        <h1>Mini Pokémon-Style Adventure</h1>
        <div class="sub">Move on grass to encounter wild creatures. Arrow keys / WASD or on-screen D-pad.</div>
      </div>
      <div style="margin-left:auto; text-align:right">
        <div class="sub">Save file to play offline</div>
        <div style="font-size:12px; color:var(--muted)">Author: Miracle Okorie's Mini Game — lightweight demo</div>
      </div>
    </header>

    <section class="game-wrap">
      <div id="map" aria-label="game map"></div>

      <div class="panel">
        <div class="status-row">
          <div class="stat">
            <div style="font-size:13px; color:var(--muted)">Trainer</div>
            <div style="font-size:16px;">You</div>
          </div>
          <div class="stat">
            <div style="font-size:13px; color:var(--muted)">Pokéballs</div>
            <div id="balls" style="font-size:16px;">5</div>
          </div>
          <div class="stat">
            <div style="font-size:13px; color:var(--muted)">Steps</div>
            <div id="steps" style="font-size:16px;">0</div>
          </div>
        </div>

        <div style="margin-top:12px;">
          <div style="font-size:13px; color:var(--muted)">Current Pokémon</div>
          <div style="display:flex; gap:8px; align-items:center; margin-top:8px;">
            <div style="font-size:32px" id="playerSprite">🐾</div>
            <div style="flex:1">
              <div id="playerName" style="font-weight:700">Flit</div>
              <div style="margin-top:6px">
                <div class="hpbar"><div class="hpfill" id="playerHp" style="width:100%"></div></div>
                <div style="font-size:12px; color:var(--muted); margin-top:6px" id="playerHpText">HP: 30/30</div>
              </div>
            </div>
          </div>
        </div>

        <div class="controls">
          <button class="btn" id="healBtn">Use Potion (+15 HP)</button>
          <button class="btn" id="saveBtn">Save Progress</button>
          <button class="btn" id="resetBtn">Reset</button>
        </div>

        <div style="margin-top:12px; font-size:13px; color:var(--muted)">Game Log</div>
        <div class="log" id="log"></div>

        <div class="mobile-controls">
          <div style="flex:1">
            <div style="font-size:13px; color:var(--muted); margin-bottom:6px">Move</div>
            <div class="dpad">
              <div></div><button data-dir="up">↑</button><div></div>
              <button data-dir="left">←</button><button data-dir="down">↓</button><button data-dir="right">→</button>
              <div></div><button data-dir="space">•</button><div></div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>

  <!-- Battle modal -->
  <div id="modal" class="modal" role="dialog" aria-hidden="true">
    <div class="battle" role="document">
      <div class="poke-card">
        <div style="display:flex; justify-content:space-between; align-items:center;">
          <div>
            <div style="font-size:13px; color:var(--muted)">Wild</div>
            <div id="wildName" style="font-weight:800; font-size:18px">--</div>
          </div>
          <div style="text-align:right">
            <div style="font-size:13px; color:var(--muted)">Level</div>
            <div id="wildLevel" style="font-weight:700">1</div>
          </div>
        </div>

        <div class="poke-sprite" id="wildSprite">🦋</div>
        <div style="margin-top:8px">
          <div class="hpbar"><div id="wildHp" class="hpfill" style="width:100%"></div></div>
          <div style="font-size:12px; color:var(--muted); margin-top:6px" id="wildHpText">HP: --/--</div>
        </div>
      </div>

      <div class="poke-card battle-controls">
        <div style="display:flex; justify-content:space-between; align-items:center;">
          <div>
            <div style="font-size:13px; color:var(--muted)">Your</div>
            <div id="battlePlayerName" style="font-weight:800; font-size:18px">Flit</div>
          </div>
          <div style="text-align:right">
            <div style="font-size:13px; color:var(--muted)">Level</div>
            <div id="battlePlayerLevel" style="font-weight:700">1</div>
          </div>
        </div>

        <div style="display:flex; gap:10px; align-items:center; margin-top:8px">
          <div style="font-size:36px" id="battlePlayerSprite">🐾</div>
          <div style="flex:1">
            <div class="hpbar"><div id="battlePlayerHp" class="hpfill" style="width:100%"></div></div>
            <div style="font-size:12px; color:var(--muted); margin-top:6px" id="battlePlayerHpText">HP: --/--</div>
          </div>
        </div>

        <div style="margin-top:8px; display:flex; gap:8px;">
          <button class="btn-action" id="fightBtn">Fight</button>
          <button class="btn-action" id="bagBtn">Bag</button>
          <button class="btn-action" id="runBtn">Run</button>
        </div>

        <div style="margin-top:8px; font-size:13px; color:var(--muted)">Battle Log</div>
        <div class="log" id="battleLog"></div>
      </div>
    </div>
  </div>

<script>
/* Mini Pokémon-like game
   Features:
   - Grid map with path, grass, water, trees.
   - Player movement, encounter on grass with chance.
   - Simple turn-based battle: fight, bag (pokéball), run.
   - Save/Load to localStorage.
   - Mobile D-pad and keyboard controls.
*/

// ---------- Config & Data ----------
const MAP_W = 12, MAP_H = 8;
const TILE_TYPES = ['path','grass','water','tree'];
const encounterChance = 0.18; // 18% on grass tile per step
const wildPool = [
  {name:'Sparky', sprite:'⚡', hp:18, atk:6, levelRange:[1,2], catchRate:0.6},
  {name:'Buzzy',  sprite:'🐝', hp:14, atk:5, levelRange:[1,3], catchRate:0.5},
  {name:'Flare',  sprite:'🔥', hp:22, atk:7, levelRange:[2,4], catchRate:0.45},
  {name:'Glim',   sprite:'🦋', hp:12, atk:4, levelRange:[1,2], catchRate:0.7},
];

// Player's starter creature
const starter = {name:'Flit', sprite:'🐾', maxHp:30, currentHp:30, atk:7, level:1, xp:0};

// ---------- State ----------
let map = []; // 2D array of tile types
let player = {x:5, y:4, steps:0, balls:5, pokemon: structuredClone(starter)};
let inBattle = false;
let currentWild = null;
let lastSaved = null;

// ---------- Utils ----------
const $ = id => document.getElementById(id);
function log(msg){ const el = $('log'); el.innerHTML += `<div>• ${escapeHtml(msg)}</div>`; el.scrollTop = el.scrollHeight; }
function battleLog(msg){ const el = $('battleLog'); el.innerHTML += `<div>• ${escapeHtml(msg)}</div>`; el.scrollTop = el.scrollHeight; }
function escapeHtml(str){ return String(str).replaceAll('&','&amp;').replaceAll('<','&lt;').replaceAll('>','&gt;'); }
function rand(n){ return Math.floor(Math.random()*n); }
function randBetween(a,b){return a + rand(b-a+1);}
function clamp(v,a,b){return Math.max(a, Math.min(b,v));}
function percentage(part,total){ return total?Math.round((part/total)*100):0;}

// ---------- Map Generation ----------
function generateMap(){
  map = [];
  for(let y=0;y<MAP_H;y++){
    const row = [];
    for(let x=0;x<MAP_W;x++){
      // Simple hand-tuned layout for playability
      if (y===0 || y===MAP_H-1 || x===0 || x===MAP_W-1) row.push('tree');
      else if ((x===3 && y>=2 && y<=5) || (x===8 && y>=1 && y<=3)) row.push('tree');
      else if ( (y===2 && x>=4 && x<=7) || (y===5 && x>=2 && x<=9) ) row.push('path');
      else if ( (x>=1 && x<=3 && y===6) || (x>=9 && x<=10 && y===3) ) row.push('water');
      else {
        // random grass or path bias
        row.push(Math.random() < 0.5 ? 'grass' : 'path');
      }
    }
    map.push(row);
  }
}

// ---------- Render ----------
function renderMap(){
  const mapEl = $('map');
  mapEl.innerHTML = '';
  for(let y=0;y<MAP_H;y++){
    for(let x=0;x<MAP_W;x++){
      const t = map[y][x];
      const div = document.createElement('div');
      div.className = 'tile ' + t;
      // simple icons for features
      if (t==='tree') div.textContent = '🌳';
      else if (t==='water') div.textContent = '~~~';
      else if (t==='path') div.textContent = '·';
      else if (t==='grass') div.textContent = '🌿';
      if (player.x===x && player.y===y){
        const p = document.createElement('div');
        p.className = 'player';
        p.textContent = player.pokemon.sprite;
        div.appendChild(p);
      }
      mapEl.appendChild(div);
    }
  }
  $('steps').textContent = player.steps;
  $('balls').textContent = player.balls;
  // Player info refresh
  refreshPlayerPanel();
}

function refreshPlayerPanel(){
  $('playerName').textContent = player.pokemon.name + ' (Lv ' + player.pokemon.level + ')';
  const hpPerc = percentage(player.pokemon.currentHp, player.pokemon.maxHp);
  $('playerHp').style.width = hpPerc + '%';
  $('playerHpText').textContent = `HP: ${player.pokemon.currentHp}/${player.pokemon.maxHp}`;
  $('playerSprite').textContent = player.pokemon.sprite;
}

// ---------- Movement & Input ----------
function tryMove(dx,dy){
  if (inBattle) return;
  const nx = player.x + dx, ny = player.y + dy;
  if (nx <0 || nx >= MAP_W || ny <0 || ny >= MAP_H) return;
  const tile = map[ny][nx];
  if (tile === 'tree' || tile === 'water') {
    log('You cannot go that way.');
    return;
  }
  player.x = nx; player.y = ny; player.steps++;
  renderMap();

  // Encounter check if on grass
  if (tile === 'grass' && Math.random() < encounterChance){
    triggerEncounter();
  }
}

function triggerEncounter(){
  // pick random wild
  const w = structuredClone(wildPool[rand(wildPool.length)]);
  const lvl = randBetween(w.levelRange[0], w.levelRange[1]);
  w.level = lvl;
  w.maxHp = Math.max(6, Math.floor(w.hp + lvl*3));
  w.currentHp = w.maxHp;
  w.atk = Math.max(2, Math.floor(w.atk + lvl));
  currentWild = w;
  openBattle();
}

// ---------- Battle ----------
function openBattle(){
  inBattle = true;
  $('modal').classList.add('open');
  $('modal').setAttribute('aria-hidden','false');
  // populate UI
  $('wildName').textContent = currentWild.name;
  $('wildSprite').textContent = currentWild.sprite;
  $('wildLevel').textContent = currentWild.level;
  $('wildHp').style.width = '100%';
  $('wildHpText').textContent = `HP: ${currentWild.currentHp}/${currentWild.maxHp}`;

  $('battlePlayerName').textContent = player.pokemon.name;
  $('battlePlayerSprite').textContent = player.pokemon.sprite;
  $('battlePlayerLevel').textContent = player.pokemon.level;
  updateBattlePlayerHpUI();

  $('battleLog').innerHTML = '';
  battleLog(`A wild ${currentWild.name} appeared!`);
}

function updateBattlePlayerHpUI(){
  const pct = percentage(player.pokemon.currentHp, player.pokemon.maxHp);
  $('battlePlayerHp').style.width = pct + '%';
  $('battlePlayerHpText').textContent = `HP: ${player.pokemon.currentHp}/${player.pokemon.maxHp}`;
}

function updateBattleWildHpUI(){
  const pct = percentage(currentWild.currentHp, currentWild.maxHp);
  $('wildHp').style.width = pct + '%';
  $('wildHpText').textContent = `HP: ${currentWild.currentHp}/${currentWild.maxHp}`;
}

function closeBattle(){
  inBattle = false;
  $('modal').classList.remove('open');
  $('modal').setAttribute('aria-hidden','true');
  currentWild = null;
  // after battle, small heal to player's pokemon
  player.pokemon.currentHp = clamp(player.pokemon.currentHp, 0, player.pokemon.maxHp);
  renderMap();
  saveProgress(false);
}

function playerAttack(){
  const dmg = Math.max(1, player.pokemon.atk + rand(3) - 1);
  currentWild.currentHp -= dmg;
  if (currentWild.currentHp < 0) currentWild.currentHp = 0;
  battleLog(`${player.pokemon.name} deals ${dmg} damage to ${currentWild.name}.`);
  updateBattleWildHpUI();
  if (currentWild.currentHp === 0){
    battleLog(`${currentWild.name} fainted! You won!`);
    // reward xp & small heal
    player.pokemon.xp += 10 + currentWild.level*2;
    player.pokemon.currentHp = Math.min(player.pokemon.maxHp, player.pokemon.currentHp + 4);
    closeBattle();
    return;
  }
  // wild attacks
  setTimeout(()=>{ wildAttack(); }, 700);
}

function wildAttack(){
  const dmg = Math.max(1, currentWild.atk + rand(3) - 1);
  player.pokemon.currentHp -= dmg;
  if (player.pokemon.currentHp < 0) player.pokemon.currentHp = 0;
  battleLog(`${currentWild.name} hits ${player.pokemon.name} for ${dmg} damage.`);
  updateBattlePlayerHpUI();
  if (player.pokemon.currentHp === 0){
    battleLog(`${player.pokemon.name} fainted! You run back home...`);
    // reset player's pokemon to half hp for this mini game
    player.pokemon.currentHp = Math.max(4, Math.floor(player.pokemon.maxHp/2));
    closeBattle();
  }
}

function tryCatch(){
  if (player.balls <= 0){
    battleLog("You have no Pokéballs!");
    return;
  }
  player.balls--;
  $('balls').textContent = player.balls;
  // simple catch formula: better when HP low and pokemon has higher catchRate
  const hpFactor = 1 - (currentWild.currentHp / currentWild.maxHp); // 0..1
  const baseChance = currentWild.catchRate;
  const final = clamp(baseChance * 0.6 + hpFactor * 0.8, 0.05, 0.98);
  battleLog(`You throw a Pokéball... (chance ${(final*100).toFixed(0)}%)`);
  if (Math.random() < final){
    battleLog(`Yes! You caught ${currentWild.name}!`);
    // add to player's "collection" in localStorage (simple)
    addToCollection(currentWild);
    closeBattle();
  } else {
    battleLog("It broke free!");
    // wild gets free attack
    setTimeout(()=> wildAttack(), 700);
  }
}

function runFromBattle(){
  // chance to run depends on wild level vs player
  const chance = player.pokemon.level >= currentWild.level ? 0.95 : 0.5;
  if (Math.random() < chance){
    battleLog('You got away safely!');
    closeBattle();
  } else {
    battleLog('Could not escape!');
    setTimeout(()=> wildAttack(), 700);
  }
}

function addToCollection(pk){
  const col = JSON.parse(localStorage.getItem('mini_col') || '[]');
  col.push({name:pk.name, sprite:pk.sprite, level:pk.level, caughtAt:Date.now()});
  localStorage.setItem('mini_col', JSON.stringify(col));
  log(`Captured ${pk.name} (Lv ${pk.level}) — added to collection.`);
}

// ---------- Save / Load ----------
function saveProgress(showToast=true){
  const state = {player, map, lastSaved:Date.now()};
  localStorage.setItem('mini_save', JSON.stringify(state));
  lastSaved = state.lastSaved;
  if (showToast) log('Progress saved.');
}

function loadProgress(){
  const raw = localStorage.getItem('mini_save');
  if (!raw) return false;
  try{
    const st = JSON.parse(raw);
    player = st.player;
    map = st.map;
    lastSaved = st.lastSaved;
    return true;
  }catch(e){ return false; }
}

function resetGame(){
  localStorage.removeItem('mini_save');
  localStorage.removeItem('mini_col');
  player = {x:5, y:4, steps:0, balls:5, pokemon: structuredClone(starter)};
  generateMap();
  renderMap();
  $('log').innerHTML = '';
  log('Game reset.');
  saveProgress(false);
}

// ---------- UI Wireup ----------
document.addEventListener('DOMContentLoaded', ()=>{
  // load or generate
  if (!loadProgress()){
    generateMap();
    saveProgress(false);
  }
  renderMap();
  // bind keyboard
  document.addEventListener('keydown', (e)=>{
    if (inBattle){
      // allow fight (F), bag (B), run (R) via keys
      if (e.key.toLowerCase()==='f') { playerAttack(); }
      if (e.key.toLowerCase()==='b') { tryCatch(); }
      if (e.key.toLowerCase()==='r') { runFromBattle(); }
      return;
    }
    if (['ArrowUp','w','W'].includes(e.key)) { tryMove(0,-1); }
    if (['ArrowDown','s','S'].includes(e.key)) { tryMove(0,1); }
    if (['ArrowLeft','a','A'].includes(e.key)) { tryMove(-1,0); }
    if (['ArrowRight','d','D'].includes(e.key)) { tryMove(1,0); }
  });

  // buttons
  $('fightBtn').addEventListener('click', ()=>{ if(inBattle) playerAttack(); });
  $('bagBtn').addEventListener('click', ()=>{ if(inBattle) tryCatch(); });
  $('runBtn').addEventListener('click', ()=>{ if(inBattle) runFromBattle(); });

  $('healBtn').addEventListener('click', ()=>{
    const heal = 15;
    player.pokemon.currentHp = Math.min(player.pokemon.maxHp, player.pokemon.currentHp + heal);
    refreshPlayerPanel();
    log(`You used a Potion. ${player.pokemon.name} recovered ${heal} HP.`);
    saveProgress(false);
  });

  $('saveBtn').addEventListener('click', ()=> saveProgress(true));
  $('resetBtn').addEventListener('click', ()=> {
    if (confirm('Reset game and clear saved progress?')) resetGame();
  });

  // modal click outside to close only when not in battle (but we want close only via battle end)
  $('modal').addEventListener('click', (e)=>{
    if (e.target === $('modal') && !inBattle) closeBattle();
  });

  // mobile dpad
  document.querySelectorAll('[data-dir]').forEach(btn=>{
    btn.addEventListener('click', ()=> {
      const d = btn.dataset.dir;
      if (d==='up') tryMove(0,-1);
      if (d==='down') tryMove(0,1);
      if (d==='left') tryMove(-1,0);
      if (d==='right') tryMove(1,0);
      if (d==='space') {
        log('No action assigned.');
      }
    });
  });

  log('Welcome Trainer! Use arrow keys or the on-screen D-pad to move.');
  log('Tip: Walk on grass (🌿) to find wild creatures.');
});

// ---------- Init ----------
// If no save exists, generate.
if (!localStorage.getItem('mini_save')){
  generateMap();
  saveProgress(false);
}
</script>
</body>
</html>

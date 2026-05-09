# francais-vivant
Learn french, don't translate it

<style>
*{box-sizing:border-box;margin:0;padding:0}
#app{padding:1rem 0;font-family:var(--font-sans)}
.screen{display:none}.screen.active{display:block}
.card{background:var(--color-background-primary);border:0.5px solid var(--color-border-tertiary);border-radius:var(--border-radius-lg);overflow:hidden;margin-bottom:1rem}
.card-p{padding:1rem 1.25rem}
.nav-btn{background:#534AB7;color:#fff;border:none;border-radius:var(--border-radius-md);padding:13px 20px;font-size:15px;font-weight:500;cursor:pointer;width:100%;margin-bottom:8px;transition:opacity .15s;display:flex;align-items:center;justify-content:center;gap:8px}
.nav-btn:hover{opacity:.88}
.nav-btn.ghost{background:transparent;color:var(--color-text-secondary);border:0.5px solid var(--color-border-tertiary)}
.nav-btn.ghost:hover{background:var(--color-background-secondary)}
.vbtn{background:var(--color-background-primary);border:0.5px solid var(--color-border-secondary);border-radius:var(--border-radius-md);padding:12px;font-size:16px;font-weight:500;color:var(--color-text-primary);cursor:pointer;transition:all .15s;text-align:center;width:100%}
.vbtn:hover{background:var(--color-background-secondary)}
.vbtn.ok{background:#EAF3DE;border-color:#639922;color:#27500A}
.vbtn.bad{background:#FCEBEB;border-color:#A32D2D;color:#501313}
.fb{border-radius:var(--border-radius-md);padding:12px 16px;margin-bottom:1rem;font-size:14px;display:none;line-height:1.5}
.fb.show{display:block}.fb.ok{background:#EAF3DE;color:#27500A}.fb.bad{background:#FCEBEB;color:#501313}
.pb-wrap{background:var(--color-background-secondary);border-radius:99px;height:5px;margin-bottom:1.25rem;overflow:hidden}
.pb{height:100%;background:#534AB7;border-radius:99px;transition:width .35s}
.grid2{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-bottom:1rem}
.scene-vis{background:#EEEDFE;display:flex;align-items:center;justify-content:center;flex-direction:column;gap:6px;padding:1.5rem;min-height:130px}
.scene-emoji{font-size:52px}
.scene-verb{font-size:24px;font-weight:500;color:#3C3489}
.scene-ctx{font-size:13px;color:#534AB7;text-align:center}
.conj-vis{background:#EEEDFE;padding:1.25rem;display:flex;align-items:center;gap:16px}
.conj-vis-emoji{font-size:48px;line-height:1;flex-shrink:0}
.conj-mini{display:grid;grid-template-columns:1fr 1fr;border-top:0.5px solid var(--color-border-tertiary)}
.cm-cell{padding:7px 10px;font-size:13px;border-bottom:0.5px solid var(--color-border-tertiary)}
.cm-pro{color:var(--color-text-secondary);border-right:0.5px solid var(--color-border-tertiary)}
.cm-frm{color:#3C3489;font-weight:500}
.cm-hi{background:#EAF3DE}
.pill-row{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:1.25rem}
.pill{border-radius:99px;padding:6px 14px;font-size:13px;cursor:pointer;border:0.5px solid var(--color-border-secondary);background:var(--color-background-primary);color:var(--color-text-secondary);transition:all .15s}
.pill.on{background:#EEEDFE;border-color:#534AB7;color:#3C3489;font-weight:500}
.mode-card{background:var(--color-background-primary);border:0.5px solid var(--color-border-tertiary);border-radius:var(--border-radius-lg);padding:1rem 1.25rem;cursor:pointer;display:flex;align-items:center;gap:14px;margin-bottom:10px;transition:border-color .15s}
.mode-card:hover{border-color:#534AB7}
.mode-icon{width:40px;height:40px;border-radius:var(--border-radius-md);background:#EEEDFE;display:flex;align-items:center;justify-content:center;font-size:20px;color:#534AB7;flex-shrink:0}
.mode-title{font-size:15px;font-weight:500;color:var(--color-text-primary)}
.mode-desc{font-size:12px;color:var(--color-text-secondary);margin-top:2px}
.flip-card{perspective:600px;height:160px;cursor:pointer;margin-bottom:1rem}
.flip-inner{transition:transform .45s;transform-style:preserve-3d;height:100%;position:relative}
.flip-card.flipped .flip-inner{transform:rotateY(180deg)}
.flip-face{position:absolute;inset:0;backface-visibility:hidden;border-radius:var(--border-radius-lg);border:0.5px solid var(--color-border-tertiary);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:8px}
.flip-front{background:#EEEDFE}.flip-back{background:var(--color-background-primary);transform:rotateY(180deg)}
.score-ring{width:96px;height:96px;border-radius:50%;background:#EEEDFE;border:3px solid #534AB7;display:flex;align-items:center;justify-content:center;flex-direction:column;margin:1.25rem auto}
.tag-pill{background:#EEEDFE;color:#3C3489;border-radius:99px;padding:4px 12px;font-size:13px;font-weight:500;display:inline-block;margin:3px}
.hard-badge{background:#FCEBEB;color:#791F1F;border-radius:99px;padding:3px 10px;font-size:12px;font-weight:500}
.ai-badge{background:#E1F5EE;color:#085041;border-radius:99px;padding:3px 10px;font-size:12px;font-weight:500}
.dot-spin{width:18px;height:18px;border:2px solid #CECBF6;border-top-color:#534AB7;border-radius:50%;animation:spin .7s linear infinite;flex-shrink:0}
@keyframes spin{to{transform:rotate(360deg)}}
textarea{width:100%;border:0.5px solid var(--color-border-secondary);border-radius:var(--border-radius-md);padding:10px 12px;font-size:14px;font-family:var(--font-sans);color:var(--color-text-primary);background:var(--color-background-primary);resize:none;outline:none;line-height:1.5}
textarea:focus{border-color:#534AB7}
</style>

<div id="app">
<h2 class="sr-only">Français Vivant — five-mode immersive French verb learning app</h2>

<div class="screen active" id="s-home">
  <div style="text-align:center;padding:1rem 0 1.5rem">
    <div style="font-size:36px;margin-bottom:8px">🇫🇷</div>
    <div style="font-size:20px;font-weight:500;color:var(--color-text-primary)">Français Vivant</div>
    <div style="font-size:13px;color:var(--color-text-secondary);margin-top:4px">Think in French — never translate.</div>
  </div>
  <div class="mode-card" onclick="startScene()">
    <div class="mode-icon"><i class="ti ti-photo" aria-hidden="true"></i></div>
    <div><div class="mode-title">Scene quiz</div><div class="mode-desc">See it happen, pick the verb — immersion style</div></div>
  </div>
  <div class="mode-card" onclick="startConj()">
    <div class="mode-icon"><i class="ti ti-list" aria-hidden="true"></i></div>
    <div><div class="mode-title">Conjugation drill</div><div class="mode-desc">Master je / tu / il / nous / vous / ils with scene clues</div></div>
  </div>
  <div class="mode-card" onclick="startFC()">
    <div class="mode-icon"><i class="ti ti-cards" aria-hidden="true"></i></div>
    <div><div class="mode-title">Flashcard browse</div><div class="mode-desc">Flip to reveal all conjugations</div></div>
  </div>
  <div class="mode-card" onclick="startHard()">
    <div class="mode-icon" style="background:#FCEBEB;color:#A32D2D"><i class="ti ti-bolt" aria-hidden="true"></i></div>
    <div><div class="mode-title">Hard mode &nbsp;<span class="hard-badge">No hints</span></div><div class="mode-desc">Type the conjugated form — no choices, no clues</div></div>
  </div>
  <div class="mode-card" onclick="showScreen('aiquiz')">
    <div class="mode-icon" style="background:#E1F5EE;color:#0F6E56"><i class="ti ti-sparkles" aria-hidden="true"></i></div>
    <div><div class="mode-title">AI quiz generator</div><div class="mode-desc">Enter a topic — get a custom 6-question quiz</div></div>
  </div>
</div>

<div class="screen" id="s-scene">
  <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px">
    <div style="font-size:13px;color:var(--color-text-secondary)" id="sc-step">Q 1/6</div>
    <div class="pill-row" style="margin:0">
      <div class="pill on" id="sc-pbeg" onclick="setSceneLvl('beginner')">Beginner</div>
      <div class="pill" id="sc-pint" onclick="setSceneLvl('intermediate')">Intermediate</div>
    </div>
  </div>
  <div class="pb-wrap"><div class="pb" id="sc-pb" style="width:0%"></div></div>
  <div class="card"><div class="scene-vis"><div class="scene-emoji" id="sc-emoji">🍽️</div><div class="scene-verb" id="sc-verb">manger</div><div class="scene-ctx" id="sc-ctx">Il mange une pizza.</div></div></div>
  <div style="font-size:13px;color:var(--color-text-secondary);text-align:center;margin-bottom:10px">Quel est ce verbe ?</div>
  <div class="grid2" id="sc-choices"></div>
  <div class="fb" id="sc-fb"></div>
  <button class="nav-btn" id="sc-next" onclick="scNext()" style="display:none">Suivant <i class="ti ti-arrow-right" aria-hidden="true"></i></button>
  <button class="nav-btn ghost" onclick="goHome()"><i class="ti ti-arrow-left" aria-hidden="true"></i> Menu</button>
</div>

<div class="screen" id="s-conj">
  <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px">
    <div style="font-size:13px;color:var(--color-text-secondary)" id="cj-step">Q 1/6</div>
    <div style="font-size:13px;color:#534AB7;font-weight:500" id="cj-badge"></div>
  </div>
  <div class="pb-wrap"><div class="pb" id="cj-pb" style="width:0%"></div></div>
  <div class="card">
    <div class="conj-vis">
      <div class="conj-vis-emoji" id="cj-emoji">😴</div>
      <div>
        <div style="font-size:20px;font-weight:500;color:#3C3489" id="cj-verb">dormir</div>
        <div style="font-size:13px;color:#534AB7;margin-top:3px" id="cj-scene">Elle dort dans son lit.</div>
      </div>
    </div>
    <div style="padding:1rem 1.25rem">
      <div style="font-size:13px;color:var(--color-text-secondary);margin-bottom:4px">Complétez :</div>
      <div style="font-size:22px;font-weight:500;color:var(--color-text-primary)" id="cj-prompt">Nous ___</div>
    </div>
  </div>
  <div class="grid2" id="cj-choices"></div>
  <div class="fb" id="cj-fb"></div>
  <div class="card" id="cj-reveal" style="display:none">
    <div class="card-p" style="padding-bottom:6px"><div style="font-size:12px;color:var(--color-text-secondary)">Toutes les formes de <strong id="cj-reveal-name"></strong></div></div>
    <div class="conj-mini" id="cj-mini"></div>
  </div>
  <button class="nav-btn" id="cj-next" onclick="cjNext()" style="display:none">Suivant <i class="ti ti-arrow-right" aria-hidden="true"></i></button>
  <button class="nav-btn ghost" onclick="goHome()"><i class="ti ti-arrow-left" aria-hidden="true"></i> Menu</button>
</div>

<div class="screen" id="s-fc">
  <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px">
    <div style="font-size:16px;font-weight:500;color:var(--color-text-primary)">Flashcards</div>
    <div style="font-size:13px;color:var(--color-text-secondary)" id="fc-count">1 / 12</div>
  </div>
  <div style="font-size:13px;color:var(--color-text-secondary);margin-bottom:12px">Tap the card to reveal conjugations</div>
  <div class="flip-card" id="fc-card" onclick="flipCard()">
    <div class="flip-inner" id="fc-inner">
      <div class="flip-face flip-front"><div style="font-size:44px" id="fc-emoji">🍽️</div><div style="font-size:26px;font-weight:500;color:#3C3489" id="fc-verb">manger</div><div style="font-size:13px;color:#534AB7">Tap pour voir les formes</div></div>
      <div class="flip-face flip-back"><div style="padding:1rem;width:100%"><table style="width:100%;font-size:13px;border-collapse:collapse" id="fc-table"></table></div></div>
    </div>
  </div>
  <div style="display:flex;gap:10px;margin-bottom:1rem">
    <button class="nav-btn ghost" style="flex:1" onclick="fcMove(-1)"><i class="ti ti-arrow-left" aria-hidden="true"></i> Précédent</button>
    <button class="nav-btn" style="flex:1" onclick="fcMove(1)">Suivant <i class="ti ti-arrow-right" aria-hidden="true"></i></button>
  </div>
  <button class="nav-btn ghost" onclick="goHome()"><i class="ti ti-arrow-left" aria-hidden="true"></i> Menu</button>
</div>

<div class="screen" id="s-hard">
  <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px">
    <div style="font-size:13px;color:var(--color-text-secondary)" id="hd-step">Q 1/6</div>
    <span class="hard-badge">Hard mode</span>
  </div>
  <div class="pb-wrap"><div class="pb" id="hd-pb" style="width:0%"></div></div>
  <div class="card">
    <div class="conj-vis">
      <div class="conj-vis-emoji" id="hd-emoji">😴</div>
      <div>
        <div style="font-size:20px;font-weight:500;color:#3C3489" id="hd-verb">dormir</div>
        <div style="font-size:13px;color:#534AB7;margin-top:3px" id="hd-scene">Elle dort dans son lit.</div>
      </div>
    </div>
    <div style="padding:1rem 1.25rem">
      <div style="font-size:13px;color:var(--color-text-secondary);margin-bottom:4px">Écrivez la forme correcte :</div>
      <div style="font-size:20px;font-weight:500;color:var(--color-text-primary)" id="hd-prompt">nous ___</div>
    </div>
  </div>
  <input type="text" id="hd-input" placeholder="Écrivez ici..." style="width:100%;margin-bottom:10px;font-size:16px;padding:12px" onkeydown="if(event.key==='Enter')checkHard()">
  <button class="nav-btn" onclick="checkHard()">Vérifier <i class="ti ti-check" aria-hidden="true"></i></button>
  <div class="fb" id="hd-fb"></div>
  <button class="nav-btn" id="hd-next" onclick="hdNext()" style="display:none;margin-top:4px">Suivant <i class="ti ti-arrow-right" aria-hidden="true"></i></button>
  <button class="nav-btn ghost" onclick="goHome()"><i class="ti ti-arrow-left" aria-hidden="true"></i> Menu</button>
</div>

<div class="screen" id="s-aiquiz">
  <div style="font-size:16px;font-weight:500;color:var(--color-text-primary);margin-bottom:4px">AI quiz generator</div>
  <div style="font-size:13px;color:var(--color-text-secondary);margin-bottom:1.25rem">Describe a topic — get a custom 6-question quiz.</div>
  <div class="card card-p" style="margin-bottom:1rem">
    <div style="font-size:12px;color:var(--color-text-secondary);margin-bottom:6px">Topic or context</div>
    <textarea id="ai-topic" rows="3" placeholder="e.g. Ordering food at a café in Paris, a soccer game, morning routine at school..."></textarea>
    <div class="pill-row" style="margin-top:10px;margin-bottom:0">
      <div class="pill on" id="aiq-beg" onclick="setAILvl('beginner')">Beginner</div>
      <div class="pill" id="aiq-int" onclick="setAILvl('intermediate')">Intermediate</div>
      <div class="pill" id="aiq-hard" onclick="setAILvl('hard')">Hard</div>
    </div>
  </div>
  <button class="nav-btn" onclick="generateAIQuiz()"><i class="ti ti-sparkles" aria-hidden="true"></i> Generate quiz</button>
  <button class="nav-btn ghost" onclick="goHome()"><i class="ti ti-arrow-left" aria-hidden="true"></i> Menu</button>
</div>

<div class="screen" id="s-aiquiz-play">
  <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px">
    <div style="font-size:13px;color:var(--color-text-secondary)" id="aiq-step">Q 1/6</div>
    <span class="ai-badge">AI Quiz</span>
  </div>
  <div class="pb-wrap"><div class="pb" id="aiq-pb" style="width:0%"></div></div>
  <div class="card"><div class="scene-vis"><div class="scene-emoji" id="aiq-emoji">✨</div><div class="scene-verb" id="aiq-verb"></div><div class="scene-ctx" id="aiq-ctx"></div></div></div>
  <div style="font-size:13px;color:var(--color-text-secondary);text-align:center;margin-bottom:10px" id="aiq-hint">Quel est ce verbe ?</div>
  <div class="grid2" id="aiq-choices"></div>
  <div class="fb" id="aiq-fb"></div>
  <button class="nav-btn" id="aiq-next" onclick="aiqNext()" style="display:none">Suivant <i class="ti ti-arrow-right" aria-hidden="true"></i></button>
  <button class="nav-btn ghost" onclick="showScreen('aiquiz')"><i class="ti ti-arrow-left" aria-hidden="true"></i> New topic</button>
</div>

<div class="screen" id="s-result">
  <div class="score-ring">
    <div style="font-size:26px;font-weight:500;color:#3C3489" id="res-n">0</div>
    <div style="font-size:11px;color:#534AB7" id="res-d">/ 6</div>
  </div>
  <div style="text-align:center;margin-bottom:1.5rem">
    <div style="font-size:16px;font-weight:500;color:var(--color-text-primary)" id="res-title">Bien joué !</div>
    <div style="font-size:13px;color:var(--color-text-secondary);margin-top:4px" id="res-sub">Tu penses en français.</div>
  </div>
  <div class="card card-p" style="margin-bottom:1rem">
    <div style="font-size:12px;color:var(--color-text-secondary);margin-bottom:8px">Verbes pratiqués</div>
    <div id="res-tags"></div>
  </div>
  <button class="nav-btn" onclick="goHome()"><i class="ti ti-home" aria-hidden="true"></i> Menu principal</button>
  <button class="nav-btn ghost" onclick="sendPrompt('Teach me more French verbs in the immersion style!')">Plus de verbes ↗</button>
</div>

</div>
<script>
const PRONOUNS=['je','tu','il/elle','nous','vous','ils/elles'];
const VERBS=[
  {verb:'manger',emoji:'🍽️',scene:'Il mange une pizza au dîner.',conj:['mange','manges','mange','mangeons','mangez','mangent']},
  {verb:'dormir',emoji:'😴',scene:'Elle dort dans son lit.',conj:['dors','dors','dort','dormons','dormez','dorment']},
  {verb:'courir',emoji:'🏃',scene:'Il court dans le parc.',conj:['cours','cours','court','courons','courez','courent']},
  {verb:'lire',emoji:'📖',scene:'Elle lit un livre.',conj:['lis','lis','lit','lisons','lisez','lisent']},
  {verb:'écrire',emoji:'✍️',scene:'Il écrit une lettre à sa mère.',conj:['écris','écris','écrit','écrivons','écrivez','écrivent']},
  {verb:'chanter',emoji:'🎵',scene:'Elle chante une belle chanson.',conj:['chante','chantes','chante','chantons','chantez','chantent']},
  {verb:'nager',emoji:'🏊',scene:'Il nage dans la piscine.',conj:['nage','nages','nage','nageons','nagez','nagent']},
  {verb:'peindre',emoji:'🎨',scene:'Elle peint un tableau magnifique.',conj:['peins','peins','peint','peignons','peignez','peignent']},
  {verb:'réfléchir',emoji:'🤔',scene:'Il réfléchit à la question.',conj:['réfléchis','réfléchis','réfléchit','réfléchissons','réfléchissez','réfléchissent']},
  {verb:'croire',emoji:'🙏',scene:'Elle croit en ses amis.',conj:['crois','crois','croit','croyons','croyez','croient']},
  {verb:'promettre',emoji:'🤝',scene:'Il promet de revenir demain.',conj:['promets','promets','promet','promettons','promettez','promettent']},
  {verb:'rire',emoji:'😂',scene:'Ils rient ensemble au café.',conj:['ris','ris','rit','rions','riez','rient']},
];

function shuffle(a){return a.slice().sort(()=>Math.random()-.5)}
function showScreen(id){document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));document.getElementById('s-'+id).classList.add('active')}
function goHome(){showScreen('home')}

let sceneLvl='beginner';
function setSceneLvl(l){sceneLvl=l;document.getElementById('sc-pbeg').classList.toggle('on',l==='beginner');document.getElementById('sc-pint').classList.toggle('on',l==='intermediate')}

let scQ=[],scI=0,scScore=0,scAns=false;
function startScene(){
  scQ=shuffle(VERBS).slice(0,6);scI=0;scScore=0;scAns=false;
  showScreen('scene');renderScene();
}
function renderScene(){
  const q=scQ[scI];
  document.getElementById('sc-step').textContent=`Q ${scI+1}/${scQ.length}`;
  document.getElementById('sc-pb').style.width=(scI/scQ.length*100)+'%';
  document.getElementById('sc-emoji').textContent=q.emoji;
  document.getElementById('sc-verb').textContent=q.verb;
  document.getElementById('sc-ctx').textContent=q.scene;
  document.getElementById('sc-fb').className='fb';
  document.getElementById('sc-next').style.display='none';
  scAns=false;
  let opts=shuffle([q.verb,...shuffle(VERBS.filter(v=>v.verb!==q.verb)).slice(0,3).map(v=>v.verb)]);
  const ch=document.getElementById('sc-choices');ch.innerHTML='';
  opts.forEach(v=>{const b=document.createElement('button');b.className='vbtn';b.textContent=v;b.onclick=()=>ansScene(v,q.verb);ch.appendChild(b)});
}
function ansScene(chosen,correct){
  if(scAns)return;scAns=true;
  document.querySelectorAll('#sc-choices .vbtn').forEach(b=>{b.onclick=null;if(b.textContent===correct)b.classList.add('ok');else if(b.textContent===chosen&&chosen!==correct)b.classList.add('bad')});
  const fb=document.getElementById('sc-fb');
  if(chosen===correct){scScore++;fb.className='fb ok show';fb.innerHTML=`<strong>Oui !</strong> <em>${correct}</em> — tu l'as senti.`}
  else{fb.className='fb bad show';fb.innerHTML=`Le verbe est <strong>${correct}</strong>. Regarde la scène et mémorise.`}
  document.getElementById('sc-next').style.display='flex';
}
function scNext(){scI++;if(scI>=scQ.length)showResult(scScore,scQ.length,scQ.map(q=>q.verb));else renderScene()}

let cjQ=[],cjI=0,cjScore=0,cjAns=false;
function startConj(){
  cjQ=shuffle(VERBS).slice(0,6).map(v=>{const pi=Math.floor(Math.random()*6);return{verb:v.verb,emoji:v.emoji,scene:v.scene,pronoun:PRONOUNS[pi],answer:v.conj[pi],allConj:v.conj,pi};});
  cjI=0;cjScore=0;cjAns=false;showScreen('conj');renderConj();
}
function renderConj(){
  const q=cjQ[cjI];
  document.getElementById('cj-step').textContent=`Q ${cjI+1}/${cjQ.length}`;
  document.getElementById('cj-pb').style.width=(cjI/cjQ.length*100)+'%';
  document.getElementById('cj-badge').textContent=q.emoji+' '+q.verb;
  document.getElementById('cj-emoji').textContent=q.emoji;
  document.getElementById('cj-verb').textContent=q.verb;
  document.getElementById('cj-scene').textContent=q.scene;
  document.getElementById('cj-prompt').textContent=q.pronoun+' ___';
  document.getElementById('cj-fb').className='fb';
  document.getElementById('cj-next').style.display='none';
  document.getElementById('cj-reveal').style.display='none';
  cjAns=false;
  const allF=VERBS.flatMap(v=>v.conj);
  let dis=shuffle(q.allConj.filter(f=>f!==q.answer));
  if(dis.length<3)dis=[...dis,...shuffle(allF.filter(f=>!q.allConj.includes(f)))].slice(0,3);
  else dis=dis.slice(0,3);
  const opts=shuffle([q.answer,...dis]);
  const ch=document.getElementById('cj-choices');ch.innerHTML='';
  opts.forEach(v=>{const b=document.createElement('button');b.className='vbtn';b.textContent=v;b.onclick=()=>ansConj(v,q);ch.appendChild(b)});
}
function ansConj(chosen,q){
  if(cjAns)return;cjAns=true;
  document.querySelectorAll('#cj-choices .vbtn').forEach(b=>{b.onclick=null;if(b.textContent===q.answer)b.classList.add('ok');else if(b.textContent===chosen&&chosen!==q.answer)b.classList.add('bad')});
  const fb=document.getElementById('cj-fb');
  if(chosen===q.answer){cjScore++;fb.className='fb ok show';fb.innerHTML=`<strong>Correct !</strong> ${q.pronoun} <em>${q.answer}</em>.`}
  else{fb.className='fb bad show';fb.innerHTML=`La bonne forme : <strong>${q.pronoun} ${q.answer}</strong>`}
  document.getElementById('cj-reveal-name').textContent=q.verb;
  const mini=document.getElementById('cj-mini');
  mini.innerHTML=PRONOUNS.map((p,i)=>`<div class="cm-cell cm-pro">${p}</div><div class="cm-cell cm-frm${i===q.pi?' cm-hi':''}">${q.allConj[i]}</div>`).join('');
  document.getElementById('cj-reveal').style.display='block';
  document.getElementById('cj-next').style.display='flex';
}
function cjNext(){cjI++;if(cjI>=cjQ.length)showResult(cjScore,cjQ.length,cjQ.map(q=>q.verb));else renderConj()}

let fcI=0;
function startFC(){fcI=0;showScreen('fc');renderFC()}
function renderFC(){
  const v=VERBS[fcI];
  document.getElementById('fc-count').textContent=`${fcI+1} / ${VERBS.length}`;
  document.getElementById('fc-emoji').textContent=v.emoji;
  document.getElementById('fc-verb').textContent=v.verb;
  document.getElementById('fc-card').classList.remove('flipped');
  document.getElementById('fc-table').innerHTML=PRONOUNS.map((p,i)=>`<tr><td style="color:var(--color-text-secondary);padding:5px 8px;border-bottom:0.5px solid var(--color-border-tertiary);width:45%">${p}</td><td style="color:#3C3489;font-weight:500;padding:5px 8px;border-bottom:0.5px solid var(--color-border-tertiary)">${v.conj[i]}</td></tr>`).join('');
}
function flipCard(){document.getElementById('fc-card').classList.toggle('flipped')}
function fcMove(d){fcI=(fcI+d+VERBS.length)%VERBS.length;renderFC()}

let hdQ=[],hdI=0,hdScore=0;
function startHard(){
  hdQ=shuffle(VERBS).slice(0,6).map(v=>{const pi=Math.floor(Math.random()*6);return{verb:v.verb,emoji:v.emoji,scene:v.scene,pronoun:PRONOUNS[pi],answer:v.conj[pi]}});
  hdI=0;hdScore=0;showScreen('hard');renderHard();
}
function renderHard(){
  const q=hdQ[hdI];
  document.getElementById('hd-step').textContent=`Q ${hdI+1}/${hdQ.length}`;
  document.getElementById('hd-pb').style.width=(hdI/hdQ.length*100)+'%';
  document.getElementById('hd-emoji').textContent=q.emoji;
  document.getElementById('hd-verb').textContent=q.verb;
  document.getElementById('hd-scene').textContent=q.scene;
  document.getElementById('hd-prompt').textContent=q.pronoun+' ___';
  document.getElementById('hd-input').value='';
  document.getElementById('hd-input').disabled=false;
  document.getElementById('hd-fb').className='fb';
  document.getElementById('hd-next').style.display='none';
  document.getElementById('hd-input').focus();
}
function checkHard(){
  const q=hdQ[hdI];
  const val=document.getElementById('hd-input').value.trim().toLowerCase();
  if(!val)return;
  document.getElementById('hd-input').disabled=true;
  const fb=document.getElementById('hd-fb');
  if(val===q.answer){hdScore++;fb.className='fb ok show';fb.innerHTML=`<strong>Parfait !</strong> ${q.pronoun} <em>${q.answer}</em> ✓`}
  else{fb.className='fb bad show';fb.innerHTML=`La bonne réponse : <strong>${q.pronoun} ${q.answer}</strong>`}
  document.getElementById('hd-next').style.display='flex';
}
function hdNext(){hdI++;if(hdI>=hdQ.length)showResult(hdScore,hdQ.length,hdQ.map(q=>q.verb));else renderHard()}

let aiLvl='beginner';
function setAILvl(l){aiLvl=l;['beg','int','hard'].forEach(k=>document.getElementById('aiq-'+k).classList.remove('on'));document.getElementById('aiq-'+(l==='beginner'?'beg':l==='intermediate'?'int':'hard')).classList.add('on')}

let aiqQ=[],aiqI=0,aiqScore=0,aiqAns=false;
async function generateAIQuiz(){
  const topic=document.getElementById('ai-topic').value.trim();
  if(!topic){document.getElementById('ai-topic').focus();return}
  showScreen('aiquiz-play');
  document.getElementById('aiq-choices').innerHTML='<div style="display:flex;align-items:center;gap:10px;padding:1rem;color:var(--color-text-secondary);font-size:14px"><div class="dot-spin"></div>Génération du quiz en cours...</div>';
  document.getElementById('aiq-emoji').textContent='✨';document.getElementById('aiq-verb').textContent='';document.getElementById('aiq-ctx').textContent='';
  document.getElementById('aiq-fb').className='fb';document.getElementById('aiq-next').style.display='none';document.getElementById('aiq-step').textContent='Chargement...';document.getElementById('aiq-pb').style.width='0%';
  const lvlDesc=aiLvl==='beginner'?'beginner (simple present, common verbs like manger, dormir, courir)':aiLvl==='intermediate'?'intermediate (irregular verbs, mixed tenses)':'hard (subjunctive, rare verbs, complex conjugations)';
  try{
    const r=await fetch('https://api.anthropic.com/v1/messages',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({model:'claude-sonnet-4-20250514',max_tokens:1000,messages:[{role:'user',content:`You are a French teacher. Create a 6-question immersive French verb quiz about: "${topic}". Level: ${lvlDesc}. Rules: all French only, no English. Each question has a scene emoji, infinitive verb, one French example sentence, and 4 answer choices (correct + 3 distractors). Return ONLY valid JSON, no markdown: {"questions":[{"emoji":"🍽️","verb":"manger","sentence":"Il mange une pizza au café.","choices":["manger","dormir","courir","lire"],"hint":"Quel est ce verbe ?"}]}`}]})});
    const d=await r.json();
    const txt=d.content.map(c=>c.text||'').join('');
    aiqQ=JSON.parse(txt.replace(/```json|```/g,'').trim()).questions;
    aiqI=0;aiqScore=0;aiqAns=false;renderAIQ();
  }catch(e){document.getElementById('aiq-choices').innerHTML='<div style="padding:1rem;color:var(--color-text-danger);font-size:14px">Erreur — réessayez.</div>'}
}
function renderAIQ(){
  const q=aiqQ[aiqI];
  document.getElementById('aiq-step').textContent=`Q ${aiqI+1}/${aiqQ.length}`;
  document.getElementById('aiq-pb').style.width=(aiqI/aiqQ.length*100)+'%';
  document.getElementById('aiq-emoji').textContent=q.emoji||'✨';
  document.getElementById('aiq-verb').textContent=q.verb;
  document.getElementById('aiq-ctx').textContent=q.sentence;
  document.getElementById('aiq-hint').textContent=q.hint||'Quel est ce verbe ?';
  document.getElementById('aiq-fb').className='fb';document.getElementById('aiq-next').style.display='none';aiqAns=false;
  const ch=document.getElementById('aiq-choices');ch.innerHTML='';
  shuffle(q.choices).forEach(v=>{const b=document.createElement('button');b.className='vbtn';b.textContent=v;b.onclick=()=>ansAIQ(v,q.verb);ch.appendChild(b)});
}
function ansAIQ(chosen,correct){
  if(aiqAns)return;aiqAns=true;
  document.querySelectorAll('#aiq-choices .vbtn').forEach(b=>{b.onclick=null;if(b.textContent===correct)b.classList.add('ok');else if(b.textContent===chosen&&chosen!==correct)b.classList.add('bad')});
  const fb=document.getElementById('aiq-fb');
  if(chosen===correct){aiqScore++;fb.className='fb ok show';fb.innerHTML=`<strong>Oui !</strong> <em>${correct}</em> — tu l'as senti.`}
  else{fb.className='fb bad show';fb.innerHTML=`Le verbe est <strong>${correct}</strong>.`}
  document.getElementById('aiq-next').style.display='flex';
}
function aiqNext(){aiqI++;if(aiqI>=aiqQ.length)showResult(aiqScore,aiqQ.length,aiqQ.map(q=>q.verb));else renderAIQ()}

function showResult(score,total,verbs){
  showScreen('result');
  document.getElementById('res-n').textContent=score;
  document.getElementById('res-d').textContent='/ '+total;
  const pct=score/total;
  const[t,s]=pct===1?['Parfait !','Tu maîtrises ces formes !']:pct>=.67?['Très bien !','Tu es sur la bonne voie.']:['Continue !','Chaque essai renforce ton instinct.'];
  document.getElementById('res-title').textContent=t;document.getElementById('res-sub').textContent=s;
  document.getElementById('res-tags').innerHTML=[...new Set(verbs)].map(v=>`<span class="tag-pill">${v}</span>`).join('');
}
</script>

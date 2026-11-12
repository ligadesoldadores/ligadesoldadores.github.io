<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="utf-8">
<title>Liga de Soldadores</title>
<meta name="theme-color" content="#0d1420">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Barlow:wght@400;500;600;700&family=Barlow+Condensed:wght@600;700;800&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#0d1420; --card:#162034; --card2:#1c2843; --line:#2a3757;
  --text:#eef2f8; --muted:#94a1ba;
  --arc:#ff8a1f; --arc2:#ffc061; --blue:#5cc8ff;
  --red:#e5484d; --green:#2fa84f; --purple:#8e4ec6;
  --gold:#f5c542; --silver:#c8d0db; --bronze:#d98b52;
  --cond:'Barlow Condensed','Arial Narrow',Arial,sans-serif;
}
*{box-sizing:border-box;margin:0;padding:0}
html,body{background:var(--bg);color:var(--text);font-family:Barlow,system-ui,sans-serif;-webkit-font-smoothing:antialiased}
body{min-height:100vh;background:
  radial-gradient(600px 300px at 85% -80px,rgba(255,138,31,.18),transparent 70%),
  radial-gradient(500px 260px at -10% 0,rgba(92,200,255,.10),transparent 70%),var(--bg)}
.hidden{display:none!important}
button{font:inherit;cursor:pointer;border:0;color:inherit;background:none}
a{color:var(--arc2)}
#login{min-height:100vh;display:flex;flex-direction:column;justify-content:center;padding:32px 16px;max-width:400px;margin:0 auto}
.brand{text-align:center;margin-bottom:28px}
.badge{width:84px;height:84px;margin:0 auto 16px;border-radius:24px;display:grid;place-items:center;font-size:42px;
  background:linear-gradient(145deg,#2a1a0c,#1a1209);border:1px solid rgba(255,138,31,.45);
  box-shadow:0 0 0 6px rgba(255,138,31,.07),0 10px 40px rgba(255,138,31,.25)}
.badge img{max-width:64px;max-height:64px}
.brand h1{font-family:var(--cond);font-weight:800;font-size:38px;letter-spacing:.5px;text-transform:uppercase;line-height:1}
.brand h1 span{color:var(--arc)}
.brand p{color:var(--muted);font-size:14px;margin-top:8px}
.form{background:var(--card);border:1px solid var(--line);border-radius:18px;padding:20px}
label{display:block;font-size:13px;font-weight:600;color:var(--muted);margin:0 0 6px 2px}
.field{position:relative;margin-bottom:14px}
input{width:100%;font:inherit;font-size:17px;color:var(--text);background:var(--bg);border:1px solid var(--line);border-radius:12px;padding:13px 14px;outline:none}
input:focus{border-color:var(--arc);box-shadow:0 0 0 3px rgba(255,138,31,.2)}
.eye{position:absolute;right:6px;top:6px;bottom:6px;padding:0 10px;color:var(--muted);font-size:13px;font-weight:600}
.btn{width:100%;padding:14px;border-radius:12px;background:linear-gradient(180deg,var(--arc2),var(--arc));color:#1b0f02;font-weight:700;font-size:17px}
.btn:disabled{opacity:.6}
.err{color:#ff8e91;font-size:14px;min-height:20px;margin-top:12px;text-align:center}
.foot{text-align:center;color:var(--muted);font-size:12px;margin-top:22px}
.wrap{max-width:520px;margin:0 auto;padding:14px 16px 110px}
.top{display:flex;align-items:center;justify-content:space-between;margin-bottom:14px}
.top .t{font-family:var(--cond);font-weight:800;font-size:20px;text-transform:uppercase;letter-spacing:.5px}
.top .t span{color:var(--arc)}
.ghost{border:1px solid var(--line);color:var(--muted);padding:7px 12px;border-radius:999px;font-size:13px;font-weight:600}
nav{position:fixed;left:0;right:0;bottom:0;z-index:10;background:rgba(13,20,32,.96);border-top:1px solid var(--line);
  backdrop-filter:blur(8px);-webkit-backdrop-filter:blur(8px);padding-bottom:env(safe-area-inset-bottom)}
nav .in{max-width:520px;margin:0 auto;display:grid;grid-template-columns:repeat(5,1fr)}
nav button{padding:9px 2px 10px;display:flex;flex-direction:column;align-items:center;gap:3px;color:var(--muted);font-size:11px;font-weight:600}
nav button .ic{font-size:21px;line-height:1;filter:grayscale(1);opacity:.75}
nav button.on{color:var(--arc2)}
nav button.on .ic{filter:none;opacity:1}
h2{font-family:var(--cond);font-weight:800;font-size:22px;text-transform:uppercase;letter-spacing:.5px;margin:0 0 10px;display:flex;align-items:center;gap:8px}
h2 small{font-family:Barlow,sans-serif;font-size:12px;text-transform:none;letter-spacing:0;color:var(--muted);font-weight:600;margin-left:auto}
.sec{margin-bottom:22px}
.card{background:var(--card);border:1px solid var(--line);border-radius:16px;overflow:hidden}
.empty{padding:18px 14px;color:var(--muted);font-size:14px;text-align:center}
.hello{font-size:15px;color:var(--muted);margin:2px 0 12px}
.hello b{color:var(--text);font-size:22px;display:block;font-weight:700}
.hero{position:relative;overflow:hidden;border-radius:20px;padding:18px;border:1px solid rgba(255,138,31,.35);
  background:linear-gradient(150deg,#2b1b0d 0%,#1a1424 55%,#14213a 100%)}
.hero:after{content:"";position:absolute;right:-60px;top:-60px;width:200px;height:200px;border-radius:50%;
  background:radial-gradient(circle,rgba(255,192,97,.35),transparent 65%)}
.hero .row{display:flex;align-items:flex-end;justify-content:space-between;gap:12px;position:relative;z-index:1}
.lbl{font-size:12px;font-weight:700;letter-spacing:1px;text-transform:uppercase;color:var(--arc2)}
.pos{font-family:var(--cond);font-weight:800;font-size:72px;line-height:.9;margin-top:6px}
.pos small{font-size:20px;color:var(--muted);font-weight:600;margin-left:6px}
.pts{text-align:right}
.pts .n{font-family:var(--cond);font-weight:800;font-size:44px;line-height:.9;color:var(--arc2)}
.pts .u{font-size:13px;color:var(--muted)}
.goal{position:relative;z-index:1;margin-top:14px;padding:10px 12px;border-radius:12px;background:rgba(255,255,255,.06);font-size:14px}
.goal b{color:var(--arc2)}
.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin:12px 0 22px}
.stat{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:12px 10px;text-align:center}
.stat .v{font-family:var(--cond);font-weight:800;font-size:28px;line-height:1}
.stat .k{font-size:11.5px;color:var(--muted);margin-top:5px;font-weight:600}
.bar{height:6px;border-radius:6px;background:var(--line);margin-top:8px;overflow:hidden}
.bar i{display:block;height:100%;background:linear-gradient(90deg,var(--arc),var(--arc2));border-radius:6px}
.aviso{padding:12px 14px;border-top:1px solid var(--line);font-size:14.5px;line-height:1.4}
.aviso:first-child{border-top:0}
.aviso .f{font-size:11.5px;font-weight:700;color:var(--arc2);margin-bottom:2px}
.logros{display:grid;grid-template-columns:repeat(4,1fr);gap:8px}
.lg{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:10px 4px;text-align:center}
.lg .e{font-size:26px;line-height:1.1}
.lg .n{font-size:11px;font-weight:700;margin-top:5px;line-height:1.15}
.lg.off{opacity:.45}
.lg.off .e{filter:grayscale(1)}
.lg.on{border-color:rgba(255,192,97,.55);background:linear-gradient(180deg,rgba(255,138,31,.16),var(--card))}
.tip{font-size:12.5px;color:var(--muted);margin-top:8px;min-height:18px}
.upd{display:flex;align-items:center;justify-content:space-between;color:var(--muted);font-size:12.5px}
.pr{padding:12px 14px;border-top:1px solid var(--line)}
.pr:first-child{border-top:0}
.pr .r{display:flex;align-items:center;gap:10px}
.pn{font-family:var(--cond);font-weight:800;font-size:16px;color:var(--muted);width:30px;flex:none}
.pd{flex:1;min-width:0}
.pd .name{font-weight:600;font-size:15px;line-height:1.2}
.chip{display:inline-block;margin-top:4px;font-size:11.5px;font-weight:700;padding:2px 8px;border-radius:999px;border:1px solid var(--line);color:var(--muted)}
.chip.terminada{background:rgba(47,168,79,.15);border-color:rgba(47,168,79,.5);color:#7fdc98}
.chip.encurso{background:rgba(255,192,97,.13);border-color:rgba(255,192,97,.5);color:var(--arc2)}
.chip.repetir{background:rgba(229,72,77,.15);border-color:rgba(229,72,77,.5);color:#ff8e91}
.chip.noasiste{background:rgba(148,161,186,.12);color:var(--muted)}
.nota{flex:none;min-width:52px;text-align:center;font-family:var(--cond);font-weight:800;font-size:22px;padding:6px 8px;border-radius:10px;background:var(--card2);color:var(--muted)}
.nota.r{background:var(--red);color:#fff}
.nota.g{background:var(--green);color:#fff}
.nota.p{background:var(--purple);color:#fff;box-shadow:0 0 14px rgba(142,78,198,.6)}
.com{margin:10px 0 0 40px;padding:9px 11px;border-radius:10px;background:rgba(92,200,255,.08);border:1px solid rgba(92,200,255,.25);font-size:13.5px;line-height:1.4}
.com b{display:block;font-size:11px;color:var(--blue);margin-bottom:2px;letter-spacing:.3px}
.lnk{margin:8px 0 0 40px;font-size:13px;font-weight:700;color:var(--arc2)}
.upl{display:inline-flex;align-items:center;gap:6px;margin:10px 0 0 40px;padding:9px 14px;border-radius:10px;background:linear-gradient(180deg,var(--arc2),var(--arc));color:#1b0f02;font-weight:700;font-size:13.5px}
.upl.sec2{background:transparent;border:1px solid var(--arc);color:var(--arc2)}
.upl:disabled{opacity:.6}
.ent{margin:10px 0 0 40px;font-size:12.5px;color:var(--muted);display:flex;align-items:center;gap:6px;flex-wrap:wrap}
.chip.pendientedecorregir{background:rgba(255,192,97,.13);border-color:rgba(255,192,97,.5);color:var(--arc2)}
.chip.corregida{background:rgba(47,168,79,.15);border-color:rgba(47,168,79,.5);color:#7fdc98}
.upmsg{margin:8px 0 0 40px;font-size:13px;color:var(--arc2);font-weight:600}
.upmsg.err{color:#ff8e91}
#foto{position:absolute;left:-9999px;width:1px;height:1px;opacity:0}
.toast{position:fixed;left:50%;bottom:86px;transform:translateX(-50%);background:#2fa84f;color:#fff;font-weight:700;padding:12px 18px;border-radius:12px;z-index:20;box-shadow:0 8px 30px rgba(0,0,0,.45);font-size:15px}
.legend{display:flex;gap:12px;flex-wrap:wrap;font-size:12px;color:var(--muted);margin:10px 0 0 2px}
.legend span:before{content:"";display:inline-block;width:10px;height:10px;border-radius:3px;margin-right:5px;vertical-align:-1px;background:var(--c)}
.rk{display:flex;align-items:center;gap:10px;padding:11px 14px;border-top:1px solid var(--line)}
.rk:first-child{border-top:0}
.rk .p{width:38px;flex:none;font-family:var(--cond);font-weight:800;font-size:20px;text-align:center}
.rk .who{flex:1;min-width:0}
.rk .who .name{font-weight:600;font-size:15px;display:flex;align-items:center;min-width:0}
.rk .who .nm{white-space:nowrap;overflow:hidden;text-overflow:ellipsis;min-width:0}
.rk .mini{height:5px;border-radius:5px;background:var(--line);margin-top:6px;overflow:hidden}
.rk .mini i{display:block;height:100%;background:var(--blue);border-radius:5px}
.rk .s{flex:none;font-family:var(--cond);font-weight:800;font-size:20px;min-width:46px;text-align:right}
.rk.m1{background:linear-gradient(90deg,rgba(245,197,66,.20),transparent)} .rk.m1 .mini i{background:var(--gold)}
.rk.m2{background:linear-gradient(90deg,rgba(200,208,219,.16),transparent)} .rk.m2 .mini i{background:var(--silver)}
.rk.m3{background:linear-gradient(90deg,rgba(217,139,82,.18),transparent)} .rk.m3 .mini i{background:var(--bronze)}
.rk.yo{box-shadow:inset 3px 0 0 var(--arc);background-color:rgba(255,138,31,.10)}
.tu{flex:none;font-size:10.5px;font-weight:800;background:var(--arc);color:#1b0f02;padding:1px 6px;border-radius:6px;margin-left:6px}
.dots{text-align:center;color:var(--muted);padding:4px 0;border-top:1px solid var(--line);letter-spacing:4px}
.fc{display:flex;align-items:center;gap:12px;width:100%;text-align:left;padding:14px;border-top:1px solid var(--line)}
.fc:first-child{border-top:0}
.fc .num{flex:none;width:44px;height:44px;border-radius:12px;display:grid;place-items:center;font-family:var(--cond);font-weight:800;font-size:19px;
  background:linear-gradient(145deg,#2a1a0c,#1a1209);border:1px solid rgba(255,138,31,.45);color:var(--arc2)}
.fc .tx{flex:1;min-width:0}
.fc .tx b{display:block;font-size:15.5px;line-height:1.2}
.fc .tx span{font-size:12.5px;color:var(--muted)}
.fc .go{color:var(--muted);font-size:22px}
.back{display:inline-flex;align-items:center;gap:6px;color:var(--arc2);font-weight:700;font-size:14px;margin-bottom:12px}
.fh{border-radius:18px;padding:16px;border:1px solid rgba(255,138,31,.35);background:linear-gradient(150deg,#2b1b0d 0%,#1a1424 60%,#14213a 100%);margin-bottom:14px}
.fh .k{font-family:var(--cond);font-weight:800;color:var(--arc2);font-size:15px;letter-spacing:1px}
.fh h3{font-family:var(--cond);font-weight:800;font-size:28px;line-height:1.05;text-transform:uppercase;margin:4px 0 8px}
.fh p{font-size:14.5px;line-height:1.45;color:#d6dceb}
.params{display:grid;grid-template-columns:repeat(2,1fr);gap:8px;margin-bottom:14px}
.prm{background:var(--card);border:1px solid var(--line);border-radius:12px;padding:10px 12px}
.prm .k{font-size:11px;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.6px}
.prm .v{font-family:var(--cond);font-weight:800;font-size:20px;margin-top:2px;line-height:1.1}
.prm.big{grid-column:1/-1}
.prm.big .v{font-family:Barlow,sans-serif;font-size:14.5px;font-weight:600}
ol.pasos{list-style:none;counter-reset:p}
ol.pasos li{counter-increment:p;display:flex;gap:12px;padding:12px 14px;border-top:1px solid var(--line);font-size:14.5px;line-height:1.4}
ol.pasos li:first-child{border-top:0}
ol.pasos li:before{content:counter(p);flex:none;width:26px;height:26px;border-radius:50%;display:grid;place-items:center;background:var(--arc);color:#1b0f02;font-weight:800;font-size:13px}
.cons li{list-style:none;padding:11px 14px;border-top:1px solid var(--line);font-size:14px;line-height:1.4}
.cons li:first-child{border-top:0}
.cons li:before{content:"⚠️ ";}
.btn2{display:block;text-align:center;padding:13px;border-radius:12px;border:1px solid var(--arc);color:var(--arc2);font-weight:700;text-decoration:none}
.epis{display:grid;grid-template-columns:repeat(2,1fr);gap:8px}
.epi{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:12px;font-size:13.5px;font-weight:600;line-height:1.3;display:flex;gap:8px;align-items:flex-start}
.epi:before{content:"🦺";font-size:18px;line-height:1}
.norma{display:flex;gap:10px;padding:12px 14px;border-top:1px solid var(--line);font-size:14.5px;line-height:1.4}
.norma:first-child{border-top:0}
.norma:before{content:"✔";color:var(--green);font-weight:800}
.spin{display:inline-block;width:16px;height:16px;border:2px solid rgba(0,0,0,.25);border-top-color:#1b0f02;border-radius:50%;animation:s .7s linear infinite;vertical-align:-3px}
@keyframes s{to{transform:rotate(360deg)}}
</style>
</head>
<body>

<section id="login">
  <div class="brand">
    <div class="badge" id="logo">🏆</div>
    <h1 id="titulo">Liga de <span>Soldadores</span></h1>
    <p id="subtitulo"></p>
  </div>
  <form class="form" id="f" autocomplete="on">
    <div class="field">
      <label for="u">Usuario</label>
      <input id="u" name="username" autocomplete="username" autocapitalize="none" autocorrect="off" spellcheck="false" placeholder="nombre.apellido">
    </div>
    <div class="field">
      <label for="c">Contraseña</label>
      <input id="c" name="password" type="password" autocomplete="current-password" autocapitalize="none" placeholder="••••••">
      <button type="button" class="eye" id="eye">Ver</button>
    </div>
    <button class="btn" id="go" type="submit">Entrar</button>
    <div class="err" id="err"></div>
  </form>
  <p class="foot" id="centro"></p>
</section>

<input type="file" id="foto" accept="image/*">
<section id="panel" class="hidden">
  <div class="wrap">
    <div class="top"><div class="t">🏆 Liga de <span>Soldadores</span></div><button class="ghost" onclick="salir()">Salir</button></div>
    <div id="out"></div>
  </div>
  <nav><div class="in">
    <button data-v="inicio" onclick="ir('inicio')"><span class="ic">🏠</span>Inicio</button>
    <button data-v="practicas" onclick="ir('practicas')"><span class="ic">🔧</span>Prácticas</button>
    <button data-v="liga" onclick="ir('liga')"><span class="ic">🏆</span>Liga</button>
    <button data-v="fichas" onclick="ir('fichas')"><span class="ic">📘</span>Fichas</button>
    <button data-v="seguridad" onclick="ir('seguridad')"><span class="ic">🦺</span>Seguridad</button>
  </div></nav>
</section>

<script>
var API = 'https://script.google.com/macros/s/AKfycbwS-3chr8gCePo3mi_ZfcUP8PvfzcbNV-Ta6bPEa-P-eobP5vCe0GbvaHA_Z2rUcbs5cA/exec';
var CFG = {titulo:'Liga de Soldadores', subtitulo:'Soldadura en atmósfera natural · 1º Soldadura y Calderería', centro:'IES Sanje', logo:''};
var cred = null, D = null, vista = 'inicio';

function $(id){return document.getElementById(id);}
function esc(s){return String(s==null?'':s).replace(/[&<>"']/g,function(c){return {'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c];});}
function br(s){return esc(s).replace(/\n/g,'<br>');}
function num(x){return x==null?'—':Number(x).toLocaleString('es-ES',{maximumFractionDigits:1});}
function claseNota(n){return n==null?'':(n<5?'r':(n<9?'g':'p'));}
function claseEstado(e){return String(e||'').toLowerCase().normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/\s+/g,'');}
function medalla(p){return p===1?'🥇':p===2?'🥈':p===3?'🥉':p+'º';}
function fichaDe(n){return (D.fichas||[]).filter(function(f){return f.n===n;})[0];}

(function init(){
  var t=CFG.titulo.split(' '); var last=t.pop();
  $('titulo').innerHTML=esc(t.join(' '))+' <span>'+esc(last)+'</span>';
  $('subtitulo').textContent=CFG.subtitulo;
  $('centro').textContent=CFG.centro;
  if(CFG.logo){$('logo').innerHTML='<img alt="" src="'+esc(CFG.logo)+'">';}
  try{var u=localStorage.getItem('liga_user'); if(u){$('u').value=u;}}catch(e){}
})();

$('eye').onclick=function(){var c=$('c'); var v=c.type==='password'; c.type=v?'text':'password'; this.textContent=v?'Ocultar':'Ver';};

$('f').onsubmit=function(ev){
  ev.preventDefault();
  var u=$('u').value.trim().toLowerCase(), c=$('c').value.trim();
  if(!u||!c){$('err').textContent='Escribe tu usuario y tu contraseña.';return;}
  cred={u:u,c:c}; entrar(false);
};

function entrar(refresco){
  var b=$('go'); $('err').textContent='';
  if(!refresco){b.disabled=true;b.innerHTML='<span class="spin"></span>';}
  else { var r=$('ref'); if(r){r.disabled=true;r.textContent='Actualizando…';} }
  fetch(API,{method:'POST',body:JSON.stringify({u:cred.u,c:cred.c}),credentials:'omit',redirect:'follow'})
    .then(function(r){ if(!r.ok) throw new Error('http '+r.status); return r.json(); })
    .then(function(res){
      b.disabled=false;b.textContent='Entrar';
      if(!res.ok){ if(refresco){salir();} $('err').textContent=res.msg; return; }
      try{localStorage.setItem('liga_user',cred.u);}catch(e){}
      D=res;
      $('login').classList.add('hidden'); $('panel').classList.remove('hidden');
      ir(refresco?vista:'inicio');
    })
    .catch(function(){
      b.disabled=false;b.textContent='Entrar';
      $('err').textContent='No se ha podido conectar. Revisa tu conexión e inténtalo otra vez.';
      var r=$('ref'); if(r){r.disabled=false;r.textContent='Actualizar';}
    });
}

function salir(){
  cred=null; D=null; $('c').value=''; $('out').innerHTML='';
  $('panel').classList.add('hidden'); $('login').classList.remove('hidden');
  window.scrollTo(0,0);
}

function ir(v,arg){
  vista=v;
  var h = v==='inicio'?vInicio(): v==='practicas'?vPracticas(): v==='liga'?vLiga():
          v==='fichas'?vFichas(): v==='ficha'?vFicha(arg): vSeguridad();
  $('out').innerHTML=h;
  var marcar = v==='ficha'?'fichas':v;
  Array.prototype.forEach.call(document.querySelectorAll('nav button'),function(b){b.classList.toggle('on',b.getAttribute('data-v')===marcar);});
  window.scrollTo(0,0);
}

function vInicio(){
  var a=D.alumno, h='';
  h+='<div class="hello">Hola,<b>'+esc(a.nombre)+'</b></div>';
  h+='<div class="hero"><div class="row"><div><div class="lbl">Tu puesto</div>';
  h+= a.puesto ? '<div class="pos">'+(a.puesto<=3?medalla(a.puesto)+' ':'')+a.puesto+'º<small>de '+a.enLiga+'</small></div>'
               : '<div class="pos" style="font-size:44px">Sin puntos</div>';
  h+='</div><div class="pts"><div class="n">'+num(a.puntos)+'</div><div class="u">puntos</div></div></div>';
  var msg;
  if(!a.puesto) msg='Tu primera nota te mete en la liga. ¡A por ella! 🔥';
  else if(a.puesto===1 && a.faltan==null) msg='<b>¡Eres el líder de la liga!</b> Que no te alcancen. 👑';
  else if(a.faltan!=null) msg='Te faltan <b>'+num(a.faltan)+(a.faltan===1?' punto':' puntos')+'</b> para llegar al <b>'+a.puestoObjetivo+'º puesto</b>.';
  else msg='¡Sigue así!';
  h+='<div class="goal">'+msg+'</div></div>';
  var pct=a.total?Math.round(a.terminadas/a.total*100):0;
  h+='<div class="stats">';
  h+='<div class="stat"><div class="v">'+a.terminadas+'<span style="font-size:16px;color:var(--muted)">/'+a.total+'</span></div><div class="k">Terminadas</div><div class="bar"><i style="width:'+Math.min(pct,100)+'%"></i></div></div>';
  h+='<div class="stat"><div class="v" style="color:'+(a.media==null?'var(--text)':a.media<5?'#ff8e91':a.media<9?'#7fdc98':'#c49bf0')+'">'+num(a.media)+'</div><div class="k">Nota media</div></div>';
  h+='<div class="stat"><div class="v">'+a.excelentes+' ⭐</div><div class="k">Notas de 9-10</div></div>';
  h+='</div>';
  if(D.avisos && D.avisos.length){
    h+='<div class="sec"><h2>📢 Avisos</h2><div class="card">';
    D.avisos.forEach(function(x){h+='<div class="aviso">'+(x.fecha?'<div class="f">'+esc(x.fecha)+'</div>':'')+br(x.texto)+'</div>';});
    h+='</div></div>';
  }
  var con=a.logros.filter(function(l){return l.ok;}).length;
  h+='<div class="sec"><h2>🎖️ Logros<small>'+con+' de '+a.logros.length+'</small></h2><div class="logros">';
  a.logros.forEach(function(l,i){
    h+='<button class="lg '+(l.ok?'on':'off')+'" onclick="tip('+i+')"><div class="e">'+l.i+'</div><div class="n">'+esc(l.t)+'</div></button>';
  });
  h+='</div><div class="tip" id="tip">Toca un logro para ver cómo se consigue.</div></div>';
  h+='<div class="upd"><span>Actualizado: '+esc(D.actualizado||'')+'</span><button class="ghost" id="ref" onclick="entrar(true)">Actualizar</button></div>';
  return h;
}
function tip(i){var l=D.alumno.logros[i]; $('tip').innerHTML=(l.ok?'✅ <b>Conseguido:</b> ':'🔒 <b>Para conseguirlo:</b> ')+esc(l.d);}

function vPracticas(){
  var a=D.alumno, h='<h2>🔧 Mis prácticas</h2><div class="card">';
  if(!a.practicas.length) h+='<div class="empty">Todavía no hay prácticas publicadas.</div>';
  a.practicas.forEach(function(p){
    var f=fichaDe(p.n);
    h+='<div class="pr"><div class="r"><div class="pn">P'+p.n+'</div><div class="pd"><div class="name">'+esc(p.nombre||(f&&f.titulo)||('Práctica '+p.n))+'</div>'+
       '<span class="chip '+claseEstado(p.estado)+'">'+esc(p.estado)+'</span></div>'+
       '<div class="nota '+claseNota(p.nota)+'">'+num(p.nota)+'</div></div>';
    if(p.comentario) h+='<div class="com"><b>💬 COMENTARIO DEL PROFESOR</b>'+br(p.comentario)+'</div>';
    var e=p.entrega;
    if(e) h+='<div class="ent">📷 Entregada el '+esc(e.fecha)+' <span class="chip '+claseEstado(e.estado)+'">'+esc(e.estado)+'</span>'+(e.total>1?' · '+e.total+' fotos':'')+'</div>';
    if(!e || e.total<(D.maxFotos||5)) h+='<button class="upl'+(e?' sec2':'')+'" id="b'+p.n+'" onclick="elegirFoto('+p.n+')">📷 '+(e?'Subir otra foto':'Entregar foto de la práctica')+'</button>';
    h+='<div class="upmsg" id="m'+p.n+'"></div>';
    if(f) h+='<button class="lnk" onclick="ir(\'ficha\','+p.n+')">📘 Ver ficha de la práctica ›</button>';
    h+='</div>';
  });
  h+='</div><div class="legend"><span style="--c:var(--red)">Menos de 5</span><span style="--c:var(--green)">5 a 8</span><span style="--c:var(--purple)">9 y 10</span></div>';
  return h;
}

var subiendo=false, practicaFoto=null;
function elegirFoto(n){
  if(subiendo) return;
  practicaFoto=n; var inp=$('foto'); inp.value=''; inp.click();
}
$('foto').onchange=function(){
  var file=this.files&&this.files[0], n=practicaFoto;
  if(!file||!n) return;
  subiendo=true; msgFoto(n,'⏳ Preparando la foto…'); var bt=$('b'+n); if(bt) bt.disabled=true;
  reducirFoto(file).then(function(b64){
    msgFoto(n,'⏳ Subiendo… no cierres la app');
    return fetch(API,{method:'POST',body:JSON.stringify({accion:'subir',u:cred.u,c:cred.c,p:n,img:b64}),credentials:'omit',redirect:'follow'})
      .then(function(r){ if(!r.ok) throw new Error('http'); return r.json(); });
  }).then(function(res){
    subiendo=false;
    if(!res.ok){ msgFoto(n,res.msg||'No se ha podido subir.',true); if(bt) bt.disabled=false; return; }
    D.alumno.practicas.forEach(function(p){ if(p.n===n) p.entrega=res.entrega; });
    ir('practicas'); aviso('✅ ¡Foto de la P'+n+' entregada!');
  }).catch(function(){
    subiendo=false; if(bt) bt.disabled=false;
    msgFoto(n,'No se ha podido subir. Revisa la conexión e inténtalo otra vez.',true);
  });
};
function msgFoto(n,t,err){var m=$('m'+n); if(m){m.textContent=t; m.className='upmsg'+(err?' err':'');}}
function reducirFoto(file){
  return new Promise(function(ok,ko){
    var url=URL.createObjectURL(file), img=new Image();
    img.onload=function(){
      var max=1600, w=img.naturalWidth, h=img.naturalHeight, s=Math.min(1,max/Math.max(w,h));
      var c=document.createElement('canvas'); c.width=Math.round(w*s); c.height=Math.round(h*s);
      c.getContext('2d').drawImage(img,0,0,c.width,c.height);
      URL.revokeObjectURL(url);
      ok(c.toDataURL('image/jpeg',0.8).split(',')[1]);
    };
    img.onerror=function(){URL.revokeObjectURL(url); ko(new Error('img'));};
    img.src=url;
  });
}
function aviso(t){var d=document.createElement('div'); d.className='toast'; d.textContent=t; document.body.appendChild(d); setTimeout(function(){d.remove();},3500);}

function vLiga(){
  var h='<h2>🏆 Clasificación<small>Top '+D.top.length+'</small></h2><div class="card">';
  if(!D.top.length) h+='<div class="empty">La liga empieza con las primeras notas.</div>';
  var max=D.top.length?D.top[0].puntos:1;
  function fila(r){
    var cls='rk'+(r.puesto<=3?' m'+r.puesto:'')+(r.yo?' yo':'');
    return '<div class="'+cls+'"><div class="p">'+medalla(r.puesto)+'</div><div class="who"><div class="name"><span class="nm">'+esc(r.nombre)+'</span>'+(r.yo?'<span class="tu">TÚ</span>':'')+'</div>'+
      '<div class="mini"><i style="width:'+Math.max(4,Math.round(r.puntos/max*100))+'%"></i></div></div><div class="s">'+num(r.puntos)+'</div></div>';
  }
  D.top.forEach(function(r){h+=fila(r);});
  if(D.yoFuera){h+='<div class="dots">···</div>'+fila(D.yoFuera);}
  h+='</div><p class="tip">Puntos = suma de las notas de todas tus prácticas.</p>';
  return h;
}

function vFichas(){
  var h='<h2>📘 Fichas de prácticas</h2><div class="card">';
  if(!D.fichas || !D.fichas.length) h+='<div class="empty">El profesor todavía no ha publicado fichas.</div>';
  (D.fichas||[]).forEach(function(f){
    var sub=[f.electrodo, f.diametro?'Ø'+f.diametro:'', f.intensidad].filter(Boolean).join(' · ');
    h+='<button class="fc" onclick="ir(\'ficha\','+f.n+')"><div class="num">'+esc(f.p||'')+'</div><div class="tx"><b>'+esc(f.titulo)+'</b><span>'+esc(sub)+'</span></div><div class="go">›</div></button>';
  });
  return h+'</div>';
}
function vFicha(n){
  var f=fichaDe(n); if(!f) return vFichas();
  var h='<button class="back" onclick="ir(\'fichas\')">‹ Todas las fichas</button>';
  h+='<div class="fh"><div class="k">PRÁCTICA '+esc(String(f.n||''))+'</div><h3>'+esc(f.titulo)+'</h3>'+(f.objetivo?'<p>'+br(f.objetivo)+'</p>':'')+'</div>';
  var ps=[['Electrodo',f.electrodo],['Diámetro',f.diametro],['Intensidad',f.intensidad],['Voltaje',f.voltaje],['Polaridad',f.polaridad],['Posición',f.posicion]]
    .filter(function(x){return x[1];});
  if(ps.length || f.material){
    h+='<div class="params">';
    ps.forEach(function(x){h+='<div class="prm"><div class="k">'+x[0]+'</div><div class="v">'+esc(x[1])+'</div></div>';});
    if(f.material) h+='<div class="prm big"><div class="k">Material</div><div class="v">'+esc(f.material)+'</div></div>';
    h+='</div>';
  }
  if(f.pasos.length){
    h+='<div class="sec"><h2>🛠️ Paso a paso</h2><div class="card"><ol class="pasos">';
    f.pasos.forEach(function(p){h+='<li><span>'+esc(p)+'</span></li>';});
    h+='</ol></div></div>';
  }
  if(f.consejos.length){
    h+='<div class="sec"><h2>💡 Errores típicos</h2><div class="card"><ul class="cons">';
    f.consejos.forEach(function(c){h+='<li>'+esc(c)+'</li>';});
    h+='</ul></div></div>';
  }
  if(/^https?:\/\//i.test(f.enlace)) h+='<a class="btn2" href="'+esc(f.enlace)+'" target="_blank" rel="noopener">📄 Ver documento o vídeo</a>';
  return h;
}

function vSeguridad(){
  var s=D.seguridad||{epis:[],normas:[]}, h='';
  h+='<div class="sec"><h2>🦺 EPIs obligatorios</h2>';
  if(!s.epis.length) h+='<div class="card"><div class="empty">Sin datos.</div></div>';
  else { h+='<div class="epis">'; s.epis.forEach(function(e){h+='<div class="epi">'+esc(e)+'</div>';}); h+='</div>'; }
  h+='</div><div class="sec"><h2>📋 Normas del taller</h2><div class="card">';
  if(!s.normas.length) h+='<div class="empty">Sin datos.</div>';
  s.normas.forEach(function(n){h+='<div class="norma"><span>'+esc(n)+'</span></div>';});
  h+='</div></div>';
  h+='<p class="tip">Sin EPIs no se suelda. Tu seguridad es lo primero. 💪</p>';
  return h;
}
</script>
</body>
</html>

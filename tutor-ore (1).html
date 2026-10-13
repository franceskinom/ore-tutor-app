<!DOCTYPE html><html lang="it"><head><meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover"><title>Ore Tutor</title>
<style>
:root{--bg:#f6f7f9;--cd:#fff;--tx:#1d2330;--mu:#6b7385;--bd:#dfe3ea;--ac:#2f6fed;--ok:#1f9d55;--wa:#d97706;--er:#d33;color-scheme:light dark;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#12151c;--cd:#1c212c;--tx:#e8ebf2;--mu:#98a1b5;--bd:#2c3342;--ac:#6b9bff;--ok:#43c37c;--wa:#f0a03c;--er:#ff6b6b}}
:root[data-theme="dark"]{--bg:#12151c;--cd:#1c212c;--tx:#e8ebf2;--mu:#98a1b5;--bd:#2c3342;--ac:#6b9bff;--ok:#43c37c;--wa:#f0a03c;--er:#ff6b6b}
*{box-sizing:border-box}html,body{margin:0}body{background:var(--bg);color:var(--tx);font:15px/1.4 system-ui,-apple-system,Segoe UI,sans-serif}
main{max-width:640px;margin:0 auto;padding:12px 12px 40px}
.tabs{display:flex;gap:6px;margin-bottom:12px}.tabs button{flex:1}
button,input,select,textarea{font:inherit;color:var(--tx);background:var(--cd);border:1px solid var(--bd);border-radius:8px;padding:8px}
button{cursor:pointer}button.on,button.pr{background:var(--ac);color:#fff;border-color:var(--ac)}button.dl{color:var(--er)}
input[type=number]{width:70px}input[type=date]{min-width:0}
.c{background:var(--cd);border:1px solid var(--bd);border-radius:12px;padding:12px;margin-bottom:10px}
.r{display:flex;gap:8px;align-items:center;flex-wrap:wrap}.r>.g{flex:1}
.mu{color:var(--mu);font-size:13px}h2{font-size:16px;margin:16px 0 8px}h3{margin:0 0 4px;font-size:15px}
.b{padding:8px 10px;border-radius:8px;margin-bottom:10px;font-size:14px}.b.er{background:#d3333322;color:var(--er)}.b.wa{background:#d9770622;color:var(--wa)}.b.ok{background:#1f9d5522;color:var(--ok)}
.bar{height:8px;background:var(--bd);border-radius:5px;overflow:hidden;margin:4px 0}.bar i{display:block;height:100%;background:var(--ac)}.bar i.f{background:var(--ok)}
.tag{font-size:12px;padding:2px 7px;border-radius:9px;background:var(--bd)}
textarea{width:100%;height:90px;font-size:12px}
</style></head><body><main id="app"></main>
<script>
const K='tutorore_v1';
let S={classes:[],contract:[],absences:[],stages:[],signed:{},ch:{},defH:6},tab='reg',msg='',bk='';
let user=null;
const save=()=>{if(window.cloudSave&&user)window.cloudSave(JSON.stringify(S))};
const iso=d=>d.getFullYear()+'-'+String(d.getMonth()+1).padStart(2,'0')+'-'+String(d.getDate()).padStart(2,'0');
const pd=s=>new Date(s+'T12:00:00');
const fmt=s=>pd(s).toLocaleDateString('it-IT',{day:'numeric',month:'short',year:'numeric'});
const esc=s=>String(s).replace(/&/g,'&amp;').replace(/"/g,'&quot;').replace(/</g,'&lt;');
const uid=()=>'c'+Date.now().toString(36)+Math.random().toString(36).slice(2,5);
let cur=iso(new Date());
const cap=d=>{const p=S.contract.find(p=>p.from<=d&&d<=p.to);return p?+p.max:0};
const absent=d=>S.absences.find(a=>a.from<=d&&d<=a.to);
const isStage=(c,d)=>c.year>=2&&S.stages.some(s=>s.cid==c.id&&s.from<=d&&d<=s.to);
const cls=(c,d)=>{if(!c.start||d<c.start)return 0;const o=S.ch[d+'|'+c.id];if(o!==undefined)return o;const w=pd(d).getDay();return w>=1&&w<=5?S.defH:0};
const used=d=>Object.values(S.signed[d]||{}).reduce((a,b)=>a+b,0);
const sg=(c,d)=>(S.signed[d]||{})[c.id]||0;
const blocked=(c,d)=>absent(d)||cap(d)==0||(S.classes.some(x=>x.id!=c.id&&isStage(x,d)&&cls(x,d)>0)&&!isStage(c,d));
const maxFor=(c,d)=>blocked(c,d)?0:Math.max(0,Math.min(cls(c,d),cap(d)-(used(d)-sg(c,d))));
const tot=(c,st)=>Object.keys(S.signed).reduce((a,d)=>a+(isStage(c,d)===st?sg(c,d):0),0);
function forecast(){
 const nd={};S.classes.forEach(c=>{const a=Math.max(0,c.minA-tot(c,false)),s=c.year>=2?Math.max(0,c.minS-tot(c,true)):0;nd[c.id]={a,s,da:a==0?'ok':null,ds:s==0?'ok':null}});
 let d=new Date();d.setHours(12);
 for(let i=0;i<1500;i++,d.setDate(d.getDate()+1)){
  const ds=iso(d);let rem=cap(ds)-used(ds);if(absent(ds)||rem<=0)continue;
  const act=S.classes.filter(c=>ds>=c.start),st=act.filter(c=>isStage(c,ds)&&cls(c,ds)>0);
  (st.length?st:act).forEach(c=>{const n=nd[c.id],k=st.length?'s':'a';const h=Math.min(cls(c,ds)-sg(c,ds),rem,n[k]);if(h>0){n[k]-=h;rem-=h}});
  let all=true;S.classes.forEach(c=>{const n=nd[c.id];if(n.a<=0&&!n.da)n.da=ds;if(n.s<=0&&!n.ds)n.ds=ds;if(!n.da||!n.ds)all=false});if(all)break;
 }
 return nd}
const R=()=>{document.getElementById('app').innerHTML=!user?vLogin():head()+(tab=='reg'?vReg():tab=='sum'?vSum():vSet());msg=''};
const head=()=>`<div class=tabs>${[['reg','Registro'],['sum','Riepilogo'],['set','Impostazioni']].map(t=>`<button class="${tab==t[0]?'on':''}" onclick="tab='${t[0]}';R()">${t[1]}</button>`).join('')}</div>${msg?`<div class="b wa">${msg}</div>`:''}`;
function mv(n){const d=pd(cur);d.setDate(d.getDate()+n);cur=iso(d);R()}
function vReg(){
 if(!S.classes.length)return`<div class=c>Prima aggiungi le tue classi in <b>Impostazioni</b>.</div>`;
 const ab=absent(cur),cp=cap(cur),u=used(cur);
 let h=`<div class=r style="margin-bottom:8px"><button onclick="mv(-1)">‹</button><input class=g type=date value="${cur}" onchange="cur=this.value||cur;R()"><button onclick="mv(1)">›</button></div><div class=mu style="margin-bottom:8px">${pd(cur).toLocaleDateString('it-IT',{weekday:'long',day:'numeric',month:'long',year:'numeric'})}</div>`;
 if(ab)h+=`<div class="b er">In ${ab.type}: non puoi firmare ore in nessuna classe.</div>`;
 else if(cp==0)h+=`<div class="b wa">Nessun contratto con ore previste in questa data: non puoi firmare.</div>`;
 else h+=`<div class="b ${u>=cp?'ok':'wa'}">Firmate ${u} / ${cp} ore massime del giorno</div>`;
 const stc=S.classes.filter(c=>isStage(c,cur)&&cls(c,cur)>0);
 if(stc.length&&!ab)h+=`<div class="b wa">Stage: ${stc.map(c=>esc(c.name)).join(', ')}. Puoi firmare solo lo stage, non le altre aule.</div>`;
 S.classes.forEach(c=>{const st=isStage(c,cur),bl=blocked(c,cur),ch=cls(c,cur),mx=maxFor(c,cur);
  h+=`<div class=c><div class=r><div class=g><h3>${esc(c.name)} <span class=tag>${c.year}° anno · ${st?'Stage':'Aula'}</span></h3><div class=mu>${cur<c.start?'Non ancora iniziata':bl?'Non puoi firmare qui oggi':'Max firmabile: '+mx+' h'}</div></div></div>
  <div class=r style="margin-top:8px"><label class=mu>Ore classe <input type=number step=0.5 min=0 value="${ch}" onchange="sch('${c.id}',this.value)"></label><label class=mu>Ore firmate <input type=number step=0.5 min=0 value="${sg(c,cur)}" ${bl||ch==0?'disabled':''} onchange="sgn('${c.id}',this.value)"></label></div></div>`});
 return h}
function sch(id,v){S.ch[cur+'|'+id]=Math.max(0,+v||0);save();R()}
function sgn(id,v){const c=S.classes.find(x=>x.id==id),mx=maxFor(c,cur);let n=Math.max(0,+v||0);if(n>mx){n=mx;msg='Ridotto a '+mx+' ore: limite di classe o del contratto giornaliero.'}
 S.signed[cur]=S.signed[cur]||{};if(n)S.signed[cur][id]=n;else delete S.signed[cur][id];save();R()}
const bar=(a,b)=>`<div class=bar><i class="${a>=b?'f':''}" style="width:${b?Math.min(100,a/b*100):100}%"></i></div>`;
function vSum(){
 if(!S.classes.length)return`<div class=c>Nessuna classe inserita.</div>`;
 const nd=forecast();let h='',last='',ok=true;
 S.classes.forEach(c=>{const a=tot(c,false),s=tot(c,true),n=nd[c.id];
  const f=(x)=>x=='ok'?'<b style="color:var(--ok)">già raggiunto</b>':x?'raggiunto il <b>'+fmt(x)+'</b>':'<b style="color:var(--er)">non raggiungibile con i contratti inseriti</b>';
  [n.da,n.ds].forEach(x=>{if(!x||x=='ok'){if(!x)ok=false}else if(x>last)last=x});
  h+=`<div class=c><h3>${esc(c.name)} <span class=tag>${c.year}° anno</span></h3>
  <div class=mu>Aula: ${a} / ${c.minA} h</div>${bar(a,c.minA)}<div class=mu>Firmando ogni giorno il massimo: ${f(n.da)}</div>
  ${c.year>=2?`<div class=mu style="margin-top:8px">Stage: ${s} / ${c.minS} h</div>${bar(s,c.minS)}<div class=mu>Firmando ogni giorno il massimo: ${f(n.ds)}</div>`:''}</div>`});
 return`<div class="b ${ok?'ok':'er'}">${ok?(last?'Monte ore minimo di tutte le classi raggiunto il <b>'+fmt(last)+'</b> firmando ogni giorno il massimo.':'Tutti i minimi sono già raggiunti.'):'Con i contratti inseriti non tutti i minimi sono raggiungibili: aggiungi i periodi mancanti.'}</div>`+h+`<p class=mu>La previsione parte da oggi, tiene conto di contratto, ferie/malattia, stage, inizio classi e ore giornaliere di ciascuna classe.</p>`}
const inp=(arr,i,k,t='text',x='')=>`<input type=${t} ${x} value="${esc(S[arr][i][k])}" onchange="upd('${arr}',${i},'${k}',${t=='number'?'+this.value':'this.value'})">`;
function upd(a,i,k,v){S[a][i][k]=v;save();R()}
function del(a,i){if(a=='classes'){const id=S.classes[i].id;S.stages=S.stages.filter(s=>s.cid!=id);Object.values(S.signed).forEach(o=>delete o[id])}S[a].splice(i,1);save();R()}
const t0=()=>iso(new Date());
function addC(){const y=+document.getElementById('ny').value,n=document.getElementById('nn').value.trim(),s=document.getElementById('ns').value;if(!n||!s){msg='Inserisci nome classe e data di inizio.';return R()}
 S.classes.push({id:uid(),year:y,name:n,start:s,minA:y==1?300:200,minS:y>=2?200:0});save();R()}
function addP(){const d=new Date(),a=new Date(d.getFullYear(),d.getMonth(),1,12),b=new Date(d.getFullYear(),d.getMonth()+1,0,12);S.contract.push({from:iso(a),to:iso(b),max:6});save();R()}
function addA(){S.absences.push({from:t0(),to:t0(),type:'ferie'});save();R()}
function addS(id){S.stages.push({cid:id,from:t0(),to:t0()});save();R()}
function vSet(){
 let h=`<h2>Classi e annualità</h2>`;
 S.classes.forEach((c,i)=>{h+=`<div class=c><div class=r><div class=g>${inp('classes',i,'name')}</div><span class=tag>${c.year}° anno</span><button class=dl onclick="del('classes',${i})">✕</button></div>
 <div class=r style="margin-top:8px"><label class=mu>Inizio ${inp('classes',i,'start','date')}</label></div>
 <div class=r style="margin-top:8px"><label class=mu>Min. ore aula ${inp('classes',i,'minA','number','min=0')}</label>${c.year>=2?`<label class=mu>Min. ore stage ${inp('classes',i,'minS','number','min=0')}</label>`:''}</div>`;
 if(c.year>=2){h+=`<div class=mu style="margin-top:8px">Periodi di stage</div>`;S.stages.forEach((s,j)=>{if(s.cid==c.id)h+=`<div class=r style="margin-top:4px">${inp('stages',j,'from','date')}<span>→</span>${inp('stages',j,'to','date')}<button class=dl onclick="del('stages',${j})">✕</button></div>`});h+=`<button style="margin-top:6px" onclick="addS('${c.id}')">+ Periodo stage</button>`}
 h+=`</div>`});
 h+=`<div class=c><div class=r><select id=ny><option value=1>1° anno</option><option value=2>2° anno</option><option value=3>3° anno</option></select><input id=nn class=g placeholder="Nome classe" style="min-width:120px"></div><div class=r style="margin-top:8px"><label class=mu>Inizio <input id=ns type=date value="${t0()}"></label><button class=pr onclick="addC()">Aggiungi classe</button></div></div>`;
 h+=`<h2>Ore massime giornaliere da contratto</h2>`;
 S.contract.forEach((p,i)=>{h+=`<div class="c r">${inp('contract',i,'from','date')}<span>→</span>${inp('contract',i,'to','date')}${inp('contract',i,'max','number','min=0 step=0.5')}<span class=mu>h/giorno</span><button class=dl onclick="del('contract',${i})">✕</button></div>`});
 h+=`<button onclick="addP()">+ Periodo contratto</button><h2>Ferie e malattia</h2>`;
 S.absences.forEach((a,i)=>{h+=`<div class="c r">${inp('absences',i,'from','date')}<span>→</span>${inp('absences',i,'to','date')}<select onchange="upd('absences',${i},'type',this.value)"><option ${a.type=='ferie'?'selected':''}>ferie</option><option ${a.type=='malattia'?'selected':''}>malattia</option></select><button class=dl onclick="del('absences',${i})">✕</button></div>`});
 h+=`<button onclick="addA()">+ Assenza</button><h2>Calendario</h2><div class="c r"><span>Ore standard giornaliere (lun-ven)</span><input type=number min=0 step=0.5 value="${S.defH}" onchange="S.defH=Math.max(0,+this.value||0);save();R()"></div><div class=mu>Per cambiare le ore di un singolo giorno usa il campo "Ore classe" nel Registro (0 = giorno di chiusura).</div>
 <h2>Account</h2><div class='c r'><span class=g>${esc(user.email||'')}</span><button onclick="cloud.out()">Esci</button></div><h2>Backup dati</h2><div class=c><textarea id=bk placeholder="Qui compare il backup. Incolla un backup per ripristinarlo.">${esc(bk)}</textarea><div class=r style="margin-top:8px"><button onclick="bk=JSON.stringify(S);R()">Esporta</button><button onclick="imp()">Importa</button></div><div class=mu style="margin-top:6px">I dati sono salvati online nel tuo account: ogni collega vede solo le proprie classi.</div></div>`;
 return h}
function imp(){try{const o=JSON.parse(document.getElementById('bk').value);if(!o.classes)throw 0;S=Object.assign({classes:[],contract:[],absences:[],stages:[],signed:{},ch:{},defH:6},o);save();bk='';msg='Backup importato.'}catch(e){msg='Backup non valido.'}R()}
const vLogin=()=>`<div class=c><h3>Ore Tutor</h3><div class=mu style="margin-bottom:10px">Accedi per vedere le tue classi. Ogni utente ha il proprio archivio.</div>${msg?`<div class="b er">${msg}</div>`:''}<button class=pr style="width:100%" onclick="cloud.google()">Accedi con Google</button><div class=mu style="margin:12px 0 6px">oppure con email</div><input id=em type=email placeholder="Email" style="width:100%;margin-bottom:6px"><input id=pw type=password placeholder="Password (min. 6 caratteri)" style="width:100%;margin-bottom:8px"><div class=r><button class=g onclick="cloud.email(0)">Accedi</button><button class=g onclick="cloud.email(1)">Registrati</button></div><button style="margin-top:8px;width:100%" onclick="cloud.reset()">Password dimenticata</button></div>`;
window.setState=o=>{S=Object.assign({classes:[],contract:[],absences:[],stages:[],signed:{},ch:{},defH:6},o);tab=S.classes.length?'reg':'set'};
window.setUser=u=>{user=u;R()};window.showMsg=m=>{msg=m;R()};
R();
</script>
<script type="module">
import {initializeApp} from "https://www.gstatic.com/firebasejs/10.12.2/firebase-app.js";
import {getAuth,onAuthStateChanged,signInWithPopup,GoogleAuthProvider,signInWithEmailAndPassword,createUserWithEmailAndPassword,signOut,sendPasswordResetEmail} from "https://www.gstatic.com/firebasejs/10.12.2/firebase-auth.js";
import {getFirestore,doc,getDoc,setDoc} from "https://www.gstatic.com/firebasejs/10.12.2/firebase-firestore.js";
// === INCOLLA QUI LA CONFIGURAZIONE DEL TUO NUOVO PROGETTO FIREBASE ===
const firebaseConfig={
  apiKey: "AIzaSyCeMSy_Kon13kvQhXqOPlgFrumqFxdKGeI",
  authDomain: "ore-tutor.firebaseapp.com",
  projectId: "ore-tutor",
  storageBucket: "ore-tutor.firebasestorage.app",
  messagingSenderId: "643028200007",
  appId: "1:643028200007:web:83cc4c55c5faae07da9f62"
};
// =====================================================================
const COL="tutor_users";
if(firebaseConfig.apiKey==="INCOLLA"){showMsg("Configurazione Firebase mancante: apri il file e incolla firebaseConfig.")}
else{
const app=initializeApp(firebaseConfig),auth=getAuth(app),db=getFirestore(app);let t=null,uid=null;
const err=e=>showMsg("Errore: "+(e.code||e.message));
window.cloudSave=txt=>{clearTimeout(t);t=setTimeout(()=>setDoc(doc(db,COL,uid),{data:txt,updated:Date.now()}).catch(()=>showMsg("Salvataggio non riuscito: controlla la connessione.")),600)};
window.cloud={
 google:()=>signInWithPopup(auth,new GoogleAuthProvider()).catch(err),
 email:m=>{const e=document.getElementById('em').value.trim(),p=document.getElementById('pw').value;(m?createUserWithEmailAndPassword:signInWithEmailAndPassword)(auth,e,p).catch(err)},
 reset:()=>{const e=document.getElementById('em').value.trim();if(!e)return showMsg("Inserisci prima l'email.");sendPasswordResetEmail(auth,e).then(()=>showMsg("Email di reset inviata.")).catch(err)},
 out:()=>signOut(auth)};
onAuthStateChanged(auth,async u=>{
 if(!u){uid=null;setUser(null);return}
 try{const d=await getDoc(doc(db,COL,u.uid));uid=u.uid;setState(d.exists()?JSON.parse(d.data().data):{});setUser(u)}
 catch(e){showMsg("Impossibile caricare i dati: controlla le regole di sicurezza Firestore.")}});
}
</script></body></html>


<style>
@import url('https://fonts.googleapis.com/css2?family=Unbounded:wght@400;700;900&family=DM+Mono:ital,wght@0,400;0,500;1,400&display=swap');

*{box-sizing:border-box;margin:0;padding:0}

.root{
  font-family:'DM Mono',monospace;
  background:#080b10;
  color:#f0f4ff;
  border-radius:20px;
  overflow:hidden;
  position:relative;
}

.noise{position:absolute;inset:0;opacity:0.03;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");background-size:200px;z-index:0;pointer-events:none}
.scan-lines{position:absolute;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,255,136,.015) 2px,rgba(0,255,136,.015) 4px);z-index:1;pointer-events:none}

.hero{position:relative;min-height:230px;display:grid;grid-template-columns:1fr 220px;overflow:hidden;z-index:2}
.hero-left{padding:2.5rem 2rem 2rem;position:relative;z-index:3}
.hero-right{position:relative;overflow:hidden}
.gif-frame{width:100%;height:100%;object-fit:cover;display:block;opacity:.85}
.gif-overlay{position:absolute;inset:0;background:linear-gradient(90deg,#080b10 0%,transparent 45%);z-index:2}

.tag{display:inline-flex;align-items:center;gap:5px;font-size:9px;letter-spacing:3px;text-transform:uppercase;color:#00ff88;margin-bottom:16px;animation:fadeUp .5s ease both}
.tag-dot{width:5px;height:5px;border-radius:50%;background:#00ff88;animation:blink 1.4s step-end infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

.hero-name{
  font-family:'Unbounded',sans-serif;
  font-weight:900;
  font-size:38px;
  letter-spacing:-1.5px;
  line-height:1.1;
  color:#f0f4ff;
  animation:fadeUp .5s ease both .1s;
}
.hero-name span{
  display:block;
  color:#00ff88;
}

.hero-sub{font-size:10px;color:#5a6a80;margin-top:10px;letter-spacing:.5px;animation:fadeUp .5s ease both .2s}
.hero-sub b{color:#8892a4;font-weight:500}

@keyframes fadeUp{from{opacity:0;transform:translateY(14px)}to{opacity:1;transform:translateY(0)}}

.divider{height:1px;background:linear-gradient(90deg,#00ff88,rgba(0,207,255,.5),transparent 80%);opacity:.35;position:relative;z-index:2}

.body{padding:1.75rem 2rem;display:grid;grid-template-columns:1fr 260px;gap:2rem;position:relative;z-index:2}

.section-label{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:#00ff88;margin-bottom:12px;opacity:.8}

.stat-row{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:1.75rem;animation:fadeUp .5s ease both .3s}
.stat{background:#0d1219;border:1px solid #1a2030;border-radius:10px;padding:14px 12px;position:relative;overflow:hidden;transition:border-color .2s}
.stat:hover{border-color:#00ff8850}
.stat::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,#00ff88,#00cfff);opacity:0;transition:opacity .2s}
.stat:hover::before{opacity:1}
.stat-n{font-family:'Unbounded',sans-serif;font-weight:900;font-size:28px;letter-spacing:-1px;line-height:1;color:#f0f4ff}
.stat-n span{font-size:16px;color:#00ff88}
.stat-l{font-size:9px;color:#3a4a60;letter-spacing:2px;text-transform:uppercase;margin-top:3px}

.stack-grid{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:1.75rem;animation:fadeUp .5s ease both .4s}
.chip{display:flex;align-items:center;gap:6px;padding:5px 11px;background:#0d1219;border:1px solid #1a2030;border-radius:6px;font-size:11px;color:#8892a4;transition:all .2s;cursor:default}
.chip:hover{background:#131c28;border-color:#00ff8840;color:#f0f4ff;transform:translateY(-2px)}
.chip img{width:13px;height:13px}

.terminal{background:#060910;border:1px solid #1a2030;border-radius:10px;overflow:hidden;animation:fadeUp .5s ease both .5s}
.term-bar{display:flex;align-items:center;gap:6px;padding:8px 12px;background:#0d1219;border-bottom:1px solid #1a2030}
.tb{width:10px;height:10px;border-radius:50%}
.tb1{background:#ff5f57}.tb2{background:#febc2e}.tb3{background:#28c840}
.term-title{font-size:10px;color:#3a4a60;margin:0 auto;letter-spacing:1px}
.term-body{padding:14px 16px}
.tl{font-size:11px;color:#5a6a80;line-height:2;display:flex;align-items:center;gap:8px}
.tl .p{color:#00ff88}.tl .c{color:#c0d4ff}.tl .s{color:#00cfff}.tl .x{color:#ff6b6b}
.cursor-blink{display:inline-block;width:7px;height:13px;background:#c0d4ff;animation:blink 1s step-end infinite;vertical-align:middle;margin-left:2px}

.right-col{animation:fadeUp .5s ease both .3s}

.profile-card{background:#0d1219;border:1px solid #1a2030;border-radius:14px;overflow:hidden;margin-bottom:14px}
.profile-banner{height:60px;background:linear-gradient(135deg,#001a0d,#001a2a,#0d0020);position:relative;overflow:hidden}
.profile-banner-grid{position:absolute;inset:0;background-image:linear-gradient(rgba(0,255,136,.06) 1px,transparent 1px),linear-gradient(90deg,rgba(0,255,136,.06) 1px,transparent 1px);background-size:20px 20px}

.profile-avatar-wrap{position:relative;width:64px;height:64px;margin:-32px 0 0 20px}
.av-ring{position:absolute;inset:-3px;border-radius:50%;background:conic-gradient(from 0deg,#00ff88,#00cfff,#7c3aed,#00ff88);animation:spin 4s linear infinite}
@keyframes spin{to{transform:rotate(360deg)}}
.av-inner{position:absolute;inset:2px;border-radius:50%;background:linear-gradient(135deg,#001a10,#000d1a);display:flex;align-items:center;justify-content:center}
.av-text{font-family:'Unbounded',sans-serif;font-weight:900;font-size:16px;letter-spacing:-1px;background:linear-gradient(135deg,#00ff88,#00cfff);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}

.profile-info{padding:10px 20px 18px}
.pname{font-family:'Unbounded',sans-serif;font-weight:900;font-size:13px;letter-spacing:-0.5px;color:#f0f4ff;margin-top:8px;line-height:1.4}
.phandle{font-size:11px;color:#3a4a60;margin-top:2px}
.pbio{font-size:11px;color:#5a6a80;margin-top:8px;line-height:1.7}
.status-pill{display:inline-flex;align-items:center;gap:6px;padding:4px 10px;background:rgba(0,255,136,.07);border:1px solid rgba(0,255,136,.2);border-radius:99px;font-size:10px;color:#00ff88;margin-top:10px}
.sdot{width:5px;height:5px;border-radius:50%;background:#00ff88;animation:blink 1.4s step-end infinite}

.links-col{display:flex;flex-direction:column;gap:8px;margin-bottom:14px}
.link-card{display:flex;align-items:center;gap:10px;padding:10px 14px;background:#0d1219;border:1px solid #1a2030;border-radius:10px;text-decoration:none;transition:all .2s}
.link-card:hover{border-color:#00ff8840;background:#131c28;transform:translateX(3px)}
.link-icon{width:28px;height:28px;border-radius:8px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.link-title{font-size:12px;color:#c0d4ff;font-weight:500}
.link-sub{font-size:10px;color:#3a4a60}
.link-arr{font-size:12px;color:#3a4a60}

.contrib-wrap{background:#0d1219;border:1px solid #1a2030;border-radius:12px;padding:14px;margin-bottom:14px}
.contrib-grid{display:grid;grid-template-columns:repeat(13,1fr);gap:3px;margin-top:10px}
.cc{aspect-ratio:1;border-radius:2px;background:#0d1219;border:1px solid #1a2030}
.cc.l1{background:#003d1f;border-color:#004d27}.cc.l2{background:#007a3d;border-color:#009a50}.cc.l3{background:#00b85c;border-color:#00d66a}.cc.l4{background:#00ff88;border-color:#00ff88}

.lang-row{display:flex;flex-direction:column;gap:8px;background:#0d1219;border:1px solid #1a2030;border-radius:12px;padding:14px}
.lang-item{display:flex;flex-direction:column;gap:4px}
.lang-top{display:flex;justify-content:space-between;font-size:10px;color:#5a6a80}
.lang-top b{color:#8892a4}
.lang-bar-bg{height:3px;background:#1a2030;border-radius:99px;overflow:hidden}
.lang-bar{height:100%;border-radius:99px;width:0;transition:width 1.4s cubic-bezier(.23,1,.32,1)}

.xp-row{margin-bottom:1.75rem;animation:fadeUp .5s ease both .45s}
.xp-top{display:flex;justify-content:space-between;align-items:center;margin-bottom:6px}
.xp-label{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:#00ff88;opacity:.8}
.xp-val{font-size:10px;color:#5a6a80}
.xp-bg{height:6px;background:#0d1219;border:1px solid #1a2030;border-radius:99px;overflow:hidden}
.xp-fill{height:100%;width:0;border-radius:99px;background:linear-gradient(90deg,#00ff88,#00cfff);transition:width 1.6s cubic-bezier(.23,1,.32,1)}
</style>

<div class="root">
  <div class="noise"></div>
  <div class="scan-lines"></div>

  <div class="hero">
    <div class="hero-left">
      <div class="tag"><span class="tag-dot"></span>available for collab</div>
      <div class="hero-name">
        Priyanshu
        <span>Kandari</span>
      </div>
      <div class="hero-sub">Full Stack Dev &nbsp;·&nbsp; <b>100x in progress</b> &nbsp;·&nbsp; Music + Code</div>
    </div>
    <div class="hero-right">
      <img class="gif-frame" src="https://raw.githubusercontent.com/himanshukandari14/himanshukandari14/main/get.gif" alt="coding gif" onerror="this.style.display='none';this.parentNode.style.background='linear-gradient(135deg,#001a0d,#00080f)'" />
      <div class="gif-overlay"></div>
    </div>
  </div>

  <div class="divider"></div>

  <div class="body">
    <div>
      <div class="section-label">// stats</div>
      <div class="stat-row">
        <div class="stat"><div class="stat-n" id="s1">0<span>+</span></div><div class="stat-l">Projects</div></div>
        <div class="stat"><div class="stat-n" id="s2">0<span>+</span></div><div class="stat-l">Commits</div></div>
        <div class="stat"><div class="stat-n" id="s3">0<span>+</span></div><div class="stat-l">Skills</div></div>
      </div>

      <div class="xp-row">
        <div class="xp-top"><span class="xp-label">100x dev progress</span><span class="xp-val" id="xpv">0 / 100</span></div>
        <div class="xp-bg"><div class="xp-fill" id="xpf"></div></div>
      </div>

      <div class="section-label">// tech stack</div>
      <div class="stack-grid" id="chips"></div>

      <div style="margin-top:1.75rem">
        <div class="terminal">
          <div class="term-bar">
            <div class="tb tb1"></div><div class="tb tb2"></div><div class="tb tb3"></div>
            <span class="term-title">bash — priyanshu@100x</span>
          </div>
          <div class="term-body">
            <div class="tl"><span class="p">~$</span><span class="c">whoami</span></div>
            <div class="tl" style="color:#8892a4;padding-left:20px">Priyanshu Kandari · Full Stack Developer</div>
            <div class="tl"><span class="p">~$</span><span class="c">cat</span><span class="s">mission.txt</span></div>
            <div class="tl" style="color:#8892a4;padding-left:20px">Ship fast. Think deep. Become 100x.</div>
            <div class="tl"><span class="p">~$</span><span class="c">echo</span><span class="s">$HOBBY</span></div>
            <div class="tl" style="color:#8892a4;padding-left:20px">Music &gt; Silence (always)</div>
            <div class="tl"><span class="p">~$</span><span class="c">npm run</span><span class="x">build</span></div>
            <div class="tl" style="color:#00ff88;padding-left:20px">✓ compiled in 42ms<span class="cursor-blink"></span></div>
          </div>
        </div>
      </div>
    </div>

    <div class="right-col">
      <div class="profile-card">
        <div class="profile-banner"><div class="profile-banner-grid"></div></div>
        <div class="profile-info">
          <div class="profile-avatar-wrap">
            <div class="av-ring"></div>
            <div class="av-inner"><span class="av-text">PK</span></div>
          </div>
          <div class="pname">Priyanshu Kandari</div>
          <div class="phandle">@himanshukandari14</div>
          <div class="pbio">Full Stack Dev on the road to 100x · MERN Stack · Loves music as much as clean code.</div>
          <div class="status-pill"><span class="sdot"></span>Learning · Building · Shipping</div>
        </div>
      </div>

      <div class="links-col">
        <a class="link-card" href="https://in.linkedin.com/in/priyanshu-kandari-424b03353" target="_blank">
          <div class="link-icon" style="background:rgba(10,102,194,.15)">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="#0a66c2"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
          </div>
          <div class="link-text"><div class="link-title">LinkedIn</div><div class="link-sub">priyanshu-kandari</div></div>
          <span class="link-arr">→</span>
        </a>
        <a class="link-card" href="mailto:preyanshukandari@gmail.com">
          <div class="link-icon" style="background:rgba(234,67,53,.12)">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#ea4335" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          </div>
          <div class="link-text"><div class="link-title">Gmail</div><div class="link-sub">preyanshukandari@gmail.com</div></div>
          <span class="link-arr">→</span>
        </a>
      </div>

      <div class="section-label">// languages</div>
      <div class="lang-row" style="margin-bottom:14px">
        <div class="lang-item"><div class="lang-top"><b>JavaScript</b><span>68%</span></div><div class="lang-bar-bg"><div class="lang-bar" id="lb1" style="background:#f7df1e"></div></div></div>
        <div class="lang-item"><div class="lang-top"><b>CSS</b><span>16%</span></div><div class="lang-bar-bg"><div class="lang-bar" id="lb2" style="background:#264de4"></div></div></div>
        <div class="lang-item"><div class="lang-top"><b>HTML</b><span>10%</span></div><div class="lang-bar-bg"><div class="lang-bar" id="lb3" style="background:#e34c26"></div></div></div>
        <div class="lang-item"><div class="lang-top"><b>Other</b><span>6%</span></div><div class="lang-bar-bg"><div class="lang-bar" id="lb4" style="background:#5a6a80"></div></div></div>
      </div>

      <div class="section-label">// contributions</div>
      <div class="contrib-wrap">
        <div class="contrib-grid" id="cgrid"></div>
      </div>
    </div>
  </div>
</div>

<script>
const techs=[
  {n:'HTML5',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg'},
  {n:'CSS3',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg'},
  {n:'Tailwind',i:'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/tailwindcss/tailwindcss-original.svg'},
  {n:'JavaScript',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg'},
  {n:'React',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg'},
  {n:'Redux',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/redux/redux-original.svg'},
  {n:'Node.js',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg'},
  {n:'Express',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg'},
  {n:'MongoDB',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg'},
  {n:'Git',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg'},
  {n:'VSCode',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg'},
  {n:'Vercel',i:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vercel/vercel-original.svg'},
];
const cg=document.getElementById('chips');
techs.forEach(t=>{
  const d=document.createElement('div');
  d.className='chip';
  d.innerHTML=`<img src="${t.i}" alt="${t.n}">${t.n}`;
  cg.appendChild(d);
});

const lvls=[0,1,0,2,0,3,1,0,2,0,1,3,2,0,1,4,0,3,1,2,0,1,3,0,0,2,1,0,3,4,1,2,0,1,2,3,1,4,2,0,3,1,0,2,1,3,0,2,3,1,0,2,4,1,3,0,2,1,0,3,2,0,1,3,2,0,4,1,2,0,3,1,0,2,3,1,0,4,2,1,3,0,1,2,1,0,3,2,1,4,0,3,2,1,0,2,2,3,0,1,4,2,0,3,1,2,0,1,3,0,2,1,0,3,1,0,2,4,1,3,0,2,0,1,3,2,4,0,1,2,3,1,0,2,2,0,1,3,0,2,1,4,0,3,2,1,0,1,2,3,0,1,4,2,1,0,3,2,1,0,2,1,3,0,2,4,1,3];
const cgrid=document.getElementById('cgrid');
lvls.forEach(l=>{
  const c=document.createElement('div');
  c.className='cc'+(l?' l'+l:'');
  cgrid.appendChild(c);
});

function countUp(el,target,dur){
  const start=performance.now();
  function step(now){
    const p=Math.min((now-start)/dur,1);
    const v=Math.round((1-Math.pow(1-p,3))*target);
    el.innerHTML=v+'<span>+</span>';
    if(p<1)requestAnimationFrame(step);
  }
  requestAnimationFrame(step);
}

setTimeout(()=>{
  countUp(document.getElementById('s1'),24,1200);
  countUp(document.getElementById('s2'),312,1500);
  countUp(document.getElementById('s3'),10,1000);
  document.getElementById('xpf').style.width='67%';
  document.getElementById('xpv').textContent='67 / 100';
  document.getElementById('lb1').style.width='68%';
  document.getElementById('lb2').style.width='16%';
  document.getElementById('lb3').style.width='10%';
  document.getElementById('lb4').style.width='6%';
},400);
</script>

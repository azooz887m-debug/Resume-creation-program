# Resume-creation-program
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>سيرتك علينا — بناء السيرة الذاتية مجاناً</title>
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;900&family=Amiri:wght@400;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#f0f4f8;--bg2:#fff;--bg3:#e8eef5;--card:#fff;
  --ink:#1a2332;--ink2:#3d5166;--ink3:#6b8299;
  --ac:#1a6b8a;--ac2:#2a9fc5;--ac3:#e8f4f8;
  --gold:#c8922a;--gr:#1a7a4a;--gr2:#d4f0e4;
  --bd:rgba(26,107,138,.15);--sh:rgba(26,51,82,.1);--sh2:rgba(26,51,82,.2);
}
[data-dark]{
  --bg:#0e1621;--bg2:#162030;--bg3:#1c2a3a;--card:#1c2a3a;
  --ink:#e8f0f8;--ink2:#a8c4d8;--ink3:#6a8aa0;
  --ac:#2ab0e0;--ac2:#45c8f5;--ac3:#1a3040;
  --gold:#e8b84b;--gr:#2ab870;--gr2:#1a3028;
  --bd:rgba(42,176,224,.18);--sh:rgba(0,0,0,.3);--sh2:rgba(0,0,0,.45);
}
*{margin:0;padding:0;box-sizing:border-box;}
body{font-family:"Tajawal",sans-serif;background:var(--bg);color:var(--ink);min-height:100vh;overflow-x:hidden;transition:background .25s,color .25s;}

/* ── NAV ── */
.topbar{background:var(--ac);color:#fff;text-align:center;padding:.4rem 1rem;font-size:.82rem;}
.topbar a{color:#ffe;text-decoration:none;}
nav{position:sticky;top:0;z-index:200;background:var(--bg2);border-bottom:2px solid var(--bd);box-shadow:0 2px 16px var(--sh);padding:0 2rem;}
.navi{max-width:1200px;margin:0 auto;height:64px;display:flex;align-items:center;justify-content:space-between;}
.logo{font-family:"Amiri",serif;font-size:1.65rem;font-weight:700;color:var(--ac);display:flex;align-items:center;gap:8px;cursor:pointer;}
.logo small{font-size:.68rem;color:var(--ink3);font-family:"Tajawal",sans-serif;display:block;margin-top:-4px;}
.navl{display:flex;gap:.2rem;list-style:none;}
.navl a{display:block;padding:.4rem .9rem;color:var(--ink2);text-decoration:none;font-size:.9rem;font-weight:500;border-radius:6px;cursor:pointer;transition:background .15s,color .15s;}
.navl a:hover,.navl a.on{background:var(--ac3);color:var(--ac);}
.navr{display:flex;align-items:center;gap:.8rem;}
.dbtn{background:var(--bg3);border:1px solid var(--bd);border-radius:20px;padding:.35rem .9rem;cursor:pointer;font-size:.84rem;color:var(--ink2);font-family:"Tajawal",sans-serif;display:flex;align-items:center;gap:5px;}
.mbtn{background:var(--ac);color:#fff;border:none;padding:.45rem 1rem;border-radius:8px;font-family:"Tajawal",sans-serif;font-weight:700;font-size:.85rem;cursor:pointer;text-decoration:none;display:flex;align-items:center;gap:5px;white-space:nowrap;}
.mbtn:hover{background:var(--ac2);}

/* ── SETTINGS BAR ── */
.sbar{background:var(--bg2);border-bottom:1px solid var(--bd);padding:.5rem 2rem;position:sticky;top:64px;z-index:150;}
.sbar-in{max-width:1200px;margin:0 auto;display:flex;align-items:center;gap:1rem;flex-wrap:wrap;}
.stog{display:flex;align-items:center;gap:.5rem;font-size:.84rem;color:var(--ink2);font-weight:600;cursor:pointer;user-select:none;}
.stog input{display:none;}
.stgl{width:40px;height:21px;background:var(--bd);border-radius:100px;position:relative;transition:background .2s;flex-shrink:0;}
.stgl::after{content:"";position:absolute;width:15px;height:15px;background:#fff;border-radius:50%;top:3px;right:3px;transition:transform .2s;box-shadow:0 1px 4px rgba(0,0,0,.2);}
.stog input:checked + .stgl{background:var(--ac);}
.stog input:checked + .stgl::after{transform:translateX(-19px);}
.sbsep{width:1px;height:20px;background:var(--bd);}
.exbtn{background:var(--bg3);border:1px solid var(--bd);color:var(--ink2);padding:.35rem .85rem;border-radius:6px;font-family:"Tajawal",sans-serif;font-size:.8rem;cursor:pointer;transition:background .15s;}
.exbtn:hover{background:var(--ac3);color:var(--ac);}

/* ── PAGES ── */
.pg{display:none;}.pg.on{display:block;animation:fu .35s ease;}
@keyframes fu{from{opacity:0;transform:translateY(14px)}to{opacity:1;transform:translateY(0)}}

/* ── HERO ── */
.hero{background:linear-gradient(135deg,var(--ac) 0%,#0d4a6b 65%,#0a3550 100%);padding:5rem 2rem 4rem;text-align:center;position:relative;overflow:hidden;}
.hero::before{content:"";position:absolute;inset:0;opacity:.05;background-image:repeating-linear-gradient(45deg,#fff 0,#fff 1px,transparent 0,transparent 50%);background-size:20px 20px;}
.hbadge{display:inline-block;background:rgba(255,255,255,.15);color:#fff;border:1px solid rgba(255,255,255,.3);padding:.3rem 1rem;border-radius:100px;font-size:.8rem;margin-bottom:1.5rem;}
.hero h1{font-family:"Amiri",serif;font-size:clamp(2.2rem,5vw,3.8rem);color:#fff;font-weight:700;line-height:1.25;margin-bottom:1rem;}
.hero h1 em{color:var(--gold);font-style:normal;}
.hero p{color:rgba(255,255,255,.85);font-size:1.05rem;max-width:600px;margin:0 auto 2.5rem;line-height:1.8;font-weight:300;}
.hbtns{display:flex;gap:1rem;justify-content:center;flex-wrap:wrap;}
.bw{background:#fff;color:var(--ac);border:none;padding:.8rem 2rem;border-radius:8px;font-family:"Tajawal",sans-serif;font-weight:700;font-size:1rem;cursor:pointer;box-shadow:0 4px 20px rgba(0,0,0,.2);transition:transform .15s,box-shadow .15s;}
.bw:hover{transform:translateY(-2px);box-shadow:0 8px 28px rgba(0,0,0,.25);}
.bgb{background:transparent;color:#fff;border:2px solid rgba(255,255,255,.4);padding:.8rem 2rem;border-radius:8px;font-family:"Tajawal",sans-serif;font-size:1rem;cursor:pointer;transition:border-color .2s;}
.bgb:hover{border-color:#fff;}
.hstats{display:flex;justify-content:center;gap:3rem;margin-top:3rem;flex-wrap:wrap;}
.hst .n{font-family:"Amiri",serif;font-size:2.2rem;font-weight:700;color:var(--gold);}
.hst .l{font-size:.82rem;color:rgba(255,255,255,.7);}

/* ── SECTION ── */
.sec{max-width:1200px;margin:0 auto;padding:3rem 2rem;}
.sech{text-align:center;margin-bottom:2.5rem;}
.sech h2{font-family:"Amiri",serif;font-size:2rem;font-weight:700;color:var(--ink);margin-bottom:.5rem;}
.sech p{color:var(--ink3);font-size:1rem;}
.badge{display:inline-block;background:var(--ac3);color:var(--ac);border:1px solid var(--bd);padding:.22rem .9rem;border-radius:100px;font-size:.74rem;font-weight:700;margin-bottom:.8rem;}
.ctabar{background:var(--ac);padding:3rem 2rem;text-align:center;}
.ctabar h2{font-family:"Amiri",serif;color:#fff;font-size:2rem;margin-bottom:1.5rem;}
.steps{display:grid;grid-template-columns:repeat(4,1fr);gap:1.4rem;}
.step{background:var(--card);border:1px solid var(--bd);border-radius:12px;padding:1.4rem;text-align:center;box-shadow:0 2px 10px var(--sh);position:relative;}
.snum{width:42px;height:42px;background:var(--ac);color:#fff;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1.1rem;font-weight:700;margin:0 auto .9rem;font-family:"Amiri",serif;}
.step h3{font-size:.98rem;font-weight:700;color:var(--ink);margin-bottom:.4rem;}
.step p{font-size:.82rem;color:var(--ink3);line-height:1.6;}
.sarr{position:absolute;left:-13px;top:50%;transform:translateY(-50%);color:var(--ac);font-size:1.2rem;}
.feats{display:grid;grid-template-columns:repeat(3,1fr);gap:1.2rem;}
.feat{background:var(--card);border:1px solid var(--bd);border-radius:12px;padding:1.3rem;box-shadow:0 2px 10px var(--sh);display:flex;gap:.9rem;align-items:flex-start;}
.fico{width:44px;height:44px;border-radius:10px;background:var(--ac3);display:flex;align-items:center;justify-content:center;font-size:1.3rem;flex-shrink:0;}
.feat h3{font-size:.97rem;font-weight:700;color:var(--ink);margin-bottom:.3rem;}
.feat p{font-size:.82rem;color:var(--ink3);line-height:1.6;}

/* ── BUILDER ── */
.builder{display:grid;grid-template-columns:1fr 1fr;gap:2rem;align-items:start;}
.fbox{background:var(--card);border:1px solid var(--bd);border-radius:14px;padding:2rem;box-shadow:0 4px 20px var(--sh);}
.fbox h2{font-family:"Amiri",serif;font-size:1.55rem;color:var(--ink);margin-bottom:.5rem;}
.prog-wrap{margin-bottom:1.2rem;}
.prog-label{display:flex;justify-content:space-between;font-size:.8rem;color:var(--ink3);margin-bottom:.35rem;}
.prog-label strong{color:var(--ink);font-weight:700;}
.prog-bar{height:6px;background:var(--bg3);border-radius:100px;overflow:hidden;}
.prog-fill{height:100%;background:linear-gradient(90deg,var(--ac),var(--ac2));border-radius:100px;transition:width .4s ease;}
.prog-tips{display:flex;gap:.35rem;flex-wrap:wrap;margin-top:.4rem;}
.ptip{font-size:.7rem;padding:.15rem .55rem;border-radius:100px;border:1px solid var(--bd);color:var(--ink3);background:var(--bg3);}
.ptip.done{background:var(--gr2);color:var(--gr);border-color:rgba(26,122,74,.2);}
.fg{margin-bottom:1.1rem;}
.fg label{display:block;font-size:.85rem;font-weight:600;color:var(--ink2);margin-bottom:.32rem;}
.fg input,.fg textarea{width:100%;background:var(--bg3);border:1.5px solid var(--bd);color:var(--ink);padding:.63rem .9rem;border-radius:8px;font-family:"Tajawal",sans-serif;font-size:.9rem;outline:none;transition:border-color .2s;}
.fg input:focus,.fg textarea:focus{border-color:var(--ac);}
.fg textarea{resize:vertical;min-height:82px;}
.fg2{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
.gbtn{width:100%;background:var(--ac);color:#fff;border:none;padding:1rem;border-radius:10px;font-family:"Tajawal",sans-serif;font-weight:700;font-size:1rem;cursor:pointer;transition:background .2s,transform .15s;margin-top:.5rem;display:flex;align-items:center;justify-content:center;gap:8px;}
.gbtn:hover{background:var(--ac2);transform:translateY(-1px);}
.gbtn:disabled{opacity:.6;cursor:not-allowed;transform:none;}
.draft-ind{font-size:.72rem;color:var(--gr);display:flex;align-items:center;gap:4px;opacity:0;transition:opacity .3s;margin-bottom:.3rem;}
.draft-ind.on{opacity:1;}

/* ── AI MODE ── */
.ai-box{background:linear-gradient(135deg,var(--ac3),var(--bg3));border:2px solid var(--ac);border-radius:14px;padding:1.6rem;margin-bottom:1.3rem;display:none;}
.ai-box.on{display:block;}
.ai-box h3{font-family:"Amiri",serif;font-size:1.25rem;color:var(--ink);margin-bottom:.4rem;}
.ai-box p{font-size:.83rem;color:var(--ink3);margin-bottom:.9rem;line-height:1.6;}
.ai-ta{width:100%;background:var(--bg2);border:1.5px solid var(--bd);color:var(--ink);padding:.8rem 1rem;border-radius:8px;font-family:"Tajawal",sans-serif;font-size:.9rem;outline:none;resize:vertical;min-height:110px;line-height:1.7;}
.ai-ta:focus{border-color:var(--ac);}
.ai-gbtn{width:100%;background:var(--ac);color:#fff;border:none;padding:.9rem;border-radius:10px;font-family:"Tajawal",sans-serif;font-weight:700;font-size:1rem;cursor:pointer;margin-top:.8rem;display:flex;align-items:center;justify-content:center;gap:8px;transition:background .2s;}
.ai-gbtn:hover{background:var(--ac2);}
.ai-gbtn:disabled{opacity:.6;cursor:not-allowed;}
.mwrap.hidden{display:none;}

/* ── PROJECTS ── */
.projbox{border:2px dashed var(--bd);border-radius:12px;padding:1.1rem;margin-bottom:1.1rem;background:var(--bg3);}
.projbox-h{display:flex;align-items:center;justify-content:space-between;margin-bottom:.7rem;}
.projbox-h h4{font-size:.9rem;font-weight:700;color:var(--ink);}
.projbox-h small{font-size:.72rem;color:var(--ink3);display:block;margin-top:2px;}
.abtn{background:var(--ac);color:#fff;border:none;padding:.38rem .9rem;border-radius:7px;font-family:"Tajawal",sans-serif;font-weight:700;font-size:.83rem;cursor:pointer;}
.prji{background:var(--bg2);border:1px solid var(--bd);border-radius:8px;padding:.9rem .9rem .9rem 2.2rem;margin-bottom:.65rem;position:relative;}
.prjdel{position:absolute;top:.5rem;left:.5rem;background:rgba(155,58,26,.12);color:#9b3a1a;border:none;width:24px;height:24px;border-radius:50%;cursor:pointer;font-size:.85rem;display:flex;align-items:center;justify-content:center;}
.prjrow{display:flex;gap:.45rem;margin-bottom:.5rem;flex-wrap:wrap;}
.prji input,.prji textarea{background:var(--bg3);border:1.5px solid var(--bd);color:var(--ink);border-radius:6px;font-family:"Tajawal",sans-serif;font-size:.86rem;outline:none;padding:.46rem .72rem;transition:border-color .2s;width:100%;}
.prji input:focus,.prji textarea:focus{border-color:var(--ac);}
.prji .pname,.prji .ptech{flex:1;min-width:100px;width:auto;}
.prji .purl{direction:ltr;text-align:left;color:var(--ac);}

/* ── CUSTOM SECTIONS ── */
.csdbox{border:2px dashed var(--bd);border-radius:12px;padding:1.1rem;margin-bottom:1.1rem;background:var(--bg3);}
.csdbox-h{display:flex;align-items:center;justify-content:space-between;margin-bottom:.7rem;}
.csi{background:var(--bg2);border:1px solid var(--bd);border-radius:8px;padding:.9rem .9rem .9rem 2.2rem;margin-bottom:.65rem;position:relative;}
.csd2{position:absolute;top:.5rem;left:.5rem;background:rgba(155,58,26,.12);color:#9b3a1a;border:none;width:24px;height:24px;border-radius:50%;cursor:pointer;font-size:.85rem;display:flex;align-items:center;justify-content:center;}
.csrow{display:flex;gap:.45rem;margin-bottom:.5rem;}
.csinp{flex:1;background:var(--bg3);border:1.5px solid var(--bd);color:var(--ink);padding:.46rem .72rem;border-radius:6px;font-family:"Tajawal",sans-serif;font-size:.85rem;outline:none;}
.csinp:focus{border-color:var(--ac);}
.cssel{background:var(--bg3);border:1.5px solid var(--bd);color:var(--ink3);padding:.46rem .5rem;border-radius:6px;font-family:"Tajawal",sans-serif;font-size:.8rem;outline:none;cursor:pointer;}
.csta{width:100%;background:var(--bg3);border:1.5px solid var(--bd);color:var(--ink);padding:.46rem .72rem;border-radius:6px;font-family:"Tajawal",sans-serif;font-size:.85rem;outline:none;resize:vertical;min-height:55px;}
.csta:focus{border-color:var(--ac);}

/* ── SECTIONS ORDER ── */
.ord-panel{border:2px solid var(--bd);border-radius:14px;padding:1.3rem;margin-bottom:1.2rem;background:var(--bg3);}
.ord-top{display:flex;align-items:flex-start;justify-content:space-between;gap:1rem;margin-bottom:1rem;flex-wrap:wrap;}
.ord-top-left h4{font-size:.95rem;font-weight:700;color:var(--ink);margin-bottom:.18rem;}
.ord-top-left small{font-size:.72rem;color:var(--ink3);}
.ats-score-wrap{display:flex;align-items:center;gap:.6rem;background:var(--bg2);border:1px solid var(--bd);border-radius:8px;padding:.4rem .8rem;}
.ats-score-label{font-size:.72rem;color:var(--ink3);font-weight:600;}
.ats-score-val{font-size:1.1rem;font-weight:900;}
.ats-score-txt{font-size:.72rem;font-weight:700;}
.c-green{color:#1a7a4a;}.c-amber{color:#b36200;}.c-red{color:#9b3a1a;}
.ord-presets{display:flex;gap:.5rem;margin-bottom:.9rem;flex-wrap:wrap;}
.ord-preset-btn{background:var(--bg2);border:1px solid var(--bd);color:var(--ink2);padding:.35rem .85rem;border-radius:100px;font-family:"Tajawal",sans-serif;font-size:.78rem;cursor:pointer;transition:all .15s;font-weight:600;}
.ord-preset-btn:hover,.ord-preset-btn.active{background:var(--ac);color:#fff;border-color:var(--ac);}
.ord-list{display:flex;flex-direction:column;gap:.45rem;}
.ord-item{background:var(--bg2);border:1.5px solid var(--bd);border-radius:10px;padding:.6rem .9rem;display:flex;align-items:center;gap:.65rem;cursor:grab;user-select:none;transition:box-shadow .15s,border-color .15s;}
.ord-item:active{cursor:grabbing;box-shadow:0 4px 16px var(--sh2);}
.ord-item.drag-over{border-color:var(--ac);background:var(--ac3);}
.ord-item.dragging{opacity:.4;}
.ord-item.hidden-sec{opacity:.5;background:var(--bg3);}
.ord-handle{color:var(--ink3);font-size:1.1rem;flex-shrink:0;}
.ord-icon{font-size:1rem;flex-shrink:0;width:22px;text-align:center;}
.ord-info{flex:1;}
.ord-name{font-size:.86rem;font-weight:700;color:var(--ink);}
.ord-hint{font-size:.7rem;color:var(--ink3);margin-top:1px;}
.ord-badges{display:flex;gap:.4rem;align-items:center;flex-shrink:0;}
.ord-ats-tag{font-size:.62rem;font-weight:700;padding:.15rem .5rem;border-radius:100px;}
.tag-must{background:rgba(26,122,74,.12);color:#1a7a4a;border:1px solid rgba(26,122,74,.2);}
.tag-warn{background:rgba(179,98,0,.12);color:#b36200;border:1px solid rgba(179,98,0,.2);}
.tag-free{background:rgba(26,107,138,.1);color:var(--ac);border:1px solid rgba(26,107,138,.15);}
.ord-toggle{background:none;border:1px solid var(--bd);border-radius:5px;padding:.18rem .52rem;font-family:"Tajawal",sans-serif;font-size:.72rem;color:var(--ink3);cursor:pointer;transition:all .15s;}
.ord-toggle.off{background:rgba(155,58,26,.08);color:#9b3a1a;border-color:rgba(155,58,26,.2);}
.ord-toggle:hover{background:var(--ac3);color:var(--ac);border-color:var(--ac);}
.ats-warn-box{display:none;background:rgba(179,98,0,.08);border:1px solid rgba(179,98,0,.25);border-radius:8px;padding:.65rem .9rem;margin-top:.7rem;font-size:.78rem;color:#7a4400;line-height:1.6;}
.ats-warn-box.on{display:block;}
.ord-reset-btn{background:none;border:1px solid var(--bd);color:var(--ink3);padding:.3rem .75rem;border-radius:6px;font-family:"Tajawal",sans-serif;font-size:.76rem;cursor:pointer;transition:all .15s;}
.ord-reset-btn:hover{background:var(--ac3);color:var(--ac);border-color:var(--ac);}

/* ── CV OUTPUT ── */
.cvout{background:var(--card);border:1px solid var(--bd);border-radius:14px;padding:1.4rem;box-shadow:0 4px 20px var(--sh);}
.cvouth{display:flex;align-items:center;justify-content:space-between;margin-bottom:.9rem;}
.cvouth h2{font-family:"Amiri",serif;font-size:1.25rem;color:var(--ink);}
.atsbadge{background:var(--gr2);color:var(--gr);border:1px solid rgba(26,122,74,.2);font-size:.68rem;font-weight:700;padding:.2rem .75rem;border-radius:100px;}
.cvacts{display:flex;gap:.55rem;flex-wrap:wrap;margin-bottom:.9rem;}
.cvact{background:var(--bg3);border:1px solid var(--bd);color:var(--ink2);padding:.38rem .8rem;border-radius:6px;font-family:"Tajawal",sans-serif;font-size:.8rem;cursor:pointer;transition:background .15s;}
.cvact:hover{background:var(--ac3);color:var(--ac);}
.cvact.pr{background:var(--ac);color:#fff;border-color:var(--ac);}
.cvact.pr:hover{background:var(--ac2);}

/* ── CV PAPER ── */
#cvp{background:#fff;color:#111;border:1px solid #ddd;border-radius:4px;min-height:460px;font-family:"Tajawal",sans-serif;direction:rtl;box-shadow:0 2px 14px rgba(0,0,0,.1);overflow:hidden;}
.cvempty{display:flex;flex-direction:column;align-items:center;justify-content:center;min-height:420px;color:#aaa;text-align:center;padding:2rem;}
.cvempty .ico{font-size:4rem;margin-bottom:1rem;opacity:.35;}

/* CV Template 1 */
.t1{padding:2rem;}
.t1 .ch{border-bottom:3px solid #1a6b8a;padding-bottom:.9rem;margin-bottom:.9rem;}
.t1 .cn{font-size:1.65rem;font-weight:900;color:#1a2332;}
.t1 .ct{font-size:.9rem;color:#1a6b8a;font-weight:600;margin:.18rem 0;}
.t1 .cc{font-size:.78rem;color:#555;margin-top:.35rem;display:flex;gap:.9rem;flex-wrap:wrap;}
.cvs{font-size:.88rem;font-weight:800;color:#1a6b8a;text-transform:uppercase;letter-spacing:1px;border-bottom:1.5px solid #ddd;padding-bottom:.22rem;margin:.9rem 0 .45rem;}
.cvb{font-size:.84rem;color:#333;line-height:1.7;}
/* CV Template 2 */
.t2{width:100%;overflow:hidden;}
.t2s{background:#1a2332;color:#fff;padding:1.5rem 1rem;width:185px;float:right;min-height:500px;box-sizing:border-box;}
.t2m-wrap{margin-right:185px;}
.t2s .cn{font-size:1.15rem;font-weight:900;color:#fff;margin-bottom:.18rem;}
.t2s .ct{font-size:.76rem;color:#2ab0e0;margin-bottom:.9rem;}
.t2si{margin-bottom:.9rem;}
.t2si .lb{font-size:.66rem;font-weight:700;color:#2ab0e0;text-transform:uppercase;letter-spacing:1px;border-bottom:1px solid rgba(255,255,255,.15);padding-bottom:.22rem;margin-bottom:.35rem;}
.t2si .vl{font-size:.74rem;color:rgba(255,255,255,.8);line-height:1.6;}
.t2m{padding:1.5rem;overflow:hidden;}
.t2m .cvs{color:#1a2332;border-bottom-color:#1a6b8a;border-bottom-width:2px;}
.t2m .cvb{font-size:.82rem;}
/* CV Template 3 */
.t3{padding:2rem;}
.t3 .bar{width:52px;height:2px;background:#111;margin-bottom:.75rem;}
.t3 .cn{font-size:1.8rem;font-weight:900;color:#111;letter-spacing:-.5px;}
.t3 .ct{font-size:.88rem;color:#555;margin:.22rem 0 .55rem;}
.t3 .cc{font-size:.78rem;color:#777;display:flex;gap:1.1rem;flex-wrap:wrap;padding-bottom:.65rem;border-bottom:1px solid #eee;margin-bottom:.65rem;}
.t3 .cvs{font-size:.76rem;font-weight:800;color:#111;text-transform:uppercase;letter-spacing:2px;border-bottom:none;margin:.9rem 0 .35rem;}
.t3 .cvb{font-size:.83rem;color:#444;line-height:1.75;}
.sk{display:inline-block;background:#e8f4f8;color:#1a2332;padding:2px 9px;border-radius:3px;font-size:.78rem;margin:2px 2px;}
.prj-cv{margin-bottom:.65rem;padding-bottom:.65rem;border-bottom:1px solid #eee;}
.prj-cv:last-child{border-bottom:none;padding-bottom:0;margin-bottom:0;}
.prj-cv-title{font-weight:700;font-size:.86rem;color:#1a2332;}
.prj-cv-tech{font-size:.76rem;color:#888;}
.prj-cv-desc{font-size:.82rem;color:#444;line-height:1.65;margin:.2rem 0;}
.prj-cv-link{display:inline-block;color:#1a6b8a;font-size:.78rem;word-break:break-all;}

/* ── LOADING ── */
.loading{display:flex;flex-direction:column;align-items:center;justify-content:center;min-height:380px;gap:1rem;}
.spin{width:40px;height:40px;border:3px solid #ddd;border-top-color:#1a6b8a;border-radius:50%;animation:sp .8s linear infinite;}
@keyframes sp{to{transform:rotate(360deg)}}
.loading p{color:#888;font-size:.9rem;}

/* ── TEMPLATES ── */
.tmpls{display:grid;grid-template-columns:repeat(3,1fr);gap:1.3rem;margin-bottom:2rem;}
.tmpl{background:var(--card);border:2px solid var(--bd);border-radius:12px;overflow:hidden;cursor:pointer;transition:border-color .2s,transform .2s,box-shadow .2s;box-shadow:0 2px 10px var(--sh);}
.tmpl:hover{border-color:var(--ac);transform:translateY(-3px);box-shadow:0 8px 22px var(--sh2);}
.tmpl.on{border-color:var(--ac);box-shadow:0 0 0 3px rgba(26,107,138,.18);}
.tprev{height:185px;background:#fff;border-bottom:1px solid var(--bd);overflow:hidden;}
.tprev svg{width:100%;height:100%;}
.tbody{padding:1rem;}
.atag{background:#d4f0e4;color:#1a7a4a;font-size:.66rem;font-weight:700;padding:.18rem .65rem;border-radius:100px;display:inline-block;margin-bottom:.38rem;}
[data-dark] .atag{background:var(--gr2);color:var(--gr);}
.tbody h3{font-size:.97rem;font-weight:700;color:var(--ink);margin-bottom:.22rem;}
.tbody p{font-size:.79rem;color:var(--ink3);}
.tbtn{width:100%;margin-top:.65rem;background:var(--ac3);color:var(--ac);border:1px solid var(--bd);padding:.42rem;border-radius:6px;font-family:"Tajawal",sans-serif;font-weight:700;font-size:.84rem;cursor:pointer;transition:background .15s;}
.tmpl.on .tbtn{background:var(--ac);color:#fff;}

/* ── SHARE BAR ── */
.share-bar{background:var(--ac3);border:1px solid var(--bd);border-radius:10px;padding:.8rem 1rem;margin-top:1rem;display:flex;align-items:center;gap:.8rem;flex-wrap:wrap;}
.share-bar p{font-size:.84rem;color:var(--ink2);flex:1;}
.shr-btn{border:none;padding:.38rem .85rem;border-radius:6px;font-family:"Tajawal",sans-serif;font-weight:700;font-size:.8rem;cursor:pointer;}
.shr-wa{background:#25D366;color:#fff;}
.shr-tw{background:#1DA1F2;color:#fff;}
.shr-cp{background:var(--ac);color:#fff;}

/* ── JOBS PANEL ── */
.jobs-panel{margin-top:1.5rem;display:none;}
.jobs-panel.on{display:block;animation:fu .4s ease;}
.jobs-panel-head{display:flex;align-items:center;justify-content:space-between;margin-bottom:1rem;}
.jobs-panel-head h3{font-family:"Amiri",serif;font-size:1.3rem;color:var(--ink);display:flex;align-items:center;gap:8px;}
.jobs-close-btn{background:none;border:1px solid var(--bd);color:var(--ink3);padding:.25rem .7rem;border-radius:6px;font-family:"Tajawal",sans-serif;font-size:.78rem;cursor:pointer;}
.jobs-close-btn:hover{background:var(--bg3);}
.match-bar{display:flex;align-items:center;gap:.7rem;background:var(--bg3);border-radius:10px;padding:.7rem 1rem;margin-bottom:1rem;}
.match-circle{width:52px;height:52px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1rem;font-weight:900;flex-shrink:0;border:3px solid;}
.mc-high{background:var(--gr2);color:var(--gr);border-color:var(--gr);}
.mc-mid{background:#fff8e1;color:#b36200;border-color:#c8922a;}
.mc-low{background:#fdecea;color:#9b3a1a;border-color:#9b3a1a;}
[data-dark] .mc-mid{background:#2a1f00;color:#e8b84b;}
[data-dark] .mc-low{background:#2a0a08;color:#ff8a80;}
.match-info{flex:1;}
.match-info h4{font-size:.9rem;font-weight:700;color:var(--ink);margin-bottom:.2rem;}
.match-info p{font-size:.78rem;color:var(--ink3);line-height:1.5;}
.jobs-cats{display:flex;gap:.5rem;flex-wrap:wrap;margin-bottom:.9rem;}
.jobs-cat{background:var(--bg3);border:1px solid var(--bd);color:var(--ink2);padding:.32rem .8rem;border-radius:100px;font-family:"Tajawal",sans-serif;font-size:.78rem;cursor:pointer;transition:all .15s;font-weight:600;}
.jobs-cat:hover,.jobs-cat.on{background:var(--ac);color:#fff;border-color:var(--ac);}
.job-grid{display:grid;grid-template-columns:1fr 1fr;gap:.8rem;}
.job-card{background:var(--bg2);border:1.5px solid var(--bd);border-radius:10px;padding:.9rem 1rem;cursor:pointer;transition:border-color .15s,transform .15s,box-shadow .15s;}
.job-card:hover{border-color:var(--ac);transform:translateY(-2px);box-shadow:0 4px 14px var(--sh2);}
.job-card.top-match{border-color:var(--ac);background:var(--ac3);}
.jc-top{display:flex;align-items:flex-start;gap:.6rem;margin-bottom:.5rem;}
.jc-icon{font-size:1.4rem;flex-shrink:0;}
.jc-title{font-size:.9rem;font-weight:700;color:var(--ink);line-height:1.3;}
.jc-comp{font-size:.72rem;color:var(--ink3);margin-top:2px;}
.jc-tags{display:flex;gap:.35rem;flex-wrap:wrap;margin-bottom:.5rem;}
.jt{font-size:.65rem;font-weight:700;padding:.15rem .5rem;border-radius:100px;}
.jt-hi{background:#d4f0e4;color:#1a7a4a;}
.jt-mi{background:#fff8e1;color:#b36200;}
.jt-lo{background:#fdecea;color:#9b3a1a;}
.jt-match{background:var(--ac3);color:var(--ac);}
[data-dark] .jt-hi{background:var(--gr2);color:var(--gr);}
[data-dark] .jt-mi{background:#2a1f00;color:#e8b84b;}
.jc-desc{font-size:.78rem;color:var(--ink3);line-height:1.55;}
.jc-companies{margin:.5rem 0;padding:.4rem .6rem;background:var(--bg3);border-radius:6px;font-size:.72rem;color:var(--ink3);line-height:1.6;}
.jc-footer{display:flex;align-items:center;justify-content:space-between;margin-top:.55rem;padding-top:.55rem;border-top:1px solid var(--bd);}
.jc-keys{font-size:.7rem;color:var(--ink3);}
.jc-apply{font-size:.72rem;font-weight:700;color:var(--ac);background:none;border:none;cursor:pointer;font-family:"Tajawal",sans-serif;padding:0;}
.jc-apply:hover{text-decoration:underline;}
.missing-box{background:rgba(179,98,0,.07);border:1px solid rgba(179,98,0,.2);border-radius:8px;padding:.7rem .9rem;margin-top:.8rem;}
.missing-box h5{font-size:.82rem;font-weight:700;color:#b36200;margin-bottom:.4rem;}
[data-dark] .missing-box{background:rgba(100,70,0,.2);}
[data-dark] .missing-box h5{color:#e8b84b;}
.missing-pills{display:flex;gap:.35rem;flex-wrap:wrap;}
.mpill{font-size:.72rem;background:var(--bg2);border:1px dashed rgba(179,98,0,.3);color:#7a4400;padding:.15rem .6rem;border-radius:100px;}
[data-dark] .mpill{color:#e8b84b;}

/* ── TIPS ── */
.tips{display:grid;grid-template-columns:repeat(3,1fr);gap:1.1rem;margin-bottom:2rem;}
.tip{background:var(--card);border:1px solid var(--bd);border-radius:12px;padding:1.1rem;box-shadow:0 2px 8px var(--sh);}
.tipico{font-size:1.65rem;margin-bottom:.65rem;}
.tiptag{background:var(--ac3);color:var(--ac);font-size:.66rem;font-weight:700;padding:.18rem .65rem;border-radius:100px;display:inline-block;margin-bottom:.38rem;}
.tip h3{font-size:.92rem;font-weight:700;color:var(--ink);margin-bottom:.38rem;}
.tip p{font-size:.8rem;color:var(--ink3);line-height:1.7;}
.jobsbox{background:var(--card);border:1px solid var(--bd);border-radius:12px;padding:1.3rem;box-shadow:0 2px 8px var(--sh);margin-bottom:2rem;}
.jobsbox h2{font-family:"Amiri",serif;font-size:1.4rem;color:var(--ink);margin-bottom:.9rem;}
.jobsg{display:grid;grid-template-columns:repeat(2,1fr);gap:.65rem;}
.jobi{background:var(--bg3);border:1px solid var(--bd);border-radius:8px;padding:.8rem 1rem;display:flex;align-items:center;gap:8px;}
.jdot{width:9px;height:9px;background:var(--gr);border-radius:50%;flex-shrink:0;}
.jobi h4{font-size:.86rem;font-weight:600;color:var(--ink);margin-bottom:1px;}
.jobi span{font-size:.72rem;color:var(--ink3);}

/* ── CHAT ── */
.ailay{display:grid;grid-template-columns:1fr 320px;gap:2rem;align-items:start;}
.chatbox{background:var(--card);border:1px solid var(--bd);border-radius:14px;overflow:hidden;box-shadow:0 4px 20px var(--sh);display:flex;flex-direction:column;height:570px;}
.chathd{background:var(--ac);color:#fff;padding:.9rem 1.3rem;display:flex;align-items:center;gap:9px;}
.chatav{width:34px;height:34px;background:rgba(255,255,255,.2);border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1.1rem;}
.chathd h3{font-size:.92rem;font-weight:700;}
.chathd p{font-size:.7rem;opacity:.8;}
.cdot{width:7px;height:7px;background:#4eff9a;border-radius:50%;animation:pb 2s infinite;}
@keyframes pb{0%,100%{opacity:1}50%{opacity:.3}}
.msgs{flex:1;overflow-y:auto;padding:1rem;display:flex;flex-direction:column;gap:.65rem;}
.msg{max-width:88%;padding:.62rem .9rem;border-radius:10px;font-size:.85rem;line-height:1.65;white-space:pre-line;}
.mai{background:var(--ac3);color:var(--ink);border-radius:10px 10px 10px 2px;}
.mme{background:var(--ac);color:#fff;align-self:flex-end;border-radius:10px 10px 2px 10px;}
.chatinp{border-top:1px solid var(--bd);padding:.85rem;display:flex;gap:.55rem;}
.cinp{flex:1;background:var(--bg3);border:1.5px solid var(--bd);color:var(--ink);padding:.52rem .85rem;border-radius:8px;font-family:"Tajawal",sans-serif;font-size:.88rem;outline:none;}
.cinp:focus{border-color:var(--ac);}
.csend{background:var(--ac);color:#fff;border:none;width:36px;height:36px;border-radius:8px;cursor:pointer;font-size:.95rem;flex-shrink:0;}
.csend:hover{background:var(--ac2);}
.quickbox{background:var(--card);border:1px solid var(--bd);border-radius:12px;padding:1.1rem;box-shadow:0 2px 8px var(--sh);}
.quickbox h3{font-size:.92rem;font-weight:700;color:var(--ink);margin-bottom:.85rem;}
.qb{display:block;width:100%;text-align:right;background:var(--bg3);border:1px solid var(--bd);color:var(--ink2);padding:.52rem .82rem;border-radius:8px;font-family:"Tajawal",sans-serif;font-size:.81rem;cursor:pointer;margin-bottom:.5rem;transition:background .15s;}
.qb:hover{background:var(--ac3);color:var(--ac);}
.ccard{background:var(--card);border:1px solid var(--bd);border-radius:12px;padding:1.1rem;margin-top:.9rem;box-shadow:0 2px 8px var(--sh);}
.ccard h3{font-size:.9rem;font-weight:700;color:var(--ink);margin-bottom:.65rem;}
.ccard p{font-size:.8rem;color:var(--ink3);margin-bottom:.75rem;line-height:1.6;}
.mlink{display:flex;align-items:center;gap:7px;background:var(--ac);color:#fff;padding:.6rem .9rem;border-radius:8px;text-decoration:none;font-weight:700;font-size:.86rem;word-break:break-all;}

/* ── PRINT ── */
@media print{
  body > * { display:none !important; }
  #pw { display:block !important; position:fixed; inset:0; background:#fff; z-index:9999; overflow:auto; padding:0; margin:0; }
  #pw .t2s { background:#1a2332 !important; -webkit-print-color-adjust:exact; print-color-adjust:exact; color:#fff !important; }
  #pw .t2s .lb { color:#2ab0e0 !important; -webkit-print-color-adjust:exact; print-color-adjust:exact; }
  #pw .cvs { color:#1a6b8a !important; -webkit-print-color-adjust:exact; print-color-adjust:exact; }
  #pw .sk  { background:#e8f4f8 !important; -webkit-print-color-adjust:exact; print-color-adjust:exact; }
  #pw { font-family:"Tajawal",Arial,sans-serif; }
  @page { margin:10mm; size:A4; }
}
#pw { display:none; }

/* ── TOAST ── */
.toast{position:fixed;bottom:1.5rem;left:50%;transform:translateX(-50%) translateY(80px);background:#1a2332;color:#fff;padding:.7rem 1.5rem;border-radius:100px;font-size:.88rem;font-weight:600;z-index:9999;opacity:0;transition:all .3s;pointer-events:none;white-space:nowrap;}
.toast.show{transform:translateX(-50%) translateY(0);opacity:1;}

footer{background:var(--bg2);border-top:2px solid var(--bd);padding:1.8rem;text-align:center;}
.fti{max-width:1200px;margin:0 auto;}
.fti p{color:var(--ink3);font-size:.82rem;line-height:1.7;margin:.4rem 0;}
.fti a{color:var(--ac);font-weight:700;text-decoration:none;}

@media(max-width:900px){
  nav{padding:0 1rem;}
  .navl{display:none;}
  .builder,.ailay,.tmpls,.steps,.feats,.tips,.jobsg,.job-grid{grid-template-columns:1fr !important;}
  .feats{grid-template-columns:1fr 1fr !important;}
  .sec{padding:2rem 1rem;}
}

/* No Jobs Panel */
.no-jobs-panel{background:var(--bg3);border:1.5px solid var(--bd);border-radius:12px;padding:1.4rem;margin-top:.8rem;}
.no-jobs-panel h4{font-family:"Amiri",serif;font-size:1.1rem;color:var(--ink);margin-bottom:.5rem;}
.no-jobs-panel p{font-size:.84rem;color:var(--ink3);line-height:1.65;margin-bottom:1rem;}
.improve-list{list-style:none;display:flex;flex-direction:column;gap:.5rem;}
.improve-item{display:flex;align-items:flex-start;gap:.6rem;font-size:.84rem;color:var(--ink2);background:var(--bg2);border:1px solid var(--bd);border-radius:8px;padding:.6rem .85rem;}
.improve-item .ii{font-size:1rem;flex-shrink:0;}
/* Job card why matched */
.jc-why{font-size:.72rem;color:var(--gr);background:var(--gr2);border-radius:4px;padding:.15rem .5rem;display:inline-block;margin-bottom:.35rem;}
[data-dark] .jc-why{background:var(--gr2);color:var(--gr);}
/* Score breakdown */
.score-breakdown{display:flex;gap:.5rem;flex-wrap:wrap;margin-top:.6rem;}
.sb-item{font-size:.7rem;background:var(--bg2);border:1px solid var(--bd);border-radius:5px;padding:.15rem .5rem;color:var(--ink3);}
.sb-hit{border-color:var(--gr);color:var(--gr);background:var(--gr2);}
[data-dark] .sb-hit{background:var(--gr2);color:var(--gr);}
</style>
</head>
<body>

<div class="topbar">🎉 خدمة 100% مجانية — للتواصل: <a href="mailto:azooz.887m@gmail.com">azooz.887m@gmail.com</a></div>

<nav>
  <div class="navi">
    <div class="logo" onclick="go('home')">✦ سيرتك علينا<small>مجاني 100% — بدون تسجيل</small></div>
    <ul class="navl">
      <li><a id="nl-home" class="on" onclick="go('home')">الرئيسية</a></li>
      <li><a id="nl-build" onclick="go('build')">أنشئ سيرتك</a></li>
      <li><a id="nl-tips" onclick="go('tips')">نصائح وتعلّم</a></li>
      <li><a id="nl-ai" onclick="go('ai')">المساعد الذكي</a></li>
    </ul>
    <div class="navr">
      <button class="dbtn" onclick="toggleDark()"><span id="di">🌙</span><span id="dl">الوضع الداكن</span></button>
      <a class="mbtn" href="mailto:azooz.887m@gmail.com">✉️ راسلنا</a>
    </div>
  </div>
</nav>

<div class="sbar">
  <div class="sbar-in">
    <label class="stog">
      <input type="checkbox" id="aitog" onchange="toggleAI()">
      <div class="stgl"></div>
      <span id="ailbl">🤖 المساعد يبني السيرة: <strong>مطفي</strong></span>
    </label>
    <div class="sbsep"></div>
    <button class="exbtn" onclick="fillExample()">📡 مثال: خبير شبكات وسيرفرات</button>
    <button class="exbtn" onclick="clearForm()">🗑️ مسح الحقول</button>
  </div>
</div>

<!-- HOME -->
<div id="pg-home" class="pg on">
  <div class="hero">
    <div class="hbadge">✦ مجاني 100% — لا تسجيل — لا رسوم</div>
    <h1>سيرتك الذاتية<br><em>في دقائق</em></h1>
    <p>أنشئ سيرة ذاتية احترافية بنظام ATS مع اقتراح الوظائف المناسبة لك.</p>
    <div class="hbtns">
      <button class="bw" onclick="go('build')">🚀 أنشئ سيرتك الآن — مجاناً</button>
      <button class="bgb" onclick="go('tips')">📚 تعلّم أسرار السير الذاتية</button>
    </div>
    <div class="hstats">
      <div class="hst"><div class="n">ATS</div><div class="l">متوافق 100%</div></div>
      <div class="hst"><div class="n">51+</div><div class="l">وظيفة في قاعدة البيانات</div></div>
      <div class="hst"><div class="n">0 ر.س</div><div class="l">مجاني تماماً</div></div>
      <div class="hst"><div class="n">فوري</div><div class="l">بدون انتظار</div></div>
    </div>
  </div>
  <div class="sec">
    <div class="sech"><div class="badge">كيف يعمل</div><h2>أربع خطوات وسيرتك جاهزة</h2></div>
    <div class="steps">
      <div class="step"><div class="snum">١</div><h3>اختر القالب</h3><p>ثلاثة قوالب ATS احترافية</p></div>
      <div class="step"><div class="sarr">←</div><div class="snum">٢</div><h3>أدخل بياناتك</h3><p>الاسم والخبرات والمهارات</p></div>
      <div class="step"><div class="sarr">←</div><div class="snum">٣</div><h3>رتّب الأقسام</h3><p>اسحب وأفلت حسب تخصصك</p></div>
      <div class="step"><div class="sarr">←</div><div class="snum">٤</div><h3>اكتشف وظائفك</h3><p>نقترح الوظائف المناسبة لسيرتك</p></div>
    </div>
  </div>
  <div class="sec" style="padding-top:0">
    <div class="sech"><div class="badge">مزايا الموقع</div><h2>لماذا سيرتك علينا؟</h2></div>
    <div class="feats">
      <div class="feat"><div class="fico">✅</div><div><h3>نظام ATS 100%</h3><p>سيرتك تمر من الفلاتر الآلية — بيضاء ونظيفة.</p></div></div>
      <div class="feat"><div class="fico">🎯</div><div><h3>اقتراح وظائف ذكي</h3><p>يحلل مهاراتك ويقترح الوظائف والشركات المناسبة لك.</p></div></div>
      <div class="feat"><div class="fico">↕️</div><div><h3>ترتيب مخصص للأقسام</h3><p>اسحب وأفلت مع مقياس ATS لحظي.</p></div></div>
      <div class="feat"><div class="fico">🔗</div><div><h3>روابط المشاريع</h3><p>أضف روابط GitHub — تظهر في السيرة.</p></div></div>
      <div class="feat"><div class="fico">🤖</div><div><h3>مساعد ذكي</h3><p>يبني السيرة من وصف بسيط بكلامك الطبيعي.</p></div></div>
      <div class="feat"><div class="fico">🆓</div><div><h3>مجاني 100% دائماً</h3><p>لا اشتراكات، لا رسوم، لا تسجيل.</p></div></div>
    </div>
  </div>
  <div class="ctabar"><p style="color:rgba(255,255,255,.8);margin-bottom:.5rem;">جاهز تبدأ؟</p><h2>أنشئ سيرتك الآن — مجاناً</h2><button class="bw" onclick="go('build')">🚀 ابدأ الآن</button></div>
</div>

<!-- BUILD -->
<div id="pg-build" class="pg">
  <div class="sec">
    <div class="sech"><div class="badge">منشئ السيرة</div><h2>أنشئ سيرتك الذاتية</h2><p>أدخل بياناتك وسيرتك تظهر فوراً بنظام ATS</p></div>

    <h3 style="font-size:1.02rem;font-weight:700;color:var(--ink);margin-bottom:.9rem;">① اختر القالب:</h3>
    <div class="tmpls">
      <div class="tmpl on" id="tp1" onclick="setTmpl(1)">
        <div class="tprev"><svg viewBox="0 0 180 140"><rect width="180" height="140" fill="white"/><rect x="10" y="10" width="160" height="24" rx="2" fill="#1a6b8a"/><text x="90" y="26" font-size="8" fill="white" text-anchor="middle" font-weight="bold">اسم المتقدم</text><rect x="10" y="40" width="65" height="2" fill="#1a6b8a"/><rect x="10" y="47" width="160" height="3" rx="1" fill="#eee"/><rect x="10" y="53" width="140" height="3" rx="1" fill="#eee"/><rect x="10" y="64" width="65" height="2" fill="#1a6b8a"/><rect x="10" y="71" width="130" height="3" rx="1" fill="#eee"/><rect x="10" y="84" width="65" height="2" fill="#1a6b8a"/><rect x="10" y="91" width="38" height="5" rx="2" fill="#e8f4f8"/><rect x="52" y="91" width="38" height="5" rx="2" fill="#e8f4f8"/></svg></div>
        <div class="tbody"><span class="atag">✓ ATS</span><h3>الكلاسيكي المحترف</h3><p>شريط أزرق أعلى — لمعظم الوظائف</p><button class="tbtn">✓ محدد</button></div>
      </div>
      <div class="tmpl" id="tp2" onclick="setTmpl(2)">
        <div class="tprev"><svg viewBox="0 0 180 140"><rect width="180" height="140" fill="white"/><rect width="52" height="140" fill="#1a2332"/><text x="26" y="22" font-size="7" fill="white" text-anchor="middle" font-weight="bold">الاسم</text><text x="26" y="33" font-size="5" fill="#2ab0e0" text-anchor="middle">المسمى</text><rect x="5" y="56" width="40" height="3" rx="2" fill="rgba(42,176,224,.3)"/><rect x="5" y="62" width="36" height="3" rx="2" fill="rgba(42,176,224,.3)"/><rect x="60" y="12" width="112" height="2" fill="#1a2332"/><text x="60" y="21" font-size="6" fill="#333" font-weight="bold">الخبرة العملية</text><rect x="60" y="24" width="112" height="3" rx="1" fill="#eee"/><rect x="60" y="30" width="95" height="3" rx="1" fill="#eee"/></svg></div>
        <div class="tbody"><span class="atag">✓ ATS</span><h3>العمودي الحديث</h3><p>شريط جانبي داكن — للمجالات التقنية</p><button class="tbtn">اختر هذا</button></div>
      </div>
      <div class="tmpl" id="tp3" onclick="setTmpl(3)">
        <div class="tprev"><svg viewBox="0 0 180 140"><rect width="180" height="140" fill="white"/><text x="10" y="19" font-size="12" fill="#111" font-weight="900">الاسم الكامل</text><text x="10" y="30" font-size="6" fill="#777">المسمى الوظيفي</text><rect x="10" y="34" width="52" height="1" fill="#111"/><rect x="10" y="48" width="160" height="3" rx="1" fill="#f0f0f0"/><rect x="10" y="54" width="140" height="3" rx="1" fill="#f0f0f0"/><rect x="10" y="86" width="34" height="5" rx="2" fill="#f5f5f5"/><rect x="47" y="86" width="34" height="5" rx="2" fill="#f5f5f5"/></svg></div>
        <div class="tbody"><span class="atag">✓ ATS</span><h3>المينيمال النظيف</h3><p>بساطة مطلقة — أعلى نسب نجاح ATS</p><button class="tbtn">اختر هذا</button></div>
      </div>
    </div>

    <div class="builder">
      <div class="fbox">
        <h2>② أدخل بياناتك</h2>
        <div class="prog-wrap">
          <div class="prog-label"><span>اكتمال السيرة</span><strong id="prog-pct">0%</strong></div>
          <div class="prog-bar"><div class="prog-fill" id="prog-fill" style="width:0%"></div></div>
          <div class="prog-tips" id="prog-tips"></div>
        </div>

        <div class="ai-box" id="aibox">
          <h3>🤖 المساعد يبني السيرة لك</h3>
          <p>اكتب وصفك بكلامك الطبيعي — المساعد يبني السيرة كاملة تلقائياً.</p>
          <textarea class="ai-ta" id="aidesc" placeholder="مثال: اسمي عبدالعزيز، خبير شبكات وسيرفرات بخبرة 8 سنوات. عملت في stc وأرامكو. أتقن Cisco وWindows Server وLinux. حاصل على CCNA وMCSA. أبحث عن وظيفة مدير شبكات في الرياض..."></textarea>
          <button class="ai-gbtn" id="aigbtn" onclick="buildFromAI()"><span id="aigtxt">✨ اجعل المساعد يبني سيرتي</span></button>
        </div>

        <div class="mwrap" id="mwrap">
          <div class="fg2">
            <div class="fg"><label>الاسم الكامل *</label><input id="fn" oninput="updateProg()" placeholder="محمد أحمد العتيبي"></div>
            <div class="fg"><label>المسمى الحالي</label><input id="ft" oninput="updateProg()" placeholder="مهندس برمجيات"></div>
          </div>
          <div class="fg2">
            <div class="fg"><label>البريد الإلكتروني</label><input id="fe" oninput="updateProg()" type="email" placeholder="name@email.com"></div>
            <div class="fg"><label>رقم الهاتف</label><input id="fp" oninput="updateProg()" placeholder="05XXXXXXXX"></div>
          </div>
          <div class="fg2">
            <div class="fg"><label>المدينة / الدولة</label><input id="fc" oninput="updateProg()" placeholder="الرياض، السعودية"></div>
            <div class="fg"><label>لينكد إن</label><input id="fli" oninput="updateProg()" placeholder="linkedin.com/in/..."></div>
          </div>
          <div class="fg"><label>🎯 عنوان الوظيفة المستهدفة *</label><input id="fj" oninput="updateProg()" placeholder="مثال: مدير تسويق رقمي، محلل بيانات..."></div>
          <div class="fg"><label>📌 التخصص / الكلمات المفتاحية <span style="font-size:.72rem;color:var(--ink3);font-weight:400;">(اختياري)</span></label><input id="fsp" placeholder="مثال: Cisco، التسويق الرقمي، الشبكات..."></div>
          <div class="fg"><label>الخبرة العملية</label><textarea id="fex" oninput="updateProg()" placeholder="شركة stc (2019-2024): مهندس شبكات&#10;&#10;شركة أرامكو (2016-2019): مهندس بنية تحتية"></textarea></div>
          <div class="fg"><label>التعليم</label><textarea id="fed" oninput="updateProg()" placeholder="بكالوريوس هندسة حاسوب — جامعة الملك فهد — 2016" style="min-height:62px;"></textarea></div>
          <div class="fg"><label>المهارات</label><input id="fsk" oninput="updateProg()" placeholder="Cisco, Windows Server, Linux, VMware, Python..."></div>
          <div class="fg"><label>اللغات</label><input id="fla" oninput="updateProg()" placeholder="العربية (الأم)، الإنجليزية (ممتاز)"></div>
          <div class="fg"><label>الشهادات والدورات</label><input id="fce" oninput="updateProg()" placeholder="CCNP، MCSA، AWS Solutions Architect..."></div>

          <div class="projbox">
            <div class="projbox-h">
              <div><h4>🔗 المشاريع (مع روابط)</h4><small>أضف روابط GitHub أو موقعك — تظهر في السيرة</small></div>
              <button class="abtn" onclick="addProj()">+ مشروع</button>
            </div>
            <div id="pjl"></div>
            <div id="pjempty" style="text-align:center;padding:.6rem;color:var(--ink3);font-size:.8rem;">لا توجد مشاريع — اضغط "+ مشروع"</div>
          </div>

          <div class="csdbox">
            <div class="csdbox-h">
              <div><h4>➕ أقسام إضافية</h4><small>تطوع · جوائز · اهتمامات · منشورات...</small></div>
              <button class="abtn" onclick="addSec()">+ قسم</button>
            </div>
            <div id="csl"></div>
            <div id="csempty" style="text-align:center;padding:.6rem;color:var(--ink3);font-size:.8rem;">لا توجد أقسام مضافة</div>
          </div>
        </div>

        <!-- SECTIONS ORDER -->
        <div class="ord-panel">
          <div class="ord-top">
            <div class="ord-top-left">
              <h4>↕️ ترتيب أقسام السيرة</h4>
              <small>اسحب وأفلت — حسب احتياجك وتخصصك</small>
            </div>
            <div style="display:flex;align-items:center;gap:.5rem;">
              <div class="ats-score-wrap">
                <span class="ats-score-label">ATS</span>
                <span class="ats-score-val c-green" id="ats-score">100%</span>
                <span class="ats-score-txt c-green" id="ats-txt">ممتاز</span>
              </div>
              <button class="ord-reset-btn" onclick="resetOrder()">↺ إعادة</button>
            </div>
          </div>
          <div class="ord-presets">
            <button class="ord-preset-btn active" id="pre-exp" onclick="applyPreset('exp')">💼 ذو خبرة</button>
            <button class="ord-preset-btn" id="pre-fresh" onclick="applyPreset('fresh')">🎓 خريج جديد</button>
            <button class="ord-preset-btn" id="pre-tech" onclick="applyPreset('tech')">💻 تقني / مبرمج</button>
            <button class="ord-preset-btn" id="pre-net" onclick="applyPreset('net')">📡 شبكات / سيرفرات</button>
          </div>
          <div class="ord-list" id="ord-list"></div>
          <div class="ats-warn-box" id="ats-warn"></div>
        </div>

        <div class="draft-ind" id="draft-ind">✓ حُفظت مسودة</div>
        <button class="gbtn" id="gbtn" onclick="buildCV()"><span id="gbtxt">🤖 أنشئ سيرتي الذاتية</span></button>
      </div>

      <div class="cvout">
        <div class="cvouth"><h2>معاينة السيرة</h2><span class="atsbadge">✓ ATS</span></div>
        <div class="cvacts" id="cva" style="display:none;">
          <button class="cvact pr" onclick="printCV()">🖨️ طباعة / PDF</button>
          <button class="cvact" onclick="copyCV()">📋 نسخ</button>
          <button class="cvact" onclick="buildCV()">🔄 إعادة</button>
        </div>
        <div id="cvp"><div class="cvempty"><div class="ico">📄</div><p>أدخل بياناتك واضغط<br><strong>أنشئ سيرتي الذاتية</strong><br>ستظهر هنا فوراً</p></div></div>

        <div class="share-bar">
          <p>📤 شارك الموقع</p>
          <button class="shr-btn shr-wa" onclick="shareWA()">واتساب</button>
          <button class="shr-btn shr-tw" onclick="shareTW()">تويتر X</button>
          <button class="shr-btn shr-cp" onclick="shareCopy()">نسخ الرابط</button>
        </div>

        <div class="jobs-panel" id="jobs-panel">
          <div class="jobs-panel-head">
            <h3>🎯 الوظائف المناسبة لسيرتك</h3>
            <button class="jobs-close-btn" onclick="document.getElementById('jobs-panel').classList.remove('on')">إخفاء</button>
          </div>
          <div id="match-bar-wrap"></div>
          <div class="jobs-cats" id="jobs-cats"></div>
          <div class="job-grid" id="job-cards"></div>
          <div class="missing-box" id="missing-box" style="display:none;">
            <h5>💡 أضف هذه المهارات لتوسيع خياراتك:</h5>
            <div class="missing-pills" id="missing-pills"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div id="pw"></div>

<!-- TIPS -->
<div id="pg-tips" class="pg">
  <div class="sec">
    <div class="sech"><div class="badge">لوحة التعلّم</div><h2>كل ما تحتاجه عن السير والوظائف</h2></div>
    <div class="jobsbox">
      <h2>🔥 الوظائف الأكثر طلباً في السوق السعودي 2025</h2>
      <div class="jobsg">
        <div class="jobi"><div class="jdot"></div><div><h4>مهندس / محلل بيانات</h4><span>رؤية 2030 — طلب عالٍ جداً</span></div></div>
        <div class="jobi"><div class="jdot"></div><div><h4>متخصص ذكاء اصطناعي</h4><span>الأعلى نمواً في السوق</span></div></div>
        <div class="jobi"><div class="jdot"></div><div><h4>مدير تسويق رقمي</h4><span>مطلوب في جميع القطاعات</span></div></div>
        <div class="jobi"><div class="jdot"></div><div><h4>محاسب / مراجع مالي</h4><span>ثابت ومتصاعد الطلب</span></div></div>
        <div class="jobi"><div class="jdot"></div><div><h4>مطور تطبيقات Flutter</h4><span>نقص واضح في السوق</span></div></div>
        <div class="jobi"><div class="jdot"></div><div><h4>مهندس شبكات وسيرفرات</h4><span>طلب متصاعد مع رؤية 2030</span></div></div>
        <div class="jobi"><div class="jdot"></div><div><h4>مهندس سحابي Cloud</h4><span>نمو 45% سنوياً</span></div></div>
        <div class="jobi"><div class="jdot"></div><div><h4>مدير مشاريع PMP</h4><span>مطلوب في القطاع الحكومي</span></div></div>
      </div>
    </div>
    <h3 style="font-family:'Amiri',serif;font-size:1.4rem;color:var(--ink);margin-bottom:1rem;">📚 نصائح السيرة الذاتية</h3>
    <div class="tips">
      <div class="tip"><div class="tipico">🎯</div><span class="tiptag">أهم نصيحة</span><h3>خصّص سيرتك لكل وظيفة</h3><p>استخدم نفس الكلمات المفتاحية من إعلان الوظيفة — هذا ما تبحث عنه أنظمة ATS.</p></div>
      <div class="tip"><div class="tipico">🤖</div><span class="tiptag">نظام ATS</span><h3>افهم كيف تعمل أنظمة ATS</h3><p>80% من السير تُرفض آلياً. ATS يبحث عن كلمات مفتاحية — اجعل سيرتك نصية بحتة.</p></div>
      <div class="tip"><div class="tipico">📏</div><span class="tiptag">الطول المثالي</span><h3>صفحة أو صفحتان فقط</h3><p>أقل من 5 سنوات: صفحة. أكثر من 5 سنوات: صفحتان. لا أحد يقرأ أكثر.</p></div>
      <div class="tip"><div class="tipico">📊</div><span class="tiptag">قياس الإنجازات</span><h3>اكتب أرقاماً وليس كلاماً</h3><p>❌ "حسّنت المبيعات" — ✅ "رفعت المبيعات 35% خلال 6 أشهر."</p></div>
      <div class="tip"><div class="tipico">↕️</div><span class="tiptag">ترتيب الأقسام</span><h3>رتّب حسب تخصصك</h3><p>خريج جديد: التعليم أولاً. ذو خبرة: الخبرة أولاً. تقني: المهارات والمشاريع أولاً.</p></div>
      <div class="tip"><div class="tipico">🔗</div><span class="tiptag">المشاريع</span><h3>أضف روابط مشاريعك</h3><p>GitHub أو portfolio يرفع فرصك — خاصةً في المجالات التقنية.</p></div>
      <div class="tip"><div class="tipico">🌟</div><span class="tiptag">الملخص الشخصي</span><h3>ابدأ بملخص قوي</h3><p>أول 3-4 أسطر هي الأهم. اذكر خبرتك وأبرز إنجاز وهدفك المهني.</p></div>
      <div class="tip"><div class="tipico">⚠️</div><span class="tiptag">أخطاء شائعة</span><h3>أخطاء تقتل سيرتك</h3><p>✗ صورة غير رسمية ✗ أخطاء إملائية ✗ بريد غير احترافي ✗ الكذب في الخبرات.</p></div>
      <div class="tip"><div class="tipico">🖨️</div><span class="tiptag">الطباعة</span><h3>دائماً PDF وليس Word</h3><p>PDF يحافظ على التنسيق — استخدم "طباعة" ثم "حفظ كـ PDF".</p></div>
    </div>
  </div>
</div>

<!-- AI CHAT -->
<div id="pg-ai" class="pg">
  <div class="sec">
    <div class="sech"><div class="badge">المساعد الذكي</div><h2>اسأل — نجيب فوراً</h2></div>
    <div class="ailay">
      <div class="chatbox">
        <div class="chathd">
          <div class="chatav">🤖</div>
          <div style="flex:1;"><h3>مساعد سيرتك</h3><p>خبير السير الذاتية والتوظيف</p></div>
          <div class="cdot"></div>
        </div>
        <div class="msgs" id="msgs"><div class="msg mai">مرحباً! 👋 أنا مساعدك الذكي. اسألني عن السير الذاتية، الوظائف، المقابلات، أو أي شيء يخص التوظيف!</div></div>
        <div class="chatinp">
          <input class="cinp" id="cinp" placeholder="اكتب سؤالك هنا..." onkeydown="if(event.key==='Enter')sendMsg()">
          <button class="csend" onclick="sendMsg()">➤</button>
        </div>
      </div>
      <div>
        <div class="quickbox">
          <h3>💡 اضغط للسؤال:</h3>
          <button class="qb" onclick="ask('كيف أجعل سيرتي متوافقة مع نظام ATS؟')">كيف أجعل سيرتي متوافقة مع ATS؟</button>
          <button class="qb" onclick="ask('ما أكثر الوظائف طلباً في السوق السعودي 2025؟')">أكثر الوظائف طلباً في السوق؟</button>
          <button class="qb" onclick="ask('كيف أكتب ملخصاً شخصياً قوياً في السيرة؟')">كيف أكتب ملخصاً قوياً؟</button>
          <button class="qb" onclick="ask('كيف أتحضر لمقابلة عمل ناجحة؟')">كيف أتحضر للمقابلة؟</button>
          <button class="qb" onclick="ask('خبرتي قليلة كيف أكتب سيرتي بشكل احترافي؟')">خبرتي قليلة — كيف أكتب سيرتي؟</button>
          <button class="qb" onclick="ask('ما أهم مهارات مجال الشبكات والسيرفرات؟')">أهم مهارات الشبكات والسيرفرات؟</button>
        </div>
        <div class="ccard">
          <h3>📧 تواصل مباشر</h3>
          <p>للمساعدة الشخصية في سيرتك:</p>
          <a class="mlink" href="mailto:azooz.887m@gmail.com">✉️ azooz.887m@gmail.com</a>
          <p style="font-size:.72rem;color:var(--ink3);margin-top:.5rem;">نرد في أقرب وقت ممكن</p>
        </div>
      </div>
    </div>
  </div>
</div>

<footer>
  <div class="fti">
    <div class="logo" style="justify-content:center;display:flex;margin-bottom:.55rem;" onclick="go('home')">✦ سيرتك علينا</div>
    <p>خدمة مجانية 100% لبناء السيرة الذاتية بنظام ATS</p>
    <p><a href="mailto:azooz.887m@gmail.com">✉️ azooz.887m@gmail.com</a></p>
    <p style="font-size:.74rem;margin-top:.7rem;color:var(--ink3);">© 2025 سيرتك علينا — جميع الحقوق محفوظة</p>
  </div>
</footer>

<div class="toast" id="toast"></div>

<script>
(function() {
"use strict";

/* ═══════════════════════════════════════════════════════
   NAVIGATION
═══════════════════════════════════════════════════════ */
function go(name) {
  document.querySelectorAll(".pg").forEach(function(e) { e.classList.remove("on"); });
  document.querySelectorAll(".navl a").forEach(function(e) { e.classList.remove("on"); });
  var p = document.getElementById("pg-" + name);
  if (p) p.classList.add("on");
  var n = document.getElementById("nl-" + name);
  if (n) n.classList.add("on");
  window.scrollTo(0, 0);
}
window.go = go;

/* ═══════════════════════════════════════════════════════
   DARK MODE
═══════════════════════════════════════════════════════ */
window.toggleDark = function() {
  var d = document.documentElement;
  if (d.hasAttribute("data-dark")) {
    d.removeAttribute("data-dark");
    document.getElementById("di").textContent = "🌙";
    document.getElementById("dl").textContent = "الوضع الداكن";
  } else {
    d.setAttribute("data-dark", "");
    document.getElementById("di").textContent = "☀️";
    document.getElementById("dl").textContent = "الوضع الفاتح";
  }
};

/* ═══════════════════════════════════════════════════════
   TOAST
═══════════════════════════════════════════════════════ */
function showToast(msg) {
  var t = document.getElementById("toast");
  if (!t) return;
  t.textContent = msg;
  t.classList.add("show");
  setTimeout(function() { t.classList.remove("show"); }, 2800);
}

/* ═══════════════════════════════════════════════════════
   TEMPLATE
═══════════════════════════════════════════════════════ */
var tmplN = 1;
window.setTmpl = function(n) {
  tmplN = n;
  [1,2,3].forEach(function(i) {
    var el = document.getElementById("tp" + i);
    el.classList.remove("on");
    el.querySelector(".tbtn").textContent = "اختر هذا";
  });
  document.getElementById("tp" + n).classList.add("on");
  document.getElementById("tp" + n).querySelector(".tbtn").textContent = "✓ محدد";
};

/* ═══════════════════════════════════════════════════════
   AI MODE TOGGLE
═══════════════════════════════════════════════════════ */
window.toggleAI = function() {
  var on = document.getElementById("aitog").checked;
  document.getElementById("ailbl").innerHTML = "🤖 المساعد يبني السيرة: <strong>" +
    (on ? '<span style="color:var(--ac)">شغال</span>' : "مطفي") + "</strong>";
  document.getElementById("aibox").classList.toggle("on", on);
  document.getElementById("mwrap").classList.toggle("hidden", on);
  document.getElementById("gbtn").style.display = on ? "none" : "flex";
};

/* ═══════════════════════════════════════════════════════
   PROGRESS BAR
═══════════════════════════════════════════════════════ */
var PROG = [
  {id:"fn",  lbl:"الاسم",     w:20},
  {id:"fe",  lbl:"البريد",    w:8},
  {id:"fj",  lbl:"الوظيفة",  w:25},
  {id:"fex", lbl:"الخبرة",   w:22},
  {id:"fed", lbl:"التعليم",  w:12},
  {id:"fsk", lbl:"المهارات", w:13},
];
function updateProg() {
  var total = 0, max = 0;
  PROG.forEach(function(f) {
    max += f.w;
    var el = document.getElementById(f.id);
    if (el && el.value.trim().length > 2) total += f.w;
  });
  var pct = Math.round((total / max) * 100);
  var fill = document.getElementById("prog-fill");
  var pctEl = document.getElementById("prog-pct");
  if (!fill || !pctEl) return;
  fill.style.width = pct + "%";
  fill.style.background = pct < 40 ?
    "linear-gradient(90deg,#9b3a1a,#c8922a)" :
    pct < 70 ? "linear-gradient(90deg,#c8922a,#2a9fc5)" :
    "linear-gradient(90deg,var(--ac),var(--gr))";
  pctEl.textContent = pct + "%";
  var tips = document.getElementById("prog-tips");
  if (tips) {
    tips.innerHTML = PROG.map(function(f) {
      var done = document.getElementById(f.id) && document.getElementById(f.id).value.trim().length > 2;
      return '<span class="ptip' + (done ? " done" : "") + '">' + (done ? "✓ " : "") + f.lbl + "</span>";
    }).join("");
  }
  saveDraft();
}
window.updateProg = updateProg;

/* ═══════════════════════════════════════════════════════
   DRAFT SAVE / LOAD
═══════════════════════════════════════════════════════ */
var DRAFT_KEYS = ["fn","ft","fe","fp","fc","fli","fj","fsp","fex","fed","fsk","fla","fce"];
function saveDraft() {
  try {
    var d = {};
    DRAFT_KEYS.forEach(function(id) {
      var el = document.getElementById(id);
      if (el) d[id] = el.value;
    });
    sessionStorage.setItem("cv_draft", JSON.stringify(d));
    var ind = document.getElementById("draft-ind");
    if (ind) {
      ind.classList.add("on");
      clearTimeout(window._dt);
      window._dt = setTimeout(function() { ind.classList.remove("on"); }, 2000);
    }
  } catch(e) {}
}
function loadDraft() {
  try {
    var raw = sessionStorage.getItem("cv_draft");
    if (!raw) return;
    var d = JSON.parse(raw);
    DRAFT_KEYS.forEach(function(id) {
      var el = document.getElementById(id);
      if (el && d[id]) el.value = d[id];
    });
    updateProg();
    showToast("✓ تم استعادة مسودتك السابقة");
  } catch(e) {}
}

/* ═══════════════════════════════════════════════════════
   SECTIONS ORDER
═══════════════════════════════════════════════════════ */
var SEC_META = {
  summary:  {icon:"📝", label:"الملخص المهني",    hint:"يجب أن يكون أولاً دائماً",     ats:"must"},
  exp:      {icon:"💼", label:"الخبرة العملية",    hint:"الأهم بعد الملخص للمحترفين",   ats:"must"},
  edu:      {icon:"🎓", label:"التعليم",            hint:"مهم للخريجين والأكاديميين",    ats:"must"},
  skills:   {icon:"⚡", label:"المهارات",           hint:"ضرورية لتجاوز مرشحات ATS",    ats:"must"},
  projects: {icon:"🔗", label:"المشاريع",           hint:"ضرورية للمجالات التقنية",     ats:"free"},
  langs:    {icon:"🌐", label:"اللغات",             hint:"مفيدة للوظائف الدولية",       ats:"free"},
  certs:    {icon:"🏅", label:"الشهادات والدورات",  hint:"تقوّي الملف الوظيفي",         ats:"warn"},
  custom:   {icon:"➕", label:"الأقسام الإضافية",  hint:"اختيارية حسب المجال",         ats:"free"},
};
var PRESETS = {
  exp:   ["summary","exp","skills","edu","certs","projects","langs","custom"],
  fresh: ["summary","edu","skills","projects","exp","certs","langs","custom"],
  tech:  ["summary","skills","projects","exp","edu","certs","langs","custom"],
  net:   ["summary","exp","skills","certs","projects","edu","langs","custom"],
};
var sections = PRESETS.exp.map(function(id) { return {id:id, vis:true}; });
var activePreset = "exp";
var dragFrom = -1;

function renderOrdList() {
  var list = document.getElementById("ord-list");
  if (!list) return;
  list.innerHTML = "";
  sections.forEach(function(sec, idx) {
    var m = SEC_META[sec.id];
    if (!m) return;
    var item = document.createElement("div");
    item.className = "ord-item" + (sec.vis ? "" : " hidden-sec");
    item.setAttribute("draggable", "true");
    item.dataset.idx = String(idx);
    var atsClass = m.ats === "must" ? "tag-must" : m.ats === "warn" ? "tag-warn" : "tag-free";
    var atsText  = m.ats === "must" ? "أساسي ATS" : m.ats === "warn" ? "موصى به" : "اختياري";
    item.innerHTML =
      '<span class="ord-handle">⠿</span>' +
      '<span class="ord-icon">' + m.icon + '</span>' +
      '<div class="ord-info">' +
        '<div class="ord-name">' + m.label + '</div>' +
        '<div class="ord-hint">' + m.hint + '</div>' +
      '</div>' +
      '<div class="ord-badges">' +
        '<span class="ord-ats-tag ' + atsClass + '">' + atsText + '</span>' +
        '<button class="ord-toggle' + (sec.vis ? "" : " off") + '" onclick="toggleVis(' + idx + ')">' +
          (sec.vis ? "ظاهر" : "مخفي") + '</button>' +
      '</div>';
    item.addEventListener("dragstart", function(e) {
      dragFrom = idx;
      e.dataTransfer.effectAllowed = "move";
      e.dataTransfer.setData("text/plain", String(idx));
      setTimeout(function() { item.classList.add("dragging"); }, 0);
    });
    item.addEventListener("dragend", function() {
      item.classList.remove("dragging");
      dragFrom = -1;
    });
    item.addEventListener("dragover", function(e) {
      e.preventDefault();
      document.querySelectorAll(".ord-item").forEach(function(el) { el.classList.remove("drag-over"); });
      item.classList.add("drag-over");
    });
    item.addEventListener("dragleave", function(e) {
      if (!item.contains(e.relatedTarget)) item.classList.remove("drag-over");
    });
    item.addEventListener("drop", function(e) {
      e.preventDefault();
      item.classList.remove("drag-over");
      var from = parseInt(e.dataTransfer.getData("text/plain"), 10);
      var to = parseInt(item.dataset.idx, 10);
      if (!isNaN(from) && !isNaN(to) && from !== to) {
        var moved = sections.splice(from, 1)[0];
        sections.splice(to, 0, moved);
        activePreset = null;
        updatePresetBtns();
        renderOrdList();
        checkATS();
      }
    });
    list.appendChild(item);
  });
  checkATS();
}

window.toggleVis = function(idx) {
  var m = SEC_META[sections[idx].id];
  if (sections[idx].vis && m && m.ats === "must") {
    if (!confirm('قسم "' + m.label + '" أساسي لنظام ATS. هل أنت متأكد من إخفائه؟')) return;
  }
  sections[idx].vis = !sections[idx].vis;
  activePreset = null;
  updatePresetBtns();
  renderOrdList();
};

function checkATS() {
  var visible = sections.filter(function(s) { return s.vis; }).map(function(s) { return s.id; });
  var warnings = [];
  var score = 100;
  if (visible.length && visible[0] !== "summary") {
    warnings.push("⚠️ الملخص المهني يجب أن يكون القسم الأول");
    score -= 30;
  }
  if (!visible.includes("skills")) {
    warnings.push("⚠️ قسم المهارات مخفي — أساسي لتمرير فلاتر ATS");
    score -= 25;
  }
  var expIdx = visible.indexOf("exp");
  if (expIdx > 5 && expIdx !== -1) {
    warnings.push("💡 الخبرة العملية في النهاية — يُنصح برفعها للأعلى");
    score -= 10;
  }
  score = Math.max(0, score);
  var sv = document.getElementById("ats-score");
  var st = document.getElementById("ats-txt");
  if (!sv || !st) return;
  sv.textContent = score + "%";
  st.textContent = score >= 85 ? "ممتاز" : score >= 60 ? "جيد" : "يحتاج تحسين";
  var cls = score >= 85 ? "c-green" : score >= 60 ? "c-amber" : "c-red";
  sv.className = "ats-score-val " + cls;
  st.className = "ats-score-txt " + cls;
  var wb = document.getElementById("ats-warn");
  if (!wb) return;
  if (warnings.length) {
    wb.innerHTML = warnings.join("<br>");
    wb.classList.add("on");
  } else {
    wb.classList.remove("on");
    wb.innerHTML = "";
  }
}

window.applyPreset = function(preset) {
  var order = PRESETS[preset];
  if (!order) return;
  sections = order.map(function(id) { return {id:id, vis:true}; });
  activePreset = preset;
  updatePresetBtns();
  renderOrdList();
};
window.resetOrder = function() { window.applyPreset("exp"); };

function updatePresetBtns() {
  ["exp","fresh","tech","net"].forEach(function(p) {
    var el = document.getElementById("pre-" + p);
    if (el) el.classList.toggle("active", activePreset === p);
  });
}

/* ═══════════════════════════════════════════════════════
   PROJECTS
═══════════════════════════════════════════════════════ */
var projId = 0;
window.addProj = function() {
  document.getElementById("pjempty").style.display = "none";
  projId++;
  var id = "pj" + projId;
  var div = document.createElement("div");
  div.className = "prji";
  div.id = id;
  div.innerHTML =
    '<button class="prjdel" onclick="delProj(\'' + id + '\')">✕</button>' +
    '<div class="prjrow">' +
      '<input class="pname" placeholder="اسم المشروع *">' +
      '<input class="ptech" placeholder="التقنيات المستخدمة">' +
    '</div>' +
    '<input class="purl" placeholder="https://github.com/username/repo">' +
    '<textarea class="pdesc" rows="2" placeholder="وصف المشروع..."></textarea>';
  document.getElementById("pjl").appendChild(div);
};
window.delProj = function(id) {
  var el = document.getElementById(id);
  if (el) el.remove();
  if (!document.getElementById("pjl").children.length)
    document.getElementById("pjempty").style.display = "block";
};
function getProjs() {
  var out = [];
  document.querySelectorAll(".prji").forEach(function(d) {
    var n = d.querySelector(".pname").value.trim();
    var t = d.querySelector(".ptech").value.trim();
    var u = d.querySelector(".purl").value.trim();
    var desc = d.querySelector(".pdesc").value.trim();
    if (n) out.push({n:n, t:t, u:u, desc:desc});
  });
  return out;
}

/* ═══════════════════════════════════════════════════════
   CUSTOM SECTIONS
═══════════════════════════════════════════════════════ */
var secId = 0;
var PRESETS_SEC = ["الأعمال التطوعية","المشاريع الشخصية","الجوائز والتكريم","الاهتمامات","المنشورات","العضويات المهنية","إنجازات أخرى"];
window.addSec = function() {
  document.getElementById("csempty").style.display = "none";
  secId++;
  var id = "cs" + secId;
  var opts = PRESETS_SEC.map(function(p) { return '<option value="' + p + '">' + p + '</option>'; }).join("");
  var div = document.createElement("div");
  div.className = "csi";
  div.id = id;
  div.innerHTML =
    '<button class="csd2" onclick="delSec(\'' + id + '\')">✕</button>' +
    '<div class="csrow">' +
      '<input class="csinp sec-t" placeholder="اسم القسم">' +
      '<select class="cssel" onchange="this.previousElementSibling.value=this.value;this.value=\'\'">' +
        '<option value="">اختر...</option>' + opts +
      '</select>' +
    '</div>' +
    '<textarea class="csta sec-c" rows="3" placeholder="اكتب محتوى هذا القسم..."></textarea>';
  document.getElementById("csl").appendChild(div);
};
window.delSec = function(id) {
  var el = document.getElementById(id);
  if (el) el.remove();
  if (!document.getElementById("csl").children.length)
    document.getElementById("csempty").style.display = "block";
};
function getSecs() {
  var out = [];
  document.querySelectorAll(".csi").forEach(function(d) {
    var t = d.querySelector(".sec-t").value.trim();
    var c = d.querySelector(".sec-c").value.trim();
    if (t && c) out.push({t:t, c:c});
  });
  return out;
}

/* ═══════════════════════════════════════════════════════
   HELPERS
═══════════════════════════════════════════════════════ */
function v(id) { return document.getElementById(id).value.trim(); }

function esc(s) {
  return String(s)
    .replace(/&/g,"&amp;")
    .replace(/</g,"&lt;")
    .replace(/>/g,"&gt;")
    .replace(/"/g,"&quot;");
}

function mkSk(sk) {
  if (!sk) return "";
  return sk.split(",").map(function(s) {
    return '<span class="sk">' + esc(s.trim()) + "</span>";
  }).join("");
}

function mkExp(exp) {
  if (!exp) return "";
  return exp.split(/\n\n+/).map(function(b) {
    var lines = b.split("\n").filter(Boolean);
    if (!lines.length) return "";
    var title = lines[0];
    var bullets = lines.slice(1).filter(Boolean);
    var bulletsHtml = bullets.length ?
      "<ul style='margin:.3rem 0 0 1.2rem;padding:0;'>" +
        bullets.map(function(l) {
          var txt = l.replace(/^[—\-•·]\s*/, "");
          return "<li style='font-size:.83rem;color:#333;line-height:1.6;margin-bottom:2px;'>" + esc(txt) + "</li>";
        }).join("") +
      "</ul>" : "";
    return '<div class="cvb" style="margin-bottom:.75rem;"><strong style="font-size:.88rem;color:#1a2332;">' +
      esc(title) + "</strong>" + bulletsHtml + "</div>";
  }).join("");
}

function mkProjs(projs) {
  if (!projs || !projs.length) return "";
  return projs.map(function(p) {
    return '<div class="prj-cv">' +
      '<span class="prj-cv-title">' + esc(p.n) + "</span>" +
      (p.t ? ' <span class="prj-cv-tech">(' + esc(p.t) + ")</span>" : "") +
      (p.desc ? '<div class="prj-cv-desc">' + esc(p.desc) + "</div>" : "") +
      (p.u ? '<a class="prj-cv-link" href="' + esc(p.u) + '">' + esc(p.u) + "</a>" : "") +
      "</div>";
  }).join("");
}

function mkSum(job, spec, exp, sk) {
  var sp = spec || job;
  var sk3 = sk ? sk.split(",").slice(0,3).map(function(s) { return s.trim(); }).join(" و") : "";
  var sk6 = sk ? sk.split(",").slice(0,6).map(function(s) { return s.trim(); }).join(", ") : "";
  // ATS-optimized: include job title keywords, skills, and objective
  return "محترف متخصص في " + sp +
    (exp ? "، لديّ خبرة مهنية موثّقة في مجال " + job : "، أسعى للانضمام لمجال " + job) + ". " +
    (sk3 ? "أتقن " + sk3 + (sk6 ? " وغيرها" : "") + ". " : "") +
    "أهدف إلى تقديم قيمة حقيقية وتحقيق نتائج ملموسة في " + sp + ".";
}

/* ═══════════════════════════════════════════════════════
   BUILD SECTIONS (ordered)
═══════════════════════════════════════════════════════ */
function buildSections(d, cs, cb) {
  function sec(title, content) {
    if (!content) return "";
    return '<div class="' + cs + '">' + title + '</div><div class="' + cb + '">' + content + "</div>";
  }
  var map = {
    summary:  sec("الملخص المهني", d.summary),
    exp:      d.exp ? '<div class="' + cs + '">الخبرة العملية — Work Experience</div>' + mkExp(d.exp) : "",
    edu:      d.edu ? sec("التعليم — Education", d.edu.replace(/\n/g,"<br>")) : "",
    skills:   d.sk  ? '<div class="' + cs + '">المهارات — Skills</div><div style="padding:.3rem 0;">' + mkSk(d.sk) + "</div>" : "",
    projects: d.projs && d.projs.length ? '<div class="' + cs + '">المشاريع — Projects</div>' + mkProjs(d.projs) : "",
    langs:    d.langs ? sec("اللغات — Languages", d.langs) : "",
    certs:    d.certs ? sec("الشهادات والدورات — Certifications", d.certs) : "",
    custom:   d.secs && d.secs.length ? d.secs.map(function(s) { return sec(s.t, s.c); }).join("") : "",
  };
  var html = "";
  sections.forEach(function(s) { if (s.vis && map[s.id]) html += map[s.id]; });
  return html;
}

/* ═══════════════════════════════════════════════════════
   RENDER CV
═══════════════════════════════════════════════════════ */
function renderCV(d) {
  var contact = [d.email, d.phone, d.city, d.linkedin].filter(Boolean).join(" · ");
  if (d.tmpl === 1) {
    return '<div class="t1">' +
      '<div class="ch">' +
        '<div class="cn">' + esc(d.name) + "</div>" +
        '<div class="ct">' + esc(d.title) + "</div>" +
        (contact ? '<div class="cc">' + esc(contact) + "</div>" : "") +
      "</div>" +
      buildSections(d, "cvs", "cvb") + "</div>";
  }
  if (d.tmpl === 2) {
    var ss = d.sk ? d.sk.split(",").map(function(s) {
      return '<div style="font-size:.74rem;color:rgba(255,255,255,.8);margin-bottom:2px;">• ' + esc(s.trim()) + "</div>";
    }).join("") : "";
    return '<div class="t2">' +
      '<div class="t2s">' +
        '<div class="cn">' + esc(d.name) + "</div>" +
        '<div class="ct">' + esc(d.title) + "</div>" +
        (contact ? '<div class="t2si"><div class="lb">التواصل</div><div class="vl">' + [d.email,d.phone,d.city].filter(Boolean).map(esc).join("<br>") + "</div></div>" : "") +
        (d.sk ? '<div class="t2si"><div class="lb">المهارات</div>' + ss + "</div>" : "") +
        (d.langs ? '<div class="t2si"><div class="lb">اللغات</div><div class="vl">' + esc(d.langs).replace(/[،,]/g,"<br>") + "</div></div>" : "") +
        (d.certs ? '<div class="t2si"><div class="lb">الشهادات</div><div class="vl">' + esc(d.certs) + "</div></div>" : "") +
        (d.linkedin ? '<div class="t2si"><div class="lb">لينكد إن</div><div class="vl" style="word-break:break-all;font-size:.68rem;">' + esc(d.linkedin) + "</div></div>" : "") +
      "</div>" +
      '<div class="t2m-wrap"><div class="t2m">' + buildSections(d, "cvs", "cvb") + "</div></div><div style='clear:both'></div></div>";
  }
  return '<div class="t3">' +
    '<div class="bar"></div>' +
    '<div class="cn">' + esc(d.name) + "</div>" +
    '<div class="ct">' + esc(d.title) + "</div>" +
    (contact ? '<div class="cc">' + esc(contact) + "</div>" : "") +
    buildSections(d, "cvs", "cvb") + "</div>";
}

/* ═══════════════════════════════════════════════════════
   BUILD CV
═══════════════════════════════════════════════════════ */
window.buildCV = function() {
  var name = v("fn"), job = v("fj");
  if (!name) { alert("يرجى إدخال الاسم الكامل"); return; }
  if (!job)  { alert("يرجى إدخال عنوان الوظيفة المستهدفة"); return; }
  var btn = document.getElementById("gbtn");
  document.getElementById("gbtxt").textContent = "⏳ جاري البناء...";
  btn.disabled = true;
  document.getElementById("cvp").innerHTML = '<div class="loading"><div class="spin"></div><p>يتم بناء سيرتك بنظام ATS...</p></div>';
  document.getElementById("cva").style.display = "none";
  var d = {
    name:name, title:v("ft")||job, email:v("fe"), phone:v("fp"),
    city:v("fc"), linkedin:v("fli"), job:job, spec:v("fsp"),
    exp:v("fex"), edu:v("fed"), sk:v("fsk"), langs:v("fla"),
    certs:v("fce"), secs:getSecs(), projs:getProjs(), tmpl:tmplN
  };
  d.summary = mkSum(d.job, d.spec, d.exp, d.sk);
  setTimeout(function() {
    document.getElementById("cvp").innerHTML = renderCV(d);
    document.getElementById("cva").style.display = "flex";
    document.getElementById("gbtxt").textContent = "🤖 أنشئ سيرتي الذاتية";
    btn.disabled = false;
    showJobsPanel(d);
  }, 600);
};

/* ═══════════════════════════════════════════════════════
   AI BUILD
═══════════════════════════════════════════════════════ */
window.buildFromAI = function() {
  var desc = document.getElementById("aidesc").value.trim();
  if (!desc) { alert("اكتب وصفاً لنفسك أولاً"); return; }
  var btn = document.getElementById("aigbtn");
  btn.disabled = true;
  document.getElementById("aigtxt").textContent = "⏳ المساعد يبني سيرتك...";
  document.getElementById("cvp").innerHTML = '<div class="loading"><div class="spin"></div><p>المساعد يبني سيرتك...</p></div>';
  document.getElementById("cva").style.display = "none";
  setTimeout(function() {
    var d = parseDesc(desc);
    document.getElementById("cvp").innerHTML = renderCV(d);
    document.getElementById("cva").style.display = "flex";
    btn.disabled = false;
    document.getElementById("aigtxt").textContent = "✨ اجعل المساعد يبني سيرتي";
    showJobsPanel(d);
  }, 800);
};

function parseDesc(desc) {
  var dl = desc.toLowerCase();
  var name = "المتقدم";
  var nm = desc.match(/اسمي\s+([^\،,\n\.،]{2,20})/);
  if (nm) name = nm[1].trim();
  else { nm = desc.match(/أنا\s+([^\،,\n\.،]{2,15})/); if (nm) name = nm[1].trim(); }
  var title = "متخصص تقنية معلومات";
  var isNet = dl.includes("شبكات") || dl.includes("cisco") || dl.includes("network");
  var isSrv = dl.includes("سيرفر") || dl.includes("server") || dl.includes("windows server") || dl.includes("linux");
  if (isNet && isSrv) title = "خبير شبكات وخوادم IT";
  else if (isNet) title = "مهندس شبكات";
  else if (isSrv) title = "متخصص خوادم وبنية تحتية";
  else if (dl.includes("برمجة") || dl.includes("مطور")) title = "مطور برمجيات";
  else if (dl.includes("بيانات") || dl.includes("data")) title = "محلل بيانات";
  else if (dl.includes("تسويق")) title = "متخصص تسويق رقمي";
  else if (dl.includes("محاسب")) title = "محاسب مالي";
  var city = "";
  ["الرياض","جدة","الدمام","مكة","المدينة"].forEach(function(c) { if (dl.includes(c)) city = c; });
  var yrs = ""; var ym = desc.match(/(\d+)\s*سنوات?/); if (ym) yrs = ym[1];
  var job = title;
  var jm = desc.match(/(?:أبحث عن|أريد|وظيفة)\s+([^\.\n،,]+)/);
  if (jm) job = jm[1].trim();
  var sk = extractSkills(dl);
  var certs = extractCerts(dl);
  var exp = "";
  var re = /(?:شركة|في شركة|عملت في)\s+([^\،\n\.،,]+)/g;
  var m, cos = [];
  while ((m = re.exec(desc)) !== null) cos.push(m[1].trim());
  if (cos.length) exp = cos.slice(0,3).map(function(c) { return c + " — " + title; }).join("\n\n");
  var sum = buildNetSummary(isNet, isSrv, yrs, title, job, sk);
  return {
    name:name, title:title, email:"", phone:"", city:city, linkedin:"",
    job:job, spec:title, exp:exp, edu:"", sk:sk,
    langs:"العربية (الأم)، الإنجليزية (جيد)",
    certs:certs, secs:[], projs:[], tmpl:tmplN, summary:sum
  };
}

function buildNetSummary(isNet, isSrv, yrs, title, job, sk) {
  var y = yrs ? yrs + " سنوات" : "عدة سنوات";
  if (isNet || isSrv) {
    return "خبير متخصص في " + title + " بخبرة " + y +
      " في تصميم وإدارة البنى التحتية للشبكات والخوادم." +
      " أتقن إعداد خوادم Windows Server وLinux وأجهزة Cisco مع كفاءة عالية في الأمن السيبراني." +
      " أهدف إلى الانضمام لفريق تقني محترف يستثمر خبرتي في " + job + ".";
  }
  var sp3 = sk ? sk.split(",").slice(0,2).map(function(s){return s.trim();}).join(" و") : title;
  return "محترف متخصص في " + title + " بخبرة " + y + " في المجال." +
    (sp3 ? " أتقن " + sp3 + "." : "") +
    " أهدف إلى تقديم قيمة حقيقية في بيئة تتوافق مع تخصصي في " + job + ".";
}

function extractSkills(dl) {
  var map = {
    "cisco routing":"Cisco Routing & Switching",
    "windows server":"Windows Server",
    "linux":"Linux Administration",
    "vmware":"VMware vSphere",
    "firewall":"Firewall & VPN",
    "شبكات":"Network Administration",
    "سيرفر":"Server Management",
    "cybersecurity":"Cybersecurity",
    "active directory":"Active Directory",
    "python":"Python","sql":"SQL","power bi":"Power BI","excel":"Excel",
    "docker":"Docker","kubernetes":"Kubernetes","aws":"AWS Cloud","azure":"Microsoft Azure",
    "flutter":"Flutter","react":"React","node":"Node.js","php":"PHP",
    "machine learning":"Machine Learning","deep learning":"Deep Learning",
    "تسويق":"التسويق الرقمي","محاسبة":"المحاسبة","pmp":"PMP"
  };
  var sk = [];
  Object.keys(map).forEach(function(k) { if (dl.includes(k)) sk.push(map[k]); });
  return sk.length ? sk.join(", ") : "إدارة الشبكات, الخوادم, الأمن السيبراني";
}

function extractCerts(dl) {
  var certs = [];
  ["ccna","ccnp","mcsa","mcse","aws","azure","pmp","cissp","ceh","rhce","itil","cpa","cfa"].forEach(function(c) {
    if (dl.includes(c)) certs.push(c.toUpperCase());
  });
  return certs.join("، ");
}

/* ═══════════════════════════════════════════════════════
   PRINT
═══════════════════════════════════════════════════════ */
window.printCV = function() {
  var p = document.getElementById("cvp");
  if (!p.querySelector(".t1,.t2,.t3")) { alert("أنشئ السيرة أولاً ثم اطبعها"); return; }
  var styles = "<style>" +
    'body{margin:0;padding:0;font-family:"Tajawal",sans-serif;direction:rtl;background:#fff;color:#111;}' +
    ".t1{padding:2rem;}.t1 .ch{border-bottom:3px solid #1a6b8a;padding-bottom:.9rem;margin-bottom:.9rem;}" +
    ".t1 .cn{font-size:1.65rem;font-weight:900;color:#1a2332;}.t1 .ct{font-size:.9rem;color:#1a6b8a;font-weight:600;}" +
    ".t1 .cc{font-size:.78rem;color:#555;margin-top:.35rem;display:flex;gap:.9rem;flex-wrap:wrap;}" +
    ".cvs{font-size:.88rem;font-weight:800;color:#1a6b8a;text-transform:uppercase;letter-spacing:1px;border-bottom:1.5px solid #ddd;padding-bottom:.22rem;margin:.9rem 0 .45rem;}" +
    ".cvb{font-size:.84rem;color:#333;line-height:1.7;}" +
    ".t2{display:grid;grid-template-columns:185px 1fr;}" +
    ".t2s{background:#1a2332;color:#fff;padding:1.5rem 1rem;-webkit-print-color-adjust:exact;print-color-adjust:exact;}" +
    ".t2s .cn{font-size:1.15rem;font-weight:900;color:#fff;}.t2s .ct{font-size:.76rem;color:#2ab0e0;margin-bottom:.9rem;}" +
    ".t2si{margin-bottom:.9rem;}.t2si .lb{font-size:.66rem;font-weight:700;color:#2ab0e0;text-transform:uppercase;border-bottom:1px solid rgba(255,255,255,.15);padding-bottom:.22rem;margin-bottom:.35rem;}" +
    ".t2si .vl{font-size:.74rem;color:rgba(255,255,255,.8);line-height:1.6;}" +
    ".t2m{padding:1.5rem;}.t2m .cvs{color:#1a2332;border-bottom-color:#1a6b8a;border-bottom-width:2px;}" +
    ".t3{padding:2rem;}.t3 .bar{width:52px;height:2px;background:#111;margin-bottom:.75rem;}" +
    ".t3 .cn{font-size:1.8rem;font-weight:900;color:#111;}.t3 .ct{font-size:.88rem;color:#555;margin:.22rem 0 .55rem;}" +
    ".t3 .cc{font-size:.78rem;color:#777;display:flex;gap:1.1rem;flex-wrap:wrap;padding-bottom:.65rem;border-bottom:1px solid #eee;margin-bottom:.65rem;}" +
    ".t3 .cvs{font-size:.76rem;font-weight:800;color:#111;text-transform:uppercase;letter-spacing:2px;border-bottom:none;margin:.9rem 0 .35rem;}" +
    ".t3 .cvb{font-size:.83rem;color:#444;line-height:1.75;}" +
    ".sk{display:inline-block;background:#e8f4f8;color:#1a2332;padding:2px 9px;border-radius:3px;font-size:.78rem;margin:2px 2px;-webkit-print-color-adjust:exact;print-color-adjust:exact;}" +
    ".prj-cv{margin-bottom:.65rem;padding-bottom:.65rem;border-bottom:1px solid #eee;}" +
    ".prj-cv-title{font-weight:700;font-size:.86rem;color:#1a2332;}" +
    ".prj-cv-tech{font-size:.76rem;color:#888;}" +
    ".prj-cv-desc{font-size:.82rem;color:#444;line-height:1.65;margin:.2rem 0;}" +
    ".prj-cv-link{color:#1a6b8a;font-size:.78rem;word-break:break-all;}" +
    "</style>";
  document.getElementById("pw").innerHTML = styles + p.innerHTML;
  window.print();
  setTimeout(function() { document.getElementById("pw").innerHTML = ""; }, 1500);
};

window.copyCV = function() {
  var text = document.getElementById("cvp").innerText;
  if (navigator.clipboard) {
    navigator.clipboard.writeText(text).then(function() { showToast("✓ تم نسخ السيرة!"); });
  } else {
    var ta = document.createElement("textarea");
    ta.value = text; document.body.appendChild(ta); ta.select();
    document.execCommand("copy"); document.body.removeChild(ta);
    showToast("✓ تم نسخ السيرة!");
  }
};

/* ═══════════════════════════════════════════════════════
   FILL EXAMPLE / CLEAR
═══════════════════════════════════════════════════════ */
window.fillExample = function() {
  document.getElementById("fn").value = "عبدالعزيز محمد الغامدي";
  document.getElementById("ft").value = "خبير شبكات وخوادم IT";
  document.getElementById("fe").value = "azooz.887m@gmail.com";
  document.getElementById("fp").value = "0500000000";
  document.getElementById("fc").value = "الرياض، المملكة العربية السعودية";
  document.getElementById("fli").value = "linkedin.com/in/azooz-alghamdi";
  document.getElementById("fj").value = "مدير شبكات وبنية تحتية";
  document.getElementById("fsp").value = "Cisco, Windows Server, Linux, VMware, Network Security";
  document.getElementById("fex").value = "شركة stc للاتصالات (2019-2024): مهندس شبكات أول\n— تصميم وإدارة شبكة 500+ جهاز عبر 12 فرعاً\n— خفضت وقت التوقف 60% عبر نظام مراقبة تلقائي\n\nشركة أرامكو السعودية (2016-2019): مهندس بنية تحتية\n— إدارة 80 خادماً افتراضياً على VMware vSphere\n— نشر وصيانة Windows Server 2019 وLinux RHEL";
  document.getElementById("fed").value = "بكالوريوس هندسة شبكات — جامعة الملك عبدالله للعلوم — 2016";
  document.getElementById("fsk").value = "Cisco Routing & Switching, Windows Server 2019, Linux Administration, VMware vSphere, Firewall & VPN, Active Directory, Cybersecurity, Network Monitoring, TCP/IP, Wi-Fi Enterprise, Azure Cloud";
  document.getElementById("fla").value = "العربية (الأم)، الإنجليزية (ممتاز)";
  document.getElementById("fce").value = "CCNP Enterprise, MCSA: Windows Server, VMware VCP-DCV, CompTIA Security+";
  updateProg();
  window.addProj();
  setTimeout(function() {
    var items = document.querySelectorAll(".prji");
    if (items.length) {
      var last = items[items.length - 1];
      last.querySelector(".pname").value = "نظام مراقبة الشبكة التلقائي";
      last.querySelector(".ptech").value = "Python, Zabbix, Cisco API";
      last.querySelector(".purl").value = "https://github.com/azooz887/network-monitor";
      last.querySelector(".pdesc").value = "نظام مراقبة 500+ جهاز — خفّض وقت الاستجابة من 4 ساعات إلى 20 دقيقة.";
    }
  }, 100);
  go("build");
};

window.clearForm = function() {
  ["fn","ft","fe","fp","fc","fli","fj","fsp","fex","fed","fsk","fla","fce"].forEach(function(id) {
    document.getElementById(id).value = "";
  });
  document.getElementById("pjl").innerHTML = "";
  document.getElementById("pjempty").style.display = "block";
  document.getElementById("csl").innerHTML = "";
  document.getElementById("csempty").style.display = "block";
  updateProg();
};

/* ═══════════════════════════════════════════════════════
   SHARE
═══════════════════════════════════════════════════════ */
var SITE_URL = window.location.href.split("#")[0];
var SITE_MSG = "جرب \"سيرتك علينا\" — أنشئ سيرة ذاتية احترافية بنظام ATS مجاناً! 🚀\n";
window.shareWA = function() { window.open("https://wa.me/?text=" + encodeURIComponent(SITE_MSG + SITE_URL), "_blank"); };
window.shareTW = function() { window.open("https://twitter.com/intent/tweet?text=" + encodeURIComponent(SITE_MSG) + "&url=" + encodeURIComponent(SITE_URL), "_blank"); };
window.shareCopy = function() {
  var txt = SITE_MSG + SITE_URL;
  if (navigator.clipboard) navigator.clipboard.writeText(txt).then(function() { showToast("✓ تم نسخ رابط الموقع!"); });
  else { var ta = document.createElement("textarea"); ta.value = txt; document.body.appendChild(ta); ta.select(); document.execCommand("copy"); document.body.removeChild(ta); showToast("✓ تم نسخ الرابط!"); }
};

/* ═══════════════════════════════════════════════════════
   JOBS MATCHING ENGINE
═══════════════════════════════════════════════════════ */
// Word-boundary safe matching — avoids false positives from short substrings
function wordMatch(text, keyword) {
  if (!keyword || keyword.length < 2) return false;
  var k = keyword.toLowerCase().trim();
  // Direct match first
  if (text.includes(k)) return true;
  // For multi-word keywords, check if ANY significant word matches
  var words = k.split(/[\s,\/\-&+]+/).filter(function(w) { return w.length >= 4; });
  return words.length > 0 && words.some(function(w) { return text.includes(w); });
}

var JOB_DB = [

  /* ══ 📡 شبكات وسيرفرات ══ */
  {id:"neteng", cat:"net", icon:"📡", title:"مهندس شبكات",
   comp:"18,000–30,000", demand:"high",
   desc:"تصميم وإدارة الشبكات المحلية والموسعة وضمان استمراريتها وأمانها.",
   keys:["cisco routing","cisco switch","شبكات","network administration","ccna","ccnp","routing","switching","tcp/ip","wifi enterprise","lan","wan"],
   must:["cisco","شبكات","ccna","network"],
   suggest:["ccnp","network security","firewall management"],
   companies:["stc — شركة الاتصالات السعودية","موبايلي","زين السعودية","أرامكو السعودية","سابك","الهيئة السعودية للبيانات SDAIA","وزارة الاتصالات","المياه الوطنية","هيئة الاتصالات وتقنية المعلومات","الهيئة الملكية للجبيل وينبع","بنك الرياض","البنك الأهلي السعودي","NEOM","Huawei KSA","Ericsson KSA","Nokia KSA","STC Solutions","Elm — شركة علم"]},

  {id:"sysadm", cat:"net", icon:"🖥️", title:"مدير أنظمة وخوادم",
   comp:"16,000–28,000", demand:"high",
   desc:"إدارة خوادم Windows وLinux وضمان أداء البنية التحتية.",
   keys:["windows server","linux administration","server management","سيرفر","خوادم","active directory","vmware vsphere","hyper-v","rhel","powershell"],
   must:["windows server","linux","server","سيرفر"],
   suggest:["vmware","azure","powershell"],
   companies:["أرامكو السعودية","stc","سابك","البنك الأهلي السعودي","مصرف الراجحي","بنك الرياض","وزارة الصحة","وزارة التعليم","NEOM","Elm — شركة علم","STC Solutions","المركز الوطني للحكومة الرقمية","هيئة الزكاة والضريبة والجمارك","الجمارك السعودية","Oracle KSA","Microsoft KSA","IBM KSA"]},

  {id:"netsec", cat:"net", icon:"🔒", title:"متخصص أمن شبكات وسيبراني",
   comp:"20,000–38,000", demand:"high",
   desc:"حماية الشبكات والأنظمة وتطبيق سياسات الأمن السيبراني.",
   keys:["cybersecurity","firewall management","vpn configuration","أمن سيبراني","security operations","cissp","ceh","siem","splunk","penetration testing"],
   must:["cybersecurity","firewall","أمن","security"],
   suggest:["cissp","ceh","soc analyst"],
   companies:["الهيئة الوطنية للأمن السيبراني NCA","stc","أرامكو السعودية","وزارة الداخلية","المديرية العامة للجوازات","هيئة الاتصالات وتقنية المعلومات","البنك الأهلي السعودي","مصرف الراجحي","NEOM","Elm — شركة علم","IBM Security KSA","Palo Alto Networks KSA","Thales KSA","Kaspersky KSA","CrowdStrike","STC Solutions","المركز الوطني للحكومة الرقمية"]},

  {id:"cloud", cat:"net", icon:"☁️", title:"مهندس بنية سحابية",
   comp:"22,000–45,000", demand:"high",
   desc:"تصميم ونشر وإدارة البنية التحتية على AWS وAzure وGCP.",
   keys:["aws cloud","azure cloud","cloud computing","سحابي","kubernetes","docker containers","terraform","devops","gcp"],
   must:["aws","azure","cloud"],
   suggest:["kubernetes","terraform","devops"],
   companies:["أرامكو السعودية","stc","NEOM","وزارة الاتصالات","Elm — شركة علم","المركز الوطني للحكومة الرقمية","Accenture KSA","IBM KSA","Oracle KSA","Microsoft KSA","Amazon Web Services KSA","Google Cloud KSA","STC Solutions","SAP KSA","هيئة الاتصالات وتقنية المعلومات","الهيئة السعودية للبيانات SDAIA"]},

  {id:"devops", cat:"net", icon:"🔄", title:"مهندس DevOps",
   comp:"18,000–35,000", demand:"high",
   desc:"أتمتة عمليات البناء والنشر وإدارة البنية التحتية بالكود.",
   keys:["devops","docker containers","kubernetes","ci/cd","jenkins","ansible","terraform","git","pipeline automation"],
   must:["devops","docker containers","ci/cd"],
   suggest:["kubernetes","ansible","aws cloud"],
   companies:["stc","موبايلي","أرامكو السعودية","Lean Technologies","Foodics","Tamara","Salla","Jahez","Toters","STC Pay","Tabby","Unifonic","Mozn","Lucidya","Eyouth","ZATCA — هيئة الزكاة"]},

  {id:"helpdesk", cat:"net", icon:"🛠️", title:"دعم تقني / Help Desk",
   comp:"7,000–14,000", demand:"mid",
   desc:"تقديم الدعم التقني للمستخدمين وحل المشكلات اليومية.",
   keys:["it support","دعم تقني","help desk","technical support","hardware troubleshoot","itil","windows desktop","comptia"],
   must:["دعم تقني","it support","help desk","technical support"],
   suggest:["itil","comptia","azure"],
   companies:["وزارة التعليم","وزارة الصحة","وزارة الداخلية","stc","موبايلي","جامعة الملك عبدالعزيز","جامعة الملك فهد للبترول","مدارس دولية","مستشفى الملك فيصل التخصصي","البنك الأهلي السعودي","مصرف الراجحي","شركات التأمين","أرامكو السعودية","سابك","المياه الوطنية"]},

  /* ══ 💻 برمجة وتطوير ══ */
  {id:"backend", cat:"dev", icon:"⚙️", title:"مطور Backend",
   comp:"16,000–32,000", demand:"high",
   desc:"تطوير واجهات برمجية وقواعد بيانات وخوادم الويب.",
   keys:["python","java","node.js","php laravel","sql database","rest api","django","spring boot","برمجة backend","dotnet"],
   must:["python","java","node","php","برمجة"],
   suggest:["docker containers","microservices","sql database"],
   companies:["Salla — منصة سلة","Foodics","Lean Technologies","stc","Tamara","STC Pay","STC Solutions","Jahez — جاهز","Toters","Tabby","Unifonic","Mozn — مزن","Lucidya","Eyouth","Zid — زد","Webook","Cerner KSA","SAP KSA","Oracle KSA","Huawei KSA"]},

  {id:"frontend", cat:"dev", icon:"🎨", title:"مطور واجهات Frontend",
   comp:"14,000–28,000", demand:"high",
   desc:"بناء واجهات المستخدم التفاعلية باستخدام React وVue وAngular.",
   keys:["javascript","react.js","vue.js","angular","html css","typescript","next.js","tailwind","frontend development"],
   must:["javascript","react","frontend"],
   suggest:["typescript","next.js","ux design"],
   companies:["Salla — منصة سلة","Foodics","Lean Technologies","stc","Tamara","Tabby","Zid — زد","Webook","Jahez — جاهز","Toters","STC Pay","Eyouth","Unifonic","Mozn","Lucidya","Aqar — عقار","Bayut KSA","Property Finder KSA"]},

  {id:"mobile", cat:"dev", icon:"📱", title:"مطور تطبيقات جوال",
   comp:"16,000–32,000", demand:"high",
   desc:"تطوير تطبيقات iOS وAndroid باستخدام Flutter أو React Native.",
   keys:["flutter","react native","swift ios","kotlin android","mobile development","dart","xcode","android studio"],
   must:["flutter","react native","mobile"],
   suggest:["firebase","api design","ux design"],
   companies:["Salla — منصة سلة","Foodics","stc","موبايلي","Careem KSA","Jahez — جاهز","Toters","Hungerstation","STC Pay","Tamara","Tabby","وزارة الصحة — تطبيق صحتي","وزارة التعليم","نادي الهلال","نادي الاتحاد","Zid","Unifonic"]},

  {id:"fullstack", cat:"dev", icon:"🔧", title:"مطور Full Stack",
   comp:"18,000–38,000", demand:"high",
   desc:"تطوير الواجهتين الأمامية والخلفية مع قواعد البيانات.",
   keys:["full stack development","node.js","react.js","python","django","php laravel","javascript","sql database","mongodb"],
   must:["full stack development","javascript"],
   suggest:["docker containers","devops","microservices"],
   companies:["Lean Technologies","Foodics","stc","Tamara","Tabby","STC Solutions","Salla","Zid","Webook","Mozn","Lucidya","Unifonic","Eyouth","Expensya KSA","Baims","Noon KSA","Amazon KSA"]},

  {id:"qa", cat:"dev", icon:"🧪", title:"مهندس جودة برمجيات QA",
   comp:"12,000–22,000", demand:"mid",
   desc:"اختبار وضمان جودة التطبيقات والأنظمة البرمجية.",
   keys:["quality assurance","software testing","selenium","automation testing","manual testing","jira","postman api","cypress"],
   must:["quality assurance","software testing","automation testing"],
   suggest:["selenium","cypress","performance testing"],
   companies:["stc","Salla","Foodics","Lean Technologies","STC Solutions","Tamara","Tabby","Mozn","البنك الأهلي السعودي","مصرف الراجحي","Elm — شركة علم","أرامكو السعودية","SAP KSA","Oracle KSA"]},

  /* ══ 📊 بيانات وذكاء اصطناعي ══ */
  {id:"data", cat:"data", icon:"📊", title:"محلل بيانات",
   comp:"14,000–28,000", demand:"high",
   desc:"تحليل البيانات واستخراج رؤى تجارية لدعم القرارات.",
   keys:["data analysis","sql database","excel advanced","power bi","tableau","python data","pandas","statistics","business analytics","بيانات"],
   must:["data","sql","analytics","بيانات"],
   suggest:["python data","power bi","tableau"],
   companies:["الهيئة السعودية للبيانات والذكاء الاصطناعي SDAIA","أرامكو السعودية","stc","البنك الأهلي السعودي","مصرف الراجحي","بنك الرياض","وزارة الاقتصاد","وزارة المالية","NEOM","Elm — شركة علم","Deloitte KSA","PwC KSA","KPMG KSA","McKinsey KSA","BCG KSA","Mozn — مزن","Lucidya","سابك"]},

  {id:"ml", cat:"data", icon:"🤖", title:"متخصص ذكاء اصطناعي / ML",
   comp:"22,000–50,000", demand:"high",
   desc:"بناء نماذج التعلم الآلي والذكاء الاصطناعي وتطبيقاتها.",
   keys:["machine learning","deep learning","tensorflow","pytorch","artificial intelligence","natural language processing","python","llm","generative ai"],
   must:["machine learning","artificial intelligence","deep learning","nlp"],
   suggest:["llm","mlops","cloud ai"],
   companies:["الهيئة السعودية للبيانات والذكاء الاصطناعي SDAIA","أرامكو السعودية","stc","KAUST — جامعة الملك عبدالله","KACST — مدينة الملك عبدالعزيز للعلوم","NEOM","Mozn — مزن","Google Cloud KSA","Microsoft KSA","IBM KSA","Accenture KSA","McKinsey QuantumBlack KSA","Lucidya","STC Solutions","Elm — شركة علم","Bayanat Analytics"]},

  {id:"bi", cat:"data", icon:"📈", title:"محلل ذكاء أعمال BI",
   comp:"12,000–24,000", demand:"mid",
   desc:"بناء لوحات تحكم وتقارير تحليلية لدعم القرار.",
   keys:["power bi","tableau","business intelligence","excel advanced","kpi dashboard","dax","sql reporting","data visualization"],
   must:["power bi","business intelligence","data visualization"],
   suggest:["sql database","python data","azure synapse"],
   companies:["أرامكو السعودية","سابك","stc","البنك الأهلي السعودي","مصرف الراجحي","بنك الرياض","وزارة المالية","هيئة الزكاة والضريبة والجمارك","Deloitte KSA","PwC KSA","KPMG KSA","EY KSA","SAP KSA","Oracle KSA","Microsoft KSA","المياه الوطنية","الهيئة العامة للطيران المدني"]},

  {id:"dataeng", cat:"data", icon:"🏗️", title:"مهندس بيانات",
   comp:"18,000–38,000", demand:"high",
   desc:"بناء وإدارة خطوط معالجة البيانات وبنية التخزين.",
   keys:["etl pipeline","apache spark","kafka","airflow","data engineering","sql database","python data","snowflake","databricks"],
   must:["etl pipeline","data engineering","apache spark"],
   suggest:["kafka","cloud data","databricks"],
   companies:["الهيئة السعودية للبيانات SDAIA","أرامكو السعودية","stc","البنك الأهلي السعودي","وزارة المالية","Deloitte KSA","Accenture KSA","Amazon KSA","NEOM","Mozn","Bayanat Analytics","Elm — شركة علم","STC Solutions"]},

  /* ══ 🎨 تصميم ══ */
  {id:"ux", cat:"design", icon:"🎨", title:"مصمم UX/UI",
   comp:"12,000–25,000", demand:"high",
   desc:"تصميم تجارب وواجهات المستخدم للتطبيقات والمواقع.",
   keys:["figma design","user experience design","user interface design","ux research","تصميم واجهات","wireframe","prototype","adobe xd"],
   must:["figma design","user experience design","user interface design","تصميم واجهات"],
   suggest:["motion design","user research","html css"],
   companies:["Salla — منصة سلة","Foodics","Lean Technologies","stc","موبايلي","NEOM","Elm — شركة علم","STC Pay","Webook","Zid","Baims","وكالة MBC الإبداعية","VMLY&R KSA","FP7 McCann KSA","Publicis KSA","Jahez","Tamara","Tabby"]},

  {id:"graphic", cat:"design", icon:"✏️", title:"مصمم جرافيك",
   comp:"8,000–18,000", demand:"mid",
   desc:"تصميم المواد البصرية والهوية التجارية والمحتوى الإبداعي.",
   keys:["photoshop design","illustrator","indesign","graphic design","تصميم جرافيك","brand identity","canva","visual design"],
   must:["photoshop design","graphic design","تصميم جرافيك"],
   suggest:["motion graphics","after effects","brand identity"],
   companies:["وكالات إعلانية (JWT, FP7, Publicis)","مجموعة MBC","صحيفة عرب نيوز","قناة روتانا","stc","موبايلي","أرامكو — قسم الاتصالات","Salla","Noon KSA","هيئة الترفيه","العلا للتطوير","NEOM","Jawwy TV","Shahid VIP","Asda'a BCW"]},

  /* ══ 📣 تسويق ومبيعات ══ */
  {id:"digmkt", cat:"mkt", icon:"📣", title:"مدير تسويق رقمي",
   comp:"12,000–28,000", demand:"high",
   desc:"قيادة الحملات الرقمية وتحسين الحضور الإلكتروني.",
   keys:["digital marketing","search engine optimization","google ads","meta advertising","تسويق رقمي","social media marketing","email marketing","crm system"],
   must:["digital marketing","تسويق","google ads","seo"],
   suggest:["crm system","email marketing","google analytics"],
   companies:["Salla — منصة سلة","Noon KSA","Namshi KSA","stc","موبايلي","Foodics","Jahez","وكالة Publicis KSA","وكالة FP7 McCann KSA","وكالة VMLY&R KSA","وكالة Havas KSA","NEOM","هيئة الترفيه","وزارة السياحة","بنك الرياض","مصرف الراجحي","أرامكو — التسويق","Almarai — المراعي"]},

  {id:"sales", cat:"mkt", icon:"🤝", title:"مندوب / مدير مبيعات",
   comp:"8,000–25,000+عمولة", demand:"high",
   desc:"إتمام الصفقات وبناء علاقات العملاء وتحقيق أهداف المبيعات.",
   keys:["مبيعات","sales management","b2b sales","b2c sales","account management","retail sales","customer relations","تفاوض","negotiation skills"],
   must:["مبيعات","sales"],
   suggest:["crm system","salesforce","negotiation skills"],
   companies:["stc — مبيعات الأعمال","موبايلي","زين السعودية","أرامكو — تسويق المنتجات","الجزيرة للسيارات","عبد اللطيف جميل","عبدالله العثيم للتجارة","مجموعة بنيان العقارية","Noon KSA","أسواق العثيم","بنده","Almarai","Nestle KSA","Unilever KSA","P&G KSA","شركات أدوية (Roche, Pfizer, Novartis) KSA"]},

  /* ══ 💰 مالي ومحاسبة ══ */
  {id:"acct", cat:"fin", icon:"📒", title:"محاسب / مراجع مالي",
   comp:"10,000–20,000", demand:"high",
   desc:"إعداد القوائم المالية والتقارير ومراجعة الحسابات.",
   keys:["محاسبة","financial accounting","cpa certification","vat compliance","zakat filing","financial statements","ifrs standards","erp system"],
   must:["محاسبة","accounting","financial"],
   suggest:["cpa certification","ifrs standards","erp system"],
   companies:["Deloitte KSA — ديلويت","PwC KSA — برايس ووترهاوس","KPMG KSA","EY KSA — إرنست ويونغ","BDO KSA","هيئة الزكاة والضريبة والجمارك ZATCA","وزارة المالية","أرامكو السعودية","سابك","البنك الأهلي السعودي","مصرف الراجحي","بنك الرياض","شركات التأمين","Almarai — المراعي","مجموعة الزامل","مجموعة MBC"]},

  {id:"fin", cat:"fin", icon:"💹", title:"محلل / مستشار مالي",
   comp:"14,000–35,000", demand:"mid",
   desc:"تحليل البيانات المالية وتقديم التوصيات الاستثمارية.",
   keys:["financial analysis","cfa certification","investment management","portfolio management","financial modeling","valuation","equity research","fixed income"],
   must:["financial analysis","investment","financial modeling"],
   suggest:["cfa certification","bloomberg","excel advanced"],
   companies:["البنك الأهلي السعودي NCB","مصرف الراجحي","بنك الرياض Riyad Bank","البنك السعودي الأول SAB","البنك العربي الوطني ANB","Alinma Bank","هيئة السوق المالية CMA","الشركة السعودية للاستثمار SAIB","صندوق الاستثمارات العامة PIF","شركة الجزيرة كابيتال","Jadwa Investment","NCB Capital","Aljazira Capital","Deloitte KSA","McKinsey KSA"]},

  {id:"banking", cat:"fin", icon:"🏦", title:"متخصص مصرفي",
   comp:"12,000–25,000", demand:"mid",
   desc:"العمل في خدمات مصرفية كتمويل الأفراد والشركات.",
   keys:["banking operations","retail banking","corporate banking","credit analysis","risk management","kyc compliance","aml compliance","mortgage financing"],
   must:["banking operations","retail banking","credit analysis"],
   suggest:["cfa certification","compliance","risk management"],
   companies:["البنك الأهلي السعودي NCB","مصرف الراجحي","بنك الرياض","البنك السعودي الأول SAB","البنك العربي الوطني ANB","Alinma Bank — بنك الإنماء","Saudi Investment Bank SAIB","Bank Albilad — بنك البلاد","Arab National Bank","Gulf International Bank KSA","HSBC KSA","Citibank KSA","مصرف الإنماء","STC Pay","Tamara","Tabby"]},

  /* ══ 👥 موارد بشرية وإدارة ══ */
  {id:"hr", cat:"hr", icon:"👥", title:"متخصص موارد بشرية",
   comp:"10,000–20,000", demand:"mid",
   desc:"إدارة التوظيف والتدريب وشؤون الموظفين.",
   keys:["human resources","hr management","recruitment","talent acquisition","training development","payroll management","employee relations","hris system"],
   must:["human resources","hr","recruitment","موارد بشرية"],
   suggest:["hris system","shrm","sap hr"],
   companies:["أرامكو السعودية","سابك","stc","وزارة الموارد البشرية","هيئة تطوير الموارد البشرية هدف","البنك الأهلي السعودي","مصرف الراجحي","Deloitte KSA","Accenture KSA","مستشفى الملك فيصل التخصصي","وزارة الصحة","وزارة التعليم","هيئة الترفيه","NEOM","Almarai — المراعي","مجموعة الزامل","مجموعة الفطيم KSA"]},

  {id:"pm", cat:"hr", icon:"📋", title:"مدير مشاريع PMP",
   comp:"16,000–35,000", demand:"high",
   desc:"قيادة وتخطيط وتنفيذ المشاريع وفق منهجيات احترافية.",
   keys:["pmp certification","project management","agile methodology","scrum master","jira tool","pmbok","program management","risk assessment"],
   must:["pmp","project management","agile"],
   suggest:["agile methodology","scrum master","risk assessment"],
   companies:["أرامكو السعودية","سابك","stc","NEOM","وزارة الإسكان","Accenture KSA","Deloitte KSA","McKinsey KSA","Bechtel KSA","Parsons KSA","أطلس للمقاولات","Saudi Binladin Group","الهيئة الملكية للجبيل وينبع","شركة نيوم","وزارة الاتصالات","Elm — شركة علم","Aecom KSA","Turner & Townsend KSA"]},

  /* ══ 🏥 صحة وطب ══ */
  {id:"doctor", cat:"health", icon:"👨‍⚕️", title:"طبيب / متخصص طبي",
   comp:"20,000–60,000", demand:"high",
   desc:"تقديم الرعاية الصحية والتشخيص والعلاج.",
   keys:["طب سريري","طبيب","physician","medical diagnosis","clinical practice","hospital medicine","specialty medicine","board certification"],
   must:["طب","طبيب","clinical"],
   suggest:["board certification","research","fellowship"],
   companies:["وزارة الصحة — المستشفيات الحكومية","مستشفى الملك فيصل التخصصي","مستشفى الملك عبدالعزيز","مدينة الملك عبدالله الطبية","ضمان للرعاية الصحية","Mayo Clinic KSA","شبكة مستشفيات ومراكز الدكتور سليمان الحبيب","المستشفى السعودي الألماني","مستشفى الموسى","مستشفى المانع","American Hospital KSA","شركة بالم للرعاية الصحية","شركة SEHA","Pure Health KSA","Cigna KSA","أرامكو الطبية"]},

  {id:"nursing", cat:"health", icon:"💉", title:"ممرض / ممرضة",
   comp:"8,000–18,000", demand:"high",
   desc:"تقديم الرعاية التمريضية ومتابعة المرضى.",
   keys:["تمريض","nursing care","registered nurse","patient care","intensive care unit","emergency nursing","bls acls","clinical nursing"],
   must:["تمريض","nursing care","registered nurse"],
   suggest:["intensive care unit","critical care","bls acls"],
   companies:["وزارة الصحة","مستشفى الملك فيصل التخصصي","مدينة الملك عبدالله الطبية","ضمان للرعاية الصحية","أرامكو الطبية","مستشفى الحرس الوطني","المستشفى السعودي الألماني","شبكة مستشفيات الدكتور سليمان الحبيب","Pure Health KSA","شركة بالم للرعاية الصحية","مستشفى المانع","American Hospital KSA"]},

  /* ══ 🏗️ هندسة وصناعة ══ */
  {id:"civil", cat:"eng", icon:"🏗️", title:"مهندس مدني",
   comp:"12,000–28,000", demand:"high",
   desc:"تصميم وإشراف على مشاريع البنية التحتية والمباني.",
   keys:["هندسة مدنية","civil engineering","structural design","construction management","autocad","revit design","infrastructure projects","concrete design"],
   must:["هندسة مدنية","civil","construction"],
   suggest:["revit design","project management","sap2000"],
   companies:["أرامكو السعودية","وزارة الإسكان","NEOM","شركة نيوم للبناء","Saudi Binladin Group","Bechtel KSA","Parsons KSA","Aecom KSA","Dar Al-Handasah KSA","مجموعة بن لادن السعودية","الهيئة الملكية للجبيل وينبع","شركة المياه الوطنية","وزارة النقل","Saudi Aramco Total Refinery SATORP","Almabani General Contractors","Turner & Townsend KSA","الشركة السعودية للكهرباء"]},

  {id:"mech", cat:"eng", icon:"⚙️", title:"مهندس ميكانيكي",
   comp:"12,000–28,000", demand:"mid",
   desc:"تصميم وتطوير وصيانة الأنظمة الميكانيكية.",
   keys:["هندسة ميكانيكية","mechanical engineering","maintenance management","autocad","solidworks","catia design","plc programming","hvac systems"],
   must:["هندسة ميكانيكية","mechanical","maintenance"],
   suggest:["plc programming","cmms","six sigma"],
   companies:["أرامكو السعودية","سابك","الهيئة الملكية للجبيل وينبع","المياه الوطنية","هيئة الطيران المدني","شركة أبشر للطاقة","Saudi Electricity Company","مصانع الأسمنت السعودية","شركة صلب SteelTech","شركة المصافي السعودية SASREF","Emerson KSA","Honeywell KSA","Schneider Electric KSA","Siemens KSA","GE KSA","ABB KSA"]},

  {id:"elec", cat:"eng", icon:"⚡", title:"مهندس كهربائي",
   comp:"12,000–30,000", demand:"mid",
   desc:"تصميم وتركيب وصيانة الأنظمة الكهربائية.",
   keys:["هندسة كهربائية","electrical engineering","plc programming","scada systems","power systems","electrical installation","renewable energy","electrical design"],
   must:["هندسة كهربائية","electrical","plc"],
   suggest:["scada systems","renewable energy","power systems"],
   companies:["الشركة السعودية للكهرباء SEC","أرامكو السعودية","سابك","NEOM","شركة أكوا باور ACWA Power","شركة الطاقة الكهرضوئية SPPC","Schneider Electric KSA","Siemens KSA","ABB KSA","Hitachi Energy KSA","Eaton KSA","وزارة الطاقة","الهيئة الملكية للجبيل","مشاريع نيوم الكهربائية","SWCC — تحلية المياه"]},

  {id:"petro", cat:"eng", icon:"🛢️", title:"مهندس بترول / كيميائي",
   comp:"18,000–45,000", demand:"mid",
   desc:"العمل في استخراج ومعالجة النفط والغاز.",
   keys:["هندسة بترول","petroleum engineering","oil gas","reservoir engineering","drilling operations","process engineering","refinery","petrochemical"],
   must:["هندسة بترول","petroleum","نفط"],
   suggest:["reservoir engineering","hse safety","drilling operations"],
   companies:["أرامكو السعودية","سابك","الهيئة الملكية للجبيل وينبع","SABIC Agri-Nutrients","Shell KSA","Total KSA","ExxonMobil KSA","Saudi Kayan Petrochemical","شركة ينبع أرامكو","شركة سدير للبتروكيماويات","شركة معادن","شركة المصافي السعودية SASREF","Schlumberger KSA","Halliburton KSA","Baker Hughes KSA","شركة أنابيب الشرق الأوسط"]},

  {id:"hse", cat:"eng", icon:"🦺", title:"متخصص سلامة HSE",
   comp:"12,000–25,000", demand:"high",
   desc:"تطبيق معايير السلامة والصحة المهنية في بيئة العمل.",
   keys:["hse safety","safety management","occupational health","nebosh","risk assessment","incident investigation","iso 45001","safety inspection"],
   must:["hse","safety","سلامة"],
   suggest:["nebosh","iso 45001","fire safety"],
   companies:["أرامكو السعودية","سابك","الهيئة الملكية للجبيل وينبع","وزارة الموارد البشرية","هيئة السلامة والصحة المهنية","Saudi Binladin Group","Bechtel KSA","مشاريع NEOM","Parsons KSA","Aecom KSA","شركة المصافي SASREF","شركة معادن","الشركة السعودية للكهرباء","مصانع الأسمنت","شركات البناء والمقاولات"]},

  /* ══ 📚 تعليم ══ */
  {id:"teacher", cat:"edu", icon:"📚", title:"معلم / مدرس",
   comp:"7,000–15,000", demand:"high",
   desc:"التدريس وتطوير المناهج وتقييم الطلاب.",
   keys:["تعليم","teaching experience","classroom management","curriculum development","lesson planning","student assessment","educational technology"],
   must:["تعليم","teaching","معلم"],
   suggest:["e-learning","educational technology","classroom management"],
   companies:["وزارة التعليم — المدارس الحكومية","مدارس الرياض الأهلية","مدارس المعرفة الدولية","مدارس الفيصلية","مدارس النخبة","مدارس العلوم والتكنولوجيا KIST","مدارس الجزيرة","British International School Riyadh","ISG — International Schools Group","DIS — Deutsche Internationale Schule","Alef Education","Noon Academy","Mawdoo3 — موضوع","إدراك — Edraak","Rwaq — رواق"]},

  /* ══ ⚖️ قانوني ══ */
  {id:"lawyer", cat:"legal", icon:"⚖️", title:"محامي / مستشار قانوني",
   comp:"15,000–45,000", demand:"mid",
   desc:"تقديم الاستشارات القانونية وتمثيل العملاء.",
   keys:["قانون","legal counsel","contract drafting","litigation","corporate law","commercial law","arbitration","legal compliance"],
   must:["قانون","legal","محامي"],
   suggest:["arbitration","intellectual property","corporate law"],
   companies:["وزارة العدل","هيئة التحقيق والادعاء العام","هيئة حسم","مكتب الشيخ سعود الزهراني للمحاماة","مكتب الراشد للمحاماة","مكتب Al Tamimi & Company","مكتب Baker McKenzie KSA","مكتب Freshfields KSA","مكتب White & Case KSA","أرامكو السعودية — الشؤون القانونية","سابك — الإدارة القانونية","البنك الأهلي السعودي","هيئة السوق المالية","وزارة التجارة"]},

  /* ══ 🏠 عقارات وسياحة ══ */
  {id:"realestate", cat:"real", icon:"🏠", title:"وسيط / مستشار عقاري",
   comp:"8,000–30,000+عمولة", demand:"high",
   desc:"إدارة وتسويق العقارات وتقديم الاستشارات.",
   keys:["عقارات","real estate brokerage","property management","real estate sales","property valuation","تطوير عقاري","investment properties"],
   must:["عقارات","real estate","property"],
   suggest:["property valuation","project marketing","crm system"],
   companies:["ROSHN — روشن","Dar Al Arkan — دار الأركان","إعمار المدينة الاقتصادية","شركة الرياض للتعمير","مجموعة بنيان العقارية","Aqar — منصة عقار","Bayut KSA","Property Finder KSA","JLL KSA","CBRE KSA","Savills KSA","Knight Frank KSA","شركة نيوم","شركة القدية Entertainment City","مشروع البحر الأحمر Red Sea Project","العلا للتطوير"]},

  /* ══ 🚚 لوجستيات وتوريد ══ */
  {id:"supply", cat:"log", icon:"🚚", title:"متخصص سلسلة التوريد",
   comp:"12,000–25,000", demand:"high",
   desc:"إدارة المشتريات والمستودعات وتدفق البضائع.",
   keys:["supply chain management","لوجستيات","procurement management","warehouse management","inventory control","erp system","logistics operations","vendor management"],
   must:["supply chain","لوجستيات","procurement"],
   suggest:["cpim","apics","sap scm"],
   companies:["أرامكو السعودية","سابك","Aramex KSA","DHL Supply Chain KSA","FedEx KSA","Nupco — الشركة الوطنية للتوريد","وزارة الصحة — اللوجستيات","مستشفى الملك فيصل التخصصي","Noon Logistics","Jollyes KSA","Almarai — المراعي","شركة البحري للشحن","عبدالله العثيم للتجارة","بنده","أسواق العثيم","Amazon KSA Logistics","SAP KSA"]},
];


var CAT_LABELS = {
  all:"الكل", net:"📡 شبكات وسيرفرات", dev:"💻 برمجة وتطوير",
  data:"📊 بيانات وذكاء اصطناعي", design:"🎨 تصميم وإبداع",
  mkt:"📣 تسويق ومبيعات", fin:"💰 مالي ومحاسبة",
  hr:"👥 موارد بشرية وإدارة", health:"🏥 صحة وطب",
  eng:"🏗️ هندسة وصناعة", edu:"📚 تعليم", legal:"⚖️ قانوني", real:"🏠 عقارات", log:"🚚 لوجستيات"
};

function matchJobs(d) {
  // Build comprehensive text from all CV fields
  var userText = [
    d.sk||"", d.exp||"", d.certs||"",
    d.spec||"", d.job||"", d.title||"",
    d.edu||"", d.summary||""
  ].join(" ").toLowerCase();
  var results = JOB_DB.map(function(job) {
    var keyHits = 0, mustHits = 0;
    job.keys.forEach(function(k) { if (wordMatch(userText, k)) keyHits++; });
    job.must.forEach(function(k) { if (wordMatch(userText, k)) mustHits++; });
    if (mustHits === 0) return {job:job, score:0};
    var maxScore = job.keys.length * 10 + job.must.length * 25;
    var rawScore = keyHits * 10 + mustHits * 25;
    var score = Math.round(Math.min((rawScore / maxScore) * 100, 100));
    if (mustHits >= 2) score = Math.min(score + 10, 100);
    if (mustHits >= 3) score = Math.min(score + 10, 100);
    return {job:job, score:score};
  });
  results.sort(function(a,b) { return b.score - a.score; });
  return results;
}

function getMissing(d, topJobs) {
  var userText = [d.sk||"", d.certs||"", d.spec||""].join(" ").toLowerCase();
  var missing = {};
  topJobs.slice(0,4).forEach(function(r) {
    r.job.suggest.forEach(function(s) { if (!wordMatch(userText, s)) missing[s] = true; });
  });
  return Object.keys(missing).slice(0,8);
}

window.showJobsPanel = function(d) {
  var panel = document.getElementById("jobs-panel");
  if (!panel) return;

  // Build rich userText from all CV fields
  var userText = [
    d.sk||"", d.exp||"", d.certs||"",
    d.spec||"", d.job||"", d.title||"",
    d.edu||"", d.summary||""
  ].join(" ").toLowerCase();

  var allResults = matchJobs(d);
  // Strict: score >= 30 is a real match, 20-29 is weak
  var topResults = allResults.filter(function(r) { return r.score >= 25; }).slice(0,12);

  panel.classList.add("on");

  // ── NO MATCH: show improvement panel ──────────────────────
  if (!topResults.length) {
    document.getElementById("match-bar-wrap").innerHTML =
      '<div class="no-jobs-panel">' +
        '<h4>🔍 لا يوجد اقتراح وظائف حسب مجال السيرة الحالية</h4>' +
        '<p>لم نتمكن من تحديد مجال واضح من بيانات سيرتك. إليك ما يمكنك تحسينه للحصول على اقتراحات دقيقة:</p>' +
        '<ul class="improve-list">' +
          '<li class="improve-item"><span class="ii">🎯</span><div><strong>أضف عنوان الوظيفة المستهدفة</strong> — مثل "مهندس شبكات" أو "محلل بيانات"</div></li>' +
          '<li class="improve-item"><span class="ii">💼</span><div><strong>أضف مهاراتك التقنية</strong> — مثل Python أو Cisco أو Excel</div></li>' +
          '<li class="improve-item"><span class="ii">📝</span><div><strong>اكتب خبرتك العملية</strong> — حتى لو كانت تدريباً أو مشاريع</div></li>' +
          '<li class="improve-item"><span class="ii">🏅</span><div><strong>أضف شهاداتك</strong> — CCNA أو PMP أو CPA وغيرها تساعد في التصنيف</div></li>' +
          '<li class="improve-item"><span class="ii">🎓</span><div><strong>اذكر تخصصك الدراسي</strong> — الهندسة أو المحاسبة أو الحاسوب...</div></li>' +
        '</ul>' +
      '</div>';
    document.getElementById("jobs-cats").innerHTML = "";
    document.getElementById("job-cards").innerHTML = "";
    var mb = document.getElementById("missing-box");
    if (mb) mb.style.display = "none";
    setTimeout(function() { panel.scrollIntoView({behavior:"smooth", block:"nearest"}); }, 200);
    return;
  }

  // ── MATCH FOUND ───────────────────────────────────────────
  var overallScore = topResults[0].score;
  var sc = overallScore >= 70 ? "mc-high" : overallScore >= 40 ? "mc-mid" : "mc-low";
  var sl = overallScore >= 70 ? "تطابق ممتاز" : overallScore >= 40 ? "تطابق جيد" : "تطابق محدود";
  document.getElementById("match-bar-wrap").innerHTML =
    '<div class="match-bar">' +
      '<div class="match-circle ' + sc + '">' + overallScore + '%</div>' +
      '<div class="match-info">' +
        '<h4>' + sl + " — " + topResults.length + " وظيفة مناسبة لسيرتك</h4>" +
        "<p>الاقتراحات مبنية على مهاراتك وخبراتك وشهاداتك الموجودة في السيرة.</p>" +
      "</div></div>";

  var cats = {all:true};
  topResults.forEach(function(r) { cats[r.job.cat] = true; });
  var catsEl = document.getElementById("jobs-cats");
  catsEl.innerHTML = "";

  function getWhyMatched(job, userTxt) {
    var hits = [];
    job.must.forEach(function(k) { if (wordMatch(userTxt, k)) hits.push(k); });
    return hits.slice(0,3);
  }

  function buildCards(cat) {
    catsEl.querySelectorAll(".jobs-cat").forEach(function(b) {
      b.classList.toggle("on", b.dataset.cat === cat);
    });
    var filtered = cat === "all" ? topResults : topResults.filter(function(r) { return r.job.cat === cat; });
    var grid = document.getElementById("job-cards");
    grid.innerHTML = "";

    if (!filtered.length) {
      grid.innerHTML = '<div style="grid-column:1/-1;text-align:center;padding:1.5rem;color:var(--ink3);font-size:.85rem;">لا توجد وظائف في هذا التصنيف ضمن نتائجك</div>';
      return;
    }

    filtered.slice(0,10).forEach(function(r, i) {
      var job = r.job;
      var dc = r.score >= 70 ? "jt-hi" : r.score >= 45 ? "jt-mi" : "jt-lo";
      var dl = r.score >= 70 ? "🔥 تطابق عالٍ" : r.score >= 45 ? "📈 تطابق جيد" : "📊 تطابق جزئي";
      var why = getWhyMatched(job, userText);
      var coList = job.companies ? job.companies.slice(0,6).join("  |  ") : "";
      // Missing skills for this specific job
      var missing = job.suggest ? job.suggest.filter(function(s) {
        return !wordMatch(userText, s);
      }).slice(0,3) : [];

      var card = document.createElement("div");
      card.className = "job-card" + (i === 0 && r.score >= 50 ? " top-match" : "");
      card.innerHTML =
        '<div class="jc-top">' +
          '<span class="jc-icon">' + job.icon + "</span>" +
          '<div style="flex:1">' +
            '<div class="jc-title">' + job.title + (i===0 && r.score>=70 ? " ⭐" : "") + "</div>" +
            '<div class="jc-comp">💵 ' + job.comp + " ر.س / شهر</div>" +
          "</div>" +
        "</div>" +
        (why.length ? '<div class="jc-why">✓ تطابق: ' + why.join("، ") + "</div>" : "") +
        '<div class="jc-tags">' +
          '<span class="jt jt-match">تطابق ' + r.score + "%</span>" +
          '<span class="jt ' + dc + '">' + dl + "</span>" +
          (job.demand === "high" ? '<span class="jt jt-hi">🔥 طلب عالٍ</span>' : "") +
        "</div>" +
        '<div class="jc-desc">' + job.desc + "</div>" +
        (coList ? '<div class="jc-companies"><strong>🏢 شركات توظف في هذا التخصص:</strong><br>' + coList + "</div>" : "") +
        (missing.length ? '<div style="margin-top:.45rem;font-size:.72rem;color:var(--ink3);">💡 أضف: ' + missing.map(function(m){ return '<strong>'+m+'</strong>'; }).join("، ") + " لتحسين فرصك</div>" : "") +
        '<div class="jc-footer">' +
          '<span class="jc-keys">' + job.keys.slice(0,3).join(" · ") + "</span>" +
          '<button class="jc-apply" onclick="searchJob(\'' + encodeURIComponent(job.title) + '\')">LinkedIn ←</button>' +
        "</div>";
      grid.appendChild(card);
    });
  }

  Object.keys(cats).forEach(function(cat) {
    var btn = document.createElement("button");
    btn.className = "jobs-cat" + (cat === "all" ? " on" : "");
    btn.dataset.cat = cat;
    btn.textContent = CAT_LABELS[cat] || cat;
    btn.onclick = function() { buildCards(cat); };
    catsEl.appendChild(btn);
  });
  buildCards("all");

  // Missing skills overall
  var missing = getMissing(d, topResults);
  var mb = document.getElementById("missing-box");
  var mp = document.getElementById("missing-pills");
  if (missing.length && mb && mp) {
    mp.innerHTML = missing.map(function(m) { return '<span class="mpill">+ ' + m + "</span>"; }).join("");
    mb.style.display = "block";
  } else if (mb) {
    mb.style.display = "none";
  }

  setTimeout(function() { panel.scrollIntoView({behavior:"smooth", block:"nearest"}); }, 200);
};

window.searchJob = function(title) {
  var q = decodeURIComponent(title);
  window.open("https://www.linkedin.com/jobs/search/?keywords=" + encodeURIComponent(q) + "&location=%D8%A7%D9%84%D8%B3%D8%B9%D9%88%D8%AF%D9%8A%D8%A9", "_blank");
};

/* ═══════════════════════════════════════════════════════
   AI CHAT
═══════════════════════════════════════════════════════ */
var KB = {
  ats:"نظام ATS يفلتر السير تلقائياً. للنجاح:\n✅ استخدم نفس الكلمات المفتاحية من الإعلان\n✅ تجنب الجداول والصور والألوان\n✅ عناوين قياسية: الخبرة، التعليم، المهارات\n✅ احفظ بصيغة PDF أو DOCX\n✅ لا تضع معلوماتك في header/footer",
  interview:"نصائح المقابلة:\n⭐ ابحث عن الشركة مسبقاً\n⭐ حضّر إجابة لـ 'عرّف عن نفسك'\n⭐ استخدم أسلوب STAR في إجاباتك\n⭐ ارتدِ ملابس رسمية مناسبة\n⭐ احضر مبكراً 10-15 دقيقة\n⭐ اسأل أسئلة ذكية عن الشركة",
  summary:"الملخص المهني (3-4 أسطر):\n1️⃣ مسماك ومجالك وسنوات خبرتك\n2️⃣ أبرز إنجاز أو مهارة\n3️⃣ هدفك المرتبط بالوظيفة\n\nمثال: 'مهندس شبكات 8 سنوات خبرة في stc وأرامكو. أدار شبكة 500+ جهاز. أهدف لقيادة بنية تحتية محترفة.'",
  jobs:"أكثر الوظائف طلباً 2025:\n🔥 محلل بيانات — رؤية 2030\n🔥 خبير شبكات وسيرفرات — طلب متصاعد\n🔥 متخصص ذكاء اصطناعي\n🔥 مدير تسويق رقمي\n🔥 مطور تطبيقات Flutter\n🔥 مهندس سحابي Cloud\n🔥 محاسب ومراجع مالي\n🔥 مدير مشاريع PMP",
  skills:"أهم مهارات الشبكات والسيرفرات:\n💻 Cisco CCNA/CCNP\n🖥️ Windows Server 2019/2022\n🐧 Linux Administration\n☁️ VMware vSphere, Azure, AWS\n🔒 Cybersecurity & Firewall\n📊 Network Monitoring (Zabbix)\n🗂️ Active Directory & DNS",
  beginner:"خبرتك محدودة؟ لا مشكلة!\n✨ ضع التعليم والشهادات في الأعلى\n✨ اذكر المشاريع والتدريب الميداني\n✨ اذكر الأعمال التطوعية\n✨ ركز على الشهادات التقنية (CCNA، MCSA)\n✨ أضف مشاريع GitHub حتى لو صغيرة",
  length:"الطول المثالي:\n📄 أقل من 5 سنوات: صفحة واحدة\n📄📄 5-15 سنة: صفحتان\n📄📄📄 قيادي: 3 صفحات كحد أقصى"
};

function getReply(msg) {
  var m = msg.toLowerCase();
  if (m.includes("ats") || m.includes("فلتر") || m.includes("رفض")) return KB.ats;
  if (m.includes("مقابل") || m.includes("interview")) return KB.interview;
  if (m.includes("ملخص") || m.includes("summary")) return KB.summary;
  if (m.includes("وظيف") || m.includes("طلب") || m.includes("سوق") || m.includes("مطلوب")) return KB.jobs;
  if (m.includes("مهار") || m.includes("skill") || m.includes("شبكات") || m.includes("سيرفر")) return KB.skills;
  if (m.includes("قليل") || m.includes("مبتدئ") || m.includes("خريج")) return KB.beginner;
  if (m.includes("طول") || m.includes("صفح")) return KB.length;
  if (m.includes("شكر") || m.includes("مرحب") || m.includes("هلا")) return "هلا وغلا! 😊 اسألني عن السير، الوظائف، المقابلات، أو أي شيء يخص التوظيف!";
  return "يسعدني مساعدتك! 💡\n\nأستطيع الإجابة عن:\n• نظام ATS\n• الوظائف المطلوبة\n• مهارات الشبكات والسيرفرات\n• المقابلات\n• كتابة الملخص المهني\n\nراسلنا: azooz.887m@gmail.com";
}

function addMsg(text, who) {
  var msgs = document.getElementById("msgs");
  var div = document.createElement("div");
  div.className = "msg " + (who === "me" ? "mme" : "mai");
  div.textContent = text;
  msgs.appendChild(div);
  msgs.scrollTop = msgs.scrollHeight;
}

window.sendMsg = function() {
  var inp = document.getElementById("cinp");
  var msg = inp.value.trim();
  if (!msg) return;
  inp.value = "";
  addMsg(msg, "me");
  var msgs = document.getElementById("msgs");
  var t = document.createElement("div");
  t.className = "msg mai"; t.id = "typ"; t.textContent = "...";
  msgs.appendChild(t); msgs.scrollTop = msgs.scrollHeight;
  setTimeout(function() {
    var el = document.getElementById("typ");
    if (el) el.remove();
    addMsg(getReply(msg), "ai");
  }, 500);
};

window.ask = function(q) {
  go("ai");
  setTimeout(function() { document.getElementById("cinp").value = q; window.sendMsg(); }, 150);
};

/* ═══════════════════════════════════════════════════════
   INIT
═══════════════════════════════════════════════════════ */
renderOrdList();
loadDraft();

})();
</script>
</body>
</html>

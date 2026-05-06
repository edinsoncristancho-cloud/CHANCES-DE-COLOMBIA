index.html
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="theme-color" content="#0a0a14">
<title>Chances Colombia</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root{
  --gold:#C9A84C;--gold-l:#F0CF82;--gold-d:#8A6E2E;
  --bg0:#06060f;--bg1:#0e0e1e;--bg2:#121224;--bg3:#1a1a30;
  --bdr:rgba(201,168,76,0.18);--bdrb:rgba(201,168,76,0.5);
  --tx:#e8e4d6;--txm:#7a7460;--txd:#3a3628;
  --gr:#2dd4a0;--bl:#5b9cf6;--pu:#9b7ef8;--co:#f07060;--pk:#e87fa0;--tl:#40c8b0;
  --r:12px;--rs:8px;
}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',sans-serif;background:var(--bg0);color:var(--tx);min-height:100vh;overflow-x:hidden}
body::before{content:'';position:fixed;inset:0;z-index:0;
  background:radial-gradient(ellipse 80% 50% at 20% 20%,rgba(201,168,76,.06) 0%,transparent 60%),
             radial-gradient(ellipse 60% 40% at 80% 80%,rgba(91,156,246,.05) 0%,transparent 60%);
  pointer-events:none}
.hdr{position:relative;z-index:10;text-align:center;padding:44px 20px 28px;border-bottom:.5px solid var(--bdr)}
.gem{display:inline-block;width:40px;height:40px;background:linear-gradient(135deg,var(--gold) 0%,var(--gold-l) 50%,var(--gold) 100%);clip-path:polygon(50% 0%,100% 38%,82% 100%,18% 100%,0% 38%);animation:gp 3s ease-in-out infinite;vertical-align:middle;margin-right:10px}
@keyframes gp{0%,100%{filter:brightness(1)}50%{filter:brightness(1.4) drop-shadow(0 0 10px rgba(201,168,76,.6))}}
.htitle{display:inline;font-family:'Cinzel',serif;font-size:clamp(20px,5vw,36px);font-weight:700;letter-spacing:4px;
  background:linear-gradient(135deg,var(--gold-d) 0%,var(--gold-l) 40%,var(--gold) 60%,var(--gold-d) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;text-transform:uppercase}
.hsub{font-size:12px;color:var(--txm);letter-spacing:3px;text-transform:uppercase;margin-top:8px}
.hdate{display:inline-block;margin-top:12px;font-size:11px;color:var(--gold-d);background:rgba(201,168,76,.08);border:.5px solid var(--bdr);border-radius:20px;padding:4px 16px;letter-spacing:1px}
.tabs{display:flex;justify-content:center;gap:4px;padding:14px 16px;background:rgba(0,0,0,.3);border-bottom:.5px solid var(--bdr);position:sticky;top:0;z-index:100;backdrop-filter:blur(20px);flex-wrap:wrap}
.tab{font-family:'DM Sans',sans-serif;font-size:13px;padding:7px 16px;border-radius:20px;border:.5px solid transparent;background:transparent;color:var(--txm);cursor:pointer;transition:all .2s;white-space:nowrap}
.tab:hover{color:var(--tx);background:var(--bg3)}
.tab.on{background:rgba(201,168,76,.12);border-color:var(--bdrb);color:var(--gold-l);font-weight:500}
.main{position:relative;z-index:1;padding:20px 14px;max-width:900px;margin:0 auto}
.sec{display:none}.sec.on{display:block}
.frow{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:18px;align-items:center}
.flbl{font-size:11px;color:var(--txm);letter-spacing:1px;text-transform:uppercase}
.fbtn{font-size:12px;padding:5px 14px;border-radius:20px;border:.5px solid var(--bdr);background:transparent;color:var(--txm);cursor:pointer;transition:all .15s;font-family:'DM Sans',sans-serif}
.fbtn:hover{background:var(--bg3);color:var(--tx)}
.fbtn.on{border-color:var(--gold-d);color:var(--gold-l);background:rgba(201,168,76,.1)}
.rgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:10px}
.rcard{background:var(--bg1);border:.5px solid var(--bdr);border-radius:var(--r);padding:14px;cursor:pointer;transition:all .2s;position:relative;overflow:hidden}
.rcard::before{content:'';position:absolute;left:0;top:0;bottom:0;width:3px;border-radius:3px 0 0 3px}
.rcard.tm::before{background:var(--gold)}
.rcard.td::before{background:var(--gr)}
.rcard.tt::before{background:var(--bl)}
.rcard.tn::before{background:var(--pu)}
.rcard:hover{border-color:var(--bdrb);background:var(--bg2);transform:translateY(-2px)}
.ctop{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:10px}
.cname{font-size:14px;font-weight:500;color:var(--tx)}
.ttag{font-size:10px;padding:2px 8px;border-radius:10px;font-weight:500;letter-spacing:.5px;text-transform:uppercase}
.tagm{background:rgba(201,168,76,.15);color:var(--gold)}
.tagt{background:rgba(45,212,160,.12);color:var(--gr)}
.tagT{background:rgba(91,156,246,.12);color:var(--bl)}
.tagn{background:rgba(155,126,248,.12);color:var(--pu)}
.digs{display:flex;gap:4px;margin-bottom:6px}
.dig{width:34px;height:38px;display:flex;align-items:center;justify-content:center;font-family:'DM Mono',monospace;font-size:20px;font-weight:500;border-radius:6px;background:rgba(201,168,76,.08);border:.5px solid var(--bdr);color:var(--gold-l);transition:all .2s}
.rcard:hover .dig{background:rgba(201,168,76,.14);border-color:var(--bdrb)}
.cmeta{font-size:11px;color:var(--txm)}
.cpills{display:flex;flex-wrap:wrap;gap:5px;margin-bottom:16px}
.cpill{font-size:11px;padding:4px 11px;border-radius:20px;border:.5px solid var(--bdr);background:transparent;color:var(--txm);cursor:pointer;transition:all .15s;font-family:'DM Sans',sans-serif}
.cpill:hover{background:var(--bg3);color:var(--tx)}
.cpill.on{background:rgba(201,168,76,.12);border-color:var(--bdrb);color:var(--gold-l);font-weight:500}
.mrow{display:flex;gap:5px;flex-wrap:wrap;margin-bottom:16px;align-items:center}
.mlbl{font-size:11px;color:var(--txm);letter-spacing:1px;text-transform:uppercase}
.mbtn{font-size:10px;padding:3px 9px;border-radius:20px;border:.5px solid var(--bdr);background:transparent;color:var(--txm);cursor:pointer;transition:all .12s;font-family:'DM Sans',sans-serif}
.mbtn.on{font-weight:500}
.mc0.on{background:rgba(201,168,76,.12);border-color:rgba(201,168,76,.4);color:var(--gold)}
.mc1.on{background:rgba(45,212,160,.1);border-color:rgba(45,212,160,.4);color:var(--gr)}
.mc2.on{background:rgba(91,156,246,.1);border-color:rgba(91,156,246,.4);color:var(--bl)}
.mc3.on{background:rgba(155,126,248,.1);border-color:rgba(155,126,248,.4);color:var(--pu)}
.mc4.on{background:rgba(240,112,96,.1);border-color:rgba(240,112,96,.4);color:var(--co)}
.mc5.on{background:rgba(64,200,176,.1);border-color:rgba(64,200,176,.4);color:var(--tl)}
.mc6.on{background:rgba(232,127,160,.1);border-color:rgba(232,127,160,.4);color:var(--pk)}
.mc7.on{background:rgba(91,156,246,.08);border-color:rgba(91,156,246,.3);color:#a0c4f8}
.apanel{background:var(--bg1);border:.5px solid var(--bdr);border-radius:var(--r);padding:18px;margin-bottom:12px;animation:fi .3s ease}
@keyframes fi{from{opacity:0;transform:translateY(6px)}to{opacity:1;transform:translateY(0)}}
.ptitle{font-family:'Cinzel',serif;font-size:12px;letter-spacing:2px;color:var(--gold-d);text-transform:uppercase;margin-bottom:14px}
.pgrid4{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;margin-bottom:14px}
.pbox{background:var(--bg2);border:.5px solid var(--bdr);border-radius:var(--rs);padding:10px 6px;text-align:center}
.pblbl{font-size:9px;color:var(--txm);letter-spacing:1px;text-transform:uppercase;margin-bottom:4px}
.pbf{font-family:'DM Mono',monospace;font-size:24px;font-weight:500;color:var(--gold)}
.pbc{font-size:8px;color:var(--txm);margin-bottom:4px}
.pbt{font-family:'DM Mono',monospace;font-size:18px;color:var(--gr)}
.pbtl{font-size:8px;color:var(--txm)}
.ebox{background:linear-gradient(135deg,rgba(201,168,76,.1) 0%,rgba(201,168,76,.04) 100%);border:1px solid rgba(201,168,76,.3);border-radius:var(--r);padding:14px 18px;display:flex;align-items:center;justify-content:space-between;margin-bottom:14px}
.elbl{font-size:10px;color:var(--gold-d);text-transform:uppercase;letter-spacing:1.5px;margin-bottom:4px}
.enum{font-family:'DM Mono',monospace;font-size:30px;font-weight:500;letter-spacing:6px;color:var(--gold-l);text-shadow:0 0 20px rgba(201,168,76,.4)}
.epts{font-family:'DM Mono',monospace;font-size:20px;font-weight:500;color:var(--gold)}
.esc{font-size:10px;color:var(--gold-d)}
.ctitle{font-size:10px;color:var(--txm);letter-spacing:1.5px;text-transform:uppercase;margin-bottom:10px}
.cgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(175px,1fr));gap:7px;margin-bottom:16px}
.ccard{background:var(--bg2);border:.5px solid var(--bdr);border-radius:var(--rs);padding:10px;transition:all .15s}
.ccard.r1{border-color:rgba(201,168,76,.5);background:rgba(201,168,76,.05)}
.ccard:hover{border-color:var(--bdrb);background:var(--bg3)}
.chdr{display:flex;align-items:center;gap:5px;margin-bottom:7px}
.crk{font-size:10px;color:var(--txm);min-width:16px}
.crk.gd{color:var(--gold);font-weight:500}
.cnum{font-family:'DM Mono',monospace;font-size:20px;font-weight:500;letter-spacing:3px;color:var(--gold-l)}
.cpts{margin-left:auto;font-size:9px;color:var(--txm);background:rgba(255,255,255,.04);border:.5px solid var(--bdr);border-radius:3px;padding:1px 5px}
.cbars{display:flex;flex-direction:column;gap:2px}
.brow{display:flex;align-items:center;gap:4px;font-size:9px}
.blbl{min-width:44px;color:var(--txm)}
.btrk{flex:1;height:3px;background:rgba(255,255,255,.05);border-radius:2px}
.bfil{height:100%;border-radius:2px;transition:width .3s}
.bval{min-width:18px;text-align:right;color:var(--txm)}
.mdgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(195px,1fr));gap:8px}
.mdcard{border-left:2px solid transparent;padding-left:8px}
.mdcard strong{display:block;font-size:11px;font-weight:500;color:var(--tx);margin-bottom:2px}
.mdcard span{font-size:10px;color:var(--txm);line-height:1.5}
.lgrow{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:12px}
.lgitem{display:flex;align-items:center;gap:4px;font-size:10px;color:var(--txm)}
.lgdot{width:8px;height:8px;border-radius:2px;flex-shrink:0}
.sgrid{display:grid;grid-template-columns:repeat(auto-fill,minmax(130px,1fr));gap:8px;margin-bottom:16px}
.sbox{background:var(--bg1);border:.5px solid var(--bdr);border-radius:var(--rs);padding:14px;text-align:center}
.sblbl{font-size:9px;color:var(--txm);letter-spacing:1px;text-transform:uppercase;margin-bottom:6px}
.sbval{font-family:'DM Mono',monospace;font-size:24px;font-weight:500;color:var(--gold)}
.fbars{display:flex;flex-direction:column;gap:5px}
.frow2{display:flex;align-items:center;gap:8px;font-size:12px}
.fdig{min-width:16px;font-family:'DM Mono',monospace;font-weight:500;color:var(--tx)}
.ftrk{flex:1;height:5px;background:rgba(255,255,255,.05);border-radius:3px}
.ffil{height:100%;border-radius:3px;background:linear-gradient(90deg,var(--gold-d),var(--gold))}
.fcnt{min-width:40px;text-align:right;color:var(--txm);font-size:11px}
.footer{text-align:center;padding:28px 20px;border-top:.5px solid var(--bdr);font-size:11px;color:var(--txd);letter-spacing:1px}
::-webkit-scrollbar{width:4px}::-webkit-scrollbar-track{background:var(--bg0)}::-webkit-scrollbar-thumb{background:var(--bdrb);border-radius:2px}
@media(max-width:480px){.tabs{justify-content:flex-start;overflow-x:auto}.tab{font-size:12px;padding:6px 12px}.enum{font-size:22px}.cnum{font-size:16px;letter-spacing:2px}}
</style>
</head>
<body>
<header class="hdr">
  <div><div class="gem"></div><span class="htitle">Chances Colombia</span></div>
  <p class="hsub">Analisis &middot; Candidatos &middot; Estadisticas</p>
  <div class="hdate" id="fecha"></div>
</header>
<nav class="tabs">
  <button class="tab on" onclick="showTab('resultados',this)">Resultados</button>
  <button class="tab" onclick="showTab('analisis',this)">Analisis</button>
  <button class="tab" onclick="showTab('candidatos',this)">Candidatos</button>
  <button class="tab" onclick="showTab('stats',this)">Stats</button>
</nav>
<main class="main">
  <div id="tab-resultados" class="sec on">
    <div class="frow">
      <span class="flbl">Turno</span>
      <button class="fbtn on" onclick="filtrar('',this)">Todos</button>
      <button class="fbtn" onclick="filtrar('manana',this)">Manana</button>
      <button class="fbtn" onclick="filtrar('dia',this)">Dia</button>
      <button class="fbtn" onclick="filtrar('tarde',this)">Tarde</button>
      <button class="fbtn" onclick="filtrar('noche',this)">Noche</button>
    </div>
    <div class="rgrid" id="rgrid"></div>
  </div>
  <div id="tab-analisis" class="sec">
    <div class="cpills" id="pills-a"></div>
    <div id="analisis-out"></div>
  </div>
  <div id="tab-candidatos" class="sec">
    <div class="cpills" id="pills-c"></div>
    <div class="mrow" id="mrow"></div>
    <div id="cands-out"></div>
  </div>
  <div id="tab-stats" class="sec">
    <div id="stats-out"></div>
  </div>
</main>
<footer class="footer">Datos: loteriasdehoy.co &middot; Solo informativo &middot; v3.1</footer>
<script>
const DB={
  doradom:{name:"Dorado Manana",t:"manana",h:["9579","5768","0745","9347","2995","7717","1070","2664","7793","4833","4399","5701","1861","1614","5703","5011","7411","7835","0327","7496"],fp:[["7",260],["4",258],["5",262],["7",263]],td:["3","2","8","2"]},
  doradon:{name:"Dorado Noche",t:"noche",h:["5562","8420","4767","0250","4205","7544","5142","3308","0288","4004","6715","4076","0226","6769","5770","2885","4772","8805","2921","7108","3568","7872","6452"],fp:[["5",255],["5",260],["6",248],["2",258]],td:["3","1","4","7"]},
  doradot:{name:"Dorado Tarde",t:"tarde",h:["9924","1592","0392","4971","7989","8662","0275","8123","4634","6243","9302","6983","8134","9516","7057","5687","1776","9044","6562","9863"],fp:[["1",259],["5",267],["8",250],["4",255]],td:["2","4","5","8"]},
  sinuanod:{name:"Sinuano Dia",t:"dia",h:["5131","1979","9012","6626","9385","9645","6726","6672","3706","1266","9247","3862","4350","9754","1336","4587","8010","0727","2852","1942"],fp:[["3",316],["4",311],["3",303],["2",327]],td:["7","4","9","3"]},
  sinuanon:{name:"Sinuano Noche",t:"noche",h:["6037","9748","2708","2658","6599","2649","6057","1456","0874","5981","1183","2472","9342","0087","2478","6768","4752","1049","8024","8618","6327","6324","1180","2290","2995","9098","4981","6744","4252","9346"],fp:[["2",304],["9",316],["2",314],["8",320]],td:["7","2","1","5"]},
  chonticod:{name:"Chontico Dia",t:"dia",h:["0402","8549","4299","1062","9061","7457","8141","8292","2153","0679","7452","5632","9065","8561","2412","7369","2265","3458","1628","4711"],fp:[["7",313],["8",322],["5",333],["5",323]],td:["6","8","8","4"]},
  chonticoN:{name:"Chontico Noche",t:"noche",h:["0806","0480","4748","9842","1271","1674","1163","1295","8461","3039","6050","0951","7568","2056","8691","1608","0830","9876","9961","7467"],fp:[["4",312],["8",308],["3",313],["1",296]],td:["5","3","2","7"]},
  paisitad:{name:"Paisita Dia",t:"dia",h:["2389","3544","3514","2797","0316","9793","9342","3818","7377","9448","9989","6802","9914","3407","7769","7177","6237","1721","0763","2745"],fp:[["2",310],["7",308],["7",305],["2",312]],td:["9","8","2","6"]},
  paisitan:{name:"Paisita Noche",t:"noche",h:["1000","7534","6371","0100","7364","4704","1169","0663","1273","4465","7565","7088","4532","5292","0989","1452","1303","8330","4207","1857"],fp:[["3",326],["9",307],["2",310],["8",312]],td:["9","8","2","6"]},
  caribenad:{name:"Caribena Dia",t:"dia",h:["5172","8221","4648","0684","3177","0782","5866","2489","7301","8443","3720","3020","7301","0683","7922","4242","5828","4103","5843","4353"],fp:[["4",299],["5",316],["6",308],["6",328]],td:["6","5","3","5"]},
  caribenan:{name:"Caribena Noche",t:"noche",h:["3599","5774","3837","3252","9937","7475","3248","1046","7155","7562","6852","8704","2030","5641","5909","8318","8607","9613","0433","8352"],fp:[["4",302],["4",309],["6",315],["3",308]],td:["4","3","8","3"]},
  culonad:{name:"Culona Dia",t:"dia",h:["7765","6402","2923","8153","5383","3206","1758","4412","7152","1226","9819","3409","2251","7498","1536","3540","3265","8146","6316","9503"],fp:[["5",229],["7",225],["4",232],["5",228]],td:["4","0","2","3"]},
  culonan:{name:"Culona Noche",t:"noche",h:["3078","4684","0788","3079","7773","4469","6826","6284","9905","1562","1680","4340","6231","9562","3890","3263","7224","7542","0949","4662"],fp:[["0",221],["2",218],["8",225],["1",220]],td:["5","1","3","6"]},
  cafetT:{name:"Cafeterito Tarde",t:"tarde",h:["6410","0638","8809","3316","4573","1483","5042","6674","5116","0795","8788","3165","8671","6435","8546","7281","5342","9087","2614","3758"],fp:[["6",298],["5",290],["4",302],["5",295]],td:["2","3","1","0"]},
  cafetN:{name:"Cafeterito Noche",t:"noche",h:["7175","8895","8489","9108","7007","2717","2560","0121","1836","4887","3420","9299","7063","0869","9474","3398","6251","1405","8162","0027"],fp:[["5",302],["8",309],["4",314],["4",300]],td:["5","6","4","2"]},
  astroluna:{name:"Astro Luna",t:"noche",h:["3789","3195","8381","5259","1230","9331","2696","0533","0868","3777","6922","7867","5009","8247","7548","1705","5736","1013","6593","9037","7087","7414","9721","8158","5341","1054","1400","0669","0082","2759","6117","7417","4417","8735","0253","9094","9924","4515","2393","9682","6001","2828","9472","9649","8779","3703","8097","0496","5149","3512"],fp:[["2",310],["6",320],["7",327],["8",312]],td:["4","4","1","4"]},
  astrosol:{name:"Astro Sol",t:"tarde",h:["1207","3679","3278","5498","2469","0878","5163","5376","1250","2007","5650","0977","4657","9544","8555","3702","0989","9505","5168","6977"],fp:[["5",254],["6",273],["7",255],["9",285]],td:["7","7","3","1"]},
  antioq1:{name:"Antioqueñita 1",t:"manana",h:["7067","5525","6186","7572","9620","8216","7410","3799","1704","3472","0803","0130","7231","0898","5025","4136","2417","1913","1436","8667"],fp:[["1",342],["4",313],["1",316],["6",307]],td:["2","3","4","8"]},
  antioq2:{name:"Antioqueñita 2",t:"tarde",h:["0479","2696","7668","3838","9250","6752","1092","5266","2423","7173","5123","3378","0237","5377","8116","7576","0366","1194","6680","8014"],fp:[["3",300],["5",305],["4",310],["5",308]],td:["4","1","3","6"]},
  pijaod:{name:"Pijao de Oro",t:"dia",h:["1728","2133","7793","8048","3514","3261","7670","8780","8831","4568","2735","0359","1652","0337","1052","4397","7504","3064","3396","6357"],fp:[["0",280],["2",290],["1",275],["0",285]],td:["5","6","4","3"]},
  saman:{name:"Samana",t:"dia",h:["9682","9935","4663","6316","7089","1081","6552","0854","4923","3703","7661","2607","9588","2134","5517","9681","3953","5841","2591","0194"],fp:[["6",312],["6",294],["3",298],["8",303]],td:["8","2","7","0"]},
  motilont:{name:"Motilon Tarde",t:"tarde",h:["3820","1184","6139","9919","0586","6701","5360","0719","6166","9434","4696","7570","3642","9219","1903","3620","8535","6192","1390","1011"],fp:[["4",244],["7",243],["0",242],["0",237]],td:["2","0","5","7"]},
  motilonN:{name:"Motilon Noche",t:"noche",h:["4593","6845","7229","6346","8247","4077","5771","1766","4130","1769","4945","1209","9794","0409","8373","0695","9384","3093","0813","2805"],fp:[["3",235],["8",245],["2",242],["4",252]],td:["2","6","5","2"]},
  fantasticad:{name:"Fantastica Dia",t:"dia",h:["7023","2812","0734","7281","1375","9266","0389","3968","4657","6113","4376","6638","4628","6307","6821","0090","8032","7112","7016","2033"],fp:[["2",240],["7",250],["9",244],["7",249]],td:["5","4","4","1"]},
  fantasticanN:{name:"Fantastica Noche",t:"noche",h:["6100","9716","1737","8402","1777","9022","7000","9717","5898","4176","6233","2337","2321","6859","0840","0603","7511","8282","7413","1750"],fp:[["3",296],["4",292],["8",316],["0",293]]  ,td:["3","9","6","5"]},
};
const RES={doradom:"9579",doradon:"5562",doradot:"9924",sinuanod:"5131",sinuanon:"6037",chonticod:"0402",chonticoN:"0806",paisitad:"2389",paisitan:"1000",caribenad:"5172",caribenan:"3599",culonad:"7765",culonan:"3078",cafetT:"6410",cafetN:"7175",astroluna:"3789",astrosol:"1207",antioq1:"7067",antioq2:"0479",pijaod:"1728",saman:"9682",motilont:"3820",motilonN:"4593",fantasticad:"7023",fantasticanN:"6100"};
const PESOS=[1.5,1.3,1.2,1.0,0.8,1.1,1.4,1.0];
const MCOL=["#C9A84C","#2dd4a0","#5b9cf6","#9b7ef8","#f07060","#40c8b0","#e87fa0","#a0c4f8"];
const MLBL=["Frec.G","Tard.","Markov","Ciclos","Entrop.","Tend.","Frec.P","Caliente"];
const MNMS=["Frecuencia Global x1.5","Tardanza x1.3","Markov x1.2","Ciclos x1.0","Entropia x0.8","Tendencia x1.1","Frec. Posicion x1.4","Caliente x1.0"];
const MDSC=["Digitos que mas aparecen en el historial, sin importar posicion.","Digitos ausentes hace mas sorteos. Mayor ausencia = mayor probabilidad.","Cadenas de Markov: probabilidad de que un digito siga al anterior.","Detecta repeticion en ciclos de 5, 7, 10, 14 o 21 sorteos.","Favorece combinaciones variadas sobre numeros con digitos repetidos.","Digitos en alza en los ultimos 10 sorteos vs. los 10 anteriores.","Frecuencia de cada digito en su posicion exacta (1,2,3,4).","Coincidencias por posicion con los ultimos 5 resultados."];
const ACT=[true,true,true,true,true,true,true,true];
let selA="doradom",selC="doradom",filtro="";
function fD(h){const f={};h.forEach(n=>n.split("").forEach(d=>{f[d]=(f[d]||0)+1}));return f;}
function fPD(h){const f=[];for(let p=0;p<4;p++){const fp={};h.forEach(n=>{const d=n[p];fp[d]=(fp[d]||0)+1;});f.push(fp);}return f;}
function s0(n,h){const f=fD(h),t=h.length*4;let s=0;n.split("").forEach(d=>s+=(f[d]||0)/t);return Math.round(s*25);}
function s1(n,h){let s=0;n.split("").forEach(d=>{const i=h.findIndex(x=>x.includes(d));s+=i<0?20:Math.min(20,i);});return Math.round(s/4*1.5);}
function s2(n,h){const tr={};h.forEach(x=>{for(let i=0;i<3;i++){const k=x[i];tr[k]=tr[k]||{};tr[k][x[i+1]]=(tr[k][x[i+1]]||0)+1;}});let s=0;for(let i=0;i<3;i++){const a=n[i],b=n[i+1],row=tr[a]||{},t=Object.values(row).reduce((x,y)=>x+y,0)||1;s+=(row[b]||0)/t;}return Math.round(s*30);}
function s3(n,h){let s=0;[5,7,10,14,21].forEach(c=>{if(h[c]===n)s+=12;if(h[c*2]===n)s+=8;});return Math.min(35,s);}
function s4(n){const d=n.split(""),u=new Set(d).size,p=d.slice(0,-1).filter((x,i)=>x===d[i+1]).length;return Math.round((u*5)-(p*3)+10);}
function s5(n,h){const r=h.slice(0,10),o=h.slice(10,20);let s=0;n.split("").forEach(d=>{const ri=r.filter(x=>x.includes(d)).length,oi=o.filter(x=>x.includes(d)).length+1;s+=(ri/oi)*5;});return Math.round(s);}
function s6(n,h){const fp=fPD(h),t=h.length;let s=0;for(let p=0;p<4;p++){s+=((fp[p][n[p]]||0)/t)*25;}return Math.round(s);}
function s7(n,h){const r=h.slice(0,5);let s=0;r.forEach((x,i)=>{let m=0;for(let p=0;p<4;p++)if(x[p]===n[p])m++;s+=m*(5-i)*2;});return Math.round(s);}
function scoreN(num,data){const h=data.h,raw=[s0(num,h),s1(num,h),s2(num,h),s3(num,h),s4(num),s5(num,h),s6(num,h),s7(num,h)];let t=0;raw.forEach((v,i)=>{if(ACT[i])t+=v*PESOS[i];});return{raw,total:Math.round(t)};}
function estrellaD(data){const fp=fPD(data.h);return[0,1,2,3].map(p=>Object.entries(fp[p]).sort((a,b)=>b[1]-a[1])[0][0]).join("");}
function top10(id){
  const data=DB[id],h=data.h,cands=new Set();
  h.forEach(n=>{cands.add(n);cands.add(n.split("").reverse().join(""));[1111,2222,3333,5678,1234,4321].forEach(d=>cands.add(String((parseInt(n)+d)%10000).padStart(4,"0")));for(let i=0;i<4;i++){const a=n.split("");a[i]=String((parseInt(a[i])+1)%10);cands.add(a.join(""));const b=n.split("");b[i]=String((parseInt(b[i])+9)%10);cands.add(b.join(""));}});
  const fp=data.fp,td=data.td;
  [fp[0][0]+fp[1][0]+fp[2][0]+fp[3][0],td[0]+td[1]+td[2]+td[3],fp[0][0]+td[1]+fp[2][0]+td[3],td[0]+fp[1][0]+td[2]+fp[3][0],fp[0][0]+fp[1][0]+td[2]+td[3],td[0]+td[1]+fp[2][0]+fp[3][0]].forEach(n=>cands.add(n));
  for(let i=0;i<300;i++)cands.add(String(Math.abs(parseInt(h[i%h.length])*7+i*13)%10000).padStart(4,"0"));
  const sc=[...cands].map(n=>({num:n,...scoreN(n,data)}));sc.sort((a,b)=>b.total-a.total);return sc.slice(0,10);
}
function digs(n){return n.split("").map(d=>`<div class="dig">${d}</div>`).join("");}
function renderResultados(){
  const ids=Object.keys(DB).filter(id=>!filtro||DB[id].t===filtro);
  const tMap={manana:"Manana",dia:"Dia",tarde:"Tarde",noche:"Noche"};
  const tcls={manana:"tagm",dia:"tagt",tarde:"tagT",noche:"tagn"};
  const rcls={manana:"tm",dia:"td",tarde:"tt",noche:"tn"};
  document.getElementById("rgrid").innerHTML=ids.map(id=>{
    const d=DB[id],num=RES[id]||d.h[0]||"----";
    return `<div class="rcard ${rcls[d.t]}" onclick="irA('${id}')">
      <div class="ctop"><div class="cname">${d.name}</div><span class="ttag ${tcls[d.t]}">${tMap[d.t]}</span></div>
      <div class="digs">${digs(num)}</div>
      <div class="cmeta">Ultimo sorteo &middot; ${d.h.length} en historial</div>
    </div>`;
  }).join("");
}
function filtrar(t,btn){filtro=t;document.querySelectorAll(".fbtn").forEach(b=>b.classList.remove("on"));btn.classList.add("on");renderResultados();}
function irA(id){selA=id;selC=id;showTab("analisis",document.querySelectorAll(".tab")[1]);setTimeout(()=>{renderPills("pills-a","a",id);renderAnalisis();},50);}
function renderPills(el,tipo,sel){document.getElementById(el).innerHTML=Object.keys(DB).map(id=>`<button class="cpill${sel===id?" on":""}" onclick="pick('${tipo}','${id}')">${DB[id].name}</button>`).join("");}
function pick(tipo,id){if(tipo==="a"){selA=id;renderPills("pills-a","a",id);renderAnalisis();}else{selC=id;renderPills("pills-c","c",id);renderCands();}}
function renderAnalisis(){
  const data=DB[selA],h=data.h,fp=fPD(h),freq=fD(h);
  const sorted=Object.entries(freq).sort((a,b)=>b[1]-a[1]),maxF=sorted[0][1];
  const rec=h.slice(0,5),old=h.slice(5,10);
  document.getElementById("analisis-out").innerHTML=`
  <div class="apanel">
    <div class="ptitle">Analisis por posicion &mdash; ${data.name}</div>
    <div class="pgrid4">${[0,1,2,3].map(p=>`<div class="pbox"><div class="pblbl">Pos ${p+1}</div><div class="pbf">${data.fp[p][0]}</div><div class="pbc">${data.fp[p][1]}x</div><div class="pbt">${data.td[p]}</div><div class="pbtl">demorado</div></div>`).join("")}</div>
    <div class="ptitle">Frecuencia de digitos</div>
    <div class="fbars">${sorted.map(([d,f])=>`<div class="frow2"><span class="fdig">${d}</span><div class="ftrk"><div class="ffil" style="width:${Math.round(f/maxF*100)}%"></div></div><span class="fcnt">${f}</span></div>`).join("")}</div>
  </div>
  <div class="apanel">
    <div class="ptitle">Ultimos 10 resultados</div>
    <div style="display:flex;flex-direction:column;gap:7px">${h.slice(0,10).map((n,i)=>`<div style="display:flex;align-items:center;gap:8px"><span style="font-size:10px;color:var(--txm);min-width:18px">${i+1}</span><div style="display:flex;gap:4px">${n.split("").map(dg=>`<div class="dig" style="width:30px;height:34px;font-size:17px">${dg}</div>`).join("")}</div>${i<5?'<span style="font-size:9px;background:rgba(45,212,160,.1);color:var(--gr);border-radius:4px;padding:1px 5px">reciente</span>':""}</div>`).join("")}</div>
  </div>
  <div class="apanel">
    <div class="ptitle">Tendencia reciente vs anterior</div>
    <div style="display:flex;gap:6px;flex-wrap:wrap">${[0,1,2,3,4,5,6,7,8,9].map(d=>{const r=rec.filter(n=>n.includes(d)).length,o=old.filter(n=>n.includes(d)).length;const t=r>o?"&#9650;":r<o?"&#9660;":"&rarr;";const c=r>o?"var(--gr)":r<o?"var(--co)":"var(--txm)";return`<div style="text-align:center;min-width:42px;background:var(--bg2);border:.5px solid var(--bdr);border-radius:8px;padding:7px 5px"><div style="font-family:'DM Mono',monospace;font-size:16px;font-weight:500;color:var(--tx)">${d}</div><div style="font-size:14px;color:${c}">${t}</div><div style="font-size:9px;color:var(--txm)">${r}/${o}</div></div>`;}).join("")}</div>
  </div>`;
}
function renderMRow(){document.getElementById("mrow").innerHTML='<span class="mlbl">Metodos</span>'+MNMS.map((n,i)=>`<button class="mbtn on mc${i}" onclick="togM(${i},this)">${MLBL[i]}</button>`).join("");}
function togM(i,btn){ACT[i]=!ACT[i];btn.classList.toggle("on",ACT[i]);renderCands();}
function renderCands(){
  const data=DB[selC],t10=top10(selC),star=estrellaD(data),starSc=scoreN(star,data);
  const fp=data.fp,td=data.td,aktiv=ACT.map((a,i)=>a?i:-1).filter(i=>i>=0);
  let html=`<div class="apanel">
    <div class="ptitle">Numero estrella &mdash; ${data.name}</div>
    <div class="ebox">
      <div><div class="elbl">Frecuencia por posicion</div><div class="enum">${star}</div></div>
      <div style="text-align:right"><div class="elbl">Score</div><div class="epts">${starSc.total}</div><div class="esc">puntos</div></div>
    </div>
    <div class="pgrid4">${[0,1,2,3].map(p=>`<div class="pbox"><div class="pblbl">Pos ${p+1}</div><div class="pbf">${fp[p][0]}</div><div class="pbc">${fp[p][1]}x</div><div class="pbt">${td[p]}</div><div class="pbtl">demorado</div></div>`).join("")}</div>
    <div class="ctitle">Top 10 candidatos &middot; ${data.h.length} sorteos reales</div>
    <div class="cgrid">`;
  t10.forEach((c,i)=>{
    const maxV=Math.max(...aktiv.map(k=>Math.round(c.raw[k]*PESOS[k])),1);
    html+=`<div class="ccard${i===0?" r1":""}"><div class="chdr"><span class="crk${i===0?" gd":""}">#${i+1}</span><span class="cnum">${c.num}</span><span class="cpts">${c.total}pts</span></div><div class="cbars">`;
    aktiv.forEach(k=>{const v=Math.round(c.raw[k]*PESOS[k]),w=Math.round(v/maxV*100);html+=`<div class="brow"><span class="blbl">${MLBL[k]}</span><div class="btrk"><div class="bfil" style="width:${w}%;background:${MCOL[k]}"></div></div><span class="bval">${v}</span></div>`;});
    html+=`</div></div>`;
  });
  html+=`</div></div>
  <div class="apanel">
    <div class="ptitle">Los 8 metodos aplicados</div>
    <div class="lgrow">${MNMS.map((n,i)=>`<span class="lgitem"><span class="lgdot" style="background:${MCOL[i]}"></span>${MLBL[i]}</span>`).join("")}</div>
    <div class="mdgrid">${MNMS.map((n,i)=>`<div class="mdcard" style="border-color:${MCOL[i]}"><strong>${n}</strong><span>${MDSC[i]}</span></div>`).join("")}</div>
  </div>`;
  document.getElementById("cands-out").innerHTML=html;
}
function renderStats(){
  const total=Object.keys(DB).length;
  const tr={manana:0,dia:0,tarde:0,noche:0};Object.values(DB).forEach(d=>tr[d.t]++);
  const af={};Object.values(DB).forEach(d=>d.h.forEach(n=>n.split("").forEach(dg=>{af[dg]=(af[dg]||0)+1})));
  const sf=Object.entries(af).sort((a,b)=>b[1]-a[1]),mf=sf[0][1];
  document.getElementById("stats-out").innerHTML=`
  <div class="sgrid">
    <div class="sbox"><div class="sblbl">Total chances</div><div class="sbval">${total}</div></div>
    <div class="sbox"><div class="sblbl">Manana</div><div class="sbval" style="color:var(--gold)">${tr.manana}</div></div>
    <div class="sbox"><div class="sblbl">Dia</div><div class="sbval" style="color:var(--gr)">${tr.dia}</div></div>
    <div class="sbox"><div class="sblbl">Tarde</div><div class="sbval" style="color:var(--bl)">${tr.tarde}</div></div>
    <div class="sbox"><div class="sblbl">Noche</div><div class="sbval" style="color:var(--pu)">${tr.noche}</div></div>
    <div class="sbox"><div class="sblbl">Metodos</div><div class="sbval">8</div></div>
  </div>
  <div class="apanel">
    <div class="ptitle">Digito mas frecuente &mdash; todos los chances</div>
    <div class="fbars">${sf.map(([d,f])=>`<div class="frow2"><span class="fdig">${d}</span><div class="ftrk"><div class="ffil" style="width:${Math.round(f/mf*100)}%"></div></div><span class="fcnt">${f.toLocaleString()}</span></div>`).join("")}</div>
  </div>
  <div class="apanel" style="margin-top:10px">
    <div class="ptitle">Numero estrella por chance</div>
    <div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(195px,1fr));gap:7px">${Object.keys(DB).map(id=>{const d=DB[id],star=estrellaD(d);return`<div style="display:flex;align-items:center;justify-content:space-between;background:var(--bg2);border:.5px solid var(--bdr);border-radius:8px;padding:9px 12px"><span style="font-size:12px;color:var(--txm)">${d.name}</span><span style="font-family:'DM Mono',monospace;font-size:16px;color:var(--gold);letter-spacing:2px">${star}</span></div>`;}).join("")}</div>
  </div>`;
}
function showTab(id,btn){
  document.querySelectorAll(".sec").forEach(s=>s.classList.remove("on"));
  document.querySelectorAll(".tab").forEach(b=>b.classList.remove("on"));
  document.getElementById("tab-"+id).classList.add("on");
  if(btn)btn.classList.add("on");
  if(id==="analisis"){renderPills("pills-a","a",selA);renderAnalisis();}
  if(id==="candidatos"){renderPills("pills-c","c",selC);renderMRow();renderCands();}
  if(id==="stats")renderStats();
}
(function init(){
  const d=new Date();
  const dias=["Dom","Lun","Mar","Mie","Jue","Vie","Sab"];
  const meses=["enero","febrero","marzo","abril","mayo","junio","julio","agosto","septiembre","octubre","noviembre","diciembre"];
  document.getElementById("fecha").textContent=dias[d.getDay()]+" "+d.getDate()+" de "+meses[d.getMonth()]+" de "+d.getFullYear();
  renderResultados();
})();
</script>
</body>
</html>

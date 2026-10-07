<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Sopaan · Radical Functions and Equations</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,500;9..144,700&family=Source+Sans+3:wght@400;600;700&family=IBM+Plex+Mono:wght@500;600&display=swap">
<style>
  html,body{margin:0;} img{max-width:100%;} [hidden]{display:none !important;}
  :root{
    --navy:#16264A; --navy-2:#1F3B6B; --gold:#C79A3E; --gold-soft:#F3E7C9;
    --paper:#FBF9F4; --paper-2:#F1EAD8; --card:#FFFFFF;
    --ink:#211E1A; --ink-soft:#655D4C; --rule:#E4DCC8;
    --success:#2E8B57; --success-soft:#E1F2E7;
    --danger:#BF4B45; --danger-soft:#FAE3E1;
    --locked:#C7BEA9;
    --focus:#1F3B6B;
    --accent-text:#1F3B6B; --retry-text:#8A661F;
    color-scheme:light;
  }
  @media (prefers-color-scheme: dark){
    :root:not([data-theme="light"]){
      --navy:#0E1830; --navy-2:#16264A; --gold:#E0B75B; --gold-soft:#3A2F16;
      --paper:#141210; --paper-2:#1C1914; --card:#1C1914;
      --ink:#EDE7DA; --ink-soft:#B2A996; --rule:#3A342A;
      --success:#7BC79A; --success-soft:#1B2E22;
      --danger:#E38884; --danger-soft:#331D1B;
      --locked:#4A4436;
      --focus:#E0B75B;
      --accent-text:#E0B75B; --retry-text:#E0B75B;
      color-scheme:dark;
    }
  }
  :root[data-theme="dark"]{
    --navy:#0E1830; --navy-2:#16264A; --gold:#E0B75B; --gold-soft:#3A2F16;
    --paper:#141210; --paper-2:#1C1914; --card:#1C1914;
    --ink:#EDE7DA; --ink-soft:#B2A996; --rule:#3A342A;
    --success:#7BC79A; --success-soft:#1B2E22;
    --danger:#E38884; --danger-soft:#331D1B;
    --locked:#4A4436;
    --focus:#E0B75B;
    --accent-text:#E0B75B; --retry-text:#E0B75B;
    color-scheme:dark;
  }

  *{box-sizing:border-box;}
  body{background:var(--paper); color:var(--ink); font-family:'Source Sans 3',-apple-system,'Segoe UI',sans-serif; padding-inline:0; padding-block:0;}
  h1,h2,h3{font-family:'Fraunces',Georgia,serif; text-wrap:balance; margin:0;}
  .num{font-family:'IBM Plex Mono',ui-monospace,monospace; font-variant-numeric:tabular-nums;}

  header.brand{
    background:linear-gradient(155deg,var(--navy) 0%, var(--navy-2) 100%);
    color:#F4EFDF; padding-block:calc(20px + env(safe-area-inset-top,0px)) 18px; padding-inline:20px;
  }
  .brand-row{display:flex; align-items:center; gap:12px; max-width:900px; margin:0 auto;}
  .crest{
    width:42px; height:42px; border-radius:10px; background:var(--gold); color:var(--navy);
    display:flex; align-items:center; justify-content:center; font-family:'Fraunces',serif; font-weight:700; font-size:18px; flex-shrink:0;
  }
  .brand-name{font-size:12px; letter-spacing:.08em; text-transform:uppercase; color:var(--gold); font-weight:700;}
  .series-name{font-size:19px; font-weight:700; font-family:'Fraunces',serif;}
  .chapter-eyebrow{max-width:900px; margin:14px auto 0; font-size:12px; letter-spacing:.06em; text-transform:uppercase; color:#AEB9D6;}
  .chapter-title{font-size:28px; max-width:900px; margin:2px auto 0;}
  .chapter-sub{font-size:14.5px; color:var(--gold); font-weight:700; max-width:900px; margin:3px auto 0;}

  .chapter-progress{max-width:900px; margin:14px auto 0; display:flex; align-items:center; gap:10px;}
  .cp-track{flex:1; height:6px; border-radius:99px; background:rgba(255,255,255,.18); overflow:hidden;}
  .cp-fill{height:100%; background:var(--gold); border-radius:99px; transition:width .3s ease;}
  .cp-label{font-size:11.5px; color:#CFD7EA; white-space:nowrap;}

  .tabbar{position:sticky; top:env(safe-area-inset-top,0px); z-index:15; background:var(--paper); border-bottom:1px solid var(--rule); overflow-x:auto; white-space:nowrap;}
  .tabbar-inner{max-width:900px; margin:0 auto; display:flex; padding-inline:16px;}
  .tab-btn{font-family:inherit; font-size:14px; font-weight:600; color:var(--ink-soft); background:none; border:none; padding:13px 16px; cursor:pointer; position:relative; flex-shrink:0;}
  .tab-btn.active{color:var(--accent-text);}
  .tab-btn.active::after{content:''; position:absolute; left:12px; right:12px; bottom:0; height:3px; background:var(--gold); border-radius:3px 3px 0 0;}
  .tab-count{font-size:11px; color:var(--ink-soft); margin-left:5px;}

  .slide-progress{max-width:900px; margin:0 auto; padding:10px 16px 0; display:flex; align-items:center; gap:10px;}
  .sp-track{flex:1; height:5px; border-radius:99px; background:var(--rule); overflow:hidden;}
  .sp-fill{height:100%; background:var(--accent-text); border-radius:99px; transition:width .3s ease;}
  .sp-label{font-size:12px; color:var(--ink-soft); white-space:nowrap; font-weight:600;}

  .wrap{max-width:900px; margin:0 auto; padding:16px 16px calc(110px + env(safe-area-inset-bottom,0px));}

  .qcard{background:var(--card); border:1px solid var(--rule); border-radius:14px; padding:18px;}
  .qhead{display:flex; align-items:flex-start; gap:10px; margin-bottom:10px;}
  .qnum{width:32px; height:32px; border-radius:8px; background:var(--gold-soft); color:var(--accent-text); display:flex; align-items:center; justify-content:center; font-weight:700; font-family:'Fraunces',serif; flex-shrink:0; font-size:14px;}
  .qtext{font-size:16px; line-height:1.55; flex:1;}
  .qtag{font-size:10.5px; color:var(--gold); background:var(--gold-soft); padding:2px 7px; border-radius:99px; font-weight:700; margin-left:6px; white-space:nowrap;}
  .marks-pill{font-size:11px; font-weight:700; color:var(--ink-soft); border:1px solid var(--rule); padding:3px 9px; border-radius:99px; margin-left:auto; flex-shrink:0; white-space:nowrap;}
  .step-badge{font-size:11px; font-weight:700; color:var(--accent-text); background:var(--paper-2); border:1px solid var(--rule); padding:3px 9px; border-radius:99px; display:inline-block; margin-bottom:12px;}

  .options{display:flex; flex-direction:column; gap:8px; margin-top:10px;}
  .opt{display:flex; align-items:center; gap:10px; padding:11px 12px; border:1.5px solid var(--rule); border-radius:10px; cursor:pointer; font-size:15px; background:var(--paper);}
  .opt input{accent-color:var(--navy-2);}
  .opt.is-correct{border-color:var(--success); background:var(--success-soft);}
  .opt.is-wrong{border-color:var(--danger); background:var(--danger-soft);}
  .opt.locked{cursor:not-allowed;}

  .subpart-label{font-weight:700; font-size:12.5px; color:var(--accent-text); text-transform:uppercase; letter-spacing:.03em; margin:14px 0 6px;}
  .or-divider{text-align:center; font-size:11px; font-weight:700; letter-spacing:.08em; color:var(--ink-soft); margin:8px 0;}

  .steps{display:flex; flex-direction:column; gap:10px;}
  .step-line{font-size:14.5px; line-height:1.9; background:var(--paper); border:1px dashed var(--rule); border-radius:10px; padding:9px 12px;}
  .step-line.resolved{opacity:.9;}
  .blank-input{font-family:'IBM Plex Mono',monospace; font-size:14px; border:1.5px solid var(--rule); border-radius:6px; padding:3px 8px; width:120px; background:var(--card); color:var(--ink); margin:0 2px;}
  .blank-input:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 3px var(--gold-soft);}
  .blank-input.is-correct{border-color:var(--success); background:var(--success-soft);}
  .blank-input.is-wrong{border-color:var(--danger); background:var(--danger-soft);}
  .blank-input[disabled]{opacity:.85;}
  .reveal-note{font-size:12px; color:var(--danger); padding-left:2px; margin-top:-2px;}

  .feedback{font-size:13.5px; padding:10px 12px; border-radius:9px; margin-top:14px; display:none;}
  .feedback.show{display:block;}
  .feedback.ok{background:var(--success-soft); color:var(--success);}
  .feedback.retry{background:var(--gold-soft); color:var(--retry-text);}
  .feedback.reveal{background:var(--danger-soft); color:var(--danger);}
  .feedback.err{background:var(--danger-soft); color:var(--danger);}
  .attempts-dots{display:inline-flex; gap:4px; margin-left:2px;}
  .attempts-dots span{width:6px; height:6px; border-radius:50%; background:var(--ink-soft); opacity:.3; display:inline-block;}
  .attempts-dots span.used{opacity:1; background:var(--danger);}

  .ar-box{background:var(--paper-2); border-radius:10px; padding:10px 12px; margin-bottom:12px; font-size:13px; color:var(--ink-soft);}

  .navbar{
    position:fixed; left:0; right:0; bottom:0; z-index:30; background:var(--paper);
    border-top:1px solid var(--rule); padding:10px 16px calc(10px + env(safe-area-inset-bottom,0px));
  }
  .navbar-inner{max-width:900px; margin:0 auto; display:flex; gap:8px; flex-wrap:wrap; align-items:center;}
  .btn{font-family:inherit; font-size:13.5px; font-weight:700; padding:10px 14px; border-radius:9px; border:1.5px solid var(--rule); background:var(--card); color:var(--ink); cursor:pointer;}
  .btn:hover{border-color:var(--navy-2);}
  .btn:disabled{opacity:.4; cursor:not-allowed;}
  .btn-primary{background:var(--navy-2); color:#fff; border-color:var(--navy-2);}
  .navbar .spacer{flex:1;}

  .fab{position:fixed; right:16px; bottom:calc(74px + env(safe-area-inset-bottom,0px)); background:var(--gold); color:var(--navy); border:none; border-radius:999px; padding:11px 16px; font-family:inherit; font-weight:700; font-size:13px; display:flex; align-items:center; gap:7px; cursor:pointer; box-shadow:0 6px 16px rgba(0,0,0,.18); z-index:35;}
  .fab-badge{background:rgba(255,255,255,.55); border-radius:99px; padding:1px 7px; font-size:11px;}

  .overlay{position:fixed; inset:0; background:rgba(20,18,14,.45); z-index:50; display:none; align-items:flex-end; justify-content:center;}
  .overlay.show{display:flex;}
  .palette{background:var(--card); width:min(480px,100%); max-height:78vh; overflow-y:auto; border-radius:18px 18px 0 0; padding:18px 18px calc(18px + env(safe-area-inset-bottom,0px)); border:1px solid var(--rule); border-bottom:none;}
  @media (min-width:640px){ .overlay{align-items:center;} .palette{border-radius:18px; border-bottom:1px solid var(--rule); max-height:74vh;} }
  .palette-head{display:flex; align-items:center; justify-content:space-between; margin-bottom:6px;}
  .palette-head h2{font-size:16px;}
  .palette-close{background:none; border:none; font-size:20px; color:var(--ink-soft); cursor:pointer; padding:4px;}
  .palette-legend{display:flex; gap:12px; flex-wrap:wrap; font-size:11px; color:var(--ink-soft); margin:10px 0 14px;}
  .palette-legend span{display:inline-flex; align-items:center; gap:5px;}
  .dot{width:9px; height:9px; border-radius:50%; display:inline-block;}
  .dot.correct{background:var(--success);} .dot.revealed{background:var(--danger);}
  .dot.skipped{background:var(--gold);} .dot.locked{background:var(--locked);}
  .dot.current{background:var(--navy-2);}
  .chip-grid{display:grid; grid-template-columns:repeat(auto-fill,minmax(48px,1fr)); gap:8px;}
  .chip{border:1.5px solid var(--rule); border-radius:9px; padding:8px 4px; text-align:center; font-family:'IBM Plex Mono',monospace; font-size:12.5px; font-weight:600; cursor:pointer; background:var(--paper); color:var(--ink);}
  .chip[data-status="correct"]{border-color:var(--success); background:var(--success-soft); color:var(--success);}
  .chip[data-status="revealed"]{border-color:var(--danger); background:var(--danger-soft); color:var(--danger);}
  .chip[data-status="skipped"]{border-color:var(--gold); background:var(--gold-soft); color:var(--retry-text);}
  .chip[data-status="locked"]{border-color:var(--rule); color:var(--locked); cursor:not-allowed; background:var(--paper-2);}
  .chip[data-status="current"]{outline:2px solid var(--navy-2); outline-offset:1px;}

  .toast{position:fixed; left:50%; bottom:calc(140px + env(safe-area-inset-bottom,0px)); transform:translateX(-50%); background:var(--ink); color:var(--paper); padding:9px 16px; border-radius:99px; font-size:13px; opacity:0; pointer-events:none; transition:opacity .25s ease; z-index:60;}
  .toast.show{opacity:1;}

  .done-card{text-align:center; padding:36px 20px;}
  .done-card .big{font-size:38px; margin-bottom:6px;}
  .score-pills{display:flex; gap:10px; justify-content:center; flex-wrap:wrap; margin:16px 0;}
  .score-pill{padding:8px 16px; border-radius:99px; font-size:13px; font-weight:700;}

  footer.brandfoot{max-width:900px; margin:14px auto 0; padding:0 16px calc(110px + env(safe-area-inset-bottom,0px)); text-align:center; font-size:12px; color:var(--ink-soft);}

  .mode-pill{font-family:inherit; font-size:12.5px; font-weight:700; color:var(--navy); background:var(--gold); border:none; border-radius:99px; padding:6px 14px; cursor:pointer; margin-top:12px; display:inline-flex; align-items:center; gap:6px;}
  .mode-pick{display:flex; flex-direction:column; gap:14px; padding:8px 0 24px;}
  .mode-card{background:var(--card); border:1.5px solid var(--rule); border-radius:16px; padding:22px; cursor:pointer; text-align:left;}
  .mode-card:hover{border-color:var(--navy-2);}
  .mode-card .mode-icon{font-size:26px; margin-bottom:8px;}
  .mode-card h3{font-size:18px; margin-bottom:6px;}
  .mode-card p{font-size:13.5px; color:var(--ink-soft); line-height:1.5; margin:0;}
  .quiz-hint{font-size:12.5px; color:var(--ink-soft); background:var(--paper-2); border-radius:9px; padding:8px 12px; margin-bottom:14px;}
  .review-row{border:1px solid var(--rule); border-radius:10px; padding:11px 13px; margin-bottom:10px;}
  .review-tag{font-size:11.5px; font-weight:700; margin-bottom:4px; display:block;}
  .review-tag.ok{color:var(--success);} .review-tag.bad{color:var(--danger);} .review-tag.na{color:var(--ink-soft);}
  .review-q{font-size:13.5px; margin-bottom:6px; color:var(--ink-soft);}
  .review-ans{font-size:13px; margin-bottom:2px;}

  .who-row{max-width:900px; margin:12px auto 0; display:flex; flex-wrap:wrap; gap:8px; align-items:center;}
  .who-row .mode-pill{margin-top:0;}
  .who{display:inline-flex; flex-wrap:wrap; align-items:center; gap:6px; font-size:12.5px; color:#CFD7EA;}
  .who b{color:#F4EFDF;}
  .who button{font-family:inherit; font-size:12px; font-weight:700; color:#F4EFDF; background:rgba(255,255,255,.12); border:1px solid rgba(255,255,255,.22); border-radius:99px; padding:5px 11px; cursor:pointer;}
  .who button:hover{background:rgba(255,255,255,.2);}
  .login-card{max-width:460px; margin:8px auto 0; background:var(--card); border:1px solid var(--rule); border-radius:16px; padding:22px;}
  .login-card h2{font-size:21px; margin-bottom:4px;}
  .login-card p.lead{font-size:13.5px; color:var(--ink-soft); margin:0 0 16px; line-height:1.5;}
  .fld{display:flex; flex-direction:column; gap:5px; margin-bottom:12px;}
  .fld label{font-size:12px; font-weight:700; letter-spacing:.04em; text-transform:uppercase; color:var(--ink-soft);}
  .fld input{font-family:inherit; font-size:15px; padding:10px 12px; border:1.5px solid var(--rule); border-radius:9px; background:var(--paper); color:var(--ink);}
  .fld input:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 3px var(--gold-soft);}
  .fld-row{display:grid; grid-template-columns:1fr 1fr; gap:10px;}
  .login-err{font-size:13px; color:var(--danger); background:var(--danger-soft); border-radius:8px; padding:8px 10px; margin-bottom:12px;}
  .login-note{font-size:12px; color:var(--ink-soft); margin-top:12px; line-height:1.5;}
  .known{margin:0 0 16px; display:flex; flex-direction:column; gap:6px;}
  .known-label{font-size:12px; font-weight:700; letter-spacing:.04em; text-transform:uppercase; color:var(--ink-soft);}
  .known-btn{display:flex; justify-content:space-between; align-items:center; gap:10px; text-align:left; font-family:inherit; font-size:14.5px; padding:10px 12px; border:1.5px solid var(--rule); border-radius:10px; background:var(--paper); color:var(--ink); cursor:pointer;}
  .known-btn:hover{border-color:var(--navy-2);}
  .known-btn small{font-size:12px; color:var(--ink-soft);}
  .rec-card{background:var(--card); border:1px solid var(--rule); border-radius:14px; padding:18px; margin-bottom:14px;}
  .rec-card h2{font-size:19px; margin-bottom:10px;}
  .rec-card h3{font-size:15px; margin:4px 0 8px;}
  .rec-table-wrap{overflow-x:auto;}
  .rec-table{width:100%; border-collapse:collapse; font-size:13.5px; font-variant-numeric:tabular-nums;}
  .rec-table th{text-align:left; font-size:11.5px; text-transform:uppercase; letter-spacing:.04em; color:var(--ink-soft); padding:6px 8px; border-bottom:1px solid var(--rule); white-space:nowrap;}
  .rec-table td{padding:8px; border-bottom:1px solid var(--rule); white-space:nowrap;}
  .rec-bar{display:inline-block; width:70px; height:6px; border-radius:99px; background:var(--rule); overflow:hidden; vertical-align:middle; margin-right:6px;}
  .rec-bar i{display:block; height:100%; background:var(--success);}
  .rec-empty{font-size:13.5px; color:var(--ink-soft);}
  .sec-sub{max-width:900px; margin:0 auto; padding:10px 16px 0; font-size:12.5px; font-weight:700; color:var(--accent-text); letter-spacing:.02em;}
  .opt{flex-wrap:wrap;}
  .opt-l{font-family:'IBM Plex Mono',monospace; font-size:13px; font-weight:600; color:var(--ink-soft);}
  .opt-t{flex:1; min-width:0;}
  .opt.is-chosen:not(.is-correct):not(.is-wrong){border-color:var(--navy-2); background:var(--gold-soft);}
  .opt-tag{font-size:11px; font-weight:700; padding:2px 8px; border-radius:99px; background:var(--card); border:1px solid currentColor; white-space:nowrap;}
  .opt.is-correct .opt-tag{color:var(--success);} .opt.is-wrong .opt-tag{color:var(--danger);} .opt.is-chosen:not(.is-correct):not(.is-wrong) .opt-tag{color:var(--accent-text);}
  .chosen{font-size:13.5px; margin-top:10px; padding:8px 12px; border-radius:9px;}
  .chosen.ok{background:var(--success-soft); color:var(--success);} .chosen.bad{background:var(--danger-soft); color:var(--danger);}
  .chosen + .chosen{margin-top:6px;}
  .solution{margin-top:14px; border:1px solid var(--rule); border-left:4px solid var(--gold); background:var(--paper-2); border-radius:10px; padding:12px 14px;}
  .sol-h{font-family:'Fraunces',Georgia,serif; font-weight:700; font-size:14px; color:var(--accent-text); margin-bottom:6px;}
  .sol-line{font-size:14.5px; line-height:1.7;}
  .rev-sol summary{cursor:pointer; font-size:12.5px; font-weight:700; color:var(--accent-text); margin-top:6px;}
  .rev-sol .solution{margin-top:8px;}
  .chapter-credit{max-width:900px; margin:4px auto 0; font-size:12px; color:#CFD7EA;}
  footer.brandfoot a{color:inherit;}
  .blank-input.wide{width:260px; max-width:100%; font-family:'Source Sans 3',sans-serif;}
  .blank-input.expr{width:170px; max-width:100%;}
  /*fix-layout*/ .cp-fill,.sp-fill{width:0;} .fld{min-width:0;} .fld input{width:100%; min-width:0; box-sizing:border-box;}
  .fig{margin:6px 0 10px; display:flex; justify-content:center;}
  .figsvg{width:100%; max-width:340px; height:auto; overflow:visible;}
  .figsvg .ln,.figsvg .arm{stroke:var(--ink); stroke-width:1.6; fill:none;}
  .figsvg .arm{stroke:var(--accent-text); stroke-width:2;}
  .figsvg .pt{fill:var(--ink);}
  .figsvg .lb{fill:var(--ink); font:600 13px 'Source Sans 3',sans-serif;}
  .figsvg .al{fill:var(--accent-text); font:700 12px 'Source Sans 3',sans-serif;}
  .figsvg .wg{fill:var(--gold-soft); stroke:var(--gold); stroke-width:1.2;}
  .figsvg .wg2{fill:rgba(199,154,62,.35); stroke:var(--gold); stroke-width:1.2;}
  .figsvg .ra{fill:none; stroke:var(--ink); stroke-width:1.2;}
  .figsvg .ahd{fill:var(--ink);}
  .figsvg .pr{fill:var(--paper-2); stroke:var(--ink-soft); stroke-width:1.2;}
  .figsvg .tk{stroke:var(--ink-soft); stroke-width:.8;}
  .figsvg .po{fill:var(--ink); font:600 8.5px 'IBM Plex Mono',monospace;}
  .figsvg .pi{fill:var(--danger); font:600 7.5px 'IBM Plex Mono',monospace;}
  .figsvg .sh{fill:var(--gold-soft); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .sh2{fill:rgba(199,154,62,.38); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .sh3{fill:rgba(199,154,62,.22); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .none{fill:none;}
  .figsvg .hid{stroke-dasharray:5 4; fill:none;}
  .figsvg .tick{stroke:var(--ink); stroke-width:1.4; fill:none;}
  .figsvg .shd{fill:var(--accent-text); fill-opacity:.55;}
  .figsvg .cell{fill:var(--card); stroke:var(--ink); stroke-width:1.1;}
  .figsvg .dr{fill:var(--danger);} .figsvg .dw{fill:var(--card); stroke:var(--ink); stroke-width:1.2;}
  .figsvg .dotfill{fill:var(--danger);}
  .tt{border-collapse:collapse; font-size:13.5px; margin:4px auto; font-variant-numeric:tabular-nums;} .tt th,.tt td{border:1px solid var(--rule); padding:4px 9px; text-align:left;} .tt th{background:var(--paper-2); font-weight:700;} .ttw{overflow-x:auto; max-width:100%;}
  .fq{display:inline-flex; flex-direction:column; vertical-align:middle; text-align:center; font-size:.82em; line-height:1.12; margin:0 2px;}
  .fq>span:first-child{border-bottom:1.5px solid currentColor; padding:0 2px;}
  .fq>span:last-child{padding:0 2px;}
  .mx{white-space:nowrap;}
  .blank-input.fr{width:110px;}
  @media (prefers-reduced-motion:reduce){ *{transition:none !important;} }
.datline{display:block;margin-top:8px;padding:8px 10px;border-radius:8px;background:var(--paper-2);font:500 14px/1.7 'IBM Plex Mono',monospace;word-spacing:2px;overflow-wrap:anywhere;}

  .theory{display:flex;flex-direction:column;gap:16px;padding-bottom:40px;}
  .hub{display:grid;grid-template-columns:1fr;gap:12px;}
  @media (min-width:640px){ .hub{grid-template-columns:repeat(3,1fr);} }
  .hub-card{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:16px;display:flex;flex-direction:column;gap:8px;}
  .hub-card h3{font-family:'Fraunces',serif;font-size:18px;margin:0;color:var(--accent-text);}
  .hub-card p{margin:0;font-size:14px;color:var(--ink-soft);line-height:1.5;}
  .hub-btns{display:flex;flex-wrap:wrap;gap:8px;margin-top:auto;}
  .hub-btn{min-height:40px;border:1.5px solid var(--rule);background:var(--paper-2);color:var(--ink);border-radius:10px;padding:8px 12px;font:600 14px 'Source Sans 3',sans-serif;cursor:pointer;text-align:left;}
  .hub-btn:hover{border-color:var(--gold);}
  .hub-btn.primary{background:var(--navy);color:#F4EFDF;border-color:var(--navy);}
  .note{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:18px;scroll-margin-top:120px;}
  .note h2{font-family:'Fraunces',serif;font-size:22px;margin:0 0 4px;color:var(--ink);}
  .note .lt{font-size:13.5px;color:var(--ink-soft);margin:0 0 12px;}
  .note .lt b{color:var(--accent-text);}
  .note h4{font:700 15px 'Source Sans 3',sans-serif;margin:16px 0 6px;color:var(--accent-text);}
  .note p,.note li{font-size:15.5px;line-height:1.6;}
  .note ul{padding-left:20px;margin:6px 0;}
  .keybox{background:var(--gold-soft);border-left:4px solid var(--gold);border-radius:8px;padding:10px 12px;margin:10px 0;font-size:15px;line-height:1.6;}
  .keybox b{color:var(--ink);}
  .ex{background:var(--paper-2);border-radius:10px;padding:12px;margin:10px 0;}
  .ex .exh{font-family:'Fraunces',serif;font-weight:700;color:var(--accent-text);margin-bottom:4px;}
  .ex .exl{font-size:15px;line-height:1.7;}
  .ttab{width:100%;border-collapse:collapse;font-size:14.5px;margin:8px 0;}
  .ttab th,.ttab td{border:1px solid var(--rule);padding:7px 8px;text-align:left;vertical-align:top;}
  .ttab th{background:var(--paper-2);}
  .tscroll{overflow-x:auto;}
  .mono{font-family:'IBM Plex Mono',monospace;font-size:.92em;}
  @media (max-width:480px){ .ttab{font-size:13.5px;} .ttab th,.ttab td{padding:6px;} }
  .note .figsvg{max-width:100%;height:auto;display:block;margin:8px auto;}


  .rep-top{display:flex;flex-wrap:wrap;gap:18px;align-items:center;justify-content:center;margin-top:8px;}
  .rep-legend{flex:1;min-width:220px;display:flex;flex-direction:column;gap:8px;}
  .rep-cap{font:700 13px 'Source Sans 3',sans-serif;color:var(--ink-soft);text-transform:uppercase;letter-spacing:.05em;}
  .rep-li{display:flex;align-items:center;gap:6px;font-size:15px;}
  .rep-n{margin-left:auto;white-space:nowrap;padding-left:8px;font-family:'IBM Plex Mono',monospace;font-weight:600;}
  .sw{display:inline-block;width:12px;height:12px;border-radius:3px;flex:none;}
  .rep-grid{display:grid;grid-template-columns:1fr;gap:12px;}
  @media (min-width:640px){ .rep-grid{grid-template-columns:1fr 1fr;} }
  .rep-card{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:14px;display:flex;flex-direction:column;gap:10px;}
  .rep-h{display:flex;align-items:center;gap:8px;font:700 16px 'Source Sans 3',sans-serif;}
  .crit{display:inline-grid;place-items:center;width:28px;height:28px;border-radius:50%;color:var(--card);font:700 15px Fraunces,serif;flex:none;}
  .rep-row{display:flex;gap:14px;align-items:center;}
  .rep-stats{display:flex;flex-direction:column;gap:5px;font-size:14.5px;}
  .rep-stats div{display:flex;align-items:center;gap:6px;}
  .rep-lvl{margin-top:4px;color:var(--accent-text);} .rep-lvl span{color:var(--ink-soft);font-size:13px;}
  .rep-note{font-size:13px;color:var(--ink-soft);}


  .skip-chips{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;margin:12px 0;}
  .skip-chips .chip{min-width:48px;min-height:40px;cursor:pointer;border:1.5px solid var(--gold);background:var(--gold-soft);color:var(--retry-text);border-radius:10px;font:600 14px 'IBM Plex Mono',monospace;}
  .skip-btns{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;margin-top:12px;}


  .kb-toggle{border:none;background:transparent;font-size:15px;cursor:pointer;padding:0 2px;vertical-align:middle;opacity:.7;}
  .vkb{position:fixed;left:0;right:0;bottom:0;z-index:80;background:var(--paper-2);border-top:1px solid var(--rule);box-shadow:0 -6px 20px rgba(0,0,0,.12);padding:6px 6px 8px;display:none;}
  .vkb.show{display:block;}
  .vkb-top{display:flex;justify-content:space-between;align-items:center;max-width:640px;margin:0 auto 4px;font:600 12px 'Source Sans 3',sans-serif;color:var(--ink-soft);}
  .vkb-link{border:none;background:none;color:var(--accent-text);font:600 12px 'Source Sans 3',sans-serif;cursor:pointer;text-decoration:underline;}
  .vkb-row{display:flex;gap:5px;max-width:640px;margin:0 auto 5px;}
  .vkb-k{flex:1;min-height:42px;border:1px solid var(--rule);border-radius:8px;background:var(--card);color:var(--ink);font:600 17px 'IBM Plex Mono',monospace;cursor:pointer;padding:0;}
  .vkb-k.fn{font:600 13px 'Source Sans 3',sans-serif;background:var(--gold-soft);}
  .vkb-k.done{background:var(--navy);color:#F4EFDF;border-color:var(--navy);}
  .vkb-k:active{transform:scale(.96);}
  body.kb-open .wrap{padding-bottom:360px;}
  body.kb-open .fab{display:none;}
  .tool-bar{display:flex;gap:8px;flex-wrap:wrap;margin:-4px 0 10px;}
  .tool-btn{min-height:36px;border:1.5px solid var(--gold);background:var(--gold-soft);color:var(--ink);border-radius:18px;padding:4px 12px;font:600 13.5px 'Source Sans 3',sans-serif;cursor:pointer;}
  .tool-panel{position:fixed;z-index:85;background:var(--card);border:1px solid var(--rule);border-radius:14px;box-shadow:0 10px 30px rgba(0,0,0,.25);display:none;}
  .tool-panel.show{display:block;}
  .tp-head{display:flex;align-items:center;gap:8px;padding:8px 10px;border-bottom:1px solid var(--rule);font:600 14px 'Source Sans 3',sans-serif;}
  .tp-note{font-size:12px;color:var(--ink-soft);font-weight:500;}
  .tp-x{margin-left:auto;border:1px solid var(--rule);background:var(--paper-2);color:var(--ink);border-radius:8px;min-height:32px;padding:2px 10px;cursor:pointer;font:600 13px 'Source Sans 3',sans-serif;}
  .tp-x + .tp-x{margin-left:0;}
  .calc{right:12px;bottom:84px;width:min(330px,calc(100vw - 24px));}
  body.calc-open .wrap{padding-bottom:440px;}
  body.calc-open .fab{display:none;}
  @media (max-width:640px){ .calc{left:6px;right:6px;width:auto;} .calc-keys button{min-height:36px;} }
  .calc-disp{padding:8px 12px;text-align:right;background:var(--paper-2);}
  .calc-expr{font:500 13px 'IBM Plex Mono',monospace;color:var(--ink-soft);min-height:18px;word-break:break-all;}
  .calc-res{font:600 24px 'IBM Plex Mono',monospace;color:var(--ink);word-break:break-all;}
  .calc-keys{display:grid;grid-template-columns:repeat(6,1fr);gap:5px;padding:8px;}
  .calc-keys button{min-height:40px;border:1px solid var(--rule);border-radius:8px;background:var(--card);color:var(--ink);font:600 14px 'IBM Plex Mono',monospace;cursor:pointer;padding:0;}
  .calc-keys button.fn{background:var(--gold-soft);font-family:'Source Sans 3',sans-serif;font-size:13px;}
  .calc-keys button.eq{grid-column:span 2;background:var(--navy);color:#F4EFDF;border-color:var(--navy);}
  .desmos{left:50%;top:50%;transform:translate(-50%,-50%);width:min(760px,calc(100vw - 16px));height:min(560px,calc(100vh - 90px));flex-direction:column;}
  .desmos.show{display:flex;}
  #desmosBox{flex:1;min-height:0;border-radius:0 0 14px 14px;overflow:hidden;}
  .desmos-msg{padding:24px;text-align:center;color:var(--ink-soft);}
  .chip[data-status="skipped"]{cursor:pointer;}
  .chip[data-status="answered"]{border-color:var(--accent-text);color:var(--accent-text);}


  button.crest-home{border:none;padding:0;position:relative;cursor:pointer;transition:transform .15s ease;}
  button.crest-home:hover,button.crest-home:focus-visible{transform:scale(1.06);outline:2px solid var(--gold);outline-offset:2px;}
  .crest-h{position:absolute;right:-7px;bottom:-7px;width:18px;height:18px;border-radius:50%;background:#F4EFDF;color:var(--navy);font:700 12px/18px 'Source Sans 3',sans-serif;text-align:center;box-shadow:0 1px 3px rgba(0,0,0,.3);}
  .brand .brand-row{position:relative;}
  .bmasw{position:absolute;left:50%;top:50%;transform:translate(-50%,-50%);display:flex;flex-shrink:0;white-space:nowrap;align-items:center;gap:6px;background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.25);border-radius:99px;padding:5px 14px;color:#F4EFDF;}
  .bmasw-ic{font-size:16px;} .bmasw-t{font:600 20px 'IBM Plex Mono',monospace;letter-spacing:.02em;min-width:62px;text-align:center;}
  .bmasw-b{border:none;background:rgba(255,255,255,.18);color:#F4EFDF;border-radius:50%;width:30px;height:30px;cursor:pointer;font-size:13px;}
  .bmasw.off{display:none;}
  @media (max-width:560px){ .bmasw{position:static;transform:none;margin-left:auto;padding:4px 5px 4px 8px;gap:4px;} .bmasw-ic{display:none;} .bmasw-t{font-size:16px;min-width:48px;} .bmasw-b{width:26px;height:26px;} .brand .series-name{font-size:15px;} .brand .brand-name{font-size:10.5px;} .brand .brand-row>div:not(.bmasw){min-width:0;} }
  .bmasw-done{font:600 15px 'IBM Plex Mono',monospace;color:var(--accent-text);margin:4px 0 8px;}
  .sp-fab{position:fixed;left:14px;bottom:84px;z-index:60;border:1.5px solid var(--navy-2);background:var(--card);color:var(--ink);border-radius:99px;padding:9px 14px;font:700 14px 'Source Sans 3',sans-serif;box-shadow:0 4px 14px rgba(0,0,0,.15);cursor:pointer;}
  .sp-fab.on{background:var(--navy);color:#F4EFDF;}
  body.kb-open .sp-fab{display:none;}
  .sp-canvas{position:absolute;z-index:55;display:none;touch-action:none;cursor:crosshair;}
  .sp-canvas.passive{pointer-events:none;cursor:default;}
  .sp-bar{position:fixed;top:8px;left:8px;right:8px;margin:0 auto;width:max-content;z-index:90;display:none;align-items:center;gap:6px;background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:6px 8px;box-shadow:0 6px 20px rgba(0,0,0,.2);max-width:calc(100vw - 16px);flex-wrap:wrap;justify-content:center;}
  .sp-lbl{font:700 13px 'Source Sans 3',sans-serif;color:var(--ink-soft);margin-right:2px;}
  .sp-pen,.sp-tool{width:38px;height:38px;border-radius:10px;border:1.5px solid var(--rule);background:var(--paper);cursor:pointer;display:inline-flex;align-items:center;justify-content:center;font-size:17px;padding:0;color:var(--ink);}
  .sp-pen i{width:20px;height:20px;border-radius:50%;display:block;}
  .sp-pen.on,.sp-tool.on{border-color:var(--navy-2);box-shadow:0 0 0 3px var(--gold-soft);}
  @media (max-width:560px){ .sp-lbl{display:none;} .sp-pen,.sp-tool{width:34px;height:34px;} .sp-fab span{display:none;} }

  /* larger reading sizes */
  .chapter-eyebrow{font-size:13.5px;}
  .chapter-title{font-size:36px;line-height:1.15;}
  .chapter-sub{font-size:16.5px;}
  .tab-btn{font-size:15.5px;}
  .sec-sub{font-size:15px;}
  .qtext{font-size:19px;line-height:1.55;}
  .qnum{width:36px;height:36px;font-size:16px;}
  .opt{font-size:17.5px;padding:12px 14px;}
  .step-line{font-size:17.5px;line-height:2;}
  .blank-input{font-size:16px;}
  .sol-line{font-size:16.5px;}
  .feedback{font-size:15px;}
  .note h2{font-size:28px;}
  .note h4{font-size:19px;}
  .note p,.note li{font-size:17.5px;line-height:1.65;}
  .note .lt{font-size:15.5px;}
  .ex .exh{font-size:18px;} .ex .exl{font-size:16.5px;}
  .keybox{font-size:16.5px;}
  .ttab{font-size:15.5px;}
  .hub-card h3{font-size:21px;} .hub-card p{font-size:15.5px;} .hub-btn{font-size:15px;}
  @media (max-width:480px){ .chapter-title{font-size:30px;} .qtext{font-size:18px;} .opt,.step-line{font-size:16.5px;} .note h2{font-size:24px;} .note p,.note li{font-size:16.5px;} }

  /* v4 celebration */
  .v4conf{position:fixed;inset:0;width:100vw;height:100vh;pointer-events:none;z-index:9999;}
  .v4ban{background:linear-gradient(135deg,var(--gold-soft),var(--card));border:2px solid var(--gold);border-radius:18px;padding:18px 14px 16px;margin:-4px 0 18px;text-align:center;animation:v4pop .55s cubic-bezier(.2,1.6,.4,1);}
  @keyframes v4pop{0%{transform:scale(.6);opacity:0}100%{transform:scale(1);opacity:1}}
  .v4trophy{font-size:54px;line-height:1;animation:v4bob 1.4s ease-in-out infinite;}
  @keyframes v4bob{0%,100%{transform:translateY(0) rotate(-6deg)}50%{transform:translateY(-6px) rotate(6deg)}}
  .v4h{font-size:28px;font-weight:800;color:var(--accent-text);margin-top:6px;}
  .v4m{font-size:19px;color:var(--ink);margin-top:4px;}
  .v4pills{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;margin-top:12px;}
  .v4p{font-size:16px;font-weight:700;border-radius:999px;padding:6px 12px;}
  .v4p.g{background:var(--success-soft);color:var(--success);} .v4p.o{background:var(--gold-soft);color:var(--retry-text);}
  .v4p.r{background:var(--danger-soft);color:var(--danger);} .v4p.s{background:var(--rule);color:var(--ink);}
  .v4next{margin-top:14px;} .v4go{font-size:18px !important;padding:13px 20px !important;}
  .v4rec td.v4g{color:var(--success);font-weight:700;} .v4rec td.v4o{color:var(--retry-text);font-weight:700;} .v4rec td.v4r{color:var(--danger);font-weight:700;}
  .v4rec tr.v4tot td{font-weight:800;border-top:2px solid var(--rule);}
  .v4rec th{font-size:12.5px;padding:6px 3px !important;white-space:nowrap;} .v4rec td{font-size:15px;padding:7px 3px !important;text-align:center;}
  .v4rec td:first-child,.v4rec th:first-child{text-align:left;white-space:normal;min-width:92px;max-width:150px;font-size:14.5px;}
  @media(max-width:460px){ .v4left{display:none;} }
  .v4leg{font-size:14.5px;color:var(--ink-soft);margin:2px 0 8px;line-height:1.5;}
  body.v4done .fab-q,body.v4done #qFab{display:none;}
  .v4sum{font-size:16px;margin-top:10px;}
  /* v4 larger reading sizes */
  body{font-size:18px;}
  .chapter-title{font-size:38px !important;line-height:1.15;}
  .chapter-sub{font-size:17px !important;}
  .tab-btn{font-size:16.5px !important;}
  .sec-sub{font-size:16.5px !important;}
  .qtext{font-size:21px !important;line-height:1.6 !important;}
  .qnum{width:38px !important;height:38px !important;font-size:17px !important;}
  .opt{font-size:19.5px !important;padding:13px 15px !important;}
  .step-line{font-size:19.5px !important;line-height:2.1 !important;}
  .blank-input{font-size:18px !important;min-height:40px;}
  .sol-line{font-size:18px !important;line-height:1.6;}
  .feedback{font-size:16.5px !important;}
  .note h2{font-size:29px !important;}
  .note h3{font-size:22px !important;}
  .note h4{font-size:20px !important;}
  .note p,.note li,.note td,.note th{font-size:18.5px !important;line-height:1.7 !important;}
  .ex .exh{font-size:19px !important;} .ex .exl{font-size:18px !important;}
  .keybox{font-size:18px !important;}
  .hub-card p{font-size:17.5px !important;} .hub-btn{font-size:16.5px !important;}
  .review-q,.review-ans{font-size:17.5px !important;}
  .rec-table td{font-size:16px;}
  .vkb-k{font-size:19px !important;}
  .fq{font-size:0.95em;}
</style>
</head>
<body>
<header class="brand">
  <div class="brand-row">
    <div class="crest">BM</div>
    <div>
      <div class="brand-name">Brain &amp; Mind Academy</div>
      <div class="series-name">Sopaan <span style="font-weight:400;font-size:14px;color:#CFD7EA;">Practice Series</span></div>
    </div>
  </div>
  <div class="chapter-eyebrow">Algebra 1 · Chapter 10</div>
  <div class="chapter-title">Radical Functions and Equations</div>
  <div class="chapter-sub">Theory Notes · Practice by Section · Learning Assessment</div><div class="chapter-credit">Follows the sections of Big Ideas Math Algebra 1, Chapter 10</div>
  <div class="chapter-progress">
    <div class="cp-track"><div class="cp-fill" id="cpFill"></div></div>
    <div class="cp-label" id="cpLabel">0% complete</div>
  </div>
  <div class="who-row"><button class="mode-pill" id="modePill" hidden>Choose a mode</button><span class="who" id="whoBar" hidden></span></div>
</header>

<nav class="tabbar"><div class="tabbar-inner" id="tabbar"></div></nav>
<div class="sec-sub" id="secSub"></div><div class="slide-progress"><div class="sp-track"><div class="sp-fill" id="spFill"></div></div><div class="sp-label" id="spLabel">Question 1 of 49</div></div>
<div class="wrap" id="wrap"></div>
<footer class="brandfoot">Brain &amp; Mind Academy · Sopaan Practice Series · Algebra 1 · Chapter 10<br>Lessons follow the chapter and section structure of <i>Big Ideas Math Algebra 1</i> (2015), Chapter 10. Theory notes, questions, learning assessments and worked solutions are written by Brain &amp; Mind Academy.</footer>

<div class="navbar"><div class="navbar-inner" id="navbarInner"></div></div>
<button class="fab" id="paletteFab"><span>Questions</span><span class="fab-badge" id="fabBadge">0/49</span></button>

<div class="overlay" id="overlay">
  <div class="palette" role="dialog" aria-label="Question palette">
    <div class="palette-head"><h2 id="paletteTitle">Question palette</h2><button class="palette-close" id="paletteClose">&times;</button></div>
    <div class="palette-legend">
      <span><i class="dot current"></i>Current</span><span><i class="dot correct"></i>Correct</span>
      <span><i class="dot revealed"></i>Revealed</span><span><i class="dot skipped"></i>Skipped</span>
      <span><i class="dot locked"></i>Locked</span>
    </div>
    <div class="chip-grid" id="paletteBody"></div>
  </div>
</div>
<div class="toast" id="toast"></div>

<script>
(function(){
"use strict";

/* ================= audio ================= */
var audioCtx=null;
function ensureAudio(){ if(!audioCtx){ try{ audioCtx=new (window.AudioContext||window.webkitAudioContext)(); }catch(e){} } return audioCtx; }
function playTone(freqs,dur,type){
  var ctx=ensureAudio(); if(!ctx) return;
  try{
    var t0=ctx.currentTime;
    freqs.forEach(function(f,i){
      var o=ctx.createOscillator(), g=ctx.createGain();
      o.type=type||'sine'; o.frequency.value=f;
      var start=t0+i*dur;
      g.gain.setValueAtTime(0.0001,start);
      g.gain.exponentialRampToValueAtTime(0.16,start+0.02);
      g.gain.exponentialRampToValueAtTime(0.0001,start+dur);
      o.connect(g); g.connect(ctx.destination);
      o.start(start); o.stop(start+dur+0.02);
    });
  }catch(e){}
}
function playSuccess(){ playTone([523.25,659.25,783.99],0.11,'sine'); }
function playWrong(){ playTone([220,185],0.14,'square'); }
function playReveal(){ playTone([300,220],0.16,'triangle'); }

/* ================= helpers ================= */
function norm(s){
  return String(s===undefined||s===null?'':s).trim().toLowerCase().replace(/\s+/g,'')
    .replace(/[×∗*·]/g,'x').replace(/÷/g,'/').replace(/–|—|−/g,'-')
    .replace(/[²]/g,'^2').replace(/[³]/g,'^3').replace(/[⁴]/g,'^4').replace(/[⁵]/g,'^5')
    .replace(/[⁶]/g,'^6').replace(/[⁷]/g,'^7').replace(/[⁸]/g,'^8').replace(/[⁹]/g,'^9')
    .replace(/\^/g,'');
}
function parseNum(s){
  if(s===undefined||s===null) return null;
  var t=String(s).trim().replace(/,/g,'').replace(/[−–—]/g,'-').replace(/\s+/g,''); if(t==='') return null;
  var neg=false; if(t[0]==='-'){neg=true;t=t.slice(1);}
  var m=t.match(/^(\d+)\/(\d+)$/);
  if(m){ var v=parseInt(m[1],10)/parseInt(m[2],10); return neg?-v:v; }
  if(/^\d+(\.\d+)?$/.test(t)){ var v2=parseFloat(t); return neg?-v2:v2; }
  return null;
}
/* ---- expression checker: compares answers like (P-2w)/2 and P/2-w at random values ---- */
function exprPrep(s){
  return String(s).toLowerCase().replace(/\s+/g,'').replace(/^[a-z]\(x\)=/i,'').replace(/^[a-z]=/i,'').replace(/[×∗·]/g,'*').replace(/÷/g,'/').replace(/[−–—]/g,'-')
    .replace(/²/g,'^2').replace(/³/g,'^3').replace(/⁴/g,'^4').replace(/⁵/g,'^5').replace(/⁶/g,'^6').replace(/⁷/g,'^7').replace(/⁸/g,'^8').replace(/⁹/g,'^9').replace(/π/g,'#').replace(/pi/gi,'#').replace(/½/g,'(1/2)');
}
function exprCompile(src){
  var s=exprPrep(src), i=0, toks=[], absDepth=0;
  while(i<s.length){
    var ch=s[i];
    if(/[0-9.]/.test(ch)){ var j=i; while(j<s.length && /[0-9.]/.test(s[j])) j++; toks.push({k:'n',v:parseFloat(s.slice(i,j))}); i=j; continue; }
    if(/[a-zA-Z#]/.test(ch)){ toks.push({k:'v',v:ch}); i++; continue; }
    if(ch==='|'){ var pv=toks[toks.length-1]; var opn=(absDepth===0)||!pv||('+-*/^(['.indexOf(pv.k)>=0); if(opn){ absDepth++; toks.push({k:'['}); } else { absDepth--; toks.push({k:']'}); } i++; continue; }
    if('+-*/^()'.indexOf(ch)>=0){ toks.push({k:ch}); i++; continue; }
    return null;
  }
  var out=[];
  for(var t=0;t<toks.length;t++){
    var a=toks[t], b=out[out.length-1];
    if(b && (b.k==='n'||b.k==='v'||b.k===')'||b.k===']') && (a.k==='n'||a.k==='v'||a.k==='('||a.k==='[')) out.push({k:'&'});
    out.push(a);
  }
  var p=0;
  function peek(){ return out[p]; }
  function parseE(){ var n=parseT(); while(peek() && (peek().k==='+'||peek().k==='-')){ var o=out[p++].k, r=parseT(); n=(function(l,r,o){return function(e){ return o==='+'?l(e)+r(e):l(e)-r(e); };})(n,r,o); } return n; }
  function parseI(){ var n=parseU(); while(peek() && peek().k==='&'){ p++; var r=parseP(); n=(function(l,r){return function(e){ return l(e)*r(e); };})(n,r); } return n; }
  function parseT(){ var n=parseI(); while(peek() && (peek().k==='*'||peek().k==='/')){ var o=out[p++].k, r=parseI(); n=(function(l,r,o){return function(e){ return o==='*'?l(e)*r(e):l(e)/r(e); };})(n,r,o); } return n; }
  function parseU(){ if(peek() && peek().k==='-'){ p++; var u=parseU(); return function(e){ return -u(e); }; } if(peek() && peek().k==='+'){ p++; return parseU(); } return parseP(); }
  function parseP(){ var b=parseA(); if(peek() && peek().k==='^'){ p++; var x=parseU(); return function(e){ return Math.pow(b(e),x(e)); }; } return b; }
  function parseA(){
    var t=out[p++]; if(!t) throw 0;
    if(t.k==='n') return function(){ return t.v; };
    if(t.k==='v') return t.v==='#' ? function(){ return Math.PI; } : function(e){ return e[t.v]; };
    if(t.k==='('){ var n=parseE(); if(!peek()||peek().k!==')') throw 0; p++; return n; }
    if(t.k==='['){ var m=parseE(); if(!peek()||peek().k!==']') throw 0; p++; return function(e){ return Math.abs(m(e)); }; }
    throw 0;
  }
  try{ var f=parseE(); if(p!==out.length) return null; return f; }catch(e){ return null; }
}
function exprEqual(input,answer){
  var f=exprCompile(input), g=exprCompile(answer); if(!f||!g) return false;
  var hits=0;
  for(var trial=0;trial<8;trial++){
    var env={}; 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('').forEach(function(c){ env[c]=1.3+Math.random()*4.1; });
    var x=f(env), y=g(env);
    if(!isFinite(x)||!isFinite(y)) continue;
    if(Math.abs(x-y)>1e-7*Math.max(1,Math.abs(x),Math.abs(y))) return false;
    hits++;
  }
  return hits>=3;
}
function wordsNorm(s){ return String(s||'').toLowerCase().replace(/\band\b/g,' ').replace(/[^a-z]/g,''); }
function listNorm(s){ return (String(s||'').replace(/[−–—]/g,'-').replace(/(\d) (?=\d{3}\b)/g,'$1').match(/-?\d+(\.\d+)?/g)||[]).join(','); }
function powNorm(s){ return String(s||'').toLowerCase().replace(/\s+/g,'').replace(/[×∗*·.]/g,'x').replace(/[⁰¹²³⁴⁵⁶⁷⁸⁹]+/g,function(m){ return '^'+m.split('').map(function(c){ return '⁰¹²³⁴⁵⁶⁷⁸⁹'.indexOf(c); }).join(''); }).replace(/\^1(?!\d)/g,''); }
function fr(s){ return String(s).replace(/\{(\d+) (\d+)\/(\d+)\}/g,'<span class="mx">$1<span class="fq"><span>$2</span><span>$3</span></span></span>').replace(/\{(\d+)\/(\d+)\}/g,'<span class="fq"><span>$1</span><span>$2</span></span>'); }
function gcdI(a,b){ a=Math.abs(a); b=Math.abs(b); while(b){ var t=a%b; a=b; b=t; } return a; }
function fracParse(s){ s=String(s===undefined||s===null?'':s).trim().replace(/[\u2044\u2215\u00f7]/g,'/').replace(/\s+/g,' ').replace(/\s*\/\s*/g,'/'); var m;
  if((m=s.match(/^(-?\d+)$/))) return {v:+m[1],form:'int',n:+m[1],d:1};
  if((m=s.match(/^(-?\d+)\/(\d+)$/))){ if(+m[2]===0) return null; return {v:m[1]/m[2],form:'frac',n:+m[1],d:+m[2]}; }
  if((m=s.match(/^(-?)(\d+)(?: |\+)(\d+)\/(\d+)$/))){ if(+m[4]===0) return null; var sg=m[1]?-1:1; return {v:sg*(+m[2]+m[3]/m[4]),form:'mixed',w:sg*m[2],n:+m[3],d:+m[4]}; }
  if((m=s.match(/^-?\d*\.\d+$/))) return {v:parseFloat(s),form:'dec'};
  return null; }
function fracOK(mode,input,answer){
  if(mode==='flist'){ var A=String(input).split(/[,;]/).map(function(x){return x.trim();}).filter(Boolean), K=String(answer).split(/[,;]/).map(function(x){return x.trim();});
    if(A.length!==K.length) return false; return A.every(function(x,i){ var a=fracParse(x), k=fracParse(K[i]); return a&&k&&Math.abs(a.v-k.v)<1e-9; }); }
  var a=fracParse(input), k=fracParse(answer); if(!a||!k) return false;
  var same=Math.abs(a.v-k.v)<1e-9; if(!same) return false;
  if(mode==='fv') return true;
  if(mode==='dec') return a.form==='dec'||a.form==='int';
  if(mode==='fe') return (a.form==='frac'&&k.form==='frac'&&a.n===k.n&&a.d===k.d)||(a.form==='int'&&k.form==='int');
  if(mode==='fi') return a.form==='frac'||(a.form==='int'&&k.form==='int');
  if(mode==='fl') return a.form==='int'||(a.form==='frac'&&gcdI(a.n,a.d)===1)||(a.form==='mixed'&&a.n<a.d&&gcdI(a.n,a.d)===1);
  if(mode==='fm') return a.form==='int'||(a.form==='mixed'&&a.n>0&&a.n<a.d&&gcdI(a.n,a.d)===1);
  return false; }
function answerMatches(input,answer,accept,expr){
  if(expr==='dec'||expr==='fv'||expr==='fe'||expr==='fl'||expr==='fm'||expr==='fi'||expr==='flist'){ if(input===undefined||input===null||String(input).trim()==='') return false; return fracOK(expr,input,answer); }
  if(input===undefined||input===null||String(input).trim()==='') return false;
  if(expr==='words'){ return [answer].concat(accept||[]).some(function(a){ if(/\d/.test(a)) return norm(a)===norm(input); var w=wordsNorm(a); return w!=='' && w===wordsNorm(input); }); }
  if(expr==='list'){ return [answer].concat(accept||[]).some(function(a){ return listNorm(a)===listNorm(input); }); }
  if(expr==='pow'){ return [answer].concat(accept||[]).some(function(a){ return powNorm(a)===powNorm(input); }); }
  if(expr==='time'){ var tn=function(x){ var t=String(x).toLowerCase().replace(/[\s.]/g,'').replace(/[:h]/g,''); if(/^\d{3}(am|pm)?$/.test(t)) t='0'+t; return t; }; return [answer].concat(accept||[]).some(function(a){ return tn(a)===tn(input); }); }
  if(expr==='glist'){ var gn=function(x){ return String(x).toUpperCase().split(/[\s,;]+/).filter(Boolean).sort().join(','); }; return [answer].concat(accept||[]).some(function(a){ return gn(a)===gn(input); }); }
  if(expr==='coord'){ var cn=function(x){ return String(x).replace(/[\u2212\u2013\u2014]/g,'-').replace(/[\s()\[\]]/g,''); }; return [answer].concat(accept||[]).some(function(a){ return cn(a)===cn(input); }); }
  if(expr==='dlist'){ var dn=function(x){ return (String(x).replace(/[−–—]/g,'-').match(/-?\d*\.?\d+/g)||[]).map(Number).join(','); }; return [answer].concat(accept||[]).some(function(a){ return dn(a)===dn(input); }); }
  if(expr==='set'){ var sn=function(x){ return (String(x).match(/-?\d+/g)||[]).map(Number).sort(function(a,b){return a-b;}).join(','); }; return [answer].concat(accept||[]).some(function(a){ return sn(a)===sn(input); }); }
  if(expr==='primes'){ var pn=function(x){ var t=powNorm(x).replace(/[^0-9x^]/g,''); var out=[]; t.split('x').forEach(function(tok){ if(!tok) return; var m=tok.split('^'); var b=+m[0], e=m[1]?+m[1]:1; for(var i=0;i<e;i++) out.push(b); }); return out.sort(function(a,b){return a-b;}).join(','); }; return [answer].concat(accept||[]).some(function(a){ return pn(a)===pn(input); }); }
  if(expr==='angle'){ var an=function(x){ return String(x).toUpperCase().replace(/[^A-Z]/g,''); }; var k=an(answer), v=an(input); return v===k || v===k.split('').reverse().join(''); }
  if(expr==='trans'){ var tv=function(x){ var s=String(x).toLowerCase().replace(/[−–—]/g,'-').replace(/\b(units?|squares?|and|then|steps?|to|the|a)\b/g,' ').replace(/[,;.]/g,' '); var re=/(\d+)\s*(right|left|up|down|r|l|u|d)\b/g, m, dx=0, dy=0, n=0; while((m=re.exec(s))){ var v=+m[1], d=m[2][0]; if(d==='r')dx+=v; else if(d==='l')dx-=v; else if(d==='u')dy+=v; else dy-=v; n++; } if(!n||s.replace(re,'').replace(/\s+/g,'')!=='') return null; return dx+','+dy; }; var ti=tv(input); return ti!==null && [answer].concat(accept||[]).some(function(a){ return tv(a)===ti; }); }
  if(expr==='rot'){ var rv=function(x){ var s=String(x).toLowerCase().replace(/quarter[\s-]*turn/g,'90').replace(/half[\s-]*turn/g,'180').replace(/three[\s-]*quarter[\s-]*turn/g,'270'); var m=s.match(/\b(90|180|270)\b/); if(!m) return null; var a=+m[1]; if(a===180) return '180'; var dir=/anti|counter|acw|ccw/.test(s)?-1:(/clockwise|\bcw\b/.test(s)?1:0); if(!dir) return null; return String(((a*dir)%360+360)%360); }; var ri=rv(input); return ri!==null && ri===rv(answer); }
  if(expr==='expanded'){ var f=function(x){ return String(x).replace(/\s+/g,'').replace(/,/g,''); }; return [answer].concat(accept||[]).some(function(a){ return f(a)===f(input); }); }
  if(expr===true && input!==undefined && input!==null && String(input).trim()!==''){
    if(exprEqual(input,answer)) return true;
    var alt=String(input).replace(/\/\s*(\d+(?:\.\d+)?)\s*([a-zA-Z(])/g,'/$1*$2'); if(alt!==String(input) && exprEqual(alt,answer)) return true;
    return (accept||[]).some(function(a){ return exprEqual(input,a); });
  }
  if(input===undefined||input===null||String(input).trim()==='') return false;
  var n1=parseNum(input), n2=parseNum(answer);
  if(n1!==null && n2!==null){ if(Math.abs(n1-n2)<1e-3) return true; return (accept||[]).some(function(a){ var n3=parseNum(a); return n3!==null && Math.abs(n1-n3)<1e-3; }); }
  var cands=[answer].concat(accept||[]); var ni=norm(input);
  for(var i=0;i<cands.length;i++){ if(norm(cands[i])===ni) return true; }
  return false;
}
function esc(s){ return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;'); }

/* ================= DATA ================= */
var AR_OPTIONS = ["Both A and R are true, and R is the correct explanation of A","Both A and R are true, but R is NOT the correct explanation of A","A is true but R is false","A is false but R is true"];
var THEORY = "<div class=\"hub\"><div class=\"hub-card\"><h3>📖 Theory notes</h3><p>Explained notes for every section of the chapter, with rules in boxes, graphs of square root and cube root functions, common mistakes and worked examples.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-jump=\"n101\">10.1 notes</button><button class=\"hub-btn\" data-jump=\"n102\">10.2 notes</button><button class=\"hub-btn\" data-jump=\"n103\">10.3 notes</button><button class=\"hub-btn\" data-jump=\"n104\">10.4 notes</button></div></div><div class=\"hub-card\"><h3>🎯 Practice by section</h3><p>One practice sheet for each section, easy to hard, mixing multiple-choice and fill-in-the-blank questions, with real-life problems and error-analysis items.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-go=\"s1\">10.1 · Graphing Square Root Functions</button><button class=\"hub-btn\" data-go=\"s2\">10.2 · Graphing Cube Root Functions</button><button class=\"hub-btn\" data-go=\"s3\">10.3 · Solving Radical Equations</button><button class=\"hub-btn\" data-go=\"s4\">10.4 · Inverse of a Function</button></div></div><div class=\"hub-card\"><h3>📝 Learning assessment</h3><p>Four short assessments mixing all four sections, one per skill area. Take them in Quiz mode and open the report to see your results as pie charts.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-go=\"s5\">A · Knowing and understanding</button><button class=\"hub-btn\" data-go=\"s6\">B · Investigating patterns</button><button class=\"hub-btn\" data-go=\"s7\">C · Communicating</button><button class=\"hub-btn\" data-go=\"s8\">D · Applying mathematics in real-life contexts</button><button class=\"hub-btn primary\" data-go=\"report\">📊 View my report</button></div></div></div><section class=\"note\" id=\"nintro\"><h2>About this chapter</h2><p>A <b>radical function</b> has the variable inside a radical, such as f(x) = √(x − 2) or g(x) = ∛x + 1. In this chapter you graph square root and cube root functions, solve equations that contain radicals, and learn how to “undo” a function by finding its <b>inverse</b>.</p><h4>Maintaining mathematical proficiency</h4><p>These earlier skills are used on every page. Check that each example makes sense before you start 10.1.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Skill</th><th>Key idea</th><th>Example</th></tr><tr><td>Perfect squares and square roots</td><td>√a is the non-negative number whose square is a.</td><td class=\"mono\">√49 = 7 ; √0.25 = 0.5 ; √(−9) is not real</td></tr><tr><td>Perfect cubes and cube roots</td><td>∛a is the number whose cube is a; it can be negative.</td><td class=\"mono\">∛64 = 4 ; ∛(−125) = −5</td></tr><tr><td>Squaring a binomial</td><td>(a − b)² = a² − 2ab + b²; do not forget the middle term.</td><td class=\"mono\">(x − 3)² = x² − 6x + 9</td></tr><tr><td>Solving quadratics by factoring</td><td>If ab = 0, then a = 0 or b = 0.</td><td class=\"mono\">x² − 5x + 6 = 0 → x = 2 or 3</td></tr><tr><td>Translating graphs</td><td>f(x − h) + k moves the graph h units right and k units up.</td><td class=\"mono\">|x − 4| + 1 : 4 right, 1 up</td></tr></table></div><div class=\"ex\"><div class=\"exh\">Warm-up example · Solve x² − 7x + 10 = 0</div><div class=\"exl\">Factor: (x − 2)(x − 5) = 0.<br><b>x = 2 or x = 5</b>. You will meet equations like this after squaring both sides of a radical equation.</div></div><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Sheet</th><th>Section</th><th>Learning target</th></tr><tr><td>10.1</td><td>Graphing Square Root Functions</td><td>I can graph square root functions, find their domain and range, describe transformations of f(x) = √x and compare average rates of change.</td></tr><tr><td>10.2</td><td>Graphing Cube Root Functions</td><td>I can graph cube root functions, find their point of symmetry and intercepts, describe transformations of f(x) = ∛x and compare them with other functions.</td></tr><tr><td>10.3</td><td>Solving Radical Equations</td><td>I can solve equations with square roots and cube roots by isolating the radical and raising both sides to a power, and identify extraneous solutions.</td></tr><tr><td>10.4</td><td>Inverse of a Function</td><td>I can find inverses of relations and functions, restrict domains so that an inverse is a function, and check that two functions are inverses.</td></tr></table></div><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Assessment</th><th>Skill area</th><th>What it checks</th></tr><tr><td>A</td><td>Knowing and understanding</td><td>Domains, ranges, solving radical equations and finding inverses.</td></tr><tr><td>B</td><td>Investigating patterns</td><td>How outputs, solutions and inverses change when the numbers change.</td></tr><tr><td>C</td><td>Communicating</td><td>Vocabulary, notation, explaining steps, spotting and correcting errors.</td></tr><tr><td>D</td><td>Applying mathematics in real-life contexts</td><td>Falling objects, pendulums, skid marks, conversions and judging answers.</td></tr></table></div><p><b>Tools:</b> ⏱ at the top times each tab (pause or reset it). ✏️ opens a scratchpad for rough work. Many graph questions have a 📈 Desmos button: type equations as <span class=\"mono\">y = sqrt(x−2)+1</span> or <span class=\"mono\">y = cbrt(x)</span>. Some questions have a 🧮 calculator. Tap the BM badge to go back to the home page.</p><p><b>Typing answers:</b> type numbers like <span class=\"mono\">-7</span> or <span class=\"mono\">2.25</span>. Type an inverse such as <span class=\"mono\">(x-6)/2</span> or <span class=\"mono\">x&#94;2+3</span>. Type square roots as <span class=\"mono\">sqrt(x+4)</span> or with the √ key, and cube roots as a power: <span class=\"mono\">(x+8)&#94;(1/3)</span>.</p></section><section class=\"note\" id=\"n101\"><h2>10.1 Graphing Square Root Functions</h2><p class=\"lt\"><b>Learning target:</b> I can graph square root functions, find their domain and range, describe transformations of f(x) = √x and compare average rates of change.</p><p>A <b>square root function</b> is a function that contains a square root with the independent variable in the <b>radicand</b> (the expression under the radical sign). The parent square root function is f(x) = √x.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>x</th><td>0</td><td>1</td><td>4</td><td>9</td><td>16</td></tr><tr><th>√x</th><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td></tr></table></div><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Parent square root function</text><line x1=\"22.0\" y1=\"214.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"46.0\" y1=\"214.0\" x2=\"46.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"70.0\" y1=\"214.0\" x2=\"70.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"94.0\" y1=\"214.0\" x2=\"94.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"118.0\" y1=\"214.0\" x2=\"118.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"142.0\" y1=\"214.0\" x2=\"142.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"166.0\" y1=\"214.0\" x2=\"166.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"190.0\" y1=\"214.0\" x2=\"190.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"214.0\" y1=\"214.0\" x2=\"214.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"238.0\" y1=\"214.0\" x2=\"238.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"262.0\" y1=\"214.0\" x2=\"262.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"286.0\" y1=\"214.0\" x2=\"286.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"310.0\" y1=\"214.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"214.0\" x2=\"310.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"186.6\" x2=\"310.0\" y2=\"186.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"159.1\" x2=\"310.0\" y2=\"159.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"131.7\" x2=\"310.0\" y2=\"131.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"104.3\" x2=\"310.0\" y2=\"104.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"76.9\" x2=\"310.0\" y2=\"76.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"49.4\" x2=\"310.0\" y2=\"49.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"159.1\" x2=\"310.0\" y2=\"159.1\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"70.0\" y1=\"214.0\" x2=\"70.0\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"22.0\" y=\"168.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"118.0\" y=\"168.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"166.0\" y=\"168.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"214.0\" y=\"168.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"262.0\" y=\"168.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><text class=\"po\" x=\"310.0\" y=\"168.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">10</text><text class=\"po\" x=\"66.0\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"66.0\" y=\"104.3\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"66.0\" y=\"49.4\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"306.0\" y=\"151.1\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"78.0\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x1\"><rect x=\"22.0\" y=\"22.0\" width=\"288.0\" height=\"192.0\"/></clipPath><path d=\"M70.0,159.1 L70.5,155.3 L71.0,153.7 L71.4,152.4 L71.9,151.4 L72.4,150.5 L72.9,149.6 L73.4,148.9 L73.8,148.2 L74.3,147.5 L74.8,146.9 L75.3,146.3 L75.8,145.7 L76.2,145.2 L76.7,144.6 L77.2,144.1 L77.7,143.6 L78.2,143.1 L78.6,142.7 L79.1,142.2 L79.6,141.8 L80.1,141.4 L80.6,140.9 L81.0,140.5 L81.5,140.1 L82.0,139.7 L82.5,139.4 L83.0,139.0 L83.4,138.6 L83.9,138.3 L84.4,137.9 L84.9,137.5 L85.4,137.2 L85.8,136.9 L86.3,136.5 L86.8,136.2 L87.3,135.9 L87.8,135.5 L88.2,135.2 L88.7,134.9 L89.2,134.6 L89.7,134.3 L90.2,134.0 L90.6,133.7 L91.1,133.4 L91.6,133.1 L92.1,132.8 L92.6,132.5 L93.0,132.3 L93.5,132.0 L94.0,131.7 L94.5,131.4 L95.0,131.2 L95.4,130.9 L95.9,130.6 L96.4,130.4 L96.9,130.1 L97.4,129.9 L97.8,129.6 L98.3,129.3 L98.8,129.1 L99.3,128.8 L99.8,128.6 L100.2,128.4 L100.7,128.1 L101.2,127.9 L101.7,127.6 L102.2,127.4 L102.6,127.2 L103.1,126.9 L103.6,126.7 L104.1,126.5 L104.6,126.2 L105.0,126.0 L105.5,125.8 L106.0,125.5 L106.5,125.3 L107.0,125.1 L107.4,124.9 L107.9,124.7 L108.4,124.4 L108.9,124.2 L109.4,124.0 L109.8,123.8 L110.3,123.6 L110.8,123.4 L111.3,123.2 L111.8,123.0 L112.2,122.8 L112.7,122.5 L113.2,122.3 L113.7,122.1 L114.2,121.9 L114.6,121.7 L115.1,121.5 L115.6,121.3 L116.1,121.1 L116.6,120.9 L117.0,120.7 L117.5,120.5 L118.0,120.4 L118.5,120.2 L119.0,120.0 L119.4,119.8 L119.9,119.6 L120.4,119.4 L120.9,119.2 L121.4,119.0 L121.8,118.8 L122.3,118.6 L122.8,118.5 L123.3,118.3 L123.8,118.1 L124.2,117.9 L124.7,117.7 L125.2,117.5 L125.7,117.4 L126.2,117.2 L126.6,117.0 L127.1,116.8 L127.6,116.7 L128.1,116.5 L128.6,116.3 L129.0,116.1 L129.5,115.9 L130.0,115.8 L130.5,115.6 L131.0,115.4 L131.4,115.3 L131.9,115.1 L132.4,114.9 L132.9,114.7 L133.4,114.6 L133.8,114.4 L134.3,114.2 L134.8,114.1 L135.3,113.9 L135.8,113.7 L136.2,113.6 L136.7,113.4 L137.2,113.2 L137.7,113.1 L138.2,112.9 L138.6,112.8 L139.1,112.6 L139.6,112.4 L140.1,112.3 L140.6,112.1 L141.0,112.0 L141.5,111.8 L142.0,111.6 L142.5,111.5 L143.0,111.3 L143.4,111.2 L143.9,111.0 L144.4,110.8 L144.9,110.7 L145.4,110.5 L145.8,110.4 L146.3,110.2 L146.8,110.1 L147.3,109.9 L147.8,109.8 L148.2,109.6 L148.7,109.5 L149.2,109.3 L149.7,109.2 L150.2,109.0 L150.6,108.9 L151.1,108.7 L151.6,108.6 L152.1,108.4 L152.6,108.3 L153.0,108.1 L153.5,108.0 L154.0,107.8 L154.5,107.7 L155.0,107.5 L155.4,107.4 L155.9,107.2 L156.4,107.1 L156.9,107.0 L157.4,106.8 L157.8,106.7 L158.3,106.5 L158.8,106.4 L159.3,106.2 L159.8,106.1 L160.2,106.0 L160.7,105.8 L161.2,105.7 L161.7,105.5 L162.2,105.4 L162.6,105.3 L163.1,105.1 L163.6,105.0 L164.1,104.8 L164.6,104.7 L165.0,104.6 L165.5,104.4 L166.0,104.3 L166.5,104.1 L167.0,104.0 L167.4,103.9 L167.9,103.7 L168.4,103.6 L168.9,103.5 L169.4,103.3 L169.8,103.2 L170.3,103.1 L170.8,102.9 L171.3,102.8 L171.8,102.7 L172.2,102.5 L172.7,102.4 L173.2,102.3 L173.7,102.1 L174.2,102.0 L174.6,101.9 L175.1,101.7 L175.6,101.6 L176.1,101.5 L176.6,101.3 L177.0,101.2 L177.5,101.1 L178.0,101.0 L178.5,100.8 L179.0,100.7 L179.4,100.6 L179.9,100.4 L180.4,100.3 L180.9,100.2 L181.4,100.1 L181.8,99.9 L182.3,99.8 L182.8,99.7 L183.3,99.6 L183.8,99.4 L184.2,99.3 L184.7,99.2 L185.2,99.0 L185.7,98.9 L186.2,98.8 L186.6,98.7 L187.1,98.6 L187.6,98.4 L188.1,98.3 L188.6,98.2 L189.0,98.1 L189.5,97.9 L190.0,97.8 L190.5,97.7 L191.0,97.6 L191.4,97.4 L191.9,97.3 L192.4,97.2 L192.9,97.1 L193.4,97.0 L193.8,96.8 L194.3,96.7 L194.8,96.6 L195.3,96.5 L195.8,96.4 L196.2,96.2 L196.7,96.1 L197.2,96.0 L197.7,95.9 L198.2,95.8 L198.6,95.6 L199.1,95.5 L199.6,95.4 L200.1,95.3 L200.6,95.2 L201.0,95.1 L201.5,94.9 L202.0,94.8 L202.5,94.7 L203.0,94.6 L203.4,94.5 L203.9,94.4 L204.4,94.2 L204.9,94.1 L205.4,94.0 L205.8,93.9 L206.3,93.8 L206.8,93.7 L207.3,93.5 L207.8,93.4 L208.2,93.3 L208.7,93.2 L209.2,93.1 L209.7,93.0 L210.2,92.9 L210.6,92.7 L211.1,92.6 L211.6,92.5 L212.1,92.4 L212.6,92.3 L213.0,92.2 L213.5,92.1 L214.0,92.0 L214.5,91.8 L215.0,91.7 L215.4,91.6 L215.9,91.5 L216.4,91.4 L216.9,91.3 L217.4,91.2 L217.8,91.1 L218.3,91.0 L218.8,90.8 L219.3,90.7 L219.8,90.6 L220.2,90.5 L220.7,90.4 L221.2,90.3 L221.7,90.2 L222.2,90.1 L222.6,90.0 L223.1,89.9 L223.6,89.8 L224.1,89.6 L224.6,89.5 L225.0,89.4 L225.5,89.3 L226.0,89.2 L226.5,89.1 L227.0,89.0 L227.4,88.9 L227.9,88.8 L228.4,88.7 L228.9,88.6 L229.4,88.5 L229.8,88.4 L230.3,88.3 L230.8,88.1 L231.3,88.0 L231.8,87.9 L232.2,87.8 L232.7,87.7 L233.2,87.6 L233.7,87.5 L234.2,87.4 L234.6,87.3 L235.1,87.2 L235.6,87.1 L236.1,87.0 L236.6,86.9 L237.0,86.8 L237.5,86.7 L238.0,86.6 L238.5,86.5 L239.0,86.4 L239.4,86.3 L239.9,86.2 L240.4,86.1 L240.9,86.0 L241.4,85.9 L241.8,85.7 L242.3,85.6 L242.8,85.5 L243.3,85.4 L243.8,85.3 L244.2,85.2 L244.7,85.1 L245.2,85.0 L245.7,84.9 L246.2,84.8 L246.6,84.7 L247.1,84.6 L247.6,84.5 L248.1,84.4 L248.6,84.3 L249.0,84.2 L249.5,84.1 L250.0,84.0 L250.5,83.9 L251.0,83.8 L251.4,83.7 L251.9,83.6 L252.4,83.5 L252.9,83.4 L253.4,83.3 L253.8,83.2 L254.3,83.1 L254.8,83.0 L255.3,82.9 L255.8,82.8 L256.2,82.7 L256.7,82.6 L257.2,82.5 L257.7,82.4 L258.2,82.3 L258.6,82.2 L259.1,82.1 L259.6,82.0 L260.1,82.0 L260.6,81.9 L261.0,81.8 L261.5,81.7 L262.0,81.6 L262.5,81.5 L263.0,81.4 L263.4,81.3 L263.9,81.2 L264.4,81.1 L264.9,81.0 L265.4,80.9 L265.8,80.8 L266.3,80.7 L266.8,80.6 L267.3,80.5 L267.8,80.4 L268.2,80.3 L268.7,80.2 L269.2,80.1 L269.7,80.0 L270.2,79.9 L270.6,79.8 L271.1,79.7 L271.6,79.6 L272.1,79.6 L272.6,79.5 L273.0,79.4 L273.5,79.3 L274.0,79.2 L274.5,79.1 L275.0,79.0 L275.4,78.9 L275.9,78.8 L276.4,78.7 L276.9,78.6 L277.4,78.5 L277.8,78.4 L278.3,78.3 L278.8,78.2 L279.3,78.1 L279.8,78.1 L280.2,78.0 L280.7,77.9 L281.2,77.8 L281.7,77.7 L282.2,77.6 L282.6,77.5 L283.1,77.4 L283.6,77.3 L284.1,77.2 L284.6,77.1 L285.0,77.0 L285.5,76.9 L286.0,76.9 L286.5,76.8 L287.0,76.7 L287.4,76.6 L287.9,76.5 L288.4,76.4 L288.9,76.3 L289.4,76.2 L289.8,76.1 L290.3,76.0 L290.8,75.9 L291.3,75.9 L291.8,75.8 L292.2,75.7 L292.7,75.6 L293.2,75.5 L293.7,75.4 L294.2,75.3 L294.6,75.2 L295.1,75.1 L295.6,75.0 L296.1,75.0 L296.6,74.9 L297.0,74.8 L297.5,74.7 L298.0,74.6 L298.5,74.5 L299.0,74.4 L299.4,74.3 L299.9,74.2 L300.4,74.2 L300.9,74.1 L301.4,74.0 L301.8,73.9 L302.3,73.8 L302.8,73.7 L303.3,73.6 L303.8,73.5 L304.2,73.5 L304.7,73.4 L305.2,73.3 L305.7,73.2 L306.2,73.1 L306.6,73.0 L307.1,72.9 L307.6,72.8 L308.1,72.8 L308.6,72.7 L309.0,72.6 L309.5,72.5 L310.0,72.4\" clip-path=\"url(#b10x1)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><text x=\"238.0\" y=\"78.6\" text-anchor=\"middle\" style=\"fill:var(--danger);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">y = √x</text><circle cx=\"70.0\" cy=\"159.1\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"77.0\" y=\"150.1\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(0, 0)</text><circle cx=\"94.0\" cy=\"131.7\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"166.0\" cy=\"104.3\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"173.0\" y=\"95.3\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(4, 2)</text><circle cx=\"286.0\" cy=\"76.9\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"293.0\" y=\"67.9\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(9, 3)</text></svg><p>Because you cannot take the square root of a negative number (in the real numbers), the <b>domain</b> of √x is x ≥ 0 and its <b>range</b> is y ≥ 0. The graph starts at its <b>endpoint</b> (0, 0) and rises more and more slowly.</p><h4>Transformations of f(x) = √x</h4><div class=\"keybox\"><b>g(x) = a√(x − h) + k</b><br>• |a| &gt; 1 vertical stretch; 0 &lt; |a| &lt; 1 vertical shrink; a &lt; 0 reflection in the x-axis.<br>• h moves the graph left or right; k moves it up or down. The endpoint is <b>(h, k)</b>.<br>• Domain: x ≥ h. Range: y ≥ k when a &gt; 0, and y ≤ k when a &lt; 0.<br>• √(−x) reflects the graph in the y-axis; then the domain is x ≤ 0.</div><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Reflect, stretch, then move 1 right and 3 up</text><line x1=\"22.0\" y1=\"214.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"46.0\" y1=\"214.0\" x2=\"46.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"70.0\" y1=\"214.0\" x2=\"70.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"94.0\" y1=\"214.0\" x2=\"94.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"118.0\" y1=\"214.0\" x2=\"118.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"142.0\" y1=\"214.0\" x2=\"142.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"166.0\" y1=\"214.0\" x2=\"166.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"190.0\" y1=\"214.0\" x2=\"190.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"214.0\" y1=\"214.0\" x2=\"214.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"238.0\" y1=\"214.0\" x2=\"238.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"262.0\" y1=\"214.0\" x2=\"262.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"286.0\" y1=\"214.0\" x2=\"286.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"310.0\" y1=\"214.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"214.0\" x2=\"310.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"192.7\" x2=\"310.0\" y2=\"192.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"171.3\" x2=\"310.0\" y2=\"171.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"150.0\" x2=\"310.0\" y2=\"150.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"128.7\" x2=\"310.0\" y2=\"128.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"107.3\" x2=\"310.0\" y2=\"107.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"86.0\" x2=\"310.0\" y2=\"86.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"64.7\" x2=\"310.0\" y2=\"64.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"43.3\" x2=\"310.0\" y2=\"43.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"128.7\" x2=\"310.0\" y2=\"128.7\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"70.0\" y1=\"214.0\" x2=\"70.0\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"22.0\" y=\"137.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"118.0\" y=\"137.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"166.0\" y=\"137.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"214.0\" y=\"137.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"262.0\" y=\"137.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><text class=\"po\" x=\"310.0\" y=\"137.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">10</text><text class=\"po\" x=\"66.0\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"66.0\" y=\"171.3\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"66.0\" y=\"86.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"66.0\" y=\"43.3\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"306.0\" y=\"120.7\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"78.0\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x2\"><rect x=\"22.0\" y=\"22.0\" width=\"288.0\" height=\"192.0\"/></clipPath><path d=\"M70.0,128.7 L70.5,125.6 L71.0,124.4 L71.4,123.4 L71.9,122.6 L72.4,121.9 L72.9,121.3 L73.4,120.7 L73.8,120.1 L74.3,119.6 L74.8,119.1 L75.3,118.7 L75.8,118.2 L76.2,117.8 L76.7,117.4 L77.2,117.0 L77.7,116.6 L78.2,116.2 L78.6,115.9 L79.1,115.5 L79.6,115.2 L80.1,114.8 L80.6,114.5 L81.0,114.2 L81.5,113.9 L82.0,113.6 L82.5,113.3 L83.0,113.0 L83.4,112.7 L83.9,112.4 L84.4,112.1 L84.9,111.9 L85.4,111.6 L85.8,111.3 L86.3,111.1 L86.8,110.8 L87.3,110.6 L87.8,110.3 L88.2,110.1 L88.7,109.8 L89.2,109.6 L89.7,109.3 L90.2,109.1 L90.6,108.9 L91.1,108.7 L91.6,108.4 L92.1,108.2 L92.6,108.0 L93.0,107.8 L93.5,107.5 L94.0,107.3 L94.5,107.1 L95.0,106.9 L95.4,106.7 L95.9,106.5 L96.4,106.3 L96.9,106.1 L97.4,105.9 L97.8,105.7 L98.3,105.5 L98.8,105.3 L99.3,105.1 L99.8,104.9 L100.2,104.7 L100.7,104.5 L101.2,104.3 L101.7,104.2 L102.2,104.0 L102.6,103.8 L103.1,103.6 L103.6,103.4 L104.1,103.2 L104.6,103.1 L105.0,102.9 L105.5,102.7 L106.0,102.5 L106.5,102.4 L107.0,102.2 L107.4,102.0 L107.9,101.9 L108.4,101.7 L108.9,101.5 L109.4,101.3 L109.8,101.2 L110.3,101.0 L110.8,100.9 L111.3,100.7 L111.8,100.5 L112.2,100.4 L112.7,100.2 L113.2,100.0 L113.7,99.9 L114.2,99.7 L114.6,99.6 L115.1,99.4 L115.6,99.3 L116.1,99.1 L116.6,99.0 L117.0,98.8 L117.5,98.6 L118.0,98.5 L118.5,98.3 L119.0,98.2 L119.4,98.0 L119.9,97.9 L120.4,97.8 L120.9,97.6 L121.4,97.5 L121.8,97.3 L122.3,97.2 L122.8,97.0 L123.3,96.9 L123.8,96.7 L124.2,96.6 L124.7,96.5 L125.2,96.3 L125.7,96.2 L126.2,96.0 L126.6,95.9 L127.1,95.8 L127.6,95.6 L128.1,95.5 L128.6,95.3 L129.0,95.2 L129.5,95.1 L130.0,94.9 L130.5,94.8 L131.0,94.7 L131.4,94.5 L131.9,94.4 L132.4,94.3 L132.9,94.1 L133.4,94.0 L133.8,93.9 L134.3,93.7 L134.8,93.6 L135.3,93.5 L135.8,93.4 L136.2,93.2 L136.7,93.1 L137.2,93.0 L137.7,92.8 L138.2,92.7 L138.6,92.6 L139.1,92.5 L139.6,92.3 L140.1,92.2 L140.6,92.1 L141.0,92.0 L141.5,91.8 L142.0,91.7 L142.5,91.6 L143.0,91.5 L143.4,91.3 L143.9,91.2 L144.4,91.1 L144.9,91.0 L145.4,90.9 L145.8,90.7 L146.3,90.6 L146.8,90.5 L147.3,90.4 L147.8,90.3 L148.2,90.1 L148.7,90.0 L149.2,89.9 L149.7,89.8 L150.2,89.7 L150.6,89.6 L151.1,89.4 L151.6,89.3 L152.1,89.2 L152.6,89.1 L153.0,89.0 L153.5,88.9 L154.0,88.8 L154.5,88.6 L155.0,88.5 L155.4,88.4 L155.9,88.3 L156.4,88.2 L156.9,88.1 L157.4,88.0 L157.8,87.9 L158.3,87.7 L158.8,87.6 L159.3,87.5 L159.8,87.4 L160.2,87.3 L160.7,87.2 L161.2,87.1 L161.7,87.0 L162.2,86.9 L162.6,86.8 L163.1,86.6 L163.6,86.5 L164.1,86.4 L164.6,86.3 L165.0,86.2 L165.5,86.1 L166.0,86.0 L166.5,85.9 L167.0,85.8 L167.4,85.7 L167.9,85.6 L168.4,85.5 L168.9,85.4 L169.4,85.3 L169.8,85.2 L170.3,85.1 L170.8,84.9 L171.3,84.8 L171.8,84.7 L172.2,84.6 L172.7,84.5 L173.2,84.4 L173.7,84.3 L174.2,84.2 L174.6,84.1 L175.1,84.0 L175.6,83.9 L176.1,83.8 L176.6,83.7 L177.0,83.6 L177.5,83.5 L178.0,83.4 L178.5,83.3 L179.0,83.2 L179.4,83.1 L179.9,83.0 L180.4,82.9 L180.9,82.8 L181.4,82.7 L181.8,82.6 L182.3,82.5 L182.8,82.4 L183.3,82.3 L183.8,82.2 L184.2,82.1 L184.7,82.0 L185.2,81.9 L185.7,81.8 L186.2,81.7 L186.6,81.6 L187.1,81.5 L187.6,81.4 L188.1,81.3 L188.6,81.3 L189.0,81.2 L189.5,81.1 L190.0,81.0 L190.5,80.9 L191.0,80.8 L191.4,80.7 L191.9,80.6 L192.4,80.5 L192.9,80.4 L193.4,80.3 L193.8,80.2 L194.3,80.1 L194.8,80.0 L195.3,79.9 L195.8,79.8 L196.2,79.7 L196.7,79.6 L197.2,79.6 L197.7,79.5 L198.2,79.4 L198.6,79.3 L199.1,79.2 L199.6,79.1 L200.1,79.0 L200.6,78.9 L201.0,78.8 L201.5,78.7 L202.0,78.6 L202.5,78.5 L203.0,78.5 L203.4,78.4 L203.9,78.3 L204.4,78.2 L204.9,78.1 L205.4,78.0 L205.8,77.9 L206.3,77.8 L206.8,77.7 L207.3,77.6 L207.8,77.6 L208.2,77.5 L208.7,77.4 L209.2,77.3 L209.7,77.2 L210.2,77.1 L210.6,77.0 L211.1,76.9 L211.6,76.8 L212.1,76.8 L212.6,76.7 L213.0,76.6 L213.5,76.5 L214.0,76.4 L214.5,76.3 L215.0,76.2 L215.4,76.2 L215.9,76.1 L216.4,76.0 L216.9,75.9 L217.4,75.8 L217.8,75.7 L218.3,75.6 L218.8,75.5 L219.3,75.5 L219.8,75.4 L220.2,75.3 L220.7,75.2 L221.2,75.1 L221.7,75.0 L222.2,75.0 L222.6,74.9 L223.1,74.8 L223.6,74.7 L224.1,74.6 L224.6,74.5 L225.0,74.4 L225.5,74.4 L226.0,74.3 L226.5,74.2 L227.0,74.1 L227.4,74.0 L227.9,73.9 L228.4,73.9 L228.9,73.8 L229.4,73.7 L229.8,73.6 L230.3,73.5 L230.8,73.4 L231.3,73.4 L231.8,73.3 L232.2,73.2 L232.7,73.1 L233.2,73.0 L233.7,73.0 L234.2,72.9 L234.6,72.8 L235.1,72.7 L235.6,72.6 L236.1,72.5 L236.6,72.5 L237.0,72.4 L237.5,72.3 L238.0,72.2 L238.5,72.1 L239.0,72.1 L239.4,72.0 L239.9,71.9 L240.4,71.8 L240.9,71.7 L241.4,71.7 L241.8,71.6 L242.3,71.5 L242.8,71.4 L243.3,71.3 L243.8,71.3 L244.2,71.2 L244.7,71.1 L245.2,71.0 L245.7,70.9 L246.2,70.9 L246.6,70.8 L247.1,70.7 L247.6,70.6 L248.1,70.6 L248.6,70.5 L249.0,70.4 L249.5,70.3 L250.0,70.2 L250.5,70.2 L251.0,70.1 L251.4,70.0 L251.9,69.9 L252.4,69.9 L252.9,69.8 L253.4,69.7 L253.8,69.6 L254.3,69.5 L254.8,69.5 L255.3,69.4 L255.8,69.3 L256.2,69.2 L256.7,69.2 L257.2,69.1 L257.7,69.0 L258.2,68.9 L258.6,68.9 L259.1,68.8 L259.6,68.7 L260.1,68.6 L260.6,68.6 L261.0,68.5 L261.5,68.4 L262.0,68.3 L262.5,68.3 L263.0,68.2 L263.4,68.1 L263.9,68.0 L264.4,68.0 L264.9,67.9 L265.4,67.8 L265.8,67.7 L266.3,67.7 L266.8,67.6 L267.3,67.5 L267.8,67.4 L268.2,67.4 L268.7,67.3 L269.2,67.2 L269.7,67.1 L270.2,67.1 L270.6,67.0 L271.1,66.9 L271.6,66.8 L272.1,66.8 L272.6,66.7 L273.0,66.6 L273.5,66.5 L274.0,66.5 L274.5,66.4 L275.0,66.3 L275.4,66.3 L275.9,66.2 L276.4,66.1 L276.9,66.0 L277.4,66.0 L277.8,65.9 L278.3,65.8 L278.8,65.7 L279.3,65.7 L279.8,65.6 L280.2,65.5 L280.7,65.5 L281.2,65.4 L281.7,65.3 L282.2,65.2 L282.6,65.2 L283.1,65.1 L283.6,65.0 L284.1,65.0 L284.6,64.9 L285.0,64.8 L285.5,64.7 L286.0,64.7 L286.5,64.6 L287.0,64.5 L287.4,64.5 L287.9,64.4 L288.4,64.3 L288.9,64.2 L289.4,64.2 L289.8,64.1 L290.3,64.0 L290.8,64.0 L291.3,63.9 L291.8,63.8 L292.2,63.7 L292.7,63.7 L293.2,63.6 L293.7,63.5 L294.2,63.5 L294.6,63.4 L295.1,63.3 L295.6,63.3 L296.1,63.2 L296.6,63.1 L297.0,63.1 L297.5,63.0 L298.0,62.9 L298.5,62.8 L299.0,62.8 L299.4,62.7 L299.9,62.6 L300.4,62.6 L300.9,62.5 L301.4,62.4 L301.8,62.4 L302.3,62.3 L302.8,62.2 L303.3,62.2 L303.8,62.1 L304.2,62.0 L304.7,62.0 L305.2,61.9 L305.7,61.8 L306.2,61.7 L306.6,61.7 L307.1,61.6 L307.6,61.5 L308.1,61.5 L308.6,61.4 L309.0,61.3 L309.5,61.3 L310.0,61.2\" clip-path=\"url(#b10x2)\" style=\"fill:none;stroke:var(--accent-text);stroke-width:2.2;stroke-dasharray:6 4\"/><text x=\"266.8\" y=\"59.6\" text-anchor=\"middle\" style=\"fill:var(--accent-text);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">y = √x</text><path d=\"M94.0,64.7 L94.5,70.7 L95.0,73.2 L95.4,75.1 L95.9,76.7 L96.4,78.2 L96.9,79.4 L97.4,80.6 L97.8,81.7 L98.3,82.8 L98.8,83.7 L99.3,84.7 L99.8,85.6 L100.2,86.4 L100.7,87.2 L101.2,88.0 L101.7,88.8 L102.2,89.5 L102.6,90.3 L103.1,91.0 L103.6,91.7 L104.1,92.3 L104.6,93.0 L105.0,93.6 L105.5,94.2 L106.0,94.8 L106.5,95.4 L107.0,96.0 L107.4,96.6 L107.9,97.2 L108.4,97.7 L108.9,98.3 L109.4,98.8 L109.8,99.3 L110.3,99.9 L110.8,100.4 L111.3,100.9 L111.8,101.4 L112.2,101.9 L112.7,102.3 L113.2,102.8 L113.7,103.3 L114.2,103.8 L114.6,104.2 L115.1,104.7 L115.6,105.1 L116.1,105.6 L116.6,106.0 L117.0,106.5 L117.5,106.9 L118.0,107.3 L118.5,107.8 L119.0,108.2 L119.4,108.6 L119.9,109.0 L120.4,109.4 L120.9,109.8 L121.4,110.2 L121.8,110.6 L122.3,111.0 L122.8,111.4 L123.3,111.8 L123.8,112.2 L124.2,112.6 L124.7,112.9 L125.2,113.3 L125.7,113.7 L126.2,114.1 L126.6,114.4 L127.1,114.8 L127.6,115.2 L128.1,115.5 L128.6,115.9 L129.0,116.2 L129.5,116.6 L130.0,116.9 L130.5,117.3 L131.0,117.6 L131.4,118.0 L131.9,118.3 L132.4,118.6 L132.9,119.0 L133.4,119.3 L133.8,119.6 L134.3,120.0 L134.8,120.3 L135.3,120.6 L135.8,120.9 L136.2,121.3 L136.7,121.6 L137.2,121.9 L137.7,122.2 L138.2,122.5 L138.6,122.9 L139.1,123.2 L139.6,123.5 L140.1,123.8 L140.6,124.1 L141.0,124.4 L141.5,124.7 L142.0,125.0 L142.5,125.3 L143.0,125.6 L143.4,125.9 L143.9,126.2 L144.4,126.5 L144.9,126.8 L145.4,127.1 L145.8,127.4 L146.3,127.7 L146.8,128.0 L147.3,128.2 L147.8,128.5 L148.2,128.8 L148.7,129.1 L149.2,129.4 L149.7,129.7 L150.2,129.9 L150.6,130.2 L151.1,130.5 L151.6,130.8 L152.1,131.0 L152.6,131.3 L153.0,131.6 L153.5,131.9 L154.0,132.1 L154.5,132.4 L155.0,132.7 L155.4,132.9 L155.9,133.2 L156.4,133.5 L156.9,133.7 L157.4,134.0 L157.8,134.3 L158.3,134.5 L158.8,134.8 L159.3,135.0 L159.8,135.3 L160.2,135.5 L160.7,135.8 L161.2,136.1 L161.7,136.3 L162.2,136.6 L162.6,136.8 L163.1,137.1 L163.6,137.3 L164.1,137.6 L164.6,137.8 L165.0,138.1 L165.5,138.3 L166.0,138.6 L166.5,138.8 L167.0,139.1 L167.4,139.3 L167.9,139.5 L168.4,139.8 L168.9,140.0 L169.4,140.3 L169.8,140.5 L170.3,140.8 L170.8,141.0 L171.3,141.2 L171.8,141.5 L172.2,141.7 L172.7,141.9 L173.2,142.2 L173.7,142.4 L174.2,142.6 L174.6,142.9 L175.1,143.1 L175.6,143.3 L176.1,143.6 L176.6,143.8 L177.0,144.0 L177.5,144.3 L178.0,144.5 L178.5,144.7 L179.0,144.9 L179.4,145.2 L179.9,145.4 L180.4,145.6 L180.9,145.8 L181.4,146.1 L181.8,146.3 L182.3,146.5 L182.8,146.7 L183.3,147.0 L183.8,147.2 L184.2,147.4 L184.7,147.6 L185.2,147.8 L185.7,148.1 L186.2,148.3 L186.6,148.5 L187.1,148.7 L187.6,148.9 L188.1,149.1 L188.6,149.4 L189.0,149.6 L189.5,149.8 L190.0,150.0 L190.5,150.2 L191.0,150.4 L191.4,150.6 L191.9,150.8 L192.4,151.1 L192.9,151.3 L193.4,151.5 L193.8,151.7 L194.3,151.9 L194.8,152.1 L195.3,152.3 L195.8,152.5 L196.2,152.7 L196.7,152.9 L197.2,153.1 L197.7,153.3 L198.2,153.6 L198.6,153.8 L199.1,154.0 L199.6,154.2 L200.1,154.4 L200.6,154.6 L201.0,154.8 L201.5,155.0 L202.0,155.2 L202.5,155.4 L203.0,155.6 L203.4,155.8 L203.9,156.0 L204.4,156.2 L204.9,156.4 L205.4,156.6 L205.8,156.8 L206.3,157.0 L206.8,157.2 L207.3,157.4 L207.8,157.6 L208.2,157.8 L208.7,157.9 L209.2,158.1 L209.7,158.3 L210.2,158.5 L210.6,158.7 L211.1,158.9 L211.6,159.1 L212.1,159.3 L212.6,159.5 L213.0,159.7 L213.5,159.9 L214.0,160.1 L214.5,160.3 L215.0,160.5 L215.4,160.6 L215.9,160.8 L216.4,161.0 L216.9,161.2 L217.4,161.4 L217.8,161.6 L218.3,161.8 L218.8,162.0 L219.3,162.1 L219.8,162.3 L220.2,162.5 L220.7,162.7 L221.2,162.9 L221.7,163.1 L222.2,163.3 L222.6,163.4 L223.1,163.6 L223.6,163.8 L224.1,164.0 L224.6,164.2 L225.0,164.4 L225.5,164.5 L226.0,164.7 L226.5,164.9 L227.0,165.1 L227.4,165.3 L227.9,165.5 L228.4,165.6 L228.9,165.8 L229.4,166.0 L229.8,166.2 L230.3,166.4 L230.8,166.5 L231.3,166.7 L231.8,166.9 L232.2,167.1 L232.7,167.2 L233.2,167.4 L233.7,167.6 L234.2,167.8 L234.6,168.0 L235.1,168.1 L235.6,168.3 L236.1,168.5 L236.6,168.7 L237.0,168.8 L237.5,169.0 L238.0,169.2 L238.5,169.4 L239.0,169.5 L239.4,169.7 L239.9,169.9 L240.4,170.0 L240.9,170.2 L241.4,170.4 L241.8,170.6 L242.3,170.7 L242.8,170.9 L243.3,171.1 L243.8,171.2 L244.2,171.4 L244.7,171.6 L245.2,171.8 L245.7,171.9 L246.2,172.1 L246.6,172.3 L247.1,172.4 L247.6,172.6 L248.1,172.8 L248.6,172.9 L249.0,173.1 L249.5,173.3 L250.0,173.4 L250.5,173.6 L251.0,173.8 L251.4,173.9 L251.9,174.1 L252.4,174.3 L252.9,174.4 L253.4,174.6 L253.8,174.8 L254.3,174.9 L254.8,175.1 L255.3,175.3 L255.8,175.4 L256.2,175.6 L256.7,175.8 L257.2,175.9 L257.7,176.1 L258.2,176.3 L258.6,176.4 L259.1,176.6 L259.6,176.7 L260.1,176.9 L260.6,177.1 L261.0,177.2 L261.5,177.4 L262.0,177.6 L262.5,177.7 L263.0,177.9 L263.4,178.0 L263.9,178.2 L264.4,178.4 L264.9,178.5 L265.4,178.7 L265.8,178.8 L266.3,179.0 L266.8,179.2 L267.3,179.3 L267.8,179.5 L268.2,179.6 L268.7,179.8 L269.2,179.9 L269.7,180.1 L270.2,180.3 L270.6,180.4 L271.1,180.6 L271.6,180.7 L272.1,180.9 L272.6,181.0 L273.0,181.2 L273.5,181.4 L274.0,181.5 L274.5,181.7 L275.0,181.8 L275.4,182.0 L275.9,182.1 L276.4,182.3 L276.9,182.4 L277.4,182.6 L277.8,182.8 L278.3,182.9 L278.8,183.1 L279.3,183.2 L279.8,183.4 L280.2,183.5 L280.7,183.7 L281.2,183.8 L281.7,184.0 L282.2,184.1 L282.6,184.3 L283.1,184.4 L283.6,184.6 L284.1,184.7 L284.6,184.9 L285.0,185.0 L285.5,185.2 L286.0,185.3 L286.5,185.5 L287.0,185.6 L287.4,185.8 L287.9,185.9 L288.4,186.1 L288.9,186.2 L289.4,186.4 L289.8,186.5 L290.3,186.7 L290.8,186.8 L291.3,187.0 L291.8,187.1 L292.2,187.3 L292.7,187.4 L293.2,187.6 L293.7,187.7 L294.2,187.9 L294.6,188.0 L295.1,188.2 L295.6,188.3 L296.1,188.5 L296.6,188.6 L297.0,188.8 L297.5,188.9 L298.0,189.1 L298.5,189.2 L299.0,189.4 L299.4,189.5 L299.9,189.6 L300.4,189.8 L300.9,189.9 L301.4,190.1 L301.8,190.2 L302.3,190.4 L302.8,190.5 L303.3,190.7 L303.8,190.8 L304.2,190.9 L304.7,191.1 L305.2,191.2 L305.7,191.4 L306.2,191.5 L306.6,191.7 L307.1,191.8 L307.6,192.0 L308.1,192.1 L308.6,192.2 L309.0,192.4 L309.5,192.5 L310.0,192.7\" clip-path=\"url(#b10x2)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><text x=\"218.8\" y=\"154.0\" text-anchor=\"middle\" style=\"fill:var(--danger);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">g(x) = −2√(x − 1) + 3</text><circle cx=\"94.0\" cy=\"64.7\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"101.0\" y=\"55.7\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(1, 3)</text><circle cx=\"118.0\" cy=\"107.3\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"190.0\" cy=\"150.0\" r=\"3.8\" style=\"fill:var(--ink)\"/></svg><div class=\"ex\"><div class=\"exh\">Worked example 1 · Domain from the radicand</div><div class=\"exl\">Find the domain of f(x) = √(3x − 12).<br>The radicand must be non-negative: 3x − 12 ≥ 0.<br>3x ≥ 12, so the domain is <b>x ≥ 4</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Describe and graph</div><div class=\"exl\">Describe g(x) = −2√(x − 1) + 3 and give its domain and range.<br>Vertical stretch by 2, reflection in the x-axis, then 1 unit right and 3 units up. Endpoint (1, 3).<br>Points: g(1) = 3, g(2) = 1, g(5) = −1. Domain <b>x ≥ 1</b>, range <b>y ≤ 3</b>.</div></div><h4>Comparing average rates of change</h4><p>The <b>average rate of change</b> of f from x = a to x = b is <span class=\"fq\"><span>f(b) − f(a)</span><span>b − a</span></span>, the slope of the line joining the two points. For √x it gets smaller as x grows: the graph flattens out.</p><div class=\"ex\"><div class=\"exh\">Worked example 3 · Average rate of change</div><div class=\"exl\">f(x) = 4√x. Find the average rate of change from x = 1 to x = 9.<br>f(1) = 4 and f(9) = 12.<br><span class=\"fq\"><span>12 − 4</span><span>9 − 1</span></span> = {8/8} = <b>1</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 4 · Real life</div><div class=\"exl\">The time t (seconds) for a stone to fall h feet is about t = {1/4}√h. How long does a 100-foot fall take?<br>t = {1/4}√100 = {1/4}(10).<br><b>t = 2.5 seconds</b>.</div></div><div class=\"keybox\"><b>Common mistake.</b> In √(x + 5) the graph moves 5 units <b>left</b>, so the domain is x ≥ −5, not x ≥ 5. Set the radicand ≥ 0 and solve: x + 5 ≥ 0.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s1\">Practise 10.1 →</button></div></section><section class=\"note\" id=\"n102\"><h2>10.2 Graphing Cube Root Functions</h2><p class=\"lt\"><b>Learning target:</b> I can graph cube root functions, find their point of symmetry and intercepts, describe transformations of f(x) = ∛x and compare them with other functions.</p><p>A <b>cube root function</b> contains a cube root with the independent variable in the radicand. The parent cube root function is f(x) = ∛x. Every real number has exactly one cube root, so <b>the domain and the range are all real numbers</b>.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>x</th><td>−8</td><td>−1</td><td>0</td><td>1</td><td>8</td></tr><tr><th>∛x</th><td>−2</td><td>−1</td><td>0</td><td>1</td><td>2</td></tr></table></div><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Parent cube root function</text><line x1=\"22.0\" y1=\"214.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"38.0\" y1=\"214.0\" x2=\"38.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"54.0\" y1=\"214.0\" x2=\"54.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"70.0\" y1=\"214.0\" x2=\"70.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"86.0\" y1=\"214.0\" x2=\"86.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"102.0\" y1=\"214.0\" x2=\"102.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"118.0\" y1=\"214.0\" x2=\"118.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"134.0\" y1=\"214.0\" x2=\"134.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"150.0\" y1=\"214.0\" x2=\"150.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"166.0\" y1=\"214.0\" x2=\"166.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"182.0\" y1=\"214.0\" x2=\"182.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"198.0\" y1=\"214.0\" x2=\"198.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"214.0\" y1=\"214.0\" x2=\"214.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"230.0\" y1=\"214.0\" x2=\"230.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"246.0\" y1=\"214.0\" x2=\"246.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"262.0\" y1=\"214.0\" x2=\"262.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"278.0\" y1=\"214.0\" x2=\"278.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"294.0\" y1=\"214.0\" x2=\"294.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"310.0\" y1=\"214.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"214.0\" x2=\"310.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"182.0\" x2=\"310.0\" y2=\"182.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"150.0\" x2=\"310.0\" y2=\"150.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"118.0\" x2=\"310.0\" y2=\"118.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"86.0\" x2=\"310.0\" y2=\"86.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"54.0\" x2=\"310.0\" y2=\"54.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"118.0\" x2=\"310.0\" y2=\"118.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"166.0\" y1=\"214.0\" x2=\"166.0\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"38.0\" y=\"127.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−8</text><text class=\"po\" x=\"70.0\" y=\"127.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−6</text><text class=\"po\" x=\"102.0\" y=\"127.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"134.0\" y=\"127.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"198.0\" y=\"127.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"230.0\" y=\"127.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"262.0\" y=\"127.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"294.0\" y=\"127.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><text class=\"po\" x=\"162.0\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−3</text><text class=\"po\" x=\"162.0\" y=\"182.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"162.0\" y=\"150.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−1</text><text class=\"po\" x=\"162.0\" y=\"86.0\" text-anchor=\"end\" dominant-baseline=\"middle\">1</text><text class=\"po\" x=\"162.0\" y=\"54.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"162.0\" y=\"22.0\" text-anchor=\"end\" dominant-baseline=\"middle\">3</text><text class=\"po\" x=\"306.0\" y=\"110.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"174.0\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x3\"><rect x=\"22.0\" y=\"22.0\" width=\"288.0\" height=\"192.0\"/></clipPath><path d=\"M22.0,184.6 L22.5,184.5 L23.0,184.4 L23.4,184.3 L23.9,184.3 L24.4,184.2 L24.9,184.1 L25.4,184.0 L25.8,184.0 L26.3,183.9 L26.8,183.8 L27.3,183.7 L27.8,183.7 L28.2,183.6 L28.7,183.5 L29.2,183.4 L29.7,183.4 L30.2,183.3 L30.6,183.2 L31.1,183.1 L31.6,183.0 L32.1,183.0 L32.6,182.9 L33.0,182.8 L33.5,182.7 L34.0,182.7 L34.5,182.6 L35.0,182.5 L35.4,182.4 L35.9,182.3 L36.4,182.3 L36.9,182.2 L37.4,182.1 L37.8,182.0 L38.3,181.9 L38.8,181.9 L39.3,181.8 L39.8,181.7 L40.2,181.6 L40.7,181.5 L41.2,181.5 L41.7,181.4 L42.2,181.3 L42.6,181.2 L43.1,181.1 L43.6,181.1 L44.1,181.0 L44.6,180.9 L45.0,180.8 L45.5,180.7 L46.0,180.6 L46.5,180.6 L47.0,180.5 L47.4,180.4 L47.9,180.3 L48.4,180.2 L48.9,180.1 L49.4,180.0 L49.8,180.0 L50.3,179.9 L50.8,179.8 L51.3,179.7 L51.8,179.6 L52.2,179.5 L52.7,179.4 L53.2,179.4 L53.7,179.3 L54.2,179.2 L54.6,179.1 L55.1,179.0 L55.6,178.9 L56.1,178.8 L56.6,178.7 L57.0,178.7 L57.5,178.6 L58.0,178.5 L58.5,178.4 L59.0,178.3 L59.4,178.2 L59.9,178.1 L60.4,178.0 L60.9,177.9 L61.4,177.8 L61.8,177.8 L62.3,177.7 L62.8,177.6 L63.3,177.5 L63.8,177.4 L64.2,177.3 L64.7,177.2 L65.2,177.1 L65.7,177.0 L66.2,176.9 L66.6,176.8 L67.1,176.7 L67.6,176.6 L68.1,176.5 L68.6,176.4 L69.0,176.3 L69.5,176.2 L70.0,176.1 L70.5,176.1 L71.0,176.0 L71.4,175.9 L71.9,175.8 L72.4,175.7 L72.9,175.6 L73.4,175.5 L73.8,175.4 L74.3,175.3 L74.8,175.2 L75.3,175.1 L75.8,175.0 L76.2,174.9 L76.7,174.8 L77.2,174.7 L77.7,174.6 L78.2,174.5 L78.6,174.3 L79.1,174.2 L79.6,174.1 L80.1,174.0 L80.6,173.9 L81.0,173.8 L81.5,173.7 L82.0,173.6 L82.5,173.5 L83.0,173.4 L83.4,173.3 L83.9,173.2 L84.4,173.1 L84.9,173.0 L85.4,172.9 L85.8,172.8 L86.3,172.6 L86.8,172.5 L87.3,172.4 L87.8,172.3 L88.2,172.2 L88.7,172.1 L89.2,172.0 L89.7,171.9 L90.2,171.8 L90.6,171.6 L91.1,171.5 L91.6,171.4 L92.1,171.3 L92.6,171.2 L93.0,171.1 L93.5,170.9 L94.0,170.8 L94.5,170.7 L95.0,170.6 L95.4,170.5 L95.9,170.4 L96.4,170.2 L96.9,170.1 L97.4,170.0 L97.8,169.9 L98.3,169.8 L98.8,169.6 L99.3,169.5 L99.8,169.4 L100.2,169.3 L100.7,169.1 L101.2,169.0 L101.7,168.9 L102.2,168.8 L102.6,168.6 L103.1,168.5 L103.6,168.4 L104.1,168.2 L104.6,168.1 L105.0,168.0 L105.5,167.8 L106.0,167.7 L106.5,167.6 L107.0,167.4 L107.4,167.3 L107.9,167.2 L108.4,167.0 L108.9,166.9 L109.4,166.8 L109.8,166.6 L110.3,166.5 L110.8,166.4 L111.3,166.2 L111.8,166.1 L112.2,165.9 L112.7,165.8 L113.2,165.6 L113.7,165.5 L114.2,165.4 L114.6,165.2 L115.1,165.1 L115.6,164.9 L116.1,164.8 L116.6,164.6 L117.0,164.5 L117.5,164.3 L118.0,164.2 L118.5,164.0 L119.0,163.8 L119.4,163.7 L119.9,163.5 L120.4,163.4 L120.9,163.2 L121.4,163.0 L121.8,162.9 L122.3,162.7 L122.8,162.6 L123.3,162.4 L123.8,162.2 L124.2,162.1 L124.7,161.9 L125.2,161.7 L125.7,161.5 L126.2,161.4 L126.6,161.2 L127.1,161.0 L127.6,160.8 L128.1,160.7 L128.6,160.5 L129.0,160.3 L129.5,160.1 L130.0,159.9 L130.5,159.7 L131.0,159.6 L131.4,159.4 L131.9,159.2 L132.4,159.0 L132.9,158.8 L133.4,158.6 L133.8,158.4 L134.3,158.2 L134.8,158.0 L135.3,157.8 L135.8,157.6 L136.2,157.4 L136.7,157.1 L137.2,156.9 L137.7,156.7 L138.2,156.5 L138.6,156.3 L139.1,156.0 L139.6,155.8 L140.1,155.6 L140.6,155.3 L141.0,155.1 L141.5,154.9 L142.0,154.6 L142.5,154.4 L143.0,154.1 L143.4,153.9 L143.9,153.6 L144.4,153.4 L144.9,153.1 L145.4,152.8 L145.8,152.6 L146.3,152.3 L146.8,152.0 L147.3,151.7 L147.8,151.4 L148.2,151.1 L148.7,150.8 L149.2,150.5 L149.7,150.2 L150.2,149.9 L150.6,149.6 L151.1,149.2 L151.6,148.9 L152.1,148.5 L152.6,148.2 L153.0,147.8 L153.5,147.5 L154.0,147.1 L154.5,146.7 L155.0,146.3 L155.4,145.9 L155.9,145.4 L156.4,145.0 L156.9,144.5 L157.4,144.1 L157.8,143.6 L158.3,143.1 L158.8,142.5 L159.3,142.0 L159.8,141.4 L160.2,140.8 L160.7,140.1 L161.2,139.4 L161.7,138.7 L162.2,137.9 L162.6,137.0 L163.1,136.1 L163.6,135.0 L164.1,133.8 L164.6,132.3 L165.0,130.5 L165.5,127.9 L166.0,118.0 L166.5,108.1 L167.0,105.5 L167.4,103.7 L167.9,102.2 L168.4,101.0 L168.9,99.9 L169.4,99.0 L169.8,98.1 L170.3,97.3 L170.8,96.6 L171.3,95.9 L171.8,95.2 L172.2,94.6 L172.7,94.0 L173.2,93.5 L173.7,92.9 L174.2,92.4 L174.6,91.9 L175.1,91.5 L175.6,91.0 L176.1,90.6 L176.6,90.1 L177.0,89.7 L177.5,89.3 L178.0,88.9 L178.5,88.5 L179.0,88.2 L179.4,87.8 L179.9,87.5 L180.4,87.1 L180.9,86.8 L181.4,86.4 L181.8,86.1 L182.3,85.8 L182.8,85.5 L183.3,85.2 L183.8,84.9 L184.2,84.6 L184.7,84.3 L185.2,84.0 L185.7,83.7 L186.2,83.4 L186.6,83.2 L187.1,82.9 L187.6,82.6 L188.1,82.4 L188.6,82.1 L189.0,81.9 L189.5,81.6 L190.0,81.4 L190.5,81.1 L191.0,80.9 L191.4,80.7 L191.9,80.4 L192.4,80.2 L192.9,80.0 L193.4,79.7 L193.8,79.5 L194.3,79.3 L194.8,79.1 L195.3,78.9 L195.8,78.6 L196.2,78.4 L196.7,78.2 L197.2,78.0 L197.7,77.8 L198.2,77.6 L198.6,77.4 L199.1,77.2 L199.6,77.0 L200.1,76.8 L200.6,76.6 L201.0,76.4 L201.5,76.3 L202.0,76.1 L202.5,75.9 L203.0,75.7 L203.4,75.5 L203.9,75.3 L204.4,75.2 L204.9,75.0 L205.4,74.8 L205.8,74.6 L206.3,74.5 L206.8,74.3 L207.3,74.1 L207.8,73.9 L208.2,73.8 L208.7,73.6 L209.2,73.4 L209.7,73.3 L210.2,73.1 L210.6,73.0 L211.1,72.8 L211.6,72.6 L212.1,72.5 L212.6,72.3 L213.0,72.2 L213.5,72.0 L214.0,71.8 L214.5,71.7 L215.0,71.5 L215.4,71.4 L215.9,71.2 L216.4,71.1 L216.9,70.9 L217.4,70.8 L217.8,70.6 L218.3,70.5 L218.8,70.4 L219.3,70.2 L219.8,70.1 L220.2,69.9 L220.7,69.8 L221.2,69.6 L221.7,69.5 L222.2,69.4 L222.6,69.2 L223.1,69.1 L223.6,69.0 L224.1,68.8 L224.6,68.7 L225.0,68.6 L225.5,68.4 L226.0,68.3 L226.5,68.2 L227.0,68.0 L227.4,67.9 L227.9,67.8 L228.4,67.6 L228.9,67.5 L229.4,67.4 L229.8,67.2 L230.3,67.1 L230.8,67.0 L231.3,66.9 L231.8,66.7 L232.2,66.6 L232.7,66.5 L233.2,66.4 L233.7,66.2 L234.2,66.1 L234.6,66.0 L235.1,65.9 L235.6,65.8 L236.1,65.6 L236.6,65.5 L237.0,65.4 L237.5,65.3 L238.0,65.2 L238.5,65.1 L239.0,64.9 L239.4,64.8 L239.9,64.7 L240.4,64.6 L240.9,64.5 L241.4,64.4 L241.8,64.2 L242.3,64.1 L242.8,64.0 L243.3,63.9 L243.8,63.8 L244.2,63.7 L244.7,63.6 L245.2,63.5 L245.7,63.4 L246.2,63.2 L246.6,63.1 L247.1,63.0 L247.6,62.9 L248.1,62.8 L248.6,62.7 L249.0,62.6 L249.5,62.5 L250.0,62.4 L250.5,62.3 L251.0,62.2 L251.4,62.1 L251.9,62.0 L252.4,61.9 L252.9,61.8 L253.4,61.7 L253.8,61.5 L254.3,61.4 L254.8,61.3 L255.3,61.2 L255.8,61.1 L256.2,61.0 L256.7,60.9 L257.2,60.8 L257.7,60.7 L258.2,60.6 L258.6,60.5 L259.1,60.4 L259.6,60.3 L260.1,60.2 L260.6,60.1 L261.0,60.0 L261.5,59.9 L262.0,59.9 L262.5,59.8 L263.0,59.7 L263.4,59.6 L263.9,59.5 L264.4,59.4 L264.9,59.3 L265.4,59.2 L265.8,59.1 L266.3,59.0 L266.8,58.9 L267.3,58.8 L267.8,58.7 L268.2,58.6 L268.7,58.5 L269.2,58.4 L269.7,58.3 L270.2,58.2 L270.6,58.2 L271.1,58.1 L271.6,58.0 L272.1,57.9 L272.6,57.8 L273.0,57.7 L273.5,57.6 L274.0,57.5 L274.5,57.4 L275.0,57.3 L275.4,57.3 L275.9,57.2 L276.4,57.1 L276.9,57.0 L277.4,56.9 L277.8,56.8 L278.3,56.7 L278.8,56.6 L279.3,56.6 L279.8,56.5 L280.2,56.4 L280.7,56.3 L281.2,56.2 L281.7,56.1 L282.2,56.0 L282.6,56.0 L283.1,55.9 L283.6,55.8 L284.1,55.7 L284.6,55.6 L285.0,55.5 L285.5,55.4 L286.0,55.4 L286.5,55.3 L287.0,55.2 L287.4,55.1 L287.9,55.0 L288.4,54.9 L288.9,54.9 L289.4,54.8 L289.8,54.7 L290.3,54.6 L290.8,54.5 L291.3,54.5 L291.8,54.4 L292.2,54.3 L292.7,54.2 L293.2,54.1 L293.7,54.1 L294.2,54.0 L294.6,53.9 L295.1,53.8 L295.6,53.7 L296.1,53.7 L296.6,53.6 L297.0,53.5 L297.5,53.4 L298.0,53.3 L298.5,53.3 L299.0,53.2 L299.4,53.1 L299.9,53.0 L300.4,53.0 L300.9,52.9 L301.4,52.8 L301.8,52.7 L302.3,52.6 L302.8,52.6 L303.3,52.5 L303.8,52.4 L304.2,52.3 L304.7,52.3 L305.2,52.2 L305.7,52.1 L306.2,52.0 L306.6,52.0 L307.1,51.9 L307.6,51.8 L308.1,51.7 L308.6,51.7 L309.0,51.6 L309.5,51.5 L310.0,51.4\" clip-path=\"url(#b10x3)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><text x=\"246.0\" y=\"55.3\" text-anchor=\"middle\" style=\"fill:var(--danger);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">y = ∛x</text><circle cx=\"38.0\" cy=\"182.0\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"150.0\" cy=\"150.0\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"166.0\" cy=\"118.0\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"173.0\" y=\"109.0\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(0, 0)</text><circle cx=\"182.0\" cy=\"86.0\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"294.0\" cy=\"54.0\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"301.0\" y=\"45.0\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(8, 2)</text></svg><p>The graph has <b>point symmetry</b> about the origin: turning it 180° about (0, 0) gives the same graph. This point is called the <b>point of symmetry</b>. Near it the graph is steep; far from it the graph is flat.</p><h4>Transformations of f(x) = ∛x</h4><div class=\"keybox\"><b>g(x) = a∛(x − h) + k</b><br>• a stretches, shrinks or (if a &lt; 0) reflects the graph in the x-axis.<br>• The point of symmetry moves from (0, 0) to <b>(h, k)</b>.<br>• Domain and range stay <b>all real numbers</b>.<br>• ∛(−x) = −∛x, so reflecting in the y-axis gives the same graph as reflecting in the x-axis.</div><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Translation: 2 left and 1 down</text><line x1=\"22.0\" y1=\"214.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"38.0\" y1=\"214.0\" x2=\"38.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"54.0\" y1=\"214.0\" x2=\"54.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"70.0\" y1=\"214.0\" x2=\"70.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"86.0\" y1=\"214.0\" x2=\"86.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"102.0\" y1=\"214.0\" x2=\"102.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"118.0\" y1=\"214.0\" x2=\"118.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"134.0\" y1=\"214.0\" x2=\"134.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"150.0\" y1=\"214.0\" x2=\"150.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"166.0\" y1=\"214.0\" x2=\"166.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"182.0\" y1=\"214.0\" x2=\"182.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"198.0\" y1=\"214.0\" x2=\"198.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"214.0\" y1=\"214.0\" x2=\"214.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"230.0\" y1=\"214.0\" x2=\"230.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"246.0\" y1=\"214.0\" x2=\"246.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"262.0\" y1=\"214.0\" x2=\"262.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"278.0\" y1=\"214.0\" x2=\"278.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"294.0\" y1=\"214.0\" x2=\"294.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"310.0\" y1=\"214.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"214.0\" x2=\"310.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"186.6\" x2=\"310.0\" y2=\"186.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"159.1\" x2=\"310.0\" y2=\"159.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"131.7\" x2=\"310.0\" y2=\"131.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"104.3\" x2=\"310.0\" y2=\"104.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"76.9\" x2=\"310.0\" y2=\"76.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"49.4\" x2=\"310.0\" y2=\"49.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"104.3\" x2=\"310.0\" y2=\"104.3\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"166.0\" y1=\"214.0\" x2=\"166.0\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"38.0\" y=\"113.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">−8</text><text class=\"po\" x=\"70.0\" y=\"113.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">−6</text><text class=\"po\" x=\"102.0\" y=\"113.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"134.0\" y=\"113.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"198.0\" y=\"113.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"230.0\" y=\"113.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"262.0\" y=\"113.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"294.0\" y=\"113.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><text class=\"po\" x=\"162.0\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"162.0\" y=\"186.6\" text-anchor=\"end\" dominant-baseline=\"middle\">−3</text><text class=\"po\" x=\"162.0\" y=\"159.1\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"162.0\" y=\"131.7\" text-anchor=\"end\" dominant-baseline=\"middle\">−1</text><text class=\"po\" x=\"162.0\" y=\"76.9\" text-anchor=\"end\" dominant-baseline=\"middle\">1</text><text class=\"po\" x=\"162.0\" y=\"49.4\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"162.0\" y=\"22.0\" text-anchor=\"end\" dominant-baseline=\"middle\">3</text><text class=\"po\" x=\"306.0\" y=\"96.3\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"174.0\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x4\"><rect x=\"22.0\" y=\"22.0\" width=\"288.0\" height=\"192.0\"/></clipPath><path d=\"M22.0,161.3 L22.5,161.3 L23.0,161.2 L23.4,161.1 L23.9,161.1 L24.4,161.0 L24.9,161.0 L25.4,160.9 L25.8,160.8 L26.3,160.8 L26.8,160.7 L27.3,160.6 L27.8,160.6 L28.2,160.5 L28.7,160.4 L29.2,160.4 L29.7,160.3 L30.2,160.2 L30.6,160.2 L31.1,160.1 L31.6,160.0 L32.1,160.0 L32.6,159.9 L33.0,159.8 L33.5,159.8 L34.0,159.7 L34.5,159.6 L35.0,159.6 L35.4,159.5 L35.9,159.4 L36.4,159.4 L36.9,159.3 L37.4,159.2 L37.8,159.2 L38.3,159.1 L38.8,159.0 L39.3,159.0 L39.8,158.9 L40.2,158.8 L40.7,158.8 L41.2,158.7 L41.7,158.6 L42.2,158.5 L42.6,158.5 L43.1,158.4 L43.6,158.3 L44.1,158.3 L44.6,158.2 L45.0,158.1 L45.5,158.0 L46.0,158.0 L46.5,157.9 L47.0,157.8 L47.4,157.8 L47.9,157.7 L48.4,157.6 L48.9,157.5 L49.4,157.5 L49.8,157.4 L50.3,157.3 L50.8,157.2 L51.3,157.2 L51.8,157.1 L52.2,157.0 L52.7,157.0 L53.2,156.9 L53.7,156.8 L54.2,156.7 L54.6,156.7 L55.1,156.6 L55.6,156.5 L56.1,156.4 L56.6,156.4 L57.0,156.3 L57.5,156.2 L58.0,156.1 L58.5,156.0 L59.0,156.0 L59.4,155.9 L59.9,155.8 L60.4,155.7 L60.9,155.7 L61.4,155.6 L61.8,155.5 L62.3,155.4 L62.8,155.3 L63.3,155.3 L63.8,155.2 L64.2,155.1 L64.7,155.0 L65.2,154.9 L65.7,154.9 L66.2,154.8 L66.6,154.7 L67.1,154.6 L67.6,154.5 L68.1,154.5 L68.6,154.4 L69.0,154.3 L69.5,154.2 L70.0,154.1 L70.5,154.0 L71.0,154.0 L71.4,153.9 L71.9,153.8 L72.4,153.7 L72.9,153.6 L73.4,153.5 L73.8,153.5 L74.3,153.4 L74.8,153.3 L75.3,153.2 L75.8,153.1 L76.2,153.0 L76.7,152.9 L77.2,152.8 L77.7,152.8 L78.2,152.7 L78.6,152.6 L79.1,152.5 L79.6,152.4 L80.1,152.3 L80.6,152.2 L81.0,152.1 L81.5,152.0 L82.0,152.0 L82.5,151.9 L83.0,151.8 L83.4,151.7 L83.9,151.6 L84.4,151.5 L84.9,151.4 L85.4,151.3 L85.8,151.2 L86.3,151.1 L86.8,151.0 L87.3,150.9 L87.8,150.8 L88.2,150.7 L88.7,150.7 L89.2,150.6 L89.7,150.5 L90.2,150.4 L90.6,150.3 L91.1,150.2 L91.6,150.1 L92.1,150.0 L92.6,149.9 L93.0,149.8 L93.5,149.7 L94.0,149.6 L94.5,149.5 L95.0,149.4 L95.4,149.3 L95.9,149.2 L96.4,149.1 L96.9,149.0 L97.4,148.9 L97.8,148.7 L98.3,148.6 L98.8,148.5 L99.3,148.4 L99.8,148.3 L100.2,148.2 L100.7,148.1 L101.2,148.0 L101.7,147.9 L102.2,147.8 L102.6,147.7 L103.1,147.6 L103.6,147.5 L104.1,147.3 L104.6,147.2 L105.0,147.1 L105.5,147.0 L106.0,146.9 L106.5,146.8 L107.0,146.7 L107.4,146.6 L107.9,146.4 L108.4,146.3 L108.9,146.2 L109.4,146.1 L109.8,146.0 L110.3,145.9 L110.8,145.7 L111.3,145.6 L111.8,145.5 L112.2,145.4 L112.7,145.2 L113.2,145.1 L113.7,145.0 L114.2,144.9 L114.6,144.7 L115.1,144.6 L115.6,144.5 L116.1,144.4 L116.6,144.2 L117.0,144.1 L117.5,144.0 L118.0,143.8 L118.5,143.7 L119.0,143.6 L119.4,143.4 L119.9,143.3 L120.4,143.2 L120.9,143.0 L121.4,142.9 L121.8,142.8 L122.3,142.6 L122.8,142.5 L123.3,142.3 L123.8,142.2 L124.2,142.1 L124.7,141.9 L125.2,141.8 L125.7,141.6 L126.2,141.5 L126.6,141.3 L127.1,141.2 L127.6,141.0 L128.1,140.9 L128.6,140.7 L129.0,140.5 L129.5,140.4 L130.0,140.2 L130.5,140.1 L131.0,139.9 L131.4,139.7 L131.9,139.6 L132.4,139.4 L132.9,139.2 L133.4,139.1 L133.8,138.9 L134.3,138.7 L134.8,138.6 L135.3,138.4 L135.8,138.2 L136.2,138.0 L136.7,137.8 L137.2,137.7 L137.7,137.5 L138.2,137.3 L138.6,137.1 L139.1,136.9 L139.6,136.7 L140.1,136.5 L140.6,136.3 L141.0,136.1 L141.5,135.9 L142.0,135.7 L142.5,135.5 L143.0,135.3 L143.4,135.0 L143.9,134.8 L144.4,134.6 L144.9,134.4 L145.4,134.1 L145.8,133.9 L146.3,133.7 L146.8,133.4 L147.3,133.2 L147.8,132.9 L148.2,132.7 L148.7,132.4 L149.2,132.2 L149.7,131.9 L150.2,131.6 L150.6,131.3 L151.1,131.1 L151.6,130.8 L152.1,130.5 L152.6,130.2 L153.0,129.9 L153.5,129.5 L154.0,129.2 L154.5,128.9 L155.0,128.5 L155.4,128.2 L155.9,127.8 L156.4,127.4 L156.9,127.0 L157.4,126.6 L157.8,126.2 L158.3,125.8 L158.8,125.3 L159.3,124.8 L159.8,124.3 L160.2,123.8 L160.7,123.2 L161.2,122.6 L161.7,122.0 L162.2,121.3 L162.6,120.6 L163.1,119.8 L163.6,118.9 L164.1,117.8 L164.6,116.6 L165.0,115.0 L165.5,112.8 L166.0,104.3 L166.5,95.8 L167.0,93.5 L167.4,92.0 L167.9,90.8 L168.4,89.7 L168.9,88.8 L169.4,88.0 L169.8,87.2 L170.3,86.6 L170.8,85.9 L171.3,85.3 L171.8,84.8 L172.2,84.2 L172.7,83.7 L173.2,83.3 L173.7,82.8 L174.2,82.4 L174.6,81.9 L175.1,81.5 L175.6,81.2 L176.1,80.8 L176.6,80.4 L177.0,80.0 L177.5,79.7 L178.0,79.4 L178.5,79.0 L179.0,78.7 L179.4,78.4 L179.9,78.1 L180.4,77.8 L180.9,77.5 L181.4,77.2 L181.8,76.9 L182.3,76.7 L182.8,76.4 L183.3,76.1 L183.8,75.9 L184.2,75.6 L184.7,75.4 L185.2,75.1 L185.7,74.9 L186.2,74.7 L186.6,74.4 L187.1,74.2 L187.6,74.0 L188.1,73.7 L188.6,73.5 L189.0,73.3 L189.5,73.1 L190.0,72.9 L190.5,72.7 L191.0,72.5 L191.4,72.3 L191.9,72.1 L192.4,71.9 L192.9,71.7 L193.4,71.5 L193.8,71.3 L194.3,71.1 L194.8,70.9 L195.3,70.7 L195.8,70.6 L196.2,70.4 L196.7,70.2 L197.2,70.0 L197.7,69.8 L198.2,69.7 L198.6,69.5 L199.1,69.3 L199.6,69.2 L200.1,69.0 L200.6,68.8 L201.0,68.7 L201.5,68.5 L202.0,68.3 L202.5,68.2 L203.0,68.0 L203.4,67.9 L203.9,67.7 L204.4,67.6 L204.9,67.4 L205.4,67.3 L205.8,67.1 L206.3,67.0 L206.8,66.8 L207.3,66.7 L207.8,66.5 L208.2,66.4 L208.7,66.2 L209.2,66.1 L209.7,66.0 L210.2,65.8 L210.6,65.7 L211.1,65.5 L211.6,65.4 L212.1,65.3 L212.6,65.1 L213.0,65.0 L213.5,64.9 L214.0,64.7 L214.5,64.6 L215.0,64.5 L215.4,64.3 L215.9,64.2 L216.4,64.1 L216.9,64.0 L217.4,63.8 L217.8,63.7 L218.3,63.6 L218.8,63.4 L219.3,63.3 L219.8,63.2 L220.2,63.1 L220.7,63.0 L221.2,62.8 L221.7,62.7 L222.2,62.6 L222.6,62.5 L223.1,62.4 L223.6,62.2 L224.1,62.1 L224.6,62.0 L225.0,61.9 L225.5,61.8 L226.0,61.7 L226.5,61.6 L227.0,61.4 L227.4,61.3 L227.9,61.2 L228.4,61.1 L228.9,61.0 L229.4,60.9 L229.8,60.8 L230.3,60.7 L230.8,60.6 L231.3,60.5 L231.8,60.4 L232.2,60.2 L232.7,60.1 L233.2,60.0 L233.7,59.9 L234.2,59.8 L234.6,59.7 L235.1,59.6 L235.6,59.5 L236.1,59.4 L236.6,59.3 L237.0,59.2 L237.5,59.1 L238.0,59.0 L238.5,58.9 L239.0,58.8 L239.4,58.7 L239.9,58.6 L240.4,58.5 L240.9,58.4 L241.4,58.3 L241.8,58.2 L242.3,58.1 L242.8,58.0 L243.3,57.9 L243.8,57.8 L244.2,57.7 L244.7,57.6 L245.2,57.5 L245.7,57.4 L246.2,57.4 L246.6,57.3 L247.1,57.2 L247.6,57.1 L248.1,57.0 L248.6,56.9 L249.0,56.8 L249.5,56.7 L250.0,56.6 L250.5,56.5 L251.0,56.4 L251.4,56.3 L251.9,56.3 L252.4,56.2 L252.9,56.1 L253.4,56.0 L253.8,55.9 L254.3,55.8 L254.8,55.7 L255.3,55.6 L255.8,55.5 L256.2,55.5 L256.7,55.4 L257.2,55.3 L257.7,55.2 L258.2,55.1 L258.6,55.0 L259.1,54.9 L259.6,54.9 L260.1,54.8 L260.6,54.7 L261.0,54.6 L261.5,54.5 L262.0,54.4 L262.5,54.4 L263.0,54.3 L263.4,54.2 L263.9,54.1 L264.4,54.0 L264.9,54.0 L265.4,53.9 L265.8,53.8 L266.3,53.7 L266.8,53.6 L267.3,53.5 L267.8,53.5 L268.2,53.4 L268.7,53.3 L269.2,53.2 L269.7,53.1 L270.2,53.1 L270.6,53.0 L271.1,52.9 L271.6,52.8 L272.1,52.8 L272.6,52.7 L273.0,52.6 L273.5,52.5 L274.0,52.4 L274.5,52.4 L275.0,52.3 L275.4,52.2 L275.9,52.1 L276.4,52.1 L276.9,52.0 L277.4,51.9 L277.8,51.8 L278.3,51.8 L278.8,51.7 L279.3,51.6 L279.8,51.5 L280.2,51.5 L280.7,51.4 L281.2,51.3 L281.7,51.2 L282.2,51.2 L282.6,51.1 L283.1,51.0 L283.6,51.0 L284.1,50.9 L284.6,50.8 L285.0,50.7 L285.5,50.7 L286.0,50.6 L286.5,50.5 L287.0,50.5 L287.4,50.4 L287.9,50.3 L288.4,50.2 L288.9,50.2 L289.4,50.1 L289.8,50.0 L290.3,50.0 L290.8,49.9 L291.3,49.8 L291.8,49.8 L292.2,49.7 L292.7,49.6 L293.2,49.5 L293.7,49.5 L294.2,49.4 L294.6,49.3 L295.1,49.3 L295.6,49.2 L296.1,49.1 L296.6,49.1 L297.0,49.0 L297.5,48.9 L298.0,48.9 L298.5,48.8 L299.0,48.7 L299.4,48.7 L299.9,48.6 L300.4,48.5 L300.9,48.5 L301.4,48.4 L301.8,48.3 L302.3,48.3 L302.8,48.2 L303.3,48.1 L303.8,48.1 L304.2,48.0 L304.7,47.9 L305.2,47.9 L305.7,47.8 L306.2,47.7 L306.6,47.7 L307.1,47.6 L307.6,47.6 L308.1,47.5 L308.6,47.4 L309.0,47.4 L309.5,47.3 L310.0,47.2\" clip-path=\"url(#b10x4)\" style=\"fill:none;stroke:var(--accent-text);stroke-width:2.2;stroke-dasharray:6 4\"/><text x=\"270.0\" y=\"45.1\" text-anchor=\"middle\" style=\"fill:var(--accent-text);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">y = ∛x</text><path d=\"M22.0,184.2 L22.5,184.1 L23.0,184.0 L23.4,184.0 L23.9,183.9 L24.4,183.8 L24.9,183.7 L25.4,183.7 L25.8,183.6 L26.3,183.5 L26.8,183.4 L27.3,183.3 L27.8,183.3 L28.2,183.2 L28.7,183.1 L29.2,183.0 L29.7,183.0 L30.2,182.9 L30.6,182.8 L31.1,182.7 L31.6,182.6 L32.1,182.6 L32.6,182.5 L33.0,182.4 L33.5,182.3 L34.0,182.2 L34.5,182.2 L35.0,182.1 L35.4,182.0 L35.9,181.9 L36.4,181.8 L36.9,181.7 L37.4,181.7 L37.8,181.6 L38.3,181.5 L38.8,181.4 L39.3,181.3 L39.8,181.2 L40.2,181.2 L40.7,181.1 L41.2,181.0 L41.7,180.9 L42.2,180.8 L42.6,180.7 L43.1,180.7 L43.6,180.6 L44.1,180.5 L44.6,180.4 L45.0,180.3 L45.5,180.2 L46.0,180.1 L46.5,180.0 L47.0,180.0 L47.4,179.9 L47.9,179.8 L48.4,179.7 L48.9,179.6 L49.4,179.5 L49.8,179.4 L50.3,179.3 L50.8,179.2 L51.3,179.1 L51.8,179.1 L52.2,179.0 L52.7,178.9 L53.2,178.8 L53.7,178.7 L54.2,178.6 L54.6,178.5 L55.1,178.4 L55.6,178.3 L56.1,178.2 L56.6,178.1 L57.0,178.0 L57.5,177.9 L58.0,177.8 L58.5,177.7 L59.0,177.6 L59.4,177.5 L59.9,177.4 L60.4,177.3 L60.9,177.2 L61.4,177.1 L61.8,177.0 L62.3,176.9 L62.8,176.8 L63.3,176.7 L63.8,176.6 L64.2,176.5 L64.7,176.4 L65.2,176.3 L65.7,176.2 L66.2,176.1 L66.6,176.0 L67.1,175.9 L67.6,175.8 L68.1,175.7 L68.6,175.6 L69.0,175.5 L69.5,175.4 L70.0,175.3 L70.5,175.1 L71.0,175.0 L71.4,174.9 L71.9,174.8 L72.4,174.7 L72.9,174.6 L73.4,174.5 L73.8,174.4 L74.3,174.3 L74.8,174.1 L75.3,174.0 L75.8,173.9 L76.2,173.8 L76.7,173.7 L77.2,173.6 L77.7,173.4 L78.2,173.3 L78.6,173.2 L79.1,173.1 L79.6,173.0 L80.1,172.8 L80.6,172.7 L81.0,172.6 L81.5,172.5 L82.0,172.3 L82.5,172.2 L83.0,172.1 L83.4,172.0 L83.9,171.8 L84.4,171.7 L84.9,171.6 L85.4,171.4 L85.8,171.3 L86.3,171.2 L86.8,171.1 L87.3,170.9 L87.8,170.8 L88.2,170.6 L88.7,170.5 L89.2,170.4 L89.7,170.2 L90.2,170.1 L90.6,170.0 L91.1,169.8 L91.6,169.7 L92.1,169.5 L92.6,169.4 L93.0,169.2 L93.5,169.1 L94.0,168.9 L94.5,168.8 L95.0,168.6 L95.4,168.5 L95.9,168.3 L96.4,168.2 L96.9,168.0 L97.4,167.9 L97.8,167.7 L98.3,167.5 L98.8,167.4 L99.3,167.2 L99.8,167.1 L100.2,166.9 L100.7,166.7 L101.2,166.6 L101.7,166.4 L102.2,166.2 L102.6,166.0 L103.1,165.9 L103.6,165.7 L104.1,165.5 L104.6,165.3 L105.0,165.1 L105.5,165.0 L106.0,164.8 L106.5,164.6 L107.0,164.4 L107.4,164.2 L107.9,164.0 L108.4,163.8 L108.9,163.6 L109.4,163.4 L109.8,163.2 L110.3,163.0 L110.8,162.8 L111.3,162.5 L111.8,162.3 L112.2,162.1 L112.7,161.9 L113.2,161.6 L113.7,161.4 L114.2,161.2 L114.6,160.9 L115.1,160.7 L115.6,160.5 L116.1,160.2 L116.6,159.9 L117.0,159.7 L117.5,159.4 L118.0,159.1 L118.5,158.9 L119.0,158.6 L119.4,158.3 L119.9,158.0 L120.4,157.7 L120.9,157.4 L121.4,157.1 L121.8,156.7 L122.3,156.4 L122.8,156.1 L123.3,155.7 L123.8,155.4 L124.2,155.0 L124.7,154.6 L125.2,154.2 L125.7,153.8 L126.2,153.3 L126.6,152.9 L127.1,152.4 L127.6,151.9 L128.1,151.4 L128.6,150.9 L129.0,150.3 L129.5,149.7 L130.0,149.0 L130.5,148.3 L131.0,147.5 L131.4,146.6 L131.9,145.6 L132.4,144.4 L132.9,143.0 L133.4,141.1 L133.8,137.6 L134.3,124.3 L134.8,121.6 L135.3,119.9 L135.8,118.6 L136.2,117.5 L136.7,116.5 L137.2,115.7 L137.7,114.9 L138.2,114.2 L138.6,113.6 L139.1,113.0 L139.6,112.4 L140.1,111.8 L140.6,111.3 L141.0,110.9 L141.5,110.4 L142.0,109.9 L142.5,109.5 L143.0,109.1 L143.4,108.7 L143.9,108.3 L144.4,108.0 L144.9,107.6 L145.4,107.2 L145.8,106.9 L146.3,106.6 L146.8,106.3 L147.3,105.9 L147.8,105.6 L148.2,105.3 L148.7,105.0 L149.2,104.8 L149.7,104.5 L150.2,104.2 L150.6,103.9 L151.1,103.7 L151.6,103.4 L152.1,103.1 L152.6,102.9 L153.0,102.6 L153.5,102.4 L154.0,102.2 L154.5,101.9 L155.0,101.7 L155.4,101.5 L155.9,101.3 L156.4,101.0 L156.9,100.8 L157.4,100.6 L157.8,100.4 L158.3,100.2 L158.8,100.0 L159.3,99.8 L159.8,99.6 L160.2,99.4 L160.7,99.2 L161.2,99.0 L161.7,98.8 L162.2,98.6 L162.6,98.4 L163.1,98.2 L163.6,98.0 L164.1,97.9 L164.6,97.7 L165.0,97.5 L165.5,97.3 L166.0,97.2 L166.5,97.0 L167.0,96.8 L167.4,96.6 L167.9,96.5 L168.4,96.3 L168.9,96.1 L169.4,96.0 L169.8,95.8 L170.3,95.7 L170.8,95.5 L171.3,95.4 L171.8,95.2 L172.2,95.0 L172.7,94.9 L173.2,94.7 L173.7,94.6 L174.2,94.4 L174.6,94.3 L175.1,94.1 L175.6,94.0 L176.1,93.9 L176.6,93.7 L177.0,93.6 L177.5,93.4 L178.0,93.3 L178.5,93.1 L179.0,93.0 L179.4,92.9 L179.9,92.7 L180.4,92.6 L180.9,92.5 L181.4,92.3 L181.8,92.2 L182.3,92.1 L182.8,91.9 L183.3,91.8 L183.8,91.7 L184.2,91.5 L184.7,91.4 L185.2,91.3 L185.7,91.2 L186.2,91.0 L186.6,90.9 L187.1,90.8 L187.6,90.7 L188.1,90.6 L188.6,90.4 L189.0,90.3 L189.5,90.2 L190.0,90.1 L190.5,90.0 L191.0,89.8 L191.4,89.7 L191.9,89.6 L192.4,89.5 L192.9,89.4 L193.4,89.3 L193.8,89.1 L194.3,89.0 L194.8,88.9 L195.3,88.8 L195.8,88.7 L196.2,88.6 L196.7,88.5 L197.2,88.4 L197.7,88.2 L198.2,88.1 L198.6,88.0 L199.1,87.9 L199.6,87.8 L200.1,87.7 L200.6,87.6 L201.0,87.5 L201.5,87.4 L202.0,87.3 L202.5,87.2 L203.0,87.1 L203.4,87.0 L203.9,86.9 L204.4,86.8 L204.9,86.7 L205.4,86.6 L205.8,86.5 L206.3,86.4 L206.8,86.3 L207.3,86.2 L207.8,86.1 L208.2,86.0 L208.7,85.9 L209.2,85.8 L209.7,85.7 L210.2,85.6 L210.6,85.5 L211.1,85.4 L211.6,85.3 L212.1,85.2 L212.6,85.1 L213.0,85.0 L213.5,84.9 L214.0,84.8 L214.5,84.7 L215.0,84.6 L215.4,84.5 L215.9,84.4 L216.4,84.3 L216.9,84.3 L217.4,84.2 L217.8,84.1 L218.3,84.0 L218.8,83.9 L219.3,83.8 L219.8,83.7 L220.2,83.6 L220.7,83.5 L221.2,83.4 L221.7,83.4 L222.2,83.3 L222.6,83.2 L223.1,83.1 L223.6,83.0 L224.1,82.9 L224.6,82.8 L225.0,82.7 L225.5,82.7 L226.0,82.6 L226.5,82.5 L227.0,82.4 L227.4,82.3 L227.9,82.2 L228.4,82.2 L228.9,82.1 L229.4,82.0 L229.8,81.9 L230.3,81.8 L230.8,81.7 L231.3,81.7 L231.8,81.6 L232.2,81.5 L232.7,81.4 L233.2,81.3 L233.7,81.2 L234.2,81.2 L234.6,81.1 L235.1,81.0 L235.6,80.9 L236.1,80.8 L236.6,80.8 L237.0,80.7 L237.5,80.6 L238.0,80.5 L238.5,80.4 L239.0,80.4 L239.4,80.3 L239.9,80.2 L240.4,80.1 L240.9,80.1 L241.4,80.0 L241.8,79.9 L242.3,79.8 L242.8,79.7 L243.3,79.7 L243.8,79.6 L244.2,79.5 L244.7,79.4 L245.2,79.4 L245.7,79.3 L246.2,79.2 L246.6,79.1 L247.1,79.1 L247.6,79.0 L248.1,78.9 L248.6,78.8 L249.0,78.8 L249.5,78.7 L250.0,78.6 L250.5,78.6 L251.0,78.5 L251.4,78.4 L251.9,78.3 L252.4,78.3 L252.9,78.2 L253.4,78.1 L253.8,78.0 L254.3,78.0 L254.8,77.9 L255.3,77.8 L255.8,77.8 L256.2,77.7 L256.7,77.6 L257.2,77.6 L257.7,77.5 L258.2,77.4 L258.6,77.3 L259.1,77.3 L259.6,77.2 L260.1,77.1 L260.6,77.1 L261.0,77.0 L261.5,76.9 L262.0,76.9 L262.5,76.8 L263.0,76.7 L263.4,76.7 L263.9,76.6 L264.4,76.5 L264.9,76.4 L265.4,76.4 L265.8,76.3 L266.3,76.2 L266.8,76.2 L267.3,76.1 L267.8,76.0 L268.2,76.0 L268.7,75.9 L269.2,75.8 L269.7,75.8 L270.2,75.7 L270.6,75.6 L271.1,75.6 L271.6,75.5 L272.1,75.5 L272.6,75.4 L273.0,75.3 L273.5,75.3 L274.0,75.2 L274.5,75.1 L275.0,75.1 L275.4,75.0 L275.9,74.9 L276.4,74.9 L276.9,74.8 L277.4,74.7 L277.8,74.7 L278.3,74.6 L278.8,74.6 L279.3,74.5 L279.8,74.4 L280.2,74.4 L280.7,74.3 L281.2,74.2 L281.7,74.2 L282.2,74.1 L282.6,74.1 L283.1,74.0 L283.6,73.9 L284.1,73.9 L284.6,73.8 L285.0,73.7 L285.5,73.7 L286.0,73.6 L286.5,73.6 L287.0,73.5 L287.4,73.4 L287.9,73.4 L288.4,73.3 L288.9,73.3 L289.4,73.2 L289.8,73.1 L290.3,73.1 L290.8,73.0 L291.3,73.0 L291.8,72.9 L292.2,72.8 L292.7,72.8 L293.2,72.7 L293.7,72.7 L294.2,72.6 L294.6,72.5 L295.1,72.5 L295.6,72.4 L296.1,72.4 L296.6,72.3 L297.0,72.2 L297.5,72.2 L298.0,72.1 L298.5,72.1 L299.0,72.0 L299.4,72.0 L299.9,71.9 L300.4,71.8 L300.9,71.8 L301.4,71.7 L301.8,71.7 L302.3,71.6 L302.8,71.6 L303.3,71.5 L303.8,71.4 L304.2,71.4 L304.7,71.3 L305.2,71.3 L305.7,71.2 L306.2,71.2 L306.6,71.1 L307.1,71.0 L307.6,71.0 L308.1,70.9 L308.6,70.9 L309.0,70.8 L309.5,70.8 L310.0,70.7\" clip-path=\"url(#b10x4)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><text x=\"78.0\" y=\"165.4\" text-anchor=\"middle\" style=\"fill:var(--danger);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">h(x) = ∛(x + 2) − 1</text><circle cx=\"134.0\" cy=\"131.7\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"141.0\" y=\"122.7\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(−2, −1)</text></svg><div class=\"ex\"><div class=\"exh\">Worked example 1 · Point of symmetry and points</div><div class=\"exl\">Graph h(x) = ∛(x + 2) − 1.<br>h = −2 and k = −1, so the point of symmetry is (−2, −1).<br>Move the points of the parent graph 2 left and 1 down: (−10, −3), (−3, −2), (−2, −1), (−1, 0), (6, 1).</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Intercepts</div><div class=\"exl\">Find the intercepts of g(x) = ∛(x − 1) + 2.<br>y-intercept: g(0) = ∛(−1) + 2 = 1.<br>x-intercept: ∛(x − 1) = −2 → x − 1 = −8 → <b>x = −7</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Compare rates of change</div><div class=\"exl\">Compare f(x) = ∛x and g(x) = √x from x = 0 to x = 1, and from x = 1 to x = 64.<br>0 to 1: both rise by 1, so both rates are 1.<br>1 to 64: ∛64 − 1 = 3, √64 − 1 = 7, so {3/63} &lt; {7/63}. The square root grows faster here.</div></div><div class=\"keybox\"><b>Common mistake.</b> Do not copy the square-root rules. ∛x is defined for negative x: ∛(−27) = −3. So the range of ∛x + 5 is all real numbers, not y ≥ 5.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s2\">Practise 10.2 →</button></div></section><section class=\"note\" id=\"n103\"><h2>10.3 Solving Radical Equations</h2><p class=\"lt\"><b>Learning target:</b> I can solve equations with square roots and cube roots by isolating the radical and raising both sides to a power, and identify extraneous solutions.</p><p>A <b>radical equation</b> is an equation with a variable inside a radical, such as √(x + 3) = 5. To solve it, undo the radical by raising both sides to the same power.</p><div class=\"keybox\"><b>Solving a radical equation</b><br>1. <b>Isolate</b> the radical on one side.<br>2. <b>Square</b> both sides (for √) or <b>cube</b> both sides (for ∛).<br>3. Solve the new equation.<br>4. <b>Check</b> every answer in the original equation.</div><div class=\"ex\"><div class=\"exh\">Worked example 1 · Isolate, then square</div><div class=\"exl\">Solve 2√x − 5 = 3.<br>Add 5 and divide by 2: √x = 4.<br>Square: <b>x = 16</b>. Check: 2(4) − 5 = 3 ✓</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Cube root</div><div class=\"exl\">Solve ∛(2x − 3) + 4 = 1.<br>Subtract 4: ∛(2x − 3) = −3.<br>Cube: 2x − 3 = −27, so 2x = −24 and <b>x = −12</b>.</div></div><h4>Extraneous solutions</h4><p>Squaring can create answers that do not work, because a negative number and its opposite have the same square: (−3)² = 3². A value that comes out of the algebra but fails in the <b>original</b> equation is an <b>extraneous solution</b>.</p><div class=\"ex\"><div class=\"exh\">Worked example 3 · Check every answer</div><div class=\"exl\">Solve √(x + 6) = x.<br>Square: x + 6 = x², so x² − x − 6 = 0 and (x − 3)(x + 2) = 0.<br>x = 3: √9 = 3 ✓.  x = −2: √4 = 2 ≠ −2 ✗. So −2 is extraneous and the only solution is <b>x = 3</b>.</div></div><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Only one intersection: x = 3</text><line x1=\"22.0\" y1=\"214.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"44.2\" y1=\"214.0\" x2=\"44.2\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"66.3\" y1=\"214.0\" x2=\"66.3\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"88.5\" y1=\"214.0\" x2=\"88.5\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"110.6\" y1=\"214.0\" x2=\"110.6\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"132.8\" y1=\"214.0\" x2=\"132.8\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"154.9\" y1=\"214.0\" x2=\"154.9\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"177.1\" y1=\"214.0\" x2=\"177.1\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"199.2\" y1=\"214.0\" x2=\"199.2\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"221.4\" y1=\"214.0\" x2=\"221.4\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"243.5\" y1=\"214.0\" x2=\"243.5\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"265.7\" y1=\"214.0\" x2=\"265.7\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"287.8\" y1=\"214.0\" x2=\"287.8\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"310.0\" y1=\"214.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"214.0\" x2=\"310.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"190.0\" x2=\"310.0\" y2=\"190.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"166.0\" x2=\"310.0\" y2=\"166.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"142.0\" x2=\"310.0\" y2=\"142.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"118.0\" x2=\"310.0\" y2=\"118.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"94.0\" x2=\"310.0\" y2=\"94.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"70.0\" x2=\"310.0\" y2=\"70.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"46.0\" x2=\"310.0\" y2=\"46.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"142.0\" x2=\"310.0\" y2=\"142.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"177.1\" y1=\"214.0\" x2=\"177.1\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"44.2\" y=\"151.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−6</text><text class=\"po\" x=\"88.5\" y=\"151.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"132.8\" y=\"151.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"221.4\" y=\"151.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"265.7\" y=\"151.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"310.0\" y=\"151.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"173.1\" y=\"190.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"173.1\" y=\"94.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"173.1\" y=\"46.0\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"306.0\" y=\"134.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"185.1\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x5\"><rect x=\"22.0\" y=\"22.0\" width=\"288.0\" height=\"192.0\"/></clipPath><path d=\"M44.6,138.8 L45.0,137.2 L45.5,136.0 L46.0,135.1 L46.5,134.2 L47.0,133.5 L47.4,132.8 L47.9,132.1 L48.4,131.5 L48.9,130.9 L49.4,130.4 L49.8,129.8 L50.3,129.3 L50.8,128.9 L51.3,128.4 L51.8,127.9 L52.2,127.5 L52.7,127.1 L53.2,126.7 L53.7,126.3 L54.2,125.9 L54.6,125.5 L55.1,125.1 L55.6,124.7 L56.1,124.4 L56.6,124.0 L57.0,123.7 L57.5,123.4 L58.0,123.0 L58.5,122.7 L59.0,122.4 L59.4,122.1 L59.9,121.8 L60.4,121.4 L60.9,121.1 L61.4,120.8 L61.8,120.6 L62.3,120.3 L62.8,120.0 L63.3,119.7 L63.8,119.4 L64.2,119.1 L64.7,118.9 L65.2,118.6 L65.7,118.3 L66.2,118.1 L66.6,117.8 L67.1,117.6 L67.6,117.3 L68.1,117.1 L68.6,116.8 L69.0,116.6 L69.5,116.3 L70.0,116.1 L70.5,115.8 L71.0,115.6 L71.4,115.4 L71.9,115.1 L72.4,114.9 L72.9,114.7 L73.4,114.4 L73.8,114.2 L74.3,114.0 L74.8,113.8 L75.3,113.6 L75.8,113.3 L76.2,113.1 L76.7,112.9 L77.2,112.7 L77.7,112.5 L78.2,112.3 L78.6,112.1 L79.1,111.8 L79.6,111.6 L80.1,111.4 L80.6,111.2 L81.0,111.0 L81.5,110.8 L82.0,110.6 L82.5,110.4 L83.0,110.2 L83.4,110.0 L83.9,109.8 L84.4,109.7 L84.9,109.5 L85.4,109.3 L85.8,109.1 L86.3,108.9 L86.8,108.7 L87.3,108.5 L87.8,108.3 L88.2,108.1 L88.7,108.0 L89.2,107.8 L89.7,107.6 L90.2,107.4 L90.6,107.2 L91.1,107.1 L91.6,106.9 L92.1,106.7 L92.6,106.5 L93.0,106.3 L93.5,106.2 L94.0,106.0 L94.5,105.8 L95.0,105.7 L95.4,105.5 L95.9,105.3 L96.4,105.1 L96.9,105.0 L97.4,104.8 L97.8,104.6 L98.3,104.5 L98.8,104.3 L99.3,104.1 L99.8,104.0 L100.2,103.8 L100.7,103.7 L101.2,103.5 L101.7,103.3 L102.2,103.2 L102.6,103.0 L103.1,102.8 L103.6,102.7 L104.1,102.5 L104.6,102.4 L105.0,102.2 L105.5,102.1 L106.0,101.9 L106.5,101.7 L107.0,101.6 L107.4,101.4 L107.9,101.3 L108.4,101.1 L108.9,101.0 L109.4,100.8 L109.8,100.7 L110.3,100.5 L110.8,100.4 L111.3,100.2 L111.8,100.1 L112.2,99.9 L112.7,99.8 L113.2,99.6 L113.7,99.5 L114.2,99.3 L114.6,99.2 L115.1,99.0 L115.6,98.9 L116.1,98.8 L116.6,98.6 L117.0,98.5 L117.5,98.3 L118.0,98.2 L118.5,98.0 L119.0,97.9 L119.4,97.8 L119.9,97.6 L120.4,97.5 L120.9,97.3 L121.4,97.2 L121.8,97.1 L122.3,96.9 L122.8,96.8 L123.3,96.6 L123.8,96.5 L124.2,96.4 L124.7,96.2 L125.2,96.1 L125.7,96.0 L126.2,95.8 L126.6,95.7 L127.1,95.6 L127.6,95.4 L128.1,95.3 L128.6,95.2 L129.0,95.0 L129.5,94.9 L130.0,94.8 L130.5,94.6 L131.0,94.5 L131.4,94.4 L131.9,94.2 L132.4,94.1 L132.9,94.0 L133.4,93.8 L133.8,93.7 L134.3,93.6 L134.8,93.5 L135.3,93.3 L135.8,93.2 L136.2,93.1 L136.7,92.9 L137.2,92.8 L137.7,92.7 L138.2,92.6 L138.6,92.4 L139.1,92.3 L139.6,92.2 L140.1,92.1 L140.6,91.9 L141.0,91.8 L141.5,91.7 L142.0,91.6 L142.5,91.4 L143.0,91.3 L143.4,91.2 L143.9,91.1 L144.4,90.9 L144.9,90.8 L145.4,90.7 L145.8,90.6 L146.3,90.5 L146.8,90.3 L147.3,90.2 L147.8,90.1 L148.2,90.0 L148.7,89.9 L149.2,89.7 L149.7,89.6 L150.2,89.5 L150.6,89.4 L151.1,89.3 L151.6,89.1 L152.1,89.0 L152.6,88.9 L153.0,88.8 L153.5,88.7 L154.0,88.6 L154.5,88.4 L155.0,88.3 L155.4,88.2 L155.9,88.1 L156.4,88.0 L156.9,87.9 L157.4,87.7 L157.8,87.6 L158.3,87.5 L158.8,87.4 L159.3,87.3 L159.8,87.2 L160.2,87.1 L160.7,86.9 L161.2,86.8 L161.7,86.7 L162.2,86.6 L162.6,86.5 L163.1,86.4 L163.6,86.3 L164.1,86.2 L164.6,86.0 L165.0,85.9 L165.5,85.8 L166.0,85.7 L166.5,85.6 L167.0,85.5 L167.4,85.4 L167.9,85.3 L168.4,85.2 L168.9,85.1 L169.4,84.9 L169.8,84.8 L170.3,84.7 L170.8,84.6 L171.3,84.5 L171.8,84.4 L172.2,84.3 L172.7,84.2 L173.2,84.1 L173.7,84.0 L174.2,83.9 L174.6,83.8 L175.1,83.6 L175.6,83.5 L176.1,83.4 L176.6,83.3 L177.0,83.2 L177.5,83.1 L178.0,83.0 L178.5,82.9 L179.0,82.8 L179.4,82.7 L179.9,82.6 L180.4,82.5 L180.9,82.4 L181.4,82.3 L181.8,82.2 L182.3,82.1 L182.8,82.0 L183.3,81.9 L183.8,81.8 L184.2,81.6 L184.7,81.5 L185.2,81.4 L185.7,81.3 L186.2,81.2 L186.6,81.1 L187.1,81.0 L187.6,80.9 L188.1,80.8 L188.6,80.7 L189.0,80.6 L189.5,80.5 L190.0,80.4 L190.5,80.3 L191.0,80.2 L191.4,80.1 L191.9,80.0 L192.4,79.9 L192.9,79.8 L193.4,79.7 L193.8,79.6 L194.3,79.5 L194.8,79.4 L195.3,79.3 L195.8,79.2 L196.2,79.1 L196.7,79.0 L197.2,78.9 L197.7,78.8 L198.2,78.7 L198.6,78.6 L199.1,78.5 L199.6,78.4 L200.1,78.3 L200.6,78.2 L201.0,78.1 L201.5,78.0 L202.0,77.9 L202.5,77.8 L203.0,77.7 L203.4,77.6 L203.9,77.5 L204.4,77.5 L204.9,77.4 L205.4,77.3 L205.8,77.2 L206.3,77.1 L206.8,77.0 L207.3,76.9 L207.8,76.8 L208.2,76.7 L208.7,76.6 L209.2,76.5 L209.7,76.4 L210.2,76.3 L210.6,76.2 L211.1,76.1 L211.6,76.0 L212.1,75.9 L212.6,75.8 L213.0,75.7 L213.5,75.6 L214.0,75.5 L214.5,75.5 L215.0,75.4 L215.4,75.3 L215.9,75.2 L216.4,75.1 L216.9,75.0 L217.4,74.9 L217.8,74.8 L218.3,74.7 L218.8,74.6 L219.3,74.5 L219.8,74.4 L220.2,74.3 L220.7,74.2 L221.2,74.2 L221.7,74.1 L222.2,74.0 L222.6,73.9 L223.1,73.8 L223.6,73.7 L224.1,73.6 L224.6,73.5 L225.0,73.4 L225.5,73.3 L226.0,73.2 L226.5,73.1 L227.0,73.1 L227.4,73.0 L227.9,72.9 L228.4,72.8 L228.9,72.7 L229.4,72.6 L229.8,72.5 L230.3,72.4 L230.8,72.3 L231.3,72.2 L231.8,72.2 L232.2,72.1 L232.7,72.0 L233.2,71.9 L233.7,71.8 L234.2,71.7 L234.6,71.6 L235.1,71.5 L235.6,71.4 L236.1,71.4 L236.6,71.3 L237.0,71.2 L237.5,71.1 L238.0,71.0 L238.5,70.9 L239.0,70.8 L239.4,70.7 L239.9,70.7 L240.4,70.6 L240.9,70.5 L241.4,70.4 L241.8,70.3 L242.3,70.2 L242.8,70.1 L243.3,70.0 L243.8,70.0 L244.2,69.9 L244.7,69.8 L245.2,69.7 L245.7,69.6 L246.2,69.5 L246.6,69.4 L247.1,69.4 L247.6,69.3 L248.1,69.2 L248.6,69.1 L249.0,69.0 L249.5,68.9 L250.0,68.8 L250.5,68.8 L251.0,68.7 L251.4,68.6 L251.9,68.5 L252.4,68.4 L252.9,68.3 L253.4,68.2 L253.8,68.2 L254.3,68.1 L254.8,68.0 L255.3,67.9 L255.8,67.8 L256.2,67.7 L256.7,67.7 L257.2,67.6 L257.7,67.5 L258.2,67.4 L258.6,67.3 L259.1,67.2 L259.6,67.2 L260.1,67.1 L260.6,67.0 L261.0,66.9 L261.5,66.8 L262.0,66.7 L262.5,66.7 L263.0,66.6 L263.4,66.5 L263.9,66.4 L264.4,66.3 L264.9,66.2 L265.4,66.2 L265.8,66.1 L266.3,66.0 L266.8,65.9 L267.3,65.8 L267.8,65.8 L268.2,65.7 L268.7,65.6 L269.2,65.5 L269.7,65.4 L270.2,65.3 L270.6,65.3 L271.1,65.2 L271.6,65.1 L272.1,65.0 L272.6,64.9 L273.0,64.9 L273.5,64.8 L274.0,64.7 L274.5,64.6 L275.0,64.5 L275.4,64.5 L275.9,64.4 L276.4,64.3 L276.9,64.2 L277.4,64.1 L277.8,64.1 L278.3,64.0 L278.8,63.9 L279.3,63.8 L279.8,63.7 L280.2,63.7 L280.7,63.6 L281.2,63.5 L281.7,63.4 L282.2,63.3 L282.6,63.3 L283.1,63.2 L283.6,63.1 L284.1,63.0 L284.6,62.9 L285.0,62.9 L285.5,62.8 L286.0,62.7 L286.5,62.6 L287.0,62.5 L287.4,62.5 L287.9,62.4 L288.4,62.3 L288.9,62.2 L289.4,62.2 L289.8,62.1 L290.3,62.0 L290.8,61.9 L291.3,61.8 L291.8,61.8 L292.2,61.7 L292.7,61.6 L293.2,61.5 L293.7,61.5 L294.2,61.4 L294.6,61.3 L295.1,61.2 L295.6,61.1 L296.1,61.1 L296.6,61.0 L297.0,60.9 L297.5,60.8 L298.0,60.8 L298.5,60.7 L299.0,60.6 L299.4,60.5 L299.9,60.5 L300.4,60.4 L300.9,60.3 L301.4,60.2 L301.8,60.1 L302.3,60.1 L302.8,60.0 L303.3,59.9 L303.8,59.8 L304.2,59.8 L304.7,59.7 L305.2,59.6 L305.7,59.5 L306.2,59.5 L306.6,59.4 L307.1,59.3 L307.6,59.2 L308.1,59.2 L308.6,59.1 L309.0,59.0 L309.5,58.9 L310.0,58.9\" clip-path=\"url(#b10x5)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><text x=\"99.5\" y=\"96.1\" text-anchor=\"middle\" style=\"fill:var(--danger);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">y = √(x + 6)</text><path d=\"M22.0,310.0 L22.5,309.5 L23.0,309.0 L23.4,308.4 L23.9,307.9 L24.4,307.4 L24.9,306.9 L25.4,306.4 L25.8,305.8 L26.3,305.3 L26.8,304.8 L27.3,304.3 L27.8,303.8 L28.2,303.2 L28.7,302.7 L29.2,302.2 L29.7,301.7 L30.2,301.2 L30.6,300.6 L31.1,300.1 L31.6,299.6 L32.1,299.1 L32.6,298.6 L33.0,298.0 L33.5,297.5 L34.0,297.0 L34.5,296.5 L35.0,296.0 L35.4,295.4 L35.9,294.9 L36.4,294.4 L36.9,293.9 L37.4,293.4 L37.8,292.8 L38.3,292.3 L38.8,291.8 L39.3,291.3 L39.8,290.8 L40.2,290.2 L40.7,289.7 L41.2,289.2 L41.7,288.7 L42.2,288.2 L42.6,287.6 L43.1,287.1 L43.6,286.6 L44.1,286.1 L44.6,285.6 L45.0,285.0 L45.5,284.5 L46.0,284.0 L46.5,283.5 L47.0,283.0 L47.4,282.4 L47.9,281.9 L48.4,281.4 L48.9,280.9 L49.4,280.4 L49.8,279.8 L50.3,279.3 L50.8,278.8 L51.3,278.3 L51.8,277.8 L52.2,277.2 L52.7,276.7 L53.2,276.2 L53.7,275.7 L54.2,275.2 L54.6,274.6 L55.1,274.1 L55.6,273.6 L56.1,273.1 L56.6,272.6 L57.0,272.0 L57.5,271.5 L58.0,271.0 L58.5,270.5 L59.0,270.0 L59.4,269.4 L59.9,268.9 L60.4,268.4 L60.9,267.9 L61.4,267.4 L61.8,266.8 L62.3,266.3 L62.8,265.8 L63.3,265.3 L63.8,264.8 L64.2,264.2 L64.7,263.7 L65.2,263.2 L65.7,262.7 L66.2,262.2 L66.6,261.6 L67.1,261.1 L67.6,260.6 L68.1,260.1 L68.6,259.6 L69.0,259.0 L69.5,258.5 L70.0,258.0 L70.5,257.5 L71.0,257.0 L71.4,256.4 L71.9,255.9 L72.4,255.4 L72.9,254.9 L73.4,254.4 L73.8,253.8 L74.3,253.3 L74.8,252.8 L75.3,252.3 L75.8,251.8 L76.2,251.2 L76.7,250.7 L77.2,250.2 L77.7,249.7 L78.2,249.2 L78.6,248.6 L79.1,248.1 L79.6,247.6 L80.1,247.1 L80.6,246.6 L81.0,246.0 L81.5,245.5 L82.0,245.0 L82.5,244.5 L83.0,244.0 L83.4,243.4 L83.9,242.9 L84.4,242.4 L84.9,241.9 L85.4,241.4 L85.8,240.8 L86.3,240.3 L86.8,239.8 L87.3,239.3 L87.8,238.8 L88.2,238.2 L88.7,237.7 L89.2,237.2 L89.7,236.7 L90.2,236.2 L90.6,235.6 L91.1,235.1 L91.6,234.6 L92.1,234.1 L92.6,233.6 L93.0,233.0 L93.5,232.5 L94.0,232.0 L94.5,231.5 L95.0,231.0 L95.4,230.4 L95.9,229.9 L96.4,229.4 L96.9,228.9 L97.4,228.4 L97.8,227.8 L98.3,227.3 L98.8,226.8 L99.3,226.3 L99.8,225.8 L100.2,225.2 L100.7,224.7 L101.2,224.2 L101.7,223.7 L102.2,223.2 L102.6,222.6 L103.1,222.1 L103.6,221.6 L104.1,221.1 L104.6,220.6 L105.0,220.0 L105.5,219.5 L106.0,219.0 L106.5,218.5 L107.0,218.0 L107.4,217.4 L107.9,216.9 L108.4,216.4 L108.9,215.9 L109.4,215.4 L109.8,214.8 L110.3,214.3 L110.8,213.8 L111.3,213.3 L111.8,212.8 L112.2,212.2 L112.7,211.7 L113.2,211.2 L113.7,210.7 L114.2,210.2 L114.6,209.6 L115.1,209.1 L115.6,208.6 L116.1,208.1 L116.6,207.6 L117.0,207.0 L117.5,206.5 L118.0,206.0 L118.5,205.5 L119.0,205.0 L119.4,204.4 L119.9,203.9 L120.4,203.4 L120.9,202.9 L121.4,202.4 L121.8,201.8 L122.3,201.3 L122.8,200.8 L123.3,200.3 L123.8,199.8 L124.2,199.2 L124.7,198.7 L125.2,198.2 L125.7,197.7 L126.2,197.2 L126.6,196.6 L127.1,196.1 L127.6,195.6 L128.1,195.1 L128.6,194.6 L129.0,194.0 L129.5,193.5 L130.0,193.0 L130.5,192.5 L131.0,192.0 L131.4,191.4 L131.9,190.9 L132.4,190.4 L132.9,189.9 L133.4,189.4 L133.8,188.8 L134.3,188.3 L134.8,187.8 L135.3,187.3 L135.8,186.8 L136.2,186.2 L136.7,185.7 L137.2,185.2 L137.7,184.7 L138.2,184.2 L138.6,183.6 L139.1,183.1 L139.6,182.6 L140.1,182.1 L140.6,181.6 L141.0,181.0 L141.5,180.5 L142.0,180.0 L142.5,179.5 L143.0,179.0 L143.4,178.4 L143.9,177.9 L144.4,177.4 L144.9,176.9 L145.4,176.4 L145.8,175.8 L146.3,175.3 L146.8,174.8 L147.3,174.3 L147.8,173.8 L148.2,173.2 L148.7,172.7 L149.2,172.2 L149.7,171.7 L150.2,171.2 L150.6,170.6 L151.1,170.1 L151.6,169.6 L152.1,169.1 L152.6,168.6 L153.0,168.0 L153.5,167.5 L154.0,167.0 L154.5,166.5 L155.0,166.0 L155.4,165.4 L155.9,164.9 L156.4,164.4 L156.9,163.9 L157.4,163.4 L157.8,162.8 L158.3,162.3 L158.8,161.8 L159.3,161.3 L159.8,160.8 L160.2,160.2 L160.7,159.7 L161.2,159.2 L161.7,158.7 L162.2,158.2 L162.6,157.6 L163.1,157.1 L163.6,156.6 L164.1,156.1 L164.6,155.6 L165.0,155.0 L165.5,154.5 L166.0,154.0 L166.5,153.5 L167.0,153.0 L167.4,152.4 L167.9,151.9 L168.4,151.4 L168.9,150.9 L169.4,150.4 L169.8,149.8 L170.3,149.3 L170.8,148.8 L171.3,148.3 L171.8,147.8 L172.2,147.2 L172.7,146.7 L173.2,146.2 L173.7,145.7 L174.2,145.2 L174.6,144.6 L175.1,144.1 L175.6,143.6 L176.1,143.1 L176.6,142.6 L177.0,142.0 L177.5,141.5 L178.0,141.0 L178.5,140.5 L179.0,140.0 L179.4,139.4 L179.9,138.9 L180.4,138.4 L180.9,137.9 L181.4,137.4 L181.8,136.8 L182.3,136.3 L182.8,135.8 L183.3,135.3 L183.8,134.8 L184.2,134.2 L184.7,133.7 L185.2,133.2 L185.7,132.7 L186.2,132.2 L186.6,131.6 L187.1,131.1 L187.6,130.6 L188.1,130.1 L188.6,129.6 L189.0,129.0 L189.5,128.5 L190.0,128.0 L190.5,127.5 L191.0,127.0 L191.4,126.4 L191.9,125.9 L192.4,125.4 L192.9,124.9 L193.4,124.4 L193.8,123.8 L194.3,123.3 L194.8,122.8 L195.3,122.3 L195.8,121.8 L196.2,121.2 L196.7,120.7 L197.2,120.2 L197.7,119.7 L198.2,119.2 L198.6,118.6 L199.1,118.1 L199.6,117.6 L200.1,117.1 L200.6,116.6 L201.0,116.0 L201.5,115.5 L202.0,115.0 L202.5,114.5 L203.0,114.0 L203.4,113.4 L203.9,112.9 L204.4,112.4 L204.9,111.9 L205.4,111.4 L205.8,110.8 L206.3,110.3 L206.8,109.8 L207.3,109.3 L207.8,108.8 L208.2,108.2 L208.7,107.7 L209.2,107.2 L209.7,106.7 L210.2,106.2 L210.6,105.6 L211.1,105.1 L211.6,104.6 L212.1,104.1 L212.6,103.6 L213.0,103.0 L213.5,102.5 L214.0,102.0 L214.5,101.5 L215.0,101.0 L215.4,100.4 L215.9,99.9 L216.4,99.4 L216.9,98.9 L217.4,98.4 L217.8,97.8 L218.3,97.3 L218.8,96.8 L219.3,96.3 L219.8,95.8 L220.2,95.2 L220.7,94.7 L221.2,94.2 L221.7,93.7 L222.2,93.2 L222.6,92.6 L223.1,92.1 L223.6,91.6 L224.1,91.1 L224.6,90.6 L225.0,90.0 L225.5,89.5 L226.0,89.0 L226.5,88.5 L227.0,88.0 L227.4,87.4 L227.9,86.9 L228.4,86.4 L228.9,85.9 L229.4,85.4 L229.8,84.8 L230.3,84.3 L230.8,83.8 L231.3,83.3 L231.8,82.8 L232.2,82.2 L232.7,81.7 L233.2,81.2 L233.7,80.7 L234.2,80.2 L234.6,79.6 L235.1,79.1 L235.6,78.6 L236.1,78.1 L236.6,77.6 L237.0,77.0 L237.5,76.5 L238.0,76.0 L238.5,75.5 L239.0,75.0 L239.4,74.4 L239.9,73.9 L240.4,73.4 L240.9,72.9 L241.4,72.4 L241.8,71.8 L242.3,71.3 L242.8,70.8 L243.3,70.3 L243.8,69.8 L244.2,69.2 L244.7,68.7 L245.2,68.2 L245.7,67.7 L246.2,67.2 L246.6,66.6 L247.1,66.1 L247.6,65.6 L248.1,65.1 L248.6,64.6 L249.0,64.0 L249.5,63.5 L250.0,63.0 L250.5,62.5 L251.0,62.0 L251.4,61.4 L251.9,60.9 L252.4,60.4 L252.9,59.9 L253.4,59.4 L253.8,58.8 L254.3,58.3 L254.8,57.8 L255.3,57.3 L255.8,56.8 L256.2,56.2 L256.7,55.7 L257.2,55.2 L257.7,54.7 L258.2,54.2 L258.6,53.6 L259.1,53.1 L259.6,52.6 L260.1,52.1 L260.6,51.6 L261.0,51.0 L261.5,50.5 L262.0,50.0 L262.5,49.5 L263.0,49.0 L263.4,48.4 L263.9,47.9 L264.4,47.4 L264.9,46.9 L265.4,46.4 L265.8,45.8 L266.3,45.3 L266.8,44.8 L267.3,44.3 L267.8,43.8 L268.2,43.2 L268.7,42.7 L269.2,42.2 L269.7,41.7 L270.2,41.2 L270.6,40.6 L271.1,40.1 L271.6,39.6 L272.1,39.1 L272.6,38.6 L273.0,38.0 L273.5,37.5 L274.0,37.0 L274.5,36.5 L275.0,36.0 L275.4,35.4 L275.9,34.9 L276.4,34.4 L276.9,33.9 L277.4,33.4 L277.8,32.8 L278.3,32.3 L278.8,31.8 L279.3,31.3 L279.8,30.8 L280.2,30.2 L280.7,29.7 L281.2,29.2 L281.7,28.7 L282.2,28.2 L282.6,27.6 L283.1,27.1 L283.6,26.6 L284.1,26.1 L284.6,25.6 L285.0,25.0 L285.5,24.5 L286.0,24.0 L286.5,23.5 L287.0,23.0 L287.4,22.4 L287.9,21.9 L288.4,21.4 L288.9,20.9 L289.4,20.4 L289.8,19.8 L290.3,19.3 L290.8,18.8 L291.3,18.3 L291.8,17.8 L292.2,17.2 L292.7,16.7 L293.2,16.2 L293.7,15.7 L294.2,15.2 L294.6,14.6 L295.1,14.1 L295.6,13.6 L296.1,13.1 L296.6,12.6 L297.0,12.0 L297.5,11.5 L298.0,11.0 L298.5,10.5 L299.0,10.0 L299.4,9.4 L299.9,8.9 L300.4,8.4 L300.9,7.9 L301.4,7.4 L301.8,6.8 L302.3,6.3 L302.8,5.8 L303.3,5.3 L303.8,4.8 L304.2,4.2 L304.7,3.7 L305.2,3.2 L305.7,2.7 L306.2,2.2 L306.6,1.6 L307.1,1.1 L307.6,0.6 L308.1,0.1 L308.6,-0.4 L309.0,-1.0 L309.5,-1.5 L310.0,-2.0\" clip-path=\"url(#b10x5)\" style=\"fill:none;stroke:var(--success);stroke-width:2.2\"/><text x=\"279.0\" y=\"27.4\" text-anchor=\"middle\" style=\"fill:var(--success);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">y = x</text><circle cx=\"243.5\" cy=\"70.0\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"250.5\" y=\"61.0\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(3, 3)</text></svg><p>The graph shows why: y = √(x + 6) and y = x meet only once, at (3, 3).</p><div class=\"ex\"><div class=\"exh\">Worked example 4 · Radicals on both sides</div><div class=\"exl\">Solve √(4x − 1) = √(x + 8).<br>Square: 4x − 1 = x + 8, so 3x = 9 and <b>x = 3</b>.<br>Check: √11 = √11 ✓</div></div><p>An equation with a <b>rational exponent</b> such as x<sup>1/3</sup> = 4 is solved the same way, because x<sup>1/3</sup> = ∛x: cube both sides to get x = 64.</p><div class=\"keybox\"><b>Common mistake.</b> Isolate the radical <b>before</b> squaring. Squaring √x + 3 = 7 term by term to get x + 9 = 49 is wrong; first write √x = 4, then x = 16. Also, (x − 4)² is x² − 8x + 16, not x² + 16.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s3\">Practise 10.3 →</button></div></section><section class=\"note\" id=\"n104\"><h2>10.4 Inverse of a Function</h2><p class=\"lt\"><b>Learning target:</b> I can find inverses of relations and functions, restrict domains so that an inverse is a function, and check that two functions are inverses.</p><p>An <b>inverse relation</b> switches the input and output values of a relation. If (a, b) is on the original, then (b, a) is on the inverse. The inverse of a function f is written <b>f⁻¹</b> (read “f inverse”). Note: f⁻¹(x) does <b>not</b> mean <span class=\"fq\"><span>1</span><span>f(x)</span></span>.</p><div class=\"keybox\"><b>Finding the inverse of y = f(x)</b><br>1. Replace f(x) with y.<br>2. Switch x and y.<br>3. Solve for y. The result is f⁻¹(x).<br>The <b>domain</b> of f⁻¹ is the range of f, and the range of f⁻¹ is the domain of f.</div><div class=\"ex\"><div class=\"exh\">Worked example 1 · Linear function</div><div class=\"exl\">Find the inverse of f(x) = 2x + 1.<br>Switch: x = 2y + 1. Subtract 1: x − 1 = 2y.<br><b>f⁻¹(x) = <span class=\"fq\"><span>x − 1</span><span>2</span></span></b>. Check: f(3) = 7 and f⁻¹(7) = 3 ✓</div></div><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">A function and its inverse</text><line x1=\"22.0\" y1=\"214.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"48.2\" y1=\"214.0\" x2=\"48.2\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"74.4\" y1=\"214.0\" x2=\"74.4\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"100.5\" y1=\"214.0\" x2=\"100.5\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"126.7\" y1=\"214.0\" x2=\"126.7\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"152.9\" y1=\"214.0\" x2=\"152.9\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"179.1\" y1=\"214.0\" x2=\"179.1\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"205.3\" y1=\"214.0\" x2=\"205.3\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"231.5\" y1=\"214.0\" x2=\"231.5\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"257.6\" y1=\"214.0\" x2=\"257.6\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"283.8\" y1=\"214.0\" x2=\"283.8\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"310.0\" y1=\"214.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"214.0\" x2=\"310.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"196.5\" x2=\"310.0\" y2=\"196.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"179.1\" x2=\"310.0\" y2=\"179.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"161.6\" x2=\"310.0\" y2=\"161.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"144.2\" x2=\"310.0\" y2=\"144.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"126.7\" x2=\"310.0\" y2=\"126.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"109.3\" x2=\"310.0\" y2=\"109.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"91.8\" x2=\"310.0\" y2=\"91.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"74.4\" x2=\"310.0\" y2=\"74.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"56.9\" x2=\"310.0\" y2=\"56.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"39.5\" x2=\"310.0\" y2=\"39.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"126.7\" x2=\"310.0\" y2=\"126.7\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"152.9\" y1=\"214.0\" x2=\"152.9\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"48.2\" y=\"135.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"100.5\" y=\"135.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"205.3\" y=\"135.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"257.6\" y=\"135.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"310.0\" y=\"135.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"148.9\" y=\"196.5\" text-anchor=\"end\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"148.9\" y=\"161.6\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"148.9\" y=\"91.8\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"148.9\" y=\"56.9\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"148.9\" y=\"22.0\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"306.0\" y=\"118.7\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"160.9\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x6\"><rect x=\"22.0\" y=\"22.0\" width=\"288.0\" height=\"192.0\"/></clipPath><line x1=\"22.0\" y1=\"214.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3;stroke-dasharray:5 4\"/><path d=\"M22.0,283.8 L22.5,283.2 L23.0,282.5 L23.4,281.9 L23.9,281.3 L24.4,280.6 L24.9,280.0 L25.4,279.3 L25.8,278.7 L26.3,278.1 L26.8,277.4 L27.3,276.8 L27.8,276.1 L28.2,275.5 L28.7,274.9 L29.2,274.2 L29.7,273.6 L30.2,272.9 L30.6,272.3 L31.1,271.7 L31.6,271.0 L32.1,270.4 L32.6,269.7 L33.0,269.1 L33.5,268.5 L34.0,267.8 L34.5,267.2 L35.0,266.5 L35.4,265.9 L35.9,265.3 L36.4,264.6 L36.9,264.0 L37.4,263.3 L37.8,262.7 L38.3,262.1 L38.8,261.4 L39.3,260.8 L39.8,260.1 L40.2,259.5 L40.7,258.9 L41.2,258.2 L41.7,257.6 L42.2,256.9 L42.6,256.3 L43.1,255.7 L43.6,255.0 L44.1,254.4 L44.6,253.7 L45.0,253.1 L45.5,252.5 L46.0,251.8 L46.5,251.2 L47.0,250.5 L47.4,249.9 L47.9,249.3 L48.4,248.6 L48.9,248.0 L49.4,247.3 L49.8,246.7 L50.3,246.1 L50.8,245.4 L51.3,244.8 L51.8,244.1 L52.2,243.5 L52.7,242.9 L53.2,242.2 L53.7,241.6 L54.2,240.9 L54.6,240.3 L55.1,239.7 L55.6,239.0 L56.1,238.4 L56.6,237.7 L57.0,237.1 L57.5,236.5 L58.0,235.8 L58.5,235.2 L59.0,234.5 L59.4,233.9 L59.9,233.3 L60.4,232.6 L60.9,232.0 L61.4,231.3 L61.8,230.7 L62.3,230.1 L62.8,229.4 L63.3,228.8 L63.8,228.1 L64.2,227.5 L64.7,226.9 L65.2,226.2 L65.7,225.6 L66.2,224.9 L66.6,224.3 L67.1,223.7 L67.6,223.0 L68.1,222.4 L68.6,221.7 L69.0,221.1 L69.5,220.5 L70.0,219.8 L70.5,219.2 L71.0,218.5 L71.4,217.9 L71.9,217.3 L72.4,216.6 L72.9,216.0 L73.4,215.3 L73.8,214.7 L74.3,214.1 L74.8,213.4 L75.3,212.8 L75.8,212.1 L76.2,211.5 L76.7,210.9 L77.2,210.2 L77.7,209.6 L78.2,208.9 L78.6,208.3 L79.1,207.7 L79.6,207.0 L80.1,206.4 L80.6,205.7 L81.0,205.1 L81.5,204.5 L82.0,203.8 L82.5,203.2 L83.0,202.5 L83.4,201.9 L83.9,201.3 L84.4,200.6 L84.9,200.0 L85.4,199.3 L85.8,198.7 L86.3,198.1 L86.8,197.4 L87.3,196.8 L87.8,196.1 L88.2,195.5 L88.7,194.9 L89.2,194.2 L89.7,193.6 L90.2,192.9 L90.6,192.3 L91.1,191.7 L91.6,191.0 L92.1,190.4 L92.6,189.7 L93.0,189.1 L93.5,188.5 L94.0,187.8 L94.5,187.2 L95.0,186.5 L95.4,185.9 L95.9,185.3 L96.4,184.6 L96.9,184.0 L97.4,183.3 L97.8,182.7 L98.3,182.1 L98.8,181.4 L99.3,180.8 L99.8,180.1 L100.2,179.5 L100.7,178.9 L101.2,178.2 L101.7,177.6 L102.2,176.9 L102.6,176.3 L103.1,175.7 L103.6,175.0 L104.1,174.4 L104.6,173.7 L105.0,173.1 L105.5,172.5 L106.0,171.8 L106.5,171.2 L107.0,170.5 L107.4,169.9 L107.9,169.3 L108.4,168.6 L108.9,168.0 L109.4,167.3 L109.8,166.7 L110.3,166.1 L110.8,165.4 L111.3,164.8 L111.8,164.1 L112.2,163.5 L112.7,162.9 L113.2,162.2 L113.7,161.6 L114.2,160.9 L114.6,160.3 L115.1,159.7 L115.6,159.0 L116.1,158.4 L116.6,157.7 L117.0,157.1 L117.5,156.5 L118.0,155.8 L118.5,155.2 L119.0,154.5 L119.4,153.9 L119.9,153.3 L120.4,152.6 L120.9,152.0 L121.4,151.3 L121.8,150.7 L122.3,150.1 L122.8,149.4 L123.3,148.8 L123.8,148.1 L124.2,147.5 L124.7,146.9 L125.2,146.2 L125.7,145.6 L126.2,144.9 L126.6,144.3 L127.1,143.7 L127.6,143.0 L128.1,142.4 L128.6,141.7 L129.0,141.1 L129.5,140.5 L130.0,139.8 L130.5,139.2 L131.0,138.5 L131.4,137.9 L131.9,137.3 L132.4,136.6 L132.9,136.0 L133.4,135.3 L133.8,134.7 L134.3,134.1 L134.8,133.4 L135.3,132.8 L135.8,132.1 L136.2,131.5 L136.7,130.9 L137.2,130.2 L137.7,129.6 L138.2,128.9 L138.6,128.3 L139.1,127.7 L139.6,127.0 L140.1,126.4 L140.6,125.7 L141.0,125.1 L141.5,124.5 L142.0,123.8 L142.5,123.2 L143.0,122.5 L143.4,121.9 L143.9,121.3 L144.4,120.6 L144.9,120.0 L145.4,119.3 L145.8,118.7 L146.3,118.1 L146.8,117.4 L147.3,116.8 L147.8,116.1 L148.2,115.5 L148.7,114.9 L149.2,114.2 L149.7,113.6 L150.2,112.9 L150.6,112.3 L151.1,111.7 L151.6,111.0 L152.1,110.4 L152.6,109.7 L153.0,109.1 L153.5,108.5 L154.0,107.8 L154.5,107.2 L155.0,106.5 L155.4,105.9 L155.9,105.3 L156.4,104.6 L156.9,104.0 L157.4,103.3 L157.8,102.7 L158.3,102.1 L158.8,101.4 L159.3,100.8 L159.8,100.1 L160.2,99.5 L160.7,98.9 L161.2,98.2 L161.7,97.6 L162.2,96.9 L162.6,96.3 L163.1,95.7 L163.6,95.0 L164.1,94.4 L164.6,93.7 L165.0,93.1 L165.5,92.5 L166.0,91.8 L166.5,91.2 L167.0,90.5 L167.4,89.9 L167.9,89.3 L168.4,88.6 L168.9,88.0 L169.4,87.3 L169.8,86.7 L170.3,86.1 L170.8,85.4 L171.3,84.8 L171.8,84.1 L172.2,83.5 L172.7,82.9 L173.2,82.2 L173.7,81.6 L174.2,80.9 L174.6,80.3 L175.1,79.7 L175.6,79.0 L176.1,78.4 L176.6,77.7 L177.0,77.1 L177.5,76.5 L178.0,75.8 L178.5,75.2 L179.0,74.5 L179.4,73.9 L179.9,73.3 L180.4,72.6 L180.9,72.0 L181.4,71.3 L181.8,70.7 L182.3,70.1 L182.8,69.4 L183.3,68.8 L183.8,68.1 L184.2,67.5 L184.7,66.9 L185.2,66.2 L185.7,65.6 L186.2,64.9 L186.6,64.3 L187.1,63.7 L187.6,63.0 L188.1,62.4 L188.6,61.7 L189.0,61.1 L189.5,60.5 L190.0,59.8 L190.5,59.2 L191.0,58.5 L191.4,57.9 L191.9,57.3 L192.4,56.6 L192.9,56.0 L193.4,55.3 L193.8,54.7 L194.3,54.1 L194.8,53.4 L195.3,52.8 L195.8,52.1 L196.2,51.5 L196.7,50.9 L197.2,50.2 L197.7,49.6 L198.2,48.9 L198.6,48.3 L199.1,47.7 L199.6,47.0 L200.1,46.4 L200.6,45.7 L201.0,45.1 L201.5,44.5 L202.0,43.8 L202.5,43.2 L203.0,42.5 L203.4,41.9 L203.9,41.3 L204.4,40.6 L204.9,40.0 L205.4,39.3 L205.8,38.7 L206.3,38.1 L206.8,37.4 L207.3,36.8 L207.8,36.1 L208.2,35.5 L208.7,34.9 L209.2,34.2 L209.7,33.6 L210.2,32.9 L210.6,32.3 L211.1,31.7 L211.6,31.0 L212.1,30.4 L212.6,29.7 L213.0,29.1 L213.5,28.5 L214.0,27.8 L214.5,27.2 L215.0,26.5 L215.4,25.9 L215.9,25.3 L216.4,24.6 L216.9,24.0 L217.4,23.3 L217.8,22.7 L218.3,22.1 L218.8,21.4 L219.3,20.8 L219.8,20.1 L220.2,19.5 L220.7,18.9 L221.2,18.2 L221.7,17.6 L222.2,16.9 L222.6,16.3 L223.1,15.7 L223.6,15.0 L224.1,14.4 L224.6,13.7 L225.0,13.1 L225.5,12.5 L226.0,11.8 L226.5,11.2 L227.0,10.5 L227.4,9.9 L227.9,9.3 L228.4,8.6 L228.9,8.0 L229.4,7.3 L229.8,6.7 L230.3,6.1 L230.8,5.4 L231.3,4.8 L231.8,4.1 L232.2,3.5 L232.7,2.9 L233.2,2.2 L233.7,1.6 L234.2,0.9 L234.6,0.3 L235.1,-0.3 L235.6,-1.0 L236.1,-1.6 L236.6,-2.3 L237.0,-2.9 L237.5,-3.5 L238.0,-4.2 L238.5,-4.8 L239.0,-5.5 L239.4,-6.1 L239.9,-6.7 L240.4,-7.4 L240.9,-8.0 L241.4,-8.7 L241.8,-9.3 L242.3,-9.9 L242.8,-10.6 L243.3,-11.2 L243.8,-11.9 L244.2,-12.5 L244.7,-13.1 L245.2,-13.8 L245.7,-14.4 L246.2,-15.1 L246.6,-15.7 L247.1,-16.3 L247.6,-17.0 L248.1,-17.6 L248.6,-18.3 L249.0,-18.9 L249.5,-19.5 L250.0,-20.2 L250.5,-20.8 L251.0,-21.5 L251.4,-22.1 L251.9,-22.7 L252.4,-23.4 L252.9,-24.0 L253.4,-24.7 L253.8,-25.3 L254.3,-25.9 L254.8,-26.6 L255.3,-27.2 L255.8,-27.9 L256.2,-28.5 L256.7,-29.1 L257.2,-29.8 L257.7,-30.4 L258.2,-31.1 L258.6,-31.7 L259.1,-32.3 L259.6,-33.0 L260.1,-33.6 L260.6,-34.3 L261.0,-34.9 L261.5,-35.5 L262.0,-36.2 L262.5,-36.8 L263.0,-37.5 L263.4,-38.1 L263.9,-38.7 L264.4,-39.4 L264.9,-40.0 L265.4,-40.7 L265.8,-41.3 L266.3,-41.9 L266.8,-42.6 L267.3,-43.2 L267.8,-43.9 L268.2,-44.5 L268.7,-45.1 L269.2,-45.8 L269.7,-46.4 L270.2,-47.1 L270.6,-47.7 L271.1,-48.3 L271.6,-49.0 L272.1,-49.6 L272.6,-50.3 L273.0,-50.9 L273.5,-51.5 L274.0,-52.2 L274.5,-52.8 L275.0,-53.5 L275.4,-54.1 L275.9,-54.7 L276.4,-55.4 L276.9,-56.0 L277.4,-56.7 L277.8,-57.3 L278.3,-57.9 L278.8,-58.6 L279.3,-59.2 L279.8,-59.9 L280.2,-60.5 L280.7,-61.1 L281.2,-61.8 L281.7,-62.4 L282.2,-63.1 L282.6,-63.7 L283.1,-64.3 L283.6,-65.0 L284.1,-65.6 L284.6,-66.3 L285.0,-66.9 L285.5,-67.5 L286.0,-68.2 L286.5,-68.8 L287.0,-69.5 L287.4,-70.1 L287.9,-70.7 L288.4,-71.4 L288.9,-72.0 L289.4,-72.7 L289.8,-73.3 L290.3,-73.9 L290.8,-74.6 L291.3,-75.2 L291.8,-75.9 L292.2,-76.5 L292.7,-77.1 L293.2,-77.8 L293.7,-78.4 L294.2,-79.1 L294.6,-79.7 L295.1,-80.3 L295.6,-81.0 L296.1,-81.6 L296.6,-82.3 L297.0,-82.9 L297.5,-83.5 L298.0,-84.2 L298.5,-84.8 L299.0,-85.5 L299.4,-86.1 L299.9,-86.7 L300.4,-87.4 L300.9,-88.0 L301.4,-88.7 L301.8,-89.3 L302.3,-89.9 L302.8,-90.6 L303.3,-91.2 L303.8,-91.9 L304.2,-92.5 L304.7,-93.1 L305.2,-93.8 L305.7,-94.4 L306.2,-95.1 L306.6,-95.7 L307.1,-96.3 L307.6,-97.0 L308.1,-97.6 L308.6,-98.3 L309.0,-98.9 L309.5,-99.5 L310.0,-100.2\" clip-path=\"url(#b10x6)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><text x=\"189.6\" y=\"52.4\" text-anchor=\"middle\" style=\"fill:var(--danger);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">f(x) = 2x + 1</text><path d=\"M22.0,179.1 L22.5,178.9 L23.0,178.8 L23.4,178.6 L23.9,178.5 L24.4,178.3 L24.9,178.1 L25.4,178.0 L25.8,177.8 L26.3,177.7 L26.8,177.5 L27.3,177.3 L27.8,177.2 L28.2,177.0 L28.7,176.9 L29.2,176.7 L29.7,176.5 L30.2,176.4 L30.6,176.2 L31.1,176.1 L31.6,175.9 L32.1,175.7 L32.6,175.6 L33.0,175.4 L33.5,175.3 L34.0,175.1 L34.5,174.9 L35.0,174.8 L35.4,174.6 L35.9,174.5 L36.4,174.3 L36.9,174.1 L37.4,174.0 L37.8,173.8 L38.3,173.7 L38.8,173.5 L39.3,173.3 L39.8,173.2 L40.2,173.0 L40.7,172.9 L41.2,172.7 L41.7,172.5 L42.2,172.4 L42.6,172.2 L43.1,172.1 L43.6,171.9 L44.1,171.7 L44.6,171.6 L45.0,171.4 L45.5,171.3 L46.0,171.1 L46.5,170.9 L47.0,170.8 L47.4,170.6 L47.9,170.5 L48.4,170.3 L48.9,170.1 L49.4,170.0 L49.8,169.8 L50.3,169.7 L50.8,169.5 L51.3,169.3 L51.8,169.2 L52.2,169.0 L52.7,168.9 L53.2,168.7 L53.7,168.5 L54.2,168.4 L54.6,168.2 L55.1,168.1 L55.6,167.9 L56.1,167.7 L56.6,167.6 L57.0,167.4 L57.5,167.3 L58.0,167.1 L58.5,166.9 L59.0,166.8 L59.4,166.6 L59.9,166.5 L60.4,166.3 L60.9,166.1 L61.4,166.0 L61.8,165.8 L62.3,165.7 L62.8,165.5 L63.3,165.3 L63.8,165.2 L64.2,165.0 L64.7,164.9 L65.2,164.7 L65.7,164.5 L66.2,164.4 L66.6,164.2 L67.1,164.1 L67.6,163.9 L68.1,163.7 L68.6,163.6 L69.0,163.4 L69.5,163.3 L70.0,163.1 L70.5,162.9 L71.0,162.8 L71.4,162.6 L71.9,162.5 L72.4,162.3 L72.9,162.1 L73.4,162.0 L73.8,161.8 L74.3,161.7 L74.8,161.5 L75.3,161.3 L75.8,161.2 L76.2,161.0 L76.7,160.9 L77.2,160.7 L77.7,160.5 L78.2,160.4 L78.6,160.2 L79.1,160.1 L79.6,159.9 L80.1,159.7 L80.6,159.6 L81.0,159.4 L81.5,159.3 L82.0,159.1 L82.5,158.9 L83.0,158.8 L83.4,158.6 L83.9,158.5 L84.4,158.3 L84.9,158.1 L85.4,158.0 L85.8,157.8 L86.3,157.7 L86.8,157.5 L87.3,157.3 L87.8,157.2 L88.2,157.0 L88.7,156.9 L89.2,156.7 L89.7,156.5 L90.2,156.4 L90.6,156.2 L91.1,156.1 L91.6,155.9 L92.1,155.7 L92.6,155.6 L93.0,155.4 L93.5,155.3 L94.0,155.1 L94.5,154.9 L95.0,154.8 L95.4,154.6 L95.9,154.5 L96.4,154.3 L96.9,154.1 L97.4,154.0 L97.8,153.8 L98.3,153.7 L98.8,153.5 L99.3,153.3 L99.8,153.2 L100.2,153.0 L100.7,152.9 L101.2,152.7 L101.7,152.5 L102.2,152.4 L102.6,152.2 L103.1,152.1 L103.6,151.9 L104.1,151.7 L104.6,151.6 L105.0,151.4 L105.5,151.3 L106.0,151.1 L106.5,150.9 L107.0,150.8 L107.4,150.6 L107.9,150.5 L108.4,150.3 L108.9,150.1 L109.4,150.0 L109.8,149.8 L110.3,149.7 L110.8,149.5 L111.3,149.3 L111.8,149.2 L112.2,149.0 L112.7,148.9 L113.2,148.7 L113.7,148.5 L114.2,148.4 L114.6,148.2 L115.1,148.1 L115.6,147.9 L116.1,147.7 L116.6,147.6 L117.0,147.4 L117.5,147.3 L118.0,147.1 L118.5,146.9 L119.0,146.8 L119.4,146.6 L119.9,146.5 L120.4,146.3 L120.9,146.1 L121.4,146.0 L121.8,145.8 L122.3,145.7 L122.8,145.5 L123.3,145.3 L123.8,145.2 L124.2,145.0 L124.7,144.9 L125.2,144.7 L125.7,144.5 L126.2,144.4 L126.6,144.2 L127.1,144.1 L127.6,143.9 L128.1,143.7 L128.6,143.6 L129.0,143.4 L129.5,143.3 L130.0,143.1 L130.5,142.9 L131.0,142.8 L131.4,142.6 L131.9,142.5 L132.4,142.3 L132.9,142.1 L133.4,142.0 L133.8,141.8 L134.3,141.7 L134.8,141.5 L135.3,141.3 L135.8,141.2 L136.2,141.0 L136.7,140.9 L137.2,140.7 L137.7,140.5 L138.2,140.4 L138.6,140.2 L139.1,140.1 L139.6,139.9 L140.1,139.7 L140.6,139.6 L141.0,139.4 L141.5,139.3 L142.0,139.1 L142.5,138.9 L143.0,138.8 L143.4,138.6 L143.9,138.5 L144.4,138.3 L144.9,138.1 L145.4,138.0 L145.8,137.8 L146.3,137.7 L146.8,137.5 L147.3,137.3 L147.8,137.2 L148.2,137.0 L148.7,136.9 L149.2,136.7 L149.7,136.5 L150.2,136.4 L150.6,136.2 L151.1,136.1 L151.6,135.9 L152.1,135.7 L152.6,135.6 L153.0,135.4 L153.5,135.3 L154.0,135.1 L154.5,134.9 L155.0,134.8 L155.4,134.6 L155.9,134.5 L156.4,134.3 L156.9,134.1 L157.4,134.0 L157.8,133.8 L158.3,133.7 L158.8,133.5 L159.3,133.3 L159.8,133.2 L160.2,133.0 L160.7,132.9 L161.2,132.7 L161.7,132.5 L162.2,132.4 L162.6,132.2 L163.1,132.1 L163.6,131.9 L164.1,131.7 L164.6,131.6 L165.0,131.4 L165.5,131.3 L166.0,131.1 L166.5,130.9 L167.0,130.8 L167.4,130.6 L167.9,130.5 L168.4,130.3 L168.9,130.1 L169.4,130.0 L169.8,129.8 L170.3,129.7 L170.8,129.5 L171.3,129.3 L171.8,129.2 L172.2,129.0 L172.7,128.9 L173.2,128.7 L173.7,128.5 L174.2,128.4 L174.6,128.2 L175.1,128.1 L175.6,127.9 L176.1,127.7 L176.6,127.6 L177.0,127.4 L177.5,127.3 L178.0,127.1 L178.5,126.9 L179.0,126.8 L179.4,126.6 L179.9,126.5 L180.4,126.3 L180.9,126.1 L181.4,126.0 L181.8,125.8 L182.3,125.7 L182.8,125.5 L183.3,125.3 L183.8,125.2 L184.2,125.0 L184.7,124.9 L185.2,124.7 L185.7,124.5 L186.2,124.4 L186.6,124.2 L187.1,124.1 L187.6,123.9 L188.1,123.7 L188.6,123.6 L189.0,123.4 L189.5,123.3 L190.0,123.1 L190.5,122.9 L191.0,122.8 L191.4,122.6 L191.9,122.5 L192.4,122.3 L192.9,122.1 L193.4,122.0 L193.8,121.8 L194.3,121.7 L194.8,121.5 L195.3,121.3 L195.8,121.2 L196.2,121.0 L196.7,120.9 L197.2,120.7 L197.7,120.5 L198.2,120.4 L198.6,120.2 L199.1,120.1 L199.6,119.9 L200.1,119.7 L200.6,119.6 L201.0,119.4 L201.5,119.3 L202.0,119.1 L202.5,118.9 L203.0,118.8 L203.4,118.6 L203.9,118.5 L204.4,118.3 L204.9,118.1 L205.4,118.0 L205.8,117.8 L206.3,117.7 L206.8,117.5 L207.3,117.3 L207.8,117.2 L208.2,117.0 L208.7,116.9 L209.2,116.7 L209.7,116.5 L210.2,116.4 L210.6,116.2 L211.1,116.1 L211.6,115.9 L212.1,115.7 L212.6,115.6 L213.0,115.4 L213.5,115.3 L214.0,115.1 L214.5,114.9 L215.0,114.8 L215.4,114.6 L215.9,114.5 L216.4,114.3 L216.9,114.1 L217.4,114.0 L217.8,113.8 L218.3,113.7 L218.8,113.5 L219.3,113.3 L219.8,113.2 L220.2,113.0 L220.7,112.9 L221.2,112.7 L221.7,112.5 L222.2,112.4 L222.6,112.2 L223.1,112.1 L223.6,111.9 L224.1,111.7 L224.6,111.6 L225.0,111.4 L225.5,111.3 L226.0,111.1 L226.5,110.9 L227.0,110.8 L227.4,110.6 L227.9,110.5 L228.4,110.3 L228.9,110.1 L229.4,110.0 L229.8,109.8 L230.3,109.7 L230.8,109.5 L231.3,109.3 L231.8,109.2 L232.2,109.0 L232.7,108.9 L233.2,108.7 L233.7,108.5 L234.2,108.4 L234.6,108.2 L235.1,108.1 L235.6,107.9 L236.1,107.7 L236.6,107.6 L237.0,107.4 L237.5,107.3 L238.0,107.1 L238.5,106.9 L239.0,106.8 L239.4,106.6 L239.9,106.5 L240.4,106.3 L240.9,106.1 L241.4,106.0 L241.8,105.8 L242.3,105.7 L242.8,105.5 L243.3,105.3 L243.8,105.2 L244.2,105.0 L244.7,104.9 L245.2,104.7 L245.7,104.5 L246.2,104.4 L246.6,104.2 L247.1,104.1 L247.6,103.9 L248.1,103.7 L248.6,103.6 L249.0,103.4 L249.5,103.3 L250.0,103.1 L250.5,102.9 L251.0,102.8 L251.4,102.6 L251.9,102.5 L252.4,102.3 L252.9,102.1 L253.4,102.0 L253.8,101.8 L254.3,101.7 L254.8,101.5 L255.3,101.3 L255.8,101.2 L256.2,101.0 L256.7,100.9 L257.2,100.7 L257.7,100.5 L258.2,100.4 L258.6,100.2 L259.1,100.1 L259.6,99.9 L260.1,99.7 L260.6,99.6 L261.0,99.4 L261.5,99.3 L262.0,99.1 L262.5,98.9 L263.0,98.8 L263.4,98.6 L263.9,98.5 L264.4,98.3 L264.9,98.1 L265.4,98.0 L265.8,97.8 L266.3,97.7 L266.8,97.5 L267.3,97.3 L267.8,97.2 L268.2,97.0 L268.7,96.9 L269.2,96.7 L269.7,96.5 L270.2,96.4 L270.6,96.2 L271.1,96.1 L271.6,95.9 L272.1,95.7 L272.6,95.6 L273.0,95.4 L273.5,95.3 L274.0,95.1 L274.5,94.9 L275.0,94.8 L275.4,94.6 L275.9,94.5 L276.4,94.3 L276.9,94.1 L277.4,94.0 L277.8,93.8 L278.3,93.7 L278.8,93.5 L279.3,93.3 L279.8,93.2 L280.2,93.0 L280.7,92.9 L281.2,92.7 L281.7,92.5 L282.2,92.4 L282.6,92.2 L283.1,92.1 L283.6,91.9 L284.1,91.7 L284.6,91.6 L285.0,91.4 L285.5,91.3 L286.0,91.1 L286.5,90.9 L287.0,90.8 L287.4,90.6 L287.9,90.5 L288.4,90.3 L288.9,90.1 L289.4,90.0 L289.8,89.8 L290.3,89.7 L290.8,89.5 L291.3,89.3 L291.8,89.2 L292.2,89.0 L292.7,88.9 L293.2,88.7 L293.7,88.5 L294.2,88.4 L294.6,88.2 L295.1,88.1 L295.6,87.9 L296.1,87.7 L296.6,87.6 L297.0,87.4 L297.5,87.3 L298.0,87.1 L298.5,86.9 L299.0,86.8 L299.4,86.6 L299.9,86.5 L300.4,86.3 L300.9,86.1 L301.4,86.0 L301.8,85.8 L302.3,85.7 L302.8,85.5 L303.3,85.3 L303.8,85.2 L304.2,85.0 L304.7,84.9 L305.2,84.7 L305.7,84.5 L306.2,84.4 L306.6,84.2 L307.1,84.1 L307.6,83.9 L308.1,83.7 L308.6,83.6 L309.0,83.4 L309.5,83.3 L310.0,83.1\" clip-path=\"url(#b10x6)\" style=\"fill:none;stroke:var(--success);stroke-width:2.2\"/><text x=\"268.1\" y=\"89.1\" text-anchor=\"middle\" style=\"fill:var(--success);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">f⁻¹(x)</text><circle cx=\"179.1\" cy=\"74.4\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"186.1\" y=\"65.4\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(1, 3)</text><circle cx=\"231.5\" cy=\"109.3\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"238.5\" y=\"100.3\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(3, 1)</text></svg><p>The graph of f⁻¹ is the <b>reflection of the graph of f in the line y = x</b>: the point (1, 3) on f becomes (3, 1) on f⁻¹.</p><h4>When is the inverse a function?</h4><p>Use the <b>horizontal line test</b>: if no horizontal line crosses the graph of f more than once, the inverse of f is a function. For f(x) = x² the line y = 4 crosses at x = −2 and x = 2, so we <b>restrict the domain</b> to x ≥ 0 before finding the inverse.</p><svg class=\"figsvg\" viewBox=\"0 0 320 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"160.0\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Restricting the domain of x²</text><line x1=\"22.0\" y1=\"214.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"63.1\" y1=\"214.0\" x2=\"63.1\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"104.3\" y1=\"214.0\" x2=\"104.3\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"145.4\" y1=\"214.0\" x2=\"145.4\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"186.6\" y1=\"214.0\" x2=\"186.6\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"227.7\" y1=\"214.0\" x2=\"227.7\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"268.9\" y1=\"214.0\" x2=\"268.9\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"310.0\" y1=\"214.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"214.0\" x2=\"310.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"186.6\" x2=\"310.0\" y2=\"186.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"159.1\" x2=\"310.0\" y2=\"159.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"131.7\" x2=\"310.0\" y2=\"131.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"104.3\" x2=\"310.0\" y2=\"104.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"76.9\" x2=\"310.0\" y2=\"76.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"49.4\" x2=\"310.0\" y2=\"49.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"186.6\" x2=\"310.0\" y2=\"186.6\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"63.1\" y1=\"214.0\" x2=\"63.1\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"145.4\" y=\"195.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"227.7\" y=\"195.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"310.0\" y=\"195.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"59.1\" y=\"131.7\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"59.1\" y=\"76.9\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"59.1\" y=\"22.0\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"306.0\" y=\"178.6\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"71.1\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x7\"><rect x=\"22.0\" y=\"22.0\" width=\"288.0\" height=\"192.0\"/></clipPath><line x1=\"22.0\" y1=\"214.0\" x2=\"310.0\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3;stroke-dasharray:5 4\"/><path d=\"M63.3,186.6 L63.8,186.6 L64.2,186.6 L64.7,186.5 L65.2,186.5 L65.7,186.5 L66.2,186.4 L66.6,186.4 L67.1,186.3 L67.6,186.2 L68.1,186.2 L68.6,186.1 L69.0,186.0 L69.5,185.9 L70.0,185.8 L70.5,185.7 L71.0,185.6 L71.4,185.5 L71.9,185.3 L72.4,185.2 L72.9,185.0 L73.4,184.9 L73.8,184.7 L74.3,184.5 L74.8,184.4 L75.3,184.2 L75.8,184.0 L76.2,183.8 L76.7,183.6 L77.2,183.4 L77.7,183.1 L78.2,182.9 L78.6,182.7 L79.1,182.4 L79.6,182.2 L80.1,181.9 L80.6,181.7 L81.0,181.4 L81.5,181.1 L82.0,180.8 L82.5,180.5 L83.0,180.2 L83.4,179.9 L83.9,179.6 L84.4,179.2 L84.9,178.9 L85.4,178.6 L85.8,178.2 L86.3,177.9 L86.8,177.5 L87.3,177.1 L87.8,176.8 L88.2,176.4 L88.7,176.0 L89.2,175.6 L89.7,175.2 L90.2,174.7 L90.6,174.3 L91.1,173.9 L91.6,173.4 L92.1,173.0 L92.6,172.5 L93.0,172.1 L93.5,171.6 L94.0,171.1 L94.5,170.7 L95.0,170.2 L95.4,169.7 L95.9,169.2 L96.4,168.6 L96.9,168.1 L97.4,167.6 L97.8,167.1 L98.3,166.5 L98.8,166.0 L99.3,165.4 L99.8,164.8 L100.2,164.3 L100.7,163.7 L101.2,163.1 L101.7,162.5 L102.2,161.9 L102.6,161.3 L103.1,160.7 L103.6,160.0 L104.1,159.4 L104.6,158.8 L105.0,158.1 L105.5,157.5 L106.0,156.8 L106.5,156.1 L107.0,155.5 L107.4,154.8 L107.9,154.1 L108.4,153.4 L108.9,152.7 L109.4,152.0 L109.8,151.2 L110.3,150.5 L110.8,149.8 L111.3,149.0 L111.8,148.3 L112.2,147.5 L112.7,146.7 L113.2,146.0 L113.7,145.2 L114.2,144.4 L114.6,143.6 L115.1,142.8 L115.6,142.0 L116.1,141.2 L116.6,140.3 L117.0,139.5 L117.5,138.7 L118.0,137.8 L118.5,137.0 L119.0,136.1 L119.4,135.2 L119.9,134.3 L120.4,133.4 L120.9,132.6 L121.4,131.7 L121.8,130.7 L122.3,129.8 L122.8,128.9 L123.3,128.0 L123.8,127.0 L124.2,126.1 L124.7,125.1 L125.2,124.2 L125.7,123.2 L126.2,122.2 L126.6,121.2 L127.1,120.2 L127.6,119.2 L128.1,118.2 L128.6,117.2 L129.0,116.2 L129.5,115.2 L130.0,114.1 L130.5,113.1 L131.0,112.0 L131.4,111.0 L131.9,109.9 L132.4,108.8 L132.9,107.8 L133.4,106.7 L133.8,105.6 L134.3,104.5 L134.8,103.4 L135.3,102.3 L135.8,101.1 L136.2,100.0 L136.7,98.9 L137.2,97.7 L137.7,96.5 L138.2,95.4 L138.6,94.2 L139.1,93.0 L139.6,91.8 L140.1,90.7 L140.6,89.5 L141.0,88.2 L141.5,87.0 L142.0,85.8 L142.5,84.6 L143.0,83.3 L143.4,82.1 L143.9,80.8 L144.4,79.6 L144.9,78.3 L145.4,77.0 L145.8,75.8 L146.3,74.5 L146.8,73.2 L147.3,71.9 L147.8,70.6 L148.2,69.2 L148.7,67.9 L149.2,66.6 L149.7,65.2 L150.2,63.9 L150.6,62.5 L151.1,61.2 L151.6,59.8 L152.1,58.4 L152.6,57.0 L153.0,55.6 L153.5,54.2 L154.0,52.8 L154.5,51.4 L155.0,50.0 L155.4,48.5 L155.9,47.1 L156.4,45.6 L156.9,44.2 L157.4,42.7 L157.8,41.3 L158.3,39.8 L158.8,38.3 L159.3,36.8 L159.8,35.3 L160.2,33.8 L160.7,32.3 L161.2,30.8 L161.7,29.2 L162.2,27.7 L162.6,26.2 L163.1,24.6 L163.6,23.0 L164.1,21.5 L164.6,19.9 L165.0,18.3 L165.5,16.7 L166.0,15.1 L166.5,13.5 L167.0,11.9 L167.4,10.3 L167.9,8.7 L168.4,7.0 L168.9,5.4 L169.4,3.8 L169.8,2.1 L170.3,0.4 L170.8,-1.2 L171.3,-2.9 L171.8,-4.6 L172.2,-6.3 L172.7,-8.0 L173.2,-9.7 L173.7,-11.4 L174.2,-13.1 L174.6,-14.9 L175.1,-16.6 L175.6,-18.4 L176.1,-20.1 L176.6,-21.9 L177.0,-23.6 L177.5,-25.4 L178.0,-27.2 L178.5,-29.0 L179.0,-30.8 L179.4,-32.6 L179.9,-34.4 L180.4,-36.2 L180.9,-38.0 L181.4,-39.9 L181.8,-41.7 L182.3,-43.6 L182.8,-45.4 L183.3,-47.3 L183.8,-49.2 L184.2,-51.0 L184.7,-52.9 L185.2,-54.8 L185.7,-56.7 L186.2,-58.6 L186.6,-60.6 L187.1,-62.5 L187.6,-64.4 L188.1,-66.4 L188.6,-68.3 L189.0,-70.3 L189.5,-72.2 L190.0,-74.2 L190.5,-76.2 L191.0,-78.2 L191.4,-80.1 L191.9,-82.1 L192.4,-84.2 L192.9,-86.2 L193.4,-88.2 L193.8,-90.2 L194.3,-92.3 L194.8,-94.3 L195.3,-96.3 L195.8,-98.4 L196.2,-100.5 L196.7,-102.5 L197.2,-104.6 L197.7,-106.7 L198.2,-108.8 L198.6,-110.9 L199.1,-113.0 L199.6,-115.2 L200.1,-117.3 L200.6,-119.4 L201.0,-121.6 L201.5,-123.7 L202.0,-125.9 L202.5,-128.0 L203.0,-130.2 L203.4,-132.4 L203.9,-134.6 L204.4,-136.8 L204.9,-139.0 L205.4,-141.2 L205.8,-143.4 L206.3,-145.6 L206.8,-147.8 L207.3,-150.1 L207.8,-152.3 L208.2,-154.6 L208.7,-156.8 L209.2,-159.1 L209.7,-161.4 L210.2,-163.7 L210.6,-165.9 L211.1,-168.2 L211.6,-170.6 L212.1,-172.9 L212.6,-175.2 L213.0,-177.5 L213.5,-179.8 L214.0,-182.2 L214.5,-184.5 L215.0,-186.9 L215.4,-189.3 L215.9,-191.6 L216.4,-194.0 L216.9,-196.4 L217.4,-198.8 L217.8,-201.2 L218.3,-203.6 L218.8,-206.0 L219.3,-208.5 L219.8,-210.9 L220.2,-213.3 L220.7,-215.8 L221.2,-218.2 L221.7,-220.7 L222.2,-223.2 L222.6,-225.6 L223.1,-228.1 L223.6,-230.6 L224.1,-233.1 L224.6,-235.6 L225.0,-238.1 L225.5,-240.7 L226.0,-243.2 L226.5,-245.7 L227.0,-248.3 L227.4,-250.8 L227.9,-253.4 L228.4,-256.0 L228.9,-258.5 L229.4,-261.1 L229.8,-263.7 L230.3,-266.3 L230.8,-268.9 L231.3,-271.5 L231.8,-274.1 L232.2,-276.8 L232.7,-279.4 L233.2,-282.0 L233.7,-284.7 L234.2,-287.3 L234.6,-290.0 L235.1,-292.7 L235.6,-295.4 L236.1,-298.0 L236.6,-300.7 L237.0,-303.4 L237.5,-306.1 L238.0,-308.9 L238.5,-311.6 L239.0,-314.3 L239.4,-317.1 L239.9,-319.8 L240.4,-322.6 L240.9,-325.3 L241.4,-328.1 L241.8,-330.9 L242.3,-333.6 L242.8,-336.4 L243.3,-339.2 L243.8,-342.0 L244.2,-344.8 L244.7,-347.7 L245.2,-350.5 L245.7,-353.3 L246.2,-356.2 L246.6,-359.0 L247.1,-361.9 L247.6,-364.8 L248.1,-367.6 L248.6,-370.5 L249.0,-373.4 L249.5,-376.3 L250.0,-379.2 L250.5,-382.1 L251.0,-385.0 L251.4,-387.9 L251.9,-390.9 L252.4,-393.8 L252.9,-396.8 L253.4,-399.7 L253.8,-402.7 L254.3,-405.7 L254.8,-408.6 L255.3,-411.6 L255.8,-414.6 L256.2,-417.6 L256.7,-420.6 L257.2,-423.6 L257.7,-426.7 L258.2,-429.7 L258.6,-432.7 L259.1,-435.8 L259.6,-438.8 L260.1,-441.9 L260.6,-444.9 L261.0,-448.0 L261.5,-451.1 L262.0,-454.2 L262.5,-457.3 L263.0,-460.4 L263.4,-463.5 L263.9,-466.6 L264.4,-469.8 L264.9,-472.9 L265.4,-476.0 L265.8,-479.2 L266.3,-482.3 L266.8,-485.5 L267.3,-488.7 L267.8,-491.8 L268.2,-495.0 L268.7,-498.2 L269.2,-501.4 L269.7,-504.6 L270.2,-507.9 L270.6,-511.1 L271.1,-514.3 L271.6,-517.6 L272.1,-520.8 L272.6,-524.1 L273.0,-527.3 L273.5,-530.6 L274.0,-533.9 L274.5,-537.1 L275.0,-540.4 L275.4,-543.7 L275.9,-547.0 L276.4,-550.4 L276.9,-553.7 L277.4,-557.0 L277.8,-560.3 L278.3,-563.7 L278.8,-567.0 L279.3,-570.4 L279.8,-573.8 L280.2,-577.1 L280.7,-580.5 L281.2,-583.9 L281.7,-587.3 L282.2,-590.7 L282.6,-594.1 L283.1,-597.5 L283.6,-601.0 L284.1,-604.4 L284.6,-607.8 L285.0,-611.3 L285.5,-614.7 L286.0,-618.2 L286.5,-621.7 L287.0,-625.1 L287.4,-628.6 L287.9,-632.1 L288.4,-635.6 L288.9,-639.1 L289.4,-642.6 L289.8,-646.2 L290.3,-649.7 L290.8,-653.2 L291.3,-656.8 L291.8,-660.3 L292.2,-663.9 L292.7,-667.5 L293.2,-671.0 L293.7,-674.6 L294.2,-678.2 L294.6,-681.8 L295.1,-685.4 L295.6,-689.0 L296.1,-692.6 L296.6,-696.3 L297.0,-699.9 L297.5,-703.5 L298.0,-707.2 L298.5,-710.8 L299.0,-714.5 L299.4,-718.2 L299.9,-721.9 L300.4,-725.6 L300.9,-729.2 L301.4,-732.9 L301.8,-736.7 L302.3,-740.4 L302.8,-744.1 L303.3,-747.8 L303.8,-751.6 L304.2,-755.3 L304.7,-759.1 L305.2,-762.8 L305.7,-766.6 L306.2,-770.4 L306.6,-774.2 L307.1,-778.0 L307.6,-781.8 L308.1,-785.6 L308.6,-789.4 L309.0,-793.2 L309.5,-797.0 L310.0,-800.9\" clip-path=\"url(#b10x7)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><text x=\"170.1\" y=\"27.4\" text-anchor=\"middle\" style=\"fill:var(--danger);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">f(x) = x², x ≥ 0</text><path d=\"M63.3,185.0 L63.8,183.2 L64.2,182.1 L64.7,181.2 L65.2,180.4 L65.7,179.8 L66.2,179.1 L66.6,178.6 L67.1,178.0 L67.6,177.5 L68.1,177.1 L68.6,176.6 L69.0,176.2 L69.5,175.8 L70.0,175.4 L70.5,175.0 L71.0,174.6 L71.4,174.3 L71.9,173.9 L72.4,173.6 L72.9,173.2 L73.4,172.9 L73.8,172.6 L74.3,172.3 L74.8,172.0 L75.3,171.7 L75.8,171.4 L76.2,171.1 L76.7,170.8 L77.2,170.5 L77.7,170.3 L78.2,170.0 L78.6,169.7 L79.1,169.5 L79.6,169.2 L80.1,169.0 L80.6,168.7 L81.0,168.5 L81.5,168.2 L82.0,168.0 L82.5,167.8 L83.0,167.5 L83.4,167.3 L83.9,167.1 L84.4,166.9 L84.9,166.6 L85.4,166.4 L85.8,166.2 L86.3,166.0 L86.8,165.8 L87.3,165.6 L87.8,165.4 L88.2,165.1 L88.7,164.9 L89.2,164.7 L89.7,164.5 L90.2,164.3 L90.6,164.1 L91.1,164.0 L91.6,163.8 L92.1,163.6 L92.6,163.4 L93.0,163.2 L93.5,163.0 L94.0,162.8 L94.5,162.6 L95.0,162.5 L95.4,162.3 L95.9,162.1 L96.4,161.9 L96.9,161.7 L97.4,161.6 L97.8,161.4 L98.3,161.2 L98.8,161.0 L99.3,160.9 L99.8,160.7 L100.2,160.5 L100.7,160.4 L101.2,160.2 L101.7,160.0 L102.2,159.9 L102.6,159.7 L103.1,159.5 L103.6,159.4 L104.1,159.2 L104.6,159.1 L105.0,158.9 L105.5,158.7 L106.0,158.6 L106.5,158.4 L107.0,158.3 L107.4,158.1 L107.9,158.0 L108.4,157.8 L108.9,157.7 L109.4,157.5 L109.8,157.4 L110.3,157.2 L110.8,157.1 L111.3,156.9 L111.8,156.8 L112.2,156.6 L112.7,156.5 L113.2,156.3 L113.7,156.2 L114.2,156.0 L114.6,155.9 L115.1,155.7 L115.6,155.6 L116.1,155.5 L116.6,155.3 L117.0,155.2 L117.5,155.0 L118.0,154.9 L118.5,154.8 L119.0,154.6 L119.4,154.5 L119.9,154.4 L120.4,154.2 L120.9,154.1 L121.4,153.9 L121.8,153.8 L122.3,153.7 L122.8,153.5 L123.3,153.4 L123.8,153.3 L124.2,153.1 L124.7,153.0 L125.2,152.9 L125.7,152.8 L126.2,152.6 L126.6,152.5 L127.1,152.4 L127.6,152.2 L128.1,152.1 L128.6,152.0 L129.0,151.9 L129.5,151.7 L130.0,151.6 L130.5,151.5 L131.0,151.4 L131.4,151.2 L131.9,151.1 L132.4,151.0 L132.9,150.9 L133.4,150.7 L133.8,150.6 L134.3,150.5 L134.8,150.4 L135.3,150.3 L135.8,150.1 L136.2,150.0 L136.7,149.9 L137.2,149.8 L137.7,149.7 L138.2,149.5 L138.6,149.4 L139.1,149.3 L139.6,149.2 L140.1,149.1 L140.6,148.9 L141.0,148.8 L141.5,148.7 L142.0,148.6 L142.5,148.5 L143.0,148.4 L143.4,148.3 L143.9,148.1 L144.4,148.0 L144.9,147.9 L145.4,147.8 L145.8,147.7 L146.3,147.6 L146.8,147.5 L147.3,147.3 L147.8,147.2 L148.2,147.1 L148.7,147.0 L149.2,146.9 L149.7,146.8 L150.2,146.7 L150.6,146.6 L151.1,146.5 L151.6,146.4 L152.1,146.2 L152.6,146.1 L153.0,146.0 L153.5,145.9 L154.0,145.8 L154.5,145.7 L155.0,145.6 L155.4,145.5 L155.9,145.4 L156.4,145.3 L156.9,145.2 L157.4,145.1 L157.8,145.0 L158.3,144.9 L158.8,144.7 L159.3,144.6 L159.8,144.5 L160.2,144.4 L160.7,144.3 L161.2,144.2 L161.7,144.1 L162.2,144.0 L162.6,143.9 L163.1,143.8 L163.6,143.7 L164.1,143.6 L164.6,143.5 L165.0,143.4 L165.5,143.3 L166.0,143.2 L166.5,143.1 L167.0,143.0 L167.4,142.9 L167.9,142.8 L168.4,142.7 L168.9,142.6 L169.4,142.5 L169.8,142.4 L170.3,142.3 L170.8,142.2 L171.3,142.1 L171.8,142.0 L172.2,141.9 L172.7,141.8 L173.2,141.7 L173.7,141.6 L174.2,141.5 L174.6,141.4 L175.1,141.3 L175.6,141.2 L176.1,141.1 L176.6,141.0 L177.0,140.9 L177.5,140.8 L178.0,140.7 L178.5,140.6 L179.0,140.6 L179.4,140.5 L179.9,140.4 L180.4,140.3 L180.9,140.2 L181.4,140.1 L181.8,140.0 L182.3,139.9 L182.8,139.8 L183.3,139.7 L183.8,139.6 L184.2,139.5 L184.7,139.4 L185.2,139.3 L185.7,139.2 L186.2,139.1 L186.6,139.1 L187.1,139.0 L187.6,138.9 L188.1,138.8 L188.6,138.7 L189.0,138.6 L189.5,138.5 L190.0,138.4 L190.5,138.3 L191.0,138.2 L191.4,138.1 L191.9,138.0 L192.4,138.0 L192.9,137.9 L193.4,137.8 L193.8,137.7 L194.3,137.6 L194.8,137.5 L195.3,137.4 L195.8,137.3 L196.2,137.2 L196.7,137.1 L197.2,137.1 L197.7,137.0 L198.2,136.9 L198.6,136.8 L199.1,136.7 L199.6,136.6 L200.1,136.5 L200.6,136.4 L201.0,136.4 L201.5,136.3 L202.0,136.2 L202.5,136.1 L203.0,136.0 L203.4,135.9 L203.9,135.8 L204.4,135.7 L204.9,135.7 L205.4,135.6 L205.8,135.5 L206.3,135.4 L206.8,135.3 L207.3,135.2 L207.8,135.1 L208.2,135.1 L208.7,135.0 L209.2,134.9 L209.7,134.8 L210.2,134.7 L210.6,134.6 L211.1,134.6 L211.6,134.5 L212.1,134.4 L212.6,134.3 L213.0,134.2 L213.5,134.1 L214.0,134.0 L214.5,134.0 L215.0,133.9 L215.4,133.8 L215.9,133.7 L216.4,133.6 L216.9,133.6 L217.4,133.5 L217.8,133.4 L218.3,133.3 L218.8,133.2 L219.3,133.1 L219.8,133.1 L220.2,133.0 L220.7,132.9 L221.2,132.8 L221.7,132.7 L222.2,132.6 L222.6,132.6 L223.1,132.5 L223.6,132.4 L224.1,132.3 L224.6,132.2 L225.0,132.2 L225.5,132.1 L226.0,132.0 L226.5,131.9 L227.0,131.8 L227.4,131.8 L227.9,131.7 L228.4,131.6 L228.9,131.5 L229.4,131.4 L229.8,131.4 L230.3,131.3 L230.8,131.2 L231.3,131.1 L231.8,131.0 L232.2,131.0 L232.7,130.9 L233.2,130.8 L233.7,130.7 L234.2,130.7 L234.6,130.6 L235.1,130.5 L235.6,130.4 L236.1,130.3 L236.6,130.3 L237.0,130.2 L237.5,130.1 L238.0,130.0 L238.5,129.9 L239.0,129.9 L239.4,129.8 L239.9,129.7 L240.4,129.6 L240.9,129.6 L241.4,129.5 L241.8,129.4 L242.3,129.3 L242.8,129.3 L243.3,129.2 L243.8,129.1 L244.2,129.0 L244.7,128.9 L245.2,128.9 L245.7,128.8 L246.2,128.7 L246.6,128.6 L247.1,128.6 L247.6,128.5 L248.1,128.4 L248.6,128.3 L249.0,128.3 L249.5,128.2 L250.0,128.1 L250.5,128.0 L251.0,128.0 L251.4,127.9 L251.9,127.8 L252.4,127.7 L252.9,127.7 L253.4,127.6 L253.8,127.5 L254.3,127.4 L254.8,127.4 L255.3,127.3 L255.8,127.2 L256.2,127.1 L256.7,127.1 L257.2,127.0 L257.7,126.9 L258.2,126.9 L258.6,126.8 L259.1,126.7 L259.6,126.6 L260.1,126.6 L260.6,126.5 L261.0,126.4 L261.5,126.3 L262.0,126.3 L262.5,126.2 L263.0,126.1 L263.4,126.1 L263.9,126.0 L264.4,125.9 L264.9,125.8 L265.4,125.8 L265.8,125.7 L266.3,125.6 L266.8,125.5 L267.3,125.5 L267.8,125.4 L268.2,125.3 L268.7,125.3 L269.2,125.2 L269.7,125.1 L270.2,125.0 L270.6,125.0 L271.1,124.9 L271.6,124.8 L272.1,124.8 L272.6,124.7 L273.0,124.6 L273.5,124.5 L274.0,124.5 L274.5,124.4 L275.0,124.3 L275.4,124.3 L275.9,124.2 L276.4,124.1 L276.9,124.1 L277.4,124.0 L277.8,123.9 L278.3,123.8 L278.8,123.8 L279.3,123.7 L279.8,123.6 L280.2,123.6 L280.7,123.5 L281.2,123.4 L281.7,123.4 L282.2,123.3 L282.6,123.2 L283.1,123.1 L283.6,123.1 L284.1,123.0 L284.6,122.9 L285.0,122.9 L285.5,122.8 L286.0,122.7 L286.5,122.7 L287.0,122.6 L287.4,122.5 L287.9,122.5 L288.4,122.4 L288.9,122.3 L289.4,122.3 L289.8,122.2 L290.3,122.1 L290.8,122.1 L291.3,122.0 L291.8,121.9 L292.2,121.8 L292.7,121.8 L293.2,121.7 L293.7,121.6 L294.2,121.6 L294.6,121.5 L295.1,121.4 L295.6,121.4 L296.1,121.3 L296.6,121.2 L297.0,121.2 L297.5,121.1 L298.0,121.0 L298.5,121.0 L299.0,120.9 L299.4,120.8 L299.9,120.8 L300.4,120.7 L300.9,120.6 L301.4,120.6 L301.8,120.5 L302.3,120.4 L302.8,120.4 L303.3,120.3 L303.8,120.2 L304.2,120.2 L304.7,120.1 L305.2,120.0 L305.7,120.0 L306.2,119.9 L306.6,119.8 L307.1,119.8 L307.6,119.7 L308.1,119.6 L308.6,119.6 L309.0,119.5 L309.5,119.5 L310.0,119.4\" clip-path=\"url(#b10x7)\" style=\"fill:none;stroke:var(--success);stroke-width:2.2\"/><text x=\"235.9\" y=\"122.4\" text-anchor=\"middle\" style=\"fill:var(--success);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">f⁻¹(x) = √x</text><circle cx=\"145.4\" cy=\"76.9\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"152.4\" y=\"67.9\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(2, 4)</text><circle cx=\"227.7\" cy=\"131.7\" r=\"3.8\" style=\"fill:var(--ink)\"/><text x=\"234.7\" y=\"122.7\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(4, 2)</text></svg><div class=\"ex\"><div class=\"exh\">Worked example 2 · Quadratic with restricted domain</div><div class=\"exl\">Find the inverse of f(x) = x² − 3, x ≥ 0.<br>Switch: x = y² − 3, so y² = x + 3.<br>y ≥ 0 (the old domain), so <b>f⁻¹(x) = √(x + 3)</b>, with domain x ≥ −3.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Radical function</div><div class=\"exl\">Find the inverse of f(x) = √(x − 5).<br>The range of f is y ≥ 0. Switch: x = √(y − 5), so x² = y − 5.<br><b>f⁻¹(x) = x² + 5, x ≥ 0</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 4 · Verify inverses</div><div class=\"exl\">Are f(x) = 4x − 7 and g(x) = <span class=\"fq\"><span>x + 7</span><span>4</span></span> inverses?<br>f(g(x)) = 4 · <span class=\"fq\"><span>x + 7</span><span>4</span></span> − 7 = x + 7 − 7 = x.<br>g(f(x)) = <span class=\"fq\"><span>4x − 7 + 7</span><span>4</span></span> = x. Both give x, so <b>yes</b>.</div></div><div class=\"keybox\"><b>Common mistake.</b> To invert, undo the operations in <b>reverse order with opposite operations</b>. For f(x) = 3x − 2 (multiply by 3, then subtract 2), f⁻¹(x) = (x + 2) ÷ 3, not 3x + 2 and not 1 ÷ (3x − 2).</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s4\">Practise 10.4 →</button></div></section><section class=\"note\" id=\"nsum\"><h2>Chapter checklist</h2><ul><li>I can graph square root functions, find their domain and range, describe transformations of f(x) = √x and compare average rates of change.</li><li>I can graph cube root functions, find their point of symmetry and intercepts, describe transformations of f(x) = ∛x and compare them with other functions.</li><li>I can solve equations with square roots and cube roots by isolating the radical and raising both sides to a power, and identify extraneous solutions.</li><li>I can find inverses of relations and functions, restrict domains so that an inverse is a function, and check that two functions are inverses.</li></ul><div class=\"hub-btns\" style=\"margin-top:10px\"><button class=\"hub-btn\" data-go=\"s5\">Assessment A</button><button class=\"hub-btn\" data-go=\"s6\">Assessment B</button><button class=\"hub-btn\" data-go=\"s7\">Assessment C</button><button class=\"hub-btn\" data-go=\"s8\">Assessment D</button><button class=\"hub-btn primary\" data-go=\"report\">📊 Report</button></div></section>";
var REPORT = [["s5", "A", "Knowing and understanding"], ["s6", "B", "Investigating patterns"], ["s7", "C", "Communicating"], ["s8", "D", "Applying mathematics in real-life contexts"]];
var SECTIONS = [{"id": "s1", "label": "10.1 Graphing Square Root Functions", "sub": "I can graph square root functions, find their domain and range, describe transformations of f(x) = √x and compare average rates of change.", "slides": [{"kind": "mcq", "text": "Which value of x is NOT in the domain of f(x) = √(x − 4)?", "opts": ["x = 3", "x = 13", "x = 5", "x = 4"], "correct": 0, "tag": "", "sol": "The radicand must be non-negative: x − 4 ≥ 0, so x ≥ 4. For x = 3 the radicand is −1, and √(−1) is not a real number. (x = 4 gives √0 = 0, which is allowed.)"}, {"kind": "blank", "p": "Complete the table of values for f(x) = 2√x.", "tag": "", "marks": "", "flat": [{"t": "f(0) = __B1__", "a": {"B1": "0"}}, {"t": "f(4) = __B1__", "a": {"B1": "4"}}, {"t": "f(9) = __B1__", "a": {"B1": "6"}}, {"t": "f(16) = __B1__", "a": {"B1": "8"}}], "sol": "2√0 = 2(0) = 0.\n2√4 = 2(2) = 4.\n2√9 = 2(3) = 6.\n2√16 = 2(4) = 8. Each output is twice the output of √x: a vertical stretch by 2."}, {"kind": "mcq", "text": "How is the graph of g(x) = √(x + 3) related to the graph of f(x) = √x?", "opts": ["It is translated 3 units down", "It is translated 3 units left", "It is translated 3 units right", "It is translated 3 units up"], "correct": 1, "tag": "", "sol": "g(x) = f(x − (−3)), so h = −3: the graph moves 3 units left. The endpoint moves from (0, 0) to (−3, 0).", "tools": ["desmos"], "desmos": ["y=\\sqrt{x}", "y=\\sqrt{x+3}"]}, {"kind": "blank", "p": "Look at g(x) = √(x − 5) + 2.", "tag": "", "marks": "", "flat": [{"t": "The endpoint of the graph is (5, __B1__)", "a": {"B1": "2"}}, {"t": "Domain: x ≥ __B1__", "a": {"B1": "5"}}, {"t": "Range: y ≥ __B1__", "a": {"B1": "2"}}, {"t": "g(14) = __B1__", "a": {"B1": "5"}}], "sol": "h = 5 and k = 2, so the endpoint is (5, 2).\nx − 5 ≥ 0 gives x ≥ 5.\n√(x − 5) ≥ 0, so g(x) ≥ 0 + 2 = 2.\ng(14) = √9 + 2 = 3 + 2 = 5.", "tools": ["desmos"], "desmos": ["y=\\sqrt{x-5}+2"]}, {"kind": "mcq", "text": "Which function is shown in the graph?", "opts": ["y = √(x − 2) + 1", "y = √(x + 1) + 2", "y = √(x + 2) − 1", "y = √(x + 2) + 1"], "correct": 3, "tag": "", "sol": "The endpoint is (−2, 1), so h = −2 and k = 1: y = √(x + 2) + 1. Check another point: x = 2 gives √4 + 1 = 3 ✓ and x = 7 gives √9 + 1 = 4 ✓", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"22.0\" y1=\"214.0\" x2=\"22.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"44.3\" y1=\"214.0\" x2=\"44.3\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"66.7\" y1=\"214.0\" x2=\"66.7\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"89.0\" y1=\"214.0\" x2=\"89.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"111.3\" y1=\"214.0\" x2=\"111.3\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"133.7\" y1=\"214.0\" x2=\"133.7\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"156.0\" y1=\"214.0\" x2=\"156.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"178.3\" y1=\"214.0\" x2=\"178.3\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"200.7\" y1=\"214.0\" x2=\"200.7\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"223.0\" y1=\"214.0\" x2=\"223.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"245.3\" y1=\"214.0\" x2=\"245.3\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"267.7\" y1=\"214.0\" x2=\"267.7\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"290.0\" y1=\"214.0\" x2=\"290.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"214.0\" x2=\"290.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"184.6\" x2=\"290.0\" y2=\"184.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"155.1\" x2=\"290.0\" y2=\"155.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"125.7\" x2=\"290.0\" y2=\"125.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"96.3\" x2=\"290.0\" y2=\"96.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"66.9\" x2=\"290.0\" y2=\"66.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"37.4\" x2=\"290.0\" y2=\"37.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"8.0\" x2=\"290.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"155.1\" x2=\"290.0\" y2=\"155.1\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"111.3\" y1=\"214.0\" x2=\"111.3\" y2=\"8.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"22.0\" y=\"164.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"66.7\" y=\"164.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"156.0\" y=\"164.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"200.7\" y=\"164.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"245.3\" y=\"164.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"290.0\" y=\"164.1\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><text class=\"po\" x=\"107.3\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"107.3\" y=\"96.3\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"107.3\" y=\"37.4\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"286.0\" y=\"147.1\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"119.3\" y=\"14.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x8\"><rect x=\"22.0\" y=\"8.0\" width=\"268.0\" height=\"206.0\"/></clipPath><path d=\"M66.7,125.7 L67.1,121.6 L67.6,119.8 L68.0,118.5 L68.5,117.4 L68.9,116.4 L69.3,115.5 L69.8,114.7 L70.2,113.9 L70.7,113.2 L71.1,112.6 L71.6,111.9 L72.0,111.3 L72.5,110.7 L72.9,110.1 L73.4,109.6 L73.8,109.1 L74.3,108.6 L74.7,108.1 L75.2,107.6 L75.6,107.1 L76.0,106.6 L76.5,106.2 L76.9,105.8 L77.4,105.3 L77.8,104.9 L78.3,104.5 L78.7,104.1 L79.2,103.7 L79.6,103.3 L80.1,102.9 L80.5,102.5 L81.0,102.2 L81.4,101.8 L81.9,101.4 L82.3,101.1 L82.7,100.7 L83.2,100.4 L83.6,100.1 L84.1,99.7 L84.5,99.4 L85.0,99.1 L85.4,98.7 L85.9,98.4 L86.3,98.1 L86.8,97.8 L87.2,97.5 L87.7,97.2 L88.1,96.9 L88.6,96.6 L89.0,96.3 L89.4,96.0 L89.9,95.7 L90.3,95.4 L90.8,95.1 L91.2,94.8 L91.7,94.6 L92.1,94.3 L92.6,94.0 L93.0,93.7 L93.5,93.5 L93.9,93.2 L94.4,92.9 L94.8,92.7 L95.3,92.4 L95.7,92.2 L96.1,91.9 L96.6,91.6 L97.0,91.4 L97.5,91.1 L97.9,90.9 L98.4,90.6 L98.8,90.4 L99.3,90.2 L99.7,89.9 L100.2,89.7 L100.6,89.4 L101.1,89.2 L101.5,89.0 L102.0,88.7 L102.4,88.5 L102.8,88.3 L103.3,88.0 L103.7,87.8 L104.2,87.6 L104.6,87.3 L105.1,87.1 L105.5,86.9 L106.0,86.7 L106.4,86.5 L106.9,86.2 L107.3,86.0 L107.8,85.8 L108.2,85.6 L108.7,85.4 L109.1,85.1 L109.5,84.9 L110.0,84.7 L110.4,84.5 L110.9,84.3 L111.3,84.1 L111.8,83.9 L112.2,83.7 L112.7,83.5 L113.1,83.3 L113.6,83.1 L114.0,82.9 L114.5,82.7 L114.9,82.5 L115.4,82.3 L115.8,82.1 L116.2,81.9 L116.7,81.7 L117.1,81.5 L117.6,81.3 L118.0,81.1 L118.5,80.9 L118.9,80.7 L119.4,80.5 L119.8,80.3 L120.3,80.1 L120.7,79.9 L121.2,79.7 L121.6,79.6 L122.1,79.4 L122.5,79.2 L122.9,79.0 L123.4,78.8 L123.8,78.6 L124.3,78.4 L124.7,78.3 L125.2,78.1 L125.6,77.9 L126.1,77.7 L126.5,77.5 L127.0,77.4 L127.4,77.2 L127.9,77.0 L128.3,76.8 L128.8,76.6 L129.2,76.5 L129.6,76.3 L130.1,76.1 L130.5,75.9 L131.0,75.8 L131.4,75.6 L131.9,75.4 L132.3,75.3 L132.8,75.1 L133.2,74.9 L133.7,74.7 L134.1,74.6 L134.6,74.4 L135.0,74.2 L135.5,74.1 L135.9,73.9 L136.3,73.7 L136.8,73.6 L137.2,73.4 L137.7,73.2 L138.1,73.1 L138.6,72.9 L139.0,72.7 L139.5,72.6 L139.9,72.4 L140.4,72.3 L140.8,72.1 L141.3,71.9 L141.7,71.8 L142.2,71.6 L142.6,71.5 L143.0,71.3 L143.5,71.1 L143.9,71.0 L144.4,70.8 L144.8,70.7 L145.3,70.5 L145.7,70.3 L146.2,70.2 L146.6,70.0 L147.1,69.9 L147.5,69.7 L148.0,69.6 L148.4,69.4 L148.9,69.3 L149.3,69.1 L149.7,69.0 L150.2,68.8 L150.6,68.7 L151.1,68.5 L151.5,68.3 L152.0,68.2 L152.4,68.0 L152.9,67.9 L153.3,67.7 L153.8,67.6 L154.2,67.4 L154.7,67.3 L155.1,67.2 L155.6,67.0 L156.0,66.9 L156.4,66.7 L156.9,66.6 L157.3,66.4 L157.8,66.3 L158.2,66.1 L158.7,66.0 L159.1,65.8 L159.6,65.7 L160.0,65.5 L160.5,65.4 L160.9,65.3 L161.4,65.1 L161.8,65.0 L162.3,64.8 L162.7,64.7 L163.1,64.5 L163.6,64.4 L164.0,64.3 L164.5,64.1 L164.9,64.0 L165.4,63.8 L165.8,63.7 L166.3,63.6 L166.7,63.4 L167.2,63.3 L167.6,63.1 L168.1,63.0 L168.5,62.9 L169.0,62.7 L169.4,62.6 L169.8,62.5 L170.3,62.3 L170.7,62.2 L171.2,62.1 L171.6,61.9 L172.1,61.8 L172.5,61.6 L173.0,61.5 L173.4,61.4 L173.9,61.2 L174.3,61.1 L174.8,61.0 L175.2,60.8 L175.7,60.7 L176.1,60.6 L176.5,60.4 L177.0,60.3 L177.4,60.2 L177.9,60.0 L178.3,59.9 L178.8,59.8 L179.2,59.6 L179.7,59.5 L180.1,59.4 L180.6,59.3 L181.0,59.1 L181.5,59.0 L181.9,58.9 L182.4,58.7 L182.8,58.6 L183.2,58.5 L183.7,58.3 L184.1,58.2 L184.6,58.1 L185.0,58.0 L185.5,57.8 L185.9,57.7 L186.4,57.6 L186.8,57.5 L187.3,57.3 L187.7,57.2 L188.2,57.1 L188.6,56.9 L189.1,56.8 L189.5,56.7 L189.9,56.6 L190.4,56.4 L190.8,56.3 L191.3,56.2 L191.7,56.1 L192.2,55.9 L192.6,55.8 L193.1,55.7 L193.5,55.6 L194.0,55.5 L194.4,55.3 L194.9,55.2 L195.3,55.1 L195.8,55.0 L196.2,54.8 L196.6,54.7 L197.1,54.6 L197.5,54.5 L198.0,54.4 L198.4,54.2 L198.9,54.1 L199.3,54.0 L199.8,53.9 L200.2,53.7 L200.7,53.6 L201.1,53.5 L201.6,53.4 L202.0,53.3 L202.5,53.2 L202.9,53.0 L203.3,52.9 L203.8,52.8 L204.2,52.7 L204.7,52.6 L205.1,52.4 L205.6,52.3 L206.0,52.2 L206.5,52.1 L206.9,52.0 L207.4,51.8 L207.8,51.7 L208.3,51.6 L208.7,51.5 L209.2,51.4 L209.6,51.3 L210.0,51.1 L210.5,51.0 L210.9,50.9 L211.4,50.8 L211.8,50.7 L212.3,50.6 L212.7,50.5 L213.2,50.3 L213.6,50.2 L214.1,50.1 L214.5,50.0 L215.0,49.9 L215.4,49.8 L215.9,49.7 L216.3,49.5 L216.7,49.4 L217.2,49.3 L217.6,49.2 L218.1,49.1 L218.5,49.0 L219.0,48.9 L219.4,48.7 L219.9,48.6 L220.3,48.5 L220.8,48.4 L221.2,48.3 L221.7,48.2 L222.1,48.1 L222.6,48.0 L223.0,47.9 L223.4,47.7 L223.9,47.6 L224.3,47.5 L224.8,47.4 L225.2,47.3 L225.7,47.2 L226.1,47.1 L226.6,47.0 L227.0,46.9 L227.5,46.7 L227.9,46.6 L228.4,46.5 L228.8,46.4 L229.3,46.3 L229.7,46.2 L230.1,46.1 L230.6,46.0 L231.0,45.9 L231.5,45.8 L231.9,45.7 L232.4,45.6 L232.8,45.4 L233.3,45.3 L233.7,45.2 L234.2,45.1 L234.6,45.0 L235.1,44.9 L235.5,44.8 L236.0,44.7 L236.4,44.6 L236.8,44.5 L237.3,44.4 L237.7,44.3 L238.2,44.2 L238.6,44.1 L239.1,43.9 L239.5,43.8 L240.0,43.7 L240.4,43.6 L240.9,43.5 L241.3,43.4 L241.8,43.3 L242.2,43.2 L242.7,43.1 L243.1,43.0 L243.5,42.9 L244.0,42.8 L244.4,42.7 L244.9,42.6 L245.3,42.5 L245.8,42.4 L246.2,42.3 L246.7,42.2 L247.1,42.1 L247.6,42.0 L248.0,41.9 L248.5,41.8 L248.9,41.6 L249.4,41.5 L249.8,41.4 L250.2,41.3 L250.7,41.2 L251.1,41.1 L251.6,41.0 L252.0,40.9 L252.5,40.8 L252.9,40.7 L253.4,40.6 L253.8,40.5 L254.3,40.4 L254.7,40.3 L255.2,40.2 L255.6,40.1 L256.1,40.0 L256.5,39.9 L256.9,39.8 L257.4,39.7 L257.8,39.6 L258.3,39.5 L258.7,39.4 L259.2,39.3 L259.6,39.2 L260.1,39.1 L260.5,39.0 L261.0,38.9 L261.4,38.8 L261.9,38.7 L262.3,38.6 L262.8,38.5 L263.2,38.4 L263.6,38.3 L264.1,38.2 L264.5,38.1 L265.0,38.0 L265.4,37.9 L265.9,37.8 L266.3,37.7 L266.8,37.6 L267.2,37.5 L267.7,37.4 L268.1,37.3 L268.6,37.2 L269.0,37.1 L269.5,37.0 L269.9,36.9 L270.3,36.8 L270.8,36.7 L271.2,36.6 L271.7,36.6 L272.1,36.5 L272.6,36.4 L273.0,36.3 L273.5,36.2 L273.9,36.1 L274.4,36.0 L274.8,35.9 L275.3,35.8 L275.7,35.7 L276.2,35.6 L276.6,35.5 L277.0,35.4 L277.5,35.3 L277.9,35.2 L278.4,35.1 L278.8,35.0 L279.3,34.9 L279.7,34.8 L280.2,34.7 L280.6,34.6 L281.1,34.5 L281.5,34.4 L282.0,34.3 L282.4,34.2 L282.9,34.2 L283.3,34.1 L283.7,34.0 L284.2,33.9 L284.6,33.8 L285.1,33.7 L285.5,33.6 L286.0,33.5 L286.4,33.4 L286.9,33.3 L287.3,33.2 L287.8,33.1 L288.2,33.0 L288.7,32.9 L289.1,32.8 L289.6,32.7 L290.0,32.7\" clip-path=\"url(#b10x8)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><circle cx=\"66.7\" cy=\"125.7\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"156.0\" cy=\"66.9\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"267.7\" cy=\"37.4\" r=\"3.8\" style=\"fill:var(--ink)\"/></svg>", "tools": ["desmos"], "desmos": ["y=\\sqrt{x}"]}, {"kind": "blank", "p": "Look at g(x) = −3√x.", "tag": "", "marks": "", "flat": [{"t": "The graph of √x is stretched by 3 and reflected in the __B1__ (x-axis / y-axis).", "a": {"B1": "x-axis"}, "expr": "words", "accept": ["x axis", "xaxis"]}, {"t": "Range: y ≤ __B1__", "a": {"B1": "0"}}, {"t": "g(4) = __B1__", "a": {"B1": "-6"}}], "sol": "The negative factor in front of the radical multiplies every output by −1: a reflection in the x-axis.\n√x ≥ 0, so −3√x ≤ 0.\n−3√4 = −3(2) = −6.", "tools": ["desmos"], "desmos": ["y=-3\\sqrt{x}"]}, {"kind": "mcq", "text": "<b>Error analysis.</b> Meera says the domain of f(x) = √(x + 6) is x ≥ 6. Which reply is correct?", "opts": ["The domain is all real numbers, because x + 6 can be any number", "She is right: the domain is x ≥ 6", "The domain is x ≥ −6, because x + 6 ≥ 0", "The domain is x ≤ −6, because x + 6 ≤ 0"], "correct": 2, "tag": "", "sol": "Set the radicand ≥ 0: x + 6 ≥ 0, so x ≥ −6. For example x = −2 works: √4 = 2. The +6 moves the graph 6 units left, not right."}, {"kind": "blank", "p": "Find the domain of f(x) = √(2x − 8).", "tag": "", "marks": "", "flat": [{"t": "Solve 2x − 8 ≥ 0: x ≥ __B1__", "a": {"B1": "4"}}, {"t": "f(12) = __B1__", "a": {"B1": "4"}}, {"t": "f(4) = __B1__", "a": {"B1": "0"}}], "sol": "2x ≥ 8, so x ≥ 4.\nf(12) = √(24 − 8) = √16 = 4.\nf(4) = √0 = 0: the endpoint is (4, 0)."}, {"kind": "mcq", "text": "What is the range of h(x) = −√(x − 1) + 4?", "opts": ["y ≥ 4", "y ≥ 1", "y ≤ 4", "y ≤ 1"], "correct": 2, "tag": "", "sol": "−√(x − 1) ≤ 0, so h(x) ≤ 0 + 4 = 4. The graph starts at (1, 4) and goes down. (1 is the boundary of the domain, not the range.)", "tools": ["desmos"], "desmos": ["y=-\\sqrt{x-1}+4"]}, {"kind": "blank", "p": "A stone is dropped from a cliff. The time t (in seconds) it takes to fall h feet is t = {1/4}√h.", "tag": "", "marks": "", "flat": [{"t": "Time to fall 64 ft: t = __B1__ s", "a": {"B1": "2"}}, {"t": "Time to fall 144 ft: t = __B1__ s", "a": {"B1": "3"}}, {"t": "Time to fall 256 ft: t = __B1__ s", "a": {"B1": "4"}}], "sol": "{1/4}√64 = {1/4}(8) = 2 s.\n{1/4}√144 = {1/4}(12) = 3 s.\n{1/4}√256 = {1/4}(16) = 4 s. A fall four times as high takes only twice as long.", "tools": ["desmos"], "desmos": ["y=\\frac{1}{4}\\sqrt{x}"]}, {"kind": "mcq", "text": "f(x) = 3√x. What is the average rate of change of f from x = 1 to x = 4?", "opts": ["{1/3}", "1.5", "3", "1"], "correct": 3, "tag": "", "sol": "f(1) = 3 and f(4) = 3(2) = 6. Average rate of change = (6 − 3) ÷ (4 − 1) = 3 ÷ 3 = 1. (3 is the change in f, not the rate; 1.5 is {6/4}.)"}, {"kind": "blank", "p": "The distance d (in miles) you can see to the horizon from a height of h feet is about d = √(1.5h).", "tag": "", "marks": "", "flat": [{"t": "From a 24 ft lookout tower: d = __B1__ miles", "a": {"B1": "6"}}, {"t": "From a 96 ft lighthouse: d = __B1__ miles", "a": {"B1": "12"}}, {"t": "Making the height 4 times as great makes the distance __B1__ (double / quadruple).", "a": {"B1": "double"}, "expr": "words", "accept": ["doubles", "doubled", "twice", "2 times"]}], "sol": "√(1.5 × 24) = √36 = 6.\n√(1.5 × 96) = √144 = 12.\n96 = 4 × 24 and 12 = 2 × 6: √(4h) = 2√h, so the distance doubles.", "tools": ["calc"], "desmos": []}, {"kind": "mcq", "text": "Which function has domain x ≥ −2 and range y ≤ 3?", "opts": ["y = √(x + 2) + 3", "y = −√(x − 2) + 3", "y = −√(x + 2) + 3", "y = −√(x + 3) − 2"], "correct": 2, "tag": "", "sol": "x + 2 ≥ 0 gives x ≥ −2; the negative sign in front makes the graph go down from k = 3, so y ≤ 3. √(x + 2) + 3 has range y ≥ 3; −√(x − 2) + 3 has domain x ≥ 2; −√(x + 3) − 2 has domain x ≥ −3."}, {"kind": "blank", "p": "Write a rule for g, a transformation of f(x) = √x (type √ as sqrt( ) or use the √ key).", "tag": "", "marks": "", "flat": [{"t": "Translate 2 units left and 3 units up: g(x) = __B1__", "a": {"B1": "sqrt(x+2)+3"}, "expr": "calc", "accept": ["3+sqrt(x+2)"]}, {"t": "Stretch vertically by a factor of 4, then translate 1 unit down: g(x) = __B1__", "a": {"B1": "4sqrt(x)-1"}, "expr": "calc", "accept": ["4*sqrt(x)-1", "-1+4sqrt(x)"]}], "sol": "Left 2 replaces x with x + 2; up 3 adds 3: g(x) = √(x + 2) + 3.\nStretch: 4√x. Down 1: g(x) = 4√x − 1."}, {"kind": "mcq", "text": "Which graph shows g(x) = −√(x + 1)?", "opts": ["Graph A", "Graph D", "Graph B", "Graph C"], "correct": 3, "tag": "", "sol": "√(x + 1) starts at (−1, 0); the negative sign reflects it in the x-axis, so the graph starts at (−1, 0) and goes down to the right: Graph C. (A is √(x + 1), B is √(x − 1) and D is −√(x − 1).)", "fig": "<div style=\"display:grid;grid-template-columns:1fr 1fr;gap:6px;width:100%;max-width:340px\"><svg class=\"figsvg\" viewBox=\"0 0 165 150\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"82.5\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Graph A</text><line x1=\"22.0\" y1=\"134.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"38.6\" y1=\"134.0\" x2=\"38.6\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"55.2\" y1=\"134.0\" x2=\"55.2\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"71.9\" y1=\"134.0\" x2=\"71.9\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"88.5\" y1=\"134.0\" x2=\"88.5\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"105.1\" y1=\"134.0\" x2=\"105.1\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"121.8\" y1=\"134.0\" x2=\"121.8\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"138.4\" y1=\"134.0\" x2=\"138.4\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"155.0\" y1=\"134.0\" x2=\"155.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"134.0\" x2=\"155.0\" y2=\"134.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"115.3\" x2=\"155.0\" y2=\"115.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"96.7\" x2=\"155.0\" y2=\"96.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"78.0\" x2=\"155.0\" y2=\"78.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"59.3\" x2=\"155.0\" y2=\"59.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"40.7\" x2=\"155.0\" y2=\"40.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"155.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"78.0\" x2=\"155.0\" y2=\"78.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"71.9\" y1=\"134.0\" x2=\"71.9\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"38.6\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"105.1\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"138.4\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"67.9\" y=\"115.3\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"67.9\" y=\"40.7\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"151.0\" y=\"70.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"79.9\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x9\"><rect x=\"22.0\" y=\"22.0\" width=\"133.0\" height=\"112.0\"/></clipPath><path d=\"M55.2,78.0 L55.5,75.8 L55.7,75.0 L55.9,74.3 L56.1,73.7 L56.4,73.2 L56.6,72.7 L56.8,72.3 L57.0,71.9 L57.2,71.5 L57.5,71.2 L57.7,70.9 L57.9,70.5 L58.1,70.2 L58.4,69.9 L58.6,69.7 L58.8,69.4 L59.0,69.1 L59.2,68.9 L59.5,68.6 L59.7,68.4 L59.9,68.1 L60.1,67.9 L60.3,67.7 L60.6,67.4 L60.8,67.2 L61.0,67.0 L61.2,66.8 L61.5,66.6 L61.7,66.4 L61.9,66.2 L62.1,66.0 L62.3,65.8 L62.6,65.6 L62.8,65.4 L63.0,65.2 L63.2,65.1 L63.5,64.9 L63.7,64.7 L63.9,64.5 L64.1,64.4 L64.3,64.2 L64.6,64.0 L64.8,63.9 L65.0,63.7 L65.2,63.5 L65.4,63.4 L65.7,63.2 L65.9,63.1 L66.1,62.9 L66.3,62.8 L66.6,62.6 L66.8,62.5 L67.0,62.3 L67.2,62.2 L67.4,62.0 L67.7,61.9 L67.9,61.7 L68.1,61.6 L68.3,61.4 L68.5,61.3 L68.8,61.2 L69.0,61.0 L69.2,60.9 L69.4,60.8 L69.7,60.6 L69.9,60.5 L70.1,60.4 L70.3,60.2 L70.5,60.1 L70.8,60.0 L71.0,59.8 L71.2,59.7 L71.4,59.6 L71.7,59.5 L71.9,59.3 L72.1,59.2 L72.3,59.1 L72.5,59.0 L72.8,58.8 L73.0,58.7 L73.2,58.6 L73.4,58.5 L73.6,58.4 L73.9,58.2 L74.1,58.1 L74.3,58.0 L74.5,57.9 L74.8,57.8 L75.0,57.7 L75.2,57.6 L75.4,57.4 L75.6,57.3 L75.9,57.2 L76.1,57.1 L76.3,57.0 L76.5,56.9 L76.8,56.8 L77.0,56.7 L77.2,56.6 L77.4,56.4 L77.6,56.3 L77.9,56.2 L78.1,56.1 L78.3,56.0 L78.5,55.9 L78.7,55.8 L79.0,55.7 L79.2,55.6 L79.4,55.5 L79.6,55.4 L79.9,55.3 L80.1,55.2 L80.3,55.1 L80.5,55.0 L80.7,54.9 L81.0,54.8 L81.2,54.7 L81.4,54.6 L81.6,54.5 L81.8,54.4 L82.1,54.3 L82.3,54.2 L82.5,54.1 L82.7,54.0 L83.0,53.9 L83.2,53.8 L83.4,53.7 L83.6,53.6 L83.8,53.5 L84.1,53.4 L84.3,53.3 L84.5,53.2 L84.7,53.1 L85.0,53.0 L85.2,53.0 L85.4,52.9 L85.6,52.8 L85.8,52.7 L86.1,52.6 L86.3,52.5 L86.5,52.4 L86.7,52.3 L86.9,52.2 L87.2,52.1 L87.4,52.0 L87.6,52.0 L87.8,51.9 L88.1,51.8 L88.3,51.7 L88.5,51.6 L88.7,51.5 L88.9,51.4 L89.2,51.3 L89.4,51.3 L89.6,51.2 L89.8,51.1 L90.1,51.0 L90.3,50.9 L90.5,50.8 L90.7,50.7 L90.9,50.7 L91.2,50.6 L91.4,50.5 L91.6,50.4 L91.8,50.3 L92.0,50.2 L92.3,50.1 L92.5,50.1 L92.7,50.0 L92.9,49.9 L93.2,49.8 L93.4,49.7 L93.6,49.6 L93.8,49.6 L94.0,49.5 L94.3,49.4 L94.5,49.3 L94.7,49.2 L94.9,49.2 L95.2,49.1 L95.4,49.0 L95.6,48.9 L95.8,48.8 L96.0,48.8 L96.3,48.7 L96.5,48.6 L96.7,48.5 L96.9,48.4 L97.1,48.4 L97.4,48.3 L97.6,48.2 L97.8,48.1 L98.0,48.1 L98.3,48.0 L98.5,47.9 L98.7,47.8 L98.9,47.7 L99.1,47.7 L99.4,47.6 L99.6,47.5 L99.8,47.4 L100.0,47.4 L100.2,47.3 L100.5,47.2 L100.7,47.1 L100.9,47.1 L101.1,47.0 L101.4,46.9 L101.6,46.8 L101.8,46.8 L102.0,46.7 L102.2,46.6 L102.5,46.5 L102.7,46.5 L102.9,46.4 L103.1,46.3 L103.4,46.2 L103.6,46.2 L103.8,46.1 L104.0,46.0 L104.2,46.0 L104.5,45.9 L104.7,45.8 L104.9,45.7 L105.1,45.7 L105.3,45.6 L105.6,45.5 L105.8,45.5 L106.0,45.4 L106.2,45.3 L106.5,45.2 L106.7,45.2 L106.9,45.1 L107.1,45.0 L107.3,45.0 L107.6,44.9 L107.8,44.8 L108.0,44.7 L108.2,44.7 L108.5,44.6 L108.7,44.5 L108.9,44.5 L109.1,44.4 L109.3,44.3 L109.6,44.3 L109.8,44.2 L110.0,44.1 L110.2,44.1 L110.4,44.0 L110.7,43.9 L110.9,43.9 L111.1,43.8 L111.3,43.7 L111.6,43.6 L111.8,43.6 L112.0,43.5 L112.2,43.4 L112.4,43.4 L112.7,43.3 L112.9,43.2 L113.1,43.2 L113.3,43.1 L113.5,43.0 L113.8,43.0 L114.0,42.9 L114.2,42.8 L114.4,42.8 L114.7,42.7 L114.9,42.6 L115.1,42.6 L115.3,42.5 L115.5,42.5 L115.8,42.4 L116.0,42.3 L116.2,42.3 L116.4,42.2 L116.7,42.1 L116.9,42.1 L117.1,42.0 L117.3,41.9 L117.5,41.9 L117.8,41.8 L118.0,41.7 L118.2,41.7 L118.4,41.6 L118.6,41.5 L118.9,41.5 L119.1,41.4 L119.3,41.4 L119.5,41.3 L119.8,41.2 L120.0,41.2 L120.2,41.1 L120.4,41.0 L120.6,41.0 L120.9,40.9 L121.1,40.9 L121.3,40.8 L121.5,40.7 L121.8,40.7 L122.0,40.6 L122.2,40.5 L122.4,40.5 L122.6,40.4 L122.9,40.4 L123.1,40.3 L123.3,40.2 L123.5,40.2 L123.7,40.1 L124.0,40.0 L124.2,40.0 L124.4,39.9 L124.6,39.9 L124.9,39.8 L125.1,39.7 L125.3,39.7 L125.5,39.6 L125.7,39.6 L126.0,39.5 L126.2,39.4 L126.4,39.4 L126.6,39.3 L126.8,39.3 L127.1,39.2 L127.3,39.1 L127.5,39.1 L127.7,39.0 L128.0,39.0 L128.2,38.9 L128.4,38.8 L128.6,38.8 L128.8,38.7 L129.1,38.7 L129.3,38.6 L129.5,38.5 L129.7,38.5 L130.0,38.4 L130.2,38.4 L130.4,38.3 L130.6,38.3 L130.8,38.2 L131.1,38.1 L131.3,38.1 L131.5,38.0 L131.7,38.0 L131.9,37.9 L132.2,37.8 L132.4,37.8 L132.6,37.7 L132.8,37.7 L133.1,37.6 L133.3,37.6 L133.5,37.5 L133.7,37.4 L133.9,37.4 L134.2,37.3 L134.4,37.3 L134.6,37.2 L134.8,37.2 L135.1,37.1 L135.3,37.0 L135.5,37.0 L135.7,36.9 L135.9,36.9 L136.2,36.8 L136.4,36.8 L136.6,36.7 L136.8,36.7 L137.0,36.6 L137.3,36.5 L137.5,36.5 L137.7,36.4 L137.9,36.4 L138.2,36.3 L138.4,36.3 L138.6,36.2 L138.8,36.1 L139.0,36.1 L139.3,36.0 L139.5,36.0 L139.7,35.9 L139.9,35.9 L140.1,35.8 L140.4,35.8 L140.6,35.7 L140.8,35.7 L141.0,35.6 L141.3,35.5 L141.5,35.5 L141.7,35.4 L141.9,35.4 L142.1,35.3 L142.4,35.3 L142.6,35.2 L142.8,35.2 L143.0,35.1 L143.3,35.1 L143.5,35.0 L143.7,34.9 L143.9,34.9 L144.1,34.8 L144.4,34.8 L144.6,34.7 L144.8,34.7 L145.0,34.6 L145.2,34.6 L145.5,34.5 L145.7,34.5 L145.9,34.4 L146.1,34.4 L146.4,34.3 L146.6,34.2 L146.8,34.2 L147.0,34.1 L147.2,34.1 L147.5,34.0 L147.7,34.0 L147.9,33.9 L148.1,33.9 L148.3,33.8 L148.6,33.8 L148.8,33.7 L149.0,33.7 L149.2,33.6 L149.5,33.6 L149.7,33.5 L149.9,33.5 L150.1,33.4 L150.3,33.4 L150.6,33.3 L150.8,33.3 L151.0,33.2 L151.2,33.1 L151.5,33.1 L151.7,33.0 L151.9,33.0 L152.1,32.9 L152.3,32.9 L152.6,32.8 L152.8,32.8 L153.0,32.7 L153.2,32.7 L153.4,32.6 L153.7,32.6 L153.9,32.5 L154.1,32.5 L154.3,32.4 L154.6,32.4 L154.8,32.3 L155.0,32.3\" clip-path=\"url(#b10x9)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/></svg><svg class=\"figsvg\" viewBox=\"0 0 165 150\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"82.5\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Graph B</text><line x1=\"22.0\" y1=\"134.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"38.6\" y1=\"134.0\" x2=\"38.6\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"55.2\" y1=\"134.0\" x2=\"55.2\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"71.9\" y1=\"134.0\" x2=\"71.9\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"88.5\" y1=\"134.0\" x2=\"88.5\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"105.1\" y1=\"134.0\" x2=\"105.1\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"121.8\" y1=\"134.0\" x2=\"121.8\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"138.4\" y1=\"134.0\" x2=\"138.4\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"155.0\" y1=\"134.0\" x2=\"155.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"134.0\" x2=\"155.0\" y2=\"134.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"115.3\" x2=\"155.0\" y2=\"115.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"96.7\" x2=\"155.0\" y2=\"96.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"78.0\" x2=\"155.0\" y2=\"78.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"59.3\" x2=\"155.0\" y2=\"59.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"40.7\" x2=\"155.0\" y2=\"40.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"155.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"78.0\" x2=\"155.0\" y2=\"78.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"71.9\" y1=\"134.0\" x2=\"71.9\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"38.6\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"105.1\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"138.4\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"67.9\" y=\"115.3\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"67.9\" y=\"40.7\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"151.0\" y=\"70.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"79.9\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x10\"><rect x=\"22.0\" y=\"22.0\" width=\"133.0\" height=\"112.0\"/></clipPath><path d=\"M88.5,78.0 L88.7,75.8 L88.9,75.0 L89.2,74.3 L89.4,73.7 L89.6,73.2 L89.8,72.7 L90.1,72.3 L90.3,71.9 L90.5,71.5 L90.7,71.2 L90.9,70.9 L91.2,70.5 L91.4,70.2 L91.6,69.9 L91.8,69.7 L92.0,69.4 L92.3,69.1 L92.5,68.9 L92.7,68.6 L92.9,68.4 L93.2,68.1 L93.4,67.9 L93.6,67.7 L93.8,67.4 L94.0,67.2 L94.3,67.0 L94.5,66.8 L94.7,66.6 L94.9,66.4 L95.2,66.2 L95.4,66.0 L95.6,65.8 L95.8,65.6 L96.0,65.4 L96.3,65.2 L96.5,65.1 L96.7,64.9 L96.9,64.7 L97.1,64.5 L97.4,64.4 L97.6,64.2 L97.8,64.0 L98.0,63.9 L98.3,63.7 L98.5,63.5 L98.7,63.4 L98.9,63.2 L99.1,63.1 L99.4,62.9 L99.6,62.8 L99.8,62.6 L100.0,62.5 L100.2,62.3 L100.5,62.2 L100.7,62.0 L100.9,61.9 L101.1,61.7 L101.4,61.6 L101.6,61.4 L101.8,61.3 L102.0,61.2 L102.2,61.0 L102.5,60.9 L102.7,60.8 L102.9,60.6 L103.1,60.5 L103.4,60.4 L103.6,60.2 L103.8,60.1 L104.0,60.0 L104.2,59.8 L104.5,59.7 L104.7,59.6 L104.9,59.5 L105.1,59.3 L105.3,59.2 L105.6,59.1 L105.8,59.0 L106.0,58.8 L106.2,58.7 L106.5,58.6 L106.7,58.5 L106.9,58.4 L107.1,58.2 L107.3,58.1 L107.6,58.0 L107.8,57.9 L108.0,57.8 L108.2,57.7 L108.5,57.6 L108.7,57.4 L108.9,57.3 L109.1,57.2 L109.3,57.1 L109.6,57.0 L109.8,56.9 L110.0,56.8 L110.2,56.7 L110.4,56.6 L110.7,56.4 L110.9,56.3 L111.1,56.2 L111.3,56.1 L111.6,56.0 L111.8,55.9 L112.0,55.8 L112.2,55.7 L112.4,55.6 L112.7,55.5 L112.9,55.4 L113.1,55.3 L113.3,55.2 L113.5,55.1 L113.8,55.0 L114.0,54.9 L114.2,54.8 L114.4,54.7 L114.7,54.6 L114.9,54.5 L115.1,54.4 L115.3,54.3 L115.5,54.2 L115.8,54.1 L116.0,54.0 L116.2,53.9 L116.4,53.8 L116.7,53.7 L116.9,53.6 L117.1,53.5 L117.3,53.4 L117.5,53.3 L117.8,53.2 L118.0,53.1 L118.2,53.0 L118.4,53.0 L118.6,52.9 L118.9,52.8 L119.1,52.7 L119.3,52.6 L119.5,52.5 L119.8,52.4 L120.0,52.3 L120.2,52.2 L120.4,52.1 L120.6,52.0 L120.9,52.0 L121.1,51.9 L121.3,51.8 L121.5,51.7 L121.8,51.6 L122.0,51.5 L122.2,51.4 L122.4,51.3 L122.6,51.3 L122.9,51.2 L123.1,51.1 L123.3,51.0 L123.5,50.9 L123.7,50.8 L124.0,50.7 L124.2,50.7 L124.4,50.6 L124.6,50.5 L124.9,50.4 L125.1,50.3 L125.3,50.2 L125.5,50.1 L125.7,50.1 L126.0,50.0 L126.2,49.9 L126.4,49.8 L126.6,49.7 L126.8,49.6 L127.1,49.6 L127.3,49.5 L127.5,49.4 L127.7,49.3 L128.0,49.2 L128.2,49.2 L128.4,49.1 L128.6,49.0 L128.8,48.9 L129.1,48.8 L129.3,48.8 L129.5,48.7 L129.7,48.6 L130.0,48.5 L130.2,48.4 L130.4,48.4 L130.6,48.3 L130.8,48.2 L131.1,48.1 L131.3,48.1 L131.5,48.0 L131.7,47.9 L131.9,47.8 L132.2,47.7 L132.4,47.7 L132.6,47.6 L132.8,47.5 L133.1,47.4 L133.3,47.4 L133.5,47.3 L133.7,47.2 L133.9,47.1 L134.2,47.1 L134.4,47.0 L134.6,46.9 L134.8,46.8 L135.1,46.8 L135.3,46.7 L135.5,46.6 L135.7,46.5 L135.9,46.5 L136.2,46.4 L136.4,46.3 L136.6,46.2 L136.8,46.2 L137.0,46.1 L137.3,46.0 L137.5,46.0 L137.7,45.9 L137.9,45.8 L138.2,45.7 L138.4,45.7 L138.6,45.6 L138.8,45.5 L139.0,45.5 L139.3,45.4 L139.5,45.3 L139.7,45.2 L139.9,45.2 L140.1,45.1 L140.4,45.0 L140.6,45.0 L140.8,44.9 L141.0,44.8 L141.3,44.7 L141.5,44.7 L141.7,44.6 L141.9,44.5 L142.1,44.5 L142.4,44.4 L142.6,44.3 L142.8,44.3 L143.0,44.2 L143.3,44.1 L143.5,44.1 L143.7,44.0 L143.9,43.9 L144.1,43.9 L144.4,43.8 L144.6,43.7 L144.8,43.6 L145.0,43.6 L145.2,43.5 L145.5,43.4 L145.7,43.4 L145.9,43.3 L146.1,43.2 L146.4,43.2 L146.6,43.1 L146.8,43.0 L147.0,43.0 L147.2,42.9 L147.5,42.8 L147.7,42.8 L147.9,42.7 L148.1,42.6 L148.3,42.6 L148.6,42.5 L148.8,42.5 L149.0,42.4 L149.2,42.3 L149.5,42.3 L149.7,42.2 L149.9,42.1 L150.1,42.1 L150.3,42.0 L150.6,41.9 L150.8,41.9 L151.0,41.8 L151.2,41.7 L151.5,41.7 L151.7,41.6 L151.9,41.5 L152.1,41.5 L152.3,41.4 L152.6,41.4 L152.8,41.3 L153.0,41.2 L153.2,41.2 L153.4,41.1 L153.7,41.0 L153.9,41.0 L154.1,40.9 L154.3,40.9 L154.6,40.8 L154.8,40.7 L155.0,40.7\" clip-path=\"url(#b10x10)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/></svg><svg class=\"figsvg\" viewBox=\"0 0 165 150\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"82.5\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Graph C</text><line x1=\"22.0\" y1=\"134.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"38.6\" y1=\"134.0\" x2=\"38.6\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"55.2\" y1=\"134.0\" x2=\"55.2\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"71.9\" y1=\"134.0\" x2=\"71.9\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"88.5\" y1=\"134.0\" x2=\"88.5\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"105.1\" y1=\"134.0\" x2=\"105.1\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"121.8\" y1=\"134.0\" x2=\"121.8\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"138.4\" y1=\"134.0\" x2=\"138.4\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"155.0\" y1=\"134.0\" x2=\"155.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"134.0\" x2=\"155.0\" y2=\"134.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"115.3\" x2=\"155.0\" y2=\"115.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"96.7\" x2=\"155.0\" y2=\"96.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"78.0\" x2=\"155.0\" y2=\"78.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"59.3\" x2=\"155.0\" y2=\"59.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"40.7\" x2=\"155.0\" y2=\"40.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"155.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"78.0\" x2=\"155.0\" y2=\"78.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"71.9\" y1=\"134.0\" x2=\"71.9\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"38.6\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"105.1\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"138.4\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"67.9\" y=\"115.3\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"67.9\" y=\"40.7\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"151.0\" y=\"70.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"79.9\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x11\"><rect x=\"22.0\" y=\"22.0\" width=\"133.0\" height=\"112.0\"/></clipPath><path d=\"M55.2,78.0 L55.5,80.2 L55.7,81.0 L55.9,81.7 L56.1,82.3 L56.4,82.8 L56.6,83.3 L56.8,83.7 L57.0,84.1 L57.2,84.5 L57.5,84.8 L57.7,85.1 L57.9,85.5 L58.1,85.8 L58.4,86.1 L58.6,86.3 L58.8,86.6 L59.0,86.9 L59.2,87.1 L59.5,87.4 L59.7,87.6 L59.9,87.9 L60.1,88.1 L60.3,88.3 L60.6,88.6 L60.8,88.8 L61.0,89.0 L61.2,89.2 L61.5,89.4 L61.7,89.6 L61.9,89.8 L62.1,90.0 L62.3,90.2 L62.6,90.4 L62.8,90.6 L63.0,90.8 L63.2,90.9 L63.5,91.1 L63.7,91.3 L63.9,91.5 L64.1,91.6 L64.3,91.8 L64.6,92.0 L64.8,92.1 L65.0,92.3 L65.2,92.5 L65.4,92.6 L65.7,92.8 L65.9,92.9 L66.1,93.1 L66.3,93.2 L66.6,93.4 L66.8,93.5 L67.0,93.7 L67.2,93.8 L67.4,94.0 L67.7,94.1 L67.9,94.3 L68.1,94.4 L68.3,94.6 L68.5,94.7 L68.8,94.8 L69.0,95.0 L69.2,95.1 L69.4,95.2 L69.7,95.4 L69.9,95.5 L70.1,95.6 L70.3,95.8 L70.5,95.9 L70.8,96.0 L71.0,96.2 L71.2,96.3 L71.4,96.4 L71.7,96.5 L71.9,96.7 L72.1,96.8 L72.3,96.9 L72.5,97.0 L72.8,97.2 L73.0,97.3 L73.2,97.4 L73.4,97.5 L73.6,97.6 L73.9,97.8 L74.1,97.9 L74.3,98.0 L74.5,98.1 L74.8,98.2 L75.0,98.3 L75.2,98.4 L75.4,98.6 L75.6,98.7 L75.9,98.8 L76.1,98.9 L76.3,99.0 L76.5,99.1 L76.8,99.2 L77.0,99.3 L77.2,99.4 L77.4,99.6 L77.6,99.7 L77.9,99.8 L78.1,99.9 L78.3,100.0 L78.5,100.1 L78.7,100.2 L79.0,100.3 L79.2,100.4 L79.4,100.5 L79.6,100.6 L79.9,100.7 L80.1,100.8 L80.3,100.9 L80.5,101.0 L80.7,101.1 L81.0,101.2 L81.2,101.3 L81.4,101.4 L81.6,101.5 L81.8,101.6 L82.1,101.7 L82.3,101.8 L82.5,101.9 L82.7,102.0 L83.0,102.1 L83.2,102.2 L83.4,102.3 L83.6,102.4 L83.8,102.5 L84.1,102.6 L84.3,102.7 L84.5,102.8 L84.7,102.9 L85.0,103.0 L85.2,103.0 L85.4,103.1 L85.6,103.2 L85.8,103.3 L86.1,103.4 L86.3,103.5 L86.5,103.6 L86.7,103.7 L86.9,103.8 L87.2,103.9 L87.4,104.0 L87.6,104.0 L87.8,104.1 L88.1,104.2 L88.3,104.3 L88.5,104.4 L88.7,104.5 L88.9,104.6 L89.2,104.7 L89.4,104.7 L89.6,104.8 L89.8,104.9 L90.1,105.0 L90.3,105.1 L90.5,105.2 L90.7,105.3 L90.9,105.3 L91.2,105.4 L91.4,105.5 L91.6,105.6 L91.8,105.7 L92.0,105.8 L92.3,105.9 L92.5,105.9 L92.7,106.0 L92.9,106.1 L93.2,106.2 L93.4,106.3 L93.6,106.4 L93.8,106.4 L94.0,106.5 L94.3,106.6 L94.5,106.7 L94.7,106.8 L94.9,106.8 L95.2,106.9 L95.4,107.0 L95.6,107.1 L95.8,107.2 L96.0,107.2 L96.3,107.3 L96.5,107.4 L96.7,107.5 L96.9,107.6 L97.1,107.6 L97.4,107.7 L97.6,107.8 L97.8,107.9 L98.0,107.9 L98.3,108.0 L98.5,108.1 L98.7,108.2 L98.9,108.3 L99.1,108.3 L99.4,108.4 L99.6,108.5 L99.8,108.6 L100.0,108.6 L100.2,108.7 L100.5,108.8 L100.7,108.9 L100.9,108.9 L101.1,109.0 L101.4,109.1 L101.6,109.2 L101.8,109.2 L102.0,109.3 L102.2,109.4 L102.5,109.5 L102.7,109.5 L102.9,109.6 L103.1,109.7 L103.4,109.8 L103.6,109.8 L103.8,109.9 L104.0,110.0 L104.2,110.0 L104.5,110.1 L104.7,110.2 L104.9,110.3 L105.1,110.3 L105.3,110.4 L105.6,110.5 L105.8,110.5 L106.0,110.6 L106.2,110.7 L106.5,110.8 L106.7,110.8 L106.9,110.9 L107.1,111.0 L107.3,111.0 L107.6,111.1 L107.8,111.2 L108.0,111.3 L108.2,111.3 L108.5,111.4 L108.7,111.5 L108.9,111.5 L109.1,111.6 L109.3,111.7 L109.6,111.7 L109.8,111.8 L110.0,111.9 L110.2,111.9 L110.4,112.0 L110.7,112.1 L110.9,112.1 L111.1,112.2 L111.3,112.3 L111.6,112.4 L111.8,112.4 L112.0,112.5 L112.2,112.6 L112.4,112.6 L112.7,112.7 L112.9,112.8 L113.1,112.8 L113.3,112.9 L113.5,113.0 L113.8,113.0 L114.0,113.1 L114.2,113.2 L114.4,113.2 L114.7,113.3 L114.9,113.4 L115.1,113.4 L115.3,113.5 L115.5,113.5 L115.8,113.6 L116.0,113.7 L116.2,113.7 L116.4,113.8 L116.7,113.9 L116.9,113.9 L117.1,114.0 L117.3,114.1 L117.5,114.1 L117.8,114.2 L118.0,114.3 L118.2,114.3 L118.4,114.4 L118.6,114.5 L118.9,114.5 L119.1,114.6 L119.3,114.6 L119.5,114.7 L119.8,114.8 L120.0,114.8 L120.2,114.9 L120.4,115.0 L120.6,115.0 L120.9,115.1 L121.1,115.1 L121.3,115.2 L121.5,115.3 L121.8,115.3 L122.0,115.4 L122.2,115.5 L122.4,115.5 L122.6,115.6 L122.9,115.6 L123.1,115.7 L123.3,115.8 L123.5,115.8 L123.7,115.9 L124.0,116.0 L124.2,116.0 L124.4,116.1 L124.6,116.1 L124.9,116.2 L125.1,116.3 L125.3,116.3 L125.5,116.4 L125.7,116.4 L126.0,116.5 L126.2,116.6 L126.4,116.6 L126.6,116.7 L126.8,116.7 L127.1,116.8 L127.3,116.9 L127.5,116.9 L127.7,117.0 L128.0,117.0 L128.2,117.1 L128.4,117.2 L128.6,117.2 L128.8,117.3 L129.1,117.3 L129.3,117.4 L129.5,117.5 L129.7,117.5 L130.0,117.6 L130.2,117.6 L130.4,117.7 L130.6,117.7 L130.8,117.8 L131.1,117.9 L131.3,117.9 L131.5,118.0 L131.7,118.0 L131.9,118.1 L132.2,118.2 L132.4,118.2 L132.6,118.3 L132.8,118.3 L133.1,118.4 L133.3,118.4 L133.5,118.5 L133.7,118.6 L133.9,118.6 L134.2,118.7 L134.4,118.7 L134.6,118.8 L134.8,118.8 L135.1,118.9 L135.3,119.0 L135.5,119.0 L135.7,119.1 L135.9,119.1 L136.2,119.2 L136.4,119.2 L136.6,119.3 L136.8,119.3 L137.0,119.4 L137.3,119.5 L137.5,119.5 L137.7,119.6 L137.9,119.6 L138.2,119.7 L138.4,119.7 L138.6,119.8 L138.8,119.9 L139.0,119.9 L139.3,120.0 L139.5,120.0 L139.7,120.1 L139.9,120.1 L140.1,120.2 L140.4,120.2 L140.6,120.3 L140.8,120.3 L141.0,120.4 L141.3,120.5 L141.5,120.5 L141.7,120.6 L141.9,120.6 L142.1,120.7 L142.4,120.7 L142.6,120.8 L142.8,120.8 L143.0,120.9 L143.3,120.9 L143.5,121.0 L143.7,121.1 L143.9,121.1 L144.1,121.2 L144.4,121.2 L144.6,121.3 L144.8,121.3 L145.0,121.4 L145.2,121.4 L145.5,121.5 L145.7,121.5 L145.9,121.6 L146.1,121.6 L146.4,121.7 L146.6,121.8 L146.8,121.8 L147.0,121.9 L147.2,121.9 L147.5,122.0 L147.7,122.0 L147.9,122.1 L148.1,122.1 L148.3,122.2 L148.6,122.2 L148.8,122.3 L149.0,122.3 L149.2,122.4 L149.5,122.4 L149.7,122.5 L149.9,122.5 L150.1,122.6 L150.3,122.6 L150.6,122.7 L150.8,122.7 L151.0,122.8 L151.2,122.9 L151.5,122.9 L151.7,123.0 L151.9,123.0 L152.1,123.1 L152.3,123.1 L152.6,123.2 L152.8,123.2 L153.0,123.3 L153.2,123.3 L153.4,123.4 L153.7,123.4 L153.9,123.5 L154.1,123.5 L154.3,123.6 L154.6,123.6 L154.8,123.7 L155.0,123.7\" clip-path=\"url(#b10x11)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/></svg><svg class=\"figsvg\" viewBox=\"0 0 165 150\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"82.5\" y=\"11.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Graph D</text><line x1=\"22.0\" y1=\"134.0\" x2=\"22.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"38.6\" y1=\"134.0\" x2=\"38.6\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"55.2\" y1=\"134.0\" x2=\"55.2\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"71.9\" y1=\"134.0\" x2=\"71.9\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"88.5\" y1=\"134.0\" x2=\"88.5\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"105.1\" y1=\"134.0\" x2=\"105.1\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"121.8\" y1=\"134.0\" x2=\"121.8\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"138.4\" y1=\"134.0\" x2=\"138.4\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"155.0\" y1=\"134.0\" x2=\"155.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"134.0\" x2=\"155.0\" y2=\"134.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"115.3\" x2=\"155.0\" y2=\"115.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"96.7\" x2=\"155.0\" y2=\"96.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"78.0\" x2=\"155.0\" y2=\"78.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"59.3\" x2=\"155.0\" y2=\"59.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"40.7\" x2=\"155.0\" y2=\"40.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"22.0\" x2=\"155.0\" y2=\"22.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"78.0\" x2=\"155.0\" y2=\"78.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"71.9\" y1=\"134.0\" x2=\"71.9\" y2=\"22.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"38.6\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"105.1\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"138.4\" y=\"87.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"67.9\" y=\"115.3\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"67.9\" y=\"40.7\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"151.0\" y=\"70.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"79.9\" y=\"28.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x12\"><rect x=\"22.0\" y=\"22.0\" width=\"133.0\" height=\"112.0\"/></clipPath><path d=\"M88.5,78.0 L88.7,80.2 L88.9,81.0 L89.2,81.7 L89.4,82.3 L89.6,82.8 L89.8,83.3 L90.1,83.7 L90.3,84.1 L90.5,84.5 L90.7,84.8 L90.9,85.1 L91.2,85.5 L91.4,85.8 L91.6,86.1 L91.8,86.3 L92.0,86.6 L92.3,86.9 L92.5,87.1 L92.7,87.4 L92.9,87.6 L93.2,87.9 L93.4,88.1 L93.6,88.3 L93.8,88.6 L94.0,88.8 L94.3,89.0 L94.5,89.2 L94.7,89.4 L94.9,89.6 L95.2,89.8 L95.4,90.0 L95.6,90.2 L95.8,90.4 L96.0,90.6 L96.3,90.8 L96.5,90.9 L96.7,91.1 L96.9,91.3 L97.1,91.5 L97.4,91.6 L97.6,91.8 L97.8,92.0 L98.0,92.1 L98.3,92.3 L98.5,92.5 L98.7,92.6 L98.9,92.8 L99.1,92.9 L99.4,93.1 L99.6,93.2 L99.8,93.4 L100.0,93.5 L100.2,93.7 L100.5,93.8 L100.7,94.0 L100.9,94.1 L101.1,94.3 L101.4,94.4 L101.6,94.6 L101.8,94.7 L102.0,94.8 L102.2,95.0 L102.5,95.1 L102.7,95.2 L102.9,95.4 L103.1,95.5 L103.4,95.6 L103.6,95.8 L103.8,95.9 L104.0,96.0 L104.2,96.2 L104.5,96.3 L104.7,96.4 L104.9,96.5 L105.1,96.7 L105.3,96.8 L105.6,96.9 L105.8,97.0 L106.0,97.2 L106.2,97.3 L106.5,97.4 L106.7,97.5 L106.9,97.6 L107.1,97.8 L107.3,97.9 L107.6,98.0 L107.8,98.1 L108.0,98.2 L108.2,98.3 L108.5,98.4 L108.7,98.6 L108.9,98.7 L109.1,98.8 L109.3,98.9 L109.6,99.0 L109.8,99.1 L110.0,99.2 L110.2,99.3 L110.4,99.4 L110.7,99.6 L110.9,99.7 L111.1,99.8 L111.3,99.9 L111.6,100.0 L111.8,100.1 L112.0,100.2 L112.2,100.3 L112.4,100.4 L112.7,100.5 L112.9,100.6 L113.1,100.7 L113.3,100.8 L113.5,100.9 L113.8,101.0 L114.0,101.1 L114.2,101.2 L114.4,101.3 L114.7,101.4 L114.9,101.5 L115.1,101.6 L115.3,101.7 L115.5,101.8 L115.8,101.9 L116.0,102.0 L116.2,102.1 L116.4,102.2 L116.7,102.3 L116.9,102.4 L117.1,102.5 L117.3,102.6 L117.5,102.7 L117.8,102.8 L118.0,102.9 L118.2,103.0 L118.4,103.0 L118.6,103.1 L118.9,103.2 L119.1,103.3 L119.3,103.4 L119.5,103.5 L119.8,103.6 L120.0,103.7 L120.2,103.8 L120.4,103.9 L120.6,104.0 L120.9,104.0 L121.1,104.1 L121.3,104.2 L121.5,104.3 L121.8,104.4 L122.0,104.5 L122.2,104.6 L122.4,104.7 L122.6,104.7 L122.9,104.8 L123.1,104.9 L123.3,105.0 L123.5,105.1 L123.7,105.2 L124.0,105.3 L124.2,105.3 L124.4,105.4 L124.6,105.5 L124.9,105.6 L125.1,105.7 L125.3,105.8 L125.5,105.9 L125.7,105.9 L126.0,106.0 L126.2,106.1 L126.4,106.2 L126.6,106.3 L126.8,106.4 L127.1,106.4 L127.3,106.5 L127.5,106.6 L127.7,106.7 L128.0,106.8 L128.2,106.8 L128.4,106.9 L128.6,107.0 L128.8,107.1 L129.1,107.2 L129.3,107.2 L129.5,107.3 L129.7,107.4 L130.0,107.5 L130.2,107.6 L130.4,107.6 L130.6,107.7 L130.8,107.8 L131.1,107.9 L131.3,107.9 L131.5,108.0 L131.7,108.1 L131.9,108.2 L132.2,108.3 L132.4,108.3 L132.6,108.4 L132.8,108.5 L133.1,108.6 L133.3,108.6 L133.5,108.7 L133.7,108.8 L133.9,108.9 L134.2,108.9 L134.4,109.0 L134.6,109.1 L134.8,109.2 L135.1,109.2 L135.3,109.3 L135.5,109.4 L135.7,109.5 L135.9,109.5 L136.2,109.6 L136.4,109.7 L136.6,109.8 L136.8,109.8 L137.0,109.9 L137.3,110.0 L137.5,110.0 L137.7,110.1 L137.9,110.2 L138.2,110.3 L138.4,110.3 L138.6,110.4 L138.8,110.5 L139.0,110.5 L139.3,110.6 L139.5,110.7 L139.7,110.8 L139.9,110.8 L140.1,110.9 L140.4,111.0 L140.6,111.0 L140.8,111.1 L141.0,111.2 L141.3,111.3 L141.5,111.3 L141.7,111.4 L141.9,111.5 L142.1,111.5 L142.4,111.6 L142.6,111.7 L142.8,111.7 L143.0,111.8 L143.3,111.9 L143.5,111.9 L143.7,112.0 L143.9,112.1 L144.1,112.1 L144.4,112.2 L144.6,112.3 L144.8,112.4 L145.0,112.4 L145.2,112.5 L145.5,112.6 L145.7,112.6 L145.9,112.7 L146.1,112.8 L146.4,112.8 L146.6,112.9 L146.8,113.0 L147.0,113.0 L147.2,113.1 L147.5,113.2 L147.7,113.2 L147.9,113.3 L148.1,113.4 L148.3,113.4 L148.6,113.5 L148.8,113.5 L149.0,113.6 L149.2,113.7 L149.5,113.7 L149.7,113.8 L149.9,113.9 L150.1,113.9 L150.3,114.0 L150.6,114.1 L150.8,114.1 L151.0,114.2 L151.2,114.3 L151.5,114.3 L151.7,114.4 L151.9,114.5 L152.1,114.5 L152.3,114.6 L152.6,114.6 L152.8,114.7 L153.0,114.8 L153.2,114.8 L153.4,114.9 L153.7,115.0 L153.9,115.0 L154.1,115.1 L154.3,115.1 L154.6,115.2 L154.8,115.3 L155.0,115.3\" clip-path=\"url(#b10x12)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/></svg></div>"}]}, {"id": "s2", "label": "10.2 Graphing Cube Root Functions", "sub": "I can graph cube root functions, find their point of symmetry and intercepts, describe transformations of f(x) = ∛x and compare them with other functions.", "slides": [{"kind": "mcq", "text": "f(x) = ∛x. What is f(−8)?", "opts": ["−{8/3}", "2", "Not a real number", "−2"], "correct": 3, "tag": "", "sol": "(−2)³ = −8, so ∛(−8) = −2. Unlike square roots, cube roots of negative numbers are real. ({8/3} comes from dividing by 3 instead of taking the cube root.)"}, {"kind": "blank", "p": "Complete the table for g(x) = ∛x + 1.", "tag": "", "marks": "", "flat": [{"t": "g(−8) = __B1__", "a": {"B1": "-1"}}, {"t": "g(0) = __B1__", "a": {"B1": "1"}}, {"t": "g(27) = __B1__", "a": {"B1": "4"}}], "sol": "∛(−8) + 1 = −2 + 1 = −1.\n∛0 + 1 = 1.\n∛27 + 1 = 3 + 1 = 4."}, {"kind": "mcq", "text": "What are the domain and range of f(x) = ∛(x − 2)?", "opts": ["Domain: x ≥ 2; range: y ≥ 0", "Domain: all real numbers; range: all real numbers", "Domain: all real numbers; range: y ≥ 0", "Domain: x ≥ 2; range: all real numbers"], "correct": 1, "tag": "", "sol": "Every real number has a cube root, so x − 2 can be negative: the domain is all real numbers. The outputs also take every real value. The translation does not change this.", "tools": ["desmos"], "desmos": ["y=\\sqrt[3]{x-2}"]}, {"kind": "blank", "p": "Look at g(x) = ∛(x + 4) − 3.", "tag": "", "marks": "", "flat": [{"t": "The point of symmetry is (__B1__, −3)", "a": {"B1": "-4"}}, {"t": "g(4) = __B1__", "a": {"B1": "-1"}}, {"t": "g(−12) = __B1__", "a": {"B1": "-5"}}], "sol": "g(x) = ∛(x − (−4)) + (−3), so h = −4 and k = −3.\n∛8 − 3 = 2 − 3 = −1.\n∛(−8) − 3 = −2 − 3 = −5.", "tools": ["desmos"], "desmos": ["y=\\sqrt[3]{x+4}-3"]}, {"kind": "mcq", "text": "Which function is shown in the graph?", "opts": ["y = ∛(x + 1) + 2", "y = ∛(x − 2) + 1", "y = ∛(x − 1) − 2", "y = ∛(x − 1) + 2"], "correct": 3, "tag": "", "sol": "The point of symmetry is (1, 2), so h = 1 and k = 2. Check: x = 9 gives ∛8 + 2 = 4 ✓ and x = −7 gives ∛(−8) + 2 = 0 ✓", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"22.0\" y1=\"214.0\" x2=\"22.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"36.9\" y1=\"214.0\" x2=\"36.9\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"51.8\" y1=\"214.0\" x2=\"51.8\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"66.7\" y1=\"214.0\" x2=\"66.7\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"81.6\" y1=\"214.0\" x2=\"81.6\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"96.4\" y1=\"214.0\" x2=\"96.4\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"111.3\" y1=\"214.0\" x2=\"111.3\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"126.2\" y1=\"214.0\" x2=\"126.2\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"141.1\" y1=\"214.0\" x2=\"141.1\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"156.0\" y1=\"214.0\" x2=\"156.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"170.9\" y1=\"214.0\" x2=\"170.9\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"185.8\" y1=\"214.0\" x2=\"185.8\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"200.7\" y1=\"214.0\" x2=\"200.7\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"215.6\" y1=\"214.0\" x2=\"215.6\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"230.4\" y1=\"214.0\" x2=\"230.4\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"245.3\" y1=\"214.0\" x2=\"245.3\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"260.2\" y1=\"214.0\" x2=\"260.2\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"275.1\" y1=\"214.0\" x2=\"275.1\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"290.0\" y1=\"214.0\" x2=\"290.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"214.0\" x2=\"290.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"179.7\" x2=\"290.0\" y2=\"179.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"145.3\" x2=\"290.0\" y2=\"145.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"111.0\" x2=\"290.0\" y2=\"111.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"76.7\" x2=\"290.0\" y2=\"76.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"42.3\" x2=\"290.0\" y2=\"42.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"8.0\" x2=\"290.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"179.7\" x2=\"290.0\" y2=\"179.7\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"141.1\" y1=\"214.0\" x2=\"141.1\" y2=\"8.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"22.0\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−8</text><text class=\"po\" x=\"51.8\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−6</text><text class=\"po\" x=\"81.6\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"111.3\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"170.9\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"200.7\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"230.4\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"260.2\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><text class=\"po\" x=\"290.0\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">10</text><text class=\"po\" x=\"137.1\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−1</text><text class=\"po\" x=\"137.1\" y=\"145.3\" text-anchor=\"end\" dominant-baseline=\"middle\">1</text><text class=\"po\" x=\"137.1\" y=\"111.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"137.1\" y=\"76.7\" text-anchor=\"end\" dominant-baseline=\"middle\">3</text><text class=\"po\" x=\"137.1\" y=\"42.3\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"137.1\" y=\"8.0\" text-anchor=\"end\" dominant-baseline=\"middle\">5</text><text class=\"po\" x=\"286.0\" y=\"171.7\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"149.1\" y=\"14.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x13\"><rect x=\"22.0\" y=\"8.0\" width=\"268.0\" height=\"206.0\"/></clipPath><path d=\"M22.0,182.4 L22.4,182.3 L22.9,182.3 L23.3,182.2 L23.8,182.1 L24.2,182.0 L24.7,181.9 L25.1,181.9 L25.6,181.8 L26.0,181.7 L26.5,181.6 L26.9,181.5 L27.4,181.5 L27.8,181.4 L28.3,181.3 L28.7,181.2 L29.1,181.1 L29.6,181.0 L30.0,181.0 L30.5,180.9 L30.9,180.8 L31.4,180.7 L31.8,180.6 L32.3,180.5 L32.7,180.5 L33.2,180.4 L33.6,180.3 L34.1,180.2 L34.5,180.1 L35.0,180.0 L35.4,180.0 L35.8,179.9 L36.3,179.8 L36.7,179.7 L37.2,179.6 L37.6,179.5 L38.1,179.4 L38.5,179.4 L39.0,179.3 L39.4,179.2 L39.9,179.1 L40.3,179.0 L40.8,178.9 L41.2,178.8 L41.7,178.7 L42.1,178.7 L42.5,178.6 L43.0,178.5 L43.4,178.4 L43.9,178.3 L44.3,178.2 L44.8,178.1 L45.2,178.0 L45.7,177.9 L46.1,177.8 L46.6,177.8 L47.0,177.7 L47.5,177.6 L47.9,177.5 L48.4,177.4 L48.8,177.3 L49.2,177.2 L49.7,177.1 L50.1,177.0 L50.6,176.9 L51.0,176.8 L51.5,176.7 L51.9,176.6 L52.4,176.6 L52.8,176.5 L53.3,176.4 L53.7,176.3 L54.2,176.2 L54.6,176.1 L55.1,176.0 L55.5,175.9 L55.9,175.8 L56.4,175.7 L56.8,175.6 L57.3,175.5 L57.7,175.4 L58.2,175.3 L58.6,175.2 L59.1,175.1 L59.5,175.0 L60.0,174.9 L60.4,174.8 L60.9,174.7 L61.3,174.6 L61.8,174.5 L62.2,174.4 L62.6,174.3 L63.1,174.2 L63.5,174.1 L64.0,174.0 L64.4,173.9 L64.9,173.8 L65.3,173.7 L65.8,173.6 L66.2,173.5 L66.7,173.4 L67.1,173.3 L67.6,173.2 L68.0,173.1 L68.5,173.0 L68.9,172.9 L69.3,172.8 L69.8,172.7 L70.2,172.5 L70.7,172.4 L71.1,172.3 L71.6,172.2 L72.0,172.1 L72.5,172.0 L72.9,171.9 L73.4,171.8 L73.8,171.7 L74.3,171.6 L74.7,171.5 L75.2,171.3 L75.6,171.2 L76.0,171.1 L76.5,171.0 L76.9,170.9 L77.4,170.8 L77.8,170.7 L78.3,170.6 L78.7,170.4 L79.2,170.3 L79.6,170.2 L80.1,170.1 L80.5,170.0 L81.0,169.9 L81.4,169.7 L81.9,169.6 L82.3,169.5 L82.7,169.4 L83.2,169.3 L83.6,169.2 L84.1,169.0 L84.5,168.9 L85.0,168.8 L85.4,168.7 L85.9,168.6 L86.3,168.4 L86.8,168.3 L87.2,168.2 L87.7,168.1 L88.1,167.9 L88.6,167.8 L89.0,167.7 L89.4,167.6 L89.9,167.4 L90.3,167.3 L90.8,167.2 L91.2,167.0 L91.7,166.9 L92.1,166.8 L92.6,166.7 L93.0,166.5 L93.5,166.4 L93.9,166.3 L94.4,166.1 L94.8,166.0 L95.3,165.9 L95.7,165.7 L96.1,165.6 L96.6,165.5 L97.0,165.3 L97.5,165.2 L97.9,165.0 L98.4,164.9 L98.8,164.8 L99.3,164.6 L99.7,164.5 L100.2,164.3 L100.6,164.2 L101.1,164.1 L101.5,163.9 L102.0,163.8 L102.4,163.6 L102.8,163.5 L103.3,163.3 L103.7,163.2 L104.2,163.0 L104.6,162.9 L105.1,162.7 L105.5,162.6 L106.0,162.4 L106.4,162.3 L106.9,162.1 L107.3,162.0 L107.8,161.8 L108.2,161.6 L108.7,161.5 L109.1,161.3 L109.5,161.2 L110.0,161.0 L110.4,160.8 L110.9,160.7 L111.3,160.5 L111.8,160.4 L112.2,160.2 L112.7,160.0 L113.1,159.8 L113.6,159.7 L114.0,159.5 L114.5,159.3 L114.9,159.2 L115.4,159.0 L115.8,158.8 L116.2,158.6 L116.7,158.5 L117.1,158.3 L117.6,158.1 L118.0,157.9 L118.5,157.7 L118.9,157.5 L119.4,157.3 L119.8,157.2 L120.3,157.0 L120.7,156.8 L121.2,156.6 L121.6,156.4 L122.1,156.2 L122.5,156.0 L122.9,155.8 L123.4,155.6 L123.8,155.4 L124.3,155.2 L124.7,155.0 L125.2,154.8 L125.6,154.5 L126.1,154.3 L126.5,154.1 L127.0,153.9 L127.4,153.7 L127.9,153.4 L128.3,153.2 L128.8,153.0 L129.2,152.8 L129.6,152.5 L130.1,152.3 L130.5,152.1 L131.0,151.8 L131.4,151.6 L131.9,151.3 L132.3,151.1 L132.8,150.8 L133.2,150.6 L133.7,150.3 L134.1,150.0 L134.6,149.8 L135.0,149.5 L135.5,149.2 L135.9,148.9 L136.3,148.7 L136.8,148.4 L137.2,148.1 L137.7,147.8 L138.1,147.5 L138.6,147.2 L139.0,146.9 L139.5,146.5 L139.9,146.2 L140.4,145.9 L140.8,145.6 L141.3,145.2 L141.7,144.9 L142.2,144.5 L142.6,144.1 L143.0,143.8 L143.5,143.4 L143.9,143.0 L144.4,142.6 L144.8,142.2 L145.3,141.8 L145.7,141.3 L146.2,140.9 L146.6,140.4 L147.1,140.0 L147.5,139.5 L148.0,139.0 L148.4,138.4 L148.9,137.9 L149.3,137.3 L149.7,136.7 L150.2,136.1 L150.6,135.4 L151.1,134.7 L151.5,134.0 L152.0,133.2 L152.4,132.3 L152.9,131.4 L153.3,130.4 L153.8,129.2 L154.2,127.9 L154.7,126.4 L155.1,124.4 L155.6,121.7 L156.0,111.0 L156.4,100.3 L156.9,97.6 L157.3,95.6 L157.8,94.1 L158.2,92.8 L158.7,91.6 L159.1,90.6 L159.6,89.7 L160.0,88.8 L160.5,88.0 L160.9,87.3 L161.4,86.6 L161.8,85.9 L162.3,85.3 L162.7,84.7 L163.1,84.1 L163.6,83.6 L164.0,83.0 L164.5,82.5 L164.9,82.0 L165.4,81.6 L165.8,81.1 L166.3,80.7 L166.7,80.2 L167.2,79.8 L167.6,79.4 L168.1,79.0 L168.5,78.6 L169.0,78.2 L169.4,77.9 L169.8,77.5 L170.3,77.1 L170.7,76.8 L171.2,76.4 L171.6,76.1 L172.1,75.8 L172.5,75.5 L173.0,75.1 L173.4,74.8 L173.9,74.5 L174.3,74.2 L174.8,73.9 L175.2,73.6 L175.7,73.3 L176.1,73.1 L176.5,72.8 L177.0,72.5 L177.4,72.2 L177.9,72.0 L178.3,71.7 L178.8,71.4 L179.2,71.2 L179.7,70.9 L180.1,70.7 L180.6,70.4 L181.0,70.2 L181.5,69.9 L181.9,69.7 L182.4,69.5 L182.8,69.2 L183.2,69.0 L183.7,68.8 L184.1,68.6 L184.6,68.3 L185.0,68.1 L185.5,67.9 L185.9,67.7 L186.4,67.5 L186.8,67.2 L187.3,67.0 L187.7,66.8 L188.2,66.6 L188.6,66.4 L189.1,66.2 L189.5,66.0 L189.9,65.8 L190.4,65.6 L190.8,65.4 L191.3,65.2 L191.7,65.0 L192.2,64.8 L192.6,64.7 L193.1,64.5 L193.5,64.3 L194.0,64.1 L194.4,63.9 L194.9,63.7 L195.3,63.5 L195.8,63.4 L196.2,63.2 L196.6,63.0 L197.1,62.8 L197.5,62.7 L198.0,62.5 L198.4,62.3 L198.9,62.2 L199.3,62.0 L199.8,61.8 L200.2,61.6 L200.7,61.5 L201.1,61.3 L201.6,61.2 L202.0,61.0 L202.5,60.8 L202.9,60.7 L203.3,60.5 L203.8,60.4 L204.2,60.2 L204.7,60.0 L205.1,59.9 L205.6,59.7 L206.0,59.6 L206.5,59.4 L206.9,59.3 L207.4,59.1 L207.8,59.0 L208.3,58.8 L208.7,58.7 L209.2,58.5 L209.6,58.4 L210.0,58.2 L210.5,58.1 L210.9,57.9 L211.4,57.8 L211.8,57.7 L212.3,57.5 L212.7,57.4 L213.2,57.2 L213.6,57.1 L214.1,57.0 L214.5,56.8 L215.0,56.7 L215.4,56.5 L215.9,56.4 L216.3,56.3 L216.7,56.1 L217.2,56.0 L217.6,55.9 L218.1,55.7 L218.5,55.6 L219.0,55.5 L219.4,55.3 L219.9,55.2 L220.3,55.1 L220.8,55.0 L221.2,54.8 L221.7,54.7 L222.1,54.6 L222.6,54.4 L223.0,54.3 L223.4,54.2 L223.9,54.1 L224.3,53.9 L224.8,53.8 L225.2,53.7 L225.7,53.6 L226.1,53.4 L226.6,53.3 L227.0,53.2 L227.5,53.1 L227.9,53.0 L228.4,52.8 L228.8,52.7 L229.3,52.6 L229.7,52.5 L230.1,52.4 L230.6,52.3 L231.0,52.1 L231.5,52.0 L231.9,51.9 L232.4,51.8 L232.8,51.7 L233.3,51.6 L233.7,51.4 L234.2,51.3 L234.6,51.2 L235.1,51.1 L235.5,51.0 L236.0,50.9 L236.4,50.8 L236.8,50.7 L237.3,50.5 L237.7,50.4 L238.2,50.3 L238.6,50.2 L239.1,50.1 L239.5,50.0 L240.0,49.9 L240.4,49.8 L240.9,49.7 L241.3,49.6 L241.8,49.5 L242.2,49.3 L242.7,49.2 L243.1,49.1 L243.5,49.0 L244.0,48.9 L244.4,48.8 L244.9,48.7 L245.3,48.6 L245.8,48.5 L246.2,48.4 L246.7,48.3 L247.1,48.2 L247.6,48.1 L248.0,48.0 L248.5,47.9 L248.9,47.8 L249.4,47.7 L249.8,47.6 L250.2,47.5 L250.7,47.4 L251.1,47.3 L251.6,47.2 L252.0,47.1 L252.5,47.0 L252.9,46.9 L253.4,46.8 L253.8,46.7 L254.3,46.6 L254.7,46.5 L255.2,46.4 L255.6,46.3 L256.1,46.2 L256.5,46.1 L256.9,46.0 L257.4,45.9 L257.8,45.8 L258.3,45.7 L258.7,45.6 L259.2,45.5 L259.6,45.4 L260.1,45.4 L260.5,45.3 L261.0,45.2 L261.4,45.1 L261.9,45.0 L262.3,44.9 L262.8,44.8 L263.2,44.7 L263.6,44.6 L264.1,44.5 L264.5,44.4 L265.0,44.3 L265.4,44.2 L265.9,44.2 L266.3,44.1 L266.8,44.0 L267.2,43.9 L267.7,43.8 L268.1,43.7 L268.6,43.6 L269.0,43.5 L269.5,43.4 L269.9,43.3 L270.3,43.3 L270.8,43.2 L271.2,43.1 L271.7,43.0 L272.1,42.9 L272.6,42.8 L273.0,42.7 L273.5,42.6 L273.9,42.6 L274.4,42.5 L274.8,42.4 L275.3,42.3 L275.7,42.2 L276.2,42.1 L276.6,42.0 L277.0,42.0 L277.5,41.9 L277.9,41.8 L278.4,41.7 L278.8,41.6 L279.3,41.5 L279.7,41.5 L280.2,41.4 L280.6,41.3 L281.1,41.2 L281.5,41.1 L282.0,41.0 L282.4,41.0 L282.9,40.9 L283.3,40.8 L283.7,40.7 L284.2,40.6 L284.6,40.5 L285.1,40.5 L285.5,40.4 L286.0,40.3 L286.4,40.2 L286.9,40.1 L287.3,40.1 L287.8,40.0 L288.2,39.9 L288.7,39.8 L289.1,39.7 L289.6,39.7 L290.0,39.6\" clip-path=\"url(#b10x13)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><circle cx=\"36.9\" cy=\"179.7\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"141.1\" cy=\"145.3\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"156.0\" cy=\"111.0\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"170.9\" cy=\"76.7\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"275.1\" cy=\"42.3\" r=\"3.8\" style=\"fill:var(--ink)\"/></svg>", "tools": ["desmos"], "desmos": ["y=\\sqrt[3]{x}"]}, {"kind": "blank", "p": "Look at g(x) = −2∛x.", "tag": "", "marks": "", "flat": [{"t": "Compared with ∛x, the graph is stretched by 2 and reflected in the __B1__ (x-axis / line y = x).", "a": {"B1": "x-axis"}, "expr": "words", "accept": ["x axis", "xaxis"]}, {"t": "g(8) = __B1__", "a": {"B1": "-4"}}, {"t": "g(−1) = __B1__", "a": {"B1": "2"}}], "sol": "Multiplying every output by −2 stretches by 2 and reflects in the x-axis.\n−2∛8 = −2(2) = −4.\n−2∛(−1) = −2(−1) = 2.", "tools": ["desmos"], "desmos": ["y=-2\\sqrt[3]{x}"]}, {"kind": "mcq", "text": "<b>Error analysis.</b> Kabir says the range of f(x) = ∛x + 5 is y ≥ 5, “just like for square roots”. Which reply is correct?", "opts": ["He is right: the range is y ≥ 5", "The range is y ≥ 0, because roots are never negative", "The range is y ≤ 5, because ∛x ≤ 0", "The range is all real numbers, because ∛x takes negative values too"], "correct": 3, "tag": "", "sol": "∛x can be any real number (for example ∛(−1000) = −10), so ∛x + 5 can also be any real number. f(−1000) = −5 is less than 5."}, {"kind": "blank", "p": "Find the intercepts of f(x) = ∛(x + 1) − 2.", "tag": "", "marks": "", "flat": [{"t": "y-intercept: f(0) = __B1__", "a": {"B1": "-1"}}, {"t": "x-intercept: ∛(x + 1) = 2, so x = __B1__", "a": {"B1": "7"}}], "sol": "f(0) = ∛1 − 2 = 1 − 2 = −1.\nSet f(x) = 0: ∛(x + 1) = 2. Cube: x + 1 = 8, so x = 7.", "tools": ["desmos"], "desmos": ["y=\\sqrt[3]{x+1}-2"]}, {"kind": "mcq", "text": "Which statement about g(x) = ∛(−x) is true?", "opts": ["It is the same function as ∛x", "It reflects ∛x in the y-axis, and it is undefined for x > 0", "It reflects ∛x in the line y = x", "It reflects ∛x in the y-axis, and it is the same function as −∛x"], "correct": 3, "tag": "", "sol": "Replacing x with −x reflects in the y-axis. Since (−a)³ = −a³, ∛(−x) = −∛x, so it is also the reflection in the x-axis. g(8) = ∛(−8) = −2 is defined."}, {"kind": "blank", "p": "The edge length s (cm) of a cube with volume V (cm³) is s = ∛V.", "tag": "", "marks": "", "flat": [{"t": "A cube-shaped gift box has volume 125 cm³. Its edge is __B1__ cm", "a": {"B1": "5"}}, {"t": "A cube-shaped tank has volume 1,000 cm³. Its edge is __B1__ cm", "a": {"B1": "10"}}, {"t": "If the volume is multiplied by 8, the edge is multiplied by __B1__", "a": {"B1": "2"}}], "sol": "∛125 = 5 because 5³ = 125.\n∛1000 = 10.\n∛(8V) = ∛8 · ∛V = 2∛V, so the edge doubles."}, {"kind": "mcq", "text": "What is the average rate of change of f(x) = ∛x from x = −8 to x = 8?", "opts": ["0", "{1/4}", "{1/2}", "4"], "correct": 1, "tag": "", "sol": "f(−8) = −2 and f(8) = 2. (2 − (−2)) ÷ (8 − (−8)) = {4/16} = {1/4}. (4 is only the change in f; 0 forgets that ∛(−8) is negative.)"}, {"kind": "blank", "p": "A salt crystal grows as a cube. After t days its edge length is e(t) = 2∛t millimetres.", "tag": "", "marks": "", "flat": [{"t": "Edge after 8 days: __B1__ mm", "a": {"B1": "4"}}, {"t": "Edge after 27 days: __B1__ mm", "a": {"B1": "6"}}, {"t": "The edge is 10 mm after t = __B1__ days", "a": {"B1": "125"}}], "sol": "2∛8 = 2(2) = 4 mm.\n2∛27 = 2(3) = 6 mm.\n2∛t = 10 → ∛t = 5 → t = 5³ = 125 days.", "tools": ["calc"], "desmos": []}, {"kind": "mcq", "text": "Which function has its point of symmetry at (−3, 4)?", "opts": ["y = ∛(x + 4) − 3", "y = ∛(x + 3) − 4", "y = ∛(x + 3) + 4", "y = ∛(x − 3) + 4"], "correct": 2, "tag": "", "sol": "y = ∛(x − h) + k has point of symmetry (h, k). With h = −3 and k = 4: y = ∛(x + 3) + 4."}, {"kind": "blank", "p": "Write a rule for g, a transformation of f(x) = ∛x (type ∛ as a power: ^(1/3), e.g. (x+1)^(1/3)).", "tag": "", "marks": "", "flat": [{"t": "Translate 2 units left and 5 units up: g(x) = __B1__", "a": {"B1": "(x+2)^(1/3)+5"}, "expr": "calc", "accept": ["5+(x+2)^(1/3)"]}, {"t": "Stretch vertically by a factor of 3, then translate 1 unit down: g(x) = __B1__", "a": {"B1": "3x^(1/3)-1"}, "expr": "calc", "accept": ["3*x^(1/3)-1", "-1+3x^(1/3)"]}], "sol": "Left 2: ∛(x + 2). Up 5: g(x) = ∛(x + 2) + 5.\nStretch: 3∛x. Down 1: g(x) = 3∛x − 1."}]}, {"id": "s3", "label": "10.3 Solving Radical Equations", "sub": "I can solve equations with square roots and cube roots by isolating the radical and raising both sides to a power, and identify extraneous solutions.", "slides": [{"kind": "mcq", "text": "Solve √x = 7.", "opts": ["x = 7", "x = 3.5", "x = 49", "x = 14"], "correct": 2, "tag": "", "sol": "Square both sides: x = 7² = 49. Check: √49 = 7 ✓ (14 doubles 7 and 3.5 halves it; neither undoes a square root.)"}, {"kind": "blank", "p": "Solve √x + 4 = 9.", "tag": "", "marks": "", "flat": [{"t": "Isolate the radical: √x = __B1__", "a": {"B1": "5"}}, {"t": "x = __B1__", "a": {"B1": "25"}}], "sol": "Subtract 4 from both sides: √x = 5.\nSquare both sides: x = 25. Check: √25 + 4 = 9 ✓"}, {"kind": "mcq", "text": "Solve √(2x + 3) = 5.", "opts": ["x = 4", "x = 11", "x = 1", "x = 14"], "correct": 1, "tag": "", "sol": "Square: 2x + 3 = 25. Subtract 3: 2x = 22, so x = 11. Check: √25 = 5 ✓ (x = 1 comes from forgetting to square: 2x + 3 = 5.)"}, {"kind": "blank", "p": "Solve 3√(x − 2) − 1 = 11.", "tag": "", "marks": "", "flat": [{"t": "Isolate the radical: √(x − 2) = __B1__", "a": {"B1": "4"}}, {"t": "Square both sides: x − 2 = __B1__", "a": {"B1": "16"}}, {"t": "x = __B1__", "a": {"B1": "18"}}], "sol": "Add 1: 3√(x − 2) = 12. Divide by 3: √(x − 2) = 4.\n4² = 16.\nx = 18. Check: 3√16 − 1 = 12 − 1 = 11 ✓"}, {"kind": "mcq", "text": "Which equation has no real solution?", "opts": ["√(x + 6) = 2", "∛x + 6 = 2", "√x − 6 = 2", "√x + 6 = 2"], "correct": 3, "tag": "", "sol": "√x + 6 = 2 gives √x = −4, but a principal square root is never negative. The others give x = 64, x = −2 and x = −64 (∛(−64) = −4 is fine)."}, {"kind": "blank", "p": "Solve ∛(x + 5) = 3.", "tag": "", "marks": "", "flat": [{"t": "Cube both sides: x + 5 = __B1__", "a": {"B1": "27"}}, {"t": "x = __B1__", "a": {"B1": "22"}}], "sol": "3³ = 27.\nSubtract 5: x = 22. Check: ∛27 = 3 ✓"}, {"kind": "mcq", "text": "<b>Error analysis.</b> Rohan solved √(x + 6) = x. He squared to get x + 6 = x², factored (x − 3)(x + 2) = 0 and wrote “x = 3 or x = −2”. What is correct?", "opts": ["Only x = 3; x = −2 is extraneous because √4 = 2, not −2", "Both x = 3 and x = −2 are solutions", "Only x = −2; x = 3 is extraneous because 3 is too large", "There is no solution, because you cannot square both sides"], "correct": 0, "tag": "", "sol": "Check each value in the original equation. x = 3: √9 = 3 ✓. x = −2: √4 = 2, but the right side is −2 ✗. Squaring created the extraneous solution −2."}, {"kind": "blank", "p": "Solve √(x + 8) = x − 4.", "tag": "", "marks": "", "flat": [{"t": "Square and solve x² − 9x + 8 = 0. The possible solutions are x = __B1__ (separate with a comma)", "a": {"B1": "1, 8"}, "expr": "set"}, {"t": "The extraneous solution is x = __B1__", "a": {"B1": "1"}}, {"t": "The solution is x = __B1__", "a": {"B1": "8"}}], "sol": "x + 8 = (x − 4)² = x² − 8x + 16, so x² − 9x + 8 = 0 and (x − 1)(x − 8) = 0.\nx = 1: √9 = 3 but 1 − 4 = −3 ✗.\nx = 8: √16 = 4 and 8 − 4 = 4 ✓", "tools": ["desmos"], "desmos": ["y=\\sqrt{x+8}", "y=x-4"]}, {"kind": "mcq", "text": "Solve √(3x − 4) = √(x + 6).", "opts": ["x = −1", "x = 1", "x = 2.5", "x = 5"], "correct": 3, "tag": "", "sol": "Square both sides: 3x − 4 = x + 6. Then 2x = 10 and x = 5. Check: √11 = √11 ✓ (x = 1 comes from 2x = 6 − 4, a sign slip when moving the −4.)"}, {"kind": "blank", "p": "A dropped object falls h feet in t = √({h/16}) seconds. A coin dropped from a bridge hits the water after 2.5 seconds.", "tag": "", "marks": "", "flat": [{"t": "Square both sides: {h/16} = __B1__", "a": {"B1": "6.25"}}, {"t": "Height of the bridge: h = __B1__ ft", "a": {"B1": "100"}}], "sol": "2.5² = 6.25.\nMultiply by 16: h = 100 ft. Check: √({100/16}) = √6.25 = 2.5 ✓", "tools": ["calc"], "desmos": []}, {"kind": "mcq", "text": "Solve x<sup>1/3</sup> − 2 = 3.", "opts": ["x = 125", "x = 15", "x = 1", "x = 25"], "correct": 0, "tag": "", "sol": "Add 2: x<sup>1/3</sup> = 5. x<sup>1/3</sup> means ∛x, so cube both sides: x = 125. Check: ∛125 − 2 = 3 ✓ (25 squares instead of cubing; 15 multiplies by 3.)"}, {"kind": "blank", "p": "Solve √x + 6 = x.", "tag": "", "marks": "", "flat": [{"t": "Isolate the radical: √x = x − __B1__", "a": {"B1": "6"}}, {"t": "Squaring gives x² − 13x + 36 = 0, so x = 4 or x = 9. The value x = 4 is __B1__ (a solution / extraneous).", "a": {"B1": "extraneous"}, "expr": "words", "accept": ["an extraneous solution", "extraneous solution"]}, {"t": "The solution is x = __B1__", "a": {"B1": "9"}}], "sol": "Subtract 6 from both sides.\nx = (x − 6)² = x² − 12x + 36 → x² − 13x + 36 = 0 → (x − 4)(x − 9) = 0. Check x = 4: √4 + 6 = 8 ≠ 4 ✗.\nCheck x = 9: √9 + 6 = 9 ✓", "tools": ["desmos"], "desmos": ["y=\\sqrt{x}+6", "y=x"]}, {"kind": "mcq", "text": "Police estimate a car's speed from its skid marks with s = √(22.5d), where s is the speed in miles per hour and d is the skid length in feet. A car was going 45 mi/h. How long were its skid marks?", "opts": ["90 ft", "1,012.5 ft", "30 ft", "2 ft"], "correct": 0, "tag": "", "sol": "Square both sides: 2025 = 22.5d. Divide: d = 2025 ÷ 22.5 = 90 ft. Check: √(22.5 × 90) = √2025 = 45 ✓ (2 ft is 45 ÷ 22.5 without squaring.)", "tools": ["calc"], "desmos": []}, {"kind": "blank", "p": "Solve √(5x) = 2√(x + 1).", "tag": "", "marks": "", "flat": [{"t": "Square both sides: 5x = __B1__(x + 1)", "a": {"B1": "4"}}, {"t": "x = __B1__", "a": {"B1": "4"}}], "sol": "(2√(x + 1))² = 4(x + 1).\n5x = 4x + 4, so x = 4. Check: √20 and 2√5 = √20 ✓"}]}, {"id": "s4", "label": "10.4 Inverse of a Function", "sub": "I can find inverses of relations and functions, restrict domains so that an inverse is a function, and check that two functions are inverses.", "slides": [{"kind": "mcq", "text": "What is the inverse of the relation {(1, 4), (2, 7), (3, 10)}?", "opts": ["{(1, {1/4}), (2, {1/7}), (3, {1/10})}", "{(4, 1), (7, 2), (10, 3)}", "{(1, −4), (2, −7), (3, −10)}", "{(−1, −4), (−2, −7), (−3, −10)}"], "correct": 1, "tag": "", "sol": "An inverse relation switches each input and output: (a, b) becomes (b, a)."}, {"kind": "blank", "p": "Find the inverse of f(x) = 2x + 6.", "tag": "", "marks": "", "flat": [{"t": "Switch x and y: x = 2y + 6. Solve for y: f⁻¹(x) = __B1__", "a": {"B1": "(x-6)/2"}, "expr": true, "accept": ["x/2-3", "0.5x-3"]}, {"t": "f⁻¹(10) = __B1__", "a": {"B1": "2"}}], "sol": "x − 6 = 2y, so y = (x − 6) ÷ 2 = {x/2} − 3.\n(10 − 6) ÷ 2 = 2. Check: f(2) = 10 ✓", "tools": ["desmos"], "desmos": ["y=2x+6", "y=x"]}, {"kind": "mcq", "text": "The graph of f⁻¹ is a reflection of the graph of f in which line?", "opts": ["y = x", "y = −x", "the y-axis", "the x-axis"], "correct": 0, "tag": "", "sol": "Switching x and y turns (a, b) into (b, a), and these two points are mirror images in the line y = x."}, {"kind": "blank", "p": "Find the inverse of f(x) = {1/3}x − 4.", "tag": "", "marks": "", "flat": [{"t": "f⁻¹(x) = __B1__", "a": {"B1": "3x+12"}, "expr": true, "accept": ["3(x+4)"]}, {"t": "Check: f(f⁻¹(5)) = __B1__", "a": {"B1": "5"}}], "sol": "Switch: x = {1/3}y − 4. Add 4: x + 4 = {1/3}y. Multiply by 3: y = 3x + 12.\nf⁻¹(5) = 27 and f(27) = 9 − 4 = 5: a function and its inverse undo each other."}, {"kind": "mcq", "text": "The graph shows the line y = f(x). What is f⁻¹(8)?", "opts": ["{8/3}", "26", "{1/8}", "2"], "correct": 3, "tag": "", "sol": "f⁻¹(8) is the input that gives the output 8. On the graph, y = 8 when x = 2, so f⁻¹(8) = 2. (26 is f(8) for this line, y = 3x + 2; {1/8} confuses f⁻¹ with a reciprocal.)", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"22.0\" y1=\"214.0\" x2=\"22.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"66.7\" y1=\"214.0\" x2=\"66.7\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"111.3\" y1=\"214.0\" x2=\"111.3\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"156.0\" y1=\"214.0\" x2=\"156.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"200.7\" y1=\"214.0\" x2=\"200.7\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"245.3\" y1=\"214.0\" x2=\"245.3\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"290.0\" y1=\"214.0\" x2=\"290.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"214.0\" x2=\"290.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"196.8\" x2=\"290.0\" y2=\"196.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"179.7\" x2=\"290.0\" y2=\"179.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"162.5\" x2=\"290.0\" y2=\"162.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"145.3\" x2=\"290.0\" y2=\"145.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"128.2\" x2=\"290.0\" y2=\"128.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"111.0\" x2=\"290.0\" y2=\"111.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"93.8\" x2=\"290.0\" y2=\"93.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"76.7\" x2=\"290.0\" y2=\"76.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"59.5\" x2=\"290.0\" y2=\"59.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"42.3\" x2=\"290.0\" y2=\"42.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"25.2\" x2=\"290.0\" y2=\"25.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"8.0\" x2=\"290.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"22.0\" y1=\"179.7\" x2=\"290.0\" y2=\"179.7\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"111.3\" y1=\"214.0\" x2=\"111.3\" y2=\"8.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"22.0\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"66.7\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−1</text><text class=\"po\" x=\"156.0\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><text class=\"po\" x=\"200.7\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"245.3\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><text class=\"po\" x=\"290.0\" y=\"188.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"107.3\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"107.3\" y=\"145.3\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"107.3\" y=\"111.0\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"107.3\" y=\"76.7\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"107.3\" y=\"42.3\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><text class=\"po\" x=\"107.3\" y=\"8.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><text class=\"po\" x=\"286.0\" y=\"171.7\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"119.3\" y=\"14.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b10x14\"><rect x=\"22.0\" y=\"8.0\" width=\"268.0\" height=\"206.0\"/></clipPath><path d=\"M22.0,248.3 L22.4,247.8 L22.9,247.3 L23.3,246.8 L23.8,246.3 L24.2,245.8 L24.7,245.2 L25.1,244.7 L25.6,244.2 L26.0,243.7 L26.5,243.2 L26.9,242.7 L27.4,242.2 L27.8,241.6 L28.3,241.1 L28.7,240.6 L29.1,240.1 L29.6,239.6 L30.0,239.1 L30.5,238.5 L30.9,238.0 L31.4,237.5 L31.8,237.0 L32.3,236.5 L32.7,236.0 L33.2,235.5 L33.6,234.9 L34.1,234.4 L34.5,233.9 L35.0,233.4 L35.4,232.9 L35.8,232.4 L36.3,231.9 L36.7,231.3 L37.2,230.8 L37.6,230.3 L38.1,229.8 L38.5,229.3 L39.0,228.8 L39.4,228.2 L39.9,227.7 L40.3,227.2 L40.8,226.7 L41.2,226.2 L41.7,225.7 L42.1,225.2 L42.5,224.6 L43.0,224.1 L43.4,223.6 L43.9,223.1 L44.3,222.6 L44.8,222.1 L45.2,221.6 L45.7,221.0 L46.1,220.5 L46.6,220.0 L47.0,219.5 L47.5,219.0 L47.9,218.5 L48.4,217.9 L48.8,217.4 L49.2,216.9 L49.7,216.4 L50.1,215.9 L50.6,215.4 L51.0,214.9 L51.5,214.3 L51.9,213.8 L52.4,213.3 L52.8,212.8 L53.3,212.3 L53.7,211.8 L54.2,211.3 L54.6,210.7 L55.1,210.2 L55.5,209.7 L55.9,209.2 L56.4,208.7 L56.8,208.2 L57.3,207.6 L57.7,207.1 L58.2,206.6 L58.6,206.1 L59.1,205.6 L59.5,205.1 L60.0,204.6 L60.4,204.0 L60.9,203.5 L61.3,203.0 L61.8,202.5 L62.2,202.0 L62.6,201.5 L63.1,201.0 L63.5,200.4 L64.0,199.9 L64.4,199.4 L64.9,198.9 L65.3,198.4 L65.8,197.9 L66.2,197.3 L66.7,196.8 L67.1,196.3 L67.6,195.8 L68.0,195.3 L68.5,194.8 L68.9,194.3 L69.3,193.7 L69.8,193.2 L70.2,192.7 L70.7,192.2 L71.1,191.7 L71.6,191.2 L72.0,190.7 L72.5,190.1 L72.9,189.6 L73.4,189.1 L73.8,188.6 L74.3,188.1 L74.7,187.6 L75.2,187.0 L75.6,186.5 L76.0,186.0 L76.5,185.5 L76.9,185.0 L77.4,184.5 L77.8,184.0 L78.3,183.4 L78.7,182.9 L79.2,182.4 L79.6,181.9 L80.1,181.4 L80.5,180.9 L81.0,180.4 L81.4,179.8 L81.9,179.3 L82.3,178.8 L82.7,178.3 L83.2,177.8 L83.6,177.3 L84.1,176.7 L84.5,176.2 L85.0,175.7 L85.4,175.2 L85.9,174.7 L86.3,174.2 L86.8,173.7 L87.2,173.1 L87.7,172.6 L88.1,172.1 L88.6,171.6 L89.0,171.1 L89.4,170.6 L89.9,170.1 L90.3,169.5 L90.8,169.0 L91.2,168.5 L91.7,168.0 L92.1,167.5 L92.6,167.0 L93.0,166.4 L93.5,165.9 L93.9,165.4 L94.4,164.9 L94.8,164.4 L95.3,163.9 L95.7,163.4 L96.1,162.8 L96.6,162.3 L97.0,161.8 L97.5,161.3 L97.9,160.8 L98.4,160.3 L98.8,159.8 L99.3,159.2 L99.7,158.7 L100.2,158.2 L100.6,157.7 L101.1,157.2 L101.5,156.7 L102.0,156.1 L102.4,155.6 L102.8,155.1 L103.3,154.6 L103.7,154.1 L104.2,153.6 L104.6,153.1 L105.1,152.5 L105.5,152.0 L106.0,151.5 L106.4,151.0 L106.9,150.5 L107.3,150.0 L107.8,149.5 L108.2,148.9 L108.7,148.4 L109.1,147.9 L109.5,147.4 L110.0,146.9 L110.4,146.4 L110.9,145.8 L111.3,145.3 L111.8,144.8 L112.2,144.3 L112.7,143.8 L113.1,143.3 L113.6,142.8 L114.0,142.2 L114.5,141.7 L114.9,141.2 L115.4,140.7 L115.8,140.2 L116.2,139.7 L116.7,139.2 L117.1,138.6 L117.6,138.1 L118.0,137.6 L118.5,137.1 L118.9,136.6 L119.4,136.1 L119.8,135.5 L120.3,135.0 L120.7,134.5 L121.2,134.0 L121.6,133.5 L122.1,133.0 L122.5,132.5 L122.9,131.9 L123.4,131.4 L123.8,130.9 L124.3,130.4 L124.7,129.9 L125.2,129.4 L125.6,128.9 L126.1,128.3 L126.5,127.8 L127.0,127.3 L127.4,126.8 L127.9,126.3 L128.3,125.8 L128.8,125.2 L129.2,124.7 L129.6,124.2 L130.1,123.7 L130.5,123.2 L131.0,122.7 L131.4,122.2 L131.9,121.6 L132.3,121.1 L132.8,120.6 L133.2,120.1 L133.7,119.6 L134.1,119.1 L134.6,118.6 L135.0,118.0 L135.5,117.5 L135.9,117.0 L136.3,116.5 L136.8,116.0 L137.2,115.5 L137.7,114.9 L138.1,114.4 L138.6,113.9 L139.0,113.4 L139.5,112.9 L139.9,112.4 L140.4,111.9 L140.8,111.3 L141.3,110.8 L141.7,110.3 L142.2,109.8 L142.6,109.3 L143.0,108.8 L143.5,108.3 L143.9,107.7 L144.4,107.2 L144.8,106.7 L145.3,106.2 L145.7,105.7 L146.2,105.2 L146.6,104.6 L147.1,104.1 L147.5,103.6 L148.0,103.1 L148.4,102.6 L148.9,102.1 L149.3,101.6 L149.7,101.0 L150.2,100.5 L150.6,100.0 L151.1,99.5 L151.5,99.0 L152.0,98.5 L152.4,98.0 L152.9,97.4 L153.3,96.9 L153.8,96.4 L154.2,95.9 L154.7,95.4 L155.1,94.9 L155.6,94.3 L156.0,93.8 L156.4,93.3 L156.9,92.8 L157.3,92.3 L157.8,91.8 L158.2,91.3 L158.7,90.7 L159.1,90.2 L159.6,89.7 L160.0,89.2 L160.5,88.7 L160.9,88.2 L161.4,87.7 L161.8,87.1 L162.3,86.6 L162.7,86.1 L163.1,85.6 L163.6,85.1 L164.0,84.6 L164.5,84.0 L164.9,83.5 L165.4,83.0 L165.8,82.5 L166.3,82.0 L166.7,81.5 L167.2,81.0 L167.6,80.4 L168.1,79.9 L168.5,79.4 L169.0,78.9 L169.4,78.4 L169.8,77.9 L170.3,77.4 L170.7,76.8 L171.2,76.3 L171.6,75.8 L172.1,75.3 L172.5,74.8 L173.0,74.3 L173.4,73.7 L173.9,73.2 L174.3,72.7 L174.8,72.2 L175.2,71.7 L175.7,71.2 L176.1,70.7 L176.5,70.1 L177.0,69.6 L177.4,69.1 L177.9,68.6 L178.3,68.1 L178.8,67.6 L179.2,67.1 L179.7,66.5 L180.1,66.0 L180.6,65.5 L181.0,65.0 L181.5,64.5 L181.9,64.0 L182.4,63.4 L182.8,62.9 L183.2,62.4 L183.7,61.9 L184.1,61.4 L184.6,60.9 L185.0,60.4 L185.5,59.8 L185.9,59.3 L186.4,58.8 L186.8,58.3 L187.3,57.8 L187.7,57.3 L188.2,56.8 L188.6,56.2 L189.1,55.7 L189.5,55.2 L189.9,54.7 L190.4,54.2 L190.8,53.7 L191.3,53.1 L191.7,52.6 L192.2,52.1 L192.6,51.6 L193.1,51.1 L193.5,50.6 L194.0,50.1 L194.4,49.5 L194.9,49.0 L195.3,48.5 L195.8,48.0 L196.2,47.5 L196.6,47.0 L197.1,46.5 L197.5,45.9 L198.0,45.4 L198.4,44.9 L198.9,44.4 L199.3,43.9 L199.8,43.4 L200.2,42.8 L200.7,42.3 L201.1,41.8 L201.6,41.3 L202.0,40.8 L202.5,40.3 L202.9,39.8 L203.3,39.2 L203.8,38.7 L204.2,38.2 L204.7,37.7 L205.1,37.2 L205.6,36.7 L206.0,36.2 L206.5,35.6 L206.9,35.1 L207.4,34.6 L207.8,34.1 L208.3,33.6 L208.7,33.1 L209.2,32.5 L209.6,32.0 L210.0,31.5 L210.5,31.0 L210.9,30.5 L211.4,30.0 L211.8,29.5 L212.3,28.9 L212.7,28.4 L213.2,27.9 L213.6,27.4 L214.1,26.9 L214.5,26.4 L215.0,25.9 L215.4,25.3 L215.9,24.8 L216.3,24.3 L216.7,23.8 L217.2,23.3 L217.6,22.8 L218.1,22.2 L218.5,21.7 L219.0,21.2 L219.4,20.7 L219.9,20.2 L220.3,19.7 L220.8,19.2 L221.2,18.6 L221.7,18.1 L222.1,17.6 L222.6,17.1 L223.0,16.6 L223.4,16.1 L223.9,15.6 L224.3,15.0 L224.8,14.5 L225.2,14.0 L225.7,13.5 L226.1,13.0 L226.6,12.5 L227.0,11.9 L227.5,11.4 L227.9,10.9 L228.4,10.4 L228.8,9.9 L229.3,9.4 L229.7,8.9 L230.1,8.3 L230.6,7.8 L231.0,7.3 L231.5,6.8 L231.9,6.3 L232.4,5.8 L232.8,5.3 L233.3,4.7 L233.7,4.2 L234.2,3.7 L234.6,3.2 L235.1,2.7 L235.5,2.2 L236.0,1.6 L236.4,1.1 L236.8,0.6 L237.3,0.1 L237.7,-0.4 L238.2,-0.9 L238.6,-1.4 L239.1,-2.0 L239.5,-2.5 L240.0,-3.0 L240.4,-3.5 L240.9,-4.0 L241.3,-4.5 L241.8,-5.0 L242.2,-5.6 L242.7,-6.1 L243.1,-6.6 L243.5,-7.1 L244.0,-7.6 L244.4,-8.1 L244.9,-8.7 L245.3,-9.2 L245.8,-9.7 L246.2,-10.2 L246.7,-10.7 L247.1,-11.2 L247.6,-11.7 L248.0,-12.3 L248.5,-12.8 L248.9,-13.3 L249.4,-13.8 L249.8,-14.3 L250.2,-14.8 L250.7,-15.3 L251.1,-15.9 L251.6,-16.4 L252.0,-16.9 L252.5,-17.4 L252.9,-17.9 L253.4,-18.4 L253.8,-19.0 L254.3,-19.5 L254.7,-20.0 L255.2,-20.5 L255.6,-21.0 L256.1,-21.5 L256.5,-22.0 L256.9,-22.6 L257.4,-23.1 L257.8,-23.6 L258.3,-24.1 L258.7,-24.6 L259.2,-25.1 L259.6,-25.6 L260.1,-26.2 L260.5,-26.7 L261.0,-27.2 L261.4,-27.7 L261.9,-28.2 L262.3,-28.7 L262.8,-29.3 L263.2,-29.8 L263.6,-30.3 L264.1,-30.8 L264.5,-31.3 L265.0,-31.8 L265.4,-32.3 L265.9,-32.9 L266.3,-33.4 L266.8,-33.9 L267.2,-34.4 L267.7,-34.9 L268.1,-35.4 L268.6,-35.9 L269.0,-36.5 L269.5,-37.0 L269.9,-37.5 L270.3,-38.0 L270.8,-38.5 L271.2,-39.0 L271.7,-39.6 L272.1,-40.1 L272.6,-40.6 L273.0,-41.1 L273.5,-41.6 L273.9,-42.1 L274.4,-42.6 L274.8,-43.2 L275.3,-43.7 L275.7,-44.2 L276.2,-44.7 L276.6,-45.2 L277.0,-45.7 L277.5,-46.2 L277.9,-46.8 L278.4,-47.3 L278.8,-47.8 L279.3,-48.3 L279.7,-48.8 L280.2,-49.3 L280.6,-49.9 L281.1,-50.4 L281.5,-50.9 L282.0,-51.4 L282.4,-51.9 L282.9,-52.4 L283.3,-52.9 L283.7,-53.5 L284.2,-54.0 L284.6,-54.5 L285.1,-55.0 L285.5,-55.5 L286.0,-56.0 L286.4,-56.5 L286.9,-57.1 L287.3,-57.6 L287.8,-58.1 L288.2,-58.6 L288.7,-59.1 L289.1,-59.6 L289.6,-60.2 L290.0,-60.7\" clip-path=\"url(#b10x14)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><circle cx=\"111.3\" cy=\"145.3\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"156.0\" cy=\"93.8\" r=\"3.8\" style=\"fill:var(--ink)\"/><circle cx=\"200.7\" cy=\"42.3\" r=\"3.8\" style=\"fill:var(--ink)\"/></svg>"}, {"kind": "blank", "p": "Look at f(x) = x² with domain all real numbers.", "tag": "", "marks": "", "flat": [{"t": "f(−3) = f(3) = 9, so f fails the horizontal line test and its inverse __B1__ a function (is / is not).", "a": {"B1": "is not"}, "expr": "words", "accept": ["isnot", "not", "isnt"]}, {"t": "Restrict the domain to x ≥ 0. Then f⁻¹(x) = __B1__ (type √ as sqrt( ) or use the √ key)", "a": {"B1": "sqrt(x)"}, "expr": "calc", "accept": ["x^(1/2)"]}, {"t": "For this restricted f, f⁻¹(49) = __B1__", "a": {"B1": "7"}}], "sol": "The horizontal line y = 9 meets the graph twice, so the inverse would pair 9 with both −3 and 3.\nSwitch: x = y² with y ≥ 0, so y = √x.\n√49 = 7.", "tools": ["desmos"], "desmos": ["y=x^2"]}, {"kind": "mcq", "text": "<b>Error analysis.</b> Zara found the inverse of f(x) = 4x − 1 and wrote f⁻¹(x) = 4x + 1. Which is correct?", "opts": ["f⁻¹(x) = 1 ÷ (4x − 1)", "f⁻¹(x) = 4x + 1 is correct", "f⁻¹(x) = (x + 1) ÷ 4", "f⁻¹(x) = (x − 1) ÷ 4"], "correct": 2, "tag": "", "sol": "Switch: x = 4y − 1, so x + 1 = 4y and y = (x + 1) ÷ 4. Zara undid the subtraction but not the multiplication. Check: f(2) = 7 and (7 + 1) ÷ 4 = 2 ✓, but 4(7) + 1 = 29 ✗."}, {"kind": "blank", "p": "Find the inverse of f(x) = √(x − 2).", "tag": "", "marks": "", "flat": [{"t": "Switch x and y and square: f⁻¹(x) = __B1__", "a": {"B1": "x^2+2"}, "expr": true, "accept": ["2+x^2"]}, {"t": "The domain of f⁻¹ is x ≥ __B1__", "a": {"B1": "0"}}], "sol": "x = √(y − 2) → x² = y − 2 → y = x² + 2.\nThe domain of f⁻¹ is the range of f, which is y ≥ 0. So f⁻¹(x) = x² + 2 with x ≥ 0.", "tools": ["desmos"], "desmos": ["y=\\sqrt{x-2}", "y=x"]}, {"kind": "mcq", "text": "Which pair of functions are inverses of each other?", "opts": ["f(x) = 5x − 3 and g(x) = (x + 3) ÷ 5", "f(x) = 5x − 3 and g(x) = (x − 3) ÷ 5", "f(x) = 5x − 3 and g(x) = 5x + 3", "f(x) = 5x − 3 and g(x) = 1 ÷ (5x − 3)"], "correct": 0, "tag": "", "sol": "f(g(x)) = 5 · (x + 3) ÷ 5 − 3 = x + 3 − 3 = x, and g(f(x)) = (5x − 3 + 3) ÷ 5 = x. For the second pair, f(g(x)) = x − 3 − 3 = x − 6 ≠ x."}, {"kind": "blank", "p": "Find the inverse of f(x) = x³ − 8 (type ∛ as a power: ^(1/3), e.g. (x+1)^(1/3)).", "tag": "", "marks": "", "flat": [{"t": "f⁻¹(x) = __B1__", "a": {"B1": "(x+8)^(1/3)"}, "expr": "calc", "accept": ["(8+x)^(1/3)"]}, {"t": "f⁻¹(19) = __B1__", "a": {"B1": "3"}}], "sol": "Switch: x = y³ − 8. Add 8: y³ = x + 8. Take the cube root: y = ∛(x + 8).\n∛(19 + 8) = ∛27 = 3. Check: 3³ − 8 = 19 ✓"}, {"kind": "mcq", "text": "The formula F = 1.8C + 32 converts degrees Celsius to degrees Fahrenheit. Which is its inverse, and what is 68 °F in Celsius?", "opts": ["C = (F + 32) ÷ 1.8; 55.6 °C", "C = F ÷ 1.8 − 32; 5.8 °C", "C = 1.8F − 32; 90.4 °C", "C = (F − 32) ÷ 1.8; 20 °C"], "correct": 3, "tag": "", "sol": "Subtract 32, then divide by 1.8: C = (F − 32) ÷ 1.8. For 68 °F: 36 ÷ 1.8 = 20 °C."}, {"kind": "blank", "p": "A taxi charges a $4 pick-up fee plus $2.50 per mile, so the fare for x miles is f(x) = 2.5x + 4.", "tag": "", "marks": "", "flat": [{"t": "The inverse gives the miles for a fare of x dollars: f⁻¹(x) = __B1__", "a": {"B1": "(x-4)/2.5"}, "expr": true, "accept": ["0.4x-1.6", "0.4(x-4)", "(2/5)(x-4)"]}, {"t": "A ride that cost $29 was __B1__ miles", "a": {"B1": "10"}}], "sol": "Switch: x = 2.5y + 4 → x − 4 = 2.5y → y = (x − 4) ÷ 2.5.\n(29 − 4) ÷ 2.5 = 25 ÷ 2.5 = 10 miles.", "tools": ["calc"], "desmos": []}, {"kind": "mcq", "text": "What is the inverse of f(x) = x² − 4, x ≥ 0?", "opts": ["f⁻¹(x) = √(x − 4)", "f⁻¹(x) = x² + 4", "f⁻¹(x) = √(x + 4)", "f⁻¹(x) = √x + 4"], "correct": 2, "tag": "", "sol": "Switch: x = y² − 4, so y² = x + 4 and, because y ≥ 0, y = √(x + 4). (√x + 4 adds 4 after the root; x² + 4 does not undo the square.)", "tools": ["desmos"], "desmos": ["y=x^2-4\\{x\\ge0\\}", "y=x"]}, {"kind": "blank", "p": "Look at f(x) = 2x², x ≥ 0.", "tag": "", "marks": "", "flat": [{"t": "f⁻¹(x) = __B1__ (type √ as sqrt( ) or use the √ key)", "a": {"B1": "sqrt(x/2)"}, "expr": "calc", "accept": ["sqrt(0.5x)", "sqrt(x)/sqrt(2)"]}, {"t": "f⁻¹(18) = __B1__", "a": {"B1": "3"}}, {"t": "The range of f⁻¹ is y ≥ __B1__", "a": {"B1": "0"}}], "sol": "Switch: x = 2y² → y² = {x/2} → y = √({x/2}) (y ≥ 0).\n√({18/2}) = √9 = 3. Check: 2(3)² = 18 ✓\nThe range of f⁻¹ is the domain of f: y ≥ 0."}]}, {"id": "s5", "label": "Assessment A", "sub": "Knowing and understanding", "slides": [{"kind": "mcq", "text": "What is the domain of f(x) = √(x − 7)?", "opts": ["x ≤ 7", "x ≥ −7", "All real numbers", "x ≥ 7"], "correct": 3, "tag": "", "sol": "x − 7 ≥ 0, so x ≥ 7."}, {"kind": "blank", "p": "f(x) = ∛(x − 1).", "tag": "", "marks": "", "flat": [{"t": "f(28) = __B1__", "a": {"B1": "3"}}, {"t": "f(−7) = __B1__", "a": {"B1": "-2"}}], "sol": "∛27 = 3.\n∛(−8) = −2."}, {"kind": "mcq", "text": "Solve √(x − 3) = 4.", "opts": ["x = 1", "x = 13", "x = 19", "x = 7"], "correct": 2, "tag": "", "sol": "Square: x − 3 = 16, so x = 19. (x = 7 forgets to square.)"}, {"kind": "blank", "p": "Find the inverse of f(x) = 6x + 1.", "tag": "", "marks": "", "flat": [{"t": "f⁻¹(x) = __B1__", "a": {"B1": "(x-1)/6"}, "expr": true, "accept": ["x/6-1/6"]}, {"t": "f⁻¹(13) = __B1__", "a": {"B1": "2"}}], "sol": "x = 6y + 1 → x − 1 = 6y → y = (x − 1) ÷ 6.\n(13 − 1) ÷ 6 = 2."}, {"kind": "mcq", "text": "What is the range of g(x) = √x − 5?", "opts": ["y ≤ −5", "y ≥ 5", "All real numbers", "y ≥ −5"], "correct": 3, "tag": "", "sol": "√x ≥ 0, so √x − 5 ≥ −5.", "tools": ["desmos"], "desmos": ["y=\\sqrt{x}-5"]}, {"kind": "blank", "p": "Solve 2√x − 3 = 7.", "tag": "", "marks": "", "flat": [{"t": "√x = __B1__", "a": {"B1": "5"}}, {"t": "x = __B1__", "a": {"B1": "25"}}], "sol": "Add 3: 2√x = 10. Divide by 2: √x = 5.\nSquare: x = 25. Check: 2(5) − 3 = 7 ✓"}, {"kind": "mcq", "text": "What is the point of symmetry of y = ∛(x − 6) + 1?", "opts": ["(1, 6)", "(6, 1)", "(6, −1)", "(−6, 1)"], "correct": 1, "tag": "", "sol": "y = ∛(x − h) + k has point of symmetry (h, k) = (6, 1).", "tools": ["desmos"], "desmos": ["y=\\sqrt[3]{x-6}+1"]}, {"kind": "blank", "p": "Solve ∛(4x) = −2.", "tag": "", "marks": "", "flat": [{"t": "Cube both sides: 4x = __B1__", "a": {"B1": "-8"}}, {"t": "x = __B1__", "a": {"B1": "-2"}}], "sol": "(−2)³ = −8.\nx = −2. Check: ∛(−8) = −2 ✓"}, {"kind": "mcq", "text": "What is the inverse of f(x) = x³?", "opts": ["f⁻¹(x) = √x", "f⁻¹(x) = ∛x", "f⁻¹(x) = 1 ÷ x³", "f⁻¹(x) = {x/3}"], "correct": 1, "tag": "", "sol": "Switch: x = y³, so y = ∛x. (f⁻¹ is not the reciprocal.)"}]}, {"id": "s6", "label": "Assessment B", "sub": "Investigating patterns", "slides": [{"kind": "blank", "p": "Look at outputs of f(x) = √x.", "tag": "", "marks": "", "flat": [{"t": "f(25) = __B1__", "a": {"B1": "5"}}, {"t": "f(100) = __B1__", "a": {"B1": "10"}}, {"t": "To double the output of √x, multiply the input by __B1__", "a": {"B1": "4"}}], "sol": "√25 = 5.\n√100 = 10.\n√(4x) = 2√x, so 4 times the input gives twice the output."}, {"kind": "mcq", "text": "For g(x) = a√(x − h) + k with a > 0, what is always true about its graph?", "opts": ["It starts at (h, k), with domain x ≥ h and range y ≥ k", "It starts at (−h, k), with domain x ≥ −h and range y ≥ k", "It starts at (k, h), with domain x ≥ k and range y ≥ h", "It starts at (h, k), with domain all real numbers and range y ≥ k"], "correct": 0, "tag": "", "sol": "The radicand x − h ≥ 0 gives x ≥ h; the smallest output is a(0) + k = k."}, {"kind": "blank", "p": "Solve √x = a for different values of a.", "tag": "", "marks": "", "flat": [{"t": "a = 3: x = __B1__", "a": {"B1": "9"}}, {"t": "a = 8: x = __B1__", "a": {"B1": "64"}}, {"t": "In general (a ≥ 0), x = __B1__", "a": {"B1": "a^2"}, "expr": true, "accept": ["a*a"]}], "sol": "3² = 9.\n8² = 64.\nSquaring both sides gives x = a²."}, {"kind": "mcq", "text": "∛(−1) = −1, ∛(−8) = −2, ∛(−27) = −3. What is ∛(−1000)?", "opts": ["−333.3", "−100", "10", "−10"], "correct": 3, "tag": "", "sol": "(−10)³ = −1000, so ∛(−1000) = −10. The pattern is ∛(−n³) = −n."}, {"kind": "blank", "p": "Find the inverse of f(x) = x + b for different values of b.", "tag": "", "marks": "", "flat": [{"t": "f(x) = x + 3: f⁻¹(x) = __B1__", "a": {"B1": "x-3"}, "expr": true}, {"t": "f(x) = x + 7: f⁻¹(x) = __B1__", "a": {"B1": "x-7"}, "expr": true}, {"t": "In general, f(x) = x + b: f⁻¹(x) = __B1__", "a": {"B1": "x-b"}, "expr": true, "accept": ["-b+x"]}], "sol": "Undo adding 3 by subtracting 3.\nUndo adding 7 by subtracting 7.\nUndo adding b by subtracting b."}, {"kind": "mcq", "text": "For which values of c does √x = c have a real solution?", "opts": ["c ≥ 0", "All real c", "c > 0 only", "c ≤ 0"], "correct": 0, "tag": "", "sol": "√x is never negative, so c < 0 gives no solution. c = 0 gives x = 0, and c > 0 gives x = c²."}, {"kind": "blank", "p": "Average rates of change of f(x) = √x.", "tag": "", "marks": "", "flat": [{"t": "From x = 0 to x = 1: __B1__", "a": {"B1": "1"}}, {"t": "From x = 1 to x = 4: __B1__", "a": {"B1": "1/3"}, "expr": "fl"}, {"t": "From x = 4 to x = 9: __B1__", "a": {"B1": "1/5"}, "expr": "fl"}, {"t": "Continue the pattern, from x = 9 to x = 16: __B1__", "a": {"B1": "1/7"}, "expr": "fl"}], "sol": "(1 − 0) ÷ (1 − 0) = 1.\n(2 − 1) ÷ (4 − 1) = {1/3}.\n(3 − 2) ÷ (9 − 4) = {1/5}.\n(4 − 3) ÷ (16 − 9) = {1/7}: the rate keeps getting smaller."}, {"kind": "mcq", "text": "If x is multiplied by 1,000, what happens to ∛x?", "opts": ["It is multiplied by 333", "It is multiplied by 100", "It is multiplied by 1,000", "It is multiplied by 10"], "correct": 3, "tag": "", "sol": "∛(1000x) = ∛1000 · ∛x = 10∛x. For example ∛8 = 2 and ∛8000 = 20."}, {"kind": "blank", "p": "Solve ∛x = a for different values of a.", "tag": "", "marks": "", "flat": [{"t": "a = 2: x = __B1__", "a": {"B1": "8"}}, {"t": "a = −3: x = __B1__", "a": {"B1": "-27"}}, {"t": "In general, x = __B1__", "a": {"B1": "a^3"}, "expr": true, "accept": ["a*a*a"]}], "sol": "2³ = 8.\n(−3)³ = −27.\nCubing both sides gives x = a³, for every real a."}]}, {"id": "s7", "label": "Assessment C", "sub": "Communicating", "slides": [{"kind": "mcq", "text": "An equation that has a variable in a radicand, such as √(x + 1) = 4, is called", "opts": ["a radical equation", "an inverse relation", "a cube root function", "a literal equation"], "correct": 0, "tag": "", "sol": "A radical equation has the variable inside a radical."}, {"kind": "blank", "p": "Complete the definition.", "tag": "", "marks": "", "flat": [{"t": "A value that comes out of solving but does not satisfy the original equation is an __B1__ solution.", "a": {"B1": "extraneous"}, "expr": "words"}], "sol": "Extraneous solutions often appear after squaring both sides of an equation."}, {"kind": "mcq", "text": "<b>Error analysis.</b> To solve √(x + 4) = x + 2, Leela squared both sides and wrote x + 4 = x² + 4. What is her mistake?", "opts": ["She should have cubed both sides", "She should have squared only the left side", "(x + 2)² = x² + 4x + 4; she forgot the middle term", "There is no mistake: (x + 2)² = x² + 4"], "correct": 2, "tag": "", "sol": "x + 4 = x² + 4x + 4 → x² + 3x = 0 → x = 0 or x = −3. Check: x = 0 works (√4 = 2); x = −3 gives √1 = 1 but −3 + 2 = −1 ✗, so the solution is x = 0."}, {"kind": "blank", "p": "Describe the steps for solving √(x − 1) + 3 = 7.", "tag": "", "marks": "", "flat": [{"t": "First __B1__ 3 from both sides (add / subtract).", "a": {"B1": "subtract"}, "expr": "words", "accept": ["subtracting", "take away"]}, {"t": "Then __B1__ both sides (square / cube).", "a": {"B1": "square"}, "expr": "words", "accept": ["squaring"]}, {"t": "x = __B1__", "a": {"B1": "17"}}], "sol": "This isolates the radical: √(x − 1) = 4.\nSquaring undoes the square root: x − 1 = 16.\nx = 17. Check: √16 + 3 = 7 ✓"}, {"kind": "mcq", "text": "Which statement is true?", "opts": ["Every cube root function y = a∛(x − h) + k (a ≠ 0) has domain and range all real numbers", "The inverse of every function is a function", "Every square root function has range y ≥ 0", "Squaring both sides of an equation never creates new solutions"], "correct": 0, "tag": "", "sol": "−√x has range y ≤ 0; x² has an inverse that is not a function; squaring √(x + 6) = x created the extraneous value −2. Cube roots are defined for every real number, so the first statement is true."}, {"kind": "blank", "p": "Complete each sentence about inverses.", "tag": "", "marks": "", "flat": [{"t": "The graph of f⁻¹ is the reflection of the graph of f in the line y = __B1__.", "a": {"B1": "x"}, "expr": "words"}, {"t": "The domain of f⁻¹ is the __B1__ of f.", "a": {"B1": "range"}, "expr": "words"}], "sol": "Switching coordinates (a, b) → (b, a) reflects points in y = x.\nInputs and outputs swap roles, so the domain of f⁻¹ is the range of f."}, {"kind": "mcq", "text": "<b>Error analysis.</b> Dev wrote: “The inverse of f(x) = x² is f⁻¹(x) = √x, for all real x.” Which reply is correct?", "opts": ["The inverse is 1 ÷ x², because f⁻¹ means a reciprocal", "He must first restrict f to x ≥ 0, because f(−2) = f(2)", "The inverse is −x², because an inverse reverses the sign", "He is right: √x undoes x² for every real x"], "correct": 1, "tag": "", "sol": "f(−2) = f(2) = 4, so without a restriction the inverse would send 4 to both −2 and 2. With x ≥ 0, f⁻¹(x) = √x for x ≥ 0."}, {"kind": "blank", "p": "Notation: f(x) = x + 4.", "tag": "", "marks": "", "flat": [{"t": "f⁻¹(2) = __B1__", "a": {"B1": "-2"}}, {"t": "1 ÷ f(2) = __B1__", "a": {"B1": "1/6"}, "expr": "fv"}], "sol": "f⁻¹(x) = x − 4, so f⁻¹(2) = −2.\nf(2) = 6, so 1 ÷ f(2) = {1/6}. This shows that f⁻¹(2) and 1 ÷ f(2) are different."}, {"kind": "mcq", "text": "Why must you check your answers after squaring both sides of an equation?", "opts": ["Squaring changes the domain to all real numbers, so any x works", "Squaring removes all the solutions, so they must be found again", "Squaring can turn a false equation such as −3 = 3 into a true one, 9 = 9", "Squaring always makes the answer negative, so the sign must be fixed"], "correct": 2, "tag": "", "sol": "If a = b then a² = b², but a² = b² is also true when a = −b. So some answers to the squared equation may not satisfy the original one."}]}, {"id": "s8", "label": "Assessment D", "sub": "Applying mathematics in real-life contexts", "slides": [{"kind": "mcq", "text": "The speed s (km/h) of a wave in shallow water of depth d metres is about s = 11√d. How fast is a wave where the water is 4 m deep?", "opts": ["176 km/h", "44 km/h", "22 km/h", "15 km/h"], "correct": 2, "tag": "", "sol": "s = 11√4 = 11(2) = 22 km/h. (44 uses 4 instead of √4; 176 multiplies by 4².)"}, {"kind": "blank", "p": "On a dry road, a car's speed s (mi/h) is related to its skid length d (ft) by s = √(24d).", "tag": "", "marks": "", "flat": [{"t": "Speed for a 150 ft skid: s = __B1__ mi/h", "a": {"B1": "60"}}, {"t": "Skid length for a car going 30 mi/h: d = __B1__ ft", "a": {"B1": "37.5"}}], "sol": "√(24 × 150) = √3600 = 60.\n30² = 900 = 24d, so d = 900 ÷ 24 = 37.5 ft.", "tools": ["calc"], "desmos": []}, {"kind": "mcq", "text": "A cube-shaped storage box has volume 3.375 m³. What is its edge length? (s = ∛V)", "opts": ["0.5 m", "1.84 m", "1.5 m", "1.125 m"], "correct": 2, "tag": "", "sol": "1.5³ = 3.375, so ∛3.375 = 1.5 m. (1.125 is 3.375 ÷ 3; 1.84 is √3.375.)", "tools": ["calc"], "desmos": []}, {"kind": "blank", "p": "The period T (seconds) of a pendulum of length L metres is about T = 2√L.", "tag": "", "marks": "", "flat": [{"t": "Period of a 4 m pendulum: T = __B1__ s", "a": {"B1": "4"}}, {"t": "A pendulum swings with a period of 3 s. Its length is L = __B1__ m", "a": {"B1": "2.25"}}], "sol": "2√4 = 2(2) = 4 s.\n2√L = 3 → √L = 1.5 → L = 2.25 m.", "tools": ["desmos"], "desmos": ["y=2\\sqrt{x}"]}, {"kind": "mcq", "text": "A travel app converts US dollars to rupees with r = 83d. Which inverse gives dollars from rupees, and how many dollars is ₹4,150?", "opts": ["d = {83/r}; $0.02", "d = r − 83; $4,067", "d = 83r; $344,450", "d = {r/83}; $50"], "correct": 3, "tag": "", "sol": "Divide both sides by 83: d = r ÷ 83. ₹4,150 ÷ 83 = $50."}, {"kind": "blank", "p": "A phone plan costs $10 a month plus $0.05 per minute, so the cost for m minutes is C = 0.05m + 10.", "tag": "", "marks": "", "flat": [{"t": "Solve for m: m = __B1__ (in terms of C)", "a": {"B1": "(C-10)/0.05"}, "expr": true, "accept": ["20C-200", "20(C-10)"]}, {"t": "A monthly bill of $18 means __B1__ minutes were used", "a": {"B1": "160"}}], "sol": "C − 10 = 0.05m, so m = (C − 10) ÷ 0.05 = 20C − 200.\n(18 − 10) ÷ 0.05 = 8 ÷ 0.05 = 160 minutes.", "tools": ["calc"], "desmos": []}, {"kind": "mcq", "text": "<b>Is this reasonable?</b> The side x (metres) of a square garden satisfies √(x + 10) = x − 2. Lena squares, gets x² − 5x − 6 = 0, finds x = 6 or x = −1, and says the side could be 6 m or −1 m. What should she conclude?", "opts": ["Only 6 m: x = −1 fails the check and is a negative length", "Neither works, so the garden cannot exist at all", "Both answers are reasonable because both solve the quadratic", "Only −1 m works, because it is the smaller value"], "correct": 0, "tag": "", "sol": "Check x = 6: √16 = 4 and 6 − 2 = 4 ✓. Check x = −1: √9 = 3 but −1 − 2 = −3 ✗. The side is 6 m."}, {"kind": "blank", "p": "A stone falls h feet in t = {1/4}√h seconds.", "tag": "", "marks": "", "flat": [{"t": "Time to fall 81 ft: t = __B1__ s", "a": {"B1": "2.25"}}, {"t": "Height for a 3-second fall: h = __B1__ ft", "a": {"B1": "144"}}], "sol": "{1/4}√81 = {9/4} = 2.25 s.\n{1/4}√h = 3 → √h = 12 → h = 144 ft."}, {"kind": "mcq", "text": "A small wind turbine produces P watts in a wind of speed v (m/s), where v = ∛({P/2}). What wind speed produces 250 watts?", "opts": ["62.5 m/s", "5 m/s", "125 m/s", "25 m/s"], "correct": 1, "tag": "", "sol": "v = ∛(250 ÷ 2) = ∛125 = 5 m/s. (125 m/s forgets the cube root; 62.5 divides by 4.)", "tools": ["calc"], "desmos": []}]}];
/* ================= build slide lists ================= */
var SLIDES = {}; SECTIONS.forEach(function(sec){ SLIDES[sec.id]=sec.slides; });
var TAB_DEFS = SECTIONS.map(function(sec){ return {id:sec.id, label:sec.label, sub:sec.sub}; });

/* ================= state ================= */
function blankItem(slide){
  if(slide.kind==='mcq'||slide.kind==='ar'){
    return {status:'unanswered', attempts:0, choice:undefined};
  }
  return {status:'unanswered', curStep:0, stepStates: slide.flat.map(function(){ return {status:'unanswered', attempts:0, inputs:{}}; })};
}
function defaultState(){
  var s={tabs:{}};
  TAB_DEFS.forEach(function(td){
    s.tabs[td.id] = { idx:0, maxReached:0, items: SLIDES[td.id].map(function(sl){ return blankItem(sl); }) };
  });
  return s;
}
var appState = {mode:null, learning:null, quiz:null};
var state = null;      // alias for appState[appState.mode]
var MODE = null;
var activeTab=TAB_DEFS[0].id;

function setMode(m){
  appState.mode = m;
  if(!appState[m]) appState[m] = defaultState();
  state = appState[m];
  MODE = m;
}
/* ================= student accounts (saved on this device) ================= */
var SHEET_KEY='sopaan-bim-ch10';
var ACC_KEY='sopaan-students-v1';
var storageOK=true;
var MEM={};
function lsGet(k){ var r=null; try{ r=localStorage.getItem(k); }catch(e){ storageOK=false; }
  if(r===null||r===undefined) r=MEM[k]||null; try{ return r?JSON.parse(r):null; }catch(e){ return null; } }
function lsSet(k,v){ var j=JSON.stringify(v); MEM[k]=j; try{ localStorage.setItem(k,j); return true; }catch(e){ storageOK=false; return false; } }
try{ localStorage.setItem('sopaan-probe','1'); localStorage.removeItem('sopaan-probe'); }catch(e){ storageOK=false; }
function hashPin(pin,salt){ var h=2166136261, str=salt+'|'+pin; for(var i=0;i<str.length;i++){ h^=str.charCodeAt(i); h=Math.imul(h,16777619)>>>0; } return h.toString(36); }
function accKey(name,roll){ return (name.trim().toLowerCase().replace(/\s+/g,' ')+'#'+roll.trim().toLowerCase()); }
function accounts(){ return lsGet(ACC_KEY)||{students:{}}; }
var student=null; // {key,name,roll}
var records=[];   // finished-tab history for this student on this sheet
function progKey(){ return SHEET_KEY+'::'+student.key; }

function loadState(){
  appState = {mode:null, learning:null, quiz:null}; records=[]; activeTab=TAB_DEFS[0].id;
  var saved=lsGet(progKey());
  if(!saved) return;
  try{
    ['learning','quiz'].forEach(function(m){
      if(saved[m] && saved[m].tabs){
        var fresh = defaultState();
        TAB_DEFS.forEach(function(td){
          if(saved[m].tabs[td.id] && saved[m].tabs[td.id].items && saved[m].tabs[td.id].items.length===SLIDES[td.id].length){
            fresh.tabs[td.id] = saved[m].tabs[td.id];
          }
        });
        appState[m] = fresh;
      }
    });
    if(saved.mode==='learning' || saved.mode==='quiz') appState.mode = saved.mode;
    if(saved.activeTab && TAB_DEFS.some(function(t){ return t.id===saved.activeTab; })) activeTab = saved.activeTab;
    if(Array.isArray(saved.records)) records = saved.records;
  }catch(e){}
}
function saveState(){
  if(!student) return;
  lsSet(progKey(), {mode:appState.mode, learning:appState.learning, quiz:appState.quiz, activeTab:activeTab, records:records, updated:Date.now()});
  var acc=accounts(); if(acc.students[student.key]){ acc.students[student.key].last=Date.now(); lsSet(ACC_KEY,acc); }
}
function addRecord(mode, tabId, correct, revealed, skipped, total){
  records.unshift({at:Date.now(), mode:mode, tab:tabId, correct:correct, revealed:revealed, skipped:skipped, total:total});
  if(records.length>60) records.length=60;
  saveState();
}
function fmtDate(ms){ try{ return new Date(ms).toLocaleString(undefined,{day:'numeric',month:'short',hour:'2-digit',minute:'2-digit'}); }catch(e){ return ''; } }

function renderWho(){
  var el=document.getElementById('whoBar');
  if(!student){ el.hidden=true; el.innerHTML=''; return; }
  el.hidden=false;
  el.innerHTML='Signed in as <b>'+esc(student.name)+'</b> · Roll '+esc(student.roll)+
    ' <button id="btnRecord">My record</button> <button id="btnSignOut">Sign out</button>';
  document.getElementById('btnRecord').addEventListener('click', renderRecord);
  document.getElementById('btnSignOut').addEventListener('click', signOut);
}
function signOut(){
  saveState(); student=null; state=null; MODE=null;
  var acc=accounts(); delete acc.current; lsSet(ACC_KEY,acc);
  document.getElementById('modePill').hidden=true;
  renderWho(); renderLogin();
}
function signIn(key){
  var acc=accounts(); var st=acc.students[key]; if(!st) return;
  student={key:key, name:st.name, roll:st.roll};
  acc.current=key; st.last=Date.now(); lsSet(ACC_KEY,acc);
  loadState(); renderWho();
  if(appState.mode==='learning' || appState.mode==='quiz'){
    setMode(appState.mode); document.getElementById('modePill').hidden=false; updateModePill();
    showChrome(true); buildTabbar(); renderSlide();
    showToast('Welcome back, '+st.name.split(' ')[0]+'. Picking up where you left off.');
  } else {
    renderModePicker();
  }
}
function renderLogin(msg){
  showChrome(false);
  var acc=accounts(); var keys=Object.keys(acc.students).sort(function(a,b){ return (acc.students[b].last||0)-(acc.students[a].last||0); });
  var h='<div class="login-card"><h2>Student sign-in</h2>'+
    '<p class="lead">Sign in to save your answers, see your record and continue where you left off next time.</p>';
  if(!storageOK) h+='<div class="login-err">This browser is blocking saved data (for example, a private window). You can still practise, but progress will not be kept after you close the page.</div>';
  if(msg) h+='<div class="login-err">'+esc(msg)+'</div>';
  if(keys.length){
    h+='<div class="known"><span class="known-label">Continue as</span>';
    keys.slice(0,6).forEach(function(k){ var st=acc.students[k];
      h+='<button class="known-btn" data-k="'+esc(k)+'"><span>'+esc(st.name)+' <small>· Roll '+esc(st.roll)+'</small></span><small>'+(st.last?'Last active '+fmtDate(st.last):'')+'</small></button>'; });
    h+='</div>';
  }
  h+='<form id="loginForm" novalidate>'+
    '<div class="fld"><label for="lgName">Full name</label><input id="lgName" autocomplete="name" required></div>'+
    '<div class="fld-row"><div class="fld"><label for="lgRoll">Roll no.</label><input id="lgRoll" required></div>'+
    '<div class="fld"><label for="lgPin">4-digit PIN</label><input id="lgPin" type="password" inputmode="numeric" maxlength="4" autocomplete="off" required></div></div>'+
    '<button class="btn btn-primary" type="submit" style="width:100%;">Sign in</button>'+
    '<p class="login-note">New here? Enter your name, roll no. and a PIN you will remember, and your profile is created. Progress is saved on this device, so use the same device and browser to continue.</p>'+
    '</form></div>';
  var wrap=document.getElementById('wrap'); wrap.innerHTML=h;
  wrap.querySelectorAll('.known-btn').forEach(function(b){
    b.addEventListener('click', function(){
      var st=accounts().students[b.dataset.k];
      document.getElementById('lgName').value=st.name; document.getElementById('lgRoll').value=st.roll;
      document.getElementById('lgPin').focus();
    });
  });
  document.getElementById('loginForm').addEventListener('submit', function(e){
    e.preventDefault();
    var name=document.getElementById('lgName').value.trim(), roll=document.getElementById('lgRoll').value.trim(), pin=document.getElementById('lgPin').value.trim();
    if(!name||!roll){ renderLoginErr('Enter your name and roll no.'); return; }
    if(!/^\d{4}$/.test(pin)){ renderLoginErr('Your PIN must be exactly 4 digits.'); return; }
    var k=accKey(name,roll); var acc=accounts();
    if(acc.students[k]){
      if(acc.students[k].pin!==hashPin(pin,k)){ renderLoginErr('That PIN does not match this name and roll no. Try again.'); return; }
    } else {
      acc.students[k]={name:name.replace(/\s+/g,' '), roll:roll, pin:hashPin(pin,k), created:Date.now()};
      lsSet(ACC_KEY,acc);
    }
    signIn(k);
  });
}
function renderLoginErr(m){
  var n=document.getElementById('lgName').value, r=document.getElementById('lgRoll').value;
  renderLogin(m); document.getElementById('lgName').value=n; document.getElementById('lgRoll').value=r; document.getElementById('lgPin').focus();
}
function tabSummary(m){
  var st=appState[m]; if(!st) return null;
  return TAB_DEFS.map(function(td){
    var items=st.tabs[td.id].items, n=items.length;
    var c=items.filter(function(i){return i.status==='correct';}).length;
    var done=items.filter(function(i){return i.status!=='unanswered';}).length;
    return {label:td.label, n:n, done:done, correct:c};
  });
}
function renderRecord(){
  showChrome(false);
  var tabLabel=function(id){ var t=TAB_DEFS.find(function(x){return x.id===id;}); return t?t.label:id; };
  var h='<div class="rec-card"><h2>'+esc(student.name)+'’s record</h2><p class="rec-empty" style="margin:0 0 12px;">Roll '+esc(student.roll)+' · Radical Functions and Equations</p>';
  ['learning','quiz'].forEach(function(m){
    var sum=tabSummary(m);
    h+='<h3>'+(m==='learning'?'📘 Learning Sheet':'📝 Quiz Mode')+'</h3>';
    if(!sum){ h+='<p class="rec-empty">Not started yet.</p>'; return; }
    h+='<div class="rec-table-wrap"><table class="rec-table"><thead><tr><th>Section</th><th>Progress</th><th>Correct first time</th></tr></thead><tbody>';
    sum.forEach(function(r){ var pct=Math.round(r.done/r.n*100);
      h+='<tr><td>'+r.label+'</td><td><span class="rec-bar"><i style="width:'+pct+'%"></i></span>'+r.done+' / '+r.n+'</td><td>'+(m==='quiz'?'—':r.correct+' / '+r.n)+'</td></tr>'; });
    h+='</tbody></table></div>';
  });
  h+='</div><div class="rec-card"><h3>Finished sections</h3>';
  if(!records.length){ h+='<p class="rec-empty">No sections finished yet. Each time you finish a tab, your score is recorded here.</p>'; }
  else {
    h+='<div class="rec-table-wrap"><table class="rec-table"><thead><tr><th>When</th><th>Mode</th><th>Section</th><th>Score</th></tr></thead><tbody>';
    records.forEach(function(r){ h+='<tr><td>'+fmtDate(r.at)+'</td><td>'+(r.mode==='quiz'?'Quiz':'Learning')+'</td><td>'+tabLabel(r.tab)+'</td><td>'+r.correct+' / '+r.total+(r.mode==='learning'?' <span class="rec-empty">('+r.revealed+' revealed, '+r.skipped+' skipped)</span>':'')+'</td></tr>'; });
    h+='</tbody></table></div>';
  }
  h+='</div><button class="btn btn-primary" id="btnBack">'+(MODE?'Back to practice':'Choose a mode')+'</button>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('btnBack').addEventListener('click', function(){
    if(MODE){ showChrome(true); buildTabbar(); renderSlide(); } else renderModePicker();
  });
  window.scrollTo({top:0});
}

/* ================= tab bar ================= */
function buildTabbar(){
  var el=document.getElementById('tabbar');
  el.innerHTML = '<button class="tab-btn'+(activeTab==='theory'?' active':'')+'" data-tab="theory">Theory<span class="tab-count">notes</span></button>' + TAB_DEFS.map(function(t){
    return '<button class="tab-btn'+(t.id===activeTab?' active':'')+'" data-tab="'+t.id+'">'+t.label+'<span class="tab-count">'+SLIDES[t.id].length+'</span></button>';
  }).join('') + '<button class="tab-btn'+(activeTab==='report'?' active':'')+'" data-tab="report">📊 Report<span class="tab-count">pie</span></button>';
  el.querySelectorAll('.tab-btn').forEach(function(btn){
    btn.addEventListener('click', function(){ activeTab=btn.dataset.tab; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); });
  });
}

/* ================= rendering ================= */
function canProceed(item){ return item.status==='correct'||item.status==='revealed'||item.status==='skipped'; }

function renderSlide(){
  if(!state.tabs[activeTab]){ activeTab=TAB_DEFS[0].id; }
  var ts = state.tabs[activeTab];
  var slides = SLIDES[activeTab];
  if(ts.idx>=slides.length||ts.idx<0) ts.idx=0;
  var idx = ts.idx;
  var slide = slides[idx];
  var item = ts.items[idx];

  var tdef=TAB_DEFS.find(function(t){return t.id===activeTab;});
  document.getElementById('spLabel').textContent = tdef.label+' · Question '+(idx+1)+' of '+slides.length;
  document.getElementById('secSub').textContent = tdef.label+' — '+tdef.sub;
  document.getElementById('spFill').style.width = Math.round(((idx)/(Math.max(slides.length-1,1)))*100)+'%';

  var h='<div class="qcard">';
  if(slide.kind==='mcq' || slide.kind==='ar'){
    h += renderChoiceBody(slide, item, idx);
  } else {
    h += renderBlankBody(slide, item, idx);
  }
  h += '<div class="feedback" id="feedbackBox"></div>';
  if(MODE==='learning' && (item.status==='correct'||item.status==='revealed')) h += solutionHTML(slide);
  h += '</div>';

  document.getElementById('wrap').innerHTML = h;
  wireSlideEvents(slide, item, idx);
  restoreFeedback(item);
  renderNavbar(item);
  updateFab();
  saveState();
}

function solutionHTML(slide){
  if(!slide.sol) return '';
  return '<div class="solution"><div class="sol-h">Solution</div>'+slide.sol.split('\n').map(function(l){ return '<div class="sol-line">'+fr(esc(l))+'</div>'; }).join('')+'</div>';
}
var LETTERS=['a','b','c','d','e','f'];
function chosenHTML(slide,item){
  var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
  if(item.choice===undefined) return '';
  var ok=item.choice===slide.correct;
  var h='<div class="chosen '+(ok?'ok':'bad')+'"><b>Your answer:</b> ('+LETTERS[item.choice]+') '+fr(esc(opts[item.choice]))+(ok?' ✓':' ✗')+'</div>';
  if(!ok) h+='<div class="chosen ok"><b>Correct answer:</b> ('+LETTERS[slide.correct]+') '+fr(esc(opts[slide.correct]))+'</div>';
  return h;
}
function renderChoiceBody(slide, item, idx){
  var h='<div class="qhead"><div class="qnum">'+(idx+1)+'</div>';
  if(slide.kind==='mcq'){
    h += '<div class="qtext">'+fr(esc(slide.text))+(slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  } else {
    h += '<div class="qtext"><span class="qtag" style="margin-left:0;margin-right:6px;">A / R</span>Assertion (A): '+fr(esc(slide.a))+'<br>Reason (R): '+fr(esc(slide.r))+(slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  }
  h += '</div>';
  if(slide.fig) h += '<div class="fig">'+slide.fig+'</div>';
  var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
  if(MODE==='quiz') h += '<div class="quiz-hint">Quiz mode — pick an option. The correct answer is revealed once you finish this tab.</div>';
  var locked = MODE==='learning' && (item.status==='correct' || item.status==='revealed');
  h += '<div class="options">';
  opts.forEach(function(opt,i){
    var cls='opt';
    if(locked){
      if(i===slide.correct) cls+=' is-correct';
      else if(item.choice===i) cls+=' is-wrong';
      cls+=' locked';
    }
    if(item.choice===i) cls+=' is-chosen';
    h += '<label class="'+cls+'"><input type="radio" name="choice" value="'+i+'" '+(item.choice===i?'checked':'')+' '+(locked?'disabled':'')+'> <span class="opt-l">('+LETTERS[i]+')</span> <span class="opt-t">'+fr(esc(opt))+'</span>'+(item.choice===i?'<span class="opt-tag">'+(locked?(i===slide.correct?'Your answer ✓':'Your answer ✗'):'Selected')+'</span>':'')+'</label>';
  });
  h += '</div>';
  if(locked) h += chosenHTML(slide,item);
  return h;
}

function renderBlankBody(slide, item, idx){
  var h='<div class="qhead"><div class="qnum">'+(idx+1)+'</div><div class="qtext">';
  if(slide.kind==='case'){ h += '<b>'+esc(slide.title)+'.</b> '+esc(slide.body); }
  else { var pp=fr(esc(slide.p)).split('\n'); h += pp[0]+pp.slice(1).map(function(x){return '<span class="datline">'+x+'</span>';}).join(''); }
  h += (slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  if(slide.marks) h += '<div class="marks-pill">'+slide.marks+'</div>';
  h += '</div>';
  if(slide.fig) h += '<div class="fig">'+slide.fig+'</div>';

  var total = slide.flat.length;
  var hasExpr = slide.flat.some(function(s){ return s.expr===true; });
  var hasFrac = slide.flat.some(function(s){ return ['fv','fe','fl','fm','fi','flist'].indexOf(s.expr)>=0; });
  var blankCount=0; slide.flat.forEach(function(s){ blankCount+=Object.keys(s.a).length; });

  if(MODE==='quiz'){
    h += '<div class="step-badge">'+blankCount+' blank'+(blankCount===1?'':'s')+' in this question</div>';
    h += '<div class="quiz-hint">Quiz mode — fill in what you can. Correct answers are revealed once you finish this tab.</div>';
    if(hasFrac) h += '<div class="quiz-hint">Type fractions like <b>3/4</b> and mixed numbers like <b>2 3/4</b> (whole number, space, fraction).</div>';
    if(hasExpr) h += '<div class="quiz-hint">Type answers like <b>2x-5</b>, <b>x^2-4</b> or <b>3+2i</b>. Use ^ for powers, | | for absolute value and pi for π. Any equivalent form is accepted.</div>';
    h += '<div class="steps">';
    for(var qi=0; qi<total; qi++){
      var qstep = slide.flat[qi];
      var qss = item.stepStates[qi];
      if(qstep.partLabel) h += '<div class="subpart-label">'+esc(qstep.partLabel)+'</div>';
      if(qstep.orDivider) h += '<div class="or-divider">OR</div>';
      var qline = fr(qstep.t);
      Object.keys(qstep.a).forEach(function(bkey){
        var val = qss.inputs[bkey]||'';
        var inp='<input class="blank-input'+(['fv','fe','fl','fm','fi','dec'].indexOf(qstep.expr)>=0?' fr':(qstep.expr==='flist'||qstep.expr==='dlist'||qstep.expr==='glist')?' wide':qstep.expr===true?' expr':(qstep.expr==='words'||qstep.expr==='list'||qstep.expr==='expanded'||qstep.expr==='set'||qstep.expr==='primes'||qstep.expr==='trans'||qstep.expr==='rot'?' wide':''))+'" data-step="'+qi+'" data-bkey="'+bkey+'" value="'+esc(val)+'">';
        qline = qline.replace('__'+bkey+'__', inp);
      });
      if(qstep.fig) h += '<div class="fig">'+qstep.fig+'</div>';
      h += '<div class="step-line">'+qline+'</div>';
    }
    h += '</div>';
    return h;
  }

  if(hasFrac) h += '<div class="quiz-hint">Type fractions like <b>3/4</b> and mixed numbers like <b>2 3/4</b> (whole number, space, fraction).</div>';
  if(hasExpr) h += '<div class="quiz-hint">Type answers like <b>2x-5</b>, <b>x^2-4</b> or <b>3+2i</b>. Use ^ for powers, | | for absolute value and pi for π. Any equivalent form is accepted.</div>';
  var locked = item.status==='correct' || item.status==='revealed';
  var upto = locked ? total-1 : item.curStep;
  h += '<div class="step-badge">Step '+(Math.min(item.curStep,total-1)+1)+' of '+total+'</div>';
  h += '<div class="steps">';
  for(var i=0;i<=upto;i++){
    var step = slide.flat[i];
    var ss = item.stepStates[i];
    if(step.partLabel) h += '<div class="subpart-label">'+esc(step.partLabel)+'</div>';
    if(step.orDivider) h += '<div class="or-divider">OR</div>';
    var resolved = ss.status==='correct' || ss.status==='revealed';
    var line = fr(step.t);
    Object.keys(step.a).forEach(function(bkey){
      var fs = ss.inputs['fs_'+bkey];
      var cls = fs==='correct'?'is-correct':(fs==='wrong'?'is-wrong':'');
      var val = ss.inputs[bkey]||'';
      var dis = resolved ? 'disabled':'';
      var inp='<input class="blank-input '+cls+(['fv','fe','fl','fm','fi','dec'].indexOf(step.expr)>=0?' fr':(step.expr==='flist'||step.expr==='dlist'||step.expr==='glist')?' wide':step.expr===true?' expr':(step.expr==='words'||step.expr==='list'||step.expr==='expanded'||step.expr==='set'||step.expr==='primes'||step.expr==='trans'||step.expr==='rot'?' wide':''))+'" data-step="'+i+'" data-bkey="'+bkey+'" value="'+esc(val)+'" '+dis+'>';
      line = line.replace('__'+bkey+'__', inp);
    });
    if(step.fig) h += '<div class="fig">'+step.fig+'</div>';
    h += '<div class="step-line'+(resolved?' resolved':'')+'">'+line+'</div>';
    if(ss.status==='revealed'){
      var reveals=[];
      Object.keys(step.a).forEach(function(bkey){ reveals.push(bkey+' = '+esc(step.a[bkey])); });
      h += '<div class="reveal-note">correct: '+reveals.join(', ')+'</div>';
    }
  }
  h += '</div>';
  return h;
}

var __flash=null;
function restoreFeedback(item){
  var fb=document.getElementById('feedbackBox'); if(!fb) return;
  if(__flash){ fb.className='feedback show '+__flash.c; fb.innerHTML=__flash.h; __flash=null; return; }
  if(MODE==='quiz'){ fb.className='feedback'; fb.innerHTML=''; return; }
  if(item.status==='correct'){ fb.className='feedback show ok'; fb.innerHTML='<b>All done — correct!</b>'; }
  else if(item.status==='revealed'){ fb.className='feedback show reveal'; fb.innerHTML='<b>Answer revealed above.</b> Move on whenever you’re ready.'; }
  else if(item.status==='skipped'){ fb.className='feedback show retry'; fb.innerHTML='Skipped — you can answer it now and press <b>Check</b>, or come back later from the Question Palette.'; }
  else { fb.className='feedback'; fb.innerHTML=''; }
}

function slideIsAnswered(slide,item){
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice!==undefined;
  return item.stepStates.some(function(ss){ return Object.keys(ss.inputs).some(function(k){ return k.indexOf('fs_')!==0 && ss.inputs[k] && String(ss.inputs[k]).trim()!==''; }); });
}
function renderNavbar(item){
  var ts = state.tabs[activeTab];
  var slides = SLIDES[activeTab];
  var slide = slides[ts.idx];
  var isLast = ts.idx === slides.length-1;
  var h='';
  h += '<button class="btn" id="btnPrev" '+(ts.idx===0?'disabled':'')+'>&larr; Previous</button>';

  if(MODE==='quiz'){
    h += '<button class="btn" id="btnSkip">Skip</button>';
    h += '<span class="spacer"></span>';
    h += '<button class="btn btn-primary" id="btnNext">'+(isLast?'Finish':'Next →')+'</button>';
  } else {
    h += '<button class="btn" id="btnSkip" '+(item.status!=='unanswered'?'disabled':'')+'>Skip</button>';
    h += '<span class="spacer"></span>';
    h += '<button class="btn btn-primary" id="btnCheck" '+((item.status!=='unanswered'&&item.status!=='skipped')?'disabled':'')+'>Check</button>';
    h += '<button class="btn btn-primary" id="btnNext" '+(canProceed(item)?'':'disabled')+'>'+(isLast?'Finish':'Next →')+'</button>';
  }
  document.getElementById('navbarInner').innerHTML = h;

  document.getElementById('btnPrev').addEventListener('click', function(){ if(ts.idx>0){ ts.idx--; renderSlide(); } });

  if(MODE==='quiz'){
    document.getElementById('btnSkip').addEventListener('click', function(){
      item.status='skipped';
      advanceQuiz(ts, slides);
    });
    document.getElementById('btnNext').addEventListener('click', function(){
      item.status = slideIsAnswered(slide,item) ? 'answered' : 'unanswered';
      advanceQuiz(ts, slides);
    });
  } else {
    document.getElementById('btnSkip').addEventListener('click', function(){
      if(item.status==='unanswered'){ item.status='skipped'; renderSlide(); }
    });
    document.getElementById('btnNext').addEventListener('click', function(){
      if(!canProceed(item)) return;
      if(ts.idx < slides.length-1){ ts.idx++; ts.maxReached=Math.max(ts.maxReached, ts.idx); renderSlide(); }
      else { renderFinished(); }
    });
    document.getElementById('btnCheck').addEventListener('click', function(){ handleCheck(); });
  }
}
function advanceQuiz(ts, slides){
  if(ts.idx < slides.length-1){ ts.idx++; ts.maxReached=Math.max(ts.maxReached, ts.idx); renderSlide(); }
  else { renderFinished(); }
}

function wireSlideEvents(slide, item, idx){
  document.querySelectorAll('input[type="radio"][name="choice"]').forEach(function(r){
    r.addEventListener('change', function(){ item.choice=parseInt(r.value,10); saveState();
      document.querySelectorAll('.opt').forEach(function(l){ l.classList.remove('is-chosen'); var t=l.querySelector('.opt-tag'); if(t) t.remove(); });
      var lab=r.closest('.opt'); lab.classList.add('is-chosen'); var tg=document.createElement('span'); tg.className='opt-tag'; tg.textContent='Selected'; lab.appendChild(tg); });
  });
  document.querySelectorAll('.blank-input').forEach(function(inp){
    inp.addEventListener('input', function(){
      var si=parseInt(inp.dataset.step,10), bk=inp.dataset.bkey;
      item.stepStates[si].inputs[bk]=inp.value;
      saveState();
    });
  });
}

function handleCheck(){
  var ts = state.tabs[activeTab];
  var slide = SLIDES[activeTab][ts.idx];
  var item = ts.items[ts.idx];
  if(item.status==='skipped') item.status='unanswered';
  var fb = document.getElementById('feedbackBox');

  if(slide.kind==='mcq' || slide.kind==='ar'){
    if(item.choice===undefined){ fb.className='feedback show err'; fb.innerHTML='Please choose an option first.'; return; }
    var ok = item.choice===slide.correct;
    if(ok){
      item.status='correct'; playSuccess();
      fb.className='feedback show ok'; fb.innerHTML='<b>Correct!</b>';
    } else {
      item.attempts=(item.attempts||0)+1;
      if(item.attempts>=2){ item.status='revealed'; playReveal(); }
      else { playWrong(); fb.className='feedback show retry'; fb.innerHTML='<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'; __flash={c:'retry',h:'<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'}; }
    }
    renderSlide();
    return;
  }

  // blank / case
  var step = slide.flat[item.curStep];
  var ss = item.stepStates[item.curStep];
  var blanks = Object.keys(step.a);
  var missing = blanks.some(function(k){ return !ss.inputs[k] || String(ss.inputs[k]).trim()===''; });
  if(missing){ fb.className='feedback show err'; fb.innerHTML='Fill in every blank in this step before checking.'; return; }

  var allGood=true;
  blanks.forEach(function(k){
    var good=answerMatches(ss.inputs[k], step.a[k], step.accept, step.expr);
    ss.inputs['fs_'+k]=good?'correct':'wrong';
    if(!good) allGood=false;
  });

  if(allGood){
    ss.status='correct'; playSuccess();
    advanceStepOrFinish(item, slide);
  } else {
    ss.attempts=(ss.attempts||0)+1;
    if(ss.attempts>=2){
      ss.status='revealed'; playReveal();
      advanceStepOrFinish(item, slide);
    } else {
      playWrong();
      fb.className='feedback show retry';
      fb.innerHTML='<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'; __flash={c:'retry',h:'<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'};
      renderSlide();
      return;
    }
  }
  renderSlide();
}

function advanceStepOrFinish(item, slide){
  var total = slide.flat.length;
  var hasExpr = slide.flat.some(function(s){ return s.expr===true; });
  var hasFrac = slide.flat.some(function(s){ return ['fv','fe','fl','fm','fi','flist'].indexOf(s.expr)>=0; });
  if(item.curStep < total-1){
    item.curStep++;
  } else {
    var anyRevealed = item.stepStates.some(function(ss){ return ss.status==='revealed'; });
    item.status = anyRevealed ? 'revealed' : 'correct';
  }
}

/* ================= palette ================= */
var overlay=document.getElementById('overlay');
function statusOf(tabId,i){
  var ts=state.tabs[tabId];
  if(i>ts.maxReached) return 'locked';
  if(i===ts.idx) return 'current';
  return ts.items[i].status==='unanswered' ? 'locked' : ts.items[i].status;
}
function buildPalette(){
  var slides=SLIDES[activeTab];
  document.getElementById('paletteTitle').textContent = TAB_DEFS.find(function(t){return t.id===activeTab;}).label+' · Question palette';
  var body=document.getElementById('paletteBody');
  var html='';
  for(var i=0;i<slides.length;i++){
    html += '<div class="chip" data-status="'+statusOf(activeTab,i)+'" data-idx="'+i+'">'+(i+1)+'</div>';
  }
  body.innerHTML = html;
  body.querySelectorAll('.chip').forEach(function(chip){
    chip.addEventListener('click', function(){
      var i=parseInt(chip.dataset.idx,10);
      var ts=state.tabs[activeTab];
      if(i>ts.maxReached){ showToast('Finish the earlier questions to unlock this one.'); return; }
      ts.idx=i; closePalette(); renderSlide();
    });
  });
}
function openPalette(){ buildPalette(); overlay.classList.add('show'); }
function closePalette(){ overlay.classList.remove('show'); }
var toastTimer;
function showToast(msg){
  var t=document.getElementById('toast'); t.textContent=msg; t.classList.add('show');
  clearTimeout(toastTimer); toastTimer=setTimeout(function(){ t.classList.remove('show'); },2200);
}
document.getElementById('paletteFab').addEventListener('click', openPalette);
document.getElementById('paletteClose').addEventListener('click', closePalette);
overlay.addEventListener('click', function(e){ if(e.target===overlay) closePalette(); });

function updateFab(){
  var slides=SLIDES[activeTab];
  var done=state.tabs[activeTab].items.filter(function(it){ return it.status==='correct'||it.status==='revealed'||it.status==='skipped'; }).length;
  document.getElementById('fabBadge').textContent = done+'/'+slides.length;
}

/* ================= overall progress + finish ================= */
function updateChapterProgress(){
  var total=0, done=0;
  TAB_DEFS.forEach(function(td){
    state.tabs[td.id].items.forEach(function(it){
      total++;
      if(it.status==='correct'||it.status==='revealed'||it.status==='skipped') done++;
    });
  });
  var pct = total>0 ? Math.round((done/total)*100) : 0;
  document.getElementById('cpFill').style.width=pct+'%';
  document.getElementById('cpLabel').textContent=pct+'% complete';
}
function isSlideCorrect(tabId,i){
  var slide=SLIDES[tabId][i], item=state.tabs[tabId].items[i];
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice===slide.correct;
  return slide.flat.every(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).every(function(k){ return answerMatches(ss.inputs[k], step.a[k], step.accept, step.expr); });
  });
}
function isSlideAttempted(tabId,i){
  var slide=SLIDES[tabId][i], item=state.tabs[tabId].items[i];
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice!==undefined;
  return slide.flat.some(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).some(function(k){ return ss.inputs[k] && String(ss.inputs[k]).trim()!==''; });
  });
}
function slideLabel(slide){
  var t = slide.kind==='case' ? slide.title : (slide.kind==='ar' ? slide.a : (slide.p||slide.text||''));
  t = String(t);
  return t.length>90 ? t.slice(0,90)+'…' : t;
}
function slideAnswerText(slide, item, correctSide){
  if(slide.kind==='mcq'||slide.kind==='ar'){
    var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
    if(correctSide) return '('+LETTERS[slide.correct]+') '+opts[slide.correct];
    return item.choice!==undefined ? '('+LETTERS[item.choice]+') '+opts[item.choice] : '— not attempted —';
  }
  return slide.flat.map(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).map(function(k){
      return correctSide ? step.a[k] : (ss.inputs[k] || '—');
    }).join(', ');
  }).join('  |  ');
}

function renderFinished(){
  if(MODE==='quiz'){ renderQuizResults(); return; }
  var ts=state.tabs[activeTab];
  var correct=ts.items.filter(function(i){return i.status==='correct';}).length;
  var revealed=ts.items.filter(function(i){return i.status==='revealed';}).length;
  var skipped=ts.items.filter(function(i){return i.status==='skipped';}).length;
  var h='<div class="qcard done-card"><div class="big">✨</div><h2>Tab complete</h2>';
  h+='<p style="color:var(--ink-soft);font-size:14px;">You worked through all '+ts.items.length+' questions in this tab.</p>';
  if(!ts.recorded){ ts.recorded=true; addRecord('learning', activeTab, correct, revealed, skipped, ts.items.length); }
  h+='<div class="score-pills">'+
     '<span class="score-pill" style="background:var(--success-soft);color:var(--success);">'+correct+' correct</span>'+
     '<span class="score-pill" style="background:var(--danger-soft);color:var(--danger);">'+revealed+' revealed</span>'+
     '<span class="score-pill" style="background:var(--gold-soft);color:var(--retry-text);">'+skipped+' skipped</span></div>'+
     '<button class="btn btn-primary" id="btnReview">Review from question 1</button></div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  document.getElementById('btnReview').addEventListener('click', function(){ ts.idx=0; ts.recorded=false; renderSlide(); });
  updateChapterProgress(); saveState();
}

function renderQuizResults(){
  var ts=state.tabs[activeTab];
  var slides=SLIDES[activeTab];
  var correctCount=0, attemptedCount=0;
  var rowsHtml = slides.map(function(slide,i){
    var item=ts.items[i];
    var ok=isSlideCorrect(activeTab,i);
    var att=isSlideAttempted(activeTab,i);
    if(ok) correctCount++;
    if(att) attemptedCount++;
    var tagCls = ok?'ok':(att?'bad':'na');
    var tagText = ok?'Correct':(att?'Incorrect':'Not attempted');
    var row='<div class="review-row">';
    row+='<span class="review-tag '+tagCls+'">Q'+(i+1)+' · '+tagText+'</span>';
    row+='<div class="review-q">'+fr(esc(slideLabel(slide)))+'</div>';
    row+='<div class="review-ans"><b>Your answer:</b> '+fr(esc(slideAnswerText(slide,item,false)))+'</div>';
    if(!ok) row+='<div class="review-ans" style="color:var(--success);"><b>Correct answer:</b> '+fr(esc(slideAnswerText(slide,item,true)))+'</div>';
    if(slide.sol) row+='<details class="rev-sol"><summary>Show solution</summary>'+solutionHTML(slide)+'</details>';
    row+='</div>';
    return row;
  }).join('');

  addRecord('quiz', activeTab, correctCount, 0, 0, slides.length);
  var h='<div class="qcard done-card" style="text-align:left;">';
  h+='<div style="text-align:center;"><div class="big">🏁</div><h2>Quiz complete</h2>';
  h+='<p style="color:var(--ink-soft);font-size:14px;">'+correctCount+' / '+slides.length+' correct · '+attemptedCount+' attempted</p></div>';
  h+='<div style="margin-top:16px;">'+rowsHtml+'</div>';
  h+='<div style="text-align:center;margin-top:6px;"><button class="btn btn-primary" id="btnReview">Review from question 1</button></div>';
  h+='</div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  document.getElementById('btnReview').addEventListener('click', function(){ ts.idx=0; renderSlide(); });
  playSuccess();
  updateChapterProgress(); saveState();
}

/* ================= mode picker ================= */
function updateModePill(){
  var btn=document.getElementById('modePill');
  if(!btn) return;
  btn.textContent = MODE==='quiz' ? '📝 Quiz Mode · switch' : '📘 Learning Sheet · switch';
}
function showChrome(show){
  document.querySelector('.tabbar').style.display = show?'':'none';
  document.querySelector('.slide-progress').style.display = show?'':'none';
  document.querySelector('.navbar').style.display = show?'':'none';
  document.getElementById('paletteFab').style.display = show?'':'none';
}
function renderModePicker(){
  showChrome(false);
  var wrap=document.getElementById('wrap');
  wrap.innerHTML =
    '<div class="mode-pick">'+
      '<div class="mode-card" data-pick="learning"><div class="mode-icon">📘</div><h3>Learning Sheet</h3>'+
      '<p>Work through each question step by step with instant feedback — two tries, then the correct value is revealed right there so you can keep moving.</p></div>'+
      '<div class="mode-card" data-pick="quiz"><div class="mode-icon">📝</div><h3>Quiz Mode</h3>'+
      '<p>Attempt every question with no hints along the way. Your score and the full answer key are shown together once you finish the tab — just like the real exam.</p></div>'+
    '</div>';
  wrap.querySelectorAll('[data-pick]').forEach(function(card){
    card.addEventListener('click', function(){
      setMode(card.dataset.pick); activeTab='theory';
      document.getElementById('modePill').hidden=false;
      updateModePill();
      showChrome(true);
      buildTabbar();
      renderSlide();
    });
  });
}
document.getElementById('modePill').addEventListener('click', function(){
  if(!appState.mode){ return; }
  setMode(appState.mode==='quiz' ? 'learning' : 'quiz');
  updateModePill();
  showChrome(true);
  buildTabbar();
  renderSlide();
});

/* ================= boot ================= */
var _origRenderSlide = renderSlide;
renderSlide = function(){ _origRenderSlide(); updateChapterProgress(); updateModePill(); };


/* ================= theory tab ================= */
function renderTheory(){
  var wrap=document.getElementById('wrap');
  wrap.innerHTML='<div class="theory">'+fr(THEORY)+'</div>';
  document.querySelector('.slide-progress').style.display='none';
  document.querySelector('.navbar').style.display='none';
  document.getElementById('paletteFab').style.display='none';
  document.getElementById('secSub').textContent='Theory — notes, key ideas and worked examples';
  wrap.querySelectorAll('[data-go]').forEach(function(b){ b.addEventListener('click',function(){ activeTab=b.dataset.go; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); });
  wrap.querySelectorAll('[data-jump]').forEach(function(b){ b.addEventListener('click',function(){ var t=document.getElementById(b.dataset.jump); if(t) t.scrollIntoView({behavior:'smooth',block:'start'}); }); });
}
var _rsTheory = renderSlide;
renderSlide = function(){
  if(activeTab==='theory'){ renderTheory(); buildTabbar(); updateChapterProgress(); updateModePill(); saveState(); return; }
  document.querySelector('.slide-progress').style.display='';
  document.querySelector('.navbar').style.display='';
  document.getElementById('paletteFab').style.display='';
  _rsTheory();
};


/* ================= MYP criterion report ================= */
var CRIT_COL={A:'var(--accent-text)',B:'var(--gold)',C:'#8A6FC4',D:'#2F9AA0'};
function critStats(){
  return REPORT.map(function(r){
    var tabId=r[0], slides=SLIDES[tabId], ts=state&&state.tabs[tabId];
    var c=0,w=0,n=0;
    slides.forEach(function(sl,i){
      if(!ts||!ts.items[i]){ n++; return; }
      var it=ts.items[i];
      if(MODE==='learning'){
        if(it.status==='correct') c++; else if(it.status==='revealed') w++; else n++;
      } else {
        if(isSlideCorrect(tabId,i)) c++; else if(isSlideAttempted(tabId,i)) w++; else n++;
      }
    });
    var tot=slides.length, pct=tot?Math.round(c/tot*100):0;
    var lvl=Math.round(c/Math.max(tot,1)*8);
    return {tab:tabId,letter:r[1],name:r[2],c:c,w:w,n:n,tot:tot,pct:pct,lvl:lvl};
  });
}
function arcPath(cx,cy,r,a0,a1){
  if(a1-a0>=Math.PI*2-1e-6){ return 'M'+(cx-r)+','+cy+' a'+r+','+r+' 0 1,0 '+(2*r)+',0 a'+r+','+r+' 0 1,0 '+(-2*r)+',0 Z'; }
  var x0=cx+r*Math.sin(a0), y0=cy-r*Math.cos(a0), x1=cx+r*Math.sin(a1), y1=cy-r*Math.cos(a1);
  return 'M'+cx+','+cy+' L'+x0.toFixed(2)+','+y0.toFixed(2)+' A'+r+','+r+' 0 '+((a1-a0)>Math.PI?1:0)+',1 '+x1.toFixed(2)+','+y1.toFixed(2)+' Z';
}
function pieSVG(parts,size,hole,center,sub){
  var tot=parts.reduce(function(s,p){return s+p.v;},0), cx=size/2, cy=size/2, r=size/2-4, a=0, h='';
  if(!tot){ h+='<circle cx="'+cx+'" cy="'+cy+'" r="'+r+'" style="fill:var(--paper-2);stroke:var(--rule)"/>'; }
  parts.forEach(function(p){ if(!p.v) return; var b=a+p.v/tot*Math.PI*2; h+='<path d="'+arcPath(cx,cy,r,a,b)+'" style="fill:'+p.col+';stroke:var(--card);stroke-width:2"><title>'+esc(p.label)+': '+p.v+'</title></path>'; a=b; });
  if(hole) h+='<circle cx="'+cx+'" cy="'+cy+'" r="'+(r*hole)+'" style="fill:var(--card)"/>';
  if(center) h+='<text x="'+cx+'" y="'+(cy-(sub?4:0))+'" text-anchor="middle" dominant-baseline="middle" style="fill:var(--ink);font:700 '+(size>150?22:15)+'px Fraunces,serif">'+center+'</text>';
  if(sub) h+='<text x="'+cx+'" y="'+(cy+16)+'" text-anchor="middle" style="fill:var(--ink-soft);font:600 11px \'Source Sans 3\',sans-serif">'+sub+'</text>';
  return '<svg viewBox="0 0 '+size+' '+size+'" width="'+size+'" height="'+size+'" role="img">'+h+'</svg>';
}
function band(l){ return l===0?'0':(l<=2?'1–2':(l<=4?'3–4':(l<=6?'5–6':'7–8'))); }
function renderReport(){
  var st=critStats(), totC=0, totQ=0;
  st.forEach(function(s){ totC+=s.c; totQ+=s.tot; });
  var h='<div class="theory">';
  h+='<section class="note"><h2>Chapter test report</h2><p class="lt">'+(MODE==='quiz'?'<b>Quiz mode</b> results: answers are marked when you finish each test tab.':'<b>Learning mode</b> results: a question counts as correct only if you got it without the answer being revealed. Switch to Quiz mode for an exam-style score.')+'</p>';
  h+='<div class="rep-top"><div class="rep-pie">'+pieSVG(st.map(function(s){return {v:s.c,col:CRIT_COL[s.letter],label:'Criterion '+s.letter};}),200,0.55,totC+'/'+totQ,'correct')+'</div>';
  h+='<div class="rep-legend"><div class="rep-cap">Marks earned, by criterion</div>'+st.map(function(s){ return '<div class="rep-li"><span class="sw" style="background:'+CRIT_COL[s.letter]+'"></span><b>'+s.letter+'</b>&nbsp;'+esc(s.name)+'<span class="rep-n">'+s.c+' / '+s.tot+'</span></div>'; }).join('')+'</div></div></section>';
  h+='<div class="rep-grid">'+st.map(function(s){
    return '<div class="rep-card"><div class="rep-h"><span class="crit" style="background:'+CRIT_COL[s.letter]+'">'+s.letter+'</span>'+esc(s.name)+'</div>'+
      '<div class="rep-row">'+pieSVG([{v:s.c,col:'var(--success)',label:'Correct'},{v:s.w,col:'var(--danger)',label:'Incorrect'},{v:s.n,col:'var(--locked)',label:'Not attempted'}],120,0.5,s.pct+'%')+
      '<div class="rep-stats"><div><span class="sw" style="background:var(--success)"></span>Correct <b>'+s.c+'</b></div><div><span class="sw" style="background:var(--danger)"></span>Incorrect <b>'+s.w+'</b></div><div><span class="sw" style="background:var(--locked)"></span>Not attempted <b>'+s.n+'</b></div>'+
      '<div class="rep-lvl">Indicative level <b>'+s.lvl+'</b> / 8 <span>(band '+band(s.lvl)+')</span></div></div></div>'+
      '<button class="hub-btn" data-go="'+s.tab+'">Open Test '+s.letter+' →</button></div>';
  }).join('')+'</div>';
  h+='<p class="rep-note">Indicative level = fraction of questions correct × 8, rounded. It is a practice guide only; your teacher awards the real MYP criterion levels.</p></div>';
  var wrap=document.getElementById('wrap'); wrap.innerHTML=h;
  document.querySelector('.slide-progress').style.display='none';
  document.querySelector('.navbar').style.display='none';
  document.getElementById('paletteFab').style.display='none';
  document.getElementById('secSub').textContent='Report — chapter test results by MYP criterion';
  wrap.querySelectorAll('[data-go]').forEach(function(b){ b.addEventListener('click',function(){ activeTab=b.dataset.go; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); });
}
var _rsReport = renderSlide;
renderSlide = function(){
  if(activeTab==='report'){ renderReport(); buildTabbar(); updateChapterProgress(); updateModePill(); saveState(); return; }
  _rsReport();
};


/* ================= skipped-question return ================= */
function firstSkippedIdx(ts){
  for(var i=0;i<ts.items.length;i++){
    var it=ts.items[i];
    if(MODE==='quiz'){ if(!isSlideAttempted(activeTab,i)) return i; }
    else if(it.status==='skipped'||it.status==='unanswered') return i;
  }
  return -1;
}
function skippedList(ts){
  var out=[]; for(var i=0;i<ts.items.length;i++){ var it=ts.items[i];
    if(MODE==='quiz' ? !isSlideAttempted(activeTab,i) : (it.status==='skipped'||it.status==='unanswered')) out.push(i); }
  return out;
}
function renderSkipGate(ts){
  var list=skippedList(ts);
  var h='<div class="qcard done-card"><div class="big">⏭️</div><h2>You skipped '+list.length+' question'+(list.length>1?'s':'')+'</h2>'+
    '<p style="color:var(--ink-soft);font-size:14px;">Answer them now, or submit the tab as it is. Answers are marked only when you submit.</p>'+
    '<div class="skip-chips">'+list.map(function(i){ return '<button class="chip skip-go" data-i="'+i+'">Q'+(i+1)+'</button>'; }).join('')+'</div>'+
    '<div class="skip-btns"><button class="btn btn-primary" id="btnGoSkipped">Answer skipped questions</button><button class="btn" id="btnSubmitAnyway">Submit anyway</button></div></div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  var go=function(i){ ts.idx=i; ts.maxReached=Math.max(ts.maxReached,i); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); };
  document.getElementById('btnGoSkipped').addEventListener('click',function(){ go(list[0]); });
  document.querySelectorAll('.skip-go').forEach(function(b){ b.addEventListener('click',function(){ go(parseInt(b.dataset.i,10)); }); });
  document.getElementById('btnSubmitAnyway').addEventListener('click',function(){ ts.submitOK=true; renderFinished(); ts.submitOK=false; });
  saveState();
}
var _rfSkip = renderFinished;
renderFinished = function(){
  var ts=state.tabs[activeTab];
  if(MODE==='quiz' && !ts.submitOK && skippedList(ts).length){ renderSkipGate(ts); return; }
  _rfSkip();
  if(MODE==='learning'){
    var list=skippedList(ts);
    if(list.length){
      var card=document.querySelector('.done-card');
      if(card){ var d=document.createElement('div'); d.className='skip-btns';
        d.innerHTML='<button class="btn btn-primary" id="btnGoSkipped">Attempt skipped questions ('+list.length+')</button>';
        card.appendChild(d);
        document.getElementById('btnGoSkipped').addEventListener('click',function(){ ts.idx=list[0]; ts.recorded=false; renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); }
    }
  }
};


/* ================= approx answers (physics: within 1%) ================= */
var _amTools = answerMatches;
answerMatches = function(input,answer,accept,expr){
  if(expr==='approx'){
    var n1=parseNum(input); if(n1===null) return false;
    return [answer].concat(accept||[]).some(function(a){ var n2=parseNum(a); if(n2===null) return false; return Math.abs(n1-n2) <= Math.max(0.011*Math.abs(n2), 1e-9); });
  }
  return _amTools(input,answer,accept,expr);
};

/* ================= palette: every question already reached can be opened ================= */
statusOf = function(tabId,i){
  var ts=state.tabs[tabId];
  if(i>ts.maxReached) return 'locked';
  if(i===ts.idx) return 'current';
  var s=ts.items[i].status;
  if(s==='unanswered') return 'skipped';
  return s;
};

/* ================= on-screen keyboard ================= */
var KB={on:true, page:'num', target:null};
try{ var kbp=localStorage.getItem('sopaan-kb-pref'); if(kbp==='off') KB.on=false; }catch(e){}
function kbSave(){ try{ localStorage.setItem('sopaan-kb-pref', KB.on?'on':'off'); }catch(e){} }
var KEYS_NUM=[['7','8','9','(',')'],['4','5','6','−','/'],['1','2','3','.',','],['0',':','%','°','⌫'],['abc','←','→','Clear','Done']];
var KEYS_FRAC=[['7','8','9','/'],['4','5','6','−'],['1','2','3','space'],['0',',','⌫','Clear'],['abc','←','→','Done']];
var KEYS_ALG=[['7','8','9','x','y','n'],['4','5','6','+','−','a'],['1','2','3','×','÷','b'],['0','.','(',')','^','²'],['/','π','|','t','⌫','Clear'],['abc','←','→','Done']];
function kbLayoutFor(inp){ try{ var ts=state.tabs[activeTab], sl=SLIDES[activeTab][ts.idx], stp=sl.flat[parseInt(inp.dataset.step,10)]; var m=stp.expr, key=String(stp.a[inp.dataset.bkey]||'');
  if(m==='words'||m==='glist'||m==='angle') return 'abc'; if(m===true||m==='pow'||m==='primes') return 'alg';
  if(['fv','fe','fl','fm','fi','flist'].indexOf(m)>=0) return 'frac'; if(m==='dec'||m==='approx'||m==='dlist'||m==='set'||m==='coord'||m==='list'||m==='time') return 'num';
  if(/^[\-−]?\d+ \d+\/\d+$/.test(key)||/^[\-−]?\d+\/\d+$/.test(key)) return 'frac'; if(/[a-df-z]/i.test(key.replace(/pi/gi,''))) return /\d/.test(key)?'alg':'abc'; return 'num'; }catch(e){ return 'num'; } }
var KEYS_CALC=[['7','8','9','x','(',')'],['4','5','6','+','−','^'],['1','2','3','×','/','²'],['0','.','e','eˣ','√','ln'],['sin','cos','tan','t','⌫','Clear'],['abc','←','→','Done']];
var KEYS_ABC=[['q','w','e','r','t','y','u','i','o','p'],['a','s','d','f','g','h','j','k','l','-'],['z','x','c','v','b','n','m',',',':','/'],['123','space','←','→','⌫','Done']];
function kbBuild(){
  var el=document.getElementById('vkb'); if(!el){ el=document.createElement('div'); el.id='vkb'; el.className='vkb'; document.body.appendChild(el);
    el.addEventListener('pointerdown',function(e){ var b=e.target.closest('button[data-k]'); e.preventDefault(); if(b) kbPress(b.dataset.k); });
    el.addEventListener('mousedown',function(e){ e.preventDefault(); }); }
  var rows={num:KEYS_NUM,frac:KEYS_FRAC,alg:KEYS_ALG,abc:KEYS_ABC,calc:KEYS_CALC}[KB.page]||KEYS_NUM;
  el.innerHTML='<div class="vkb-top"><span>⌨️ Keyboard</span><button data-k="device" class="vkb-link">Use device keyboard</button></div>'+
    rows.map(function(r){ return '<div class="vkb-row">'+r.map(function(k){
      var cls='vkb-k'+(/^(abc|123|Done|Clear|⌫|←|→|space)$/.test(k)?' fn':'')+(k==='Done'?' done':'');
      return '<button type="button" class="'+cls+'" data-k="'+k+'">'+(k==='space'?'space':k)+'</button>'; }).join('')+'</div>'; }).join('');
  return el;
}
function kbShow(inp){ KB.target=inp; KB.home=kbLayoutFor(inp); KB.page=KB.home; if(!KB.on) return; var cp=document.getElementById('calcPanel'); if(cp&&cp.classList.contains('show')) return; var el=kbBuild(); var nb=document.querySelector('.navbar'); el.style.bottom=(nb?nb.getBoundingClientRect().height:0)+'px'; el.classList.add('show'); document.body.classList.add('kb-open'); setTimeout(function(){ var r=inp.getBoundingClientRect(), top=el.getBoundingClientRect().top; if(r.bottom>top-12) window.scrollBy({top:r.bottom-top+60,behavior:'smooth'}); else if(r.top<60) window.scrollBy({top:r.top-80,behavior:'smooth'}); },30); }
function kbHide(){ var el=document.getElementById('vkb'); if(el) el.classList.remove('show'); document.body.classList.remove('kb-open'); }
function kbInsert(s){
  var t=KB.target; if(!t||t.disabled) return;
  var a=t.selectionStart==null?t.value.length:t.selectionStart, b=t.selectionEnd==null?a:t.selectionEnd;
  t.value=t.value.slice(0,a)+s+t.value.slice(b); var p=a+s.length; try{ t.setSelectionRange(p,p); }catch(e){}
  t.dispatchEvent(new Event('input',{bubbles:true}));
}
function kbPress(k){
  var t=KB.target; if(k==='device'){ KB.on=false; kbSave(); kbHide(); document.querySelectorAll('.blank-input').forEach(function(i){ i.removeAttribute('inputmode'); }); if(t){ t.blur(); setTimeout(function(){ t.focus(); },50); } showToast('Device keyboard on. Tap ⌨️ on any blank to bring the on-screen keyboard back.'); return; }
  if(k==='Done'){ kbHide(); if(t) t.blur(); return; }
  if(k==='abc'||k==='123'){ KB.page=(k==='abc')?'abc':(KB.home&&KB.home!=='abc'?KB.home:'num'); kbBuild(); return; }
  if(!t) return;
  if(k==='⌫'){ var a=t.selectionStart, b=t.selectionEnd; if(a===b&&a>0){ t.value=t.value.slice(0,a-1)+t.value.slice(b); try{t.setSelectionRange(a-1,a-1);}catch(e){} } else { t.value=t.value.slice(0,a)+t.value.slice(b); try{t.setSelectionRange(a,a);}catch(e){} } t.dispatchEvent(new Event('input',{bubbles:true})); return; }
  if(k==='Clear'){ t.value=''; t.dispatchEvent(new Event('input',{bubbles:true})); return; }
  if(k==='←'||k==='→'){ var p=(t.selectionStart||0)+(k==='←'?-1:1); p=Math.max(0,Math.min(t.value.length,p)); try{t.setSelectionRange(p,p);}catch(e){} return; }
  var map={'−':'-','space':' '}; kbInsert(map[k]!==undefined?map[k]:k);
}
function kbWire(){
  document.querySelectorAll('.blank-input').forEach(function(inp){
    if(inp.dataset.kb) return; inp.dataset.kb='1';
    if(KB.on) inp.setAttribute('inputmode','none');
    inp.addEventListener('focus',function(){ kbShow(inp); });
    var btn=document.createElement('button'); btn.type='button'; btn.className='kb-toggle'; btn.title='On-screen keyboard'; btn.textContent='⌨️'; btn.tabIndex=-1;
    btn.addEventListener('mousedown',function(e){ e.preventDefault(); });
    btn.addEventListener('click',function(){ KB.on=true; kbSave(); document.querySelectorAll('.blank-input').forEach(function(i){ i.setAttribute('inputmode','none'); }); inp.focus(); kbShow(inp); });
    if(!inp.disabled) inp.insertAdjacentElement('afterend',btn);
  });
}
document.addEventListener('focusout',function(e){ setTimeout(function(){ var a=document.activeElement; if(!a||!a.classList||!a.classList.contains('blank-input')){ if(!document.querySelector('#vkb:hover')) kbHide(); } },120); });

/* ================= calculator ================= */
var CALC={expr:'', ans:0};
function calcEval(src){
  var s=String(src).replace(/×/g,'*').replace(/÷/g,'/').replace(/−/g,'-').replace(/π/g,'(PI)').replace(/Ans/g,'('+CALC.ans+')').replace(/\^/g,'**').replace(/√\(/g,'sqrt(').replace(/²/g,'**2').replace(/E/g,'*10**');
  s=s.replace(/(^|[(*\/+\-,])-/g,'$1(-1)*');
  if(/[^0-9+\-*/().,a-z A-Z]/.test(s)) throw 0;
  var ok=s.replace(/sin|cos|tan|asin|acos|atan|sqrt|log|ln|PI|abs/g,''); if(/[a-zA-Z]/.test(ok)) throw 0;
  var f=new Function('sin','cos','tan','asin','acos','atan','sqrt','log','ln','PI','abs','return ('+s+');');
  var d=Math.PI/180;
  var v=f(function(x){return Math.sin(x*d);},function(x){return Math.cos(x*d);},function(x){return Math.tan(x*d);},
    function(x){return Math.asin(x)/d;},function(x){return Math.acos(x)/d;},function(x){return Math.atan(x)/d;},Math.sqrt,Math.log10,Math.log,Math.PI,Math.abs);
  if(typeof v!=='number'||!isFinite(v)) throw 0; return v;
}
function fmtNum(v){ if(Math.abs(v)>=1e10||(Math.abs(v)<1e-6&&v!==0)) return v.toExponential(6).replace(/\.?0+e/,'e'); return String(parseFloat(v.toPrecision(10))); }
var CKEYS=[['sin(','cos(','tan(','√(','^','²'],['asin(','acos(','atan(','(',')','π'],['7','8','9','÷','⌫','AC'],['4','5','6','×','E','Ans'],['1','2','3','−','(−)','Insert'],['0','.','=','+']];
function openCalc(){
  var p=document.getElementById('calcPanel');
  if(!p){ p=document.createElement('div'); p.id='calcPanel'; p.className='tool-panel calc';
    p.innerHTML='<div class="tp-head"><b>🧮 Calculator</b><span class="tp-note">degrees · tap a blank, then Insert</span><button class="tp-x" data-c="close">✕</button></div>'+
      '<div class="calc-disp"><div class="calc-expr" id="calcExpr"></div><div class="calc-res" id="calcRes">0</div></div>'+
      '<div class="calc-keys">'+CKEYS.map(function(r){ return r.map(function(k){ return '<button type="button" data-c="'+k+'" class="'+(k==='='?'eq':(/^(AC|⌫|Insert)$/.test(k)?'fn':''))+'">'+({'sin(':'sin','cos(':'cos','tan(':'tan','asin(':'sin⁻¹','acos(':'cos⁻¹','atan(':'tan⁻¹','√(':'√'}[k]||k)+'</button>'; }).join(''); }).join('')+'</div>';
    document.body.appendChild(p);
    p.addEventListener('mousedown',function(e){ if(e.target.closest('button')) e.preventDefault(); });
    p.addEventListener('click',function(e){ var b=e.target.closest('button[data-c]'); if(!b) return; calcKey(b.dataset.c); });
  }
  kbHide(); var nb=document.querySelector('.navbar'); p.style.bottom=((nb?nb.getBoundingClientRect().height:0)+8)+'px'; p.classList.add('show'); document.body.classList.add('calc-open'); calcShow();
}
function calcShow(res){ document.getElementById('calcExpr').textContent=CALC.expr||' '; if(res!==undefined) document.getElementById('calcRes').textContent=res; }
function calcKey(k){
  if(k==='close'){ document.getElementById('calcPanel').classList.remove('show'); document.body.classList.remove('calc-open'); return; }
  if(k==='AC'){ CALC.expr=''; calcShow('0'); return; }
  if(k==='⌫'){ CALC.expr=CALC.expr.replace(/(asin\(|acos\(|atan\(|sin\(|cos\(|tan\(|√\(|Ans|.)$/,''); calcShow(); return; }
  if(k==='='){ try{ var v=calcEval(CALC.expr); CALC.ans=v; calcShow(fmtNum(v)); }catch(e){ calcShow('Error'); } return; }
  if(k==='(−)'){ CALC.expr+='−'; calcShow(); return; }
  if(k==='Insert'){ var r=document.getElementById('calcRes').textContent; if(KB.target && !KB.target.disabled && r!=='Error'){ KB.target.value=r; KB.target.dispatchEvent(new Event('input',{bubbles:true})); showToast('Inserted '+r+' into the blank.'); } else showToast('Tap a blank first, then press Insert.'); return; }
  CALC.expr+=k; calcShow();
}

/* ================= Desmos ================= */
var DESMOS_KEY='dcb31709b452b1cf9dc26972add0fda6', desmosCalc=null, desmosLoading=false;
function openDesmos(exprs){
  var p=document.getElementById('desmosPanel');
  if(!p){ p=document.createElement('div'); p.id='desmosPanel'; p.className='tool-panel desmos';
    p.innerHTML='<div class="tp-head"><b>📈 Desmos graphing calculator</b><button class="tp-x" id="desmosReset">Reset graph</button><button class="tp-x" id="desmosClose">✕</button></div><div id="desmosBox"><div class="desmos-msg">Loading Desmos…</div></div>';
    document.body.appendChild(p);
    document.getElementById('desmosClose').addEventListener('click',function(){ p.classList.remove('show'); });
    document.getElementById('desmosReset').addEventListener('click',function(){ if(desmosCalc) desmosSet(p._exprs||[]); });
  }
  p._exprs=exprs||[]; p.classList.add('show');
  if(window.Desmos){ desmosInit(); desmosSet(p._exprs); return; }
  if(desmosLoading) return; desmosLoading=true;
  var sc=document.createElement('script'); sc.src='https://www.desmos.com/api/v1.9/calculator.js?apiKey='+DESMOS_KEY;
  sc.onload=function(){ desmosInit(); desmosSet(p._exprs); };
  sc.onerror=function(){ desmosLoading=false; document.getElementById('desmosBox').innerHTML='<div class="desmos-msg">Desmos needs an internet connection. <a href="https://www.desmos.com/calculator" target="_blank" rel="noopener">Open Desmos in a new tab</a>.</div>'; };
  document.head.appendChild(sc);
}
function desmosInit(){ if(desmosCalc) return; var box=document.getElementById('desmosBox'); box.innerHTML=''; desmosCalc=Desmos.GraphingCalculator(box,{expressionsCollapsed:false,settingsMenu:false,border:false,degreeMode:true}); }
function desmosSet(exprs){ if(!desmosCalc) return; desmosCalc.setBlank(); (exprs||[]).forEach(function(e,i){ if(typeof e==='string') desmosCalc.setExpression({id:'e'+i,latex:e}); else desmosCalc.setExpression(Object.assign({id:'e'+i},e)); }); }

/* ================= toolbar on each question ================= */
var _rsTools = renderSlide;
renderSlide = function(){
  _rsTools();
  kbHide();
  if(activeTab==='theory'||activeTab==='report') return;
  var ts=state.tabs[activeTab]; if(!ts) return;
  var slide=SLIDES[activeTab][ts.idx], card=document.querySelector('#wrap .qcard');
  if(card && slide && slide.tools && slide.tools.length && !card.querySelector('.tool-bar')){
    var bar=document.createElement('div'); bar.className='tool-bar';
    bar.innerHTML=(slide.tools.indexOf('calc')>=0?'<button type="button" class="tool-btn" data-t="calc">🧮 Calculator</button>':'')+
                  (slide.tools.indexOf('desmos')>=0?'<button type="button" class="tool-btn" data-t="desmos">📈 Desmos graph</button>':'');
    card.insertBefore(bar, card.firstChild);
    bar.addEventListener('click',function(e){ var b=e.target.closest('[data-t]'); if(!b) return; if(b.dataset.t==='calc') openCalc(); else openDesmos(slide.desmos||[]); });
  }
  kbWire();
};



/* ================= signed fractions in text: {−3/4}, {3/−4}, {−2 1/3}, {p/q} ================= */
fr = function(s){ return String(s).replace(/&lt;(\/?)(b|sup|sub|i)>/g,'<$1$2>')
  .replace(/\{([−-]?\d+) (\d+)\/(\d+)\}/g,'<span class="mx">$1<span class="fq"><span>$2</span><span>$3</span></span></span>')
  .replace(/\{([−-]?[A-Za-z0-9]+)\/([−-]?[A-Za-z0-9]+)\}/g,'<span class="fq"><span>$1</span><span>$2</span></span>'); };
/* ================= BMA badge → main page of this sheet (theory hub) ================= */
(function(){
  var c=document.querySelector('.brand .crest'); if(!c) return;
  var a=document.createElement('button'); a.type='button'; a.className='crest crest-home'; a.title='Back to the main page (theory notes)'; a.setAttribute('aria-label','Main page');
  a.innerHTML='BM<span class="crest-h">⌂</span>'; c.parentNode.replaceChild(a,c);
  a.addEventListener('click',function(){
    if(!student||!MODE){ window.scrollTo({top:0,behavior:'smooth'}); return; }
    if(typeof kbHide==='function') kbHide(); if(typeof SP!=='undefined'&&SP.on) spToggle(false);
    var cp=document.getElementById('calcPanel'); if(cp) cp.classList.remove('show'); document.body.classList.remove('calc-open');
    activeTab = (typeof THEORY!=='undefined') ? 'theory' : TAB_DEFS[0].id;
    buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'});
  });
})();

/* ================= session clock: starts at sign-in and keeps running ================= */
var CLK={t0:null};
(function(){
  var row=document.querySelector('.brand .brand-row'); if(!row) return;
  var d=document.createElement('div'); d.className='bmasw off'; d.id='swBox'; d.title='Time since you signed in';
  d.innerHTML='<span class="bmasw-ic">⏱</span><span class="bmasw-t" id="swT">00:00</span>';
  row.appendChild(d); setInterval(swTick,1000);
})();
function swFmt(s){ s=Math.floor(s||0); var h=Math.floor(s/3600), m=Math.floor(s%3600/60), x=s%60; return (h?h+':'+String(m).padStart(2,'0'):String(m).padStart(2,'0'))+':'+String(x).padStart(2,'0'); }
function swTick(){
  var box=document.getElementById('swBox'); if(!box) return;
  if(student && !CLK.t0) CLK.t0=Date.now();
  if(!student) CLK.t0=null;
  box.classList.toggle('off',!CLK.t0);
  document.getElementById('swT').textContent = CLK.t0 ? swFmt((Date.now()-CLK.t0)/1000) : '00:00';
}
function swTab(){ try{ if(!state||!state.tabs||activeTab==='theory'||activeTab==='report') return null; return state.tabs[activeTab]||null; }catch(e){ return null; } }
var _rsSW = renderSlide;
renderSlide = function(){ _rsSW(); swTick(); };
var _rfSW = renderFinished;
renderFinished = function(){ _rfSW(); var done=document.querySelector('#wrap .done-card'); if(CLK.t0 && done && !done.querySelector('.bmasw-done')){ var p=document.createElement('p'); p.className='bmasw-done'; p.textContent='⏱ Time since sign-in: '+swFmt((Date.now()-CLK.t0)/1000); var h2=done.querySelector('h2'); if(h2) h2.insertAdjacentElement('afterend',p); else done.appendChild(p); } };

/* ================= scratchpad (Khan-style, 4 pens) ================= */
var SP={on:false, draw:true, color:'ink', size:3, erase:false, store:{}, key:null, cv:null, ctx:null, down:false, last:null};
var SP_COL={ink:null, blue:'#2563EB', red:'#DC2626', green:'#16A34A'};
function spInk(){ return getComputedStyle(document.documentElement).getPropertyValue('--ink').trim()||'#211E1A'; }
function spKey(){ var ts=swTab(); return ts ? (MODE+'|'+activeTab+'|'+ts.idx) : null; }
function spBuild(){
  if(SP.cv) return;
  var cv=document.createElement('canvas'); cv.id='spCanvas'; cv.className='sp-canvas'; document.body.appendChild(cv);
  var bar=document.createElement('div'); bar.id='spBar'; bar.className='sp-bar';
  bar.innerHTML='<span class="sp-lbl">✏️ Scratchpad</span>'+
    ['ink','blue','red','green'].map(function(c){ return '<button type="button" class="sp-pen" data-c="'+c+'" title="'+(c==='ink'?'black':c)+' pen"><i style="background:'+(c==='ink'?'var(--ink)':SP_COL[c])+'"></i></button>'; }).join('')+
    '<button type="button" class="sp-tool" data-t="erase" title="Eraser">🧽</button><button type="button" class="sp-tool" data-t="size" title="Pen size">●</button><button type="button" class="sp-tool" data-t="scroll" title="Pause drawing to scroll or answer">✋</button>'+
    '<button type="button" class="sp-tool" data-t="clear" title="Clear page">🗑</button><button type="button" class="sp-tool" data-t="close" title="Close scratchpad">✕</button>';
  document.body.appendChild(bar);
  bar.addEventListener('click',function(e){ var b=e.target.closest('button'); if(!b) return;
    if(b.dataset.c){ SP.color=b.dataset.c; SP.erase=false; SP.draw=true; }
    else if(b.dataset.t==='erase'){ SP.erase=true; SP.draw=true; }
    else if(b.dataset.t==='size'){ SP.size = SP.size===3?6:(SP.size===6?1.5:3); b.textContent = SP.size===6?'⬤':(SP.size===1.5?'·':'●'); }
    else if(b.dataset.t==='scroll'){ SP.draw=!SP.draw; }
    else if(b.dataset.t==='clear'){ spClear(); }
    else if(b.dataset.t==='close'){ spToggle(false); return; }
    spUI(); });
  SP.cv=cv; SP.ctx=cv.getContext('2d');
  cv.addEventListener('pointerdown',function(e){ if(!SP.draw) return; e.preventDefault(); cv.setPointerCapture(e.pointerId); SP.down=true; SP.last=spPt(e); spDot(SP.last); });
  cv.addEventListener('pointermove',function(e){ if(!SP.down) return; e.preventDefault(); var p=spPt(e); spLine(SP.last,p); SP.last=p; });
  var up=function(){ if(SP.down){ SP.down=false; spSave(); } };
  cv.addEventListener('pointerup',up); cv.addEventListener('pointercancel',up); cv.addEventListener('pointerleave',up);
  window.addEventListener('resize',function(){ if(SP.on) spFit(true); });
}
function spPt(e){ var r=SP.cv.getBoundingClientRect(); return {x:e.clientX-r.left, y:e.clientY-r.top}; }
function spStyle(){ var c=SP.ctx; c.lineCap='round'; c.lineJoin='round'; c.globalCompositeOperation=SP.erase?'destination-out':'source-over'; c.strokeStyle=c.fillStyle=(SP.color==='ink'?spInk():SP_COL[SP.color]); c.lineWidth=SP.erase?22:SP.size; }
function spDot(p){ spStyle(); var c=SP.ctx; c.beginPath(); c.arc(p.x,p.y,(SP.erase?11:SP.size/2),0,Math.PI*2); c.fill(); }
function spLine(a,b){ spStyle(); var c=SP.ctx; c.beginPath(); c.moveTo(a.x,a.y); c.lineTo(b.x,b.y); c.stroke(); }
function spSave(){ if(SP.key&&SP.cv){ try{ SP.store[SP.key]=SP.cv.toDataURL(); }catch(e){} } }
function spClear(){ if(!SP.ctx) return; SP.ctx.save(); SP.ctx.setTransform(1,0,0,1,0,0); SP.ctx.clearRect(0,0,SP.cv.width,SP.cv.height); SP.ctx.restore(); if(SP.key) delete SP.store[SP.key]; }
function spFit(keep){
  var wrap=document.getElementById('wrap'); if(!wrap||!SP.cv) return;
  var r=wrap.getBoundingClientRect(), top=r.top+window.scrollY, h=Math.max(wrap.scrollHeight, window.innerHeight-r.top)+40, w=document.documentElement.clientWidth;
  var old=keep&&SP.key?SP.store[SP.key]:null, dpr=window.devicePixelRatio||1;
  SP.cv.style.top=top+'px'; SP.cv.style.left='0px'; SP.cv.style.width=w+'px'; SP.cv.style.height=h+'px';
  SP.cv.width=Math.round(w*dpr); SP.cv.height=Math.round(h*dpr); SP.ctx.setTransform(dpr,0,0,dpr,0,0);
  if(old){ var im=new Image(); im.onload=function(){ SP.ctx.save(); SP.ctx.setTransform(1,0,0,1,0,0); SP.ctx.drawImage(im,0,0); SP.ctx.restore(); }; im.src=old; }
}
function spLoad(){ spSave(); SP.key=spKey(); spFit(false); var d=SP.key&&SP.store[SP.key]; if(d){ var im=new Image(); im.onload=function(){ SP.ctx.save(); SP.ctx.setTransform(1,0,0,1,0,0); SP.ctx.drawImage(im,0,0); SP.ctx.restore(); }; im.src=d; } }
function spUI(){
  var bar=document.getElementById('spBar'); if(!bar) return;
  bar.querySelectorAll('.sp-pen').forEach(function(b){ b.classList.toggle('on', !SP.erase && SP.draw && b.dataset.c===SP.color); });
  bar.querySelector('[data-t=erase]').classList.toggle('on', SP.erase && SP.draw);
  bar.querySelector('[data-t=scroll]').classList.toggle('on', !SP.draw);
  SP.cv.classList.toggle('passive', !SP.draw);
  var fb=document.getElementById('spFab'); if(fb) fb.classList.toggle('on',SP.on);
}
function spToggle(on){
  spBuild(); SP.on=(on===undefined)?!SP.on:on;
  document.body.classList.toggle('sp-open',SP.on); SP.cv.style.display=SP.on?'block':'none'; document.getElementById('spBar').style.display=SP.on?'flex':'none';
  if(SP.on){ SP.draw=true; SP.erase=false; spLoad(); if(typeof kbHide==='function') kbHide(); } else { spSave(); }
  spUI();
}
(function(){ var f=document.createElement('button'); f.type='button'; f.id='spFab'; f.className='sp-fab'; f.innerHTML='✏️ <span>Scratchpad</span>'; f.title='Open a scratchpad to write your working'; f.addEventListener('click',function(){ spToggle(); }); document.body.appendChild(f); })();
var _rsSP = renderSlide;
renderSlide = function(){ _rsSP(); var fab=document.getElementById('spFab'); var q=!!swTab(); if(fab) fab.style.display=q?'':'none'; if(!q && SP.on) spToggle(false); if(SP.on) setTimeout(spLoad,30); };


/* ================= v4: attempt classification ================= */
function v4Class(item){
  if(!item) return 'un';
  if(item.status==='skipped') return 'sk';
  if(item.status==='unanswered') return 'un';
  if(item.stepStates){ // step question
    if(item.status!=='correct' && item.status!=='revealed') return 'un';
    if(item.status==='revealed' || item.stepStates.some(function(s){return s.status==='revealed';})) return 'w';
    return item.stepStates.some(function(s){return (s.attempts||0)>0;}) ? 'c2' : 'c1';
  }
  if(item.status==='revealed') return 'w';
  if(item.status==='correct') return (item.attempts||0)>0 ? 'c2' : 'c1';
  if(item.status==='wrong'||item.status==='incorrect') return 'w';
  return 'un';
}
function v4Counts(items){ var c={n:items.length,c1:0,c2:0,w:0,sk:0,un:0}; items.forEach(function(it){ c[v4Class(it)]++; }); return c; }

/* ================= v4: My record with attempt columns ================= */
renderRecord = function(){
  showChrome(false);
  var tabLabel=function(id){ var t=TAB_DEFS.find(function(x){return x.id===id;}); return t?t.label:id; };
  var title=(document.querySelector('.chapter-title')||{}).textContent||'';
  var h='<div class="rec-card"><h2>'+esc(student.name)+'’s record</h2><p class="rec-empty" style="margin:0 0 12px;">Roll '+esc(student.roll)+(title?' · '+esc(title):'')+'</p>';
  var st=appState.learning;
  h+='<h3>📘 Learning Sheet — attempts</h3><p class="v4leg"><b>1st ✓</b> correct on the first attempt · <b>2nd ✓</b> correct on the second attempt · <b>Wrong</b> still wrong after two attempts (answer revealed) · <b>Skip</b> skipped<span class="v4left"> · <b>Left</b> not done yet</span></p>';
  if(!st){ h+='<p class="rec-empty">Not started yet.</p>'; }
  else {
    var T={n:0,c1:0,c2:0,w:0,sk:0,un:0};
    h+='<div class="rec-table-wrap"><table class="rec-table v4rec"><thead><tr><th>Sheet</th><th>Qs</th><th>1st ✓</th><th>2nd ✓</th><th>Wrong</th><th>Skip</th><th class="v4left">Left</th></tr></thead><tbody>';
    TAB_DEFS.forEach(function(td){ var tt=st.tabs[td.id]; if(!tt||!tt.items||!tt.items.length) return; var c=v4Counts(tt.items);
      ['n','c1','c2','w','sk','un'].forEach(function(k){ T[k]+=c[k]; });
      h+='<tr><td>'+td.label+'</td><td>'+c.n+'</td><td class="v4g">'+c.c1+'</td><td class="v4o">'+c.c2+'</td><td class="v4r">'+c.w+'</td><td>'+c.sk+'</td><td class="v4left">'+c.un+'</td></tr>'; });
    h+='<tr class="v4tot"><td>Total</td><td>'+T.n+'</td><td class="v4g">'+T.c1+'</td><td class="v4o">'+T.c2+'</td><td class="v4r">'+T.w+'</td><td>'+T.sk+'</td><td class="v4left">'+T.un+'</td></tr>';
    h+='</tbody></table></div>';
    var doneN=T.c1+T.c2+T.w; if(doneN){ h+='<p class="v4sum">Of '+doneN+' questions answered: <b>'+Math.round(T.c1/doneN*100)+'%</b> right first time, <b>'+Math.round(T.c2/doneN*100)+'%</b> right on the second try, <b>'+Math.round(T.w/doneN*100)+'%</b> still wrong after two tries.</p>'; }
  }
  var q=appState.quiz;
  h+='<h3>📝 Quiz Mode</h3>';
  if(!q){ h+='<p class="rec-empty">Not started yet.</p>'; }
  else {
    h+='<div class="rec-table-wrap"><table class="rec-table v4rec"><thead><tr><th>Sheet</th><th>Qs</th><th>Status</th><th>Correct</th><th>Wrong</th></tr></thead><tbody>';
    TAB_DEFS.forEach(function(td){ var tt=q.tabs[td.id]; if(!tt||!tt.items||!tt.items.length) return; var n=tt.items.length, cor=0, att=0;
      tt.items.forEach(function(it){ if(it.status!=='unanswered'||it.choice!==undefined) att++; });
      var rec=records.filter(function(r){ return r.mode==='quiz'&&r.tab===td.id; })[0];
      if(rec){ cor=rec.correct; att=Math.max(att,rec.total); }
      h+='<tr><td>'+td.label+'</td><td>'+n+'</td><td>'+(rec?'Finished':att+' / '+n)+'</td><td class="v4g">'+(rec?cor:'—')+'</td><td class="v4r">'+(rec?(rec.total-cor):'—')+'</td></tr>'; });
    h+='</tbody></table></div>';
  }
  h+='</div><div class="rec-card"><h3>Finished sheets (latest first)</h3>';
  if(!records.length){ h+='<p class="rec-empty">No sheets finished yet. Each time you finish a sheet, your score is recorded here.</p>'; }
  else {
    h+='<div class="rec-table-wrap"><table class="rec-table v4rec"><thead><tr><th>When</th><th>Mode</th><th>Sheet</th><th>Score</th><th>1st ✓</th><th>2nd ✓</th><th>Wrong</th></tr></thead><tbody>';
    records.forEach(function(r){ h+='<tr><td>'+fmtDate(r.at)+'</td><td>'+(r.mode==='quiz'?'Quiz':'Learning')+'</td><td>'+tabLabel(r.tab)+'</td><td>'+r.correct+' / '+r.total+'</td><td>'+(r.c1!=null?r.c1:'—')+'</td><td>'+(r.c2!=null?r.c2:'—')+'</td><td>'+(r.w!=null?r.w:(r.mode==='quiz'?r.total-r.correct:'—'))+'</td></tr>'; });
    h+='</tbody></table></div>';
  }
  h+='</div><button class="btn btn-primary" id="btnBack">'+(MODE?'Back to practice':'Choose a mode')+'</button>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('btnBack').addEventListener('click', function(){ if(MODE){ showChrome(true); buildTabbar(); renderSlide(); } else renderModePicker(); });
  window.scrollTo({top:0});
};
var _v4add = addRecord;
addRecord = function(mode, tabId, correct, revealed, skipped, total){
  _v4add(mode, tabId, correct, revealed, skipped, total);
  try{ if(mode==='learning'&&records[0]){ var c=v4Counts(state.tabs[tabId].items); records[0].c1=c.c1; records[0].c2=c.c2; records[0].w=c.w; saveState(); } }catch(e){}
};

/* ================= v4: celebration ================= */
function v4Cracker(){
  var ctx=ensureAudio(); if(!ctx) return; try{ if(ctx.state==='suspended') ctx.resume(); }catch(e){}
  var now=ctx.currentTime;
  function pop(t, vol, dur, hp){
    var len=Math.floor(ctx.sampleRate*dur), buf=ctx.createBuffer(1,len,ctx.sampleRate), d=buf.getChannelData(0);
    for(var i=0;i<len;i++){ d[i]=(Math.random()*2-1)*Math.pow(1-i/len,3); }
    var src=ctx.createBufferSource(); src.buffer=buf;
    var f=ctx.createBiquadFilter(); f.type='highpass'; f.frequency.value=hp;
    var g=ctx.createGain(); g.gain.setValueAtTime(vol,t); g.gain.exponentialRampToValueAtTime(0.001,t+dur);
    src.connect(f); f.connect(g); g.connect(ctx.destination); src.start(t); src.stop(t+dur+0.02);
  }
  pop(now,0.9,0.35,300);                                   // big bang
  for(var k=0;k<14;k++){ pop(now+0.35+Math.random()*1.3, 0.25+Math.random()*0.35, 0.05+Math.random()*0.08, 1500+Math.random()*2500); } // crackles
  [523.25,659.25,783.99,1046.5].forEach(function(fq,i){ var o=ctx.createOscillator(), g=ctx.createGain(); o.type='triangle'; o.frequency.value=fq;
    var t=now+0.15+i*0.12; g.gain.setValueAtTime(0.0001,t); g.gain.exponentialRampToValueAtTime(0.18,t+0.03); g.gain.exponentialRampToValueAtTime(0.001,t+0.5);
    o.connect(g); g.connect(ctx.destination); o.start(t); o.stop(t+0.55); });
}
function v4Confetti(){
  var cv=document.createElement('canvas'); cv.className='v4conf'; document.body.appendChild(cv);
  var W=cv.width=window.innerWidth*(window.devicePixelRatio||1), H=cv.height=window.innerHeight*(window.devicePixelRatio||1), s=(window.devicePixelRatio||1);
  var ctx=cv.getContext('2d'), cols=['#e8b13a','#d9534f','#2e86de','#27ae60','#9b59b6','#f39c12','#1abc9c','#ff6b9a'], P=[];
  function burst(x,y,n){ for(var i=0;i<n;i++){ var a=Math.random()*Math.PI*2, v=(4+Math.random()*9)*s;
    P.push({x:x,y:y,vx:Math.cos(a)*v,vy:Math.sin(a)*v-6*s,w:(6+Math.random()*7)*s,h:(4+Math.random()*5)*s,r:Math.random()*6,vr:(Math.random()-.5)*.4,c:cols[i%cols.length],life:0,flyer:Math.random()<.25}); } }
  burst(W*0.2,H*0.35,90); burst(W*0.8,H*0.35,90); setTimeout(function(){ burst(W*0.5,H*0.25,120); },380); setTimeout(function(){ burst(W*0.35,H*0.3,70); burst(W*0.65,H*0.3,70); },800);
  var t0=performance.now();
  (function frame(t){
    ctx.clearRect(0,0,W,H);
    P.forEach(function(p){ p.vy+=0.22*s; p.vx*=0.985; p.vy*=0.985; p.x+=p.vx; p.y+=p.vy; p.r+=p.vr; p.life++;
      ctx.save(); ctx.translate(p.x,p.y); ctx.rotate(p.r); ctx.fillStyle=p.c;
      if(p.flyer){ ctx.fillRect(-p.w*1.4,-1.5*s,p.w*2.8,3*s); } else { ctx.fillRect(-p.w/2,-p.h/2,p.w,p.h*Math.abs(Math.cos(p.life/6))); }
      ctx.restore(); });
    if(t-t0<4200) requestAnimationFrame(frame); else cv.remove();
  })(t0);
}
function v4NextTab(){
  var i=TAB_DEFS.findIndex(function(t){return t.id===activeTab;});
  for(var j=i+1;j<TAB_DEFS.length;j++){ var id=TAB_DEFS[j].id; if(id!=='theory' && SLIDES[id] && SLIDES[id].length) return TAB_DEFS[j]; }
  return null;
}
function v4Celebrate(){
  var done=document.querySelector('#wrap .done-card'); if(!done || done.dataset.v4) return; done.dataset.v4='1';
  var ts=state.tabs[activeTab], c=v4Counts(ts.items), n=ts.items.length;
  var first=(student&&student.name)?String(student.name).split(' ')[0]:'';
  var pct=MODE==='quiz'?null:Math.round((c.c1+c.c2)/Math.max(n,1)*100);
  var msg = pct===null ? 'You finished this sheet!' : (pct>=90?'Outstanding work!':pct>=75?'Excellent effort!':pct>=50?'Well done — keep going!':'Great persistence — every try makes you stronger!');
  var banner=document.createElement('div'); banner.className='v4ban';
  banner.innerHTML='<div class="v4trophy">🏆</div><div class="v4h">Congratulations'+(first?', '+esc(first):'')+'!</div><div class="v4m">'+msg+'</div>'+
    (MODE==='quiz'?'':'<div class="v4pills"><span class="v4p g">✅ '+c.c1+' first attempt</span><span class="v4p o">🔁 '+c.c2+' second attempt</span><span class="v4p r">❌ '+c.w+' finally wrong</span>'+(c.sk?'<span class="v4p s">⏭ '+c.sk+' skipped</span>':'')+'</div>');
  done.insertBefore(banner, done.firstChild);
  var nx=v4NextTab(), wrapB=document.createElement('div'); wrapB.className='v4next';
  if(nx){ wrapB.innerHTML='<button class="btn btn-primary v4go" id="v4Next">Next sheet: '+nx.label+' →</button>'; }
  else if(SLIDES.report!==undefined || TAB_DEFS.some(function(t){return t.id==='report';})){ wrapB.innerHTML='<button class="btn btn-primary v4go" id="v4Next">📊 View my report →</button>'; }
  else { wrapB.innerHTML='<button class="btn btn-primary v4go" id="v4Next">⌂ Back to the home page</button>'; }
  banner.appendChild(wrapB);
  document.getElementById('v4Next').addEventListener('click',function(){
    var t=nx?nx.id:(TAB_DEFS.some(function(x){return x.id==='report';})?'report':(TAB_DEFS[0]&&TAB_DEFS[0].id));
    activeTab=t; showChrome(true); buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); });
  setTimeout(function(){ var r=banner.getBoundingClientRect(); window.scrollBy({top:r.top-110,behavior:'smooth'}); },60);
  v4Confetti(); v4Cracker();
}
var _v4rf = renderFinished;
renderFinished = function(){ _v4rf.apply(this,arguments); try{ v4Celebrate(); }catch(e){ console.log('v4',e); } };


/* ================= calculus answer mode ================= */
function calcCompile(src){
  var s=String(src).replace(/\s+/g,'').replace(/[×∗·]/g,'*').replace(/÷/g,'/').replace(/[−–—]/g,'-')
    .replace(/²/g,'^2').replace(/³/g,'^3').replace(/π/g,'#').replace(/eˣ/g,'e^x');
  if(s.indexOf('=')>=0) s=s.slice(s.lastIndexOf('=')+1);
  var FN=['sqrt','abs','ln','log','exp','sin','cos','tan','sec','csc','cot','pi'];
  var i=0,toks=[];
  while(i<s.length){
    var ch=s[i];
    if(/[0-9.]/.test(ch)){ var j=i; while(j<s.length&&/[0-9.]/.test(s[j])) j++; toks.push({k:'n',v:parseFloat(s.slice(i,j))}); i=j; continue; }
    if(ch==='√'){ toks.push({k:'f',v:'sqrt'}); i++; continue; }
    if(/[a-zA-Z#]/.test(ch)){
      var hit=null; for(var q=0;q<FN.length;q++){ if(s.substr(i,FN[q].length).toLowerCase()===FN[q]){ hit=FN[q]; break; } }
      if(hit==='pi'){ toks.push({k:'v',v:'#'}); i+=2; continue; }
      if(hit){ toks.push({k:'f',v:hit}); i+=hit.length; continue; }
      toks.push({k:'v',v:ch}); i++; continue; }
    if('+-*/^()|'.indexOf(ch)>=0){ toks.push({k:ch}); i++; continue; }
    return null;
  }
  // absolute value bars -> abs( )
  var t2=[],open=false; for(var a=0;a<toks.length;a++){ var tk=toks[a]; if(tk.k==='|'){ if(!open){ t2.push({k:'f',v:'abs'}); t2.push({k:'('}); open=true; } else { t2.push({k:')'}); open=false; } } else t2.push(tk); }
  toks=t2;
  var out=[];
  for(var t=0;t<toks.length;t++){ var A=toks[t], B=out[out.length-1];
    if(B&&(B.k==='n'||B.k==='v'||B.k===')')&&(A.k==='n'||A.k==='v'||A.k==='('||A.k==='f')) out.push({k:'&'});
    out.push(A); }
  var p=0; function pk(){ return out[p]; }
  var F={sqrt:Math.sqrt,ln:Math.log,log:function(x){return Math.log(x)/Math.LN10;},exp:Math.exp,sin:Math.sin,cos:Math.cos,tan:Math.tan,
    sec:function(x){return 1/Math.cos(x);},csc:function(x){return 1/Math.sin(x);},cot:function(x){return 1/Math.tan(x);},abs:Math.abs};
  function E(){ var n=T(); while(pk()&&(pk().k==='+'||pk().k==='-')){ var o=out[p++].k,r=T(); n=(function(l,r,o){return function(e){return o==='+'?l(e)+r(e):l(e)-r(e);};})(n,r,o);} return n; }
  function T(){ var n=I(); while(pk()&&(pk().k==='*'||pk().k==='/')){ var o=out[p++].k,r=I(); n=(function(l,r,o){return function(e){return o==='*'?l(e)*r(e):l(e)/r(e);};})(n,r,o);} return n; }
  function I(){ var n=U(); while(pk()&&pk().k==='&'){ p++; var r=P(); n=(function(l,r){return function(e){return l(e)*r(e);};})(n,r);} return n; }
  function U(){ if(pk()&&pk().k==='-'){ p++; var u=U(); return function(e){return -u(e);}; } if(pk()&&pk().k==='+'){ p++; return U(); } return P(); }
  function P(){ var b=Aa(); if(pk()&&pk().k==='^'){ p++; var x=U(); return function(e){return Math.pow(b(e),x(e));}; } return b; }
  function Aa(){ var t=out[p++]; if(!t) throw 0;
    if(t.k==='n') return function(){return t.v;};
    if(t.k==='v'){ if(t.v==='#') return function(){return Math.PI;}; if(t.v==='e') return function(){return Math.E;}; return function(e){return e[t.v];}; }
    if(t.k==='('){ var n=E(); if(!pk()||pk().k!==')') throw 0; p++; return n; }
    if(t.k==='f'){ var fn=F[t.v]; var ex=null;
      if(pk()&&pk().k==='^'){ p++; ex=Aa(); if(pk()&&pk().k==='&') p++; }            // sin^2(x)
      var arg; if(pk()&&pk().k==='('){ p++; arg=E(); if(!pk()||pk().k!==')') throw 0; p++; } else arg=P();
      return ex? function(e){ return Math.pow(fn(arg(e)),ex(e)); } : function(e){ return fn(arg(e)); }; }
    throw 0; }
  try{ var f=E(); if(p!==out.length) return null; return f; }catch(e){ return null; }
}
function calcEqual(input,answer){
  var f=calcCompile(input), g=calcCompile(answer); if(!f||!g) return false;
  var hits=0;
  for(var trial=0;trial<14;trial++){
    var env={}; 'abcdfghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('').forEach(function(c){ env[c]=0.35+Math.random()*2.3; });
    var x=f(env), y=g(env); if(!isFinite(x)||!isFinite(y)) continue;
    if(Math.abs(x-y)>1e-6*Math.max(1,Math.abs(x),Math.abs(y))) return false; hits++;
  }
  return hits>=4;
}
(function(){
  var _am=answerMatches;
  answerMatches=function(input,answer,accept,expr){
    if(expr==='calc'){ if(input===undefined||input===null||String(input).trim()==='') return false;
      if(calcEqual(input,answer)) return true; return (accept||[]).some(function(a){ return calcEqual(input,a); }); }
    return _am.apply(this,arguments); };
  var _kl=kbLayoutFor;
  kbLayoutFor=function(inp){ try{ var ts=state.tabs[activeTab], sl=SLIDES[activeTab][ts.idx], stp=sl.flat[parseInt(inp.dataset.step,10)]; if(stp.expr==='calc') return 'calc'; }catch(e){} return _kl(inp); };
  var _kp=kbPress;
  kbPress=function(k){ var m={'eˣ':'e^(','√':'√(','ln':'ln(','sin':'sin(','cos':'cos(','tan':'tan('}; if(KB.page==='calc'&&m[k]){ kbInsert(m[k]); return; } return _kp(k); };
})();

renderLogin();
})();
</script>
</body>
</html>

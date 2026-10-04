<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>B.Pharm Smart Calculator</title>

<style>

*{
    box-sizing:border-box;
}

body{
    margin:0;
    font-family:Arial,sans-serif;
    background:#eef2f7;
    color:#172033;
}

.app{
    max-width:760px;
    margin:auto;
    padding:18px;
}

.hero{
    background:#173f8a;
    color:white;
    padding:22px;
    border-radius:18px;
    text-align:center;
}

.hero h1{
    margin:0 0 8px;
    font-size:28px;
}

.hero p{
    margin:0;
    font-size:14px;
}

.tabs{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:10px;
    margin:16px 0;
}

.tab{
    border:0;
    border-radius:12px;
    padding:14px 8px;
    background:white;
    font-weight:bold;
    cursor:pointer;
    font-size:15px;
    box-shadow:0 2px 7px rgba(0,0,0,.08);
}

.tab.active{
    background:#173f8a;
    color:white;
}

.panel{
    display:none;
    background:white;
    border-radius:16px;
    padding:18px;
    box-shadow:0 3px 12px rgba(0,0,0,.10);
    margin-bottom:15px;
}

.panel.active{
    display:block;
}

.panel h2{
    margin-top:0;
    color:#173f8a;
}

label{
    display:block;
    font-weight:bold;
    margin:10px 0 6px;
}

input,select{
    width:100%;
    padding:12px;
    border:1px solid #cbd5e1;
    border-radius:9px;
    font-size:16px;
    background:white;
}

.grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:12px;
}

.btn{
    width:100%;
    margin-top:14px;
    padding:14px;
    border:0;
    border-radius:10px;
    background:#2563eb;
    color:white;
    font-size:16px;
    font-weight:bold;
    cursor:pointer;
}

.btn:active{
    transform:scale(.98);
}

.result{
    margin-top:16px;
    padding:15px;
    background:#f1f5f9;
    border-radius:10px;
    line-height:1.8;
}

.big{
    font-size:25px;
    font-weight:800;
    color:#173f8a;
}

.small{
    color:#64748b;
    font-size:13px;
}

.formula{
    background:#eff6ff;
    padding:10px;
    border-radius:8px;
    margin-top:10px;
    font-size:14px;
}

@media(max-width:520px){

    .grid{
        grid-template-columns:1fr;
    }

    .app{
        padding:10px;
    }

    .hero h1{
        font-size:23px;
    }

}

</style>
</head>


<body>

<div class="app">


<!-- HEADER -->

<div class="hero">

<h1>💊 B.Pharm Smart Calculator</h1>

<p>
Pharmaceutics • Chemistry • Analysis • Pharmacology • Biochemistry
</p>

</div>


<!-- MENU -->

<div class="tabs">

<button class="tab active" onclick="showPanel('flow',this)">
Powder Flow
</button>

<button class="tab" onclick="showPanel('chem',this)">
Chemistry
</button>

<button class="tab" onclick="showPanel('dilution',this)">
Dilution
</button>

<button class="tab" onclick="showPanel('ph',this)">
pH
</button>

<button class="tab" onclick="showPanel('assay',this)">
Assay
</button>

<button class="tab" onclick="showPanel('dose',this)">
Dose
</button>

<button class="tab" onclick="showPanel('stats',this)">
Statistics
</button>

<button class="tab" onclick="showPanel('drug',this)">
Drug Database
</button>

</div>



<!-- ========================= -->
<!-- POWDER FLOW -->
<!-- ========================= -->

<div id="flow" class="panel active">

<h2>📐 Powder Flow Calculator</h2>

<h3>Angle of Repose</h3>

<div class="grid">

<div>

<label>Height (h)</label>

<input
id="h"
type="number"
step="any"
placeholder="Enter height">

</div>


<div>

<label>Radius (r)</label>

<input
id="r"
type="number"
step="any"
placeholder="Enter radius">

</div>

</div>


<button class="btn" onclick="calculateAngle()">
Calculate Angle of Repose
</button>


<div id="flowOut" class="result">
Enter height and radius.
</div>


<div class="formula">

<b>Formula:</b>

θ = tan⁻¹(h/r)

</div>



<hr>



<h3>Carr's Index + Hausner Ratio</h3>

<label>Bulk Density</label>

<input
id="bulkDensity"
type="number"
step="any"
placeholder="g/mL">


<label>Tapped Density</label>

<input
id="tappedDensity"
type="number"
step="any"
placeholder="g/mL">


<button class="btn" onclick="calculateFlowInd

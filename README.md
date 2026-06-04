
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Baymax OS</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    background:#000;
    overflow:hidden;
    color:white;
}
/* Tela inicial */
#bootScreen{
    position:fixed;
    width:100%;
    height:100%;
    background:black;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
}

.logo{
    font-size:2rem;
    margin-bottom:20px;
    letter-spacing:3px;
}

.loading{
    width:300px;
    height:10px;
    border:1px solid white;
}

.bar{
    height:100%;
    width:0%;
    background:white;
    animation:load 4s forwards;
}

@keyframes load{
    from{width:0%;}
    to{width:100%;}
}
/* Interface principal */
#mainInterface{
    display:none;
    width:100vw;
    height:100vh;
    background:#050505;
    position:relative;
}
/* Scanner */
.scanner{
    position:absolute;
    width:100%;
    height:3px;
    background:red;
    box-shadow:0 0 20px red;
    animation:scan 4s linear infinite;
}

@keyframes scan{
    0%{top:0;}
    100%{top:100%;}
}

/* Baymax */

.baymax-container{
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
}

.face{
    width:250px;
    height:120px;
    position:relative;
}

.eye{
    width:22px;
    height:22px;
    background:white;
    border-radius:50%;
    position:absolute;
    top:50px;
}

.left{
    left:60px;
    opacity:0;
    animation:appear 1s forwards;
}

.right{
    right:60px;
    opacity:0;
    animation:appear 1s forwards 1s;
}

.line{
    position:absolute;
    top:60px;
    left:82px;
    width:0;
    height:4px;
    background:white;
    animation:drawline 1s forwards 2s;
}

@keyframes appear{
    to{opacity:1;}
}

@keyframes drawline{
    to{width:90px;}
}

/* Texto */

.message{
    position:absolute;
    bottom:80px;
    width:100%;
    text-align:center;
    font-size:1.4rem;
    opacity:0;
    animation:showText 2s forwards 3s;
}

@keyframes showText{
    to{opacity:1;}
}

/* Flutuação */

.baymax-container{
    animation:float 4s ease-in-out infinite;
}

@keyframes float{
    0%{transform:translate(-50%,-50%) translateY(0);}
    50%{transform:translate(-50%,-50%) translateY(-15px);}
    100%{transform:translate(-50%,-50%) translateY(0);}
}
</style>
</head>
<body>
<!-- Boot -->
<div id="bootScreen">
    <div class="logo">BAYMAX OS</div>
    <div class="loading">
        <div class="bar"></div>
    </div>
    <p style="margin-top:20px;">
        Inicializando protocolos médicos...
    </p>
</div>
 <!-- Interface -->
<div id="mainInterface">
    <div class="scanner"></div>
    <div class="baymax-container">
        <div class="face">
            <div class="eye left"></div>
            <div class="line"></div>
            <div class="eye right"></div>
        </div>
    </div>
    <div class="message" id="message">
        Olá. Eu sou Baymax, seu assistente pessoal de saúde ●━●
    </div>
</div>

<script>

setTimeout(()=>{
    document.getElementById("bootScreen").style.display="none";
    document.getElementById("mainInterface").style.display="block";
},4500);

</script>

</body>
</html>

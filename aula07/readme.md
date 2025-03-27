# Aula 07 - Inicio da construção de jogo com JavaScript

## Passo 1
Criação de arquivos iniciais HTML, JavaScript, CSS

```index.html
<!DOCTYPE HTML>
<html>
	<head>
		<title>Salve a terra!</title>
    	<link href="css/estilos.css" rel="stylesheet" />
	</head>
	<body>
		<div id='fundo'>
			<div id='area_jogo' class='area_jogo'>
				<div id='start'>
					<h1>Salve a terra</h1>
					<p>Pressione <b>W</b> para subir, <b>S</b> para descer, <b>A</b> e <b>S</b> direita e esquerda e
					<b>Barra</b> para atiar</p>
					<h2>Clique aqui para iniciar</h2>
				</div>
			</div>
		</div>
		<script type="text/javascript" src="js/jquery-1.11.1.min.js"></script>
		<script type="text/javascript" src="js/jquery-collision.min.js"></script>
		<script type="text/javascript" src="js/jogo.js"></script> 
	</body>
</html>
```

```estilos.css
/*
estilos.css
*/
@font-face {
  font-family: "Ufo";
  src: url("SFAlienEncounters.ttf");
}

/*
Areas do jogo
*/

body {
	margin: 0px;
	background: url("../img/fundo.gif");
}

#fundo {
	margin: 0;
	width: 100%;
	height: 100%;
}

.area_jogo {
	position: absolute;
	width: 680px;
	height: 350px;
	position: relative;
	margin-left: auto;
	margin-right: auto;
	top: 25px;
	background: url("../img/fundo.png");
}

#start {
	width: 350px;
	height: 250px;
	background: #fff;
	margin-left: 150px;
	margin-right: auto;
	top: 25px;
	text-align: center;
	position: absolute;
}

#start h1 {
	padding-top: 25px;
	font-family: Ufo;
	font-size: 36px;
	font-style: italic;
}


#start p {
	font-family: Ufo;
	font-size: 24px;
}

#start h2 {
	font-family: Ufo;
	font-size: 18px;
	font-weight: bold;
}
/*
Fim - Areas do jogo
*/
```


```index.js
funciton start() 
{
    $(document).apend("<div id='palyer' class='player'></div>");
    $(document).apend("<div id='nave' class='nave'></div>");
    $(document).apend("<div id='tanque' class='tanque'></div>");
    $(document).apend("<div id='pessoa' class='pessoa'></div>");    
}
```

```estilos.css (continuacao)
.player {
	width: 110px;
	height: 60px;
	top: 10px;
	background-image: url("../img/jogador.png");
	position: absolute;
}

.nave {
	width: 51px;
	height: 48px;
	margin-top: 10px;
	left: 630px;
	position: absolute;
	background-image: url("../img/inimigo.png");
}

.pessoa {
	width: 50px;
	height: 55px;
	top: 280px;
	left: 0;
	position: absolute;
	background-image: url("../img/pessoa.png");
}

.tanque {
	width: 75px;
	height: 49px;
	top: 280px;
	left: 600px;
	position: absolute;
	background-image: url("../img/tanque.png");
}
```

```estilos.css (continuação 02)
.player {
	width: 110px;
	height: 60px;
	top: 10px;
	background-image: url("../img/jogador.png");
	position: absolute;
	animation:p_player .9s steps(7) infinite;

       -webkit-animation: p_player .9s steps(7) infinite;
       -moz-animation: p_player .9s steps(7) infinite;
       -ms-animation: p_player .9s steps(7) infinite;
       -o-animation: p_player .9s steps(7) infinite;
}

@keyframes p_player {
	from {background-position:0px;}
	to {background-position:-763px;}
}


@-webkit-keyframes p_player {
   from { background-position:0px; }
     to { background-position: -763px; }
}

@-moz-keyframes p_player {
   from { background-position:0px; }
     to { background-position: -763px; }
}

@-ms-keyframes p_player {
   from { background-position:0px; }
     to { background-position: -763px; }
}

@-o-keyframes p_player {
   from { background-position:0px; }
     to { background-position: -763px; }
}

```
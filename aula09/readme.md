## Primeira parte

```js
function start() {
		//Divs
		$('#start').hide();
		
		
		//Motor do jogo
		setInterval(loop,30);

		function loop() {
			movimentacenario();
		}
		
		function movimentacenario() {
			var posicao = parseInt($('.area_jogo').css("background-position"));
			$('.area_jogo').css("background-position",posicao-1);
		} //Fim movimentacenario
}
```

## Segunda parte
```js
//Variaveis globais
var tecla = {
	W:87,
	S:83,
	A:65,
	D:68
}
var jogo = {}
jogo.pressionou = [];

//Teclas pressionadas
$(document).keydown(function(e){
	jogo.pressionou[e.which] = true;
});


$(document).keyup(function(e){
   jogo.pressionou[e.which] = false;
});	

/* jogo.js */
function loop() {
	...
	movimentaplayer();
}

/* jogo.js */
function movimentaplayer() {
	if(jogo.pressionou[tecla.W]){
		var topo = parseInt($('#player').css("top"));
		$('#player').css("top", topo-8);
		if(topo<=0)
			$('#player').css("top", 0);
	}

	if(jogo.pressionou[tecla.S]){
		var down = parseInt($('#player').css("top"));
		$('#player').css("top", down+8);
		if(down>=256)
			$('#player').css("top", 256);
	}

	if(jogo.pressionou[tecla.D]){
		var left = parseInt($('#player').css("left"));
		$('#player').css("left", left+8);
		if(left>=560)
			$('#player').css("left", 560);
	}

	if(jogo.pressionou[tecla.A]){
		var left = parseInt($('#player').css("left"));
		$('#player').css("left", left-8);
		if(left<=0)
			$('#player').css("left", 0);
	}
} //Movimenta player
```
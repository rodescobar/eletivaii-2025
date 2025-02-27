# Aula 03 - Introdução ao JavaScript

## Índice
1. [Blocos JavaScript dentro do HTML](#blocos-javascript-dentro-do-html)
2. [Blocos JavaScript fora do HTML](#blocos-javascript-fora-do-html)
3. [Buscar dados de um input](#buscar-dados-de-um-input)
4. [Aplicar estilo CSS em uma div](#aplicar-estilo-css-em-uma-div)

## Blocos JavaScript dentro do HTML
Você pode adicionar JavaScript diretamente dentro de um arquivo HTML usando a tag `<script>`.
```html
<!DOCTYPE html>
<html>
<head>
    <title>Exemplo JavaScript</title>
</head>
<body>
    <h1>Meu Primeiro JavaScript</h1>
    <script>
        document.write("Olá, mundo!");
    </script>
</body>
</html>
```

## Blocos JavaScript fora do HTML
Você também pode criar um arquivo JavaScript separado e referenciá-lo no seu arquivo HTML.
```html
<!DOCTYPE html>
<html>
<head>
    <title>Exemplo JavaScript</title>
    <script src="script.js"></script>
</head>
<body>
    <h1>Meu Primeiro JavaScript</h1>
</body>
</html>
```
E no arquivo `script.js`:
```javascript
document.write("Olá, mundo!");
```

## Buscar dados de um input
Você pode buscar dados de um input usando JavaScript com as propriedades `value`, `id` e `name`.
```html
<!DOCTYPE html>
<html>
<head>
    <title>Exemplo Input</title>
    <script>
        function mostrarValor() {
            var input = document.getElementById("meuInput");
            alert("Valor do input: " + input.value);
        }
    </script>
</head>
<body>
    <input type="text" id="meuInput" name="meuInputName" value="Texto de exemplo">
    <button onclick="mostrarValor()">Mostrar Valor</button>
</body>
</html>
```

## Aplicar estilo CSS em uma div
Você pode aplicar estilo CSS em uma div usando JavaScript.
```html
<!DOCTYPE html>
<html>
<head>
    <title>Exemplo CSS</title>
    <style>
        .minhaDiv {
            width: 100px;
            height: 100px;
            background-color: red;
        }
    </style>
    <script>
        function mudarEstilo() {
            var div = document.getElementById("minhaDiv");
            div.style.backgroundColor = "blue";
            div.style.width = "200px";
            div.style.height = "200px";
        }
    </script>
</head>
<body>
    <div id="minhaDiv" class="minhaDiv"></div>
    <button onclick="mudarEstilo()">Mudar Estilo</button>
</body>
</html>
```

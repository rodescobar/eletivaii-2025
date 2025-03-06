# Aula 04 - Manipulação de Tabelas com JavaScript

## Índice
1. [Estrutura HTML](#estrutura-html)
2. [JavaScript para mover linhas](#javascript-para-mover-linhas)

## Estrutura HTML
Crie um arquivo HTML com duas tabelas, uma embaixo da outra. A primeira tabela deve conter 10 pessoas com nome, telefone e idade. Adicione uma seta para baixo na primeira tabela e uma seta para cima na segunda tabela.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Manipulação de Tabelas</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        th, td {
            border: 1px solid black;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
        .arrow {
            cursor: pointer;
        }
    </style>
</head>
<body>
    <table id="table1">
        <thead>
            <tr>
                <th>Nome</th>
                <th>Telefone</th>
                <th>Idade</th>
                <th>Ação</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Stefany</td>
                <td>123456789</td>
                <td>25</td>
                <td class="arrow" onclick="moveRow(this, 'down')">⬇️</td>
            </tr>
            <tr>
                <td>Maria</td>
                <td>987654321</td>
                <td>30</td>
                <td class="arrow" onclick="moveRow(this, 'down')">⬇️</td>
            </tr>
            <tr>
                <td>Pedro</td>
                <td>456123789</td>
                <td>22</td>
                <td class="arrow" onclick="moveRow(this, 'down')">⬇️</td>
            </tr>
            <tr>
                <td>Ana</td>
                <td>321654987</td>
                <td>28</td>
                <td class="arrow" onclick="moveRow(this, 'down')">⬇️</td>
            </tr>
            <tr>
                <td>Lucas</td>
                <td>654987321</td>
                <td>35</td>
                <td class="arrow" onclick="moveRow(this, 'down')">⬇️</td>
            </tr>
            <tr>
                <td>Carla</td>
                <td>789123456</td>
                <td>27</td>
                <td class="arrow" onclick="moveRow(this, 'down')">⬇️</td>
            </tr>
            <tr>
                <td>Paulo</td>
                <td>159753486</td>
                <td>33</td>
                <td class="arrow" onclick="moveRow(this, 'down')">⬇️</td>
            </tr>
            <tr>
                <td>Fernanda</td>
                <td>951357486</td>
                <td>29</td>
                <td class="arrow" onclick="moveRow(this, 'down')">⬇️</td>
            </tr>
            <tr>
                <td>Rafael</td>
                <td>753951486</td>
                <td>24</td>
                <td class="arrow" onclick="moveRow(this, 'down')">⬇️</td>
            </tr>
            <tr>
                <td>Juliana</td>
                <td>852963741</td>
                <td>26</td>
                <td class="arrow" onclick="moveRow(this, 'down')">⬇️</td>
            </tr>
        </tbody>
    </table>

    <table id="table2">
        <thead>
            <tr>
                <th>Nome</th>
                <th>Telefone</th>
                <th>Idade</th>
                <th>Ação</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td class="arrow" onclick="moveRow(this, 'up')">⬆️</td>
            </tr>
        </tbody>
    </table>

    <script src="script.js"></script>
</body>
</html>
```

## JavaScript para mover linhas
Crie um arquivo `script.js` para mover as linhas entre as tabelas quando as setas forem clicadas.

```javascript
// filepath: /C:/Users/Rodrigo/Desktop/aulas/eletivaii-2025/aula04/script.js
function moveRow(element, direction) {
    var row = element.parentNode;
    var table1 = document.getElementById('table1').getElementsByTagName('tbody')[0];
    var table2 = document.getElementById('table2').getElementsByTagName('tbody')[0];

    if (direction === 'down') {
        table2.appendChild(row);
        element.innerHTML = '⬆️';
        element.setAttribute('onclick', "moveRow(this, 'up')");
    } else {
        table1.appendChild(row);
        element.innerHTML = '⬇️';
        element.setAttribute('onclick', "moveRow(this, 'down')");
    }
}

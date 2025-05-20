<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jogo Simples com Dois Links</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        #gameArea1, #gameArea2 {
            width: 300px;
            height: 300px;
            margin: 0 auto;
            border: 2px solid black;
            display: none;
        }
        #gameArea1 {
            background-color: lightgreen;
        }
        #gameArea2 {
            background-color: lightcoral;
        }
        #movableBox {
            width: 50px;
            height: 50px;
            background-color: blue;
            position: relative;
            top: 0;
            left: 0;
        }
        #clickGame {
            font-size: 20px;
        }
    </style>
</head>
<body>

    <h1>Escolha um Jogo!</h1>
    <p>Clique em um dos links abaixo para começar:</p>
   
    <!-- Link para o jogo 1: mover quadrado -->
    <a href="javascript:void(0);" onclick="iniciarJogo1()">Mover Quadrado</a>
    <br><br>
    <!-- Link para o jogo 2: contar cliques -->
    <a href="javascript:void(0);" onclick="iniciarJogo2()">Contar Cliques</a>
   
    <!-- Área do Jogo 1 (Mover Quadrado) -->
    <div id="gameArea1">
        <h2>Jogo 1: Mover Quadrado</h2>
        <p>Use as setas do teclado para mover o quadrado!</p>
        <div id="movableBox"></div>
    </div>

    <!-- Área do Jogo 2 (Contar Cliques) -->
    <div id="gameArea2">
        <h2>Jogo 2: Contar Cliques</h2>
        <p>Clique no botão abaixo para ganhar pontos!</p>
        <button onclick="incrementarPontos()">Clique aqui!</button>
        <p id="clickGame">Pontos: 0</p>
    </div>

    <script>
        // Função para iniciar o Jogo 1 (Mover Quadrado)
        function iniciarJogo1() {
            document.getElementById('gameArea1').style.display = 'block';
            document.getElementById('gameArea2').style.display = 'none';
            alert("Jogo de Mover Quadrado Iniciado! Use as setas do teclado.");
        }

        // Função para iniciar o Jogo 2 (Contar Cliques)
        function iniciarJogo2() {
            document.getElementById('gameArea2').style.display = 'block';
            document.getElementById('gameArea1').style.display = 'none';
            alert("Jogo de Contagem de Cliques Iniciado! Clique no botão para ganhar pontos.");
        }

        // Função para mover o quadrado no Jogo 1
        const box = document.getElementById('movableBox');
        let posX = 0;
        let posY = 0;

        window.addEventListener('keydown', (event) => {
            if (event.key === 'ArrowUp') {
                posY -= 10;
            } else if (event.key === 'ArrowDown') {
                posY += 10;
            } else if (event.key === 'ArrowLeft') {
                posX -= 10;
            } else if (event.key === 'ArrowRight') {
                posX += 10;
            }

            box.style.top = posY + 'px';
            box.style.left = posX + 'px';
        });

        // Função para incrementar pontos no Jogo 2
        let pontos = 0;

        function incrementarPontos() {
            pontos++;
            document.getElementById('clickGame').innerHTML = "Pontos: " + pontos;
        }
    </script>

</body>
</html>

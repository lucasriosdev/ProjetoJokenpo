🎮 Jokenpô com Shrek 🟢
Este projeto é um simples jogo de Jokenpô (Pedra, Papel e Tesoura), onde o jogador enfrenta o Shrek. O jogo é feito com HTML, CSS e JavaScript, utilizando manipulação do DOM para atualizar os resultados e a pontuação.

🏗️ Estrutura do Código
📌 1. HTML - Estrutura do Jogo
O arquivo HTML define a estrutura do jogo, contendo:

Título e botões para escolher pedra, papel ou tesoura.
Mensagens para exibir o resultado da rodada.
Pontuação do jogador e do Shrek.
Importação do CSS para estilização.
Importação do JavaScript para a lógica do jogo.
html
Copiar
Editar
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jokenpô com Shrek</title>
    <link rel="stylesheet" href="./style.css">
</head>
<body>
    <div class="container">
        <h1>Jokenpô</h1>
        <div class="buttons">
            <button id="rock" onclick="playHuman('rock')">&#x1F44A</button>
            <button id="paper" onclick="playHuman('paper')">&#x1f590</button>
            <button id="scissors" onclick="playHuman('scissors')">&#x270c</button>
        </div>
        <p class="result"></p>
        <p class="your-score">Sua Pontuação: <span id="human-score">0</span></p>
        <p class="machine-score">Pontuação do Shrek: <span id="machine-score">0</span></p>
    </div>
    <script src="./script.js"></script>
</body>
</html>
🎨 2. CSS - Estilização do Jogo
O CSS define um fundo temático do Shrek, além de estilizar os botões e pontuação.

Fundo personalizado com uma imagem do Shrek.
Botões coloridos e interativos, mudando a opacidade ao passar o mouse.
Destaque na pontuação, diferenciando as cores do jogador e do Shrek.
css
Copiar
Editar
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background: url("https://c4.wallpaperflare.com/wallpaper/966/989/139/shrek-movies-animated-movies-dreamworks-hd-wallpaper-preview.jpg");
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

.container {
    padding: 20px;
    background-color: white;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.buttons {
    margin: 30px 0;
    display: flex;
    gap: 40px;
}

button {
    padding: 10px;
    font-size: 50px;
    cursor: pointer;
    border: none;
    border-radius: 10px;
    transition: opacity 0.5s ease-in-out;
}

button:hover {
    opacity: 0.7;
}

#rock {
    background-color: rgb(221, 0, 255);
}

#paper {
    background-color: rgb(248, 18, 18);
}

#scissors {
    background-color: rgb(89, 255, 0);
}

.your-score span {
    color: blue;
}

.machine-score span {
    color: rgb(254, 0, 0);
}
🕹️ 3. JavaScript - Lógica do Jogo
O JavaScript controla a lógica do jogo, processando a escolha do usuário e do Shrek.

Escolha do jogador (ao clicar no botão).
Escolha aleatória do Shrek usando Math.random().
Comparação de jogadas e atualização da pontuação.
Exibição do resultado (vitória, derrota ou empate).
javascript
Copiar
Editar
const result = document.querySelector('.result');
const humanScore = document.querySelector('#human-score');
const machineScore = document.querySelector('#machine-score');

let humanScoreNumber = 0;
let machineScoreNumber = 0;

const playHuman = (humanChoice) => {
    playTheGame(humanChoice, playMachine());
};

const playMachine = () => {
    const choices = ['rock', 'paper', 'scissors'];
    const randomNumber = Math.floor(Math.random() * 3);
    return choices[randomNumber];
};

const playTheGame = (human, machine) => {
    console.log("Humano: " + human + " | Máquina: " + machine);

    if (human === machine) {
        result.innerHTML = "Deu Empate!";
    } else if (
        (human === 'paper' && machine === 'rock') ||
        (human === 'rock' && machine === 'scissors') ||
        (human === 'scissors' && machine === 'paper')
    ) {
        humanScoreNumber++;
        humanScore.innerHTML = humanScoreNumber;
        result.innerHTML = "Você ganhou!";
    } else {
        machineScoreNumber++;
        machineScore.innerHTML = machineScoreNumber;
        result.innerHTML = "Você perdeu para o Shrek!";
    }
};
🚀 Melhorias Futuras
🔹 Adicionar sons ao clicar nos botões.
🔹 Animação para mostrar as escolhas do jogador e do Shrek.
🔹 Modo multiplayer para jogar com amigos.
🔹 Pontuação persistente usando LocalStorage.


📌 Conclusão
Este projeto simples e divertido demonstra manipulação do DOM, estilização e lógica em JavaScript. Além disso, o tema do Shrek deixa tudo mais engraçado! 🟢😆

🎮 Agora é só jogar! 🎮

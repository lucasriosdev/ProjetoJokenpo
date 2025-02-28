# Jokenpô com Shrek

Este é um jogo simples de Jokenpô (Pedra, Papel, Tesoura) com um tema inspirado no personagem Shrek. A cada jogada, o jogador escolhe uma opção e enfrenta o Shrek, que faz sua escolha de forma aleatória.

## Estrutura de arquivos

- `index.html` - O arquivo HTML que contém a estrutura do jogo.
- `style.css` - O arquivo CSS para estilizar a interface do jogo.
- `script.js` - O arquivo JavaScript que contém a lógica do jogo.

## Como jogar

1. Clique nos botões "Pedra", "Papel" ou "Tesoura" para fazer sua jogada.
2. O Shrek fará sua jogada automaticamente.
3. O resultado aparecerá abaixo, junto com a atualização das pontuações.

## Captura de tela

Aqui está uma captura de tela do projeto:

![Captura de tela do projeto](caminho/para/imagem.png)

## Código

### `index.html`

```html
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

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body{
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

.container{
    padding: 20px;
    background-color: white;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.buttons{
    margin: 30px 0;
    display: flex;
    gap: 40px;
}

button{
    padding: 10px;
    font-size: 50px;
    cursor: pointer;
    border: none;
    border-radius: 10px;
    transition: opacity 0.5 ease-in-out;
}

button:hover{
    opacity: 0.7;
}

#rock{
    background-color: rgb(221, 0, 255);
}

#paper{
    background-color: rgb(248, 18, 18);
}

#scissors{
    background-color: rgb(89, 255, 0);
}

p{
    font-weight: bold;
    margin-bottom: 10px;
}

.your-score span{
    color: blue;
}

.machine-score span{
    color: rgb(254, 0, 0);
}
const result = document.querySelector('.result')
const humanScore = document.querySelector('#human-score')
const MachineScore = document.querySelector('#machine-score')

let humanScoreNumber = 0
let machineScoreNumber = 0

const playHuman = (humanChoice) => {
    playTheGame(humanChoice, playMachine())
}

const playMachine = () => {
    const choices = ['rock', 'paper', 'scissors']
    const randomNumber = Math.floor(Math.random() * 3)
    return choices[randomNumber]
}

const playTheGame = (human, machine) => {
    console.log("Humano:" + human + "Maquina:" + machine)

    if (human === machine) {
        result.innerHTML = "Deu Empate!"
    } else if ((human === 'paper' && machine === 'rock') ||
        (human === 'rock' && machine === 'scissors') ||
        (human === 'scissors' && machine === 'paper')
    ) {
        humanScoreNumber++
        humanScore.innerHTML = humanScoreNumber

        result.innerHTML = "Você ganhou!"
    } else {
        machineScoreNumber++
        MachineScore.innerHTML = machineScoreNumber
        result.innerHTML = "Você perdeu para a o Shrek"
    }
}
Funcionalidade
O jogo segue as regras clássicas de Jokenpô:

Pedra (🗻) ganha de Tesoura (✂️)
Tesoura (✂️) ganha de Papel (📜)
Papel (📜) ganha de Pedra (🗻)
O jogo também mantém o placar de ambos os jogadores, o usuário e o Shrek.



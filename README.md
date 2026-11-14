<!DOCTYPE html>
<html>
<head>
    <title>Stone Paper Scissors</title>

    <style>
        body {
            background: linear-gradient(135deg, #141e30, #243b55);
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 40px 15px;
        }

        .game {
            background: white;
            color: #222;
            max-width: 450px;
            margin: auto;
            padding: 30px 20px;
            border-radius: 20px;
            box-shadow: 0 5px 25px #0005;
        }

        h1 {
            color: #243b55;
        }

        .choices {
            display: flex;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
            margin: 25px 0;
        }

        button {
            padding: 15px;
            font-size: 18px;
            border: none;
            border-radius: 12px;
            background: #243b55;
            color: white;
            cursor: pointer;
        }

        button:hover {
            background: #426b99;
            transform: scale(1.05);
        }

        #result {
            font-size: 21px;
            font-weight: bold;
            margin: 20px;
        }

        #score {
            font-size: 18px;
            color: #243b55;
        }

        .reset {
            background: #e74c3c;
        }
    </style>
</head>

<body>

    <div class="game">

        <h1>✊ Stone Paper Scissors ✋</h1>
        <p>Choose your move and beat the computer!</p>

        <div class="choices">
            <button onclick="play(1)">✊ Stone</button>
            <button onclick="play(2)">✋ Paper</button>
            <button onclick="play(3)">✌️ Scissors</button>
        </div>

        <h3 id="moves">Your move: - | Computer: -</h3>

        <div id="result">Let's Play!</div>

        <div id="score">
            You: 0 | Computer: 0 | Draws: 0
        </div>

        <br>

        <button class="reset" onclick="resetGame()">
            Reset Game
        </button>

    </div>

    <script>
        let playerScore = 0;
        let computerScore = 0;
        let draws = 0;

        const names = ["", "Stone", "Paper", "Scissors"];

        function play(user) {

            let computer = Math.floor(Math.random() * 3) + 1;

            document.getElementById("moves").innerText =
                "Your move: " + names[user] +
                " | Computer: " + names[computer];

            let result = "";

            if (user === computer) {
                result = "🤝 It's a Draw!";
                draws++;
            }
            else if (
                (user === 1 && computer === 3) ||
                (user === 2 && computer === 1) ||
                (user === 3 && computer === 2)
            ) {
                result = "🎉 You Won!";
                playerScore++;
            }
            else {
                result = "😢 Computer Won!";
                computerScore++;
            }

            document.getElementById("result").innerText = result;

            document.getElementById("score").innerText =
                "You: " + playerScore +
                " | Computer: " + computerScore +
                " | Draws: " + draws;
        }

        function resetGame() {
            playerScore = 0;
            computerScore = 0;
            draws = 0;

            document.getElementById("moves").innerText =
                "Your move: - | Computer: -";

            document.getElementById("result").innerText =
                "Let's Play!";

            document.getElementById("score").innerText =
                "You: 0 | Computer: 0 | Draws: 0";
        }
    </script>

</body>
</html>

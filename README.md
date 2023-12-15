<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>XOXO Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
        }
        .game {
            display: grid;
            grid-template-columns: repeat(3, 100px);
            grid-template-rows: repeat(3, 100px);
            gap: 10px;
            border: 2px solid #000;
            padding: 10px;
            background-color: #fff;
        }
        .cell {
            width: 100px;
            height: 100px;
            border: 1px solid #000;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 24px;
            font-weight: bold;
            cursor: pointer;
        }
        .cell:hover {
            background-color: #ddd;
        }
        .game-over {
            background-color: rgba(255, 0, 0, 0.5);
        }
    </style>
</head>
<body>
    <div class="game"></div>
    <script>
        const cells = [];
        const gameOver = () => {
            for (let i = 0; i < 3; i++) {
                if (cells[i * 3].textContent === cells[i * 3 + 1].textContent && cells[i * 3].textContent === cells[i * 3 + 2].textContent && cells[i * 3].textContent !== '') {
                    return true;
                }
                if (cells[i].textContent === cells[i + 3].textContent && cells[i].textContent === cells[i + 6].textContent && cells[i].textContent !== '') {
                    return true;
                }
            }
            if (cells[0].textContent === cells[4].textContent && cells[0].textContent === cells[8].textContent && cells[0].textContent !== '') {
                return true;
            }
            if (cells[2].textContent === cells[4].textContent && cells[2].textContent === cells[6].textContent && cells[2].textContent !== '') {
                return true;
            }
            return false;
        };
        const draw = () => {
            for (let i = 0; i < 9; i++) {
                if (cells[i].textContent === '') {
                    return false;
                }
            }
            return true;
        };
        const resetGame = () => {
            for (let i = 0; i < 9; i++) {
                cells[i].textContent = '';
            }
        };
        const handleCellClick = (cell) => {
            if (cell.textContent === '') {
                cell.textContent = 'X';
                if (gameOver()) {
                    document.querySelector('.game').classList.add('game-over');
                } else if (draw()) {
                    alert('Draw!');
                    resetGame();
                } else {
                    cell.textContent = 'O';
                    if (gameOver()) {
                        document.querySelector('.game').classList.add('game-over');
                    } else if (draw()) {
                        alert('Draw!');
                        resetGame();
                    }
                }
            }
        };
        const createGame = () => {
            const game = document.querySelector('.game');
            for (let i = 0; i < 9; i++) {
                const cell = document.createElement('div');
                cell.classList.add('cell');
                cell.textContent = '';
                cell.addEventListener('click', () =>

<!---
kennyblack92/kennyblack92 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

- 👋 Hi, I’m @reelg
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
reelg/reelg is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
html

<!DOCTYPE html>

<html>

<head>
	<title>Tetris</title>
	<style>
		canvas {
			border: 1px solid black;
			background-color: #eee;
		}
	</style>

</head>

<body>
	<canvas id="game" width="400" height="400"></canvas>
	<script>
		var canvas = document.getElementById("game");
		var ctx = canvas.getContext("2d");

		// Game variables
		var gameOver = false;
		var score = 0;
		var level = 1;
		var speed = 1000;
		var rows = 20;
		var cols = 10;
		var cellSize = 20;
		var board = new Array(rows);
		for (var i = 0; i < rows; i++) {
			board[i] = new Array(cols);
			for (var j = 0; j < cols; j++) {
				board[i][j] = 0;
			}
		}
		var currentPiece = {
			shape: 0,
			rotation: 0,
			x: Math.floor(cols / 2) - 1,
			y: 0
		};
		var nextPiece = {
			shape: 0,
			rotation: 0
		};
		var holdPiece = null;

		// Piece shapes and rotations
		var shapes = [
			[
				[1, 1, 1],
				[0, 1, 0]
			],
			[
				[0, 2, 2],
				[2, 2, 0]
			],
			[
				[3, 3, 0],
				[0, 3, 3]
			],
			[
				[4, 0, 0],
				[4, 4, 4]
			],
			[
				[0, 0, 5],
				[5, 5, 5]
    

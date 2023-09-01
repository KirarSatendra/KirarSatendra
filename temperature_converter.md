<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport"
		content="width=device-width,
				initial-scale=1.0">
	<style>
		* {
			margin: 0;
			padding: 0;
			font-family:
				Verdana, Geneva, Tahoma, sans-serif;
		}
		.container {
			width: 100%;
			height: 100vh;
            background-image:
            linear-gradient(rgb(224, 136, 20),
                            rgb(173, 16, 10));
			
            display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}
		.container h1 {
            box-shadow: 1px 3px 5px rgb(217, 250, 29);
			color: rgb(80, 52, 240);
			font-size: 30px;
			font-weight: 40;
		}
		.converter-row {
            margin: 20px;
            font-size: 40px;
			width: 40%;
            box-shadow: 1px 3px 5px rgb(24, 182, 71);
			background: rgb(44, 14, 212);
			border-radius: 100px;
			padding: 20px 20px;
		}
		.col {
			text-align: center;
		}
		.col label {
			font-size: 25px;
			color: #29e211;
		}
		.col input {
			width: 120px;
			height: 25px;
			background: rgb(175, 166, 43);
			box-shadow: 1px 3px 5px rgb(182, 24, 24);
			border-radius: 100px;
			text-align:center;
		}
		.btn {
			margin-left: 220px;
			margin-top: 15px;
			padding: 10px 10px;
		 	width: 100px;
			background-color: #B64B39;
			color: #fff;
			border-radius: 40px;
			font-size: 15px;
			
		}

		
	</style>
</head>
<body>
	<div class="container">
		<h1>Temperature Converter</h1>
		<div class="converter-row">
			<div class="col">
				<label>Fahrenheit</label>
				<input type="number"
					id="fahrenheit">
			</div>
			<div class="col">
				<label>Celsius</label>
				<input type="number"
					id="celsius">
			</div>

			<div class="col">
				<label>Kelvin</label>
				<input type="number"
					id="kelvin">
			</div>
			<div id="btncontainer">
				<input type="reset" name="reset" id="rest" class="btn"  onclick="location.reload()">
			</div>
		</div>
		</div>
	</div>
	<script>
		let celsius =
			document.getElementById('celsius');
		let fahrenheit =
			document.getElementById('fahrenheit');
		let kelvin =
			document.getElementById('kelvin');
		celsius.oninput = function () {
			let f = (parseFloat(celsius.value) * 9) / 5 + 32;
			fahrenheit.value = parseFloat(f.toFixed(2));

			let k = (parseFloat(celsius.value) + 273.15);
			kelvin.value = parseFloat(k.toFixed(2));
		}
		fahrenheit.oninput = function () {
			let c = ((parseFloat(
				fahrenheit.value) - 32) * 5) / 9;
			celsius.value = parseFloat(c.toFixed(2));

			let k = (parseFloat(
				fahrenheit.value) - 32) * 5 / 9 + 273.15;
			kelvin.value = parseFloat(k.toFixed(2));
		}
		kelvin.oninput = function () {
			let f = (parseFloat(
				kelvin.value) - 273.15) * 9 / 5 + 32;
			fahrenheit.value = parseFloat(f.toFixed(2));

			let c = (parseFloat(kelvin.value) - 273.15);
			celsius.value = parseFloat(c.toFixed(2));
		}
	</script>
</body>
</html>

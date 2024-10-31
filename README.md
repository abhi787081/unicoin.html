<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Web App</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #121212; /* Dark background */
            color: #fff; /* White text */
        }
    </style>
</head>
<body>
    <h1>Welcome to UNi Coin</h1>
    <br>
   i am  abhi my testing is sucessful
    <h6>click to earn uni coin</h6>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clicker App</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #121212;
            color: #fff;
            font-family: Arial, sans-serif;
        }
        #coin {
            width: 100px;
            height: 100px;
            background-image: url('https://i.postimg.cc/qtfBqzsv/photo-2024-11-01-02-10-55.jpg'); /* Replace with your coin image URL */
            background-size: cover;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            margin-bottom: 20px;
            box-shadow: 0 0 10px rgba(8, 235, 45, 0.5);
            transition: transform 0.1s;
        }
        #coin:active {
            transform: scale(0.95);
        }
        #wallet {
            background-color: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        #walletAmount {
            font-size: 24px;
        }
        .uni-coin {
            color: rgba(255, 255, 255, 0.5);
            font-size: 14px;
        }
        #boostButton {
            background-color: #f39c12;
            color: #fff;
            border: none;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 14px;
        }
        #boostButton.active {
            background-color: #e74c3c;
        }
    </style>
</head>
<body>
    <div id="coin"></div>
    <div id="wallet">
        <div id="walletAmount">Wallet: 0</div>
        <button id="boostButton">Boost</button>
        <div class="uni-coin">Uni Coin</div>
    </div>
    <script>
        let clickCount = 0;
        let isBoostActive = false;
        let boostTimeout;
        document.getElementById("coin").addEventListener("click", function() {
            if (isBoostActive) {
                clickCount += 5;
            } else {
                clickCount += 1;
            }
            document.getElementById("walletAmount").innerText = "Wallet: " + clickCount;
            if ("vibrate" in navigator) {
                navigator.vibrate(100);
            }
        });
        document.getElementById("boostButton").addEventListener("click", function() {
            if (!isBoostActive) {
                isBoostActive = true;
                document.getElementById("boostButton").classList.add("active");
                boostTimeout = setTimeout(() => {
                    isBoostActive = false;
                    document.getElementById("boostButton").classList.remove("active");
                }, 20000);
            }
        });
    </script>

</body>
</html>

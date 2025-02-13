<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #ffebee;
            color: #d32f2f;
            overflow: hidden;
        }
        .container {
            margin-top: 100px;
        }
        .heart {
            font-size: 50px;
        }
        .btn {
            background-color: #d32f2f;
            color: white;
            padding: 15px 30px;
            font-size: 20px;
            border: none;
            cursor: pointer;
            margin: 10px;
        }
        .btn:hover {
            background-color: #b71c1c;
        }
        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            background-color: red;
            opacity: 0.7;
            animation: fall 3s linear infinite;
        }
        @keyframes fall {
            0% { transform: translateY(-100px) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(720deg); opacity: 0; }
        }
        .fireworks {
            position: fixed;
            width: 5px;
            height: 5px;
            background-color: yellow;
            border-radius: 50%;
            animation: explode 1.5s ease-out forwards;
        }
        @keyframes explode {
            0% { transform: scale(1); opacity: 1; }
            50% { transform: scale(20); opacity: 1; }
            100% { transform: scale(30); opacity: 0; }
        }
        .big-heart {
            position: fixed;
            left: 50%;
            top: 50%;
            font-size: 120px;
            color: red;
            opacity: 0;
            transform: translate(-50%, -50%) scale(0.5);
            animation: glowHeart 2s ease-out forwards;
        }
        @keyframes glowHeart {
            0% { transform: translate(-50%, -50%) scale(0.5); opacity: 0; }
            50% { transform: translate(-50%, -50%) scale(1.5); opacity: 1; text-shadow: 0 0 30px red; }
            100% { transform: translate(-50%, -50%) scale(1); opacity: 1; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Hey Babe! 💖</h1>
        <p>Will you be my Valentine?</p>
        <p>Will you make me the happiest man alive?</p>
        <p class="heart">❤️❤️❤️</p>
        <button class="btn" onclick="celebrate()">Yes</button>
        <button class="btn" onclick="alert('Oh no! 😢 But I still love you!')">No</button>
    </div>
    <script>
        function celebrate() {
            alert('Yay! I knew you would say yes! ❤️');
            let bigHeart = document.createElement('div');
            bigHeart.classList.add('big-heart');
            bigHeart.innerHTML = '❤️';
            document.body.appendChild(bigHeart);
            
            setTimeout(() => {
                for (let i = 0; i < 100; i++) {
                    let confetti = document.createElement('div');
                    confetti.classList.add('confetti');
                    confetti.style.left = Math.random() * 100 + 'vw';
                    confetti.style.backgroundColor = ['red', 'pink', 'gold', 'white'][Math.floor(Math.random() * 4)];
                    confetti.style.animationDuration = (Math.random() * 3 + 2) + 's';
                    document.body.appendChild(confetti);
                    setTimeout(() => confetti.remove(), 5000);
                }
                for (let i = 0; i < 10; i++) {
                    setTimeout(() => {
                        let fireworks = document.createElement('div');
                        fireworks.classList.add('fireworks');
                        fireworks.style.left = Math.random() * 100 + 'vw';
                        fireworks.style.top = Math.random() * 50 + 25 + 'vh';
                        fireworks.style.backgroundColor = ['yellow', 'red', 'blue', 'green', 'pink'][Math.floor(Math.random() * 5)];
                        document.body.appendChild(fireworks);
                        setTimeout(() => fireworks.remove(), 1500);
                    }, i * 200);
                }
            }, 2000);
        }
    </script>
</body>
</html>
# Valentine-propose
Valentine propose

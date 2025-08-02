<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday!</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Arial', sans-serif;
            background: #392A48;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow-x: hidden;
        }
        
        .container {
            text-align: center;
            padding: 40px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
            border: 1px solid rgba(255, 255, 255, 0.1);
            max-width: 600px;
            margin: 20px;
            animation: slideIn 1s ease-out;
        }
        
        .birthday-text {
            font-size: 3.5rem;
            color: #fff;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            animation: bounce 2s infinite;
        }
        
        .wish-text {
            font-size: 1.3rem;
            color: #f0f0f0;
            margin-bottom: 30px;
            line-height: 1.6;
        }
        
        .name {
            font-size: 2.5rem;
            color: #9E7BB5;
            margin: 20px 0;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            animation: glow 2s ease-in-out infinite alternate;
        }
        
        .balloons {
            font-size: 4rem;
            margin: 20px 0;
            animation: float 3s ease-in-out infinite;
        }
        
        .cake-button {
            background: linear-gradient(45deg, #9E7BB5, #8A6BA1);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.2rem;
            border-radius: 50px;
            cursor: pointer;
            margin: 20px 10px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(158, 123, 181, 0.4);
        }
        
        .cake-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(158, 123, 181, 0.6);
        }
        
        .surprise-message {
            display: none;
            margin-top: 20px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            color: #fff;
            font-size: 1.1rem;
            animation: fadeIn 0.5s ease-in;
        }
        
        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            background: #e67e22;
            animation: confetti-fall 3s linear infinite;
        }
        
        .confetti:nth-child(odd) { background: #3498db; }
        .confetti:nth-child(3n) { background: #2c3e50; }
        .confetti:nth-child(4n) { background: #f39c12; }
        .confetti:nth-child(5n) { background: #27ae60; }
        
        @keyframes slideIn {
            from { opacity: 0; transform: translateY(50px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }
        
        @keyframes glow {
            from { text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5), 0 0 10px #9E7BB5; }
            to { text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5), 0 0 20px #9E7BB5, 0 0 30px #9E7BB5; }
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes confetti-fall {
            to {
                transform: translateY(100vh) rotate(360deg);
            }
        }
        
        @media (max-width: 768px) {
            .birthday-text { font-size: 2.5rem; }
            .name { font-size: 2rem; }
            .wish-text { font-size: 1.1rem; }
            .container { padding: 20px; margin: 10px; }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="balloons">🎂🎉🍰</div>
        <h1 class="birthday-text">Happy Birthday!</h1>
        <div class="name">Papa</div>
        <p class="wish-text">
            Wishing the most amazing papa a fantastic birthday! Thank you for all the wisdom, 
            love, and papa jokes over the years. Hope your special day is filled with everything 
            you enjoy most - maybe some peace, your favorite food, and time to relax!
        </p>
        <button class="cake-button" onclick="showSurprise()">🎂 Papa's Special Message!</button>
        <button class="cake-button" onclick="createConfetti()">🎊 Celebration Time!</button>
        
        <div class="surprise-message" id="surprise">
            <h3>🏆 To the Best Papa Ever 🏆</h3>
            <p>Thanks for being our rock, our guide, and our biggest supporter. You've taught us so much and made every day better just by being you. Here's to another year of your awesome papa energy!</p>
        </div>
    </div>

    <script>
        function showSurprise() {
            const surprise = document.getElementById('surprise');
            if (surprise.style.display === 'none' || surprise.style.display === '') {
                surprise.style.display = 'block';
            } else {
                surprise.style.display = 'none';
            }
        }
        
        function createConfetti() {
            for (let i = 0; i < 50; i++) {
                setTimeout(() => {
                    const confetti = document.createElement('div');
                    confetti.className = 'confetti';
                    confetti.style.left = Math.random() * 100 + 'vw';
                    confetti.style.animationDelay = Math.random() * 3 + 's';
                    confetti.style.animationDuration = (Math.random() * 3 + 2) + 's';
                    document.body.appendChild(confetti);
                    
                    setTimeout(() => {
                        confetti.remove();
                    }, 5000);
                }, i * 50);
            }
        }
        
        // Auto-create some confetti on page load
        window.addEventListener('load', () => {
            setTimeout(createConfetti, 1000);
        });
    </script>
</body>
</html>

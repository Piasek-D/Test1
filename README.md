<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <title>🐣 Alicjo, jesteś wyjątkowa! 🐰</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Rubik+Bubbles&display=swap');

        body {
            margin: 0;
            padding: 0;
            font-family: 'Rubik Bubbles', cursive;
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            color: #333;
            text-align: center;
            overflow: hidden;
        }

        h1 {
            font-size: 3em;
            margin-top: 50px;
            animation: pop 1s infinite alternate;
        }

        @keyframes pop {
            0% { transform: scale(1); }
            100% { transform: scale(1.05); }
        }

        .easter-image, .skull-image {
            margin-top: 30px;
            max-width: 60%;
            border-radius: 30px;
            box-shadow: 0 8px 16px rgba(0,0,0,0.3);
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .warning {
            color: red;
            font-size: 2.5em;
            margin-top: 50px;
            animation: shake 0.5s infinite;
        }

        @keyframes shake {
            0% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            50% { transform: translateX(5px); }
            75% { transform: translateX(-5px); }
            100% { transform: translateX(0); }
        }

        .emoji {
            font-size: 2em;
            margin-top: 20px;
            animation: spin 4s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        button {
            margin-top: 20px;
            padding: 15px 30px;
            font-size: 1.2em;
            border: none;
            border-radius: 15px;
            background-color: #ff69b4;
            color: white;
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            transition: transform 0.2s;
        }

        button:hover {
            transform: scale(1.1);
            background-color: #ff1493;
        }
    </style>
</head>
<body>
    <h1 id="greeting"></h1>
    <div id="content"></div>

    <script>
        const name = prompt("Jak masz na imię?");
        const greeting = document.getElementById("greeting");
        const content = document.getElementById("content");

        if (name && name.trim().toLowerCase() === "alicja") {
            greeting.innerHTML = "🎉 Alicjo! Wesołych Świąt Wielkanocnych! 🐰🚴‍♀️😺";

            const img = document.createElement("img");
            img.src = "https://cdn.pixabay.com/photo/2017/03/27/14/56/easter-2178578_1280.jpg"; 
            img.alt = "Króliczek, kotek, rower - Wielkanoc";
            img.className = "easter-image";
            content.appendChild(img);

            const audio = document.createElement("audio");
            audio.src = "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3"; // Podmień na Forever Young jeśli masz mp3!
            audio.autoplay = true;
            audio.volume = 0.5;
            content.appendChild(audio);

            // Stop muzyki po 10 sekundach
            setTimeout(() => {
                audio.pause();
                audio.currentTime = 0;
            }, 10000);

            const emoji = document.createElement("div");
            emoji.className = "emoji";
            emoji.innerText = "🥚🐇🌸🚴‍♀️😹";
            content.appendChild(emoji);

        } else {
            greeting.innerText = "💀 To nie dla Ciebie! 💀";

            const skull = document.createElement("img");
            skull.src = "https://cdn.pixabay.com/photo/2016/03/27/22/16/skull-1282509_1280.jpg"; 
            skull.alt = "Czaszka";
            skull.className = "skull-image";
            content.appendChild(skull);

            const warning = document.createElement("div");
            warning.className = "warning";
            warning.innerText = "🚫 Niezidentyfikowany użytkownik!";
            content.appendChild(warning);
        }
    </script>
</body>
</html>

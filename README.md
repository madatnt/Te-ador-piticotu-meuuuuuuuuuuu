# Te-ador-piticotu-meuuuuuuuuuuu
Multumesc ca faci parte din viata meaaa te iubiiii cel mai multtttt
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <title>Te iubesc</title>
    <style>
        :root {
            --background-day: #ffc0cb; /* roz ziua */
            --background-night: #0d1b2a; /* albastru închis noaptea */
        }

        body {
            background-color: var(--background-day);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            text-align: center;
            overflow: hidden;
            position: relative;
            transition: background-color 1s ease;
        }

        h1 {
            color: #d63384;
            font-size: 3em;
            margin-bottom: 60px;
            max-width: 90%;
        }

        .hearts {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            max-width: 800px;
            z-index: 1;
        }

        .heart {
            width: 60px;
            height: 60px;
            background-color: red;
            position: relative;
            transform: rotate(-45deg);
            animation: pulse 1.2s infinite ease-in-out;
        }

        .heart::before,
        .heart::after {
            content: "";
            width: 60px;
            height: 60px;
            background-color: red;
            border-radius: 50%;
            position: absolute;
        }

        .heart::before {
            top: -30px;
            left: 0;
        }

        .heart::after {
            left: 30px;
            top: 0;
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1) rotate(-45deg);
            }
            50% {
                transform: scale(1.3) rotate(-45deg);
            }
        }

        /* Responsive hearts on mobile */
        @media (max-width: 600px) {
            .heart {
                width: 40px;
                height: 40px;
            }

            .heart::before,
            .heart::after {
                width: 40px;
                height: 40px;
            }

            h1 {
                font-size: 2em;
            }

            .animated-message {
                font-size: 1.2em;
            }
        }

        .animated-message {
            margin-top: 40px;
            font-size: 1.5em;
            color: #880e4f;
            animation: fadeIn 2s ease-in-out;
            z-index: 1;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .signature {
            position: absolute;
            bottom: 10px;
            right: 15px;
            font-size: 1em;
            color: #6d214f;
            opacity: 0.8;
            z-index: 1;
        }

        /* inimioare care cad */
        .falling-heart {
            position: absolute;
            top: -50px;
            font-size: 20px;
            animation: fall linear infinite;
            color: red;
            opacity: 0.7;
            z-index: 0;
        }

        @keyframes fall {
            to {
                transform: translateY(110vh);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <h1>Te iubesc și te ador, piticotu’ meu 💖</h1>

    <div class="hearts">
        <div class="heart"></div>
        <div class="heart"></div>
        <div class="heart"></div>
        <div class="heart"></div>
        <div class="heart"></div>
        <div class="heart"></div>
        <div class="heart"></div>
    </div>

    <p class="animated-message">Ești tot ce mi-am dorit 💞</p>

    <div class="signature">Cu drag, nebunu' tău</div>

    <!-- Inimioare care cad -->
    <script>
        const createFallingHeart = () => {
            const heart = document.createElement('div');
            heart.classList.add('falling-heart');
            heart.textContent = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = 3 + Math.random() * 3 + 's';
            document.body.appendChild(heart);

            // Elimină inimioara după cădere
            setTimeout(() => {
                heart.remove();
            }, 6000);
        };

        // Creează inimioare continuu
        setInterval(createFallingHeart, 400);
    </script>

    <!-- Tranziție zi/noapte -->
    <script>
        const hour = new Date().getHours();
        const isNight = hour >= 20 || hour < 6;
        document.body.style.backgroundColor = isNight ? getComputedStyle(document.documentElement).getPropertyValue('--background-night') : getComputedStyle(document.documentElement).getPropertyValue('--background-day');
    </script>

</body>
</html>

<!DOCTYPE html>
<html>
<head>
    <title>Odtwarzacz Muzyki</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-image: url('LDp.jpg');
            background-size: cover;
            background-position: center;
        }

        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: inherit;
            filter: blur(5px); /* Rozmycie tła */
            z-index: -1;
        }
    </style>
</head>
<body>
    <h1>Odtwarzacz Muzyki</h1>
    
    <audio controls id="audioPlayer">
        <source src="marzenie-pewnej-dziewczyny.mp3" type="audio/mpeg">
        Twoja przeglądarka nie obsługuje odtwarzania dźwięku.
    </audio>


    <img src="LDp.jpg" alt="Opis obrazka"
    alt="Opis obrazka"
    width="200">


    <div>
        <button onclick="skipTime(5)">Przewiń w przód o 5 sekund</button>
        <button onclick="skipTime(-5)">Przewiń wstecz o 5 sekund</button>
        <button onclick="skipTime(10)">Przewiń w przód o 10 sekund</button>
        <button onclick="skipTime(-10)">Przewiń wstecz o 10 sekund</button>
        <button onclick="skipTime(15)">Przewiń w przód o 15 sekund</button>
        <button onclick="skipTime(-15)">Przewiń wstecz o 15 sekund</button>
        <button onclick="skipTime(20)">Przewiń w przód o 20 sekund</button>
        <button onclick="skipTime(-20)">Przewiń wstecz o 20 sekund</button>
        <button onclick="skipTime(30)">Przewiń w przód o 30 sekund</button>
        <button onclick="skipTime(-30)">Przewiń wstecz o 30 sekund</button>
    </div>
    
    <script>
        const audio = document.getElementById("audioPlayer");

        function skipTime(seconds) {
            audio.currentTime += seconds;
        }

        audio.addEventListener("play", function() {
            console.log("Odtwarzam muzykę");
        });

        audio.addEventListener("pause", function() {
            console.log("Odtwarzanie zatrzymane");
        });

        // Obsługa klawiszy
        document.addEventListener("keydown", function(event) {
            if (event.key === "ArrowLeft") {
                skipTime(-5);
            } else if (event.key === "ArrowRight") {
                skipTime(5);
            } else if (event.key === " ") {
                if (audio.paused) {
                    audio.play();
                } else {
                    audio.pause();
                }
            }
        });
    </script>
</body>
</html>

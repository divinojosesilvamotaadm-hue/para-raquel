<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>Para Raquel 🎀</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary-pink: #fce4ec;
            --accent-red: #990000;
            --text-dark: #2d3436;
            --whatsapp-green: #25D366;
            --safe-top: env(safe-area-inset-top);
            --safe-bottom: env(safe-area-inset-bottom);
        }

        * { 
            margin: 0; 
            padding: 0; 
            box-sizing: border-box; 
            -webkit-tap-highlight-color: transparent;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        body {
            background: linear-gradient(135deg, #fce4ec 0%, #ffe1e1 100%);
            font-family: 'Poppins', sans-serif;
            color: var(--text-dark);
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: calc(30px + var(--safe-top)) 20px calc(20px + var(--safe-bottom));
            min-height: 100vh;
        }

        .container { 
            max-width: 450px; 
            width: 100%; 
            animation: fadeInUp 0.8s ease-out;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border-radius: 25px;
            padding: 35px 20px;
            box-shadow: 0 15px 35px rgba(153, 0, 0, 0.08);
            text-align: center;
            border: 1px solid rgba(255,255,255,0.5);
        }

        h1 { 
            font-family: 'Dancing Script', cursive; 
            font-size: clamp(2.3rem, 9vw, 3.2rem);
            color: var(--accent-red); 
            margin-bottom: 12px; 
        }
        
        .intro-text { 
            font-size: 0.92rem; 
            color: #555; 
            margin-bottom: 25px; 
            line-height: 1.5;
        }

        .generator-box {
            background: #fff;
            border: 2px solid var(--primary-pink);
            padding: 25px 20px;
            border-radius: 22px;
            margin-bottom: 20px;
            min-height: 220px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        #cantada-display {
            font-weight: 600;
            color: var(--accent-red);
            font-size: 1.05rem;
            font-style: italic;
            line-height: 1.5;
            word-wrap: break-word;
            width: 100%;
        }

        .btn-generate {
            background: var(--accent-red);
            color: white;
            border: none;
            padding: 16px 35px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.9rem;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(153, 0, 0, 0.2);
            transition: 0.2s;
            margin-top: 15px;
            touch-action: manipulation;
        }

        .btn-whatsapp {
            background: var(--whatsapp-green);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.75rem;
            cursor: pointer;
            text-decoration: none;
            display: none; 
            align-items: center;
            gap: 8px;
            margin-top: 15px;
            animation: fadeInUp 0.5s ease-out;
        }

        .btn-generate:active, .btn-whatsapp:active {
            transform: scale(0.96);
        }

        .timer-box {
            background: var(--accent-red);
            color: white;
            padding: 18px;
            border-radius: 22px;
            margin: 20px 0;
            box-shadow: 0 8px 20px rgba(153, 0, 0, 0.1);
        }

        #timer { 
            font-size: 1.6rem; 
            font-weight: 700; 
            letter-spacing: 1px;
            font-variant-numeric: tabular-nums;
        }

        .footer-legacy {
            margin-top: auto;
            padding: 30px 0 10px;
            font-size: 0.65rem;
            text-transform: uppercase;
            letter-spacing: 1.2px;
            color: #888;
            text-align: center;
            line-height: 1.6;
        }

        .highlight { color: var(--accent-red); font-weight: 600; }
    </style>
</head>
<body>

    <div class="container">
        <main class="glass-card">
            <span style="font-size: 2.2rem;">🕊️</span>
            <h1>Para Raquel 🙃</h1>
            
            <div class="intro-text">
                "Beleza é importante, mas o que me prende é a sua sabedoria. Eu quero <span class="highlight">ouvir sua história</span>."
            </div>

            <div class="generator-box">
                <p id="cantada-display">Toque no botão para uma palavra inspirada...</p>
                
                <button class="btn-generate" id="btnMain" onclick="novaCantada()">Revelar Palavra 📖</button>
                
                <a id="waLink" class="btn-whatsapp" target="_blank">
                    Enviar ao meu Jacó 🧔🏻‍♂️💬
                </a>
            </div>

            <div class="timer-box">
                <p style="font-size: 0.65rem; margin-bottom: 6px; text-transform: uppercase; opacity: 0.9; letter-spacing: 1px;">Contagem para a Tenda da Bênção:</p>
                <div id="timer">...</div>
                <p style="font-size: 0.8rem; margin-top: 10px; font-weight: 300;">Missão: Entrega do Gloss & Boa Conversa</p>
            </div>

            <p style="font-size: 0.8rem; color: #777; margin-top: 15px;">
                <em>"O melhor presente é o tempo que passamos juntos."</em>
            </p>
        </main>

        <footer class="footer-legacy">
            Desenvolvido por <strong>Divino José</strong><br>
            ADM & RH | Legado Pessoal 2026
        </footer>
    </div>

    <script>
        const cantadas = [
            "Você é como o lírio entre os espinhos; sua beleza se destaca em qualquer lugar.",
            "O inverno passou e as flores aparecem na terra, mas a flor mais linda eu encontrei em você.",
            "Muitas águas não poderiam apagar o meu carinho por você, nem os rios o afogariam.",
            "Põe-me como selo sobre o teu coração, pois minha admiração por você só cresce.",
            "Você é o meu jardim fechado, uma fonte de alegria constante na minha vida.",
            "Sua voz é doce e o seu semblante é gracioso.",
            "Você é toda bela, Raquel, e em você não há defeito que apague sua luz.",
            "Você é a prova de que Deus ainda faz milagres de sabedoria e beleza no século 21.",
            "Seu nome não é fé, mas você é a prova das coisas que eu esperava e não via.",
            "Você é o meu 'Ebenézer': até aqui me ajudou o Senhor a te encontrar.",
            "Nem as riquezas de Salomão se comparam ao valor de um sorriso seu.",
            "Você é a resposta de uma oração que eu fiz em silêncio.",
            "Deus caprichou na criação, mas quando te fez, Ele disse: 'Eis que é MUITO bom'.",
            "Não sou profeta, mas prevejo um futuro cheio de sorrisos para nós dois.",
            "Sua sabedoria me encanta mais do que qualquer palavra que eu possa dizer.",
            "Você é a pérola de grande valor que eu tive a honra de conhecer.",
            "Seu olhar brilha mais que as estrelas que Deus mostrou a Abraão.",
            "Você é a paz que excede todo o entendimento no fim de um dia cansativo.",
            "Eu não sou Adão, mas você é com certeza a parte que me faltava.",
            "Você não é a terra prometida, mas eu caminharia quilômetros só para te ouvir falar.",
            "Seu abraço é o meu lugar de descanso favorito no jardim do Senhor.",
            "Você é a luz que ilumina o meu caminho e traz clareza aos meus dias.",
            "Sabe o que eu pedi pra Deus? Alguém como você. Ele foi além e me trouxe exatamente você.",
            "Meu coração é como a arca: construído para proteger o que há de mais valioso.",
            "Você é o 'Sim' de todas as promessas que eu esperava encontrar em alguém."
        ];

        let fila = [...cantadas];
        let digitando = false;

        function novaCantada() {
            if (digitando) return;

            const display = document.getElementById('cantada-display');
            const waBtn = document.getElementById('waLink');

            if (fila.length === 0) fila = [...cantadas];

            const randomIndex = Math.floor(Math.random() * fila.length);
            const texto = fila.splice(randomIndex, 1)[0];

            digitando = true;
            waBtn.style.display = "none"; 

            typeWriter(`"${texto}"`, 'cantada-display', () => {
                digitando = false;
                prepararLinkWA(texto);
            });
        }

        function typeWriter(text, elementId, callback) {
            let i = 0;
            const element = document.getElementById(elementId);
            element.innerHTML = "";
            
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, 35);
                } else {
                    callback();
                }
            }
            type();
        }

        function prepararLinkWA(frase) {
            const waBtn = document.getElementById('waLink');
            const numero = "5561992006496";
            // Nova frase configurada conforme solicitado:
            const mensagem = encodeURIComponent(`Disseram que era uma revelação, e eu acabei lembrando de você. O que acha dessa? 🙃🌹\n\n"${frase}"`);
            
            waBtn.href = `https://api.whatsapp.com/send?phone=${numero}&text=${mensagem}`;
            waBtn.style.display = "inline-flex"; 
        }

        const targetDate = new Date('March 03, 2026 19:30:00').getTime();

        function updateTimer() {
            const now = new Date().getTime();
            const diff = targetDate - now;
            const timerEl = document.getElementById("timer");

            if (diff < 0) {
                timerEl.innerHTML = "É HOJE! 🙃🔥";
                return;
            }

            const d = Math.floor(diff / (1000 * 60 * 60 * 24));
            const h = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const m = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            const s = Math.floor((diff % (1000 * 60)) / 1000);
            
            timerEl.innerHTML = `${d}d ${h}h ${m}m ${s}s`;
        }

        setInterval(updateTimer, 1000);
        updateTimer();
    </script>
</body>
</html>

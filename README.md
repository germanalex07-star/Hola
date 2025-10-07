<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>❤️ ¿Me Perdonas? - Intento 1 ❤️</title>
    <style>
        :root {
            /* Variable CSS para el tamaño del botón SÍ. Inicial: 1.2em */
            --si-size: 1.2em;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            background-color: #ffe4e1; 
            font-family: 'Arial', sans-serif;
            text-align: center;
        }

        .container {
            background-color: #fff;
            padding: 40px 60px;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            position: relative; 
            max-width: 90%; 
            box-sizing: border-box; 
        }

        h1 {
            color: #ff69b4; 
            margin-bottom: 5px; 
            font-size: 2.5em;
            display: flex; 
            align-items: center;
            justify-content: center;
            gap: 10px; 
        }
        h1 img {
            height: 50px; 
            vertical-align: middle;
        }
        
        #sub-message {
            color: #777;
            font-size: 1.1em;
            margin-bottom: 30px;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 50px; 
            margin-top: 30px;
            position: relative; 
            z-index: 10; 
        }

        button {
            padding: 15px 30px;
            font-size: var(--si-size); 
            border: none;
            border-radius: 10px;
            cursor: pointer;
            /* Transición Lenta para los primeros 5 intentos */
            transition: all 0.8s ease-out; 
        }

        #si-btn {
            background-color: #5cb85c; 
            color: white;
        }

        #si-btn:hover {
            background-color: #4cae4c;
            transform: scale(1.05);
        }

        #no-btn {
            background-color: #d9534f; 
            color: white;
            position: absolute; 
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            white-space: nowrap; 
        }
        
        /* Clase para el movimiento ultra-rápido del Modo Imposible */
        .ultra-fast {
            /* ¡Velocidad del rayo! */
            transition: all 0.05s ease-out !important; 
        }

        .buttons button:nth-child(2) {
            position: relative;
        }

        #mensaje {
            margin-top: 30px;
            font-size: 1.5em;
            color: #ff69b4;
            display: none; 
            position: relative;
            padding: 20px 0;
            text-align: center;
        }
        
        #mensaje .message-text { 
            display: block;
            /* Permite saltos de línea en el mensaje final de éxito */
            white-space: pre-line; 
            margin-bottom: 10px;
        }

        #mensaje img { 
            position: absolute; 
            height: 100px; 
            animation: bounce 2s infinite ease-in-out; 
        }

        #mensaje img:first-of-type { 
            left: -120px; 
            bottom: 0px; 
            transform: scaleX(-1); 
            animation-delay: 0s;
        }

        #mensaje img:last-of-type { 
            right: -120px; 
            bottom: 0px; 
            animation-delay: 0.5s;
        }

        @keyframes bounce {
            0%, 100% {
                transform: translateY(0) scaleX(var(--flip-scale, 1));
            }
            50% {
                transform: translateY(-10px) scaleX(var(--flip-scale, 1));
            }
        }

        /* Media queries para pantallas más pequeñas (móviles) */
        @media (max-width: 600px) {
            .container {
                padding: 30px 20px;
            }
            h1 {
                font-size: 2em;
                flex-direction: column; 
            }
            #sub-message {
                margin-bottom: 20px;
            }
            h1 img {
                height: 40px;
            }
            .buttons {
                flex-direction: column; 
                gap: 20px;
            }
            #no-btn {
                position: relative; 
                top: auto;
                left: auto;
                transform: none; 
            }
            #mensaje {
                font-size: 1.2em;
            }
            #mensaje img:first-of-type {
                left: -60px; 
                bottom: -10px;
                height: 80px;
            }
            #mensaje img:last-of-type {
                right: -60px; 
                bottom: -10px;
                height: 80px;
            }
        }

    </style>
</head>
<body>

    <div class="container">
        <h1 id="question">¿Me perdonas? 🥺 <img id="question-kitty" src="https://media.tenor.com/KkLEtqtOSSUAAAAj/gato-llorar.gif" alt="gatito llorando"></h1>
        <p id="sub-message">Tienes un corazón hermoso. Por favor, dime que sí.</p>

        <div class="buttons">
            <button id="si-btn">¡Sí! ❤️</button>
            <button id="no-btn">No 💔</button>
        </div>

        <p id="mensaje">
            <span class="message-text">¡SABÍA QUE DIRÍAS QUE SÍ! 😊 Prometo ser mejor. Te amo. 
 Perdón, mi niña.

No quise lastimar tu corazón de pollito con mi forma fría de ser en los cumpleaños, en serio aprecio lo lindo que haces por mí tus cartas, tus detalles hechos a mano y desde el corazón.

Espero lograr demostrarte que en serio me gustan tus detalles y los aprecio con todo el corazón, Te amo desde lo más profundo del corazón, nunca cambies, por favor. 😘</span>
            <img src="https://media1.tenor.com/m/lZOUQuetSSQAAAAC/jibla-jumping-cat.gif" alt="gatito saltando">
            <img src="https://media1.tenor.com/m/lZOUQuetSSQAAAAC/jibla-jumping-cat.gif" alt="gatito saltando">
        </p>
    </div>

    <script>
        const noBtn = document.getElementById('no-btn');
        const siBtn = document.getElementById('si-btn');
        const mensaje = document.getElementById('mensaje');
        const question = document.getElementById('question');
        const subMessage = document.getElementById('sub-message');
        const container = document.querySelector('.container');
        const questionKitty = document.getElementById('question-kitty');

        let currentAttempt = 0; 

        // M A T R I Z   D E   M E N S A J E S
        const perdonMessages = [
            // Intento 1 (currentAttempt 0)
            { h1: "¿Segura? Piensa en este gatito...", sub: "Por favor, no te quise romper el corazón. 😔", kitty: "https://media.tenor.com/KkLEtqtOSSUAAAAj/gato-llorar.gif" }, 
            // Intento 2 (currentAttempt 1)
            { h1: "¿Estás jugando? 😥", sub: "Sabes que mi vida es menos brillante sin tus detalles. Vuelve a intentarlo. 🥺", kitty: "https://media.tenor.com/KkLEtqtOSSUAAAAj/gato-llorar.gif" },
            // Intento 3 (currentAttempt 2)
            { h1: "¡Por qué! 🥹", sub: "Si no me perdonas, ¿quién me va a regañar con tanto amor? Dame otra oportunidad. 🙏", kitty: "https://media.tenor.com/KkLEtqtOSSUAAAAj/gato-llorar.gif" },
            // Intento 4 (currentAttempt 3) - CAMBIO DE GIF
            { h1: "Mira el gatito... ¡Está sufriendo! 💔", sub: "No puedo con tanto rechazo. ¿No le vas a sonreír a este gatito? 🐈", kitty: "https://media1.tenor.com/m/UhKFknWkEsgAAAAC/dont-you.gif" }, 
            // Intento 5 (currentAttempt 4) - ÚLTIMA OPORTUNIDAD ANTES DEL MODO IMPOSIBLE
            { h1: "¡ÚLTIMO AVISO! 🚨", sub: "Te prometo que, si me perdonas, te haré la persona más feliz. ¿Aceptas mi tregua? ✨", kitty: "https://media.tenor.com/KkLEtqtOSSUAAAAj/gato-llorar.gif" }
        ];
        
        // F U N C I O N E S   G E N E R A L E S
        
        function checkMobileLayout() {
            if (window.matchMedia("(max-width: 600px)").matches) { 
                noBtn.style.position = 'relative';
                noBtn.style.top = 'auto';
                noBtn.style.left = 'auto';
                noBtn.style.transform = 'none';
                noBtn.style.margin = '0 auto';
            } else {
                noBtn.style.position = 'absolute';
                noBtn.style.transform = 'translateX(-50%)'; 
            }
        }
        window.addEventListener('load', checkMobileLayout);
        window.addEventListener('resize', checkMobileLayout);
        
        // Movimiento del botón 'No'
        noBtn.addEventListener('mouseover', moveNoButton);
        noBtn.addEventListener('click', moveNoButton); 

        function moveNoButton() {
            if (window.getComputedStyle(noBtn).position === 'absolute') {
                const containerRect = container.getBoundingClientRect();
                const noBtnRect = noBtn.getBoundingClientRect();

                const minX = -containerRect.width / 2 + noBtnRect.width / 2 + 20; 
                const maxX = containerRect.width / 2 - noBtnRect.width / 2 - 20;
                const minY = -containerRect.height / 2 + noBtnRect.height / 2 + 20;
                const maxY = containerRect.height / 2 - noBtnRect.height / 2 - 20;

                const randomX = Math.floor(Math.random() * (maxX - minX + 1)) + minX;
                const randomY = Math.floor(Math.random() * (maxY - minY + 1)) + minY;

                noBtn.style.transform = `translate(${randomX}px, ${randomY}px)`;
                
                // Si está en el modo imposible, la transición es muy rápida (0.05s, de la clase CSS)
                // Si no, la transición es lenta (0.7s)
                noBtn.style.transition = noBtn.classList.contains('ultra-fast') ? 'all 0.05s ease-out' : 'all 0.7s ease-out';
            }
        }


        // L Ó G I C A   D E L   B O T Ó N   N O 
        // -------------------------------------------------------------
        noBtn.addEventListener('click', (event) => {
            event.preventDefault(); 

            // Si es un intento normal (1 al 5)
            if (currentAttempt < perdonMessages.length) {
                // 1. Aumenta el tamaño del botón 'Sí' 
                const newSize = 1.2 + (currentAttempt + 1) * 0.3;
                document.documentElement.style.setProperty('--si-size', `${newSize}em`);
                
                // 2. Actualiza los mensajes y el GIF
                const messageData = perdonMessages[currentAttempt];
                
                question.innerHTML = messageData.h1 + `<img id="question-kitty" src="${messageData.kitty}" alt="gatito llorando">`;
                subMessage.textContent = messageData.sub;

                // 3. Incrementa el contador
                currentAttempt++;
            } 
            
            // Si supera los 5 intentos: Modo Imposible
            if (currentAttempt >= perdonMessages.length) {
                
                // 1. Restaura el botón a su posición inicial, le quita el color gris si lo tuviera.
                noBtn.style.backgroundColor = '#d9534f'; 
                noBtn.textContent = '¡DIJE NO! 😠'; 
                noBtn.style.transform = 'translateX(-50%)'; 
                
                // 2. Añade la clase para el movimiento ultra-rápido y asegura que los eventos estén activos.
                noBtn.classList.add('ultra-fast');
                
                // 3. Ajustamos el H1 y el Submensaje para el desafío final
                question.innerHTML = `¡NO TE DEJARÉ NUNCA! 😡 TE AMO <img id="question-kitty" src="https://media1.tenor.com/m/fW6KOfqgqSQAAAAd/amma-cat-ts-js-pmo-icl.gif">`;
                subMessage.textContent = "Te reto a que pulses 'No' ahora, si puedes... 😉";
            }
        });


        // B O T Ó N   ' S Í '   (Finaliza la dinámica)
        // -------------------------------------------
        siBtn.addEventListener('click', () => {
            // Oculta la pregunta y el botón
            question.style.display = 'none';
            subMessage.style.display = 'none'; 
            document.querySelector('.buttons').style.display = 'none';
            
            // Muestra el mensaje de éxito
            mensaje.style.display = 'flex'; 
            mensaje.style.flexDirection = 'column'; 
            mensaje.style.alignItems = 'center';

            container.style.padding = '80px 60px'; 

            // Reinicia las animaciones de los gatitos de éxito
            const kitties = document.querySelectorAll('#mensaje img');
            kitties.forEach((kitty, index) => {
                kitty.style.animation = 'none'; 
                kitty.offsetHeight; 
                kitty.style.animation = `bounce 2s infinite ease-in-out ${index * 0.5}s`;
                kitty.style.setProperty('--flip-scale', (index === 0 ? '-1' : '1'));
            });
        });
        
    </script>
</body>
</html>

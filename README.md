<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blog de José - ¡Bienvenidos!</title>
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=VT323&display=swap" rel="stylesheet">
    <style>
        /* Estilos generales */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background-color: #000;
            background-image: 
                linear-gradient(rgba(0, 30, 0, 0.8), rgba(0, 0, 0, 0.8)),
                url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%23002200"/><path d="M0 0L100 100M100 0L0 100" stroke="%23006633" stroke-width="1"/></svg>');
            color: #0f0;
            font-family: 'VT323', monospace;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 900px;
            margin: 20px auto;
            padding: 20px;
            position: relative;
            border: 4px double #0f0;
            background-color: rgba(0, 20, 0, 0.9);
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.5);
        }

        /* Animación de borde */
        @keyframes border-pulse {
            0% { box-shadow: 0 0 10px rgba(0, 255, 0, 0.5); }
            50% { box-shadow: 0 0 20px rgba(0, 255, 0, 0.8), 0 0 30px rgba(0, 255, 0, 0.6); }
            100% { box-shadow: 0 0 10px rgba(0, 255, 0, 0.5); }
        }

        .container {
            animation: border-pulse 3s infinite;
        }

        /* Cabecera */
        header {
            text-align: center;
            margin-bottom: 20px;
            position: relative;
            overflow: hidden;
            padding: 20px;
            border-bottom: 3px dashed #0f0;
        }

        .sonic-banner {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .sonic-gif {
            width: 100px;
            height: auto;
            image-rendering: pixelated;
            border: 2px solid #0f0;
            box-shadow: 0 0 10px #0f0;
        }

        h1 {
            font-family: 'Press Start 2P', cursive;
            font-size: 2.5em;
            color: #0f0;
            text-shadow: 0 0 10px #0f0, 0 0 20px #0f0;
            margin: 0;
            animation: text-flicker 1.5s infinite alternate;
        }

        @keyframes text-flicker {
            0% { opacity: 0.8; text-shadow: 0 0 10px #0f0; }
            100% { opacity: 1; text-shadow: 0 0 20px #0f0, 0 0 30px #0f0; }
        }

        /* Menús desplegables */
        .menu-container {
            margin-bottom: 20px;
        }

        .menu-item {
            margin-bottom: 10px;
        }

        .menu-title {
            font-family: 'Press Start 2P', cursive;
            font-size: 1.2em;
            color: #0f0;
            background-color: rgba(0, 30, 0, 0.9);
            padding: 15px;
            border: 2px solid #0f0;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s;
        }

        .menu-title:hover {
            background-color: rgba(0, 50, 0, 0.9);
            box-shadow: 0 0 15px #0f0;
        }

        .menu-title::after {
            content: "+";
            font-size: 1.5em;
        }

        .menu-title.active::after {
            content: "-";
        }

        .menu-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-out;
            background-color: rgba(0, 15, 0, 0.7);
            border-left: 2px solid #0f0;
            border-right: 2px solid #0f0;
            border-bottom: 2px solid #0f0;
        }

        .menu-content-inner {
            padding: 20px;
        }

        /* Contenido */
        .content-section {
            margin-bottom: 20px;
        }

        h2 {
            font-family: 'Press Start 2P', cursive;
            color: #0f0;
            border-bottom: 2px dashed #0f0;
            padding-bottom: 5px;
            margin-top: 0;
            font-size: 1.5em;
            margin-bottom: 15px;
        }

        .favorites-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
            gap: 15px;
            margin-top: 15px;
        }

        .favorite-item {
            background-color: rgba(0, 20, 0, 0.7);
            border: 1px solid #0f0;
            padding: 10px;
            text-align: center;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .favorite-item:hover {
            transform: scale(1.05);
            background-color: rgba(10, 40, 10, 0.8);
            box-shadow: 0 0 15px #0f0;
        }

        .favorite-item::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(
                transparent,
                rgba(0, 255, 0, 0.2),
                transparent
            );
            transform: rotate(45deg);
            z-index: 1;
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: rotate(45deg) translateX(-100%); }
            100% { transform: rotate(45deg) translateX(100%); }
        }

        .gif-container {
            text-align: center;
            margin: 15px 0;
        }

        .character-gif {
            max-width: 100%;
            height: auto;
            border: 2px solid #0f0;
            box-shadow: 0 0 10px #0f0;
            image-rendering: pixelated;
        }

        .emulator-container {
            background-color: #000;
            padding: 15px;
            border: 2px solid #0f0;
            margin-top: 15px;
            text-align: center;
        }

        .game-title {
            font-family: 'Press Start 2P', cursive;
            margin: 10px 0;
            color: #0f0;
            font-size: 1.2em;
        }

        .emulator-wrapper {
            width: 100%;
            height: 400px;
            position: relative;
            overflow: hidden;
            border: 2px solid #0a0;
        }

        .emulator-instructions {
            font-size: 0.9em;
            color: #8f8;
            margin-top: 5px;
            padding: 5px;
            background: rgba(0, 20, 0, 0.5);
            border: 1px solid #0a0;
        }

        /* Pie de página */
        footer {
            text-align: center;
            margin-top: 30px;
            padding: 15px;
            border-top: 3px dashed #0f0;
            font-size: 0.9em;
            color: #8f8;
        }

        .counter {
            font-family: 'Press Start 2P', cursive;
            font-size: 1.2em;
            color: #0f0;
            margin: 10px 0;
            animation: counter-pulse 2s infinite;
        }

        @keyframes counter-pulse {
            0% { text-shadow: 0 0 5px #0f0; }
            50% { text-shadow: 0 0 15px #0f0, 0 0 20px #0f0; }
            100% { text-shadow: 0 0 5px #0f0; }
        }

        /* Efectos especiales */
        .pixel-cursor {
            cursor: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='16' height='16'><rect width='16' height='16' fill='%2300FF00' opacity='0.7'/></svg>") 8 8, auto;
        }

        .scanline {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(
                to bottom,
                rgba(0, 0, 0, 0) 0%,
                rgba(0, 0, 0, 0.2) 50%,
                rgba(0, 0, 0, 0) 100%
            );
            background-size: 100% 4px;
            z-index: 1000;
            pointer-events: none;
            animation: scanline 8s linear infinite;
        }

        @keyframes scanline {
            0% { background-position: 0 0; }
            100% { background-position: 0 100%; }
        }

        .glitch {
            position: relative;
        }

        .glitch::before, .glitch::after {
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        .glitch::before {
            left: 2px;
            text-shadow: -1px 0 #f00;
            clip: rect(44px, 450px, 56px, 0);
            animation: glitch-anim 5s infinite linear alternate-reverse;
        }

        .glitch::after {
            left: -2px;
            text-shadow: -1px 0 #00f;
            clip: rect(44px, 450px, 56px, 0);
            animation: glitch-anim2 5s infinite linear alternate-reverse;
        }

        @keyframes glitch-anim {
            0% { clip: rect(42px, 9999px, 44px, 0); }
            20% { clip: rect(12px, 9999px, 59px, 0); }
            40% { clip: rect(48px, 9999px, 29px, 0); }
            60% { clip: rect(42px, 9999px, 73px, 0); }
            80% { clip: rect(63px, 9999px, 27px, 0); }
            100% { clip: rect(34px, 9999px, 55px, 0); }
        }

        @keyframes glitch-anim2 {
            0% { clip: rect(65px, 9999px, 99px, 0); }
            20% { clip: rect(79px, 9999px, 19px, 0); }
            40% { clip: rect(66px, 9999px, 36px, 0); }
            60% { clip: rect(25px, 9999px, 49px, 0); }
            80% { clip: rect(89px, 9999px, 98px, 0); }
            100% { clip: rect(95px, 9999px, 58px, 0); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 10px;
                width: 95%;
                margin: 10px auto;
            }
            
            h1 {
                font-size: 1.8em;
            }
            
            .sonic-gif {
                width: 70px;
            }
            
            .emulator-wrapper {
                height: 300px;
            }
            
            .favorites-grid {
                grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            }
            
            .menu-title {
                font-size: 1em;
                padding: 10px;
            }
        }
    </style>
</head>
<body class="pixel-cursor">
    <!-- Efecto de scanlines -->
    <div class="scanline"></div>
    
    <div class="container">
        <header>
            <div class="sonic-banner">
                <img src="https://media.tenor.com/8jUlCiKI8RMAAAAi/sonic-personaggio-per-il-videogame.gif" alt="Sonic running" class="sonic-gif">
                <h1 class="glitch" data-text="¡Hola, soy José!">¡Hola, soy José!</h1>
                <img src="https://media1.tenor.com/m/yyofCYnEXksAAAAC/sonic-the-hedgehog-classic-sonic.gif" alt="Sonic spinning" class="sonic-gif">
            </div>
            <p>¡Bienvenidos a mi página personal! Haz clic en los menús para explorar.</p>
        </header>
        
        <div class="menu-container">
            <div class="menu-item">
                <div class="menu-title">Sobre Mí</div>
                <div class="menu-content">
                    <div class="menu-content-inner">
                        <h2>Sobre Mí</h2>
                        <p>¡Hola! Soy José, un apasionado de los videojuegos y las series animadas. Mi color favorito es el <span style="color: #0f0; text-shadow: 0 0 5px #0f0;">verde</span>, como habrás notado en el diseño de mi página.</p>
                        <p>En este blog compartiré mis experiencias, reseñas y todo lo relacionado con mis sagas favoritas. Espero que disfrutes explorando mi sitio tanto como yo disfruté creándolo.</p>
                        <div class="gif-container">
                            <img src="https://media1.tenor.com/m/DP615vqUzeAAAAAC/ace-attorney-phoenix-wright.gif" alt="Phoenix Wright" class="character-gif">
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="menu-item">
                <div class="menu-title">Videojuegos Favoritos</div>
                <div class="menu-content">
                    <div class="menu-content-inner">
                        <h2>Sagas de Videojuegos Favoritas</h2>
                        <div class="favorites-grid">
                            <div class="favorite-item">Sonic The Hedgehog</div>
                            <div class="favorite-item">Resident Evil</div>
                            <div class="favorite-item">Ace Attorney</div>
                            <div class="favorite-item">Kingdom Hearts</div>
                            <div class="favorite-item">The Legend of Zelda</div>
                            <div class="favorite-item">Mario Bros</div>
                            <div class="favorite-item">Friday Night Funkin</div>
                        </div>
                        <div class="gif-container">
                            <img src="https://media1.tenor.com/m/DzUvWHlds04AAAAC/sora-donald-and-goofy-go-into-battle-kingdom-hearts.gif" alt="Kingdom Hearts" class="character-gif">
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="menu-item">
                <div class="menu-title">Series Favoritas</div>
                <div class="menu-content">
                    <div class="menu-content-inner">
                        <h2>Series Favoritas</h2>
                        <div class="favorites-grid">
                            <div class="favorite-item">El Increíble Mundo de Gumball</div>
                            <div class="favorite-item">Hora de Aventura</div>
                            <div class="favorite-item">Un Show Más</div>
                            <div class="favorite-item">Ben 10</div>
                            <div class="favorite-item">Sonic Boom</div>
                            <div class="favorite-item">Los Jóvenes Titanes (2003)</div>
                            <div class="favorite-item">Doctor House</div>
                            <div class="favorite-item">Avatar: La Leyenda de Aang</div>
                        </div>
                        <div class="gif-container">
                            <img src="https://media1.tenor.com/m/Ukb08ronEecAAAAd/leon-kennedy-resident-evil-4.gif" alt="Resident Evil" class="character-gif">
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="menu-item">
                <div class="menu-title">¡Juega Aquí!</div>
                <div class="menu-content">
                    <div class="menu-content-inner">
                        <h2>¡Juega Aquí!</h2>
                        <p>Disfruta de mis juegos favoritos directamente en el navegador. ¡Usa el teclado para jugar!</p>
                        
                        <div class="emulator-container">
                            <div class="game-title">Sonic The Hedgehog 2 (Sega Genesis)</div>
                            <div class="emulator-instructions">Controles: Flechas para mover, Z para saltar | Si no carga, recarga la página</div>
                            <div style="width:100%;height:400px;max-width:100%">
                                <div id="sonic-game"></div>
                            </div>
                        </div>
                        
                        <div class="emulator-container" style="margin-top: 30px;">
                            <div class="game-title">Super Metroid (Super Nintendo)</div>
                            <div class="emulator-instructions">Controles: Flechas para mover, Z para disparar, X para saltar | Si no carga, recarga la página</div>
                            <div style="width:100%;height:400px;max-width:100%">
                                <div id="metroid-game"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="menu-item">
                <div class="menu-title">Contacto</div>
                <div class="menu-content">
                    <div class="menu-content-inner">
                        <h2>Contacto</h2>
                        <p>¿Quieres ponerte en contacto conmigo? ¡Escríbeme!</p>
                        <form style="margin-top: 20px;">
                            <div style="margin-bottom: 15px;">
                                <label for="name" style="display: block; margin-bottom: 5px;">Nombre:</label>
                                <input type="text" id="name" style="width: 100%; padding: 8px; background: #001100; border: 1px solid #0f0; color: #0f0; font-family: 'VT323', monospace; font-size: 1.1em;">
                            </div>
                            <div style="margin-bottom: 15px;">
                                <label for="email" style="display: block; margin-bottom: 5px;">Email:</label>
                                <input type="email" id="email" style="width: 100%; padding: 8px; background: #001100; border: 1px solid #0f0; color: #0f0; font-family: 'VT323', monospace; font-size: 1.1em;">
                            </div>
                            <div style="margin-bottom: 15px;">
                                <label for="message" style="display: block; margin-bottom: 5px;">Mensaje:</label>
                                <textarea id="message" rows="5" style="width: 100%; padding: 8px; background: #001100; border: 1px solid #0f0; color: #0f0; font-family: 'VT323', monospace; font-size: 1.1em;"></textarea>
                            </div>
                            <button type="submit" style="background: #002200; color: #0f0; border: 2px solid #0f0; padding: 10px 20px; font-family: 'Press Start 2P', cursive; font-size: 0.9em; cursor: pointer; transition: all 0.3s;">Enviar Mensaje</button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
        
        <footer>
            <div class="counter">Visitantes: 8842</div>
            <p>© 2023 Blog Personal de José. Todos los derechos reservados.</p>
            <p style="font-size: 0.8em; margin-top: 10px;">¡Gracias por visitar mi página retro!</p>
        </footer>
    </div>
    
    <script>
        // Funcionalidad de los menús desplegables
        document.querySelectorAll('.menu-title').forEach(title => {
            title.addEventListener('click', () => {
                // Cerrar todos los menús excepto el que se hizo clic
                document.querySelectorAll('.menu-content').forEach(content => {
                    if (content !== title.nextElementSibling) {
                        content.style.maxHeight = null;
                        content.previousElementSibling.classList.remove('active');
                    }
                });
                
                // Alternar el menú actual
                const content = title.nextElementSibling;
                if (content.style.maxHeight) {
                    content.style.maxHeight = null;
                    title.classList.remove('active');
                } else {
                    content.style.maxHeight = content.scrollHeight + "px";
                    title.classList.add('active');
                }
            });
        });

        // Contador de visitas (simulado)
        let counter = document.querySelector('.counter');
        let count = 8842;
        setInterval(() => {
            count++;
            counter.textContent = `Visitantes: ${count}`;
        }, 30000);
        
        // Efecto de teclas al presionar
        document.querySelectorAll('.menu-t

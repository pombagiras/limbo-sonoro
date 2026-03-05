<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Portfólio de Alexia Melusine - Desenvolvedora e Narradora do Abismo.">
    <title>Alexia Melusine | Limbo Sonoro</title>
    
    <!-- Fontes -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,500;0,700;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">

    <style>
        /* --- Configurações Globais --- */
        :root {
            --bg-color: #030303;
            --card-bg: #0a0a0a;
            --text-main: #e0e0e0;
            --text-muted: #888888;
            --accent-purple: #8a2be2;
            --accent-pink: #ff69b4;
            --accent-iron: #7a7a7a;
            --font-serif: 'Cormorant Garamond', serif;
            --font-sans: 'Lato', sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            font-family: var(--font-sans);
            line-height: 1.7;
            overflow-x: hidden;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* Efeito de Ruído (Grain) */
        body::after {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)' opacity='0.04'/%3E%3C/svg%3E");
            pointer-events: none;
            z-index: 999;
        }

        /* --- Layout Principal --- */
        main {
            width: 100%;
            max-width: 900px;
            padding: 4rem 1.5rem;
            text-align: center;
            position: relative;
            z-index: 1;
        }

        /* --- Header / Perfil --- */
        header {
            margin-bottom: 4rem;
            animation: fadeIn 1.5s ease-out;
        }

        .profile-container {
            position: relative;
            display: inline-block;
            margin-bottom: 1.5rem;
        }

        .profile-img {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid var(--accent-purple);
            box-shadow: 0 0 30px rgba(138, 43, 226, 0.3);
            transition: transform 0.5s ease, box-shadow 0.5s ease;
        }

        .profile-img:hover {
            transform: scale(1.02);
            box-shadow: 0 0 50px rgba(138, 43, 226, 0.5);
        }

        h1 {
            font-family: var(--font-serif);
            font-size: 3rem;
            font-weight: 700;
            letter-spacing: 0.05em;
            margin-bottom: 0.5rem;
            background: linear-gradient(to right, #fff, #aaa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .tagline {
            font-family: var(--font-serif);
            font-style: italic;
            font-size: 1.3rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
        }

        .bio {
            max-width: 600px;
            margin: 0 auto 3rem auto;
            color: #ccc;
            font-size: 1rem;
        }

        .highlight {
            color: var(--text-main);
            font-weight: bold;
        }

        /* --- Grid de Projetos --- */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 2rem;
            width: 100%;
            margin-top: 2rem;
        }

        .card {
            background: var(--card-bg);
            border: 1px solid #222;
            padding: 2.5rem 1.5rem;
            border-radius: 4px;
            text-decoration: none;
            color: inherit;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100%;
        }

        /* Efeitos Hover Específicos por Card */
        .card:hover {
            transform: translateY(-8px);
            background: #0f0f0f;
        }

        /* Pombagiras - Roxo */
        .card.pombagiras:hover {
            border-color: var(--accent-purple);
            box-shadow: 0 10px 30px -10px rgba(138, 43, 226, 0.2);
        }
        .card.pombagiras h3 { color: var(--accent-purple); }

        /* Orgulho Trans - Rosa */
        .card.trans:hover {
            border-color: var(--accent-pink);
            box-shadow: 0 10px 30px -10px rgba(255, 105, 180, 0.2);
        }
        .card.trans h3 { color: var(--accent-pink); }

        /* Alexia Ferro - Cinza */
        .card.ferro:hover {
            border-color: var(--accent-iron);
            box-shadow: 0 10px 30px -10px rgba(122, 122, 122, 0.2);
        }
        .card.ferro h3 { color: var(--accent-iron); }

        .card h3 {
            font-family: var(--font-serif);
            font-size: 1.5rem;
            margin-bottom: 1rem;
            font-weight: 600;
        }

        .card p {
            font-size: 0.9rem;
            color: var(--text-muted);
            margin-bottom: 1.5rem;
        }

        .github-icon {
            width: 24px;
            height: 24px;
            fill: currentColor;
            opacity: 0.7;
            transition: opacity 0.3s;
        }

        .card:hover .github-icon {
            opacity: 1;
        }

        /* --- Footer --- */
        footer {
            margin-top: auto;
            padding: 3rem 1.5rem;
            border-top: 1px solid #111;
            font-family: var(--font-serif);
            font-size: 1.1rem;
            color: #555;
            text-align: center;
            width: 100%;
        }

        footer span {
            display: block;
            margin-top: 10px;
            font-size: 0.8rem;
            font-family: var(--font-sans);
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        /* --- Animações --- */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Responsividade */
        @media (max-width: 600px) {
            h1 { font-size: 2.2rem; }
            .profile-img { width: 140px; height: 140px; }
            .projects-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>

    <main>
        <header>
            <div class="profile-container">
                <!-- Sua Foto -->
                <img src="https://raw.githubusercontent.com/pombagiras/melusine/refs/heads/main/Al%C3%AA%20(3)%20(3)%20(1).png" alt="Alexia Melusine" class="profile-img">
            </div>
            
            <h1>Alexia Melusine</h1>
            <p class="tagline">Desenvolvedora | Narradora do Abismo</p>

            <div class="bio">
                <p>Mergulhando no código assim como mergulha nas memórias. Meu trabalho conecta a técnica do desenvolvimento à visceralidade da arte autobiográfica.</p>
            </div>
            
            <blockquote style="font-family: var(--font-serif); color: #666; border-left: 1px solid #333; padding-left: 1rem; display: inline-block; font-style: italic;">
                "Porque alguns abismos não se superam — apenas se narram."
            </blockquote>
        </header>

        <section class="projects-grid">
            
            <!-- Repositório 1: Pombagiras -->
            <a href="https://github.com/pombagiras" target="_blank" class="card pombagiras">
                <!-- Ícone Github SVG -->
                <svg class="github-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                
                <h3>Pombagiras</h3>
                <p>O núcleo da minha atividade técnica. Desenvolvimento, experimentação e arquivamento de projetos pessoais.</p>
            </a>

            <!-- Repositório 2: Orgulho Trans -->
            <a href="https://github.com/Orgulho-Trans" target="_blank" class="card trans">
                <svg class="github-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                
                <h3>Orgulho Trans</h3>
                <p>Memória e resistência. Um espaço dedicado à preservação de histórias, lutas e celebrações da comunidade.</p>
            </a>

            <!-- Repositório 3: Alexia Luz de Ferro -->
            <a href="https://github.com/alexialuzdeferro" target="_blank" class="card ferro">
                <svg class="github-icon" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                
                <h3>Alexia Luz de Ferro</h3>
                <p>A identidade que forja o código. Explorações sobre identidade, ferro e fogo na composição digital.</p>
            </a>

        </section>
    </main>

    <footer>
        <p>“Onde o som é ponte para lugares onde nunca voltamos.”</p>
        <span>&copy; Limbo Sonoro</span>
    </footer>

</body>
</html>

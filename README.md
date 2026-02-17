<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DilleswaraRao Nakkina · full‑stack profile</title>
    <!-- Fonts & icons (devicon, simple icons for social) -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/devicon@2.15.1/devicon.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Fira Code for typing SVG consistency -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0d1117;   /* dark base like GitHub dark */
            font-family: 'Fira Code', 'Segoe UI', monospace;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            padding: 2rem 1rem;
            color: #e6edf3;
        }

        /* main card – subtle glass effect */
        .profile-card {
            max-width: 1100px;
            width: 100%;
            background: #161b22;
            border: 1px solid #30363d;
            border-radius: 2rem;
            padding: 2.5rem 2rem;
            box-shadow: 0 15px 30px -10px rgba(0,0,0,0.6);
            transition: all 0.2s ease;
        }

        /* header with typing animation */
        .typing-header {
            display: flex;
            justify-content: center;
            margin-bottom: 2rem;
        }

        .typing-svg-container {
            background: #0d1117;
            border-radius: 100px;
            padding: 0.6rem 1.8rem;
            border: 1px solid #3d444d;
            display: inline-flex;
            box-shadow: 0 4px 10px rgba(0,0,0,0.4);
        }

        .typing-svg-container img {
            display: block;
            height: auto;
            max-width: 100%;
        }

        /* streak & stats row – responsive */
        .streak-section {
            display: flex;
            justify-content: center;
            margin: 2.5rem 0 1.5rem;
        }

        .streak-card {
            background: #0d1117;
            border-radius: 1.8rem;
            border: 1px solid #30363d;
            padding: 1rem 1.8rem;
            transition: transform 0.2s;
        }
        .streak-card:hover {
            border-color: #8957e5;
            transform: scale(1.01);
        }
        .streak-card img {
            max-width: 100%;
            height: auto;
            border-radius: 12px;
        }

        /* two column stats (github + top langs) */
        .stats-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 2rem;
            margin: 2.5rem 0 2rem;
        }

        .stat-item {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 1.8rem;
            padding: 1.2rem 1.5rem;
            transition: all 0.2s;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .stat-item:hover {
            border-color: #8957e5;
            box-shadow: 0 8px 16px -8px #000;
        }
        .stat-item img {
            max-width: 100%;
            height: auto;
            border-radius: 8px;
        }

        /* gif + tech icons row */
        .tech-row {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            background: #0d1117;
            border-radius: 2rem;
            border: 1px solid #30363d;
            padding: 1.5rem 2rem;
            margin: 2rem 0 1.8rem;
        }

        .gif-box {
            flex: 0 0 auto;
        }
        .gif-box img {
            height: 140px;
            width: auto;
            border-radius: 24px;
            box-shadow: 0 8px 18px rgba(0,0,0,0.5);
            border: 1px solid #3d444d;
        }

        .icons-wrapper {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem;
            align-items: center;
            justify-content: flex-end;
            flex: 2;
            padding-left: 1rem;
        }

        .icons-wrapper i, .icons-wrapper img {
            font-size: 2.4rem;
            color: #e6edf3;
            transition: color 0.2s, transform 0.2s;
        }
        .icons-wrapper i:hover, .icons-wrapper img:hover {
            color: #8957e5;
            transform: translateY(-3px);
        }
        /* devicon uses fonts, but also we keep standard devicon classes */
        .icons-wrapper .devicon {
            font-size: 2.4rem;
        }

        /* social badges – clean row */
        .social-links {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
            margin: 2rem 0 2.5rem;
        }

        .social-badge {
            display: inline-flex;
            align-items: center;
            background: #21262d;
            color: #f0f6fc;
            padding: 0.7rem 1.4rem;
            border-radius: 3rem;
            font-size: 1rem;
            font-weight: 500;
            border: 1px solid #3d444d;
            text-decoration: none;
            transition: background 0.2s, border-color 0.2s;
            gap: 0.6rem;
        }
        .social-badge i {
            font-size: 1.4rem;
        }
        .social-badge:hover {
            background: #2d3748;
            border-color: #8957e5;
            color: white;
        }

        /* snake animation */
        .snake-section {
            margin-top: 2rem;
            background: #0d1117;
            border-radius: 2rem;
            border: 1px solid #30363d;
            padding: 1.5rem 0.5rem;
            display: flex;
            justify-content: center;
        }
        .snake-section picture img {
            max-width: 100%;
            border-radius: 16px;
        }

        /* fine details */
        hr {
            border: 0.5px solid #30363d;
            margin: 1.5rem 0 0.5rem;
        }
        .official-tag {
            text-align: center;
            font-size: 0.9rem;
            opacity: 0.7;
            letter-spacing: 1px;
            margin-top: 1rem;
        }
        .official-tag i {
            color: #8957e5;
        }

        /* responsive touches */
        @media (max-width: 700px) {
            .profile-card { padding: 1.8rem 1.2rem; }
            .tech-row { flex-direction: column; gap: 2rem; }
            .icons-wrapper { justify-content: center; padding-left: 0; }
            .gif-box img { height: 120px; }
        }
    </style>
</head>
<body>
    <div class="profile-card">
        <!-- TYPING SVG HEADER (official, exactly as given but embedded safely) -->
        <div class="typing-header">
            <div class="typing-svg-container">
                <!-- using img src for the typing svg – direct from demolab, shows full name & role -->
                <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&pause=1000&color=58A6FF&center=true&vCenter=true&width=500&lines=DilleswaraRao+Nakkina%2C+Full+stack+Developer;6%2B+years+of+crafting+web+solutions;React+%7C+Node+%7C+TypeScript+%7C+Python" 
                     alt="DilleswaraRao Nakkina, Full stack Developer" />
            </div>
        </div>

        <!-- STREAK STATS (git.io/streak-stats) with dark mode preference -->
        <div class="streak-section">
            <div class="streak-card">
                <a href="https://git.io/streak-stats" target="_blank" rel="noopener">
                    <picture>
                        <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=dilleshdill&theme=dark&hide_border=true&border_radius=12&date_format=j%20M%5B%20Y%5D" />
                        <img src="https://streak-stats.demolab.com?user=dilleshdill&theme=default&hide_border=true&border_radius=12" alt="GitHub Streak" width="480" />
                    </picture>
                </a>
            </div>
        </div>

        <!-- TWO STAT CARDS: github stats + top languages (dracula theme) -->
        <div class="stats-grid">
            <div class="stat-item">
                <img src="https://github-readme-stats.vercel.app/api?username=dilleshdill&hide_title=true&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=dracula&locale=en&hide_border=true&border_radius=14" 
                     alt="github stats" height="180" />
            </div>
            <div class="stat-item">
                <img src="https://github-readme-stats.vercel.app/api/top-langs?username=dilleshdill&locale=en&hide_title=true&layout=compact&card_width=320&langs_count=6&theme=dracula&hide_border=true&border_radius=14" 
                     alt="top languages" height="180" />
            </div>
        </div>

        <!-- GIF + TECH ICONS (right aligned) -->
        <div class="tech-row">
            <div class="gif-box">
                <!-- original gif from imgflip "65efzo" - coding幽默 -->
                <img src="https://i.imgflip.com/65efzo.gif" alt="coding fun gif" />
            </div>
            <div class="icons-wrapper">
                <i class="devicon-javascript-original"></i>
                <i class="devicon-typescript-original"></i>
                <i class="devicon-react-original"></i>
                <i class="devicon-html5-original"></i>
                <i class="devicon-css3-original"></i>
                <i class="devicon-python-original"></i>
                <i class="devicon-csharp-original"></i>
                <!-- extra officiality: node, docker etc optional but keep minimal -->
                <i class="devicon-nodejs-plain"></i>
                <i class="devicon-git-plain"></i>
            </div>
        </div>

        <!-- SOCIAL LINKS (badges with official channels, kept as placeholders) -->
        <div class="social-links">
            <a href="#" class="social-badge" aria-label="YouTube"><i class="fab fa-youtube"></i> YouTube</a>
            <a href="#" class="social-badge" aria-label="Instagram"><i class="fab fa-instagram"></i> Instagram</a>
            <a href="#" class="social-badge" aria-label="Twitch"><i class="fab fa-twitch"></i> Twitch</a>
            <a href="#" class="social-badge" aria-label="Discord"><i class="fab fa-discord"></i> Discord</a>
            <a href="#" class="social-badge" aria-label="Gmail"><i class="fas fa-envelope"></i> Gmail</a>
            <a href="#" class="social-badge" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
        </div>

        <!-- SNAKE CONTRIBUTION GRAPH (from nanipinninti repo, official svg) -->
        <div class="snake-section">
            <picture>
                <!-- Use the exact raw.githubusercontent links (as provided) -->
                <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/nanipinninti/nanipinninti/output/github-snake-dark.svg" />
                <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/nanipinninti/nanipinninti/output/github-snake.svg" />
                <img alt="github contribution snake" src="https://raw.githubusercontent.com/nanipinninti/nanipinninti/output/github-snake.svg" style="max-width: 100%;" />
            </picture>
        </div>

        <!-- subtle separator + official footer watermark -->
        <hr />
        <div class="official-tag">
            <i class="fas fa-check-circle"></i> dilleshdill · official full‑stack profile · updated 2025
        </div>
    </div>

    <!-- small note: all links are functional except social ones (kept as # to preserve layout) 
         but feel free to replace with actual profiles. -->
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SoleminerCloud | Premium Cloud Gaming</title>
    <style>
        :root {
            --primary: #00ff88;
            --bg-dark: #0a0a0c;
            --card-bg: #16161a;
            --text-gray: #a0a0a8;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body, html {
            width: 100%;
            height: 100%;
            background-color: var(--bg-dark);
            color: white;
            font-family: 'Segoe UI', sans-serif;
            overflow: hidden;
        }

        .navbar {
            height: 50px;
            background: var(--card-bg);
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 20px;
            border-bottom: 2px solid #222;
            z-index: 10;
        }

        .logo-text {
            font-size: 18px;
            font-weight: 800;
            letter-spacing: 2px;
            color: var(--primary);
            text-transform: uppercase;
        }

        .main-viewport {
            position: relative;
            height: calc(100vh - 50px);
            width: 100%;
            background: #000;
        }

        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        #loader {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: var(--bg-dark);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 5;
            transition: opacity 0.8s ease;
        }

        .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid #222;
            border-top: 4px solid var(--primary);
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin-bottom: 15px;
        }

        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }

        .panic-hint {
            position: fixed;
            bottom: 10px;
            right: 15px;
            color: var(--text-gray);
            font-size: 10px;
            background: rgba(0,0,0,0.6);
            padding: 4px 8px;
            border-radius: 4px;
            z-index: 20;
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <div class="logo-text">SoleminerCloud</div>
        <div style="font-size: 10px; color: var(--text-gray);">SECURE CONNECTION ESTABLISHED</div>
    </nav>

    <div id="loader">
        <div class="spinner"></div>
        <p style="letter-spacing: 1px; font-size: 13px;">INITIALIZING CLOUD...</p>
    </div>

    <main class="main-viewport">
        <iframe 
            id="cloud-frame"
            src="https://web.cloudmoonapp.com/" 
            allow="autoplay; fullscreen; keyboard"
            sandbox="allow-forms allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox">
        </iframe>
    </main>

    <div class="panic-hint">Emergency: Press [7]</div>

    <script>
        // 1. PANIC REDIRECT (to Satchel One)
        function triggerPanic() {
            window.location.replace("https://www.satchelone.com/login");
        }

        // 2. LISTEN FOR KEYPRESS
        document.addEventListener('keydown', function(event) {
            if (event.key === "7") {
                triggerPanic();
            }
        });

        // 3. THE FIX: RE-FOCUS SCRIPT
        // This ensures the "7" key works even if you are clicking inside the game.
        setInterval(function() {
            if (document.activeElement.tagName === "IFRAME") {
                // We briefly take focus away from the game so the site can "hear" the 7 key
                window.focus();
            }
        }, 1000);

        // 4. LOADER TIMEOUT
        window.onload = function() {
            setTimeout(function() {
                const loader = document.getElementById('loader');
                loader.style.opacity = '0';
                setTimeout(() => { loader.style.display = 'none'; }, 800);
            }, 4000);
        };
    </script>
</body>
</html>

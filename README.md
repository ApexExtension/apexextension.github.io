<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>SoleminerCloud</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body, html {
            width: 100%;
            height: 100%;
            overflow: hidden;
            background-color: #000;
            font-family: 'Segoe UI', sans-serif;
        }

        /* Fullscreen Game Container */
        .game-wrapper {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 1;
        }

        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        /* Panic Button UI (Visible helper) */
        .panic-info {
            position: fixed;
            top: 10px;
            left: 10px;
            background: rgba(0, 0, 0, 0.6);
            color: rgba(255, 255, 255, 0.5);
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 10px;
            z-index: 100;
            pointer-events: none;
            transition: opacity 0.3s;
        }

        body:hover .panic-info {
            opacity: 1;
        }
    </style>
</head>
<body>

    <div class="panic-info">SoleminerCloud | Press "\" to Panic</div>

    <div class="game-wrapper">
        <iframe 
            id="game-frame"
            src="https://web.cloudmoonapp.com/" 
            allow="autoplay; fullscreen; keyboard"
            sandbox="allow-forms allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox">
        </iframe>
    </div>

    <script>
        // PANIC BUTTON LOGIC
        // Redirects to Google Classroom instantly when "\" is pressed
        document.addEventListener('keydown', function(e) {
            if (e.key === "\\") {
                window.location.href = "https://satchelone.com";
            }
        });

        // Error handling: if Moon Cloud link changes, try the mirror
        const frame = document.getElementById('game-frame');
        frame.onerror = function() {
            console.log("Primary link failed, trying mirror...");
            frame.src = "https://now.gg/apps/roblox-corporation/5349/roblox.html";
        };
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SoleminerCloud | Premium Cloud Gaming</title>
    <style>
        /* Modern Gaming Aesthetic */
        :root {
            --primary: #00ff88; /* Neon Green */
            --bg-dark: #0a0a0c;
            --card-bg: #16161a;
            --text-gray: #a0a0a8;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body, html {
            width: 100%;
            height: 100%;
            background-color: var(--bg-dark);
            color: white;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            overflow: hidden;
        }

        /* Top Navigation Bar */
        .navbar {
            height: 60px;
            background: var(--card-bg);
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 30px;
            border-bottom: 2px solid #222;
            z-index: 10;
        }

        .logo-text {
            font-size: 22px;
            font-weight: 800;
            letter-spacing: 2px;
            color: var(--primary);
            text-transform: uppercase;
        }

        .status-tag {
            background: rgba(0, 255, 136, 0.1);
            color: var(--primary);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
            border: 1px solid var(--primary);
        }

        /* The Game Area */
        .main-viewport {
            position: relative;
            height: calc(100vh - 60px); /* Fill space below navbar */
            width: 100%;
            background: #000;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        iframe {
            width: 100%;
            height: 100%;
            border: none;
            box-shadow: 0 0 50px rgba(0,0,0,0.5);
        }

        /* Glowing Loader Overlay */
        #loader {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--bg-dark);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 5;
            transition: opacity 1s ease;
        }

        .spinner {
            width: 50px;
            height: 50px;
            border: 5px solid #222;
            border-top: 5px solid var(--primary);
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin-bottom: 20px;
        }

        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }

        /* Panic Key Reminder */
        .panic-hint {
            position: fixed;
            bottom: 15px;
            right: 20px;
            color: var(--text-gray);
            font-size: 11px;
            background: rgba(0,0,0,0.5);
            padding: 5px 10px;
            border-radius: 4px;
            z-index: 20;
            pointer-events: none;
        }
    </style>
</head>
<body>

    <nav class="navbar">
        <div class="logo-text">SoleminerCloud</div>
        <div class="status-tag">SERVER: ONLINE</div>
    </nav>

    <div id="loader">
        <div class="spinner"></div>
        <p>Connecting to Cloud Instance...</p>
    </div>

    <main class="main-viewport">
        <iframe 
            id="cloud-frame"
            src="https://web.cloudmoonapp.com/" 
            allow="autoplay; fullscreen; keyboard"
            sandbox="allow-forms allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox">
        </iframe>
    </main>

    <div class="panic-hint">Panic Key: [7]</div>

    <script>
        // PANIC BUTTON
        document.addEventListener('keydown', function(event) {
            if (event.key === "7") {
                // Redirects to a safe school/work page
                window.location.replace("https://classroom.google.com");
            }
        });

        // HIDE LOADER
        // We hide the loading screen after 5 seconds to give the frame time to start
        window.onload = function() {
            setTimeout(function() {
                document.getElementById('loader').style.opacity = '0';
                setTimeout(() => { document.getElementById('loader').style.display = 'none'; }, 1000);
            }, 5000);
        };
    </script>
</body>
</html>
        

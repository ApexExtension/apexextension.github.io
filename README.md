<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roblox Online - No Download</title>
    <style>
        body {
            margin: 0;
            background-color: #111;
            color: white;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .header {
            padding: 20px;
            text-align: center;
        }
        .game-wrapper {
            position: relative;
            width: 90%;
            max-width: 1000px;
            aspect-ratio: 16 / 9;
            border: 5px solid #333;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 0 30px rgba(0,0,0,0.5);
        }
        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
        .footer {
            margin-top: 20px;
            font-size: 14px;
            color: #888;
        }
    </style>
</head>
<body>

    <div class="header">
        <h1>Roblox Cloud Player</h1>
        <p>Powered by Easyfun Technology</p>
    </div>

    <div class="game-wrapper">
        <iframe 
            src="https://www.easyfun.gg/games/roblox.html" 
            allow="autoplay; fullscreen; keyboard"
            scrolling="no">
        </iframe>
    </div>

    <div class="footer">
        Note: This uses cloud streaming. A fast internet connection is recommended.
    </div>

</body>
</html>

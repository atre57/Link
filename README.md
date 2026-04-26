<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Benim Bağlantılarım</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #121212;
            color: white;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 50px 20px;
            margin: 0;
        }
        .profile-img {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            border: 3px solid #00ff88;
            margin-bottom: 15px;
        }
        h1 { font-size: 1.5rem; margin-bottom: 5px; }
        p { color: #aaa; margin-bottom: 30px; }
        
        .links-container {
            width: 100%;
            max-width: 400px;
        }
        .link-card {
            background-color: #1e1e1e;
            border: 1px solid #333;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 15px;
            text-align: center;
            text-decoration: none;
            color: white;
            display: block;
            transition: transform 0.2s, background-color 0.2s;
        }
        .link-card:hover {
            transform: scale(1.03);
            background-color: #252525;
            border-color: #00ff88;
        }
    </style>
</head>
<body>

    <img src="profil-resmin.jpg" alt="Profil" class="profile-img">
    <h1>Kullanıcı Adın</h1>
    <p>Yazılım Geliştirici | Gamer | 3D Artist</p>

    <div class="links-container">
        <a href="https://github.com/kullaniciadin" class="link-card" target="_blank">GitHub</a>
        <a href="https://youtube.com/kanalin" class="link-card" target="_blank">YouTube</a>
        <a href="https://discord.gg/davetkodu" class="link-card" target="_blank">Discord Sunucum</a>
        <a href="https://modhub.com/projen" class="link-card" target="_blank">Oyun Modlarım</a>
    </div>

</body>
</html>

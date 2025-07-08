<h1>Atividade-08-</h1>
<h2>#08 - Praticando o CSS</h2>

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DVD Menu: O Baile do Simonal</title>
    <style>
        @font-face {
            font-family: 'Bebas Neue';
            src: url('https://fonts.cdnfonts.com/s/7288/BebasNeue-Regular.woff') format('woff'); /* Exemplo de fonte */
            font-weight: normal;
            font-style: normal;
        }

        body {
            margin: 0;
            padding: 0;
            font-family: 'Bebas Neue', sans-serif; /* Usando a fonte Bebas Neue como exemplo */
            color: #fff;
            background: url('https://i.imgur.com/your-simonal-background-image.jpg') no-repeat center center fixed; /* Substitua pela URL de uma imagem de fundo do Simonal */
            background-size: cover;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow: hidden;
            position: relative;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
        }

        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.6); /* Escurece a imagem de fundo */
            z-index: 1;
        }

        .dvd-menu {
            background-color: rgba(0, 0, 0, 0.85); /* Fundo semi-transparente para o menu */
            padding: 40px 60px;
            border-radius: 15px;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.9);
            text-align: center;
            z-index: 2;
            position: relative;
            border: 2px solid #ffcc00; /* Borda dourada para realçar */
        }

        .dvd-menu h1 {
            font-size: 3.5em;
            margin-bottom: 30px;
            color: #ffcc00; /* Título em destaque */
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        .dvd-menu ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .dvd-menu li {
            margin-bottom: 20px;
        }

        .dvd-menu a {
            display: block;
            background-color: #333;
            color: #fff;
            padding: 15px 30px;
            text-decoration: none;
            border-radius: 8px;
            font-size: 1.8em;
            transition: background-color 0.3s ease, transform 0.2s ease;
            border: 1px solid #666;
            letter-spacing: 1px;
            text-transform: uppercase;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
        }

        .dvd-menu a:hover,
        .dvd-menu a:focus {
            background-color: #ffcc00; /* Cor de destaque ao passar o mouse */
            color: #000;
            transform: scale(1.05);
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.7);
        }

        .dvd-menu a:active {
            transform: scale(0.98);
        }

        /* Estilos para a seção de seleção de músicas (simulada) */
        .song-selection {
            display: none; /* Escondido por padrão */
            margin-top: 30px;
            background-color: rgba(20, 20, 20, 0.9);
            padding: 25px;
            border-radius: 10px;
            max-height: 400px;
            overflow-y: auto;
            text-align: left;
            border: 1px solid #666;
        }

        .song-selection h2 {
            font-size: 2em;
            color: #ffcc00;
            margin-bottom: 20px;
            text-align: center;
        }

        .song-selection ul {
            list-style: decimal; /* Números para as faixas */
            margin-left: 20px;
        }

        .song-selection li {
            margin-bottom: 10px;
            font-size: 1.2em;
            color: #ccc;
            cursor: pointer;
            transition: color 0.2s ease;
        }

        .song-selection li:hover {
            color: #ffcc00;
        }

        .back-button {
            display: block;
            margin-top: 30px;
            background-color: #666;
            color: #fff;
            padding: 10px 20px;
            text-decoration: none;
            border-radius: 5px;
            font-size: 1.2em;
            transition: background-color 0.3s ease;
            text-align: center;
            border: none;
        }

        .back-button:hover {
            background-color: #999;
        }

    </style>
</head>
<body>
    <div class="overlay"></div>
    <div class="dvd-menu" id="mainMenu">
        <h1>O Baile do Simonal</h1>
        <ul>
            <li><a href="#" onclick="alert('Iniciando o show... (Simulação)');">Tocar Show</a></li>
            <li><a href="#" onclick="showSongSelection();">Seleção de Músicas</a></li>
            <li><a href="#" onclick="alert('Extras: Entrevista com a produção, bastidores... (Simulação)');">Extras</a></li>
            <li><a href="#" onclick="alert('Créditos: Direção, Produção, Músicos... (Simulação)');">Créditos</a></li>
        </ul>
    </div>

    <div class="dvd-menu song-selection" id="songSelectionMenu">
        <h2>Seleção de Músicas</h2>
        <ul>
            <li>Nem Vem Que Não Tem</li>
            <li>País Tropical</li>
            <li>Meu Limão, Meu Limoeiro</li>
            <li>Sá Marina</li>
            <li>Que Bandeira</li>
            <li>A Pequena Nise</li>
            <li>Na Galha do Cajueiro</li>
            <li>Vesti Azul</li>
            <li>Kriola</li>
            <li>Tributo a Martin Luther King</li>
            <li>Mamãe Passou Açúcar em Mim</li>
            <li>Canto do Povo</li>
            <li>Se Você Pensa</li>
            <li>Taj Mahal</li>
            <li>Fio Maravilha</li>
            <li>Eu Não Tenho Nada a Ver Com Isso</li>
            <li>(Outras faixas simuladas...)</li>
        </ul>
        <a href="#" class="back-button" onclick="hideSongSelection();">Voltar ao Menu Principal</a>
    </div>

    <script>
        function showSongSelection() {
            document.getElementById('mainMenu').style.display = 'none';
            document.getElementById('songSelectionMenu').style.display = 'block';
        }

        function hideSongSelection() {
            document.getElementById('mainMenu').style.display = 'block';
            document.getElementById('songSelectionMenu').style.display = 'none';
        }

        // Sugestão: Alterar a URL da imagem de fundo
        // O ideal seria usar uma imagem real do Simonal ou da capa do DVD.
        // const body = document.querySelector('body');
        // body.style.backgroundImage = "url('https://i.imgur.com/YOUR_SIMONAL_IMAGE.jpg')";
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Filtrer une liste de voitures</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        input {
            padding: 10px;
            width: 250px;
            font-size: 16px;
            margin-bottom: 10px;
        }
        ul {
            list-style: none;
            padding: 0;
        }
        li {
            padding: 8px;
            font-size: 18px;
            border: 1px solid #ccc;
            margin: 5px;
            border-radius: 5px;
            background: #f9f9f9;
        }
    </style>
</head>
<body>

    <h2>Rechercher une voiture</h2>
    <input type="text" id="searchInput" placeholder="Tapez un modèle...">
    
    <ul id="carList">
        <li>Audi A3</li>
        <li>Audi Q5</li>
        <li>BMW X1</li>
        <li>BMW X5</li>
        <li>Citroën C3</li>
        <li>Citroën C4</li>
        <li>Dacia Duster</li>
        <li>Ford Focus</li>
        <li>Ford Mustang</li>
        <li>Mercedes Classe A</li>
        <li>Mercedes Classe C</li>
        <li>Peugeot 208</li>
        <li>Peugeot 3008</li>
        <li>Renault Clio</li>
        <li>Renault Mégane</li>
        <li>Tesla Model 3</li>
        <li>Tesla Model Y</li>
        <li>Volkswagen Golf</li>
        <li>Volkswagen Polo</li>
    </ul>

    <script>
        function filterListByStartCharacter(inputId, listId) {
            var input = document.getElementById(inputId);
            var list = document.getElementById(listId);
            var items = list.querySelectorAll('li');

            input.addEventListener('input', function () {
                var searchTerm = input.value.toLowerCase();
                items.forEach(function (item) {
                    var text = item.textContent.toLowerCase();
                    item.style.display = text.startsWith(searchTerm) ? '' : 'none';
                });
            });
        }

        // Initialisation de la fonction pour l'input et la liste de voitures
        filterListByStartCharacter('searchInput', 'carList');
    </script>

</body>
</html>

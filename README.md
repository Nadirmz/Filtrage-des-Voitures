<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Filtrage des Voitures</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }

        input {
            width: 80%;
            padding: 10px;
            font-size: 16px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        #message {
            color: red;
            font-weight: bold;
            display: none;
        }

        ul {
            list-style-type: none;
            padding: 0;
            width: 80%;
            margin: auto;
        }

        li {
            padding: 10px;
            font-size: 18px;
            border: 1px solid #ccc;
            margin: 5px 0;
            background-color: #f9f9f9;
            border-radius: 5px;
            transition: background-color 0.3s;
        }

        li.found {
            background-color: #90ee90; /* Vert clair */
        }
    </style>
    <script>
        function filterListByStartCharacter(inputId, listId) {
            let input = document.getElementById(inputId).value.toLowerCase();
            let list = document.getElementById(listId).getElementsByTagName("li");
            let found = false;

            for (let i = 0; i < list.length; i++) {
                let item = list[i];
                let text = item.innerText.toLowerCase();

                if (text.startsWith(input) && input !== "") {
                    item.style.display = "";
                    item.classList.add("found"); // Ajout de la classe pour changer la couleur
                    found = true;
                } else {
                    item.style.display = "none";
                    item.classList.remove("found");
                }
            }

            let message = document.getElementById("message");
            if (!found) {
                message.innerText = "Aucune voiture trouvée.";
                message.style.display = "block";
            } else {
                message.style.display = "none";
            }
        }
    </script>
</head>
<body>
    <h2>Rechercher une voiture</h2>
    <input type="text" id="search" onkeyup="filterListByStartCharacter('search', 'liste')" placeholder="Tapez un modèle...">
    <p id="message"></p>
    <ul id="liste">
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
        <li>Logan DACIA </li>
        <li>Renault Clio</li>
        <li>Renault Mégane</li>
        <li>406</li>
    </ul>
</body>
</html>

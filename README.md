<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Accès au PDF</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background: linear-gradient(135deg, #4e54c8, #8f94fb, #81b29a);
            color: white;
        }

        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
        }

        h1 {
            margin-bottom: 20px;
            font-size: 2em;
            color: #fff;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        input {
            width: calc(100% - 22px);
            padding: 15px;
            margin: 10px 0;
            border: none;
            border-radius: 45px;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            font-size: 1em;
            box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.2);
        }

        input::placeholder {
            color: rgba(255, 255, 255, 0.5);
        }

        button {
            padding: 15px 30px;
            border: none;
            border-radius: 45px;
            background: linear-gradient(90deg, #8f94fb, #4e54c8);
            color: white;
            font-size: 1em;
            cursor: pointer;
            transition: background 0.3s ease;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }

        button:hover {
            background: linear-gradient(90deg, #4e54c8, #8f94fb);
        }

        .hidden {
            display: none;
        }

        #pdfContainer {
            margin-top: 20px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Accès au Document PDF</h1>
        <input type="text" id="codeInput" placeholder="Entrez le code d'accès">
        <button onclick="verifyCode()">Accéder</button>
        <div id="pdfContainer" class="hidden">
            <embed src="IXRauWlF.pdf" type="application/pdf" width="100%" height="600px"/>
        </div>
    </div>
    <script>
        // Liste des codes valides
        const validCodes = ["code1", "code2", "code3"]; // Remplacez par vos codes

        function verifyCode() {
            const codeInput = document.getElementById('codeInput').value;
            const pdfContainer = document.getElementById('pdfContainer');

            if (validCodes.includes(codeInput)) {
                pdfContainer.classList.remove('hidden');
            } else {
                alert("Code invalide. Veuillez réessayer.");
            }
        }
    </script>
</body>
</html>

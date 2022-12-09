# Descubra-o-segredo
Um programa que faz o usuario tentar adivinhar um número aleatório

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adivinhe o segredo</title>
</head>
<body>
    <input type="text">
    <button>Adivinhe o segredo</button>
    <script>
        var segredo = Math.round(Math.random() * 10);
        var input = document.querySelector("input");
        input.focus();
        function verifica(){
            if (input.value == segredo){
                alert("Você acertou!!!");
            } else {
                alert("Você errou!!!");
            }
            input.value = "";
            input.focus();
        }

        var button = document.querySelector("button");
        button.onclick = verifica;
    </script>
</body>
</html>

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


//Abaixo o novo modelo um pouco mais inteligente


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
        var segredos = [1,2,3,4];
        
        var input = document.querySelector("input");
        input.focus();
        function verifica(){
            var achou = false;
            for(var posicao = 0; posicao < segredos.length; posicao++) {
                if (input.value == segredos[posicao]){
                    alert("Você acertou!!!");
                    input.value = "";
                    input.focus();
                    achou = true;
                    break;
                } 
                
            }
            if (achou == false){
                alert("Você errou!!");
                input.value = "";
                input.focus();

            } 
    }
        
        var button = document.querySelector("button");
        button.onclick = verifica;
    </script>
</body>
</html>
    
    
//Tornando o programa mais dinamico
    
    
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
    function sorteia() {

       return Math.round(Math.random() * 10);

    }

    function sorteiaNumeros(quantidade) {

        var segredos = [];

        var numero = 1;

        while(numero <= quantidade) {

              var numeroAleatorio = sorteia();
              var achou = false;

              if (numeroAleatorio !== 0) {
                     for(var posicao = 0; posicao < segredos.length; posicao++) {

                           if(segredos[posicao] == numeroAleatorio){
                                achou = true;
                                break;
                           }

                     }

                     if (achou == false) {
                           segredos.push(numeroAleatorio);
                           numero++;
                     }
              }

        }

        return segredos;

    }

    var segredos = sorteiaNumeros(3);

    console.log(segredos);

    var input = document.querySelector("input");
    input.focus();

    function verifica() {

       var achou = false;

       for(var posicao = 0; posicao < segredos.length; posicao++) {

              if(input.value == segredos[posicao]) {

                     alert("Você ACERTOU!");
                     achou = true;
                     break;
              } 
       }

       if(achou == false) {

              alert("Você ERROU!");
       }

       input.value = "";
       input.focus();

    }

    var button = document.querySelector("button");

    button.onclick = verifica;

</script>
    </script>
</body>
</html>

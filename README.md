# dealing-with-stacks-alura-course

Se executarmos esse código, obteremos o seguinte resultado:

Início do main
<br>
Início do metodo1
<br>
Início do metodo2
<br>
1
<br>
2
<br>
3
<br>
4
<br>
5
<br>
Fim do metodo2
<br>
Fim do metodo1
<br>
Fim do main
<br>

Esse é o resultado do fluxo. Repare que ainda não temos orientação a objetos, mas independente do paradigma de programação, usamos uma pilha de execução. Para entendermos melhor, trabalharemos a seguinte imagem:

![01 01_001_console-main-pilha](https://user-images.githubusercontent.com/45438661/212737717-7f2e10a8-c299-4bd5-b1f6-871ebb673074.png)

Imagem que mostra o console e a pilha(stack), mostrando o seu fluxo

Como sabemos, um programa em Java sempre começa no método main(). A pilha ou stack existe para organizar a execução do código, lembrando o que ainda precisa ser executado.

O Java sempre irá procurar primeiro pelo método main(). Depois, ele cria a pilha e coloca o bloco de código dentro de outro, na pilha. Em seguida, o código do metodo1() é inserido nela.

A pilha existe para executar algo e lembrar o que ainda precisa ser executado.

![01 01_002_console-metodo1-pilha](https://user-images.githubusercontent.com/45438661/212737971-e4150544-8c3d-4bbb-b160-4badb08e78ab.png)

Nessa imagem, a pilha contém primeiro o método main e, logo em seguida, o metodo1

Agora, é a vez do metodo1() entrar na pilha de execução. Repare que main() ainda não foi finalizado, porém ele não está sendo executado agora. Apenas o método que está no topo da pilha está sendo executado.

A partir do metodo1(), vem a chamada do metodo2, e todo o bloco de código é jogado dentro da pilha.

![01 01_003_console-metodo2-pilha](https://user-images.githubusercontent.com/45438661/212738077-462644c8-be54-4896-a105-a580261d207e.png)

A pilha contém três métodos, sendo que o último método é o metodo2 que foi chamado a partir do metodo1

Agora, os métodos main() e metodo1() estão parados, pois ainda tem código a ser executado, no caso, as linhas do "Fim do metodo1" e "Fim do main". O metodo2() está sendo executado porque está no topo da pilha, que conseguirá removê-lo assim que terminar de executá-lo, quando não houver mais nada para executar.

![01 01_004_console-remover-metodo2-pilha](https://user-images.githubusercontent.com/45438661/212738199-6c0ce3d0-ce60-4034-82cb-642749b4ae83.png)

Após a mensagem "Fim do metodo2", a pilha remove o metodo2

Quem está sendo executado agora é o metodo1(). O que sobrou nele é a linha que exibe a mensagem "Fim do metodo1". Depois que ele acaba, a pilha o remove e continua com a main(), que ficou por último.

![01 01_005_console-remover-metodo1-pilha](https://user-images.githubusercontent.com/45438661/212738322-967e10ae-dd3d-4f50-8b7d-c36293aceb32.png)

Após a mensagem "Fim do metodo1", a pilha remove o metodo1

Voltando a main(), é exibida a linha que imprime "Fim do main". Com isso, ele é finalizado e retirado da pilha.

![01 01_005_console-remover-metodo1-pilha](https://user-images.githubusercontent.com/45438661/212738376-b2a30210-f826-4a9b-8e77-b966f99f5a77.png)

Imagem que mostra a pilha vazia, após terminar de executar o método main

Quando acabam os métodos da pilha, o Java entende que o processo foi encerrado.

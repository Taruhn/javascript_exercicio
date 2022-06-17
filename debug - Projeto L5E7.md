 As anotações vão ser seguidas em ordem da versão.0 até a versão.6. O que vai ser colocado como introdução no relatório desse readme, é usado para dar entrada 
no que progama faz e quais as funções dele, e na explicação do código inicialmente vai ser da versão 0,ao longo do readme vai ser falado o que foi adicionado, 
removido e/ou modificado em cada um deles.

 O conceito do programa : Ele faz com que se sorteie um número aleatório de 0 a 10 e o usuário tem que jogar com o programa para adivinhar o número que ele escolheu,
sendo que ele da a dica se o número dele está abaixo do valor ou acima do que ele selecionou, o jogador tem 3 tentativas para tentar o número que ele escolheu,
caso o jogador erre as tentativas, ele perde e o jogo acaba, caso acerte o número nessas tentativas o jogador ganha, ocorre uma tela de que ganho e para de fazer
com que o jogador continue fazendo as tentativas.

 Contexto da interface : no código para a interface foi colocada uma label para falar sobre o que é para ser colocado no input abaixo, em seguida tem um input do tipo number 
para colocar um número para ser adivinhado, depois tem um botão para gerar o resultado do numero escolhido e saber se o numero sorteado aleatoriamente pelo codigo está correto ou 
não, ao clicar vai dar um retorno se é para tentar novamente ou que acertou o número adivinhado, caso tenha tenha mais tentativas, ele da um retorno se o numero colocado é menor ou maior
que ele sorteou e se acabou as tentativas ele retorna que acabou o jogo e não acertou dentre as 3 alternativas.

 O código: Dentro do script tem uma variável "numeroSorteado"
que faz que ele um número seja sorteado de 1 até 10, em seguida tem um if para colocar o número sorteado que se o número
a tela for carregada, em seguida uma variável "tentativa", usada para as vezes que for colocada para jogar contra a máquina, depois tem uma variável  "msnSaida" que serve para dar
retorno no resultado da escolha de um número para a adivinhar se está correto ou não. Em seguida possui um função "enviar" para executar o button "enviar" na interface do programa,
dentro dele tem um "val" uma variável que fica no escopo dentro do "enviar" ela tem o nomeclatura de "numeroApostado" e se ela saia um número e que ela puxa o número do imput do número 

quando clica em "enviar" para adivinhar o número sorteado, no console ele mostra qual o número que foi gerado e com ele, e da o retorno na interface se esse qu

 v0.0 = Ela apresenta um bug que quando faz o input de tentativas, ela da um erro de ter uma chance adicional no sorteamento de um número aleatório mesmo que o jogador tenha acertado nas 3 chances, 
o que causa esse bug é na 81 e 83, pois a posição da primeira tentativa está posição zero '0' e ela é considerada como a primeira tentativa, e o número 3 seria a quarta posição desta array, 
a solução é mudar a linha 83 para "if (tentativa <=3) {", com isso ele resolve a quantidade de tentativas, se for voltado só a essa versão (index v.0).
Mas, não resolve o problema de enviar nas chances que sobraram depois de acertar. E também tem um if desnecessário(*1) da linha 67 até a linha 69 que faz 
com que toda vez o que número gerado aleatoriamente de o resultado zero '0', ele vire um número 1, sendo que na descrição do código é que gere um número aleatório entre 0 e 10,
no caso dessa versão está entre 1 e 10.

 Obs:(*1): Entre os códigos da versão 0 a 3, na descrição foi dita que o programa sorteia um número aleatório entre 0 e 10, e nas versoes v4 até a v6, está como um número aleatório entre 1 a 10,
eu vou manter o que eu tinha escrito na v0 conforme a descrição dela.

 v1.0 = Na modificação dessa versão fica nas linhas entre 70 e 78, possui um if com se a 3 tentativa der uma saída de "Jogo encerrado, você perdeu, mais sorte da próxima vez!",
ela aconteçe quando caso o "númeroApostado" seja maior que o "numeroSorteado" e de que o "numeroApostado" ser menor que o "numeroSorteado". Nas 2 primeiras tentativas ele vai responder diferente, 
que ele pode dar como resposta se está certo, se o número é maior, e de o número é menor do que sorteado.
Nessa versão possui uma implementação que faltou em quando for acertada a terceira tentativa e depois de clicar em "Enviar" ele diz "Jogo encerrado, você perdeu, mais sorte da próxima vez!",
por hora essa versão não tem um complemento ocorre uma vitória nesse caso.

 v2.0 = Nessa versão ela teve duas mudanças, sendo a primeira de remoção foi um id na linha 61 com "if (tentativa <= 3) {", pois ao na versão 0 ele era usado para fazer as 3 tentativas,
sendo que na versão 2 ele foi mudado o contexto da quantidade de tentativas e essa parte do código ficou deteriorada e foi removida. Com essa linha removida, foi adidionado um if para
corrigir a versão v1.0, em que ela implementava que não haja um retorno de "Jogo encerrado, você perdeu, mais sorte da próxima vez!" quando for clicar uma quarta vez em que o jogador
já esteja na saída que ganhou o jogo, o if em si é para que não ocorra caso seja maior ou igual a 3.

 v3.0 = Comparado a versão passada, essa versão teve uma adição de uma function que é a "finalizarJogo()", nela tem 2 booleanas, sendo ela um para o botão e outro para a entrada do número
que o jogador está querendo adivinhar, esses dois elementos ficam desabilitados quando o jogador acerta o número e quando ele erra as 3 tentativas e deseja colocar algo para tentar colocar
uma nova tentativa.

 v4.0 = A função que foi adicionada nessa versão foi a adição de um validador de entrada, o objetivo dele é que o usuário não use os números que não foram requiridos para escolher 
que é de 1 a 10. A function "validarEntradas(numeroApostado)" retorna de forma booleana caso o número esteja informado corretamente, ele verifica se o número é menor que 1 ou maior que 10, e se foi deixado a box vazia, 
caso ocorra isso, ele vai dar um retorno de falso, caso aconteça isso ele vai resetar a box onde foi colocado o número e vai dar um alerta esse alerta é uma variável chamada 
"msmSaída", ela é executada quando a validação da um retorno de false, fazendo com que de uma mensagem de saída para informar corretamente, caso o usuário repita o erro ela
vai continuar dando essa resposta. Se no caso for colocado um número desejado, ele vai retornar como verdadeiro e esse número é considerar como uma entrada valida ou "validarEntradas",
como ele foi validado ele é considerado uma aposta valida ou "isApostaValida", com isso ele pode percorrer o "if (isApostaValida)" para fazer o jogo de adivinhação com o número que foi colocado.

 v5.0 = Nessa versão houve modificações na parte do código para ele ficar mais "limpo" e também que possa ter clareza ao ler ele e de que caso ocorra alguma manutenção no código, ele fica mais fácil de achar o erro e de
modificar para colocar as correções. 






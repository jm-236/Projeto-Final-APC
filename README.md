# Projeto-final-APC

## Projeto da disciplina de algoritmos e programação de computadores da UnB.
* Universidade de Brasilia -Instituto de Ciências Exatas
* Departamento de Ciência da Computacão -Algoritmos e Programação de Computadores - 2/2023
* Prof. Carla Castanho e Prof. Frank Ned
* Aluno(a): João Marcelo Costa de Santana
![image](https://github.com/user-attachments/assets/248da361-9218-46c9-b380-b933a58ae09e)



## Projeto Final - Parte 1
* Problema: Implementar um jogo em um grid 2D que possui diversos objetos diferentes, em que todos estes objetos, exceto o controlado pelo jogador, se movimentam constantemente da direita para a esquerda e interagem de diferentes formas com o objeto controlado pelo jogador.
* O jogador tem como objetivo conseguir o maior número de pontos antes do fim do jogo.
* A arena do jogo será representada por um grid 2D de tamanho 10x135, como a mostrada
abaixo:

![image](https://github.com/user-attachments/assets/ba835ec1-fb7f-4f66-8b5c-3c9094f7bc74)
---
### Personagens:

* "+" (verde) : Será o avatar do jogador, ele poderá ser movimentado para cima ou para baixo, e pode ficar parado durante um turno. Caso o jogador digite uma tecla inválida o input deve ser ignorado.
* "X" (vermelho) : Inimigo, surge no canto direito do tabuleiro e se movimenta constantemente para a esquerda, caso encoste no jogador o jogo deve ser encerrado com uma mensagem de “GAME OVER” e a pontuação final. Após sair do limite esquerdo do grid, o ‘X’ deve ser destruído, ou seja, deixa de existir no jogo.
* "F" (azul) : Tanque de combustível, surge no canto direito do tabuleiro e se movimenta constantemente para a esquerda, caso encoste no jogador a quantidade de combustível disponível deve ser aumentada em 40 unidades.
* ">" (verde escuro) : Tiro, é disparado pelo jogador e se movimenta constantemente para a direita, caso encoste em algum outro objeto tanto o tiro quanto o objeto no qual ele encostou devem ser destruídos. Caso destrua um ‘X’ o jogador ganha 50 pontos. Quando um tiro passa do limite direito do grid (a matriz) ele deve ser destruído, ou seja, deixa de existir no jogo.

### Inicialização da partida:

* A inicialização da partida deve ser executada quando o usuário escolher a opção “1 - Jogar” no menu inicial, esta inicialização consiste em criar um grid somente com o ‘+’ no canto esquerdo do grid e iniciar o loop do jogo, onde o grid será atualizado a cada 50 milissegundos, ou seja, 20 frames por segundo.
* No início da partida dois atributos do jogador devem ser inicializados:
  1. Pontos: deve ser inicializado com o valor 0.
  2. Combustível: deve ser inicializado com o valor 400.
* O grid deve ser inicializado contendo somente o personagem controlado pelo usuário, o ‘+’, as demais posições devem ser espaços vazios.

### Aparição de inimigos:
* Inicialmente nenhum inimigo deve aparecer no grid, a cada iteração do loop do jogo um ‘X’ e/ou um ‘F’ podem aparecer na coluna mais à direita do grid, em uma linha aleatória, a aparição ou não de um ‘X’ ou ‘F’ deve ser determinada por um algoritmo randômico.
* Ações do jogador: O jogador controla o ‘+’ que fica sempre na coluna mais à esquerda do grid e entre cada intervalo de atualização do grid pode executar três ações:
  1. Movimentar-se verticalmente. Ao executar essa ação o jogador gasta 2 unidades de combustível. Não deve ser permitido ao jogador se movimentar para fora dos limites do grid.
  2. Atirar. Ao executar essa ação o jogador gasta 3 unidades de combustível.
  3. Ficar parado. Ao executar essa ação o jogador gasta 1 unidade de combustível.

### Formas de se encerrar uma partida:
* Existem duas diferentes maneiras de se encerrar uma partida:
  1. Combustível esgotado: Uma forma de se encerrar uma partida é quando o jogador fica sem combustível.
  2. Atingido por um inimigo: Se um inimigo se mover para a posição em que o jogador está, o jogo deverá ser encerrado.
* Para todas as formas de encerrar o jogo deve ser mostrada uma mensagem de “GAME OVER”, motivo do fim do jogo e a pontuação final do jogador.
* Após cada atualização, você deve limpar a tela antes de mostrar o novo estado do jogo.

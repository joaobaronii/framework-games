# SpriteFramework: SpaceInvaders e FreezeMonsters

## Visão Geral
O projeto consiste na implementação dos 2 jogos, utilizando um framework. Desenvolvido para a disciplina de Princípios e Padrões de Projeto, o projeto tem como objetivo estudar e aplicar padrões de projeto.

## Estrutura do Projeto
O projeto está organizado em:

- **`spriteframework`**: Contém as classes e interfaces do framework, que formam a base para os jogos.
- **`spaceinvaders`**: Inclui a implementação do jogo *SpaceInvaders*.
- **`freezemonsters`**: Inclui a implementação do jogo *FreezeMonsters*.

### Principais
- **SpriteFramework**:
  - `MainFrame.java`: Classe abstrata para configurar a janela do jogo.
  - `AbstractBoard.java`: Classe abstrata que gerencia o ciclo do jogo, renderização e entrada de comandos.
  - `Commons.java`: Interface com constantes compartilhadas (ex.: dimensões do tabuleiro, posições iniciais).
  - `Sprite.java`: Classe base para todos os sprites, gerenciando posição, visibilidade e imagens.
  - `Player.java`: Classe para o sprite do jogador, controlado pelo teclado.
  - `BadSprite.java`: Classe abstrata para sprites inimigos.
  - `BadnessBoxSprite.java`: Classe base para sprites compostos que contêm outros sprites.
- **SpaceInvaders**:
  - `SpaceInvadersGame.java`: Ponto de entrada do jogo, estende `MainFrame`.
  - `SpaceInvadersBoard.java`: Tabuleiro do jogo, estende `AbstractBoard`.
  - `BomberSprite.java`: Sprite alienígena que lança bombas.
  - `Shot.java`: Projétil do jogador.
  - `Bomb.java`: Projétil dos alienígenas.
  - `Commons.java`: Constantes específicas do jogo.
- **FreezeMonsters**:
  - `FreezeMonstersGame.java`: Ponto de entrada do jogo, estende `MainFrame`.
  - `FreezeMonstersBoard.java`: Tabuleiro do jogo, estende `AbstractBoard`.
  - `Woody.java`: Sprite do jogador com movimento bidimensional.
  - `Monster.java`: Sprite inimigo que lança gosma.
  - `FreezeRay.java`: Projétil congelante do jogador.
  - `Slime.java`: Projétil dos monstros.
  - `Commons.java`: Constantes específicas do jogo.

## Padrões de Projeto Utilizados
O framework e os jogos implementam os seguintes padrões de projeto:

- **Template Method**:
  - Usado em `MainFrame` para configurar a janela, com `createBoard()` como ponto de extensão.
  - Usado em `AbstractBoard` para definir o ciclo do jogo e renderização, com métodos como `update()`, `drawOtherSprites()` e `createBadSprites()` personalizados.
- **Factory Method**:
  - Usado em `MainFrame.createBoard()` e `AbstractBoard.createPlayer()` para criar tabuleiros e jogadores específicos.

## Funcionalidades
- **Framework Modular**: Permite criar novos jogos estendendo `MainFrame` e `AbstractBoard`.
- **Sprites Reutilizáveis**: A hierarquia de `Sprite` suporta a adição de novos tipos de sprites.
- **Mecânicas Extensíveis**: Os jogos podem personalizar movimentação, renderização e entrada.
- **Gráficos Baseados em Imagens**: Usa imagens PNG para sprites, com suporte a redimensionamento.
- **Detecção de Colisão**: Implementa colisão baseada em retângulos para projéteis e sprites.

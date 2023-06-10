# Compiladores_2023-1
Repositório da matéria de Compiladores (UnB - FGA) Matéria ministrada pelo professor Edson Junior

## Compiladores

GitHub da Disciplina: [edsomjr/Compiladores: Materiais da disciplina
Compiladores.](https://github.com/edsomjr/Compiladores)

Respostas dos exercícios do livro: [GitHub - fool2fish/dragon-book-exercise-answers
编译原理（紫龙书)](https://github.com/fool2fish/dragon-book-exercise-answers)

Baixe o livro do Dragon Book clicando [aqui](https://github.com/ananorberto/Compiladores_2023-1/raw/main/dragons_book.pdf)
#
### Recomendação - Aulas do professor Judson Santiago
![Foto de um
gato](https://i.ytimg.com/vi/jgI711CrnnY/hqdefault.jpg?sqp=-oaymwEXCNACELwBSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLCDf_lFr_zH1P6Vn2j8MGPozU2iqA)

[Link das video aulas](https://www.youtube.com/playlist?list=PLX6Nyaq0ebfhI396WlWN6WlBm-tp7vDtV)
#

# Conteúdo prova 1

<details>
  <summary>
   Prova 2022.1
  </summary>

  [Gabarito
  oficial](https://github.com/ananorberto/Compiladores_2023-1/blob/main/Provas%20anteriores%20e%20lista/gab_2022_1-p1.pdf)

  1. Complete a sentença:

  “A compilação pode ser dividida em `6`fases, as quais podem ser classificadas em duas partes: `análise` e `síntese`.
  Outra organização possível separa as `4` primeiras fases na interface de vanguarda e as `2` últimas fases na interface
  de retaguarda.”

  #
  2. Considere a gramática livre de contexto G abaixo:
  `S → S concat L | S replace L L | ∊
  L → a | b | c`


  De acordo com as convenções de notação, responda as questões abaixo?
  (i) (2 pontos) Quais são os não-terminais de G?

  > Os não-terminais de G são `S e L`.

  <details>
    <summary>Explicação</summary>


    >💡 Os símbolos não-terminais são aqueles que podem ser expandidos em outros símbolos através das produções da
    gramática. No caso da gramática G
    > dada, existem dois não-terminais, S e L, que representam sequências de símbolos que podem ser derivados a partir
    das produções da gramática.

  </details>


  (ii) (2 pontos) Quais são os terminais de G?

  > Os terminais de G são `concat, replace, ∊, a, b e c`.

  <details>
    <summary>Explicação</summary>


    >💡 Os terminais de uma gramática livre de contexto são os símbolos que não podem ser mais derivados a partir das
    produções da gramática, ou seja,
    > são os símbolos que aparecem nas folhas da árvore de derivação. No caso da gramática G dada, os terminais são
    concat, replace, ∊, a, b e c, que
    > não podem mais ser derivados a partir das produções da gramática.

  </details>


  (iii) (1 ponto) Qual é o símbolo de partida de G?

  > O símbolo de partida de G é S (não-terminal da primeira produção listada).
  <details>
    <summary>Explicação</summary>

    >💡 Em outras palavras, quando começamos a usar a gramática G para gerar sequências de símbolos, começamos com o
    não-terminal S, e a partir daí podemos derivar sequências de símbolos usando as produções de G. Então, podemos dizer
    que S é o símbolo de partida de G.
  </details>

  #
  3. Assinale a alternativa correta.
  Considere o seguinte código de máquina de pilha:
  `value-l a
  push 5
  push 2
  ⌽
  value-r b
  ⍨`
  Marque a expressão, em notação infixada, que é avaliada por este código. Assuma que as operações ⌽ e ⍨ sejam binárias
  e que o ordem de extração dos operando da pilha seja a seguinte: primeiro o operando à direita, em seguida o operando
  à esquerda.


  (X) a := (5 ⌽ 2) ⍨ b
  (B) a := b ⍨ (2 ⌽ 5)
  (C) a := (b ⍨ 2) ⌽ 5
  (D) a := 5 ⌽ (2 ⍨ b)

  >💡 Resposta correta a := (5 ⌽ 2) ⍨ b.
  <details>
    <summary>Explicação</summary>

    1. A instrução "value-l a" indica que a variável "a" será o destino da operação que será realizada, e a instrução
    "value-r b" indica que a variável "b" será o segundo operando.
    2. Em seguida, a instrução "push 5" coloca o valor 5 no topo da pilha, seguida pela instrução "push 2" que coloca o
    valor 2 no topo da pilha.
    3. A instrução "⌽" retira os dois valores do topo da pilha e aplica o operador ⌽, que realiza uma operação binária
    com a ordem dos operandos invertida. Portanto, essa instrução avalia a expressão 2 ⌽ 5 e coloca o resultado (que é 5
    ⌽ 2) no topo da pilha.
    4. Por fim, a instrução "⍨" retira o valor no topo da pilha (que é o resultado da operação anterior, 5 ⌽ 2) e o
    coloca no segundo lugar da pilha, invertendo a ordem dos dois valores na pilha. Assim, o valor final na pilha é o
    resultado da expressão (5 ⌽ 2) ⍨ b, que é atribuído à variável "a”

  </details>
  #
  4. Julgue os itens abaixo. Em cada item, preencha os parêntesis com V (verdadeiro) ou F (falso).


  ( F ) Em uma produção, o símbolo não-terminal que será produzido fica do lado direito da seta.

  <details>
    <summary>💡 Explicação do porquê é falsa</summary>

    > A afirmação é falsa, pois em uma gramática livre de contexto, as regras de produção são escritas com uma seta →. O
    lado esquerdo contém um único símbolo não-terminal, enquanto o lado direito contém uma sequência de símbolos
    terminais e/ou não-terminais.
    Exemplo: `S → aB` (O símbolo não-terminal S é produzido a partir da sequência de símbolos "aB").

  </details>

  ( V ) O símbolo ∊ representa uma cadeia de Tokens vazia.
  ( F ) Uma gramática livre de contexto é ambígua se existe ao menos uma expressão que não possui árvore sintática.

  <details>
    <summary>💡 Explicação do porquê é falsa</summary>

    > Uma gramática é ambígua se existem duas ou mais árvores sintáticas distintas para a mesma sentença. Se uma
    expressão não possui árvore sintática, então ela não é derivável e, portanto, não pode ser ambígua ou não ambígua.

  </details>

  ( F ) Em uma definição dirigida pela sintaxe, um atributo de um nó n é dito sintetizado se ele depende apenas dos
  valores dos atributos das folhas da árvore.

  <details>
    <summary>💡 Explicação do porquê é falsa</summary>
    💡 Explicação do porquê é falsa

    > Um atributo de um nó é dito sintetizado se ele pode ser calculado a partir dos valores dos atributos dos filhos do
    nó da árvore. Sendo assim, o atributo pode depender de outros nós além das folhas da subárvore abaixo dele.

  </details>

  ( V ) Em um esquema de tradução, as ações semânticas são inseridas no lado direito da produção e são delimitadas por
  chaves.

  #
  5. Na linguagem de programação C o enunciado `do-while` possui a forma

  `do { cmd } while ( expr );`

  O laço inicia executando cmd. Em seguida, expr é avaliada: caso seja verdadeira, o laço reinicia com uma nova execução
  de cmd; caso contrário, o laço é encerrado. O significado do enunciado `do-while` é similar a

  `cmd ; while ( expr ) { cmd }`

  Construa um gabarito para a tradução dirigida pela sintaxe que traduz enunciados `do-while` em C para código de
  máquina de pilha.


  <table>
    <thead>
      <tr>
        <th>RÓTULO LOOP</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>CÓDIGO PARA cmd</td>
      </tr>
      <tr>
        <td>CÓDIGO PARA expr</td>
      </tr>
      <tr>
        <td>gotrue loop</td>
      </tr>
    </tbody>
  </table>


</details>
<details>
  <summary>
    Prova 2022.2 
  </summary>

</details>
<details>
  <summary>
    Prova 2023.1 
  </summary>

  Resposta questão 15 - Lógica da questão:

  [CONVIERTE UN NUMERAL DE BASE 7 A BASE DECIMAL](https://www.youtube.com/shorts/qnHaeTIIm9o)

  [https://www.youtube.com/shorts/qnHaeTIIm9o](https://www.youtube.com/shorts/qnHaeTIIm9o)

</details>
<details>
  <summary>
    Lista #1 - 2023.1 
  </summary>

  [lista_1.pdf](https://github.com/ananorberto/Compiladores_2023-1/blob/main/Provas%20anteriores%20e%20lista/lista_1.pdf)

  <details>
    <summary>
      Respostas
    </summary>
      
1. S → SS+ | SS x | a

```c
    S
    |
  /   \
SS+    ax
||     |
aa  +  ax
```

c. Expressões pós-fixadas de adição e multiplicação

2.  Lista →id, Lista | id 

  </details>
</details>


# Conteúdo prova 2

:warning: **A fazer...**

#

# Conteúdo prova 3

:warning: **A fazer...**
#

<details>
  <summary>
    Dragon book exercise answers
  </summary>

  ### **1.1.1**

  Qual é a diferença entre um compilador e um intérprete?

  ### Resposta

  Um compilador é um programa que pode ler um programa em um idioma - o idioma de origem - e traduzi-lo para um programa
  equivalente em outro idioma – o idioma de destino e relatar qualquer erros no programa de origem que ele detecta
  durante o processo de tradução.

  O intérprete executa diretamente as operações especificadas no programa de origem nas entradas fornecidas pelo
  usuário.

  ### **1.1.2**

  Quais são as vantagens de:
  (a) um compilador sobre um intérprete
  (b) um intérprete sobre um compilador?

  ### Resposta

  a. O programa de destino no idioma da máquina produzido por um compilador geralmente é muito mais rápido que um
  intérprete no mapeamento de entradas para saídas.

  b. Um intérprete geralmente pode fornecer um diagnóstico de erro melhor do que um compilador, porque executa a
  instrução do programa de origem por instrução.

  ### **1.1.3**

  Quais são as vantagens de um sistema de processamento de idiomas no qual o compilador produz linguagem de montagem em
  vez de linguagem de máquina?

  ### Resposta

  O compilador pode produzir um programa em linguagem de montagem como sua saída, porque a linguagem assembly é mais
  fácil de produzir como saída e mais fácil de depurar.

  ### **1.1.4**

  Um compilador que traduz um idioma de alto nível em outro de alto nível idioma é chamado de *fonte a fonte* tradutor.
  Quais são as vantagens para usando C como idioma de destino para um compilador?

  ### Resposta

  Para a linguagem C, existem muitos compiladores disponíveis que compilam em quase todo hardware.

  ### **1.1.5**

  Descreva algumas das tarefas que um montador precisa executar.

  ### Resposta

  Traduz do idioma da montagem para o código da máquina. Este código de máquina é realocável.

</details>


<details>
  <summary>
    Resumo Vídeo aulas - Compiladores (Judson Santiago)
  </summary>


- Aula00 (Introdução)
    - Existem dois tipos de processadores de linguagem:
        - Compiladores: traduzem programas para linguagem de máquina
        - Interpretadores: executam programas em linguagem de alto nível
    - A compilação se divide em duas partes:
        - Análise: leitura e análise do código fonte (3 analise - Decomposição)
        - Síntese: geração e otimização de código abjeto (3 síntese - Produção)
    - O desenvolvimento de um compilador é uma tarefa complexa
        - Ele deve estar correto, ser eficiente e ter uma boa usabilidade
- Aula01(Ambiente Linux) e Aula02( Ambiente VS Code)
    
    [Aula 01 - Ambiente Linux | Histórico | Terminal | Shell | g++ | gdb | make | cmake | Compiladores](https://www.youtube.com/live/JJmf1wlNGeQ?feature=share)
    
    [Aula 02 - Ambiente VS Code | Visual Studio Code | C++ | Make | CMake | g++ | gdb | Compiladores](https://www.youtube.com/live/7WrTl_MaLk8?feature=share)
    
- Aula03 (Tradução Dirigida pela Sintaxe)
    
    Pulamos o `Analisador Léxico`  poque usamos dígitos simples (1 | 2 | 3)
    
    ![Untitled](Compiladores%20c5d1f86db6d941e793f1b8acb658b62d/Untitled.png)
    
    - Uma Gramática é formada por um conjunto de produções.
        - Elas descrevem as construções de uma língua.
        - Cadeias válidas podem ser visualizadas por árvores de derivação.
    - A tradução dirigida por sintaxe permite construir um tradutor simples usando uma busca em profundidade na árvore de derivação:
        - Anotada com atributos
        - Modificada por ações semânticas
    - Essa técnica de tradução ilustra de forma simples a análise sintática.
- Aula04(Análise Sintática)

</details>

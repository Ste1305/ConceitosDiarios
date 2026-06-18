# **Dia 17 de Junho 2026**

# Matematica - Teoria dos conjuntos
- **Representação explicita de um conjunto**: $A = \{3; 1; 2\}$ . No conjunto não tem o conceito de ordem.
- **Pertinência e não pertinência**: $x \in A$ ou $x \notin A$ ou seja x pertence ao conjunto A ou x não pertence ao conjunto A; a pertinência ou não é expressa com um valor Verdadeiro ou Falso.
    - Conjuntos podem tambem ser objetos de outros conjuntos: $1 \in \{1;2 \{3; 4\}; 5; 6\}$ porém $3 \notin \{1;2 \{3; 4\}; 5; 6\}$ .
- **Representação implicita de um conjunto**: $A = \{x \mid p(x)\}$ ou seja o conjunto A dos objetos x tais que p(x) se torna uma proposição verdadeira (objetos do conjunto serão apenas aqueles que tornarema a expressão verdadeira). Ex: O conjunto F de elementos x tais que  a condição $x^2 =9$ seja verdadeira $F = \{x \mid x^2 = 9\}$ equivale a $F = \{-3; 3\}$ .
- **Relação de Inclusão**: X está contido em Y ou X é subconjunto de Y: $X \subset Y$; Y contém ou Y é um superconjunto de X X: $Y \supset X$ (em $\subset$ ou em $\supset$, a abertura aponta para o conjunto maior).
- **Conjunto vazio**: $\emptyset$ conjunto sem elementos, ele é subconjunto de qualquer conjunto X ou seja $\emptyset \subset X$.

| Simbolo | Definição |
| :---: | :---: |
| $=$ | Igualdade |
| $\neq$ | Desigualdade |
| $\in$ | Pertinência |
| $\notin$ | Não Pertinência |
| $\subset$ | Inclusão |
| $\not\subset$ | Não Inclusão |
| $\supset$ | Contingência |
| $\not\supset$ | Não Contingência |
| $\emptyset$ | Conjunto Vazio|
| $\mathbb{N}$ | Conjuntos dos números naturais: números positivos |
| $\mathbb{Z}$ | Conjunto dos números inteiros: $\mathbb{N}$, o 0 e os simétricos de $\mathbb{N}$ |
| $\mathbb{Q}$ | Conjunto dos números racionais: $\mathbb{N}$ , $\mathbb{Z}$, frações, decimais finitos e decimais periodicos |
| $\mathbb{R}$ | Conjuntos dos números reais: $\mathbb{N}$, $\mathbb{Z}$, $\mathbb{Q}$ e os númeror irracionais (raizes, decimais não periodicos) |

- **Intervalos na Reta-eixo**: sendo cada ponto de uma reta-eixo representado por um número de $\mathbb{R}$, podemos representar conjuntos de números como segmentos dessa reta-eixo, e podemos chamar eles de *intervalos*.
    - *Intervalos fechados*: são os intervalos fechados nas extremidades, ou seja as extremidades são incluídas no proprio intervalo; na reta-eixo as extremidades são representadas como círculos cheios.
    - *Intervalos abertos*: são os intervalos abertos nas extremidades ou seja as extremidades não são incluidas no proprio intervalo; na reta-eixo as extremidades são representadas como círculos vazios ou setas.

| | Representação implicita | Representação como intervalo |
| :---: | :---: | :---: |
| Intervalos fechados | $\{x \in \mathbb{R} \mid a \leq x \leq b\}$ | $[a;b]$ |
| Intervalos abertos | $\{x \in \mathbb{R} \mid a < x < b\}$ | $(a;b)$ |
| Intervalo aberto a esquerda | $\{x \in \mathbb{R} \mid a < x \leq b\}$ | $(a;b]$ |
| Intervalo aberto a direita | $\{x \in \mathbb{R} \mid a \leq x < b\}$ | $[a;b)$ |
- **Módulo ou valor absoluto**: a distancia entre um número real (ou ponto da reta associado a um número real) e a origem da reta-eixo: modulo do número x, $|x|$; o módulo deve sempre ser $\geq 0$, para poder representar uma distâcia, logo $|5| = 5$ e $|-5| = 5$.
    - O módulo possui duas soluções possiveis, sendo $|x| = \begin{cases} x, & \text{se } x \ge 0 \\ -x, & \text{se } x < 0 \end{cases}$, ou seja uma solução para x $\ge 0$ e outra para $x < 0$.
- **Operações entre conjuntos**: quando operações entre connjuntos são feitas, sempre se leva em consideração um conjunto *Universo ($\mathbb{U}$)*, ou seja poderia ser $\mathbb{R}$ ou $\mathbb{N}$ ou qualquer outro, mas o resultado será restringido ao conjunto Universo escolhido. No contexto do conjunto $\mathbb{U}$, todos os outros são subconjuntos dele.

| Operação | Representação | Descrição |
| :---: | :---: | :---: |
| Interseção | $A \cap B = \{x \in \mathbb{U} \mid x \in A \text{ e } x \in B\}$ | Objetos que pertencem ao mesmo tempo ao conjunto A **E** B |
| União | $A \cup B = \{x \in \mathbb{U} \mid x \in A \text{ ou } x \in B\}$ | Objetos que pertencem pelo menos ao conjunto A **OU** B, podendo eventualmente pertencer à ambos |
| Diferença | $A - B = \{x \in \mathbb{U} \mid x \in A \text{ e } x \notin B\}$ | Os objetos que pertencem ao conjunto A, mais não ao conjunto B |
| Complementar | $A'= \{x \in \mathbb{U} \mid x \notin A\}$ | Os objetos que **NÃO** pertencem ao conjunto A mas pertencem ao Conjunto U |

- **Princípios de Contagem - Casa dos Pombos**: se você colocar mais casas do que pombos, então pelo menos uma casa conterá mais de um pombo, ou seja *se $n + 1$ objetos forem distribuidos em $n$ caixas, então pelo menos uma caixa conterá pelo menos 2 objetos*; esse príncipio é usado para provar a ocorrência de alguma coisa, mesmo sem saber exatamente onde.
- **Príncipios de Contagem - Príncipio de Adição**: o total das possiveis maneiras de executar uma tarefa, que pode ser executadas de varias maneiras exclusivas, é a soma das possibilidades de cada maneira.
    - *Exemplo*: tem que escolher uma bebida entre 3 tipos de sucos e 4 tipos de refrigerantes; se você escolhe apenas uma bebidas, tem $3 + 4 = 7$ possiveis escolhas.
    - *Se os conjuntos A e B **NÃO TÊM** elementos em comum (união)*: $A = \{1; 2; 3\}$ e $B = \{4; 5; 6; 7\}$ logo $|A \cup B| = |A| + |B|$ ou seja $|A \cup B| = 3 + 4 = 7$.
    - *Se os conjuntos A e B **TÊM** elementos em comum (interseção)*: $A = \{1; 2; 3\}$ e $B = \{3; 4; 5\}$ logo $|A \cup B| = |A| + |B| - |A \cap B|$ devemos retirar a interseção dos dois conjuntos porque senão ficariam repetidos (*Príncipios da Inclusão - Exclusão*); ex: Quantos numeros entre 1 e 100 são multiplos de 2 **ou** 5? Múltiplos de 2 = 50; Múltiplos de 5 = 20; se somarmos $50 + 20 = 70$ estamos contando os multiplos de 10 duas vezes, logo $50+20-10=60$.
- **Príncipios de Contagem - Príncipio da Multiplicação**: se uma tarefa pode ser realizada em etapas, e a primeira etapa pode ser feita de $m$ maneiras, a segunda etapa de $n$ maneiras, então o total de maneiras será $m*n$ maneiras.
    - *Exemplo 1*: Você tem 3 camisetas e 4 calças e quer formar um conjunto de roupa, logo terá $3 * 4 = 12$ combinações possíveis.
    - *Exemplo 2*: uma senha tem 2 letras e 3 digitos, sabendo que as letras são 26 e os digitos 10, logo $26*26*10*10*10=676000$ senhas possiveis.

| Adição | Multiplicação |
| :---: | :---: |
| Palavra chave: **OU** | Palavra chave: **E** |
- **Fatorial**: o fatorial é um aplicação do *Princípio da Multiplicação*, pois ele se aplica em casos onde temos que ordenar objetos distintos e precisamos saber quantas maneiras hà, e em Multiplicações onde as escolhas diminuem sucessivamente. $n! = n*(n-1)*(n-2)*...*2*1$. $0!=1$ por convenção.
    - *Exemplo*: tem 4 pessoas e você deve coloca eles numa fila: a primeira posição será ocupada por uma pessoa, sobram 3 agora; a segunda posição será ocupada por outra pessoa, sobram 2; a terceira posição vai para outra pessoa, agora sobra 1; quarta posição vai para a ultima pessoa; logo $4*3*2*1=24$ ou seja $4!=24$.
    - *Relação com o Princípio da Multiplicação*:
        - Princípio da Multiplicação: $n_1*n_2*...*n_k$
        - Fatorial: $n*(n-1)*(n-2)*...*2*1$

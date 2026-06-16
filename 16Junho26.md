# **Dia 16 de Junho 2026**

# Java
- **Arrays**: uma única variavel que armazena multiplos valores (ex: `int[] idades = new int[5];` o array de tipo *int* é declarado e inicializado com 5 elementos).
    - Cada elemento do array tem um **índice** (ex: `idades[2] = 25`, ou seja o índice 2 é inicializado com 25). Os índices **começam do 0** (ex: `idade[0]` até `idade[4]` ou seja um array de 5 elementos).
    - Para declarar multiplos valores de uma vez: `int[] idades = {18, 30, 25, 87, 12};`.
    - Para determinar o tamanho do array podemos usar `System.out.println(idades.length);` que exibirá o tamanho do array escolhido.
- **Loops com arrays**: podemos exibir todos os valores de um array usando o *for loop* dessa forma:
``` 
int[] idades = {18, 33, 24, 64, 45};
for(int x = 0; x < idades.length; x++){
    System.out.println(idades[x]);
} 
```
ou usando o *for-each loop* dessa forma:
````
int[] numeros = {2, 3, 5, 7};
for(int x : numeros){
    System.out.println(x);
}
````
ficando mais compacto e legível nesse contexto; esse metodo não usa os índices, mas os valores do array.
- **Arrays multidimensionáis**: arrays que possuem multiplas dimensões, ou seja multiplos índices (ex: `int[][] numeros = {{1, 2, 3}, {4, 5, 6}};`); para acessar um elemento: `int x = numeros[1][0]` onde o primeiro índice indica qual array, e o segundo indica a posição do valor naquele array.
    - Podemos comparar os dois arrays de um array bidimensional como *linhas* e *colunas*.
    - O loop *for* usado para imprimir um array bidimensional funciona assim: o *for* externo itera as linhas, o *for* interno itera as colunas:
    ```
    int[][] numeros = {
    {1, 2, 3},
    {4, 5, 6}
    };
    for(int i = 0; i < numeros.length; i++){
        for(int j = 0; j < numeros[i].length; j++){
            System.out.println(numeros[i][j]);
        }
    }
    ```
- **Métodos**: métodos são blocos de códigos que executam uma taréfa especifica (ex: `println()` é um método).
    - Podemos criar métodos personalizados assim:
    ```
    static void welcome(){
        System.out.println("Welcome");
        System.out.println("I am a method");
        System.out.println("End of method");
    }
    ```
    o método é sempre seguido de *parenteses*, mas o bloco dele ´contido entre *chaves*; `static` serve para poder usar o método em `main`; `void` porque não retorna nenhum valor.
    - Podemos criar métodos com parâmetros, ou seja com variaveis:
    ```
    static void welcome(String name){
        System.out.println("Welcome, " + name);
    }
    ```
    nesse caso adicionamos um parâmetro `String` chamado `name`, que será usado no bloco de código do método, quando informado (chamado) pelo usuário. Os valores usados como parâmetros são chamados de *argumentos*.
    - Ao criar métodos com multiplos argumentos, quando chamamos o método, deveremos fornecer os argumentos na ordem estabelecida (ex: `static void welcome(String name, int age)` primeiro o nome da pessoa e depois a idade, não o contrario).
    - **Return**: ao definir um método, podemos decidir que ele retorne um valor: nesse caso substituimos `void` com o tipo do valor retornado e adicionamos a *keyword* `return` no final do bloco do código do método:
    ```
    static double perc(double num, int percentual){
        double res = num * percentual / 100;
        return res;
    }
    ```
    todo código após o `return` será inutilizado.



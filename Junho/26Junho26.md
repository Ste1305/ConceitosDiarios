# **Dia 26 de Junho 2026**

# C
- **Arrays**: um array é usado para guardar varios valores ao invés de criar muitas variaveis:
```C
int ages[7]; //declara um array que se chama ages, de tipo int que contém 7 elementos
```
Usamos os *indices* do array para acessar os valores, cada indice é uma posição; o primeiro valor é o indice 0:
```C
#include <stdio.h>

int main(){
    int ages[7];
    ages[2] = 24;//terceiro valor do array
    ages[0] = 31;//primeiro valor do array

    printf("%d", ages[2]);//podemos acessar o valor pelo indice

    return 0;
}
```
   - Quando conhecemos todos os valores do array, podemos inicializar todos eles de uma vez só:
```C
#include <stdio.h>

int main(){
    //não precisamos especificar o tamanho do array se inicializado desse jeito
    int ages[] = {31, 18, 24, 55, 29};//valores entre {} e separados por ,

    printf("%d", ages[2]);

    return 0;
}
```
---
- **Loops com arrays**: podemos acessar todo o conteúdo do array com um loop `for`:
```C
#include <stdio.h>

int main(){
    int ages[] = {31, 18, 24, 55, 29};

    for(int i = 0; i < 5; i++){//i começa do 0 (primeiro valor), i < do tamnaho do array
        printf("%d\n", ages[i]);
    }

    return 0;
}
```
   - Podemos usar de varias maneiras o loop `for`, por exemplo operando com oas valores do array:
```C
#include <stdio.h>

int main(){
    int ages[] = {31, 18, 24, 55, 29};
    int total = 0;

    for(int i = 0; i < 5; i++){
        total += ages[i];//vamos calcular a soma de todos os valores do array
    }
    printf("Soma: %d\n", total);

    return 0;
}
```
---
- **Array multidimensional**: um array pode ter multiplas dimensões (ou seja, multiplos indices), por exemplo para representar uma tabela: uma dimensão para as linhas e uma para as colunas: 
```C
int ages[2][4] = {{1, 2, 3, 4}, {5, 6, 7, 8}};
//o primeiro colchete indica as dimensões, o segundo o tamanho de cada dimensão: 2 linhas e 4 colunas
```
Para acessar os valores, seguimos o mesmo principio:
```C
#include <stdio.h>

int main(){
    int ages[2][4] = {//podemos escrever dessa forma tambem
        {1, 2, 3, 4}, 
        {5, 6, 7, 8}
    };

    printf("%d\n", ages[1][2]);
    //o primeiro colchete acessa o array correspondente (segundo)
    //o segundo colchete acessa o valor daquele array (terceiro)
    return 0;
}
```
   - Para acessar os valores em arrays bidimensionais, podemos usar loopf `for` aninhados:
```C
#include <stdio.h>

int main(){
    int ages[2][4] = {
        {1, 2, 3, 4}, 
        {5, 6, 7, 8}
    };

    for(int i = 0; i < 2; i++){ //loop externo itera as linhas
        for(int j = 0; j < 4; j++){ //loop interno itera colunas
            printf("%d ", ages[i][j]); //imprime os valores
        }
        printf("\n"); //formata a tabela
    }
    return 0;
}
```
---
- **Strings**: variavel que contém texto (definido por ""); uma string pode ser considerada um *array de caracteres* e o especificador de formato é `%s`:
```C
#include <stdio.h>

int main(){
    char text[] = "some text"; //um array de char

    printf(text);

    return 0;
}
```
   - Se queremos incluir na nossa string caracteres especiais (tipo "") devemos usar a contrabarra `\`, como por `\n`:
```C
#include <stdio.h>

int main(){
    char text[] = "The title says \"The Great Gatsby\".";

    printf(text);

    return 0;
}
```
---
- **Strings e input**: quando usamos `scanf()` e queremos entrar com uma string:
```C
#include <stdio.h>

int main(){
    char name[50]; //declaramos um array de 50 caracteres
    scanf("%s", name); //não precisamos do & para enregistrar o endereço pois é um array de caracteres

    printf(name);

    return 0;
}
```
   - `scanf()` com string só entrará com a primeira palavra, caso a string conter uma frase com espaços; para poder entrar tambem espaços precisamos usar `fgets()` no lugar:
```C
#include <stdio.h>

int main(){
    char name[50];
    fgets(name, 50, stdin);
    //(nome da string, tamanho da string, metodo de entrada)
    printf("%s\n", name);

    return 0;
}
```
# **Dia 28 de Julho 2026**

# C
## Formulando algoritmos
- **Repetição controlada por contador**: tecnica que usa um *contador* para especificar quantas vezes um comando será executado. Essa tecnica é tambem chamada de *repetição definida* pois o numero de repetições é conhecido antes que o loop seja executado. A variavel usada como contador deve ser inicializada com zero ou um, a segundo dos casos: não inicilaizar essa variavel quer dizer deixar o valor de "lixo" nela (causando um *erro lógico*).
Exemplo:
```C
// programa que calcula a media das notas de uma turma
#include <stdio.h>

int main(){

    int contador; //numero da nota a digitar em seguida
    int nota;
    int total; //soma das notas inseridas pelo usuario
    int media;

    //fase de inicialização
    total = 0;
    contador = 1; //contador do loop

    //fase processamento
    while(contador <= 10){
        printf("Digite a nota: \n"); //prompt para inserção
        scanf("%d", &nota); //lê a nota do usuario
        total = total + nota; //soma nota ao total
        contador +=1; //incrementa contador
    }

    //fase de termino
    media = total / 10;
    printf("Media da turma é %d\n", media); //exibe resultado

    return 0;
}
```

- **Repetição controlada por sentinela**: o valor da *sentinela* (ou *valor sinalizador, valor artificial ou valor flag*) é usado para indicar o fim de inseção de dados em um loop: o usuario precisa inserir o valor da sentinela para poder sair do programa. Essa tecnica é chamada de *repetição indefinida* pois não sabemos quanto o loop vai iterar. O valor da sentinela deve ser inicializado com um valor a não ser confundido com os valores fornecidos.
Exemplo:
```C
#include <stdio.h>

int main(){

    int contador; //numero de notas digitadas
    int nota;
    int total;
    float media;

    //fase inicialização
    total = 0;
    contador = 0;

    //fase processamento
    printf("Digite a nota, -1 no fim: "); //primeira nota recebida
    scanf("%d", &nota);

    //loop enquanto valor sentinela não foi lido
    while(nota != -1){
        total = total + nota;
        contador +=1;

        //recebe as outras notas
        printf("Digite a nota, -1 para finalizar: ");
        scanf("%d", &nota);
    }

    //fase finalização
    if(contador != 0){ //pelo menos uma nota digitada
        media = (float) total / contador; //calcula media evitando truncamentos
        printf("Media da turma é: %.2f\n", media);
    }
    else {
        printf("Nenhuma nota informada\n"); //se não informada nenhuma nota 
    }

    return 0;
}
```
O `(float)` é o *operador unario de conversão* que C disponibiliza para poder dividir dois numeros inteiros exibindo as partes decimais (*conversão explicita*).
**NB**: nunca use `float` para comparar igualdade ou desigualdade.

- **Estruturas de controle aninhadas**: outra tecnica de controle usada para criar algoritmos eficazes de iteração que usa uma estrutura de controle dentro de outra (*aninhamento*); para aumentar o desempehno é boa pratica inicializar as variaveis quando são declaradas.
Exemplo:
```C
//analise de resultados de exame
#include <stdio.h>

int main(){

    //inicializa variaveis nas declarações
    int aprovados = 0; //alunos aprovados
    int reprovados = 0; //alunos reprovados
    int aluno = 1; //contador alunos
    int resultado; //resultado do exame

    //processa 10 alunos usando loop controlado por contador
    while(aluno <= 10){
        printf("Forneça resultado (1 - Aprovado, 2 - Reprovado): ");
        scanf("%d", &resultado);

        //incremento aprovados/reprovados
        if(resultao == 1){
            aprovados +=1;
        }
        else {
            reprovados += 1;
        }
        aluno += 1;
    }

    //fase finalização
    printf("Aprovados: %d\n", aprovados);
    printf("Reprovados: %d\n", reprovados);

    //se mais de 8 aprovados, imprime bonus
    if(aprovados > 8){
        printf("Bonus ao instrutor!\n");
    }

    return 0;
}
```

- **Operador de incremento e decremento**: C disponibiliza os seguintes operadores unários para incremento e decremento:

| Operador | Nome |Exemplo | Explicação |
| --- | --- | --- | --- |
| ++ | ++a | Pré-incremento | Incrementa a em 1, e então usa o novo valor de a na expressão em que a estiver |
| ++ | a++ | Pós-incremento | Usa o valor corrente de a na expressão em que a estiver, e então incrementa a em 1 |
| -- | --b | Pré-decremento | Decrementa b em 1, e então usa o novo valor de b na expressão em que b estiver |
| -- | b-- | Pós-decremento | Usa o valor corrente de b na expressão em que b estiver, e então decrementa b em 1 |

```C
#include <stdio.h>

int main(){
    
    int c;

    c = 5;
    printf("%d\n", c); //imprime 5
    printf("%d\n", c++); //imprime 5 e depois o incrementa
    printf("%d\n\n", c); //imprime 6

    c = 5;
    printf("%d\n", c); //imprime 5
    printf("%d\n", ++c); //incrementa e depois imprime 6
    printf("%d\n\n", c); //imprime 6

    return 0;
}
```

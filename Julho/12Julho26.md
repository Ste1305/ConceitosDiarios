# **Dia 12 de Julho 2026**

# Redes de Computadores
## Arquitetura em camadas
- A internet é um conjunto de redes de computadores que trocam informações entre si: para que isto seja possível ela tem que seguir algumas regras de comunicação, os **protocolos de rede**.
- Dado o grande numero de protocolos que a internet precisa para funcionar na melhor maneira possível, os arquitetos e projetistas da rede implementaram o modelo *dividi et impera*, ou seja, dividiram os problemas a serem resolvidos em problemas menores; dessa forma tambem a arquitetura de rede foi dividida em porções menores, chamadas de **camadas**.
- **Camadas**: cada *camada* é responsavel por resolver um problema especifico: para poder fazer isso, cada camada possui seus próprios protocolos; as camadas são dispostas em **pilhas** (ou **stack**); as camandas são numeradas de baixo pra cima.
    - A relação entre camadas é a seguinte: **a camada superior utiliza os serviços da camada imediatamente inferior** (ou seja, a camada 3 utiliza os serviços da camada 2); de maneira analoga podemos dizer que **cada camada oferece serviços para camada imediatamente superior** (ou seja, a camada 1 oferece serviços para a camada 2). 

    | Elemento da camada | Descrição |
    | --- | --- |
    | Serviço | Conjunto de funcionalidade que uma camada oferece; ele diz o que a camada faz, não como faz. |
    | Protocolo | Implementa o serviço, responsavel de como a camada faz o que faz. |
    | Interface | Ponto de comunicação entre camadas, onde a camada superior usa o serviço da camada inferior. |

- **Comunicação vertical**: devida à sua estrutura em pilha (stack), a comunicação entre camadas é *vertical*, ou seja, o dado desce da camada mais alta até a mais baixa: isso é verdade na pilha da origem, pois na pilha de destino elesobe da mais baixa até a mais alta; conforme cada camada que ele passe, o dado recebe istruções dos protocolos para que possa ser processado na camada adiacente.
- **Comunicação horizontal**: conforme vimos, o dado desce e sobe pelas camadas, criando a comunicação vertical; mas as mesmas camadas da pilha de origene e daquela de destino tambem se comunicam (através das istruções deixadas pelos protocolos das camadas) de modo que tenha uma comunicação entre camadas do mesmo nível, ou seja, para que haja uma comunicação *horizontal* também. 
- **Encapsulamento e desencapsulamento**: o encapsulamento é o processo que ocorre na comunicação vertical e que de fato permite a comunicação horizontal (que é um processo virtual, diferente do processo vertical): na medida que o dado desce a pilha de camadas para chegar à mais baixa, cada camada adiciona um *cabeçalho* ao dado; supondo de ter um modelo a tres camadas, o dado desce da camada mais acima, a camada 2 adiciona a este um cabeçalho com as informações necessarias para que a camada 2 do destino possa tratar esse dado (comunicação horizontal), quando o dado descer até a camada 1, o cabeçalho precedente já é parte do dado, aí a camada 1 adiciona seu proprio cabeçalho. esse é o *encapsulamento*.
Ao subir na pilha de destino, acontece o processo inverso: cada camada lê o cabeçalho deixado pela camada par da origem, e o retira do dado; quando ele chegará na camada da cima, o dado original será lido. Esse é o *desencapsulamento*.
   - **PDU**: PDU (Protocol Data Unit) é constituida durante o encapsulamento: é constituida pela informação que vem da camada superior e do cabeçalho da própria camada.
---
# C
- **Métodos de output**: os métodos mais usado são contido na libraria `<stdio.h>`.

| Método | Uso | Sintaxe |
| --- | --- | --- |
| `printf()` | Formata o output com o uso de especificadores de formato e precisa de newline `\n`| `printf("Meu nome é %s e tenho %d anos de idade\n", nome, idade);`|
| `puts()` | Imprime uma string (sem formatar), e con newline incluido | `puts("Olá mundo");` |
| `putchar()` | Imprime um caractere só, muito leve | `putchar('A');` |
| `fprintf()`| Formata como `printf()`, mas pode escolher o fluxo de saida (file, tela `stdout` ou erros `stderr`) | `fprintf(stdout, "mensagen\n");`|
| `fputs()`| Como `puts()`, mas pode escolher o fluxo de destinação e precisa do `\n` | `fputs("mensagen\n", stdout);` |
| `fputc()` | Versão de `putchar()` que verifica o fluxo de saida | `fputc('A', stdout);`|
| `sprintf()`| Não imprime, mas grava o resultado formatado em uma string, sem controle no buffer (buffer oveflow) | `sprintf(destinação, "formato", valores);` ou seja `sprintf(char mensagem[100], "Tenho %d anos", anos);`|
| `snprintf()` | Como acima, mas com controle de tamanho, mais seguro | `snprintf(mensagem, sizeof(mensagem), "Tenho %d anos", anos);` |

- **Especificadores de fomato**: 
    - `%d`: int
    - `%f`: float/double
    - `%c`: char
    - `%s`: string
    - `%u`: unsigned int
    - `%ld`: long
    - `%lf`: double
    - `%x`: hexadecimal
    - `%o`: octal
    - `%p`: pointer

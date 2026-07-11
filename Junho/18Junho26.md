# **Dia 18 de Junho 2026**

# Java
- **Introdução à OOP (Programação Orientada à Objetos)**: cada objeto tem uma *identidade* única, cada objeto é independente; cada objeto tem caracteristicas que o descrevem, chamadas de *atributos* (os atributos descervem o estado atual do objeto); cada objeto tem um *comportamento* especifico.
    - Logo, as tres dimenões de um objeto são *IDENTIDADE, ATRIBUTOS, COMPORTAMENTOS*.
    - Cada objeto é definido por uma *CLASSE*, ou seja uma classe define a descrição ou a definição de um objeto; logo podemos afirmar que **um objeto é a instância de uma classe**.
    - Cada classe define atributos e comportamentos de um ou masi objetos.
- **Criação de uma classe**: 
```Java
public class Animal{
    void bark(){
        System.out.println("Woof-Woof");
    }
}
```
esse exemplo cria uma classe chamada `Animal` e cria um metodo nela que devolve um comportamento.
 Criada a classe, podemos voltar no nosso `main` e criar nosso primeiro objeto:

```Java
    public class Animal{
        void bark(){
            System.out.println("Woof-Woof");
        }
    }

    class MyClass{
        public static void main(String[] args){
            Animal dog = new Animal();
            dog.bark();
        }
    }
```

nota-se que `dog` é uma instância da classe `Animal`, e o metodo `bark()` pode ser chamado por ele.
- **Definindo atributos**: considere o exemplo:

```Java
public class Vehicle{
    int maxSpeed;
    int Wheels;
    String color;
    double fuelCapacity;

    void horn(){
        System.out.println("Beep!");
    }
}
```
nossa classe `Vehicle` tem 4 atributos e 1 metodo. Agora vamos criar objetos a partir da nossa classe e caracterizar eles com os atributos e metodos:

```Java
public class Vehicle{
    int maxSpeed;
    int Wheels;
    String color;
    double fuelCapacity;

    void horn(){
        System.out.println("Beep!");
    }
}

class MyClass{
    public static void main(String[] args){
        Vehicle v1 = new Vehicle();
        Vehicle v2 = new Vehicle();
        v1.color = "red";
        v2.horn();
    }
}
```
- **Modificadores de acesso**:

| Tipo de acesso | Classe | Variaveis | Metodos |
| :---: | :---: | :---: | :---: |
| `public` | accessivel às outras classes | accessivel a partir de todas as classes | accessivel a partir de todas as classes |
| `private` | x | acessivel só dentro da classe declarada | acessivel só dentro da classe declarada |
| `default` | accessivel às classes do mesmo pacote | accessivel para classes do mesmo pacote | accessivel para classes do mesmo pacote |
| `protected` | x | accessivel para classes do mesmo pacote e subclasses podem acessar variaveis da superclasse | accessivel para classes do mesmo pacote e subclasses podem acessar metodos da superclasse |

Lembrando che se nada especificado antes de variaveis ou metodos, o `default` se aplica.
- **Getters e Setters**: são usados para proteger os dados criando classes. Fundamentais para *encapsulamento*.
    - **Getters**: o metodo `get` devolve o valor correspondente (o nome da variavel depois do `get` deve ser em majuscolo).
    - **Setters**: o metodo `set` muda o valor correspondente usando um parâmetro (o nome da variavel depois do `set` deve ser em majuscolo)
    - **`this`**: palavra chave usada para se referir ao objeto atual.

```Java
public class Vehicle{
    private String color;

    //getter
    public String getColor(){
        return color;
    }

    //setter
    public void setColor(String c){
        this.color = c;
    }
}
```
Uma vez declarados os *getters e setters*, podemos usar eles no nosso `main`.

```Java
public class Vehicle{
    private String color;

    //getter
    public String getColor(){
        return color;
    }

    //setter
    public void setColor(String c){
        this.color = c;
    }
}

class Program{
    public static void main(String[] args){
        Vehicle v1 = new Vehicle;
        v1.setColor("Red");
        System.out.println(v1.getColor());
    }
}
```
---
# Matematica
- **Agrupamento Arranjo simples**: no arranjo a ordem importa, diferente da combinação. Para constituir um arranjo simples precisamos escolher $p$ elementos dentre $n$ elementos disponiveis, cuidado com a ordem dos elementos e sem repetição de elementos.
$A_{n,p}=\frac{n!}{(n-p)!}$ . 
    - *Exemplo 1*: Quantos agrupamentos podem ser formados com um conjunto de 3 elementos: $n=3$ e $p=2$ logo $A_{3,2}=\frac{3!}{(3-2)!}=\frac{3!}{1!}=6$ .
    - *Exemplo 2*: Em uma conjunto de 10 pessoas, queremos escolher 3 delas para ocupar cargos diferentes: primeiro cargo 10 opções, segundo cargo 9 opções, terceiro cargo 8 opções, ou seja $A:{10,3}=\frac{10!}{(10-3)!}=10\times 9\times 8=720$ ou mais simples ainda: $10 \times 9 \times 8=720$.
- **Agrupamento Permutação simples**: agrupamento em que utilizamos todos os elementos dispóniveis, a ordem importa e não hà repetição.
$P_n=n!$ ou seja, o *fatorial* de $n$.
    - *Exemplo*: Quantos anagramas podemos formar a partir de uma palavra de 5 letras diferentes: $P_5=5!$ logo $5\times 4 \times 3 \times 2 \times 1= 120$.
- **Agrupamento Combinação simples**: agrupamento em que escolhemos $p$ elementos dentre $n$ elementos disponiveis, a ordem *não* importa e não ha repetição. $C_{n,p}=\frac{n!}{p!(n-p)!}$.
    - *Exemplo 1*: Quantas duplas podem ser formadas a partir de um conjunto de 5 pessoas: $n=5$ e $p=2$ logo $C_{5,2}=\frac{5!}{2!(5-2)!}=\frac{5!}{2!3!}=\frac{5 \times 4}{2}=10$.
    - *Exemplo 2*: Em uma turma de 10 alunos, quantas comissões de 3 alunos podem ser formadas: $n=10$ e $p=3$ logo $C_{10,3}=\frac{10!}{3!(10-3)!}=\frac{10 \times 9 \times 8}{3 \times 2 \times 1}=120$

| Agrupamento | Uso de todos os elementos? | Ordem importa? | Formula |
| :---: | :---: | :---: | :---: |
| Permutação | Sim | Sim | $P_n=n!$ |
| Arranjo | Depende | Sim | $A_{n,p}=\frac{n!}{(n-p)!}$ |
| Combinação | Depende | Não | $C_{n,p}=\frac{n!}{p!(n-p)!}$ |

- **Agrupamento Arranjo com repetição**: agrupamento onde escolhemos $p$ posições, a ordem importa e pode sim haver repetição; temos $n$ elementos disponiveis e queremos fazer agrupamentos de tamnaho $p$, logo:
$AR_{n,p}=n^p$.
    - *Exemplo 1*: Quantos codigos de 3 letras podem ser formados usando $A=\{a;b;c\}$: $n=3$ e $p=3$ logo $AR_{3,3}=3^3=27$.
    - *Exemplo 2*: Quantas senhas de 4 digitos podemos formar usando os algarismos de 0 a 9: $n=10$ e $p=4$ logo $AR_{10,4}=10^4=10000$ ou seja $10 \times 10 \times 10 \times 10=10000$.
- **Agrupamento Permutação com repetição**: agrupamento onde usamos todos os elementos do conjunto, a ordem importa e existem elementos iguais e repetidos, ou seja se temos $n$ elementos no conjunto, dos quais $n_1$ são iguais de um tipo, $n_2$ iguais de outro tipo eccetera, logo:
$P=\frac{n!}{n_1!n_2!\dots n_k!}$.
    - *Exemplo 1*: ANA, letras A, A, N ou seja $n=3$, $n_A=2$ logo $P=\frac{3!}{2!}=\frac{6}{2}=3$.
    - *Exemplo 2*: BANANA ou seja $n=6$, $n_A=3$, $n_N=2$, $n_B=1$ logo $P=\frac{6!}{3!2!}=\frac{720}{6\times 2}=60$.
    - *Exemplo 3*: MISSISSIPPI ou seja $n=11$, $n_I=4$, $n_S=4$, $n_P=2$ logo $\frac{11!}{4!4!2!}=34650$.
- **Agrupamento Permutação circular**: agrupamento onde os elementos são dispostos em circulos e as eventuais rotações não produzem arranjos diferentes. Veja: 4 pessoas $\{A,B,C,D\}$ en filas seriam $P_4=4!=24$, mas sentadas em uma mesa redonda: $\{A,B,C,D\}$, $\{B,C,D,A\}$, $\{C,D,A,B\}$, $\{D,A,B,C\}$ são iguais: foi girada simplesmente a mesa.
$PC_n=(n-1)!$ ou seja, mantendo uma pessoa fixa (digamos A), temos que organizar as outras logo $(n-1)!$.
    - *Exemplos*: Quantas maneira 5 pessoas podem sentar numa mesa redonda: $PC_5=(5-1)!$ logo $PC_5=4!=24$.
- **Agrupamento Combinação com repetição**: agrupamento onde escolhemos $p$ elementos, a ordem não importa e a repetição é permitida, ou seja é o numero de combinações com repetições de $n$ elementos tomados $p$ a $p$, ou seja:
$CR_{n,p}\binom{n+p-1}{p}$.
    - *Exemplo 1*: Escolha 2 bolsa de sorvete dentre de 3 sabores: $n=3$ e $p=2$ logo $CR_{3,2}=\binom{3+2-1}{2}=\binom{4}{2}=6$.
    - *Exemplo 2*: Uma confeitaria oferece 5 tipos de doces; quantas maneiras existem de escolher 3 doces potendo repetir: $n=5$ e $p=3$ logo $CR_{5,3}=\binom{5+3-1}{3}=\binom{7}{3}=\frac{7!}{3!(7-3)!}=\frac{7!}{3!4!}=35$.
    - Lembrando que $\binom{n}{p}$ é igual a $\frac{n!}{p!(n-p)!}$.

| Agrupamento | Uso de todos os elementos? | Ordem importa? | Formula |
| :---: | :---: | :---: | :---: |
| Permutação simples| Sim | Sim | $P_n=n!$ |
| Arranjo simples| Depende | Sim | $A_{n,p}=\frac{n!}{(n-p)!}$ |
| Combinação simples| Depende | Não | $C_{n,p}=\frac{n!}{p!(n-p)!}$ |
| Permutação com repetição | Sim | Sim | $P=\frac{n!}{n_1!n_2!\dots n_k!}$ |
| Permutação circular | Sim | Sim | $PC_n=(n-1)!$ |
| Arranjo com repetição | Depende | Sim | $AR_{n,p}=n^p$ |
| Combinação com repetição | Depende | Não | $CR_{n,p}\binom{n+p-1}{p}$ |









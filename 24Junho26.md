# **Dia 24 de Junho 2026**

# Java
- **Encapsulamento**: encapsulamento é um dos 4 pilares da OOP; ele consiste no "esconder" os detalhes da implementação para os usuarios; ele funciona atraves do *data hiding*, ou seja esconder as variaveis de uma classe e só deixar elas "visíveis" atraves de *metodos, getters ou setters*; por esse fim, cada variavel será declarada como `private`.
- **Herança**: herança é o processo que permite à algunas classes de "herdar" as propriedades (metodos ou atributos) de outra classe, chamada de *classe pai*; a classe herdeira é chamada de *subclasse* (ou classe derivada,ou classe filha).
    - Para poder herdar, temos que usar a palavra chave `extends`:

    ```Java
    class Dog extends Animal{
        // a classe Animal é a classe pai (superclasse), Dog é uma extensão dessa classe (subclasse)
    }
    ```
    - Lembre-se da palavras-chave `protected`, onde se indica um atributo que pode ser acessado só pela classe e as classes filhas.

```Java
class Animal{
    protected int legs; //atributo protegido
    public void eat(){ //metodo da classe Animal
        System.out.println("Animal eats");
    }
}

class Dog extends Animal{ //Dog é subclasse de animal e herda o atributo protegido legs
    Dog(){ //costrutor de Dog
        legs = 4;
    }
}

class MyClass{
    public static void main(String[] args){
        Dog d = new Dog(){ //atraves do construtor, Dog pode usar o metodo da classe pai, eat()
            d.eat();
        }
    }
}
```
    - Os construtores da classe pai não são herdados (pois não são atributos nem metodos), porem são chamados quando a subclasse é instanciada.

- **Polimorfismo**: o polimorfismo acontece quando tem uma hierarquia di classes relacionadas através da herança, ou seja a classe pai tem um metodo próprio, que as classes filhas herdam, mas que pode produzir diferentes resultados de acordo com que o usa (overriding):

```Java
class Animal{
    public void makeSound(){
        System.out.println("Grr...");
    }
}
class Cat extends Animal{
    public void makeSound(){
        System.out.println("Meow");
    }
}
class Dog extends Animal{
    public void makeSound(){
        System.out.println("Woof");
    }
}

class Program{
    public static void main(String[] args){
        Animal a = new Dog();
        Animal b = new Cat();

        a.makeSound(); // vai imprimir "Woof"
        b.makeSound(); // vai imprimir "Meow"
    }
}
```

- **Overriding**: overriding acontece quando uma subclasse define o comportamento de um método que é próprio dela, ou seja ela herda da superclasse um método especifico, mas ela modifica a comportamento desse metodo para usá-lo de maneira diferente (ver o trecho de código anterior).
    - O *overriding* é tambem conhecido como *polimorfismo runtime*.
    - As regras para ter *Overriding* são:
        - O método dve ter o memso tipo de retorno e os mesmo argumentos.
        - o tipo de acesso não pode ser mais restritivo daquele do método da classe pai (se o método da classe pai é declarado como `public`, o da classe filha não pode ser `private` nem `protected`).
        - Um método declarado `final` ou `static` não pode ser sovrascrito.
        - Construtore não podem ser sovrascritos.
- **Overloading**: isso acontece quando métodos têm o mesmo nome mas diferentes parametros (útil quando você precisa o mesmo funcionamento do método mas com paramêtros diferentes); vamos usar o exemplo desse método:

```Java
int max(int a, int b){
    if(a > b){
        return a;
    }
    else{
        return b;
    }
}
```

Esse método funciona somente com `int`, mas nós queremos que funcione também com `double`:

```Java
class Program{
    static double max(double a, double b){
        if(a > b){
            return a;
        }
        else{
            return b;
        }
    }

    static int max(int a, int b){
        if(a > b){
            return a;
        }
        else{
            return b;
        }
    }

    public static void main(String[] args){
        System.out.println(max(8, 17));
        System.out.println(max(3.14, 7.68));
    }
}
```

Um *overload* deve ter uma lista de argumentos diferentes; os parametros deves ser diferentes em tipo, numero ou ambos; *overload* é chamado também de *polimorfismo compile-time*.

- **Classes abstratas e abstração**: um exemplo de abstração pode ser um livro: quando pensamos nele, não sabemos dos detalhes tipo número das paginas, o tema, a cor da capa... assim é com a abstração: conhecemos o conceito e qualidades essenciais, mas não os detalhes. 
    - No Java usamos *classes abstratas* e *interfaces*; usamos a palavra-chave `abstract`.
        - Se uma classe é abstrata, não podemos criar instâncias delas (mas podemos herdar dela).
        - Se ums classe possui um método abstrato, ela deve ser abstrata (um método abstrato não possui corpo: `abstract void walk();`).

```Java
abstract class Animal{ //classe abstrata
    int legs = 0;
    abstract void makeSound(); // método abstrato
}
class Cat extends Animal{ //subclasse de Animal
    public void makeSound(){ //modifica o método abstrato para ser personalizado da subclasse
        System.out.println("Meow");
    }
}

public class Program{
    public static void main(String[] args){
        Cat c = new Cat();
        c.makeSound(); //imprime "Meow"
    }
}
```

- **Interfaces**: uma interface é uma classe completamente abstrata, ou seja ela possui somente métodos abstratos.
    - Ela é definida usando a palavra-chave `interface`;
    - Pode contêr somente variaveias `static final`;
    - Não pode contêr construtores (já que não pode ser instanciada);
    - Pode extender para outras interfaces;
    - Uma classe pode implementar varias interfaces.
    - Uma interface é implicitamente abstrata, não precisa usar `abstract`;
    - Os métodos de uma interface são impicitamente abstratos, não precisa definir `abstract`; eles são implicitamente `public`.

```Java
interface Animal{
    public void eat();
    public void makeSound();
}
```
*Uma classe pode herdar somente de uma outra classe, mas pode implementar varias interfaces.*
   - Para implementar uma interface precisa usar a palavra-chave `implements`.
   - Quando implementou, precisa fazer *override* de todos os métodos:

```Java
interface Animal{ //interface desclarada
    public void eat();
    public void makeSound(); //métodos abstratos implicitos
}
class Cat implements Animal{ //classe implementa interface
    public void makeSound(){
        System.out.println("Meow"); //override método1
    }
    public void eat(){
        System.out.println("omnomnom"); //override método2
    }
}

public class Program{
    public static void main(String[] args){
        Cat c = new Cat(); //instancia criada
        c.eat();
    }
}
```



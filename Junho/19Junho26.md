# **Dia 19 de Junho 2026***

# Java
- **Construtores**: construtores são metodos evocados quando um objeto é criado e que são usados para inicializar esses objetos; o nome do construtor deve ser o mesmo da sua classe e não deve retornar um tipo especifico:

```Java
public class Vehicle{
    private String color;
    Vehicle(){ //construtor
        color = "Red";
    }
}
```
Cada vez que um objeto vai ser criado a a partir dessa classe, ele vai ter o atributo `color = "Red"`. Podemos tambem fazer que o construtor pegue parametros para inicializar atributos:

```Java
public class Vehicle{
    private String color;
    Vehicle(String c){
        color = c;
    }
}
```
O construtor é chamado, quando criamos um objeto, com a palavra chave `new`:

```Java
public class MyClass{
    public static void main(String[] args){
        Vehicle v = new Vehicle("Blue"); //chamando o construtor, que vai declarar Blue como atributo
    }
}
```
Na mesma classe podemos ter varios construtores, cada um deles pode ter um parâmetro diferente (usamos os *setters* para ajustar o valore do atributo):

```Java
public class Vehicle{
    private String color;

    //temos dois construtores com parâmetros diferentes
    Vehicle(){
        this.setColor("Red");
    }
    Vehicle(String c){
        this.setColor(c);
    }

    //setter
    public void setColor(String c){
        this.color = c;
    }

    //getter
    public String getColor(){
        return color;
    }
}

public class Program{
    public static void main(String[] args){
        //agora a cor chamada è Red
        Vehicle v1 = new Vehicle();
        //agora a cor vai ser a de nossa escolha
        Vehicle v2 = new Vehicle("Green");
    }
}
```
O Java fornece de default um construtor, mesmo que nós não o especificamos.
- **Value Types**: os tipos de valores são os topis basicos (*bytes, short, int, long, float, double, boolean, char*). Quando um valor è dado a eles, esse valor ocupa espaço na memoria assim, quando os colocamos num metodo, não mexemos na variavel em si, mas apenas no valor dela:

```Java
public class MyClass{
    public static void main(String[] args){
        int x = 5;
        addOneTo(x);
        System.out.println(x); //imprime o valor de x ou seja 5
    }

    static void addOneto(int num){ //por isso que a declaração de metodo não afeta a variável
        num = num + 1;
    }
}
```
- **Reference Types**: os tipos de referencia aramezenam valores (referencias) na alocação de memoria quando o dado correspondente é armazenado; isso ocorre quando você cria um objeto usando o construtor:

```Java
public class MyClass{
    public static void main(String[] args){
        Person j; 
        j = new Person("John");
        j.setAge(20);
        celebrateBirthday(j);
        System.out.println(j.getAge());
    }
    static void celebrateBirthday(Person p){
        p.setAge(p.getAge() + 1);
    }
}
public class Person{
    private String name;
    private int age;

    Person(String n){ //construtor aqui
        this.name = n;
    }
    public int getAge(){
        return age;
    }
    public void setAge(int a){
        this.age = a;
    }
}
```
O metodo `celebrateBirthday` usa um objeto da classe `Person` como parâmetro, incrementando seu atributo; já que foi usado um construtor para `j`, esse é um tipo de referência, logo o metodo afeta o objeto em si, mudando o valor do seu atributo (*Array e String* tambem são reference types).
- **Classe Math**: a classe Math é usada para chamar metodos especificos para operações matematicas; para acessar essa classe não precisa criar objetos dela, mas simplesmente escrever `Math.` e o metodo correspondente.
    - `Math.abs(n)` devolve o valor absoluto do seu parâmetro.
    - `Math.ceil()` arredonda um float até o int *maior* mais próximo (o valor devolvido será `double`).
    - `Math.floor()`arredonda um float até o int *menor* mais próximo (em `double`).
    - `Math.max(n,p)` devolve o maior dos seus parâmetros.
    - `Math.min(n,p)` devolve o menor dos seus parâmetros.
    - `Math.pow(n,p)` devolve a potência do primeiro parâmetro elevado pelo segundo parâmetro.
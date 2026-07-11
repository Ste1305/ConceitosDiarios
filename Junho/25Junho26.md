# **Dia 25 de Junho 2026**

# Java
- **Type Casting**: quer dizer atribuir um valor de um tipo para uma variavel de outro tipo: 

```Java
public class Program{
    public static void main(String[] args){
        double a = 42.571;
        int b = (int) a; // typecasting
        System.out.println(b); // imprime 42
    }
}
```
- *Type casting* é obrigatorio quando se atribui `float` para `int`. 
---
- **Casting com classes**: existem dois tipos de *casting*, quando se trata de classes:
    - *Upcasting*: é o que acontece quando se cria uma instância de uma subclasse; é um processo automatico pois nunca vai falhar:

    ```Java
    Animal a = new Cat();
    ```
    Vamos supor aqui que `Cat` seja subclasse de `Animal`.
    - *Downcasting*: acontece quando estamos chamando um objeto de uma superclasse para a sua subclasse; esse procedimento não é automatico, porque o processo pode falhar (a superclasse `Animal` pode conter varias subclasses, mas nem todas vão ser `Cat`, por exemplo):

    ```Java
    Animal a = new Cat();
    ((Cat)a).makeSound(); //tentando chamar a variavel a para o tipo Cat e executar o seu método
    ```
---
- Quando nos usamos o *Override*, isso se aplica somente ao objeto que implementou o override do método; se criamos outra instância da classe, o método dela ficará padrão (ao menos que nós o modificamos de novo):

```Java
class Machine{
    public void start(){
        System.out.println("Starting..."); //método padrão da classe
    }
}

class Program{
    public static void main(String[] args){
        machine m1 = new Machine(){ // primeiro objeto criado da classe Machine
            @Override public void start(){ //@override é um comentario para visualizar melhor o método trocado
                System.out.println("Wooooo"); //override do método
            }
        };
        Machine m2 = new Machine(); //segunda instância da classe
        m2.start(); //o metodo imprimirá "Starting..."
    }
}
```
---
- **Classes internas**: podemos criar uma classe aninhada em outra; a classe interna pode ser `private`, ou seja não poderá ser acessada por um objeto fora da classe; a classe interna pode acessar todos os métodos e variaveis da classe externa:

```Java
class Robot{ //classe externa
    int id;
    Robot(int i){ //construtor
        id = i;
        Brain b = new Brain();//cria uma instância da classe interna
        b.think();
    }

    private class Brain{ //classe interna privada
        public void think(){
            System.out.println(id + " is thinking");
        }
    }
}

public class Program{
    public static void main(String[] args){
        Robot r = new Robot(1); //cria instância da classe robot que inclui a instância da classe Brain
    }
}
```
---
- Quando comparamos objetos com `==`, estamos comparando a referencia deles e não o valor:

```Java
class Animal{
    String name;
    Animal(String n){
        name = n;
    }
}
class myClass{
    public static void main(String[] args){
        Animal a1 = new Animal("Robbie");
        Animal a2 = new Animal("Robbie");
        System.out.println(a1 == a2); //apesar de ser instancias da mesma classe e com o mesmo nome, será retornado o valor false porque são duas referencias diferentes
    }
}
```
---


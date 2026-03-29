# Patrones de Diseño

- Class Factory
- Facade
- Singleton

## Patrón Singleton

Un solo elemento de una clase a través de nuestra app.

> Un ejemplo es simular una base de datos, tenemos una clase de datos que necesita únicamente una instancia.

```java
public clas Data() {
    List<A> a;
    List<B> b;
    static Data instance = null //Una variable static se llama
                                //desde que se compila el programa

    public Data getInstance() {
        if (this.instance == null) {
            instance = new Data();
        }
        return instance;
    }
}
```

¿Y esto para qué nos sirve?

Data existe globalmente, ejemplo:

```java
Data getInstance() a.add(O object);
```

Su aplicación es un antipatrón, cómo:

```java
public class Plane {
    int id;
    String airline;

    void save() {
        //Código
    }
}
```

```java
public class AirPortGate {
    String id;
    String terminal;
    boolean occupied;
    Plane plane;

    void save() {
        //Código
    }

    void assignPlane(Plane p) {
        Data getInstance();
        getGates("A3");
        setPlane(3, "A4")
    }
}
```

## Class Factory

```java
public interface Enemy {

void movement();
void spawn();
void attack();

}
```

Usar el patrón class factory para hacerlos spawnear aleatoriamente

```java
public class EnemyFactory {
    public Enemy generateEnemy(String name, int hp) {
        switch (name) {
            case "A":
                return new AEnemy(hp);
            case "B":
                return new BEnemy(hp);
        }
    }
}
```

## Patrón fasado (fachada) 'Facade'

El problema que intente resolver el patrón es cuando tenemos un sistema muy complejo y necesitamos configurarlo para cada operación.

Un ejemplo del **_patrón fasado_** puede ser una App Bancaria.

Una clase `Depositos` puede ser la fachada. Cómo un intermediario de procesos mucho más complejos, eso evita repetir la misma cantidad de pasos en c/u de los pasos.

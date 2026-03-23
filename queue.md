# Queue

Con colas, no se puede insertar en cualquier momento.

> "vine tarde, voy hacia atras".

En las colas, el primer "atendido" es el que llegó primero, **el último en llegar es el último en salir**.

## Primero tenemos una clase con métodos abstractos

```java
abstract class LinearStructure<T> {

}
```

```java
public class Queue<T> extends LinearStructure<T> {

}
```

# Colas y servidores

El servidor es el agente que atiende a los elementos de la cola, el servidor manda a llamar a métodos como `delete()`.

| Metodo / Tipo de dato | List        | Queue | Stack |
| --------------------- | ----------- | ----- | ----- |
| insert()              | O(n)        | O(1)  | O(1)  |
| delete()              | O(n) / O(1) | O(1)  | O(1)  |
| find()                | O(n)        | O(1)  | O(1)  |

---
title: "Algoritmos y estructuras de datos 02-02-2026"
output: pdf_document
---

# Listas Encadenadas

- lista simplemente encadenada
- lista doblemente encadenada
- lista circular

## Apuntadores (referencias)

### Listas simplemente encadenadas

```java {}
class Node<T> {
    T value;
    Node<T> next;

    public Node<T> (T value) {
    this.value = value;
    this.next = null;
    }
}

public class LinkedList<T> {
    Node<T> first;
    int count;
}

public class LinkedList<T>() {
    first = null;
    count = 0;
}

public void Add(T value, int pos) {
    if (first == null) {
        first = new Node<T>(value);
        count++
    }
    else {
    var current = first;
    while (current.getNext() != null) {
        current = current.getNext();
    }
    current.setNext(new Node<T>(value));
    count ++
    }
}
```

```java
current = first;

    for (int i = 0; i < pos; i++) {
        current = current.getNext();
    }
var aux = current.getNext();
current.setNext(new Node<T>(value));
current.getNext().setNext(aux);

```

### Listas doblemente encadenadas

```java {.line-numbers}
//En el constructor cambio en línea 5
class Node<T> {
    T value;
    Node<T> next;
    Node<T> previous;

    public Node<T> (T value) {
    this.value = value;
    this.next = null;
    this.previous = null;
    }
}
```

```java
public class DoubleLinkedList<T>{
Node<T> last;
Node<T> first;
int count;

    public LinkedList<T>() {
        last = null;
        first = null;
        count = 0;
    }
}
```

cambio en el add():

```java {.line-numbers}
//Cambio en línea 12 y 13
public void Add(T value, int pos) {
    if (first == null) {
        first = new Node<T>(value);
    }
    else {
    var current = first;
    while (current.getNext() != null) {
        current = current.getNext();
    }
    current.setNext(new Node<T>(value));
    var aux = current;
    current = current.getNext();
    current.setPrevious(aux);
    last = aux;
    }
}
```

### Listas Circulares

```java
class Node<T> {
    T value;
    Node<T> next;
    Node<T> previous;

}

public class CircularList<T> {
    Node<T> first;
    Node<T> last;

    public void Add(T value) {
        if (first == null) {
            first = new Node<T>(value);
            last = first;
            first.setNext(last);
            last.setPrevious(first); //2ble encadenada
        }
        else
        {
            var curr = first;
            while (curr.getNext() != first) {
                curr = curr.getNext();
                curr.setNext(new Node<T>(value));
                last = curr.getNext();
                last.setNext(first);
                last.setPrevious(curr); //2ble encadenada
                first.setPrevious(last); //2ble encadenada
            }
        }
    }
}
```

## Comparable (Interfaz)

Clase abstracta de java ya incluida, aunque creemos un ADT podemos heredar de esta clase abstracta.

```java
public class Sorter<T> extends Comparable<T> {
    public T[] BubbleSort(T[] input) {
        for (var i = 0; i < input.length; i++) {
            for (var j = 0; j < input.length; j++) {
                if (input[i].compareTo(input[j]) > 0) {
                    var aux = input[i];
                    input[i] O input[j];
                    input[j] = aux;
                }
            }
        }
        return input;
    }
}
```

para despues:

```java
public class Student extends Comparable {
    @Override
    int CompareTo(Studen a, Student b) {
        // -1 --> menor
        // 0 --> igual
        // 1 --> mayor
    }
}
```

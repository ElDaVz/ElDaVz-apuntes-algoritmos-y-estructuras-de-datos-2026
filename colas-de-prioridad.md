# Colas de prioridad

- Min heap
- Max heap

> orden invariante
> Forma invariante

para eliminar valores hacer la siguiente pregunta: mi nodo hijo tiene más prioridad que yo como raiz? Es mi hijo menor que yo? (o en caso de ser max heap) es mi hijo mayor que yo? R// sí -> subir nodo hijo como raiz. no -> comparar con el otro nodo del lado derecho y repetir el proceso. **En caso de tener los dos nodos hijos mayor prioridad que el padre, comparar left con right y definir si prioridad.**

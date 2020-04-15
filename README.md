# Manejo de colecciones en java

Este repositiorio sera un pequeño resumen de el taller de www.openwebinars.net sobre la colecciones de java

### **¿Qué es una coleccion?**
Una colección es un contenedor para un conjunto de elementos de un tipo en una sola unidad.

Se usa para almacenamiento, recuperación y manipulación de datos.

Suele representar elementos que forman grupos naturales
* un buzón de correo (colección de mensajes)
* un carrito de la compra (colección de items)


### **Ventajas del uso de colecciones**
* Reduce el esfuerzo de programación
* Aumenta la calidad y velocidad del programa
* Reduce esfuerzo para aparender y usar otras librerias
* Fomenta la reutilización de software

### **Interfaz Iterable<E\>**

* Nos permite recorrer y eliminar los elementos
* Permite usar el forEach y el bucle tipo for-each
```java
 public class IterableApp {

     public static void main(String[] args) {

         // Obtenemos el iterable por la vía que corresponda
         Iterable<String> unIterable = obtenerIterable();

         // Lo podemos recorrer usando un bucle for-each
         for (String s: unIterable) {
             System.out.println(s);
         }

         // También con el método forEach
         unIterable.forEach(System.out::println);


     }

     private static Iterable<String> obtenerIterable() {
         return Arrays.asList("String1", "String2", "String3");
     }

 }
```

### **Interfaz Collection<E\>**

* Extiende Iterable<E\>
* Representa un grupo de elementos
* Todas las interfaces heredan de esta menos Map y derivados
* Sirve para manipular colecciones de la forma mas general posible.

Se pueden realizar las siguientes operaciones:
* Tamaño: size y isEmpty
* contains
* add y remove
* iterator
* containsAll, addAll...
* toArray
* Streams


### **Interfaz Set<E\>**
* Hereda de Collection<E\>
* No permite duplicados
* No hay acceso posicional

**Implementaciones de Set<E\>**

HashSet<E\> -> No se podra predecir nada sobre orden, es la que mejor rendimiento nos aporta, no esta sincronizada y nos permite insertar valores nulos.

LinkedHashSet<E\> -> Almacenara los valores en una tabla hash manteniendo el orden de inserción, nos permite valores nulos.

TreeSet<E\> -> Almacena los valores en un arbol red-black, mantiene el orden basado en sus valores no permite nulos y su rendimiento es de O(log(N)) debido a su estructura de árbol


### **Interfaz List<E\>**
* Hereda de Collection<E\>
* Permite duplicados
* Acceso posicional

Las operaciones que se pueden realizar son parecidas a la de los arrays.

**Implementaciones de List<E\>**

ArrayList<E\> -> Suele ser la mas adecuada y tiene acceso por indices

LinkedList<E\> -> Suele tener peor rendimiento tambien tiene accesso por indice pero requiere de mas espacio.
ya que debe incluir dos referencias.

Queue<E\> -> Funcioan como una cola FIFO (First in first out)

Deque<E\> -> Funcioan como una cola FIFO (First in first out) o como una pila LIFO (Last in First out)


### **Interfaz Map<K,V\>**

* no hereda de Collection<E\>
* Maneja pares clave, valor
* Para cada clave hay un solo valor
* Se le suele conocer como diccionarios y no puede almacionar tipos primitivos.

Se pueden realizar las siguientes operaciones:
* put(key, value)
* get (key)
* containsKey(key) / containsValue(value)
* remove(key)



**Implementaciones de Map<E\>**

HashMap<K,V\> -> Es la mas utilizada, su tiempo de ejecución es constante O(1) y no es sincronizada

LinkedHashMap<K,V\> -> Rendimiento algo peor que HashMap, Ordena los pares clave valor según su inserción

TreeMap<K,V\> -> Peor rendimiento que las otras, mantiene las claves en orden.

### Colecciones para situaciones especiales

**Colecciones no modificables:**

Son colecciones que una vez creadas no se pueden modificar. Si intentamos modificarla nos saltara una excepción UnsupportedOperationException

**Colecciones Sincronizadas:**

Aptas para el uso de diferentes hilos de ejecución.

### Librerias de colecciones de terceros

Las mas usuales son
* Guava de google
* Eclipse Collections
* Apache commons Collections








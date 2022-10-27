# Segunda clase 
> Revisión de funciones matemáticas, sistemas numéricos, diferentes tipos de contadores, la diferencia entre los tiempos, final vs const, concatenación de cadenas y listas.

## Funciones matemáticas
Es necesario hacer uso de la librería "dart:math" para acceder a los métodos.

*Código:*
```
import 'dart:math';

void main(List<String> args) {
  var n1 = 15;
  var n2 = 7;
  print("Suma : $n1 + $n2 = ${n1 + n2}");
  print("Resta : $n1 - $n2 = ${n1 - n2}");
  print("Multiplicacion : $n1 * $n2 = ${n1 * n2}");
  print("Division : $n1 / $n2 = ${n1 / n2}");
  print("Division entera : $n1 ~/ $n2 = ${n1 ~/ n2}");
  print(pow(5, 3));
  print("Maximo: ${max(5, 3)}");
  print("Minimo: ${min(5, 3)}");
  print("Seno: ${sin(45 * pi / 180)}");
  print("Coseno: ${cos(45 * pi / 180)}");
  print("Raiz cuadrada: ${sqrt(5)}");
// Cada numero es un objeto, teniendo sus propios metodos y propiedades.
}
```
*Impresión en pantalla:*\
![FuncionesMatema](https://user-images.githubusercontent.com/111654273/198156501-d7ee2890-c0e5-4a82-9df9-d1837d2e0feb.png)

## Contadores 
*Código:*
```
void main(List<String> args) {
  var contador = 0;
  contador = contador + 1;
  print(contador);
  contador++;
  print(contador);
  ++contador;
  print(contador);
  contador += 2;
  print(contador);

  var contador2 = 10;
  contador2 = contador2 - 1;
  print(contador2);
  contador2--;
  print(contador2);
  ++contador2;
  print(contador2);
  contador2 -= 2;
  print(contador2);

  var contador3 = 3.0;

  contador3 /= 2;
  // Como da punto decimal, necesita que la variable sea flotante.
  print(contador3);
// Contador = contador / 2
  contador3 *= 2;
  print(contador3);
// Contador = contador * 2
  contador3 %= 2;
  print(contador3);
// Contador = contador % 2
}
```
*Impresión en pantalla:*\
![Contadores](https://user-images.githubusercontent.com/111654273/198156824-a3ea436f-259f-4ff1-acf7-73ec56f58e5b.png)

## Tiempos y final vs const
* Tiempo de codificación: Cuando surgen errores al escribir el código.
* Tiempo de compilación: Si hay error no compila. Antes de generar el .exe.
* Tiempo de ejecución: Tiempo en el que se le asigna los valores al introducirlos por el teclado.

*Código:*
```
import 'dart:io';

void main(List<String> args) {
  const constEntero = 10; // Creada en tiempo de compilacion.
  // const name;
  // name = "nao"; // No se puede declarar despues
  // constEntero = 15; // Las variables constantes no pueden ser modificadas.

  final finalEntero;
  print("El mensaje es: $numero");

  var numero = stdin.readLineSync();
  finalEntero = numero; // Se puede declarar despues
  print("El mensaje es: $numero");
  // Un final que se le puede asignar su valor en su tiempo de ejecucion.
  // finalEntero = 8; //Una vez establecido el valor no se puede cambiar.
  // finalEntero = "Hola";

  print(constEntero);
  print(finalEntero);
}
```
*Impresión en pantalla:*\
![fyc](https://user-images.githubusercontent.com/111654273/198157675-e8b385d1-d805-4c32-84ce-db01c5111f81.png)

## Concatenación de cadenas
Hay que tomar en cuenta que en ningún lenguaje de programación es posible concatenar directamente cadenas con números.
Para simular dicha concatenación usamos el mismo “print”.

*Código:*
```
void main(List<String> args) {
  var cadena = 5;
  print(cadena is String);
  print(cadena.runtimeType);

  var cadena1 = "Hola";
  var cadena2 = "Mundo";
  print(cadena1 + cadena2);
  // Es mejor asi, si llegase a haber un numero no marque error.
  print("$cadena1 $cadena2");

  var nombre = "Nydia";
  var edad = 19;

  // print(nombre + edad); // No puedes concatenar un string con int.
  print("$nombre $edad");
}
```
*Impresión en pantalla:*\
![concatenacion](https://user-images.githubusercontent.com/111654273/198158148-ae23b70d-a549-459d-a34c-2f799104816a.png)

## Sistemas numéricos 
Para hacer conversiones del sistema decimal a cualquier otro sistema usamos el método “.toRadixString()”.

*Código:*
```
void main(List<String> args) {
  // Binario
  var n = 125.toRadixString(2);
  print(n.runtimeType);
  // En realidad es un string, no un numero.
  // Octal
  print(125.toRadixString(8));
  // Hexadecimal
  print(125.toRadixString(16));

  var numero = 0xFFFF;
  print(numero);
  print(numero.runtimeType);
  // Ya es hexadecimal y numericos.
}
```
*Impresión en pantalla:*\
![Sistemas](https://user-images.githubusercontent.com/111654273/198158463-06b2f3c3-afe4-4256-ae96-170b45110de2.png)

## Listas
### Agregar e insertar elementos
*Código:*
```
void main(List<String> args) {
  var miLista = [1, "Hola", 9.8, true];
// Agregar elementos
  miLista.add(3.1416);
  print(miLista);

// Insertar elemento
  miLista.insert(3, "Nydia");
  print(miLista);
}
```
*Impresión en pantalla:*\
[1, Hola, 9.8, true, 3.1416]\
[1, Hola, 9.8, Nydia, true, 3.1416]

### Comportamiento de final con list
Las listas son un caso particular en el que le puedes seguir agregando elementos.

*Código:*
```
void main(List<String> args) {
  final miLista = [1, "Hola", 9.8, true];
  print(miLista);
}

```
*Impresión en pantalla:*\
[1, Hola, 9.8, true, 3.1416]

### Comportamiento del const con list
Al ser una lista declarada como constante ya no es posible seguir agregando más elementos.\
Sin embargo, si intentamos agregarlos no nos marcará ningún error, pero al intentar ejecutarlo nos indicará el error.

*Código:*
```
+void main(List<String> args) {
  const miLista = [1, "Hola", 9.8, true];
  miLista.add(3.1416);
  print(miLista);
}
```
*Impresión en pantalla:*\
![constList](https://user-images.githubusercontent.com/111654273/198159922-1e9f5d64-841d-4d68-843b-6c5de7ef9ab2.png)

### Tipos de listas
Una vez asignado el tipo de lista que es no aceptará valores de ningún tipo que no sea el asignado.

*Código:*
```
import 'dart:io';

void main(List<String> args) {
  var listaInt = [1, 2, 3, 4];
  var listaNum = [1, 2, 3, 4.5];
  var listaObject = [4, "Hola", 3.1416, true];
  List<int> listaIntF = [1, 2, 3, 4];
  // listaInt.add("hola");
  // Define el tipo de lista para no poder ingresar ningun otro tipo de error.
  print(listaInt.runtimeType);
  print(listaNum.runtimeType);
  print(listaObject.runtimeType);
  print(listaIntF.runtimeType);

  List<dynamic> miList = [1, 3.14, "Hola", true];
  print(miList);
  var data = stdin.readLineSync()!;
  miList.add(data);
  print(miList);

  final newList = const [1, 2, 3, 4];
  print(newList);
  // newList.add(5); // No es posible

  for (var i = 0; i < newList.length; i++) {
    stdout.write(
        "$i : ${newList[i]} | "); // No tiene el retorno de carro automatico.
  }
}
```
*Ingreso de datos:*\
0\
*Impresión en pantalla:*\
![Listas](https://user-images.githubusercontent.com/111654273/198169326-3fbae1a5-b94b-4e87-95f9-ae777577c060.png)

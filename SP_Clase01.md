# Primera clase
>Introducción a la programación orientada a objetos como paradigma y exposición de las bases del lenguaje Dart.

## Object Oriented Programming
Paradigma de la programación en la cual su principal característica es la similitud que se tiene con el entorno de la vida real.
El lenguaje padre de dicho paradigma es Java.

## Conceptos básicos

### Clase
Es una especie de cascarón que contiene las funciones y propiedades.
### Instancia 
Es necesaria para hacer uso de la clase en el main. Es una especie de copia de la clase.
### Herencia
Una clase es capaz de adquirir todas las propiedades y funciones de la clase padre y agregar más.
### Polimorfismo 
Capacidad que tienen ciertos lenguajes para hacer que, al enviar el mismo mensaje (o, en otras palabras, invocar al mismo método) desde distintos objetos, cada uno de esos objetos pueda responder a ese mensaje (o a esa invocación) de forma distinta.
### Herencia múltiple 
No todos los lenguajes lo aceptan. Capacidad de una clase de heredar las características de más de una clase.

## Tipos de datos
Dart es un lenguaje de tipado estático, es decir es necesario declarar el tipo de dato de una variable al ser creada.
Una vez declarada, no recibirá otro tipo de dato que no sea el especificado. Ej, Si se declaro una variable como tipo entero, no aceptará valores de tipo flotante.

* Strings
* Numericos
* int
* double
* number => Super clase
* dynamic => Equivalente a python
* bool
* var => Asignacion implicita\
\
*Código:*
```
void main(List<String> args) {
  print("Hola mundo");
  print(2 + 2);
  print('Hola');

  String nombre = 'Nao';
  print(nombre);

  String apellido;
  apellido = 'olmos';
  print(apellido);

  int edad = 19;
  // int edad = 19.5; // No es posible
  print(edad);
  double gravedad = 9.81;
  print(gravedad);

  num numero = 5; // Acepta tanto enteros como flotantes
  print(numero);
  numero = 3.1416;
  print(numero);

  dynamic variable = 5;
  print(variable);
  variable = 'Hola';
  print(variable);
  variable = true;
  print(variable);
  variable = 9.81;
  print(variable);

  bool miBool = true;
  print(!miBool); // Not bool // Imprime false
}
```
*Impresión en pantalla:*\
![TiposDeDatos](https://user-images.githubusercontent.com/111654273/198146674-248246f7-dcd8-4723-89d6-4c91bc09312e.png)

### Ingreso de datos y retorno del tipo de la variable
Usamos la librería “dart:io” para hacer uso de la función “stdin.readLineSync()” usado para el ingreso de datos desde el teclado.\
“is” retorna un valor de tipo booleano, en el caso de la variable sea del tipo indicado retornará un True, caso contrario, retornará False.\
“.runtimeType” retorna el tipo de dato que es la variable.\
“int.parce” nos transforma el tipo de dato de la variable a entero.\


*Código:*
```
import 'dart:io';

void main(List<String> args) {
  print("Dame tu edad: ");
  // int edad = 5; // tiempo de compilacion
  // var edad = 5; // tiempo de ejecucion
  var edad = stdin.readLineSync(); // Retorna String // Tiempo de ejecucion
  print(edad);
  print(edad is int);
  print(edad is double);
  print(edad is bool);
  print(edad is String);
  print(edad.runtimeType); // Imprime el tipo de dato
  int edadInt = int.parse(stdin.readLineSync()!); // el "!" obliga a que lo haga
  print("$edadInt es del tipo ${edadInt.runtimeType}");
}
```
*Ingreso de datos:*\
19\
19\
*Impresión en pantalla:*\
![timeRun](https://user-images.githubusercontent.com/111654273/198152238-0c3860b6-9ce7-4209-9c78-1e39c17140f7.png)



## Funciones
Existen dos tipos de formas de declarar funciones, ya sea de forma explicita o con fat arrow.
Existen dos tipos de funciones, las que retornan valores y las que no retornan nada. En el caso de las funciones que retornan valores, son fáciles de identificar pues son las que en la declaración explicita hacen uso de la palabra reservada “return”, y puede ser asignada o invocada en el main. En el caso de las funciones que no retornan valores, solo se invocan.

*Código:*
```
void main(List<String> args) {
  String nombre = 'Nao';
  String apellido;
  apellido = 'olmos';
  int aActual = 2022;
  int aNac = 2003;
  int edad = calcEdad(aActual, aNac);

  print(
      "Hola $nombre $apellido tienes $edad años."); // Interpolación de cadenas
  print("Hola ${getNombre()} tienes ${aActual - aNac} años");
  print(
      "Hola ${getNombre()} ${getApellido()} tienes ${calcularEdad(2022, 2003)}");

  ejNoRet();
}

// Fat Arrow
int calcularEdad(int aActual, int aNac) => aActual - aNac;
// Explicita
int calcEdad(int aActual, int aNac) {
  return aActual - aNac;
}

String getNombre() => "Naomi";
String getApellido() => "Olmos";

void ejNoRet() {
  print("Esto es un ejempllo de una función que no retorna un valor.");
}
```
*Impresión en pantalla:*\
![Funciones](https://user-images.githubusercontent.com/111654273/198150364-0fde6302-bbcc-42fd-af29-9c69d391f776.png)

## If y el operador ternario

*Código:*
```
void main(List<String> args) {
  int n1 = 3, n2 = 5;

  if (n1 > n2) {
    print("$n1 > $n2");
  } else if (n1 == n2) {
    print("$n1 = $n2");
  } else {
    print("$n1 < $n2");
  }
}
```
*Impresión en pantalla:*\
3 < 5

*Código:*
```
void main(List<String> args) {
  int n1 = 5, n2 = 3;
  int menor;
  final int mayor;

  if (n1 > n2) {
    mayor = n1;
  } else {
    mayor = n2;
  }

  print("El mayor es $mayor");

  // Operador ternario
  n1 < n2 ? menor = n1 : menor = n2;
  print("El menor es $menor");

  // Declarativo funcional
  menor = n1 < n2 ? n1 : n2;

}
```
*Impresión en pantalla:*\
El mayor es 5\
El menor es 3

## For
*Código:*
```
void main(List<String> args) {
  for (var i = 1; i <= 5; i++) {
    print("$i");
  }
  var numeros = [1, 2, 3, 4, 5];
  for (var e in numeros) {
    print("$e");
  }

  numeros.forEach((e) {
    print("$e");
  });
}
```
*Impresión en pantalla:*\
![for](https://user-images.githubusercontent.com/111654273/198153811-62b1aabd-af4a-4483-a98a-d3c78ce71a2f.png)

## Ejercicio
### Planteamiento del problema 
Calculadora que lea dos números del teclado y obtenga suma, resta, multiplicación y división, usando funciones y asignado valores a dos variables.\
*Código:*
```
import 'dart:io';

void main() {
  String op = leerDatos("Indica la operación [+,-,*,/]");
  int num1 = int.parse(leerDatos("Dame el primer número"));
  int num2 = int.parse(leerDatos("Dame el segundo número"));
  print("${calculadora(op, num1, num2)}");
}

String leerDatos(String mensaje) {
  print(mensaje);
  String data = (stdin.readLineSync()!);
  return data;
}

String calculadora(String op, int n1, int n2) {
  if (op == "+") {
    return "$n1 + $n2 = ${suma(n1, n2)}";
  } else if (op == "-") {
    return "$n1 - $n2 = ${resta(n1, n2)}";
  } else if (op == "*") {
    return "$n1 * $n2 = ${multi(n1, n2)}";
  } else if (op == "/") {
    return "$n1 / $n2 = ${divi(n1, n2)}";
  } else {
    return "Operación inválida";
  }
}

int suma(int num1, int num2) => num1 + num2;
int resta(int num1, int num2) => num1 - num2;
int multi(int num1, int num2) => num1 * num2;
int divi(int num1, int num2) => num1 ~/ num2;
```
*Ingreso de datos:*\
*\
2\
16\
*Impresión en pantalla:*\
![ej1](https://user-images.githubusercontent.com/111654273/198154517-d3d3321a-7cd7-4df1-845d-c37a148fb703.png)

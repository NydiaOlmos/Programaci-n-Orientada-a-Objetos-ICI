# Cuarta clase
>Se realizo un mismo ejercicio con 3 versiones diferentes y un segundo ejercicio para demostrar lo aprendido.

## Primer ejercicio
>Una calculadora que sume, reste, multiplique y divida dos números como argumentos.
### Uso de funciones
*Código:*
```
void main(List<String> args) {
  // Invocar
  print(suma(2, 2));
  // Asignacion
  var res = resta(3, 3);
  print(res);
}

// Expresion imperativa
int suma(int num1, int num2) {
  return num1 + num2;
}

// Expresion declarativa
int resta(int num1, int num2) => num1 - num2;

int multi(num1, num2) => num1 * num2;
double div(num1, num2) => num1 / num2;
// Se puede invocar pero no se puede asignar
void mensaje() {
  print("Hola mundo");
}
```
*Impresión en pantalla:*\
4\
0

### Uso de clases, versión valores establecidos
*Código:*
```
void main(List<String> args) {
  // Instancia de la calse calculadora, asi como una copia
  Calculadora miCa = new Calculadora();
  // var n1, n2;
  // n1 = 5;
  // n2 = 10;

  miCa.n1 = 5;
  miCa.n2 = 10;

  // var res = miCa.suma(n1, n2);
  // print("$n1 + $n2 = $res");
  print("${miCa.n1} + ${miCa.n2} = ${miCa.suma(miCa.n1, miCa.n2)}");
  print("${miCa.n1} - ${miCa.n2} = ${miCa.resta(miCa.n1, miCa.n2)}");
  print("${miCa.n1} * ${miCa.n2} = ${miCa.multi(miCa.n1, miCa.n2)}");
  print("${miCa.n1} / ${miCa.n2} = ${miCa.div(miCa.n1, miCa.n2)}");
}

class Calculadora {
  int n1 = 0;
  int n2 = 0;
  int resta(int num1, int num2) => num1 - num2;
  int suma(int num1, int num2) => num1 + num2;
  int multi(num1, num2) => num1 * num2;
  double div(num1, num2) => num1 / num2;
}
```
*Impresión en pantalla:*\
![c4ej1](https://user-images.githubusercontent.com/111654273/198174505-4b3383de-c87f-4938-afff-72d08a9ed4e6.png)
### Ingreso de datos mediante los argumentos del main
*Código:*
```
void main(List<String> args) {
  print(args);
  // for común
  for (var i = 0; i < args.length; i++) {
    print(args[i].runtimeType);
  }
  // for each version extensa
  args.forEach((element) {
    print(element.runtimeType);
  });
  // for each versión reducida
  args.forEach((element) => print(element.runtimeType));
}
```
*Impresión en pantalla:*\
[5, 4, 2]\
String\
String\
String\
String\
String\
String\
String\
String\
String

### Ejercicio con clases e implementación de los argumentos del main
*Código:*
```
void main(List<String> args) {
  Calculadora calc = new Calculadora();
  if (args.length == 3) {
    int n1 = calc.n1 = int.parse(args[0]);
    int n2 = calc.n2 = int.parse(args[1]);
    String op = args[2];
    calc.calcular(n1, n2, op);
  } else {
    print("Error de argumentos.");
    print("Formato: dart nomArch.dart num1 num2 operacion");
  }
}

class Calculadora {
  int n1 = 0;
  int n2 = 0;
  int resta(int num1, int num2) => num1 - num2;
  int suma(int num1, int num2) => num1 + num2;
  int multi(num1, num2) => num1 * num2;
  double div(num1, num2) => num1 / num2;

  void calcular(int a, int b, String op) {
    switch (op) {
      case '+':
        int res = suma(a, b);
        print("$a $op $b = $res");
        break;
      case '-':
        int res = resta(a, b);
        print("$a $op $b = $res");
        break;
      case '*':
        int res = multi(a, b);
        print("$a $op $b = $res");
        break;
      case '/':
        double res = div(a, b);
        print("$a $op $b = $res");
        break;
      default:
        print("Operacion no reconocida");
        break;
    }
  }
}
```
*Impresión en pantalla:*\
![Terminal](https://user-images.githubusercontent.com/111654273/198175311-34c7778d-9455-46f0-a393-ff81cf294adf.png)

## Segundo ejercicio
>Una clase que la edad de la persona, reciba el nombre(s), apellidos y los acomode de paterno, materno, nombres.

*Código:*
```
void main(List<String> args) {
  Personita p = new Personita();
  p.nom1 = 'Nydia';
  p.nom2 = 'Naomi';
  p.aPaterno = 'Olmos';
  p.aMaterno = 'Romero';
  p.aNac = 2003;
  // print('Hola ${p.name('Nydia', 'Naomi', "Olmos", "Romero")} tienes ${p.edad(2003)}');
  print(
      "Hola ${p.name(p.nom1, p.nom2, p.aPaterno, p.aMaterno)} tienes ${p.edad(p.aNac)}");
}

class Personita {
  String nom1 = "";
  String nom2 = "";
  String aPaterno = "";
  String aMaterno = "";
  int aNac = 0;
  int edad(int aNac) => 2022 - aNac;
  String name(String nom1, String nom2, String aPater, String aMater) =>
      "$aPater $aMater $nom1 $nom2";
}
```
*Impresión en pantalla:*\
Hola Olmos Romero Nydia Naomi tienes 19

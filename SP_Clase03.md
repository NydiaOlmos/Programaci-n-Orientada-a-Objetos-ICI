# Tercera clase
>Clases, encapsulamientos, propiedades, métodos, setters, getters e instancias.

## Clases
Pueden ponerse ya sea arriba o abajo del main.\
Al crear una clase el nombre de la misma deberá ser mayúscula, esto para poderlas diferenciar de las variables.\
El main mismo es una clase.
### Propiedades
Un dato no puede ser nulo.\
Null ni siquiera tiene el "rollo".\
Los null puede provocar efectos secundarios.\
Con el signo de interrogación permite que sean nulo.
### Métodos
Igual que una función.\
Va dentro de la misma clase.

*Código:*
```
void main(List<String> args) {
  // Usuario uno es una instancias de la clase User.
  User usuario1 = User();
  // var usuario2 = User();
  // Se puede asignar, pero no se debe hacer.
  usuario1.nombre = "Nydia";
  usuario1.edad = 19;
  //Para acceder a las propiedasdes usamos "clase.propiedad"
  // print(usuario1.nombre);
  // print(usuario2.edad);
  usuario1.reporte();
  // Un método de nuestra clase.
}

class Sin {
  // Clase sin propiedades ni métodos.
}

class User {
  // Propiedades
  String? nombre;
  int? edad;
  // Métodos.
  void reporte() {
    print(nombre);
    // print(usuario1.edad);//Ya no es necesario llamar a la instancia, solo a la propiedad.
    print(edad);
  }
}
```
*Impresión en pantalla:*\
Nydia\
19
## Ejercicio
### Planteamiento del problema
Hacer una clase llamada estudiante con propiedades el nombre la carrera, el semestre y el número de cuenta.

*Código:*
```
void main(List<String> args) {
  var alumno = Estudiante();

  alumno.carrera = "ICI";
  alumno.noCuenta = "20184561";
  alumno.semestre = 3;

  alumno.reporteChido();
}

class Estudiante {
  // String es el único que se incicializa con mayúscula.
  // La primera letra de las variables debe ir en minúsculas.
  String? carrera;
  int? semestre;
  String? noCuenta;

  void reporteChido() {
    print("Carrera:            $carrera");
    print("Semestre:           $semestre");
    print("Número de cuenta:   $noCuenta");
  }
}
```
*Impresión en pantalla:*\
![ejC3](https://user-images.githubusercontent.com/111654273/198171566-794c5534-7c51-4aa7-8020-eba660e09335.png)

## Encapsulamiento
 "No puedes acceder a los órganos internos de una persona sin antes cortarla."\
Ocultar los atributos de la clase.\
Hacerlos locales dentro de la clase.\
Hace uso del símbolo "_".\
Privadas, no se pueden usar fuera de la clase.

*Código:*
```
class User {
  String? _nombre;
  int? _edad;

  void reporte() {
    print(_nombre);
    print(_edad);
  }
}

void main(List<String> args) {
  var usuario1 = User();
  // El compilador no verifica si es privada o no.
  // "El hecho que funcione no significa que este bien."
  usuario1._nombre = "Nydia";
  usuario1._edad = 19;
  usuario1.reporte();
}
```
*Impresión en pantalla:*\
Nydia\
19

## Setters y Getters
* Getter = establece valores.  Leer una propiedad.
* Setters = método para asignar valores.
Setter es por variable o por propiedad. Va dentro de la clase.\
Es una práctica común ponerle el mismo nombre al setter y la propiedad.\
Puedes no poner el void al inicio del setter.

*Código:*
```
void main(List<String> args) {
  User usuario1 = User();
  usuario1.nombre = "Nydia";
  usuario1.edad = 19;
  print(usuario1.nombre);
  print(usuario1.edad);
}

class User {
  String? _nombre;
  int? _edad;

  void set nombre(String nombre) {
    _nombre = nombre;
  }

  void set edad(int edad) {
    _edad = edad;
  }

  String get nombre {
    // Es necesario el "!" para obligarlo a retornar null.
    return _nombre!;
  }

  int get edad {
    return _edad!;
  }

  void reporte() {
    print(_nombre);
    print(_edad);
  }
}
```
*Impresión en pantalla:*\
Nydia\
19

### Recorte de funciones
*Código:*
```
void main(List<String> args) {
  User usuario1 = User();
  usuario1.nombre = "Nydia";
  usuario1.edad = 19;
  print(usuario1.nombre);
  print(usuario1.edad);
}

class User {
  String? _nombre;
  int? _edad;

  set nombre(String nombre) => _nombre = nombre;
  String get nombre => _nombre!;
  void set edad(int edad) => _edad = edad;
  int get edad => _edad!;

  void reporte() {
    print(_nombre);
    print(_edad);
  }
}
```
*Impresión en pantalla:*\
Nydia\
19

## Scope y diferencia entre funciones
Scope o ámbito se refiere al lugar en el que la variable es conocida, alcanzable y utilizable.

*Código:*
```
int x = 25;
void main(List<String> args) {
  var x = 5;
  void showNumber() {
    print(x);
    var y = 10;
    print(y);
  }

  // print(y); // No se puede por que solo existe en showNumber.
// Scope de variables o ámbito
  showNumber();
  showX();
  showX1();
}

// Funciones tradicionales.
void showX() {
  print(x);
}

// Funciones fat arrow, arrow
void showX1() => print(x);
```
*Impresión en pantalla:*\
5\
10\
25\
25

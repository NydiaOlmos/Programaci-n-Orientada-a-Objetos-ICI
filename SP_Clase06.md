# Sexta clase
>Ejercicio de herencia y herencia multiple
## Planteamiento del problema
Crear una clase "animal" con dos propiedades y un métodos

*Código:*
```
void main(List<String> args) {
  Animal a = new Animal.data("gato", "felino");
  Perro firulais = Perro("chihuahua");
  Ave pajaro = new Ave();
  Mounsturo moun = new Mounsturo("Si");

  a.caminar();
  firulais.especie = "canino";
  pajaro.volar();
  firulais.caminar();
  moun.nombre = "Pablo";
  moun.escupir(1);
  moun.volar();
}

class Animal {
  String _nombre = "";
  String _especie = "";

  set nombre(String nombre) => _nombre = nombre;
  set especie(String especie) => _especie = especie;

  String get nombre => _nombre;
  String get especie => _especie;

  void caminar() {
    print("Animal caminando");
  }

  Animal();
  Animal.data(this._nombre, this._especie);
}

// Hereda las propiedades y métodos de la clase padre.
class Perro extends Animal {
  String _raza = "";

  set raza(String raza) => _raza = raza;

  String get raza => _raza;

  void ladrar() {
    print("Ladra");
  }

  void caminar() {
    super.caminar(); // Accede al método padre
  }

  Perro(this._raza);
}

class Ave {
  String _color = "";

  set color(String color) => _color;

  String get colot => _color;

  void volar() {
    print("Vuela :D");
  }

  // Ave();
  // Ave.data(this._color);
  // No permite los constructores con el with
}

// Hereda las propiedades y métodos de la clase Animal y Ave al mismo tiempo.
class Mounsturo extends Animal with Ave {
  String _garras = "";

  set garras(String garras) => _garras;

  String get garras => _garras;

  void escupir(int op) {
    if (op == 1) {
      print("Escupe fuego.");
    } else {
      print("No escupe fuego.");
    }
  }

  Mounsturo(this._garras);
}
```
*Impresión en pantalla:*\
![C6](https://user-images.githubusercontent.com/111654273/198181329-3f41c0aa-7f24-41d3-b52d-6860ef753387.png)
    

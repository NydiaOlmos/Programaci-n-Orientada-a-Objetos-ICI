# Quinta clase
>Simulacro de Examen Práctico y explicación de los constructores.

## Constructores.
* Inicializa la instancia de la clase con argumentos predefinidos.
* Es un método.
* Es obligatorio que tenga el mismo nombre de la clase.

*Código:*
```
void main(List<String> args) {
  Vehiculo vm = Vehiculo.marca("Toyota");
  Vehiculo v = new Vehiculo(4, "Azul", "Fit", "Honda");
  // var v = Vehiculo();
  // var v = new Vehiculo();

  // Uso de setters
  // Ya tiene los valores predefinidos, no es necesario volverlo a poner.
  // v.noLlantas = 4;
  // v.color = 'Azul';
  // v.marca = 'Honda';
  // v.modelo = 'Fit';

  vm.showVehiculo(vm);
  showVehiculo(vm);

  v.arrancar();
  v.correr();
  v.frenar();
  print("");
  showVehiculo(v);
}

class Vehiculo {
//Propiedades
  int _noLlantas = 0;
  String _color = "";
  String _modelo = "";
  String _marca = "";

// Metodos
  // Setters
  set noLlantas(int noLlantas) => _noLlantas = noLlantas;
  set color(String color) => _color = color;
  set modelo(String modelo) => _modelo = modelo;
  set marca(String marca) => _marca = marca;

  // Getters
  int get noLlantas => _noLlantas;
  String get color => _color;
  String get modelo => _modelo;
  String get marca => _marca;

  // Resto de metodos
  void arrancar() {
    print("Arranca");
  }

  void correr() {
    print("Correr");
  }

  void frenar() {
    print("Frenar");
  }

  void showVehiculo(Vehiculo micarro) {
    print("Marca   : ${_marca}");
    print("Modelo  : ${_modelo}");
    print("Color   : ${_color}");
    print("Llantas : ${_noLlantas}");
  }

// Constructor

  // Vehiculo(int numLlantas, String color, String modelo, String marca) {
  //   this._noLlantas = numLlantas;
  //   this._color = color;
  //   this._modelo = modelo;
  //   this._marca = marca;
  // }

  Vehiculo(this._noLlantas, this._color, this._modelo, this._marca);
  Vehiculo.marca(this._marca);
}

void showVehiculo(Vehiculo micarro) {
  // Uso de getters
  print("Marca   : ${micarro.marca}");
  print("Modelo  : ${micarro.modelo}");
  print("Color   : ${micarro.color}");
  print("Llantas : ${micarro.noLlantas}");
}
```
*Impresión en pantalla:*\
![c5](https://user-images.githubusercontent.com/111654273/198176431-c53a4b15-9877-4527-9d8a-5fe12657e184.png)

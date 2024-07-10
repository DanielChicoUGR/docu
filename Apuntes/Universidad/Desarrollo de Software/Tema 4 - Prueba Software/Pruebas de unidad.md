Una **unidad** puede definirse como un trozo de código con un propósito especifico. Por ejemplo, una función o un procedimiento, y en OO, un método o toda una clase

Las pruebas de unidad pretenden detectar ==errores en la lógica interna, probando caminos de control o en sus estructuras==. Son ==difíciles de mantener,== pues al probar el código, cada vez que este se cambia, hay que cambiar el código de la prueba. Suelen ser consideradas [[Prueba de caja blanca|pruebas de caja blanca]], pero también pueden ser consideradas de [[Prueba de caja negra|caja negra]] si probamos la interfaz de la unidad

Para hacer las pruebas de unidad a menudo hay que utilizar *dobles de prueba*, elementos que se hacen pasar por los colaboradores reales de la unidad a probar pero que, en realidad, no lo son: **[[Arnés de prueba]]**

**Ejemplo de prueba de unidad en Dart**
```dart
class Medallero {
	static Medallero _instance = null;
	int _totalPremios = 0;
	
	static Medallero getInstance() {
		return (_instance == null) ? new Medallero() : _instance;
	}
	
	void addPremio () {
		if (_totalPremios < 4)
			_totalPremios++;
		else
			resetPremios();
	}
	
	void resetPremios () => _totalPremios =0;
	int get totalPremios => _totalPremios ;
	
}
```

```dart
import 'package:test/test.dart';
import 'package:flutter_taller_vs/medallero.dart';

void main() {
	group('Medallero', () {
		test('value should start at 0', () {
			final medallero = Medallero.getInstance();
			expect(medallero.totalPremios, 0);
		});
		test('value should be incremented', () {
			final medallero = Medallero.getInstance();
			medallero.addPremio();
			expect(medallero.totalPremios, 1);
		});
		test('value should be resent', () {
			final medallero = Medallero.getInstance();
			medallero.resetPremios();
			expect(medallero.totalPremios, 0);
		});
	});
}
```
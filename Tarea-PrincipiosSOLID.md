				Principios S.O.L.I.D

Son cinco principios fundamentales, uno por cada letra, que hablan del diseño orientado a
objetos en términos de la gestión de dependencias. Las dependencias entre unas clases y 
otras son las que hacen al código más frágil o más robusto y reutilizable. El problema con 
el modelado tradicional es que no se ocupa en profundidad de la gestión de dependencias 
entre clases sino de la conceptualización.


		*Single Responsibility Principle (SRP)

El principio que da origen a la S de S.O.L.I.D es el de una única responsabilidad y dice 
que cada clase debe ocuparse de un solo menester. Visto de otro modo, R. Martin dice que 
cada clase debería tener un único motivo para ser modificada.
Si estamos delante de una clase que se podría ver obligada a cambiar ante una modificación 
en la base de datos y a la vez, ante un cambio en el proceso de negocio, podemos afirmar 
que dicha clase tiene más de una responsabilidad o más de un motivo para cambiar, por poner un ejemplo.
Se aplica tanto a la clase como a cada uno de sus métodos, con lo que cada método también 
debería tener un solo motivo para cambiar. El efecto que produce este principio son clases 
con nombres muy descriptivos y por tanto largos, que tienen menos de cinco métodos, cada 
uno también con nombres que sirven perfectamente de documentación, es decir, de varias 
palabras: CalcularAreaRectangulo y que no contienen más de 15 líneas de código.


		*Open-Closed Principle (OCP)

Una entidad software (una clase, módulo o función) debe estar abierta a extensiones pero 
cerrada a modificaciones. Puesto que el software requiere cambios y que unas entidades 
dependen de otras, las modificaciones en el código de una de ellas puede generar 
indeseables efectos colaterales en cascada.
Para evitarlo, el principio dice que el comportamiento de una entidad debe poder ser 
alterado sin tener que modificar su propio código fuente. ¿Cómo se hace esto?, Hay varias 
técnicas dependiendo del diseño, una podría ser mediante herencia y redefinición de los 
métodos de la clase padre, donde dicha clase padre podría incluso ser abstracta. La otra 
podría ser inyectando dependencias que cumplen el mismo contrato (que tienen la misma 
interfaz) pero que implementan diferente funcionamiento.


		*Liskov Substitution Principle (LSP)

Introducido por Barbara Liskov en 1987, lo que viene diciendo es que si una función recibe
un objeto como parámetro, de tipo X y en su lugar le pasamos otro de tipo Y, que hereda de 
X, dicha función debe proceder correctamente.
Por el propio polimorfismo, los compiladores e intérpretes admiten este paso de parámetros, la cuestión es si la función de verdad está diseñada para hacer lo que debe, aunque quien 
recibe como parámetro no es exactamente X, sino Y.
El principio de sustitución de Liskov está estrechamente relacionado con el anterior en 
cuanto a la extensibilidad de las clases cuando ésta se realiza mediante herencia o 
subtipos. Si una función no cumple el LSP entonces rompe el OCP puesto que para ser capaz 
de funcionar con subtipos (clases hijas) necesita saber demasiado de la clase padre y por 
tanto, modificarla. El diseño por contrato (Design by Contract) es otra forma de llamar al 
LSP.


		*Interface Segregation Principle (ISP)
	
Cuando empleamos el SRP también empleamos el ISP como efecto colateral. El ISP defiende 
que no obliguemos a los clientes a depender de clases o interfaces que no necesitan usar. 
Tal imposición ocurre cuando una clase o interfaz tiene más métodos de los que un cliente 
(otra clase o entidad) necesita para sí mismo. Seguramente sirve a varios objetos cliente 
con responsabilidades diferentes, con lo que debería estar dividida en varias entidades.
En los lenguajes como Java y C# hablamos de interfaces pero en lenguajes interpretados como Python, que no requieren interfaces, hablamos de clases. No sólo es por motivos de robustez del software, sino también por motivos de despliegue. Cuando un cliente depende de una 
interfaz con funcionalidad que no utiliza, se convierte en dependiente de otro cliente y la posibilidad de catástrofe frente a cambios en la interfaz o clase base se multiplica.


		*Dependency Inversión Principle (DIP)

La inversión de dependencias da origen a la conocida inyección de dependencias, una de las 
mejores técnicas para lidiar con las colaboraciones entre clases, produciendo un código 
reutilizable, sobrio y preparado para cambiar sin producir efectos bola de nieve.
DIP explica que un módulo concreto A, no debe depender directamente de otro módulo concreto B, sino de una abstracción de B. Tal abstracción es una interfaz o una clase (que podría ser abstracta) que sirve de base para un conjunto de clases hijas.

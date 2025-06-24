## Anexo - Aplicación de Patrón de Diseño creacional - Factory Method  

Los patrones de diseño creacionales se centran en la creación de objetos. Su propósito principal es abstraer y desacoplar el proceso de instanciación, brindando mecanismos flexibles para crear objetos sin depender de clases concretas. Esto favorece sistemas más escalables, mantenibles y extensibles.

El patrón Factory Method es uno de los más conocidos dentro de este grupo. Permite que una superclase defina un método para crear objetos, pero deja que las subclases decidan qué tipo concreto instanciar.

Este patrón se alinea de manera natural con varios principios SOLID:

- **Principio de Responsabilidad Única (SRP)**  
El patrón creacional separa la lógica de creación de objetos de la lógica de negocio.
- **Principio de Abierto/Cerrado (OCP)**  
Con un patrón creacional podés agregar nuevas clases concretas sin modificar el código cliente.
- **Principio de Inversión de Dependencias (DIP)**  
El código cliente depende de abstracciones, no de clases concretas.

### Propósito y Tipo del Patrón

El **Factory Method** es un patrón de diseño **creacional** cuyo propósito es definir una interfaz para la creación de objetos, pero permite que las subclases decidan qué clase concreta instanciar. Esto permite que el código que utiliza dichos objetos trabaje exclusivamente con abstracciones, lo que reduce el acoplamiento y mejora la extensibilidad del sistema.

Este patrón resulta útil cuando el sistema debe ser independiente de las clases que necesita instanciar o cuando se desea delegar la lógica de creación a otras partes del sistema.


### Motivación

En el sistema de gestión de turnos que hice, el problema central se presentaba al instanciar notificadores concretos (NotificadorEmail, NotificadorSMS) directamente dentro de la clase GestorTurnos. Esto generaba un fuerte acoplamiento y violaba el Principio Abierto/Cerrado (OCP), ya que añadir nuevos tipos de notificación implicaba modificar el código existente en GestorTurnos.

El patrón Método de Fábrica solucionó este problema al desacoplar la creación de notificadores de su uso. Ahora, GestorTurnos interactúa con una abstracción de fábrica (NotificadorFactory) que es responsable de instanciar el notificador adecuado. Esto permitió que el sistema fuera extensible (se pueden añadir nuevos tipos de notificadores sin modificar GestorTurnos) y flexible (la decisión de qué notificador usar puede configurarse externamente). El patrón invirtió la dependencia directa de GestorTurnos a las implementaciones concretas, promoviendo el Principio de Inversión de Dependencias (DIP).

Ahora, GestorTurnos puede recibir una NotificadorFactory (o una de sus implementaciones concretas) y simplemente llamar a su método crearNotificador() para obtener la instancia de INotificadorTurno que necesita, sin tener que preocuparse por la clase específica que se está instanciando. Esto reduce el acoplamiento y facilita la adición de nuevos tipos de notificadores

### Estructura de Clases
![Diagrama aplicando Factory Method](https://github.com/user-attachments/assets/e16e1138-e716-400b-aac4-c0b8f1af88ee)
[Enlace para UMLETINO](https://drive.google.com/file/d/1HsRVAKwJImFCCWVgg691Z8yJYOZVGNwb/view?usp=sharing)


## Anexo - Aplicación de Patrón de Diseño estructural - Decorator

Los patrones estructurales se enfoncan en cómo ensamblar objetos y clases para formar estructuras más grandes y complejas, garantizando al mismo tiempo que estas estructuras mantengan su flexibilidad y eficiencia. Su propósito fundamental es simplificar el diseño al identificar relaciones claras entre las entidades del sistema, lo que conduce a la creación de software más modular, comprensible y escalable. Estos patrones, definidos inicialmente por el "Gang of Four" (GoF), son considerados fundamentales en el desarrollo de software orientado a objetos, promoviendo sistemas más robustos y fáciles de mantener.

El patrón Decorator permite estructurar la lógica de negocio en capas, crear un decorador para cada capa y componer objetos con varias combinaciones de esta lógica, durante el tiempo de ejecución. El código cliente puede tratar a todos estos objetos de la misma forma, ya que todos siguen una interfaz común.

Los patrones de diseño se amalgaman perfectamente con los principios SOLID, siempre manteniendo una linea de orden y posiblidad de escalabilidad sostenible.

- **OCP (Abierto/Cerrado):** permiten extender funcionalidades sin modificar estructuras existentes.  

- **DIP (Inversión de Dependencias):** fomentan el uso de interfaces y abstracciones para desacoplar componentes.  

- **SRP (Responsabilidad Única):** al dividir responsabilidades entre clases conectadas, cada una se enfoca en una sola tarea.  

### Propósito y Tipo del Patrón

El **patrón Decorator** es un diseño estructural que permite agregar funcionalidades extra a un objeto de forma flexible y dinámica, sin modificar su estructura original. En lugar de alterar el código base, lo envolvemos con capas que amplían su comportamiento.

Así, podés sumar nuevas responsabilidades sin romper nada, manteniendo el código limpio, extensible y fiel a los principios SOLID.

### Motivación

El problema que me encontraba antes de aplicar el patrón Decorator era que si yo quería modificar o agregar una funcionalidad nueva por ejemplo validación de reintentos, logs, etc. Necesitaba si o si modificar código de las clases bases lo cual podía llegar a generar problema, con esta aplicación podemos, sumar valor, escalabilidad al programa y además mantenemos la responsabilidad única (SRP) firme. No tocamos nada de código ya hecho sino que generamos una extensión la cual plantea nuevas funcionalidades sin acoplar todo en una clase.

### Estructura de Clases
![Diagrama aplicando Decorator](https://github.com/user-attachments/assets/daf21948-158c-4262-87bf-337f29ff0aa9)
[Enlace para UMLetino](https://drive.google.com/file/d/1nEnsXNp6IOk8XtGr39n6q7_7z-hzkNNX/view?usp=drive_link)

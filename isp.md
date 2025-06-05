## Principio de Segregación de Interfaces (ISP)
**Tipo:** Principio de diseño estructural  
**Propósito:** Evitar que una clase esté obligada a implementar métodos que no necesita.  

En otras palabras: más vale muchas interfaces chicas y bien definidas, que una gigante que nadie quiera implementar entera. Es mejor disponer de pequeñas interfaces pequeñas y bien armadas que una grande la cual puede dar
problemas a futuro.

Cuando una interfaz tiene demasiados métodos, algunas clases que la implementan terminan obligadas a tener comportamientos que no les corresponden. Esto genera código muerto, confusión y acoplamiento innecesario.  

#### Motivación

Una manera explicativa sería, si creamos una interfaz IGestionTurnos con métodos como: 
 - *crearTurno(); modificarTurno(); cancelarTurno(); listarTodosLosTurnos();*

Y la implementamos en Administrador, todo bien. Pero luego también la implementamos en Profesional… y no debería ver o listar todos los turnos.
Entonces empiezan a quedar métodos vacíos.  
Eso rompe el *ISP*, el profesional no debería tener que implementar métodos que no necesita.

**Ejemplo del mundo real:**  
En un sistema de gestión de turnos, el Administrador tiene acceso a toda la cartera de turnos de manera global. Sin embargo, podemos aplicar el Principio de Segregación de Interfaces creando una interfaz específica para el Profesional, que le permita únicamente visualizar y gestionar sus propios turnos.
De esta manera, cada rol implementa únicamente las operaciones que necesita, evitando comportamientos innecesarios y reduciendo el acoplamiento.

#### Estructura de Clases
 *Utilizamos el mismo diagrama que LSP porque ambos principios van de la mano.*
 
![Image](https://github.com/user-attachments/assets/116c84ef-10f3-4fdb-b52d-cd8dd19b20e5)  
![Enlace .ulx para umletino](https://drive.google.com/file/d/17uM2-D3AiBl-PfZ4q2oej-CEpi6hRrMe/view?usp=sharing)

# Abstracción

La abstracción consiste en modelar lo esencial de una entidad del mundo real, dejando de lado los detalles irrelevantes para el contexto actual. 
Se enfoca en qué hace un objeto, no cómo lo hace, permitiendo trabajar con una interfaz clara y desacoplada.

En la práctica, aplicamos abstracción cuando definimos **interfaces o clases abstractas** que representan comportamientos genéricos, y luego dejamos que otras clases los implementen con los detalles concretos.

En relación a los Principios SOLID:
- Refuerza el principio de **Inversión de Dependencias (DIP)**:  
  el sistema depende de abstracciones (`INotificadorTurno`), no de clases concretas.
- Favorece el **OCP** (Abierto/Cerrado): se pueden agregar nuevas implementaciones sin modificar las clases existentes.

También va muy alineado con lo que son los patroñes de diseño, un ejemplo:  
- **Decorator**: 
 Agrega responsabilidades a un objeto de forma dinámica, usando una interfaz común.  
 Todos los decoradores implementan la misma abstracción (INotificadorTurno), lo que permite componer objetos sin alterar su estructura base.  

## Ejemplo en el proyecto
![abstraccionPOO](https://github.com/user-attachments/assets/88a6ece2-968f-43ee-95b6-56d62be10452)

En el sistema, la clase `GestorTurnos` utiliza un objeto que implementa la interfaz `INotificadorTurno` para enviar notificaciones cuando se modifica un turno. `GestorTurnos` nunca sabe y no le interesa saber que tipo de notificado se le inyecta, si es SMS, Email o Whatsapp.

## Ejemplo de código

```java
public class GestorTurnos {
    private INotificadorTurno notificador;

    public void confirmarTurno(Turno turno, Paciente paciente) {
        turno.setEstado(Estado.CONFIRMADO);
        notificador.notificar(turno);
    }
}

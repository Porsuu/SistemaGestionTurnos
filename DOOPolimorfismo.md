# Polimorfismo

El polimorfismo permite que un mismo mensaje (o método) tenga diferentes comportamientos según el objeto que lo reciba. Es decir, diferentes clases pueden responder al mismo mensaje de distintas maneras, siempre que compartan una interfaz común.

**Principio de Abierto/Cerrado (OCP)**  
*"El código debe estar abierto a la extensión, pero cerrado a la modificación."*  

Gracias al polimorfismo, es posible agregar nuevas clases que implementen una interfaz (o hereden de una clase base) sin tener que modificar el código que las usa 

  Ejemplo: agregar NotificadorWhatsapp sin tocar GestorTurnos.

Así mismo también muchos patrones de diseño se apoyan en el polimorfismo para funcionar correctamente.  
Uno de los más representativos es:  

**Factory Method** facilita el uso del polimorfismo desde el momento de la creación, permitiendo que el sistema trabaje con abstracciones y no con implementaciones específicas.  

## Ejemplo en el proyecto

![Polimorfismo](https://github.com/user-attachments/assets/88a6ece2-968f-43ee-95b6-56d62be10452)



## Ejemplo de Código

No importa si el objeto real es NotificadorEmail o NotificadorSMS, el método notificar() se ejecutará acorde a la implementación específica.
Haciendo polimorfismo, mismo mensaje distintos resultados.

```java
public interface INotificadorTurno {
    void notificar(Turno turno);
}

public class NotificadorEmail implements INotificadorTurno {
    public void notificar(Turno turno) {
        System.out.println("Enviando EMAIL: Turno modificado.");
    }
}

public class NotificadorSMS implements INotificadorTurno {
    public void notificar(Turno turno) {
        System.out.println("Enviando SMS: Turno modificado.");
    }
}

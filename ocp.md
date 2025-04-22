## Principio de Abierto/Cerrado (OCP)

**Tipo:** Principio de diseño estructural  
**Propósito:** Que las clases y módulos estén **abiertos a la extensión** pero **cerrados a la modificación**.  

Esto significa que deberíamos poder **agregar nuevas funcionalidades sin tener que modificar el código existente**, lo cual ayuda a evitar errores y mantener el sistema estable.   
Cuando se necesita modificar una clase cada vez que se quiere agregar una nueva funcionalidad (por ejemplo, agregar otro medio de notificación), se corre el riesgo de romper lo que ya funcionaba. Esto viola el OCP.  

### Motivación

En el sistema de turnos, inicialmente la lógica para notificar a los pacientes podía estar directamente en la clase *Turno*, con condiciones del tipo:

Esto permite que con el principio OCP, simplemente definimos una interfaz MedioNotificacion, y cada implementación se encarga de su propio método enviar. Entonces, Turno o Paciente usan esa interfaz sin saber cuál es la implementación concreta.

### Estructura de Clases

![Image](https://github.com/user-attachments/assets/a1d00961-9815-452e-add0-d0d5315a87fc)
- [Enlace .ufx para umletino](https://drive.google.com/file/d/1OoCOBPsd-w4uSRyRdSlQx6BlZ932yMI2/view?usp=sharing)

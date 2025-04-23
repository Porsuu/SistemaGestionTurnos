## Principio de Abierto/Cerrado (OCP)

**Tipo:** Principio de diseño estructural  
**Propósito:** Que las clases y módulos estén **abiertos a la extensión** pero **cerrados a la modificación**.  

Esto significa que deberíamos poder **agregar nuevas funcionalidades sin tener que modificar el código existente**, lo cual ayuda a evitar errores y mantener el sistema estable.   
Cuando se necesita modificar una clase cada vez que se quiere agregar una nueva funcionalidad (por ejemplo, agregar otro medio de notificación), se corre el riesgo de romper lo que ya funcionaba. Esto viola el OCP.  

### Motivación

El OCP se aplica creando clases concretas que implementan una interfaz común. Esto permite agregar nuevas funcionalidades sin tocar el código ya existente, simplemente conectando nuevas clases a la interfaz.

En nuestro caso, definimos la interfaz NotificarTurno, y luego implementamos distintas clases como NotificacionEmail y NotificacionWhatsApp, cada una con su lógica específica. Así, la clase Turno o Paciente pueden usar la interfaz sin importar qué implementación concreta se está utilizando.

Esto respeta el OCP porque extender el comportamiento (agregar una nueva forma de notificación) no requiere modificar las clases que ya funcionan.  

**Ejemplo del mundo real**

En una clínica, al principio se notificaba a los pacientes solo por teléfono.  
Cuando se empezó a usar WhatsApp, tuvieron que reescribir todo el proceso de aviso.  

Si en cambio desde el principio hubieran tenido un sistema donde cada canal de notificación era un módulo aparte, solo habrían agregado el nuevo canal sin tocar lo anterior.  
### Estructura de Clases

![Image](https://github.com/user-attachments/assets/a1d00961-9815-452e-add0-d0d5315a87fc)
- [Enlace .ufx para umletino](https://drive.google.com/file/d/1OoCOBPsd-w4uSRyRdSlQx6BlZ932yMI2/view?usp=sharing)

## Principio de Inversión de Dependencias (DIP)
**Tipo:** Principio de diseño estructural  
**Propósito:** Las clases de alto nivel no deben depender de clases de bajo nivel, ambas deben depender de abstracciones.  

Y además: las abstracciones no deben depender de los detalles, los detalles deben depender de las abstracciones.

#### Motivación
Cada vez que se necesitaba agregar un nuevo canal de comunicación (por ejemplo, WhatsApp, SMS o Telegram), era necesario modificar la clase Turno o Paciente.  
Eso rompía los principios tanto DIP como OCP, haciendo al sistema rígido y difícil de escalar o testear.  

Se propuso una solución basada en una interfaz MedioNotificacion, la cual es utilizada por la clase Paciente para indicar cómo quiere ser notificado.  
Turno, a su vez, no depende de NotificacionEmail ni de ninguna clase concreta, sino que solamente llama a través de la abstracción que el paciente tenga configurada.  

De esta forma:

  -  Turno y Paciente no dependen de detalles, sino de una abstracción.

  -  Se puede cambiar o extender la lógica de notificación sin modificar las clases principales.

  -  El sistema gana en flexibilidad, mantenimiento y testeo.

**Ejemplo del mundo real:**  
Imaginá un sistema de turnos que quiere avisarte tu cita.  
En lugar de decir: “Te mando un email”, el sistema te pregunta:  

  “¿Cómo querés que te avise?”  

Vos respondés: “Por WhatsApp, por favor.”  
Y el sistema simplemente actúa en consecuencia.  
No necesita saber cómo funciona WhatsApp, ni cambiar su código.  
Sólo usa el canal configurado por vos.  
#### Estructura de Clases 
![Image](https://github.com/user-attachments/assets/00fd2262-de73-4890-a965-3cbfd63ad53e)  
- [Enlace .ulx para Umletino](https://drive.google.com/file/d/1qRA5bqNTvTlJvbIE_-xKg7DoMhgW99z-/view?usp=sharing)

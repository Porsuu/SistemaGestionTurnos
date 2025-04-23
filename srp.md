## Principio de Responsabilidad Única (SRP)

**Propósito y Tipo del Principio SOLID:** 
  - **Tipo:** Principio de diseño estructural  
  - **Propósito:** Asegurar que cada clase tenga **una única razón para cambiar**, es decir, que tenga **una única responsabilidad** clara y definida.  

Cuando una clase tiene más de una responsabilidad, se vuelve frágil y difícil de mantener. Cambios en una funcionalidad pueden romper otras no relacionadas, y el código se vuelve más propenso a errores y más difícil de testear.  

### Motivación    
En el sistema de gestión de turnos, la clase Turno no solo manejaba su propio estado (fecha, paciente, profesional) sino también notificaba al usuario. Eso rompe el SRP, porque son dos responsabilidades distintas: la lógica de negocio del turno y la comunicación con el paciente.

Separar esas responsabilidades en clases distintas.
Ahora, Turno solo se encarga de ser un turno, y la clase NotificarTurno se encarga de enviar la notificación.

Esto permite:

- Modificar la lógica de notificación (por email, WhatsApp, etc.) sin tocar la clase Turno.
- Reutilizar NotificarTurno en otros contextos (como recordatorios).
- Hacer pruebas unitarias más simples y enfocadas.

**Ejemplo del mundo real**  

Un recepcionista que agenda turnos no debería encargarse también de enviar los recordatorios. Si mezcla tareas, se vuelve ineficiente y cualquier cambio en cómo se notifican los pacientes puede afectar la agenda.  

Lo mismo en código: si una clase gestiona turnos y también notifica, está asumiendo dos responsabilidades distintas.  
Separarlas hace que cada parte del sistema sea más clara, más estable y más fácil de mantener.  

### Estructura de Clases
![Image](https://github.com/user-attachments/assets/d88d68dd-d7b5-4eb0-9402-c8896c5dd251)

- [Enlace .ufx para umletino](https://drive.google.com/file/d/153vpvR5Erw028JppD6svFcZ1ri90LWxa/view?usp=sharing)

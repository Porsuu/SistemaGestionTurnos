## Anexo - Aplicación de Patrón de Diseño de Comportamiento - Observer

Los patrones de diseño de comportamiento se enfocan en **cómo interactúan los objetos entre sí**, cómo se comunican y cómo se reparten las responsabilidades. Su objetivo es mejorar la flexibilidad y reutilización del código mediante una mejor organización de la lógica de control.

Estos patrones se relacionan fuertemente con los principios **SOLID**, especialmente:
- **OCP (Abierto/Cerrado):** Permiten extender el comportamiento del sistema sin modificar las clases existentes.
- **SRP (Responsabilidad Única):** Separan claramente las responsabilidades de comunicación y acción entre objetos.
- **DIP (Inversión de Dependencias):** Fomentan la programación orientada a interfaces en lugar de clases concretas.

## Propósito y Tipo del Patrón

El patrón **Observer** es de tipo comportamiento este permite que varios objetos ("observadores") estén al tanto y reaccionen automáticamente cuando otro objeto ("sujeto") cambia su estado.

Este patrón se aplica cuando queremos **notificar a distintos componentes** del sistema de un cambio, sin acoplarlos directamente. Por ejemplo, notificar a diferentes servicios cuando un turno se confirma o se cancela.

## Motivación

En el sistema de gestión de turnos, necesitaba una forma de avisar automáticamente a múltiples componentes cuando un evento importante ocurría (como un turno nuevo, modificación o cancelación).

Antes de aplicar el patrón, cada servicio (como el de logs, notificaciones por email o actualización de agenda) estaba fuertemente acoplado al flujo principal. Esto complicaba la extensión o el reemplazo de esos servicios.

Con el patrón **Observer**:

- Ahora cualquier clase interesada puede suscribirse y escuchar cuando un turno cambia de estado.
- La clase Turno ya no depende de otras clases simplemente ahora avisa "Cambie de estado" a las suscriptores que lo escuchen.
- Se genera un desacople muy grande, escalabilidad y SRP, se nota el cambio de responsabilidad única, cada clase hace lo suyo, GestorTurnos gestiona turnos, Turnos avisa cambios y guarda información concreta para reportes.

Esto mejoró la escalabilidad y permitió aplicar los principios OCP y SRP.

## Estructura de Clases

![Patron Observer](https://github.com/user-attachments/assets/baf33885-d99e-44d5-876d-3d0b844ff804)
[Enlace para UMLetino](https://drive.google.com/file/d/1h48VG2EehJb4qil-BdOj_dYIW0cKe_ps/view?usp=sharing)

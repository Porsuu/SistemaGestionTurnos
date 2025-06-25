## Anexo - Aplicación de Patrón de Diseño de Comportamiento - Observer

Los patrones de diseño de comportamiento se enfocan en **cómo interactúan los objetos entre sí**, cómo se comunican y cómo se reparten las responsabilidades. Su objetivo es mejorar la flexibilidad y reutilización del código mediante una mejor organización de la lógica de control.

Estos patrones se relacionan fuertemente con los principios **SOLID**, especialmente:
- **OCP (Abierto/Cerrado):** Permiten extender el comportamiento del sistema sin modificar las clases existentes.
- **SRP (Responsabilidad Única):** Separan claramente las responsabilidades de comunicación y acción entre objetos.
- **DIP (Inversión de Dependencias):** Fomentan la programación orientada a interfaces en lugar de clases concretas.

### Propósito y Tipo del Patrón

El patrón **Observer** es de tipo comportamiento este permite que varios objetos ("observadores") estén al tanto y reaccionen automáticamente cuando otro objeto ("sujeto") cambia su estado.

Este patrón se aplica cuando queremos **notificar a distintos componentes** del sistema de un cambio, sin acoplarlos directamente. Por ejemplo, notificar a diferentes servicios cuando un turno se confirma o se cancela.

### Motivación

En el sistema de gestión de turnos, necesitaba una forma de avisar automáticamente a múltiples componentes cuando un evento importante ocurría (como un turno nuevo, modificación o cancelación).

Antes de aplicar el patrón, cada servicio (como el de logs, notificaciones por email o actualización de agenda) estaba fuertemente acoplado al flujo principal. Esto complicaba la extensión o el reemplazo de esos servicios.

Con el patrón **Observer**:

- Centralizamos el evento en un **sujeto observable**, como el `GestorTurnos`.
- Cada servicio que debe reaccionar (por ejemplo, `NotificadorEmail`, `Logger`, etc.) se registra como **observador**.
- Cuando se produce un cambio, el sistema notifica automáticamente a todos los observadores, sin necesidad de modificar el código principal.

Esto mejoró la escalabilidad y permitió aplicar los principios OCP y SRP.

### Estructura de Clases

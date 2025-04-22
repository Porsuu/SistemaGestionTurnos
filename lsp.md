## Principio de Sustitución de Liskov (LSP)

**Tipo:**  Principio de diseño estructural  
**Propósito:**   Garantizar que las subclases puedan ser utilizadas como si fueran sus clases padre sin alterar el correcto funcionamiento del sistema.  

En otras palabras, una subclase no debe romper las expectativas del código que trabaja con la superclase. Si una clase Hija hereda de una clase Padre, entonces debería poder reemplazarla sin que el sistema se entere de la diferencia.

#### Motivación
En este caso, distintos actores interactúan con los turnos: administradores y profesionales. Ambos gestionan turnos, pero desde roles diferentes: el administrador gestiona todo el sistema, mientras que el profesional solo gestiona los turnos asignados a él. (Se fue modificando en base a las primeras entregas donde el boceto inicial simplemente denotaba que Ambos actores tenían los mismos alcances, acá marcamos la diferencia.)

Si se tratara a ambos como si fueran intercambiables, usando la misma interfaz o clase base, se rompería el principio de sustitución.
Por ejemplo, si un Profesional pudiera reemplazar a un Administrador en una función del sistema, podría intentar modificar o cancelar turnos que no le corresponden, violando las reglas del negocio y generando comportamientos erróneos.

**Ejemplo del mundo real:**  
Pensá en un hospital.
El director médico puede acceder a toda la agenda, crear nuevos turnos, reasignar médicos, etc.
Un médico clínico, en cambio, solo puede modificar sus propios turnos.
Aunque ambos gestionan turnos, no tienen el mismo alcance ni responsabilidad, por lo tanto no deberían compartir el mismo contrato de comportamiento.

#### Estructura de Clases
![Image](https://github.com/user-attachments/assets/116c84ef-10f3-4fdb-b52d-cd8dd19b20e5)  
![Enlace .ulx para umletino](https://drive.google.com/file/d/17uM2-D3AiBl-PfZ4q2oej-CEpi6hRrMe/view?usp=sharing)

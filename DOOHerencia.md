# Herencia

La herencia es uno de los pilares esenciales de la Programación Orientada a Objetos. Permite que una clase (llamada subclase o clase hija) herede atributos y comportamientos de otra clase (superclase o clase padre), facilitando la reutilización de código y promoviendo una estructura lógica jerárquica.

**Relación con principios SOLID**

- Principio de Responsabilidad Única (SRP) 
Permite **organizar las responsabilidades comunes** en clases generales y delegar especializaciones en subclases, evitando que una sola clase tenga múltiples propósitos.  

- Principio de Sustitución de Liskov (LSP) 
Una subclase debe poder ser utilizada en lugar de su superclase sin alterar el funcionamiento del sistema.  
La herencia bien aplicada garantiza compatibilidad entre clases base y derivadas.  

Ejemplo: `Paciente` y `Profesional` pueden ser tratados como `Usuario`, ya que respetan su estructura y comportamiento.  

**Relación con patrones de diseño**

- Template Method  
Define el paso a paso de un proceso en una clase base, pero deja que algunas partes del proceso puedan ser redefinidas por las subclases.



## Ejemplo en el proyecto

![Herencia](https://github.com/user-attachments/assets/4290d1ab-fe10-47de-855f-891fb0e59bad)

Con herencia, tanto Paciente como Profesional heredan de la clase Usuario, reutilizando su lógica y estructura sin repetir código.
Así, si necesitás modificar algo común (por ejemplo, el método obtenerDatos()), lo hacés en un solo lugar y se aplica a todos los que heredan.


## Ejemplo de código

```java
public abstract class Usuario {
    protected String nombre;
    protected String email;

    public Usuario(String nombre, String email) {
        this.nombre = nombre;
        this.email = email;
    }

    public String obtenerDatos() {
        return "Nombre: " + nombre + " | Email: " + email;
    }
}

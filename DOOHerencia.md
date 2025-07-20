# Herencia

La herencia es uno de los pilares esenciales de la Programación Orientada a Objetos. Permite que una clase (llamada subclase o clase hija) herede atributos y comportamientos de otra clase (superclase o clase padre), facilitando la reutilización de código y promoviendo una estructura lógica jerárquica.



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

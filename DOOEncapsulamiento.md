# Encapsulamiento

El propósito del encapsulamiento es ocultar los detalles internos de una clase y exponer solo lo necesario a través de una interfaz pública bien definida.

En otras palabras, encapsular significa proteger los datos y la lógica interna de un objeto para que no puedan ser accedidos ni modificados directamente desde afuera. Esto permite que el estado del objeto se mantenga coherente y controlado.


## Ejemplo en el proyecto

![Encapsulamiento](https://github.com/user-attachments/assets/4290d1ab-fe10-47de-855f-891fb0e59bad)

En este fragmento del diagrama se observa que la clase abstracta Usuario declara sus atributos como privados (-) y expone un método público obtenerDatos(). Esto es un ejemplo claro de encapsulamiento, ya que se restringe el acceso directo a los datos sensibles (nombre, email, teléfono, etc.) y se los expone solo a través de un método controlado.

Si, por ejemplo, se instancia un objeto de tipo Administrador, y desde otra instancia como Paciente se quisiera acceder a esos datos, no sería posible de forma directa, ya que están encapsulados. Solo se podría acceder a ellos mediante la interfaz pública definida, sin posibilidad de modificarlos desde afuera, preservando así la integridad del objeto.

## Ejemplo de Código
```java
public abstract class Usuario {
    private String nombre;
    private String email;

    public Usuario(String nombre, String email) {
        this.nombre = nombre;
        this.email = email;
    }

    // Método público para acceder de forma controlada
    public String obtenerDatos() {
        return "Nombre: " + nombre + " | Email: " + email;
    }

    // Método privado, inaccesible desde fuera de la clase
    private void cambiarEmail(String nuevoEmail) {
        this.email = nuevoEmail;
    }
}

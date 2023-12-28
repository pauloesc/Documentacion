En Java, el constructor de la clase padre (`ClasePadre` en este caso) puede ser invocado explícitamente por el constructor de una subclase usando la palabra clave `super()` como se mencionó anteriormente. Sin embargo, es importante entender que esta invocación ocurre automáticamente incluso si no lo haces explícitamente.

Cuando creas una instancia de la subclase, el constructor de la subclase se ejecuta. Antes de que el cuerpo del constructor de la subclase se ejecute, automáticamente se invoca el constructor de la clase padre. Esto garantiza que cualquier inicialización necesaria en la clase padre se realice antes de que se realice la inicialización específica de la subclase.

Ejemplo:

```java
public class ClasePadre {
    public ClasePadre() {
        System.out.println("Constructor de ClasePadre");
    }
}

public class Subclase extends ClasePadre {
    public Subclase() {
        // La llamada a super() se inserta automáticamente aquí
        System.out.println("Constructor de Subclase");
    }
}

public class Ejemplo {
    public static void main(String[] args) {
        Subclase subclaseObj = new Subclase();
    }
}
```

En este ejemplo, cuando creas una instancia de `Subclase` (`Subclase subclaseObj = new Subclase();`), se imprimirá primero "Constructor de ClasePadre" y luego "Constructor de Subclase". Esto muestra que el constructor de la clase padre se invoca automáticamente antes del constructor de la subclase.

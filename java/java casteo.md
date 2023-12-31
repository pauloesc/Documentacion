Sí, al hacer un casting como A aa = (A) cc;, la referencia cc (que inicialmente es de tipo C, asumiendo que C es una subclase de A) se está convirtiendo explícitamente a una referencia de tipo A. Sin embargo, debes tener en cuenta que el tipo real del objeto al que apunta cc no cambia; solo la referencia se trata como si fuera de tipo A.

Entonces, cuando llamas a métodos a través de aa, se llaman a los métodos de la clase A si esos métodos están definidos en A (y no están sobreescritos en C). Aunque el objeto real pueda ser de tipo C, el casting solo afecta la vista que tienes de él a través de la referencia aa.

Si los métodos en cuestión están sobreescritos en C, entonces se llamará a la versión de C cuando los invoques a través de aa. La resolución de métodos en Java se basa en el tipo real del objeto en tiempo de ejecución, no en el tipo de la referencia.

```
class A {
    void metodo() {
        System.out.println("Método de A");
    }
}

class C extends A {
    @Override
    void metodo() {
        System.out.println("Método de C");
    }
}

public class Main {
    public static void main(String[] args) {
        C cc = new C();

        // Haciendo casting a tipo A
        A aa = (A) cc;

        // Llamando al método
        aa.metodo();  // Salida: "Método de C" (si el método está sobreescrito en C)
    }
}

```

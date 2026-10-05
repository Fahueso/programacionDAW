# Tabla de multiplicar

```java
import java.util.Scanner; // Importamos la clase Scanner para poder leer datos del teclado

public class TablaMultiplicar {

    public static void main(String[] args) {
        // Creamos un objeto Scanner llamado 'lector' que escucha la entrada estándar (System.in)
        Scanner lector = new Scanner(System.in);

        // Solicitamos al usuario que ingrese el número
        System.out.print("Introduce el número del cual quieres ver la tabla: ");
        
        // Leemos el número entero ingresado por el usuario
        int numero = lector.nextInt();

        System.out.println("\n--- Tabla de multiplicar del " + numero + " ---");

        /* 
            Usamos un bucle 'for' para iterar del 1 al 10.
            - int i = 1: Iniciamos el contador en 1.
            - i <= 10: El bucle continuará mientras 'i' sea menor o igual a 10.
            - i++: Incrementamos el contador de uno en uno en cada vuelta.
        */
        for (int i = 1; i <= 10; i++) {
            // Calculamos el resultado de la multiplicación
            int resultado = numero * i;
            
            // Imprimimos el formato: "Número x i = Resultado"
            System.out.println(numero + " x " + i + " = " + resultado);
        }
        
        System.out.println("---------------------------------------");
    }
}
```

# Las 10 primeras tablas:

```java
public class TodasLasTablas {

    public static void main(String[] args) {
        

        System.out.println("===========================================");
        System.out.println("   IMPRIMIENDO TABLAS DEL 1 AL 10 ");
        System.out.println("===========================================\n");

        /* 
           BUCLE EXTERNO: 
           Controla el número de la tabla actual.
           i empezará en 1 y llegará hasta 10.
        */
        for (int i = 1; i <= 10; i++) {
            
            // Imprimimos un encabezado para separar cada tabla visualmente
            System.out.println("--- Tabla del " + i + " ---");

            /* 
               BUCLE INTERNO: 
               Para cada valor de 'i', este bucle se ejecutará 10 veces.
               j es el multiplicador (1, 2, 3... 10).
            */
            for (int j = 1; j <= 10; j++) {
                // Calculamos el resultado: número de tabla (i) por multiplicador (j)
                int resultado = i * j;
                
                // Imprimimos la línea de la operación
                System.out.println(i + " x " + j + " = " + resultado);
            }

            // Imprimimos una línea en blanco al final de cada tabla para que sea legible
            System.out.println(); 
        }
        
        System.out.println("===========================================");
        System.out.println("            Fin de las tablas             ");
        System.out.println("===========================================");
    }
}
```
# Triángulo estrellas:

```java
import java.util.Scanner; // Importamos Scanner para leer la entrada del usuario

public class TrianguloPersonalizado {

    public static void main(String[] args) {
        // Creamos el objeto Scanner
        Scanner lector = new Scanner(System.in);

        try {
            // Pedimos al usuario que defina la altura del triángulo
            System.out.print("¿Cuántas filas quieres que tenga el triángulo?: ");
            int filas = lector.nextInt();

            System.out.println("\nGenerando triángulo de " + filas + " filas:\n");

            /* 
               BUCLE EXTERNO: Controla las filas.
               Va desde 1 hasta el número que el usuario ingresó.
            */
            for (int i = 1; i <= filas; i++) {
                
                /* 
                   BUCLE INTERNO: Controla las columnas (estrellas).
                   La condición 'j <= i' hace que en la fila 1 haya 1 estrella,
                   en la fila 2 haya 2 estrellas, etc.
                */
                for (int j = 1; j <= i; j++) {
                    // Imprime la estrella y un espacio sin saltar de línea
                    System.out.print("* ");
                }

                // Al terminar el bucle interno, saltamos a la siguiente línea
                System.out.println();
            }

        } catch (Exception e) {
            // Captura errores si el usuario ingresa texto en lugar de un número
            System.out.println("Error: Por favor, ingresa un número entero válido.");
        } finally {
            // Cerramos el scanner para liberar memoria
            lector.close();
        }
    }
}

```

# Diagonal

```java
import java.util.Scanner;

public class TrianguloPersonalizado {

    public static void main(String[] args) {
        Scanner lector = new Scanner(System.in);


        System.out.print("¿Cuántas filas quieres que tenga el triángulo?: ");
        int filas = lector.nextInt();

        System.out.println("\nGenerando diagonal de " + filas + " filas:\n");

        for (int i = 1; i <= filas; i++) {
            
            // El bucle interno sigue yendo hasta 'i'
            for (int j = 1; j <= i; j++) {
                
                /* 
                    AQUÍ ESTÁ EL CAMBIO:
                    Si j es igual a i, significa que hemos llegado 
                    al final de la fila actual. Solo entonces ponemos la estrella.
                */
                if (j == i) {
                    System.out.print("*");
                } else {
                    // Si no es el último (j < i), ponemos espacios
                    // Ponemos dos espacios para compensar el ancho del "* " original
                    System.out.print("  "); 
                }
            }

            System.out.println();
            }


    }
}
``
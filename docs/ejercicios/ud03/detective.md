# Actividad: Detective de Métodos

## Objetivos

- Comprender qué es la modularidad.
- Identificar responsabilidades dentro de un programa.
- Detectar código repetido.
- Diseñar métodos con nombres adecuados.
- Refactorizar un programa monolítico en un programa modular.

---

# Situación

La tienda **GameWorld** necesita una aplicación para gestionar un videojuego.

Un programador novato ha conseguido que el programa funcione, pero ha cometido un error importante: **ha puesto toda la lógica dentro del método `main()`**.

Tu trabajo será actuar como un **detective del código** para descubrir qué partes del programa deberían convertirse en métodos independientes.

---

# Tareas

## Parte 1. Análisis

Lee el programa completo e identifica:

- Las distintas tareas que realiza.
- Las validaciones de datos.
- Los cálculos que aparecen.
- Los fragmentos de código repetidos.

---

## Parte 2. Detectar responsabilidades

Haz una lista de todas las responsabilidades encontradas.

Por ejemplo:

```text
Mostrar menú
Registrar videojuego
...
```

No existe una única respuesta correcta.

---

## Parte 3. Diseñar métodos

Propón un nombre de método para cada responsabilidad detectada.

Ejemplo:

```java
mostrarMenu()
registrarVideojuego()
...
```

---

## Parte 4. Dibujar el árbol de llamadas

Diseña un esquema similar al siguiente:

```text
main()
│
├── mostrarMenu()
├── registrarVideojuego()
├── mostrarVideojuego()
├── cambiarPrecio()
├── aplicarDescuento()
└── ...
```

---

## Parte 5. Refactorización

Transforma el programa para que:

- El método `main()` tenga el menor número posible de líneas.
- Cada método haga una sola tarea.
- No exista código duplicado.

---

# Programa original

## Código del programador novato

```java
import java.util.Scanner;

public class TiendaVideojuegos {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        String titulo = "";
        String plataforma = "";
        String genero = "";
        double precio = 0;
        int stock = 0;

        boolean registrado = false;

        int opcion;

        do {

            System.out.println();
            System.out.println("=================================");
            System.out.println("     TIENDA DE VIDEOJUEGOS");
            System.out.println("=================================");
            System.out.println("1. Registrar videojuego");
            System.out.println("2. Mostrar videojuego");
            System.out.println("3. Cambiar precio");
            System.out.println("4. Aplicar descuento");
            System.out.println("5. Vender unidad");
            System.out.println("6. Reponer stock");
            System.out.println("7. Consultar disponibilidad");
            System.out.println("8. Mostrar valoración");
            System.out.println("9. Mostrar ficha completa");
            System.out.println("10. Salir");
            System.out.print("Seleccione una opción: ");

            opcion = sc.nextInt();
            sc.nextLine();

            if (opcion == 1) {

                System.out.println();
                System.out.println("REGISTRO DE VIDEOJUEGO");

                System.out.print("Título: ");
                titulo = sc.nextLine();

                System.out.print("Plataforma: ");
                plataforma = sc.nextLine();

                System.out.print("Género: ");
                genero = sc.nextLine();

                do {
                    System.out.print("Precio: ");
                    precio = sc.nextDouble();

                    if (precio < 0) {
                        System.out.println("Error. El precio no puede ser negativo.");
                    }

                } while (precio < 0);

                do {
                    System.out.print("Stock inicial: ");
                    stock = sc.nextInt();

                    if (stock < 0) {
                        System.out.println("Error. El stock no puede ser negativo.");
                    }

                } while (stock < 0);

                registrado = true;

                System.out.println();
                System.out.println("Videojuego registrado correctamente.");

            } else if (opcion == 2) {

                System.out.println();

                if (registrado) {

                    System.out.println("DATOS DEL VIDEOJUEGO");
                    System.out.println("Título: " + titulo);
                    System.out.println("Plataforma: " + plataforma);
                    System.out.println("Precio: " + precio + " €");

                } else {

                    System.out.println("No hay videojuego registrado.");
                }

            } else if (opcion == 3) {

                System.out.println();

                if (registrado) {

                    double nuevoPrecio;

                    do {

                        System.out.print("Nuevo precio: ");
                        nuevoPrecio = sc.nextDouble();

                        if (nuevoPrecio < 0) {
                            System.out.println("Error. Precio incorrecto.");
                        }

                    } while (nuevoPrecio < 0);

                    precio = nuevoPrecio;

                    System.out.println("Precio actualizado.");

                } else {

                    System.out.println("No hay videojuego registrado.");
                }

            } else if (opcion == 4) {

                System.out.println();

                if (registrado) {

                    double descuento;

                    do {

                        System.out.print("Introduzca descuento (%): ");
                        descuento = sc.nextDouble();

                        if (descuento < 0 || descuento > 100) {
                            System.out.println("Descuento inválido.");
                        }

                    } while (descuento < 0 || descuento > 100);

                    precio = precio - (precio * descuento / 100);

                    System.out.println("Precio final: " + precio + " €");

                } else {

                    System.out.println("No hay videojuego registrado.");
                }

            } else if (opcion == 5) {

                System.out.println();

                if (registrado) {

                    if (stock > 0) {

                        stock--;

                        System.out.println("Venta realizada.");
                        System.out.println("Stock restante: " + stock);

                    } else {

                        System.out.println("No quedan unidades disponibles.");
                    }

                } else {

                    System.out.println("No hay videojuego registrado.");
                }

            } else if (opcion == 6) {

                System.out.println();

                if (registrado) {

                    int unidades;

                    do {

                        System.out.print("¿Cuántas unidades desea añadir?: ");
                        unidades = sc.nextInt();

                        if (unidades < 0) {
                            System.out.println("Cantidad incorrecta.");
                        }

                    } while (unidades < 0);

                    stock += unidades;

                    System.out.println("Nuevo stock: " + stock);

                } else {

                    System.out.println("No hay videojuego registrado.");
                }

            } else if (opcion == 7) {

                System.out.println();

                if (registrado) {

                    if (stock > 0) {
                        System.out.println("Disponible.");
                    } else {
                        System.out.println("Sin existencias.");
                    }

                } else {

                    System.out.println("No hay videojuego registrado.");
                }

            } else if (opcion == 8) {

                System.out.println();

                if (registrado) {

                    if (precio < 20) {

                        System.out.println("Valoración económica.");

                    } else if (precio < 50) {

                        System.out.println("Valoración media.");

                    } else {

                        System.out.println("Valoración premium.");
                    }

                } else {

                    System.out.println("No hay videojuego registrado.");
                }

            } else if (opcion == 9) {

                System.out.println();

                if (registrado) {

                    System.out.println("FICHA COMPLETA");
                    System.out.println("---------------------------");
                    System.out.println("Título: " + titulo);
                    System.out.println("Plataforma: " + plataforma);
                    System.out.println("Género: " + genero);
                    System.out.println("Precio: " + precio + " €");
                    System.out.println("Stock: " + stock);

                    if (stock > 0) {
                        System.out.println("Disponible: Sí");
                    } else {
                        System.out.println("Disponible: No");
                    }

                    if (precio < 20) {
                        System.out.println("Categoría: Económica");
                    } else if (precio < 50) {
                        System.out.println("Categoría: Media");
                    } else {
                        System.out.println("Categoría: Premium");
                    }

                } else {

                    System.out.println("No hay videojuego registrado.");
                }

            } else if (opcion == 10) {

                System.out.println();
                System.out.println("Gracias por utilizar el sistema.");

            } else {

                System.out.println();
                System.out.println("Opción incorrecta.");

            }

        } while (opcion != 10);

        sc.close();
    }
}
```

# Entrega

Debes entregar:

1. Lista de responsabilidades detectadas.
2. Lista de métodos propuestos.
3. Árbol de llamadas del programa.
4. Versión modularizada del código.


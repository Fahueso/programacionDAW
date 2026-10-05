
# Actividades Entregables — Unidad 2: Programación Estructurada

!!! info "Criterios de Evaluación (RA2, RA3, RA5)"

**Criterios Principales (Evaluación Directa):**

- **RA3. Escribe y depura código, analizando y utilizando las estructuras de control del lenguaje.**
    - **a)** Se ha escrito y probado código que haga uso de estructuras de selección.
    - **b)** Se han utilizado estructuras de repetición.
    - **c)** Se han reconocido las posibilidades de las sentencias de salto.
    - **e)** Se han creado programas ejecutables utilizando diferentes estructuras de control.

- **RA5. Realiza operaciones de entrada y salida de información, utilizando procedimientos específicos del lenguaje y librerías de clases.**
    - **a)** Se ha utilizado la consola para realizar operaciones de entrada y salida de información.
    - **b)** Se han aplicado formatos en la visualización de la información.

- **RA2. Escribe y prueba programas sencillos, reconociendo y aplicando los fundamentos de la programación orientada a objetos.**
    - **c)** Se han instanciado objetos a partir de clases predefinidas.
    - **d)** Se han utilizado métodos y propiedades de los objetos.
    - **e)** Se han escrito llamadas a métodos estáticos.
    - **f)** Se han utilizado parámetros en la llamada a métodos.
    - **g)** Se han incorporado y utilizado librerías de objetos.
    - **h)** Se han utilizado constructores.
    - **i)** Se ha utilizado el entorno integrado de desarrollo en la creación y compilación de programas simples.

**Criterios Secundarios:**

- **RA2.b)** Se han escrito programas simples.
- **RA3.f)** Se han probado y depurado los programas.
- **RA3.g)** Se ha comentado y documentado el código.

---

## Actividad 1: La Cooperativa de Naranjas

La **cooperativa "Casablanca"** necesita un programa para calcular el precio final por kilo de naranja. El precio depende de un **precio inicial** y se ajusta según el **tipo** (A o B) y el **tamaño** (1 o 2):

| Tipo | Tamaño | Ajuste |
|---|---|---|
| A | 1 | +10 céntimos |
| A | 2 | +25 céntimos |
| B | 1 | −5 céntimos |
| B | 2 | −10 céntimos |

El programa solicita el precio inicial, el tipo y el tamaño. Para finalizar, el programa debe calcular el precio final y **redondearlo a dos decimales** utilizando la clase `Math` para asegurar que el precio sea válido para el tique de venta.

!!! tip "Pista"
    - Utiliza `if-else if` o un `switch` anidado para los ajustes.
    - Para el redondeo, recuerda que existen métodos estáticos en la clase `Math` (como `Math.round()`).

??? example "Ejemplo de salida esperada"
    ```
    --- COOPERATIVA CASABLANCA: CALCULADORA DE PRECIOS ---
    Introduce los siguientes datos:
    - Precio inicial del kilo de naranja: 0.30
    - Tipo de naranja (A/B): A
    - Tamaño de naranja (1/2): 2
    --- RESULTADO ---
    El precio final de venta es 0.55 €/kg
    ```

### Entrega Actividad 1
Genera un fichero Java con el nombre `ud2_actividad1_[tu_nombre].java`.

---

## Actividad 2: Análisis de Facturación

Una empresa de desinfectantes necesita analizar sus ventas. Cada factura tiene un **código de artículo**, una **cantidad en litros** y un **precio por litro**.

El programa procesa **5 facturas** (introducidas por teclado) y muestra al final:

1. **Facturación total:** suma de todos los importes.
2. **Litros del Artículo 1:** cantidad total de litros vendidos del artículo con código `1`.
3. **Facturas superiores a 200€:** número de facturas cuyo importe supera los 200€.

!!! tip "Pista"
    Necesitas un bucle que se repita 5 veces. Dentro del bucle, pide los datos de cada factura y actualiza tus variables acumuladoras y contadoras.

??? example "Ejemplo de entrada y salida"
    ```
    --- EJEMPLO DE ENTRADA ---
    - Código: 1, Litros: 30, Precio/L: 4.5
    - Código: 2, Litros: 20, Precio/L: 5.0
    - Código: 1, Litros: 50, Precio/L: 4.5
    - Código: 3, Litros: 10, Precio/L: 5.8
    - Código: 3, Litros: 20, Precio/L: 5.8

    --- RESUMEN DE VENTAS ---
    * Facturación total: 634.00 €
    * Cantidad de litros vendidos del artículo #1: 80
    * Número de facturas de más de 200 €: 1
    ```

### Entrega Actividad 2
Genera un fichero Java con el nombre `ud2_actividad2_[tu_nombre].java`.

---

## Actividad 3: Simulador de Cajero Automático

¡Programa el software de un cajero automático!

**Requisitos:**

1. El cajero dispone de billetes de `500, 200, 100, 50, 20, 10 y 5` euros. Guárdalos en un **array de enteros**.
2. El saldo inicial del usuario es `0`.
3. Al iniciar el programa, el sistema debe generar un **Número de Operación aleatorio** (entre 1000 y 9999) utilizando la clase `Random`.
4. Muestra un **menú repetitivo** con las opciones:
    - Consultar saldo actual.
    - Ingresar dinero.
    - Retirar dinero.
    - Salir.
5. La opción **Retirar dinero** debe:
    - Comprobar si hay saldo suficiente. Si no, mostrar un mensaje de error.
    - Calcular el **menor número posible de billetes** para entregar la cantidad.
    - Mostrar el desglose de billetes entregados.

??? example "Ejemplo de ejecución"
    ```
    ---- MENÚ CAJERO AUTOMÁTICO ----
    Operación Nº: 4582
    1. Consultar saldo
    2. Ingresar dinero
    3. Retirar dinero
    4. Salir
    Elige una opción: 2
    Cantidad a ingresar: 385
    Saldo actual: 385.0 €
    ```

### Entrega Actividad 3
Genera un fichero Java con el nombre `ud2_actividad3_[tu_nombre].java`.

---

## Actividad 4: Gestor de Butacas de Cine

¡Programa el sistema de venta de entradas de un pequeño cine!

**Requisitos:**

1. Crea una **matriz de caracteres de 5×5** para representar la sala.
2. Inicializa todas las butacas con `'L'` (Libre).
3. Muestra un **menú repetitivo** con las opciones:
    1. **Mostrar butacas:** dibuja el estado actual de la sala (`L` = libre, `O` = ocupada).
    2. **Comprar entrada:** pide fila y columna.
        - **Validación:** El programa debe comprobar que la fila y la columna introducidas estén dentro del rango (0-4). Si el usuario introduce un valor incorrecto, el programa debe mostrar un error y **volver a pedir el dato** hasta que sea válido.
        - Si la butaca está libre (`L`): la marca como ocupada (`O`) y confirma la compra.
        - Si ya está ocupada (`O`): muestra "Butaca no disponible".
    3. **Mostrar estadísticas:** butacas libres, ocupadas y total recaudado (5€/entrada).
    4. **Salir.**

??? example "Ejemplo de salida"
    ```
    ---- CINE DAM ----
    1. Mostrar butacas
    2. Comprar entrada
    3. Ver estadísticas
    4. Salir
    Elige una opción: 2
    Introduce la fila (0-4): 8
    Error: Fila fuera de rango. Inténtalo de nuevo.
    Introduce la fila (0-4): 2
    Introduce la columna (0-4): 3
    Compra realizada con éxito.
    ```

### Entrega Actividad 4
Genera un fichero Java con el nombre `ud2_actividad4_[tu_nombre].java`.
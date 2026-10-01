# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting. Herramienta de IA usada: GEMINI

## Ejercicio 2: Zero-shot, one-shot y few-shot

| Tipo      | Aciertos (de 5) | Formato de la respuesta                               | Todas con el mismo formato (Si/No) |
| --------- | --------------- | ----------------------------------------------------- | ---------------------------------- |
| Zero-shot | 5               | Formato libre con viñetas y explicaciones detalladas  | No                                 |
| One-shot  | 5               | Lista numerada imitando un solo ejemplo dado          | Si                                 |
| Few-shot  | 5               | Estricto por línea con estructura "texto -> etiqueta" | Si                                 |

## Ejercicio 3: Chain of Thought

| Pedido      | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
| ----------- | ------------------ | ------------------------- | ---------------- |
| Directo     | 318.6              | No                        | Si               |
| Paso a paso | S/ 318.60          | Si                        | Si               |

Ver el razonamiento _Chain of Thought_ permite auditar y verificar el procedimiento lógico de la IA paso a paso. Gracias a esto, si ocurre algún error en el cálculo, es posible identificar con exactitud en qué punto falló para corregirlo rápidamente

## Ejercicio 4: Role prompting

| Version        | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo                | A quien le sirve mas                      |
| -------------- | ------------------------------ | ------------------------------------ | ----------------------------------------- |
| A. Sin rol     | Técnico estándar               | Código (Python) y viñetas            | Estudiantes independientes o autodidactas |
| B. Rol docente | Sencillo                       | Ejemplos cotidianos (cajas, juegos)  | Principiantes sin experiencia en código   |
| C. Rol senior  | Técnico avanzado               | Código (Java) y conceptos de memoria | Desarrolladores o estudiantes avanzados   |

## Ejercicio 5: Descomposicion

| Paso  | Petición                                                                                                                    | Respuesta generada por la IA                                                                                                                                   |
| :---: | :-------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1** | Identificación de los cinco requisitos principales para el sistema de una tienda pequeña.                                   | Se obtuvo una lista estructurada con las funciones básicas del programa, tales como la gestión de datos y el control de existencias en tiempo real             |
| **2** | Definición de las clases necesarias y sus respectivos tipos de datos con base en el paso anterior.                          | Se generó el diseño conceptual para las clases `Producto`, `Categoria` y `Transaccion`, asignando los tipos de variables correspondientes                      |
| **3** | Construcción del código fuente en Java para la clase `Producto`, incluyendo su constructor y métodos de acceso (get y set). | Se desarrolló el código de la clase `Producto.java`, manteniendo total coherencia con las variables y especificaciones definidas en la etapa previa            |
| **4** | Análisis del código desarrollado para proponer tres opciones de mejora concretas.                                           | Se presentaron tres sugerencias de optimización: validación en los métodos de modificación, mayor precisión en datos monetarios y funciones de ajuste de stock |

- **Comparación con el pedido de una sola vez:** El pedido de una sola vez dio un resultado muy largo y genérico, mientras que el pedido por pasos entregó un diseño de clases y un código ordenados y coherentes entre sí

## Ejercicio 6: Prompt estructurado y autocritica

```text
<rol>Actua como analista de pruebas de software.</rol>
<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto>
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>
<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>

Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
```

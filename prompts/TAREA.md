# Tarea: Mi prompt avanzado

## Tarea elegida

Explicación didáctica y arquitectónica de un ejercicio básico de Programación Orientada a Objetos (POO).

## Version 1: prompt basico

```text
Explícame este ejercicio de programación orientada a objetos en Java.
```

- **Técnica agregada:** Ninguna. Es el estado inicial
- **Por qué se aplicó:** Para poner los cimientos iniciales, ver como cambia en el proceso
- **Qué mejoró en la respuesta:** Proporcionó una explicación genérica del código, pero mezcló conceptos teóricos avanzados que confundirian a un estudiante en sus primeros ciclos

## Version 2

```text
Actúa como un docente de desarrollo de software especializado en metodología de enseñanza. Explica un ejercicio de programación orientada a objetos usando analogías sencillas y cotidianas en lugar de conceptos abstractos.
```

- **Técnica agregada:** _Role Prompting_ (Rol docente) y restricción de lenguaje.
- **Por qué se aplicó:** Contextualizar la perspectiva del modelo para disminuir la complejidad de los objetos y clases.
- **Qué mejoró en la respuesta:** Reemplazó los términos complejos por analogías del mundo real (como moldes y planos), facilitando la comprensión del flujo

## Version 3: prompt final

```text
<rol>Actúa como un docente y mentor de desarrollo de software enfocado en estudiantes de ciclos iniciales.</rol>

<contexto>El estudiante tiene un ejercicio de una clase 'Vehiculo' con atributos (color, marca) y métodos (encender, acelerar), pero no logra entender cómo se relacionan los objetos con las clases en la memoria.</contexto>

<instrucciones>
Divide tu explicación paso a paso (Chain of Thought). Primero, analiza el problema común de confusión y luego desglosa la solución en dos partes: el concepto visual (el diseño) y el código limpio.

Utiliza el siguiente formato de ejemplo para estructurar tu explicación (Few-shot):
Concepto: Una Clase es el plano arquitectónico y el Objeto es la casa construida con ese plano.
Ejemplo: Clase 'Platillo' -> Objeto 'Cebiche'.
</instrucciones>

<formato>Entrega el resultado final estructurado con títulos claros, analogías visuales cotidianas y un bloque de código breve en Java debidamente comentado.</formato>
```

- **Técnica agregada:** _Prompt Estructurado_ (Etiquetas), _Chain of Thought_ y _Few-shot Prompting_.
- **Por qué se aplicó:** Asegurar un orden lógico en la explicación y forzar el uso de estructuras de diseño comprensibles para perfiles técnicos y visuales
- **Qué mejoró en la respuesta:** El modelo separó perfectamente el análisis lógico del código, conectó la abstracción de la programación con el diseño conceptual y entregó un bloque de Java impecable y comentado paso a paso.

## Tecnicas usadas en el prompt final

| Parte del Prompt Final                                     | Técnica Correspondiente             |
| :--------------------------------------------------------- | :---------------------------------- |
| `<rol>Actúa como un docente y mentor...</rol>`             | **Role Prompting**                  |
| `<contexto>El estudiante tiene un ejercicio...</contexto>` | **Contexto del Problema**           |
| `Divide tu explicación paso a paso...`                     | **Chain of Thought**                |
| `Utiliza el siguiente formato de ejemplo...`               | **Few-shot Prompting**              |
| `<rol>`, `<contexto>`, `<instrucciones>`, `<formato>`      | **Prompt Estructurado (Etiquetas)** |

## Evaluacion del resultado

| Qué revisar                                       | Cumple (Sí / No) |
| :------------------------------------------------ | :--------------: |
| ¿El prompt final cuenta con un rol específico?    |        Sí        |
| ¿Se define un formato de respuesta estructurado?  |        Sí        |
| ¿La IA realizó un análisis previo paso a paso?    |        Sí        |
| ¿La explicación evita los tecnicismos abstractos? |        Sí        |

## Por que elegi estas tecnicas

La combinación de Role Prompting, Chain of Thought y Few-shot es ideal para abordar la Programación Orientada a Objetos, un tema que exige conectar el diseño visual con la lógica abstracta. Definir el rol de _Docente/Mentor_ garantiza que la respuesta adopte un enfoque pedagógico, amigable y libre de tecnicismos complejos que puedan abrumar a quien está aprendiendo. El uso de _Chain of Thought_ permite que la IA fdivida el aprendizaje en etapas lógicas, asegurando una transición suave desde la teoría hasta la práctica. Por último, la técnica Few-shot sirvió para estandarizar las analogías cotidianas, logrando una estructura limpia y ordenada que facilita asociar un concepto gráfico con la sintaxis real del código

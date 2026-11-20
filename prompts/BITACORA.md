# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.
Herramienta de IA usada: ChatGPT

## Ejercicio 2: Zero-shot, one-shot y few-shot

| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|-------------------------|------------------------------------|
| Zero-shot | 5 | Libre, con posibles explicaciones | No |
| One-shot | 5 | Lista numerada | No |
| Few-shot | 5 | Texto -> etiqueta | Si |

## Ejercicio 3: Chain of Thought

| Pedido       | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|--------------|--------------------|---------------------------|------------------|
| Directo      | S/ 318.60          | No                        | Si               |
| Paso a paso  | S/ 318.60          | Si                        | Si               |

## Ejercicio 4: Role prompting

| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
|---------|-------------------------------|-----------------------|----------------------|
| A. Sin rol | Sencillo, con algunos términos técnicos | Sí, código JavaScript | Personas con conocimientos básicos |
| B. Rol docente | Sencillo y fácil de entender | Sí, ejemplos, código y comparaciones | Estudiantes principiantes |
| C. Rol senior | Técnico y especializado | Sí, código Java y ejemplos prácticos | Programadores y estudiantes de Java |

## Ejercicio 5: Descomposicion

### Bitácora de trabajo con IA

| Paso | Pedido realizado a la IA | ¿Qué me entregó la IA? |
|------|--------------------------|------------------------|
| 1 | Listar los 5 requisitos principales de un sistema de inventario para una tienda pequeña en Java. | Me entregó los cinco requisitos principales: registro de productos, control de stock, consulta de productos, alertas de stock bajo y generación de reportes. |
| 2 | Diseñar las clases necesarias e indicar sus atributos y tipos de datos. | Me propuso cinco clases: Producto, Inventario, Movimiento, AlertaStock y Reporte, indicando los atributos y sus respectivos tipos de datos. |
| 3 | Escribir el código Java de la clase Producto con atributos, constructor y métodos get y set. | Me entregó el código de la clase Producto con sus seis atributos, un constructor y los métodos get y set para consultar y modificar los datos. |
| 4 | Revisar el código de la clase Producto y proponer tres mejoras concretas. | Me propuso tres mejoras: validar los datos de entrada, mejorar el control del stock y agregar un método para verificar si el stock está por debajo del mínimo. |

### Comparación con un solo pedido

Si hubiera solicitado todo en un solo mensaje, la IA habría generado una respuesta más extensa con todos los elementos juntos. Al dividir la tarea en varios pedidos, pude revisar cada resultado, comprender mejor cada parte del sistema y solicitar mejoras específicas antes de continuar.

## Ejercicio 6: Prompt estructurado y autocritica

### 4. Evaluar

| Qué revisar | Cumple (Si / No) |
|---|---|
| ¿Tiene las 4 columnas pedidas? | Si |
| ¿Incluye el bloqueo después de 3 intentos? | Si |
| ¿Incluye casos con campos vacíos? | Si |
| ¿Indica qué casos agregó en la autocrítica? | Si |
| ¿Hay algún caso repetido o que no tenga sentido? | Si |


### 4. Promt estructurado
```text
<rol>Actua como analista de pruebas de software.</rol>

<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto>

<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>

<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>

Mensaje de autocritica:

Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
```
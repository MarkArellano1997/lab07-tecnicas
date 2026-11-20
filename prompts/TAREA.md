# Tarea: Mi prompt avanzado

## Tarea elegida

Generar casos de prueba para un sistema de inicio de sesión (Login). El sistema utiliza correo y contraseña, y bloquea la cuenta después de 3 intentos fallidos.

## Version 1: prompt básico

**Prompt utilizado:**

```text
Genera 6 casos de prueba para un sistema de inicio de sesión que utiliza correo y contraseña. La cuenta se bloquea después de 3 intentos fallidos.
```

**¿Qué técnica agregué y por qué?**

Ninguna, fue mi punto de partida.

**¿Qué mejoró en la respuesta?**

La IA generó algunos casos de prueba, pero la respuesta no tenía un formato definido y faltaban algunos escenarios.

## Version 2

**Técnicas agregadas:** Role prompting y prompt estructurado.

**Prompt utilizado:**

```text
<rol>
Actúa como analista de pruebas de software.
</rol>

<contexto>
Sistema de inicio de sesión con correo y contraseña.
La cuenta se bloquea después de 3 intentos fallidos.
</contexto>

<tarea>
Genera 6 casos de prueba, incluyendo escenarios positivos y negativos.
</tarea>

<formato>
Presenta una tabla con las columnas:
ID, escenario, datos de entrada y resultado esperado.
</formato>
```

**¿Por qué agregué estas técnicas?**

Para indicar qué función debe cumplir la IA y organizar mejor las instrucciones.

**¿Qué mejoró en la respuesta?**

Los casos de prueba aparecieron más ordenados y con las columnas solicitadas.

## Version 3: prompt final

**Técnicas agregadas:** Few-shot, descomposición y autocrítica.

**Prompt utilizado:**

```text
<rol>
Actúa como analista de pruebas de software.
</rol>

<contexto>
Sistema de inicio de sesión con correo y contraseña.
La cuenta se bloquea después de 3 intentos fallidos.
No se permite ingresar con campos vacíos.
</contexto>

<tarea>
Genera 6 casos de prueba siguiendo estos pasos:
1. Identifica escenarios positivos y negativos.
2. Incluye intentos fallidos y bloqueo de cuenta.
3. Considera los campos vacíos.
4. Organiza los casos en una tabla.
</tarea>

<ejemplo>
ID: CP01
Escenario: Inicio de sesión correcto.
Datos de entrada: Correo y contraseña válidos.
Resultado esperado: Acceso permitido.
</ejemplo>

<formato>
Utiliza una tabla con las columnas:
ID, escenario, datos de entrada y resultado esperado.
</formato>

<autocritica>
Revisa que existan 6 casos, que no se repitan y que incluyan el bloqueo después de 3 intentos fallidos. Corrige cualquier error antes de presentar la respuesta.
</autocritica>
```

**¿Por qué agregué estas técnicas?**

Para darle un ejemplo a la IA, dividir el trabajo en pasos y pedirle que revise su respuesta.

**¿Qué mejoró en la respuesta?**

Los casos fueron más completos y se revisaron los escenarios importantes antes de entregar el resultado.

## Técnicas usadas en el prompt final

| Técnica | Parte del prompt | Función |
|---|---|---|
| Role prompting | `<rol>` | Define el papel de la IA. |
| Prompt estructurado | Etiquetas del prompt | Organiza las instrucciones. |
| Few-shot | `<ejemplo>` | Muestra un ejemplo de respuesta. |
| Descomposición | Pasos de `<tarea>` | Divide el trabajo en partes. |
| Autocrítica | `<autocritica>` | Revisa y corrige la respuesta. |

## Evaluación del resultado

| Criterio | Cumple (Sí / No) |
|---|---|
| Presenta 6 casos de prueba. | Sí |
| Incluye las 4 columnas solicitadas. | Sí |
| Considera escenarios positivos y negativos. | Sí |
| Incluye el bloqueo después de 3 intentos fallidos. | Sí |
| Considera los campos vacíos. | Sí |

## Por qué elegí estas técnicas

Elegí estas técnicas porque me ayudan a obtener respuestas más claras y ordenadas. El rol y la estructura permiten dar mejores instrucciones, few-shot proporciona un ejemplo, la descomposición divide el trabajo y la autocrítica ayuda a revisar los resultados. Considero que son adecuadas para generar casos de prueba de un sistema de Login.
# ✅ Verificación & Validación

En el desarrollo de software, es fundamental distinguir entre **Validación** y **Verificación**, ya que cada una aborda una dimensión distinta del aseguramiento de calidad.

---

## ✅ Validación

La **validación** consiste en asegurarse de que los **requisitos correspondan efectivamente al problema a resolver**. Es decir, busca comprobar que la aplicación **sirve para el propósito con el cual fue solicitada**.

> **¿Estamos resolviendo el problema correcto?**

Este proceso se enfoca en detectar **problemas en la especificación de requisitos** y asegurar que el producto haga lo que se espera de él en la **realidad del usuario**.

### 🛠️ ¿Cómo se puede realizar la validación?

- Contrastando los **requisitos con las necesidades reales** del usuario o cliente.
- A través de **entrevistas, feedback directo o simulaciones de uso**.
- Validando el alcance mediante **escenarios de uso reales y casos de negocio**.
- Preguntando de forma reiterativa: *¿Esto es lo que realmente necesitan?*


---

## ✅ Verificación

La **verificación** consiste en asegurarse de que el **software cumple con los requisitos especificados**. En otras palabras, se trata de confirmar que el producto **corresponde a lo que se definió en su diseño y documentación**.

> **¿Estamos resolviendo correctamente el problema?**

La verificación demuestra que el producto **se está haciendo como se dijo que se iba a hacer**, siguiendo lo acordado previamente en los artefactos del proceso de desarrollo.

### 🧪 ¿Cómo se puede realizar la verificación?

- Contrastando **artefactos entre sí** (por ejemplo, diseño vs implementación, requisitos vs pruebas).
- Ejecutando **pruebas** que permitan comprobar el cumplimiento de cada requisito.

---

## 🧪 Ejemplo: `public int calculateDiscount(int price, String category)`

Esta función calcula un descuento basado en el precio y la categoría de producto. A simple vista, parece directa. Pero si queremos **validar** y **verificar** correctamente esta función, debemos formular una serie de preguntas.

---

### ✅ Validación: ¿Estamos resolviendo el problema correcto?

Asegurarse de tener las respuestas correctas a estas preguntas es parte de la validación del programa. Antes de implementar esta función, deberíamos responder preguntas como:

1. ¿Cuáles son las categorías válidas? ¿"Electrónica", "Alimentos", "Ropa"? ¿Hay otras?
2. ¿Cuál es el porcentaje de descuento para cada categoría? ¿Estas reglas pueden cambiar?
3. ¿Se permiten precios negativos? ¿Qué hacer si el valor es 0?
4. ¿El descuento se aplica sobre el precio neto o incluye impuestos?
5. ¿Qué debe pasar si la categoría es nula o no válida?
6. ¿Hay un tope máximo o mínimo para el descuento?
7. ¿Cómo se comporta el sistema si el precio es muy alto o muy bajo?
8. ¿Este cálculo se debe usar en contexto internacional con otras monedas?

Estas preguntas permiten validar que la lógica que estamos construyendo tenga sentido **para el negocio y el contexto real**.

---

### ✅ Verificación: ¿Estamos resolviendo correctamente el problema?

Es importante tener en cuenta que sería literalmente imposible probar exhaustivamente cada combinación de entrada. Debemos escoger un conjunto verificable. Para verificar el correcto funcionamiento del código, se deben definir casos de prueba específicos:

| ID    | Entrada                                 | Salida esperada | Descripción                                  |
|-------|------------------------------------------|------------------|----------------------------------------------|
| TC01  | `calculateDiscount(10000, "Electrónica")` | `9000`           | 10% de descuento sobre electrónica           |
| TC02  | `calculateDiscount(5000, "Alimentos")`    | `4750`           | 5% de descuento                              |
| TC03  | `calculateDiscount(2000, "Ropa")`         | `1600`           | 20% de descuento                             |
| TC04  | `calculateDiscount(-1000, "Electrónica")` | Error o `0`      | Valor negativo                               |
| TC05  | `calculateDiscount(1000, null)`           | Error o `1000`   | Categoría no válida                          |
| TC06  | `calculateDiscount(0, "Ropa")`            | `0`              | Precio cero                                  |
| TC07  | `calculateDiscount(1000000, "Lujo")`      | `1000000`        | Categoría desconocida (sin descuento)        |
| TC08  | `calculateDiscount(1000, "ropa")`         | Error o `1000`   | Case sensitivity                             |
| TC09  | `calculateDiscount(1000, "")`             | Error o `1000`   | Categoría vacía                              |
| TC10  | `calculateDiscount(999999999, "Electrónica")` | Evaluar comportamiento extremo | Límite superior |

---

Este tipo de análisis ayuda a conectar los conceptos de **verificación y validación** con escenarios reales de desarrollo.




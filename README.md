# ✅ Verificación & Validación

En desarrollo de software, es fundamental distinguir entre **Validación** y **Verificación**, ya que cada una aborda una dimensión distinta del aseguramiento de calidad.

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

### ¿Cómo se puede realizar la verificación?

- Contrastando **artefactos entre sí** (por ejemplo, diseño vs implementación, requisitos vs pruebas).
- Ejecutando **pruebas** que permitan comprobar el cumplimiento de cada requisito.

---

# 🧪 Ejemplo: 
```java
// Ejemplo de función en Java
public int calculateDiscount(int price, String category) {
  // Lógica de ejemplo aquí
}
```
        
     

La función anteiro calcula un descuento basado en el precio y la categoría de producto. A simple vista, parece directa. Pero si queremos **validar** y **verificar** correctamente esta función, debemos formular una serie de preguntas.

---

## ✅ Validación: ¿Estamos resolviendo el problema correcto?

Asegurarse de tener las respuestas correctas a estas preguntas es parte de la validación del programa. Antes de implementar esta función, deberíamos responder preguntas como:

1. ¿Cuáles son las categorías válidas? ¿"Electrónica", "Alimentos", "Ropa"? ¿Hay otras?
2. ¿Cuál es el porcentaje de descuento para cada categoría? ¿Estas reglas pueden cambiar?
3. ¿Se permiten precios negativos? ¿Qué hacer si el valor es 0?
4. ¿El descuento se aplica sobre el precio neto o incluye impuestos?
5. ¿Qué debe pasar si la categoría es nula o no válida?
6. ¿Hay un tope máximo o mínimo para el descuento?
7. ¿Cómo se comporta el sistema si el precio es muy alto o muy bajo?
8. ¿Este cálculo se debe usar en contexto internacional con otras monedas?

Estas preguntas permiten validar que la lógica que estamos construyendo tenga sentido **para el negocio y el contexto**.

---

## ✅ Verificación: ¿Estamos resolviendo correctamente el problema?

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

# 💻 Ejercicios asociados a Validación y Verificación 

### 📅 Primer semestre 2025

**📦 Inventario Bodega**

**Requisito:**
>
>Un emprendedor nos ha solicitado una aplicación sencilla para gestionar su inventario de productos en la bodega de su negocio. Nos ha dicho que, con tanta tecnología, necesita algo práctico y funcional.
>
>Requerimientos:
>
>CRUD de Productos: Permitir a los usuarios agregar, consultar, actualizar y eliminar productos del inventario. Cada producto debe tener un nombre, descripción, cantidad disponible, precio unitario y categoría (por ejemplo, "Electrónica", "Ropa", "Alimentos", etc.).
>Gestión de Stock: Permitir actualizar la cantidad de productos cuando se vendan o se reciban nuevas unidades.
>Filtrado y Búsqueda
>Generación de Reportes: Mostrar un resumen con el total de productos en inventario, el valor total del inventario y los productos agotados.
>Autenticación: Proteger el acceso con un sistema de autenticación por nombre de usuario y contraseña.

📄[[>>Ver detalle caso]](ejercicios/ej_s12025.md)

#### Mejores respuestas
- [Equipo Lorna Mella - Rosario Bregante](https://github.com/lmellan/Tarea_1-INF331)
- [Esteban Castillo - Myckoll Winchester](https://github.com/MyckollWinchester/inf331-tarea1)
- [Giovanni Mealla - Ignacio Alfaro](https://github.com/inf331-alfaro-mealla/ProductGest)

### 📅 Segundo semestre 2024

**📝 Gestión de Tareas**

**Requisito:**
>
> "Un cliente nos ha solicitado una aplicación para gestionar sus tareas, algo muy sencillo nos ha dicho, más en estos tiempos con tanta tecnología":
>
>Gestión de Tareas: Desarrollar un sistema que permita a los usuarios crear, consultar, actualizar y eliminar tareas a través de la línea de comandos. Cada tarea debe tener un título, una descripción, una fecha de vencimiento, y una etiqueta que facilite la organización (por ejemplo, "urgente", "trabajo", "personal", otros).
>
>Filtrado y Búsqueda: Incluir funcionalidades para que los usuarios puedan filtrar y buscar tareas en función de varios criterios, como la fecha de vencimiento, etiquetas o estado de la tarea (pendiente, en progreso, completada).
>
>Gestión de Estados de Tareas: Implementar un sistema de gestión de estados para las tareas que permita a los usuarios marcar una tarea como "en progreso" o "completada". Las tareas completadas pueden ser archivadas y consultadas posteriormente.
>
>Autenticación: Proteger el acceso al sistema con un mecanismo de autenticación mediante un nombre de usuario y contraseña.
>

📄[[>>Ver detalle caso]](ejercicios/ej_s22024.md)

#### Mejores respuestas
- [Equipo Nicolás Olivos - Felipe Brauer](https://github.com/INF331-MiniProjects-20242/Proyecto-Gestionador-Tareas)
- [Pablo Campos - Luis Zegarra](https://github.com/Equipo13-PruebadeSoftware/Tarea1-MyTask)
---

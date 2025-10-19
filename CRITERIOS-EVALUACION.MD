# Rúbrica de Evaluación: Taller de Asincronismo y Flujo de Git

**Nombre del Estudiante:** Mariana Ardila Liscano_
**Calificación Final:** _______ / 100

---

### 1. Flujo de Trabajo y Buenas Prácticas en Git (40 Puntos)

| Criterio | **Sobresaliente (10 Puntos)** | **Notable (7 Puntos)** | **Aprobado (4 Puntos)** | **Insuficiente (0 Puntos)** |
| :--- | :--- | :--- | :--- | :--- |
| **Fork, Clone y Rama** | Realiza el fork, clona el repositorio y crea la rama personal siguiendo **exactamente** la convención de nomenclatura (`PascalCase`). | Realiza el fork y clone correctamente, pero la rama tiene un nombre que no sigue la convención exacta. | Realiza el fork y clone, pero trabaja directamente sobre la rama `main` sin crear una personal. | No realiza el fork o clone correctamente, impidiendo la revisión del trabajo. |
| **Estructura del Proyecto** | Crea la carpeta (`MAYUSCULAS`) y el archivo (`CONSULTA.MD`) con los nombres exactos y en la ubicación correcta. | Crea la carpeta y el archivo, pero con errores menores en la convención de nomenclatura (ej. usa minúsculas). | Crea solo el archivo `CONSULTA.MD` pero no la carpeta contenedora. | No crea la estructura de archivos solicitada. |
| **Calidad de Commits** | Realiza un commit por cada pregunta principal (5-6 commits en total) y los mensajes son descriptivos y claros (ej. `docs: responde pregunta sobre APIs`). | Realiza múltiples commits, pero agrupa más de una pregunta en un solo commit o los mensajes son genéricos (ej. "avance"). | Realiza muy pocos commits (1 o 2 para toda la consulta) o los mensajes no son descriptivos. | Realiza un solo commit con todo el trabajo o no realiza commits intermedios. |
| **Entrega (Pull Request)** | Sube la rama personal y crea un Pull Request al repositorio original, con el título solicitado y apuntando a la rama `main` correctamente. | Crea el Pull Request, pero el título no sigue el formato o está dirigido a una rama incorrecta de su propio fork. | Sube los cambios a su rama pero no logra crear el Pull Request, solo comparte el enlace al repositorio. | No sube los cambios a GitHub o no realiza la entrega. |

---

### 2. Calidad de la Investigación y Contenido Técnico (60 Puntos)

| Criterio | **Sobresaliente (12 Puntos)** | **Notable (8 Puntos)** | **Aprobado (5 Puntos)** | **Insuficiente (0 Puntos)** |
| :--- | :--- | :--- | :--- | :--- |
| **Call Stack y Callbacks** | Explica ambos conceptos con claridad y precisión, usando analogías efectivas y un ejemplo de "Callback Hell" bien analizado. | Explica los conceptos de forma correcta, pero las explicaciones son superficiales o la analogía es poco clara. | Define los conceptos de manera básica, pero confunde detalles o el análisis del "Callback Hell" es deficiente. | Las respuestas son incorrectas, copiadas directamente de una fuente sin análisis o están incompletas. |
| **APIs y Endpoints** | Demuestra una comprensión profunda de los conceptos de API, REST, Endpoint y herramientas como Postman. Explica todo con sus propias palabras. | Describe correctamente los conceptos, pero depende en exceso de definiciones técnicas sin una explicación personal clara. | Define los términos de forma muy básica y puede confundir API con Endpoint. | Las respuestas son incorrectas o no demuestran comprensión de los conceptos. |
| **Códigos de Estado HTTP** | Explica correctamente el propósito de cada familia de códigos de estado y proporciona ejemplos precisos y bien descritos para cada una. | Explica la mayoría de las familias de códigos correctamente, pero puede omitir o confundir el propósito de alguna de ellas. | Menciona los códigos de estado, pero la explicación de lo que representa cada familia es vaga o incorrecta. | La respuesta sobre los códigos de estado es incorrecta, está incompleta o ausente. |
| **Promesas** | Define con exactitud una Promesa y sus estados. Explica con claridad cómo soluciona el "Callback Hell" y el código de simulación es funcional y correcto. | Define correctamente la Promesa, pero la explicación sobre su ventaja es superficial. El código de simulación funciona, pero es confuso. | Define la Promesa de forma básica, pero no explica bien sus estados o ventajas. El código es incompleto o incorrecto. | No define correctamente una Promesa, o el código de simulación no tiene relación con el concepto. |
| **Async/Await** | Explica claramente la relación de `async/await` con las Promesas ("azúcar sintáctico") y reescribe el código anterior de forma impecable usando `try...catch`. | Explica que `async/await` simplifica el código, pero no profundiza en su relación con las Promesas. El código reescrito funciona, pero el manejo de errores es incompleto. | Menciona `async/await` pero no logra explicar su propósito. El código reescrito es incorrecto o no maneja errores. | Las respuestas son incorrectas, no reescribe el código o el código presentado no usa `async/await`. |

---
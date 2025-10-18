# Cuestionario: Asincronismo y Consumo de APIs en JavaScript

*A continuación, responde cada una de las siguientes preguntas. Recuerda hacer un commit por cada pregunta principal que completes.*

### Pregunta 1: El Call Stack

* **1.1.** ¿Qué es el **Call Stack** en JavaScript? Explícalo con una analogía del mundo real que facilite su comprensión.
* **1.2.** ¿Qué significa el famoso error `Maximum call stack size exceeded` y cómo podrías provocarlo intencionalmente con un pequeño y simple fragmento de código? (Incluye el código de ejemplo).

**[ESPACIO PARA TU RESPUESTA 1]**

1.1 El Call Stack es la "pila de control" de JavaScript, que organiza la ejecución de las funciones de forma ordenada: última en entrar, primera en salir (LIFO).

Ejemplo: Se realiza una llamada a un callcentener, durante la llamada, el agente necesita consultar otra información, así que pone tu llamada en espera y hace una nueva (se apila otra función en el Call Stack).

Si en esa segunda llamada necesita hablar con otro departamento, hace otra más (otra función encima de la pila).

Cuando el último departamento da la respuesta, esa llamada se cierra primero.

El agente vuelve a la llamada anterior, la resuelve y la cierra, hasta llegar a tu llamada inicial.

1.2. Ese error aparece cuando el Call Stack se llena demasiado.
En JavaScript pasa cuando una función se llama a sí misma sin nunca terminar (recursión infinita), o cuando las funciones se invocan en un ciclo que nunca se rompe.


function explotar() {
  return explotar(); // la función se llama a sí misma sin condición de parada
}

explotar(); // Llamada inicial


---

### Pregunta 2: Los Callbacks

* **2.1.** ¿Qué es un **"callback"** en JavaScript? Explica con tus propias palabras para qué se utilizaban principalmente en el contexto asíncrono.
* **2.2.** Investiga en internet sobre el término **"Callback Hell"** o **"Pyramid of Doom"**. Pega un ejemplo de código que lo ilustre y explica por qué esa estructura es problemática para la legibilidad y el mantenimiento del código a largo plazo.

**[ESPACIO PARA TU RESPUESTA 2]**

---

### Pregunta 3: El Mundo de las APIs 

* **3.1.** ¿Qué es una **API** ? Explícalo de forma sencilla, como si se lo estuvieras explicando a alguien que no es programador.
* **3.2.** ¿Qué es una **API REST**? Describe brevemente sus características principales o principios.
* **3.3.** ¿Qué es un **Endpoint**? En el contexto de la API de Rick and Morty (`https://rickandmortyapi.com/api/character/2`), ¿qué parte de la URL representa el endpoint y qué información específica esperarías obtener de él?
* **3.4.** ¿Para qué sirve una herramienta como **Postman** o **Thunder Client** (la extensión de VS Code)? Describe su función principal en el desarrollo de software.
* **3.5. Códigos de Estado HTTP:** Investiga y explica qué representa cada una de las siguientes familias de códigos de estado. Para cada familia, menciona al menos un ejemplo de código específico y lo que significa. 🆕
    * **Codigos (100-199):** ¿Cuál es su propósito general?, ¿Qué indican este tipo de respuestas?
    * **Codigos (200-299):** ¿Cuál es su propósito general?, ¿Qué indican este tipo de respuestas?
    * **Codigos (300-399):** ¿Cuál es su propósito general?, ¿Qué indican este tipo de respuestas?
    * **Codigos (400-499):** ¿Cuál es su propósito general?, ¿Qué indican este tipo de respuestas?
    * **Codigos (500-599):** ¿Cuál es su propósito general?, ¿Qué indican este tipo de respuestas?

**[ESPACIO PARA TU RESPUESTA 3]**

---

### Pregunta 4: Las Promesas (La solución elegante)

* **4.1.** ¿Qué es una **Promesa (`Promise`)** en JavaScript? Describe detalladamente sus tres estados posibles: `pending`, `fulfilled` y `rejected`.
* **4.2.** ¿Cómo resuelven las promesas el problema del "Callback Hell"? Explica el papel que juegan los métodos `.then()`, `.catch()` y `.finally()` en el manejo de una promesa.

**[ESPACIO PARA TU RESPUESTA 4]**

---

### Pregunta 5: Async/Await (Azúcar sintáctico)

* **5.1.** ¿Qué son las palabras clave **`async`** y **`await`**? ¿Qué problema vienen a solucionar o mejorar en comparación con el uso de `.then()` y `.catch()`?
* **5.2.** A menudo se dice que `async/await` es "azúcar sintáctico" sobre las Promesas. ¿Qué significa esta afirmación? Explícalo con tus palabras.
* **5.3.** Tomando como base el código que creaste para la pregunta 4.3, reescríbelo utilizando la sintaxis `async/await` y un bloque `try...catch` para manejar tanto el caso de éxito como el de error.

**[ESPACIO PARA TU RESPUESTA 5]**
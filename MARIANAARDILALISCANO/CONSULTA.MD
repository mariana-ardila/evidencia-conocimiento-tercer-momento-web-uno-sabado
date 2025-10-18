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
1. Un callback en JavaScript es, en palabras simples, una función que se pasa como argumento a otra función para que esta la ejecute después de terminar su tarea.
En el contexto asíncrono, los callbacks se usaban sobre todo para esperar a que algo terminara sin bloquear el programa.

Por ejemplo:

Hacer una petición a un servidor.
Leer un archivo desde el disco.
Esperar un temporizador.

2. Cuando tienes que hacer muchas tareas una detrás de otra en JavaScript (por ejemplo: primero leer datos, luego guardarlos, luego mostrarlos), y cada tarea usa un callback, terminas con funciones dentro de funciones dentro de funciones....

Eso hace que el código se vea como una pirámide hacia la derecha → difícil de leer, de mantener y de arreglar si algo falla.

// Paso 1: conseguir ingredientes
getIngredients(function(ingredients) {
  // Paso 2: preparar la masa
  makeDough(ingredients, function(dough) {
    // Paso 3: hornear la pizza
    bakePizza(dough, function(pizza) {
      // Paso 4: entregar la pizza
      deliverPizza(pizza, function(result) {
        console.log("🍕 Pizza lista para el cliente:", result);
      });
    });
  });
});

¿Por qué es un problema?

Mucha indentación → el código se va “metiendo hacia la derecha” y se hace feo.
Difícil de leer → si tienes 5, 6 o más pasos, es complicado seguir la lógica.
Difícil de mantener → si quieres cambiar solo el paso 2, debes meterte dentro de varios niveles.
Manejo de errores complicado → hay que poner comprobaciones en cada nivel.


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

3.1 Una API es una puerta de entrada que permite que dos programas distintos hablen entre sí.

Tú haces una petición (como pedir un plato).
La API lleva tu pedido al sistema.
El sistema devuelve una respuesta (como la comida servida).

3.2 Una API REST es una forma organizada y estandarizada de diseñar APIs que permiten crear, leer, actualizar y eliminar recursos a través de internet usando HTTP.

Caracterpisticas: 
HTTP estándar: usa métodos como GET, POST, PUT/PATCH y DELETE.
Recursos con URL: cada entidad (usuarios, productos, etc.) tiene una dirección única.
Stateless: cada petición es independiente, la información viaja en cada solicitud.
Datos en formato común: generalmente JSON.
Interfaz uniforme: reglas claras y consistentes, fáciles de entender y usar.

3.3
Un endpoint es como la dirección exacta (URL) dentro de una API a la que puedes hacer una petición para obtener, crear o modificar un recurso específico.
Es el punto final de acceso a un recurso.

Endpoint:
/character/2
Este es el recurso al que estás accediendo.

id: 2 → es el personaje con ID 2.
name: "Morty Smith".
status: "Alive" → está vivo.
species: "Human".
origin y location: indican dónde nació y dónde está actualmente.
image: URL de la imagen/avatar de Morty.
episode: lista de episodios en los que aparece.


3.4 ¿Qué es Postman o Thunder Client?

Son herramientas para probar y consumir APIs sin necesidad de escribir código desde el inicio.
En vez de armar un programa solo para ver si una API responde, usas estas herramientas para enviar peticiones y ver las respuestas fácilmente.

Función principal en el desarrollo de software

Permiten hacer solicitudes HTTP (GET, POST, PUT, DELETE, etc.) a una API.
Te muestran la respuesta completa: datos en JSON, códigos de estado (200, 404, 500), tiempos de respuesta, encabezados, etc.
Sirven para probar y depurar APIs mientras las estás desarrollando o consumiendo.
Te ayudan a documentar y organizar las diferentes peticiones a una API (colecciones en Postman, perfiles en Thunder Client).

3.5 100–199 → Respuestas informativas

Propósito: Indican que la petición fue recibida y el servidor todavía la está procesando.

El cliente debe esperar más instrucciones antes de continuar.

No suelen usarse mucho en el día a día.

🔹 Ejemplo:

100 Continue → El servidor recibió los encabezados y dice al cliente: “ok, sigue enviando el resto de la petición”.

 200–299 → Respuestas exitosas

Propósito: Significa que la petición del cliente fue entendida, procesada y completada correctamente.

🔹 Ejemplo:

200 OK → Todo salió bien, el servidor devuelve la respuesta solicitada.

201 Created → Algo nuevo fue creado en el servidor (por ejemplo, al registrar un usuario).

300–399 → Redirecciones

 Propósito: Indican que el cliente debe tomar una acción adicional, normalmente seguir otra URL porque el recurso se movió o cambió de lugar.

🔹 Ejemplo:

301 Moved Permanently → El recurso se movió a otra dirección (redirección permanente).

302 Found → Redirección temporal a otro recurso.

 400–499 → Errores del cliente

Propósito: Significa que la petición enviada por el cliente está mal o no puede procesarse.

El error está del lado del usuario o aplicación que hace la petición.

🔹 Ejemplo:

400 Bad Request → La petición tiene errores de sintaxis o parámetros inválidos.

401 Unauthorized → No tienes autorización (falta autenticación).

404 Not Found → El recurso no existe (URL incorrecta o eliminado).

500–599 → Errores del servidor

Propósito: Significa que la petición era correcta, pero el servidor falló al procesarla.

Aquí el problema no es del cliente, sino del servidor.

Ejemplo:

500 Internal Server Error → Error genérico del servidor.

503 Service Unavailable → El servidor está sobrecargado o en mantenimiento.
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
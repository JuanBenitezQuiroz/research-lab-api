## COHORTE 22
                               @JUAN MANUEL BENITEZ QUIROZ

### **1. DIFERENCIA ENTRE HTTP Y HTTPS**

A. **SIGNIFICADO DE CADA SIGLA**
> HTTP: HyperText Transfer Protocol (Protocolo de Transferencia de Hipertexto).

_Es el protocolo que permite la comunicación entre un navegador web y un servidor web para transferir información (páginas, imágenes, etc.)._

> HTTPS: HyperText Transfer Protocol Secure (Protocolo de Transferencia de Hipertexto Seguro).

_Es la versión segura de HTTP, que incorpora cifrado para proteger la información que se transmite._

B. **COMO FUNCIONA EL CIFRADO SSL/TLS**

Hay que entender que técnicamente **HTTPS no es diferente al protocolo de HTTP. La gran diferencia radica en el uso del encriptado TSL/SSL.** HTTPS se basa en la transmisión de dichos certificados, los cuales verifica que el proveedor es quién dice ser. Cuando un usuario se conecta a una página web, manda un certificado SSL, el cual contiene una llave pública necesaria para comenzar una sesión segura. El cliente y el servidor entonces avanzan en un proceso llamado _Handshake_, estableciendo entonces una conexión segura. Esto se utiliza, por ejemplo, cuando uno entra a sitios que requieren confidencialidad y seguridad, como cuentas de bancos, perfiles de cuentas, etc.


El proceso básico es el siguiente:

1. **Conexión inicial (handshake)**: El navegador solicita al servidor un certificado SSL/TLS.

2. **Verificación del certificado**: El navegador comprueba que el certificado sea válido y emitido por una autoridad certificadora confiable.

3. **Intercambio de claves**: Se generan claves de sesión únicas usando criptografía asimétrica (pública/privada).

4. **Cifrado de datos**: Toda la información enviada entre navegador y servidor se cifra con estas claves, evitando que terceros puedan leerla o modificarla.



C. **POR QUÉ HTTPS ES MÁS SEGURO**

**Protección de datos**: Cifra la información sensible, como contraseñas, tarjetas de crédito y datos personales.

**Integridad**: Impide que los datos sean alterados durante la transmisión.

**Autenticidad**: Garantiza que el sitio web es legítimo y no una copia falsa (phishing).

En Resumen:

> HTTPS utiliza SSL/TLS (Secure Sockets Layer / Transport Layer Security) para cifrar la comunicación entre el navegador y el servidor desde un servidor HTTP.

D. **EJEMPLO VISUAL**

Cuando un sitio usa HTTPS, los navegadores muestran un candado verde en la barra de direcciones.

. <Inserte una imagen acá>

E. **QUÉ SUCEDE SI UN SITIO NO USA HTTPS**

1. El navegador puede marcar el sitio como “No seguro”.

2. Los datos pueden ser interceptados o modificados por atacantes _(man-in-the-middle)._

3. Los motores de búsqueda, como Google, pueden despriorizar el sitio en resultados de búsqueda.

---

### **2. PUERTOS DE COMUNICACIÓN**

A. **¿QUÉ ES UN PUERTO EN REDES Y POR QUÉ ES IMPORTANTE PARA HTTP?**

**Un puerto es: _un número que identifica un canal de comunicación dentro de un dispositivo conectado a una red._**

Sirve para que un mismo equipo (por ejemplo, un servidor) pueda manejar múltiples servicios o aplicaciones al mismo tiempo.

👉 En otras palabras, los puertos funcionan como puertas virtuales que permiten que los datos lleguen al servicio correcto.

Por ejemplo:

> El puerto 80 se usa para tráfico web sin cifrar (HTTP).

> El puerto 443 se usa para tráfico web cifrado (HTTPS).

---
### **3. CÓDIGOS DE ESTADO DE RESPUESTA HTTP**

A. **INVESTIGA QUE SON LOS _STATUS CODES_ Y PARA QUÉ SIRVEN.**

Los códigos de estado HTTP son respuestas numéricas que los servidores web envían para indicar el resultado de una solicitud realizada por un cliente como un navegador o una aplicación. 

Se agrupan en cinco clases principales:
- 1xx informativos (100 al 199)
- 2xx éxito (200 al 299)
- 3xx redirección (300 al 399)
- 4xx errores del cliente (400 al 499)
- 5xx errores del servidor (500 al 599)

Están estandarizados por la IETF y descritos en documentos como RFC (_Request for Comments_) 9110, aunque también existen códigos no oficiales usados por determinados servidores y CDNs.

B. **CREA UNA TABLA ORGANIZADA POR _CATEGORÍA_**



| Categoría | Rango | Descripción general | Ejemplo de código |
| --- | --- | --- | --- |
| **1xx – Informativos** | 100–199 | El servidor recibió la solicitud y continúa el proceso. | 100 = Continue |
| **2xx – Éxito** | 200–299 | La solicitud fue procesada correctamente. | 200 = OK |
| **3xx – Redirección** | 300–399 | La solicitud fue redirigida a otro recurso. | 300 = Multiple Choices |
| **4xx – Error del Cliente** | 400–499 | Error causado por la solicitud del cliente. | 404 = Not Found |
| **5xx – Error del Servidor** | 500–599 | El servidor tuvo un problema al procesar la solicitud. | 500 = Internal Server Error |

A continuación, las tablas según codificación y tipo de error en detalle:

> 🟦 **1xx – INFORMATIVOS (100–199)**: _El servidor recibió la solicitud y el cliente debe esperar una respuesta final._

Código | Significado |
|--------|--------------|
| **100** | **Continue** → _El cliente puede seguir enviando la solicitud._ |
| **101** | **Switching Protocols** → _El servidor acepta cambiar de protocolo (por ejemplo, de HTTP a WebSocket)._ |
| **102** | **Processing** → _(WebDAV) El servidor está procesando la solicitud, pero aún no tiene respuesta._ |
| **103** | **Early Hints** → _Envía cabeceras preliminares antes de la respuesta final (para mejorar rendimiento)._ |

> 🟩 **2xx – ÉXITO (200–299)**: _Todo salió bien: el servidor entendió y procesó correctamente la solicitud._

| Código | Significado |
|--------|--------------|
| **200** | **OK** → _Respuesta estándar de éxito._ |
| **201** | **Created** → _Se creó un nuevo recurso (por ejemplo, al registrar un usuario)._ |
| **202** | **Accepted** → _La solicitud fue aceptada pero aún no procesada._ |
| **203** | **Non-Authoritative Information** → _La respuesta puede haber sido modificada por un proxy._ |
| **204** | **No Content** → _La solicitud fue exitosa pero no hay contenido que devolver._ |
| **205** | **Reset Content** → _Pide al cliente que reinicie el formulario o vista._ |
| **206** | **Partial Content** → _Devuelve solo parte del recurso (descargas parciales)._ |
| **207** | **Multi-Status** – _respuestas múltiples o repetidas._ |
| **208** | **Already Reported** – _respuestas múltiples o repetidas. Se utiliza como parte del status 200 y 207._ |
| **226** | **IM Used** → _Devuelve un resultado con transformaciones aplicadas._ |

> 🟨 **3xx – REDIRECCIÓN (300–399)**: _Indican que el cliente debe tomar una acción adicional (como seguir otra URL)._

| Código | Significado |
|--------|--------------|
| **300** | **Multiple Choices** → _Hay varias opciones para el recurso solicitado._ |
| **301** | **Moved Permanently** → _El recurso se movió de forma permanente._ |
| **302** | **Found** → _El recurso está temporalmente en otra ubicación._ |
| **303** | **See Other** → _Redirección a otra URL usando GET._ |
| **304** | **Not Modified** → _El recurso no ha cambiado (usa caché)._ |
| **307** | **Temporary Redirect** → _Redirección temporal (mantiene método HTTP)._ |
| **308** | **Permanent Redirect** → _Redirección permanente (mantiene método HTTP)._ |

> 🟥 **4xx – Error del Cliente (400–499)**: _El cliente envió algo incorrecto o no tiene permisos._

| Código | Significado |
|--------|--------------|
| **400** | **Bad Request** → _Solicitud mal formada._ |
| **401** | **Unauthorized** → _Requiere autenticación._ |
| **403** | **Forbidden** → _Acceso denegado incluso con autenticación._ |
| **404** | **Not Found** → _Recurso no encontrado._ |
| **405** | **Method Not Allowed** → _Método HTTP no permitido (por ejemplo, usar POST donde solo hay GET)._ |
| **406** | **Not Acceptable** → _El servidor no puede devolver el formato solicitado._ |
| **407** | **Proxy Authentication Required** → _Requiere autenticación con el proxy._ |
| **408** | **Request Timeout** → _El cliente tardó demasiado._ |
| **409** | **Conflict** → _Conflicto con el estado actual del recurso._ |
| **410** | **Gone** → _El recurso ya no existe y no volverá._ |
| **411** | **Length Required** → _El servidor se niega a aceptar la solicitud sin un encabezado definido. _|
| **412** | **Precondition Failed** → _Una condición previa en los encabezados  no se cumple._ |
| **413** | **Content Too Large** → _El cuerpo de la solicitud es demasiado grande para procesarlo._ |
| **414** | **URI Too Long** → _La URL (URI) solicitada es demasiado larga para que el servidor la procese._ |
| **415** | **Unsupported Media Type** → _El servidor no soporta el tipo de contenido del cuerpo (por ejemplo, enviar XML donde se espera JSON)._ |
| **416** | **Range Not Satisfiable** → _El cliente pidió una parte del archivo (rango) que no existe o no puede entregarse._ |
| **417** | **Expectation Failed** → _La cabecera "Expect" no puede cumplirse por el servidor._ |
| **418** | **I'm a teapot** → _Código de broma definido en el RFC 2324 (protocolo “Hyper Text Coffee Pot Control Protocol”). No se usa en la práctica._ |
| **419** | **Page Expired** → _Código de estado HTTP no oficial utilizado principalmente por el marco PHP de Laravel para indicar una discrepancia de tokens CSRF._ |
| **420** | **Enhace Your Calm** → _Código utilizado para indicar al cliente que está siendo limitado por realizar demasiadas solicitudes. Se utilizaba en Twitter, sin embargo ha quedado obsoleto y se utiliza el 429._ |
| **421** | **Misdirected Request** → _La solicitud fue enviada a un servidor que no puede responderla (usado con HTTP/2)._ |
| **422** | **Unprocessable Content** → _Antes “Unprocessable Entity”. El servidor entiende la solicitud, pero los datos son inválidos o no procesables (por ejemplo, JSON mal estructurado)._ |
| **423** | **Locked** → _El recurso está bloqueado (usado en WebDAV)._ |
| **424** | **Failed Dependency** → _Una solicitud falló porque dependía de otra que no se pudo completar._ |
| **425** | **Too Early** → _El servidor no quiere procesar la solicitud demasiado pronto (prevención de reenvíos prematuros en HTTP/2)._ |
| **426** | **Upgrade Required** → _El cliente debe usar un protocolo más avanzado (por ejemplo, pasar de HTTP/1.1 a HTTP/2)._ |
| **427** | **No asignado oficialmente** → _Reservado - actualmente no existe un código 427._ |
| **428** | **Precondition Required** → _Indica que el servidor requiere que la solicitud sea condicional, por falta de un encabezado de condición previa necesario como .If-match_ |
| **429** | **Too Many Requests** → _Exceso de solicitudes (rate limit)._ |
| **431** | **Request Header Fields Too Large** → _Cabeceras demasiado grandes._ |
| **444** | **No Response** → _Significa que nginx cerró la conexión sin enviar respuesta al cliente. No es parte del estándar HTTP; solo aparece en los registros del servidor. Se usa para bloquear o ignorar solicitudes maliciosas_ |
| **450** | **Blocked by Windows Parental Controls** → _código de estado HTTP no oficial específico de Microsoft y devuelto por el servidor para indicar que los controles parentales están activados y bloquean el acceso al recurso solicitado_ |
| **451** | **Unavailable For Legal Reasons** → _Bloqueado por motivos legales (ej. censura)._ |
| **495** | **SSL Certificate Error** → _El cliente envió un certificado SSL inválido; la conexión HTTPS falla._ |
| **496** | **SSL Certificate Required** → _El cliente no envió ningún certificado SSL donde se esperaba uno._ |
| **497** | **HTTP Request Sent to HTTPS Port** → _El cliente envió una solicitud HTTP a un puerto configurado para HTTPS._ |
| **498** | **Invalid Token** → _El token de autenticación enviado es inválido o expirado (usado en algunos API)._ |
| **499** | **Client Closed Request** → _El cliente cerró la conexión antes de recibir la respuesta del servidor._ |

> ⬛ **5xx – Error del Servidor (500–599)**: _El problema está del lado del servidor._

| Código | Significado |
|--------|--------------|
| **500** | **Internal Server Error** → _Error genérico del servidor._ |
| **501** | **Not Implemented** → _El servidor no reconoce el método solicitado._ |
| **502** | **Bad Gateway** → _El servidor intermediario recibió una respuesta inválida._ |
| **503** | **Service Unavailable** → _El servidor está saturado o en mantenimiento._ |
| **504** | **Gateway Timeout** → _No respondió a tiempo el servidor intermedio._ |
| **505** | **HTTP Version Not Supported** → _Versión de HTTP no soportada._ |
| **507** | **Insufficient Storage** → _Espacio insuficiente para completar la solicitud._ |
| **508** | **Loop Detected** → _Ciclo infinito detectado (WebDAV)._ |
| **511** | **Network Authentication Required** → _Requiere autenticación en red (por ejemplo, Wi-Fi con login)._ |
| **521** | **Web Server is Down** → _El servidor de origen está caído; Cloudflare no puede conectarse._ |
| **522** | **Connection Timed Out** → _Se agotó el tiempo de conexión entre Cloudflare y el servidor de origen._ |
| **523** | **Origin is Unreachable** → _Cloudflare no puede alcanzar el servidor de origen (posible DNS o red caída)._ |
| **525** | **SSL Handshake Failed** → _Error en el handshake SSL/TLS entre Cloudflare y el servidor de origen._ |
| **530** | **Origin DNS Error** → _Error de resolución DNS en el servidor de origen._ |
| **599** | **Network Connect Timeout Error** → _Tiempo de conexión agotado por problemas de red o proxy; no estándar HTTP._ |

---

C. **PROFUNDIZACIÓN**


Luego, profundiza **por qué debemos conocer y reconocer especialmente estos tres códigos:**

- `200 OK` → cuando todo sale bien.
- `404 Not Found` → cuando el recurso no existe o fue movido.
- `500 Internal Server Error` → cuando el problema está en el servidor.

> 💬 Explica con tus palabras cómo podrías usar estos códigos para diagnosticar errores en una API o en un proyecto web.

**RESPUESTA:** 

**Los response o respuestas de los códigos enviados desde una API nos puede indicar si el API funciona, si algo está fallando o hay un error o un bug presente en el servidor. Estos códigos, a grosso modo, nos permite identificar el error existente, cual existe, y poder corregirlo.**

> ### **200 OK**: _la solicitud se procesó correctamente._

- **SIGNIFICADO:** Esté código de estado noss confirma que la API o el endpoint está funcionando. Es útil para pruebas de conexión y para asegurarse de que los datos se reciben correctamente.

  - _Ejemplo: Si pides la lista de usuarios y obtienes un 200 OK, sabes que la solicitud fue exitosa y puedes procesar la respuesta._

- **CORRECIÓN**: En este caso, no debemos corregir nada, está en efecto operativo y funcional, por lo que podríamos continuar con otras pruebas funcionales.

> #### **404 Not Found**: _El recurso solicitado no existe o fue movido._

- **SIGNIFICADO:** Detecta rutas incorrectas en tu API o links rotos en tu web. Ayuda a identificar errores de front-end que llaman a URLs equivocadas.

  - _Ejemplo: Si tu front-end pide /api/productos/123 y obtienes 404, puede que el producto no exista o que la URL esté mal escrita._

- **CORRECIÓN**: En este caso, debemos revisar rutas, endpoints y recursos faltantes.

> #### **500 Internal Server Error**: _indica que hubo un fallo en el servidor que impidió procesar la solicitud._

- **SIGNIFICADO:** Señala errores en la lógica del servidor o problemas con la base de datos. Es un aviso para revisar logs y depurar la aplicación.

    - _Ejemplo: Si un endpoint de creación de usuario lanza 500, puede que la inserción en la base de datos esté fallando o haya un bug en el código._

- **CORRECIÓN**: En esta situación, deberemos revisar logs del servidor, excepciones y otros errores internos.

---

### **4. MÉTODOS HTTP**

A. **INVESTIGA LOS PRINCIPALES MÉTODOS HTTP UTILIZADOS EN APIs RESTful Y RESPONDE QUÉ HACE CADA UNO:** 

 A.1 **GET**: El método HTTP GET solicita una representación del recurso especificado. Las solicitudes que usan GET solo deben usarse para recuperar datos (no deben incluir datos).

 En resumidas cuenta, **solicita información, consulta datos, sin necesidad de modificar dicha información.**

 A.2 **POST**: Una solicitud POST es tipicamente enviada por un formulario HTML y resulta en un cambio en el servidor. 
 
 En resumidas cuenta, **envía datos al servidor para crear un nuevo recurso.**

 A.3 **PUT**: La petición HTTP PUT crea un nuevo elemento o reemplaza una representación del elemento de destino con los datos de la petición.

 En resumidas cuenta, **actualiza un recurso existente reemplazando completamente su contenido.**

 A.4 **DELETE:** El método de solicitud HTTP DELETE elimina el recurso especificado.

 En resumidas cuenta, **elimina datos.**
    
B: **¿EN QUÉ TIPO DE OPERACIÓN SE USSA (CONSULTAR, CREAR, ACTUALIZAR, ELIMINAR)?**

B.1 TABLA:

| MÉTODO HTTP | TIPO DE OPERACIÓN | ACCIÓN QUE REALIZA |
|----|--------------|----------------|
| GET	| 🔹 Consultar	|Obtiene o lee datos del servidor (sin modificarlos).|
POST	| 🔹 Crear	| Envía datos para crear un nuevo recurso en el servidor.|
PUT	| 🔹 Actualizar (reemplazar) |	Reemplaza completamente un recurso existente.|
DELETE |	🔹 Eliminar	| Borra un recurso existente del servidor.|
PATCH |	🔹 Actualizar (parcialmente) |	Modifica solo una parte del recurso.|
HEAD	| 🔹 Consultar (solo metadatos)	| Igual que GET, pero sin el cuerpo (solo encabezados).|
OPTIONS	| 🔹 Descubrir / configuración |	Pide información sobre los métodos o permisos disponibles en un recurso.|

C. **AGREGA UN EJEMPLO PRÁCTICO DE CADA UNO CON UNA URL O PSEUDOCÓDIGO.**

C.1. - **EJEMPLO DE GET**

- **Operación:**
```
GET /api/usuarios/25 HTTP/1.1
Host: ejemplo.com
```
- **Respuesta:**
```
"id": 25,
  "nombre": "María Pérez",
  "email": "maria@ejemplo.com"
```

C.2. **EJEMPLO DE POST**

- **Operación:**
```
POST /api/usuarios HTTP/1.1
Host: ejemplo.com
Content-Type: application/json

{
  "nombre": "Carlos Soto",
  "email": "carlos@ejemplo.com"
}
```
- **Respuesta:**
```
"{
  "id": 101,
  "nombre": "Carlos Soto",
  "email": "carlos@ejemplo.com"
}
```
C.3. **EJEMPLO DE PUT**

- **Operación:**
```
PUT /api/usuarios/25 HTTP/1.1
Host: ejemplo.com
Content-Type: application/json

{
  "nombre": "María Pérez López",
  "email": "maria.lopez@ejemplo.com"
}
```
- **Respuesta:**
```
{
  "mensaje": "Usuario actualizado correctamente"
}
```

C.4. **EJEMPLO DE DELETE**

- **Operación:**
```
DELETE /api/usuarios/25 HTTP/1.1
Host: ejemplo.com
```
- **Respuesta:**
```
(Sin cuerpo de respuesta, solo confirmación de que se eliminó.)
```


D. **BONUS**

💡 *Bonus:* menciona otros métodos menos comunes como `PATCH`, `HEAD`, `OPTIONS`.

D.1 **PATCH**: El método HTTP PATCH aplica modificaciones parciales a un recurso.

 En resumidas cuenta, **modifica solo una parte**

D.2 **HEAD**: El método HTTP HEAD solicita los metadatos de un recurso en forma de encabezados que el servidor habría enviado si se hubiera utilizado el método GET en su lugar. Este método se puede usar en los casos en que una URL puede producir una descarga grande, por ejemplo, una solicitud puede leer el encabezado Content-Length para verificar el tamaño del archivo antes de descargar el archivo con un archivo .HEADGET

Si la respuesta a una solicitud muestra que una respuesta de URL almacenada en caché ahora está desactualizada, la copia almacenada en caché se invalida incluso si no se realizó ninguna solicitud.HEADGET

En resumidas cuenta, **solo devuelve los encabezados (sin cuerpo)**

D.3 **OPTIONS**: El método HTTP OPTIONS solicita opciones de comunicación permitidas para una URL o servidor determinados. Esto se puede usar para probar los métodos HTTP permitidos para una solicitud o para determinar si una solicitud se realizaría correctamente al realizar una solicitud comprobacional de CORS. Un cliente puede especificar una dirección URL con este método o un asterisco () para hacer referencia a todo el servidor.

En resumidas cuenta, **Pide al servidor qué métodos HTTP están permitidos para ese recurso.**

---
### 5. **TEMA ADICIONAL: HEADERS**

A. **¿QUÉ SON LOS HEADERS EN UNA SOLICITUD HTTP?**

Los headers son campos de información que se envían junto con la solicitud (request) o la respuesta (response) en HTTP.

No forman parte del contenido principal del mensaje, pero dan contexto o instrucciones al servidor o cliente.

Básicamente, los headers dicen “quién eres, qué esperas, cómo interpretar los datos, etc.”.

B. **¿QUÉ TIPO DE INFORMACIÓN CONTIENEN (Por ejemplo: Content-Type, Authorization, User-Agent)??**

| Header	| Función | Ejemplo |
|-----------|---------|-----|
| Content-Type	| Indica el tipo de contenido que se está enviando (por ejemplo, application/json, text/html).| Content-Type: application/json (envías JSON) |
|Authorization	| Envía credenciales o tokens para autenticación.| Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9 |
| User-Agent	| Informa sobre el cliente que hace la petición (navegador, app, etc.). | User-Agent: MiAplicacion/1.0
| Accept |	Indica los tipos de respuesta que el cliente puede procesar (application/json, text/xml). | Accept: application/json
| Host | Especifica el dominio del servidor al que se está conectando. | Host: api.ejemplo.com
| Cache-Control |	Controla cómo se deben almacenar o reutilizar los recursos en caché.| Cache-Control: no-cache
| Cookie | Envía cookies desde el cliente al servidor. | Cookie: sessionId=abc123 |
| Set-Cookie | El servidor envía cookies al cliente para almacenar información. | Set-Cookie: sessionId=abc123; HttpOnly; Secure
|If-Modified-Since |Pide al servidor solo enviar datos si han cambiado desde una fecha dada.|If-Modified-Since: Wed, 01 Nov 2023 10:00:00 GMT|
| Referer | Indica la URL desde donde se hizo la solicitud. |Referer: https://miweb.com/pagina  |
| Origin | Usado en CORS para indicar el origen de la solicitud. | Origin: https://miweb.com |
| Accept-Encoding | Indica al servidor los tipos de compresión que el cliente soporta.|Accept-Encoding: gzip, deflate|
|Accept-Language|Indica los idiomas preferidos del cliente.|Accept-Language: es-ES, en;q=0.9|
|Connection|Controla si la conexión TCP se mantiene abierta o se cierra después de la respuesta.|Connection: keep-alive|
|Content-Length|Indica la longitud del cuerpo de la solicitud en bytes.|Content-Length: 123|

C. **¿POR QUÉ SON IMPORTANTES AL CONSUMIR APIs?**

#### Los headers son esenciales para comunicar correctamente el contexto de tu solicitud.

Autenticación: Sin el header Authorization, muchas APIs bloquean la solicitud.

Formato de datos: Content-Type y Accept aseguran que servidor y cliente hablen el mismo “idioma” (JSON, XML, etc.).

Optimización: Cache-Control o If-None-Match ayudan a reducir tráfico innecesario.

Compatibilidad: User-Agent permite al servidor ajustar respuestas según el tipo de cliente.

En resumen: los headers son esenciales para comunicar correctamente el contexto de tu solicitud.

D. **MUESTRA UN EJEMPLO DE UNA SOLICITUD COMPLETA CON CABECERAS INCLUIDAS.**

```
GET /api/usuarios/25 HTTP/1.1
Host: api.ejemplo.com
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9
Content-Type: application/json
Accept: application/json
User-Agent: MiAplicacion/1.0
Cache-Control: no-cache
Accept-Encoding: gzip, deflate
Accept-Language: es-ES,en;q=0.9
```
En el presente ejemplo se utilizan varios headers para conducir las respuestas, pues controlan el comportamiento de la respuesta y el manejo de la solicitud.

De eso se tratan.

### 6. ENDING 

```
Reflexión personal: Conocer algunos códigos y respuestas pueden permitirme a la hora de realizar trabajos de porgramación, ya sea para terceros o personales, evidenciar su status, si requiere correciones, saber qué datos se alojan, asimismo para reconocer otros datos que se requieran comparaciones (como precios de productos de distintas APIs), todo en función del manejo de la data y de su operatividad.

Este conocimiento puede permitir resolver problemas, bugeos, errores de servidores o del cliente y que requieran soluciones en las distintas etapas de la programación.
```



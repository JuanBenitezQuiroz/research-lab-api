# **Tarea de Investigación**

### 🎯 **Objetivo General**

Investigar y comprender los fundamentos del **protocolo HTTP** y su rol dentro del funcionamiento de las **APIs web**.

El propósito es que cada estudiante pueda explicar con sus propias palabras cómo los navegadores, servidores y APIs se comunican a través de este protocolo.

---

### 🧠 **Instrucciones Generales**

1. Trabaja de forma **individual o en parejas**.
2. Crea un **documento resumen** (Markdown) con los resultados de tu investigación.
3. Utiliza fuentes confiables (documentación oficial, Mozilla Developer Network, W3Schools, etc.).
4. Incluye **ejemplos reales** o imágenes cuando sea posible.
5. Al final del trabajo, agrega una **reflexión personal** sobre qué parte consideras más importante y por qué.

---

### 🔹 **1. Diferencia entre HTTP y HTTPS**

- Explica qué significa cada sigla.
- Investiga cómo funciona el **cifrado SSL/TLS** en HTTPS.
- ¿Por qué HTTPS es más seguro?
- Muestra un ejemplo visual (puede ser una captura del candado del navegador).
- ¿Qué sucede si un sitio no usa HTTPS?

---

### 🔹 **2. Puertos de comunicación**

- Explica qué es un **puerto** en redes y por qué es importante para HTTP.
- Investiga el propósito de los puertos **80** y **8080**, y qué tipo de tráfico suelen manejar.
- Menciona **otros puertos conocidos** (por ejemplo: 21, 22, 443, 3306) y su función.
- Ejemplo: ¿Qué puerto utiliza HTTPS por defecto?

---

### 🔹 **3. Códigos de estado de respuesta HTTP**

- Investiga qué son los **status codes** y para qué sirven.
- Crea una **tabla organizada por categoría**:

| Categoría | Rango | Descripción general | Ejemplo de código |
| --- | --- | --- | --- |
| **1xx – Informativos** | 100–199 | El servidor recibió la solicitud y continúa el proceso. | 100 Continue |
| **2xx – Éxito** | 200–299 | La solicitud fue procesada correctamente. | 200 OK |
| **3xx – Redirección** | 300–399 | La solicitud fue redirigida a otro recurso. | 301 Moved Permanently |
| **4xx – Error del Cliente** | 400–499 | Error causado por la solicitud del cliente. | 404 Not Found |
| **5xx – Error del Servidor** | 500–599 | El servidor tuvo un problema al procesar la solicitud. | 500 Internal Server Error |
- Luego, profundiza **por qué debemos conocer y reconocer especialmente estos tres códigos:**
    - `200 OK` → cuando todo sale bien.
    - `404 Not Found` → cuando el recurso no existe o fue movido.
    - `500 Internal Server Error` → cuando el problema está en el servidor.

> 💬 Explica con tus palabras cómo podrías usar estos códigos para diagnosticar errores en una API o en un proyecto web.
> 

---

### 🔹 **4. Métodos HTTP**

Investiga los principales métodos HTTP utilizados en APIs RESTful:

- **GET**, **POST**, **PUT**, **DELETE**
    
    y responde:
    
- ¿Qué hace cada uno?
- ¿En qué tipo de operación se usa (consultar, crear, actualizar, eliminar)?
- Agrega un ejemplo práctico de cada uno con una URL o pseudocódigo.

💡 *Bonus:* menciona otros métodos menos comunes como `PATCH`, `HEAD`, `OPTIONS`.

---

### 🔹 **5. Tema adicional sugerido: Cabeceras (Headers)**

> (Tema propuesto para investigación adicional)
> 
- ¿Qué son los **headers** en una solicitud HTTP?
- ¿Qué tipo de información contienen (por ejemplo: `Content-Type`, `Authorization`, `User-Agent`)?
- ¿Por qué son importantes al consumir APIs?
- Muestra un ejemplo de una solicitud completa con cabeceras incluidas.

---

### 🧩 **Producto Esperado**

Tu entrega debe incluir:

1. Explicaciones claras y personales.
2. Tablas o diagramas cuando sea necesario.
3. Ejemplos reales de uso en una API (puede ser `https://randomuser.me/` o `https://jsonplaceholder.typicode.com/`).
4. Reflexión final sobre qué aprendiste y cómo aplicarías este conocimiento al construir tus propias APIs.

---

## 📅 **Entrega Sugerida**

**Repositorio en GitHub:** `research-lab-api`

> 💡 Este repositorio debe contener un archivo principal llamado README.md con toda tu investigación documentada, tablas, ejemplos y reflexiones finales.
> 

**Estructura sugerida del repositorio:**

```
research-lab-api/
│
├── README.md          # Documento principal con toda la investigación
└── images/            # (Opcional) Capturas o diagramas explicativos
```

**Formato de entrega:**

- Subir el archivo `README.md` completo al repositorio en GitHub.
- Asegurarse de incluir todas las secciones solicitadas (HTTP vs HTTPS, puertos, códigos de estado, métodos HTTP, etc.).
- Incluir nombre completo y cohorte en la parte superior del documento.

📘 **Repositorio:** 

📅 **Fecha de Entrega:** 03/11/2025

🕒 **Entrega:** Al final de la sesión asincrónica o en la próxima clase.

---

> 🧠 Extra (Opcional):
> 
> 
> Si quieres ir más allá, investiga también cómo funcionan las **peticiones HTTP con herramientas reales**, como `curl`, Postman o el módulo `requests` en Python.
>
### 📄 Característica para FDD

#### **✨ Autenticación de usuario con correo y contraseña mediante OAuth2, con renovación automática de sesión**

**📝 Esta característica permitirá a los usuarios acceder al sistema GEIL ingresando su correo electrónico y contraseña. El sistema validará las credenciales utilizando un protocolo seguro (OAuth2 con Password Grant) y, si son correctas, emitirá dos tokens: uno de acceso (válido por tiempo limitado) y otro de renovación (de duración más prolongada). Este segundo token permitirá extender la sesión del usuario automáticamente, sin necesidad de volver a ingresar sus credenciales. Además, se registrará cada intento de inicio de sesión en un log de seguridad, tanto si fue exitoso como si falló, incluyendo información como IP, fecha y dispositivo. La implementación contempla mecanismos de expiración, renovación de tokens, bloqueo ante credenciales inválidas y validaciones visuales en la interfaz.**

---

**📌 Prioridad:** Alta
**⏳ Estimación de Esfuerzo:** 3 días

---

**🌿 Rama Git asociada:**
`feature/user-login-authentication-oauth2`

---

### ✅ Criterios de Aceptación

* [x] 🎯 El sistema permite iniciar sesión con correo y contraseña válidos, emitiendo correctamente los tokens correspondientes.
* [x] 📋 Las respuestas del sistema ante errores de autenticación son claras y comprensibles para el usuario.
* [x] 🧪 Se cuenta con pruebas automatizadas (unitarias, de integración y E2E) que validan el flujo completo de autenticación, incluyendo renovación automática del acceso.

---

## 🛠️ Tareas Desglosadas

### 🧩 Diseño Previo

Se elaborará un diagrama de secuencia que describa el flujo completo del inicio de sesión y renovación de sesión, abarcando la interacción entre frontend, backend y base de datos. Este modelo servirá de base para las decisiones de implementación técnica y los criterios de prueba.

---

### 🛢️ Base de Datos

Se utilizarán las tablas `user`, `company` y `security_log`, diseñadas para almacenar información de acceso, credenciales cifradas y trazabilidad de los intentos de autenticación.

---

### 🖥️ Backend

El backend gestionará todo el proceso de autenticación utilizando FastAPI. Se implementarán los endpoints necesarios para iniciar sesión (`/auth/login`) y renovar tokens (`/auth/refresh`). Las credenciales se validarán con `bcrypt`, los tokens se generarán con `python-jose`, y todos los eventos relevantes quedarán registrados en la tabla de logs de seguridad. La implementación seguirá principios de diseño limpio y será acompañada de pruebas unitarias y de integración para asegurar su confiabilidad.

---

### 🖼️ Frontend

Se desarrollará una interfaz de inicio de sesión funcional y accesible, usando Vuetify. Esta incluirá validaciones reactivas y retroalimentación visual para cada estado del proceso (en progreso, éxito, error). El almacenamiento y gestión del estado autenticado se realizará con `Pinia`, y se integrará lógica para manejar automáticamente la expiración del `access_token`, solicitando un nuevo par de tokens mediante el `refresh_token`. Se cubrirán todos los escenarios con pruebas unitarias y mocks usando MSW.

---

### 🧪 Pruebas End-to-End (E2E)

Se automatizarán escenarios completos de autenticación mediante Playwright, incluyendo ingreso correcto, errores de contraseña, expiración de sesión, renovación automática, cierre de sesión y restricción de acceso a rutas protegidas. Estas pruebas asegurarán que el sistema responde correctamente desde el punto de vista del usuario final.

---

## 🔗 Dependencias

* FastAPI
* OAuth2PasswordRequestForm
* python-jose
* bcrypt
* SQLModel
* Vue 3 / Vuetify
* Pinia
* Axios
* Playwright
* MSW

---

## 🛡️ Preocupaciones Transversales

* **🔒 Seguridad:** Uso de contraseñas hasheadas, expiración de sesiones, validación de tokens, y registro completo de eventos.
* **📈 Escalabilidad:** Arquitectura desacoplada que permite reutilización futura en apps móviles u otros clientes.
* **🔄 Compatibilidad:** Basado en el estándar OAuth2, ampliamente soportado por herramientas y librerías modernas.

---

### **Notas Adicionales:**

* Esta característica es una de las primeras en ser implementadas (Iteración 1) y es necesaria para acceder a cualquier funcionalidad del sistema.
* Su diseño y pruebas garantizan que el acceso sea seguro, auditado y renovable sin fricciones para el usuario.
* Sienta las bases para futuras extensiones como autenticación multifactor (MFA) o integración con servicios externos de identidad.

---
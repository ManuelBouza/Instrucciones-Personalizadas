### 📄 Plantilla de Características para FDD

#### **✨ \[Nombre de la Característica]**

**📝 \[Describe de forma clara el propósito de esta característica y qué funcionalidad concreta aportará al sistema. Debe explicar el valor que entrega y cómo será usada por los usuarios.]**

---

**📌 Prioridad:** \[Alta | Media | Baja]
**⏳ Estimación de Esfuerzo:** \[Horas o días estimados]
**🌿 Rama Git asociada:**
`feature/[nombre-característica]`

---

### ✅ Criterios de Aceptación

* [ ] 🎯 \[La característica permite realizar correctamente la acción prevista por el usuario.]
* [ ] 📋 \[Se validan correctamente todos los datos y escenarios definidos.]
* [ ] 🧪 \[Las pruebas unitarias, de integración y E2E están completas y aprobadas.]
* [ ] 🔒 \[Se garantiza la seguridad y privacidad de los datos durante toda la operación.]
* [ ] 👓 \[La experiencia de usuario ofrece retroalimentación clara, accesible y coherente.]

> ℹ️ *Pueden agregarse más criterios si la naturaleza de la característica lo requiere (ej. interoperabilidad, trazabilidad, rendimiento, etc.).*

---

### 🧩 Diseño Previo

Se debe modelar el flujo funcional y técnico mediante un **diagrama de secuencia dinámico (`dynamic`) en Structurizr**, describiendo la interacción entre usuarios, frontend, backend y base de datos. Este diagrama será obligatorio como guía visual para el desarrollo y validación de la tarea.

---

### 🧩 Backend (FastAPI + SQLModel)

> Cada punto debe desarrollarse siguiendo el ciclo TDD (Rojo → Verde → Refactor) con **pytest** y pruebas integradas en FastAPI.

---

**🧪 Test inicial TDD (happy path):**
\[Describir el test que valida el comportamiento principal desde una perspectiva de integración.]

---

**🌐 Endpoint:**
\[Método, ruta, permisos y descripción del comportamiento.]

---

**🗃️ Modelos `SQLModel`:**
\[Tablas, relaciones o estructuras requeridas para esta funcionalidad.]

---

### 💻 Frontend (Vue 3 + Vuetify + Pinia)

> Aplicar TDD con **Vitest**, partiendo desde la interacción del usuario.

---

**🧪 Test inicial TDD (happy path):**
\[Describir la prueba que simula la interacción del usuario en condiciones normales.]

---

**🧩 Componente/s o vista (Vuetify):**
\[Nombre del componente o vista implicada, y su rol.]

---

**🌐 Conexión con el endpoint:**
\[llamado a la API y manejo básico de respuesta.]

---

### 🧪 **Cobertura y Validación Final: Backend**

* [ ] Test de casos válidos
* [ ] Test de errores o inputs inválidos
* [ ] Test de casos extremos o borde
* [ ] Validación de flujos alternativos (si aplica)
* [ ] Confirmar que **todas las pruebas** backend (`pytest`) pasan correctamente

---

### 🧪 **Cobertura y Validación Final: Frontend**

* [ ] Test de casos válidos
* [ ] Test de errores o inputs inválidos
* [ ] Test de casos extremos o borde
* [ ] Validación de flujos alternativos (si aplica)
* [ ] Confirmar que **todas las pruebas** frontend (`vitest`) pasan correctamente

---

### 🧪 **Test E2E (`playwright`)**

* [ ] Test de casos válidos
* [ ] Test de errores o inputs inválidos
* [ ] Test de casos extremos o borde
* [ ] Validación de flujos alternativos (si aplica)
* [ ] Confirmar que **todas las pruebas** E2E (`playwright`) pasan correctamente 
****
---

## 🔗 Dependencias

* \[Nombre del módulo, componente o librería del que depende esta característica]
* \[Sistema externo o integración relevante, si aplica]

---

## 🛡️ Preocupaciones Transversales

* **🔒 Seguridad:** \[Aspectos clave como validación de acceso, cifrado de datos, control de sesiones o privacidad de la información.]
* **📈 Escalabilidad:** \[Criterios de diseño que faciliten el crecimiento de la funcionalidad sin afectar el rendimiento del sistema.]
* **🔄 Compatibilidad:** \[Alineación con otras partes del sistema, versiones anteriores o posibles extensiones futuras.]

---

### 📌 Notas Adicionales

\[Información relevante como decisiones del equipo, riesgos conocidos, consideraciones técnicas o funcionales, o cualquier aspecto que se deba tener en cuenta durante el desarrollo.]

---

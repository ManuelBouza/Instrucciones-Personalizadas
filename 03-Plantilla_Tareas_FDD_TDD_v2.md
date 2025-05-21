# 📄 Plantilla de Tarea para FDD + TDD por Acciones (🔁 Ciclo completo por cada paso)

> ⚠️ **IMPORTANTE:** Esta plantilla es exclusivamente para **documentar** la tarea antes de su desarrollo.
> **No se escribe código aquí**, solo se describe **qué se va a hacer**, **cómo se va a hacer** y **cómo se validará** según las prácticas de FDD y TDD.

---

#### **\[ ] Tarea \[N]: \[Nombre breve y descriptivo de la tarea]**

* **🎯 Objetivo general:**
  \[Describir el propósito global de la tarea, su impacto dentro de la característica y qué comportamiento del sistema se busca validar.]

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

---

### 📝 Notas Adicionales sobre la Tarea

\[Información extra relevante, como riesgos, decisiones del equipo o requisitos especiales.]

---
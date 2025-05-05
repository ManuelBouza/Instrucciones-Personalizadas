### 📄 Plantilla de Características para FDD

#### **✨ \[Nombre de la Característica]**

**📝 \[Describe de forma clara el propósito de esta característica y qué funcionalidad concreta aportará al sistema. Debe explicar el valor que entrega y cómo será usada por los usuarios.]**

---

**📌 Prioridad:** \[Alta | Media | Baja]
**⏳ Estimación de Esfuerzo:** \[Horas o días estimados]

---

**🌿 Rama Git asociada:**
`feature/[nombre-característica]`

---

### ✅ Criterios de Aceptación

* [ ] 🎯 \[La característica permite realizar correctamente la acción prevista por el usuario.]
* [ ] 📋 \[Se validan correctamente todos los datos y escenarios definidos.]
* [ ] 🧪 \[Las pruebas unitarias, de integración y E2E están completas y aprobadas.]

---

## 🛠️ Tareas Desglosadas

> ⚠️ Esta sección debe escribirse en **modo narrativo, no como lista de acciones**, y debe ofrecer una descripción clara de **lo que se hará** en cada zona del sistema. No incluir detalles técnicos específicos que pertenezcan a las tareas individuales.

---

### 🧩 Diseño Previo

\[Se debe modelar el flujo funcional y técnico de la característica, representando cómo se comunican los elementos del sistema (Frontend, Backend y Base de Datos). Este modelo puede reflejarse en un diagrama de secuencia que sirva como guía para los desarrollos posteriores.]

---

### 🛢️ Base de Datos

\[Se establecerá la estructura de datos necesaria para soportar la funcionalidad, incluyendo creación o modificación de tablas, relaciones y restricciones de integridad. Si aplica, se tendrá en cuenta el registro de eventos o estados relevantes para trazabilidad.]

---

### 🖥️ Backend

\[Se implementarán las funciones necesarias para gestionar la lógica del servidor. Esto puede incluir la creación de endpoints, validación de datos, ejecución de operaciones sobre la base de datos, emisión de respuestas estructuradas y aplicación de reglas de negocio. Además, se deben desarrollar las pruebas unitarias e integración necesarias para garantizar su funcionamiento.]

---

### 🖼️ Frontend

\[Se construirá la interfaz visual que permita al usuario interactuar con esta funcionalidad. Esto puede implicar formularios, componentes, pantallas o integraciones con el backend. También se contemplarán validaciones visuales, retroalimentación al usuario y gestión del estado asociado.]

---

### 🧪 Pruebas End-to-End (E2E)

\[Se validará el recorrido completo del usuario mediante pruebas automatizadas que simulen su interacción real con el sistema. Estas pruebas deben contemplar escenarios exitosos, casos de error, y validaciones visuales o funcionales, usando herramientas como Playwright, Cypress u otras.]

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

### **Notas Adicionales:**

\[Información relevante como decisiones del equipo, riesgos conocidos, consideraciones técnicas o funcionales, o cualquier aspecto que se deba tener en cuenta durante el desarrollo.]

---

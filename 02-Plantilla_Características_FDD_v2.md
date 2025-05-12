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

\[Se debe modelar el flujo funcional y técnico de la característica, representando cómo se comunican los elementos del sistema (Frontend, Backend y Base de Datos). Este modelo puede reflejarse en un diagrama de secuencia que sirva como guía para los desarrollos posteriores.]

---

## 🛠️ Tareas Desglosadas

> ⚠️ Esta sección debe incluir solo tareas **funcionales** que representan el objetivo visible del usuario.
>
> **Cada tarea funcional debe implicar necesariamente la creación de un endpoint**, ya que su objetivo es exponer una nueva acción o recurso disponible para el usuario o sistema externo.
>
> Las tareas técnicas necesarias para implementar cada funcionalidad se detallarán en archivos separados de tareas (`T01-*.md`), y cada una debe cumplir con TDD.

| Nº  | ✔ | Tarea funcional                                                      |
| --- | - | -------------------------------------------------------------------- |
| T01 | ⬜ | \[Descripción de la funcionalidad principal que se va a implementar] |
| T02 | ⬜ | \[Otra funcionalidad dependiente o relacionada, si aplica]           |
| ... | ⬜ | ...                                                                  |

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

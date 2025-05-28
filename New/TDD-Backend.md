# 📄 Documentación de Funcionalidad - TDD – Backend

ℹ️ Esta documentación técnica complementa la descripción funcional de la característica definida en la plantilla FDD correspondiente:
`/docs/fdd/[nombre-característica].md`

---

## ✨ Nombre de la Característica

> Ejemplo: Registro de Usuarios

---

## 📝 Descripción Técnica de la Funcionalidad

ℹ️ Esta sección desarrolla el valor y objetivo de la feature desde el punto de vista técnico del backend.

* **Propósito técnico:**
  Implementar un endpoint REST autenticado con JWT (`jti`), validaciones estrictas con `SQLModel`, y trazabilidad de operaciones críticas en `security_log`.

* **Requisitos funcionales a implementar:**

  * \[✔️] Acción esperada según FDD
  * \[✔️] Validaciones de datos, jerarquía y permisos
  * \[✔️] Registro de evento crítico en `security_log` si aplica
  * \[✔️] Documentación de errores y respuestas en `API`

---

## 🧠 Diseño Técnico y Decisiones de Arquitectura

### 🔧 Flujo o Arquitectura Técnica

ℹ️ Describe cómo se implementará técnicamente el flujo funcional ya modelado en Structurizr (ver FDD).

* Inicia en: `app/api/routes/[modulo].py`
* Requiere autorización vía `Depends(get_current_user)`
* Lógica delegada a `app/services/[modulo]_service.py`
* Persistencia con `SQLModel` vía `session.exec()`
* Respuesta estructurada con `app/schemas/[modelo].py`

### 📐 Decisiones Técnicas

ℹ️ Lista de decisiones clave tomadas en el diseño e implementación técnico.

* [x] Se utilizó `Annotated` en dependencias (`FAST002`)
* [x] Validación y desnormalización explícita con `SQLModel`
* [x] Uso de `bcrypt` para contraseñas (si aplica)
* [x] Se evita `response_model` redundante (`FAST001`)
* [x] Cada endpoint incluye test asociado en `tests/routes/`

### ⚠️ Consideraciones Técnicas / Supuestos

ℹ️ Anota supuestos importantes, límites actuales y cualquier dependencia técnica.

* [ ] Validación de unicidad gestionada por lógica + índice único DB
* [ ] El usuario autenticado debe tener permisos jerárquicos válidos
* [ ] Acciones críticas deben dejar rastro en `security_log`
* [ ] Todos los errores retornan HTTP estándar (`422`, `401`, `403`, etc.)

---

## ✅ Especificación Técnica de Pruebas

ℹ️ Estos criterios derivan de los definidos en la FDD, y aquí se traducen en condiciones verificables mediante pruebas automatizadas (`pytest`).

### 🎯 Criterios Técnicos de Aceptación

* [ ] El endpoint responde correctamente ante entradas válidas
* [ ] La autorización es obligatoria y se valida el rol/nivel del usuario
* [ ] Errores comunes retornan códigos y mensajes claros
* [ ] La lógica crítica queda registrada (si aplica) en `security_log`

### 🧪 Tipos de Pruebas a Implementar

* **Unitarias (`pytest`)**

  * Validación y lógica en servicios puros (`*_service.py`)
  * Funciones auxiliares aisladas

* **Integración (`pytest + TestClient`)**

  * Simulación de requests autenticadas
  * Fixtures de usuarios, tokens, sesiones

* **Validación de seguridad**

  * Accesos no permitidos → HTTP 403/401
  * Acciones de rol incorrecto → HTTP 403
  * Pruebas de trazabilidad en `security_log` (si aplica)

---

## 📋 Casos de Prueba y Resultados Esperados

ℹ️ Documenta los escenarios clave que serán cubiertos por los tests.
| ID | Caso de Prueba                              | Entrada             | Resultado Esperado         |
| -- | ------------------------------------------- | ------------------- | -------------------------- |
| 1  | Acción válida por usuario autorizado        | JSON válido + token | HTTP 200 + Objeto esperado |
| 2  | Token inválido o ausente                    | Sin auth header     | HTTP 401                   |
| 3  | Usuario sin permisos suficientes            | Token válido        | HTTP 403                   |
| 4  | Validación fallida                          | JSON malformado     | HTTP 422                   |
| 5  | Acción crítica se registra en security\_log | Acción sensible     | Insert en `security_log`   |

---

## 🗂 Archivos Técnicos Relevantes

ℹ️ Lista de archivos modificados o creados durante el desarrollo backend.

* `app/api/routes/[nombre].py` → Endpoint público
* `app/schemas/[modelo].py` → Validaciones y estructura de datos
* `app/services/[modulo]_service.py` → Lógica de negocio
* `app/models/security_log.py` → Modelo de auditoría
* `tests/routes/test_[nombre].py` → Pruebas integradas con `TestClient`
* `tests/services/test_[modulo]_service.py` → Pruebas unitarias

---

## 🗒 Observaciones Técnicas / Decisiones Durante TDD

ℹ️ Registro de hallazgos, decisiones técnicas, bloqueos y posibles deudas técnicas durante el desarrollo backend.

* ✅ Se utilizó `pytest` con `TestClient` y DB temporal
* 🧪 Validación de jerarquía y `company_id` se probó con múltiples fixtures
* 📋 Se agregó entrada en `security_log` al realizar acciones de riesgo
* 🧭 El error 403 se devuelve si `user.company_id != target_company_id` (si aplica)

---

## 🔗 Recursos Relacionados

ℹ️ Documentación técnica asociada al desarrollo backend de esta funcionalidad.

* 📄 Documento FDD vinculado: `/docs/fdd/[nombre-característica].md`
* 🗺️ Diagrama técnico (Structurizr): `/workspace.dsl`
* 🔖 ADR relacionada: `/docs/adr/[id]-[nombre].md`

---

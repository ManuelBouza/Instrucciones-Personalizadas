# 📄 Documentación de Funcionalidad - TDD

ℹ️ Esta documentación técnica complementa la descripción funcional de la característica definida en la plantilla FDD correspondiente:  
`/docs/fdd/[nombre-característica].md`

---

## ✨ Nombre de la Característica
> Ejemplo: Registro de Usuarios

---

## 📝 Descripción Técnica de la Funcionalidad

ℹ️ Esta sección desarrolla el valor y objetivo de la feature desde el punto de vista técnico.  
La descripción funcional completa está definida en el documento FDD asociado.

- **Propósito técnico:**  
  [Explica qué se construirá, cómo se conecta con el sistema, y qué impacto tiene en el código.]

- **Requisitos funcionales a implementar:**  
  - [✔️ Acción principal esperada]
  - [✔️ Validaciones clave]
  - [✔️ Flujos específicos que deben cubrirse con lógica técnica]

---

## 🧠 Diseño Técnico y Decisiones de Arquitectura

### 🔧 Flujo o Arquitectura Técnica

ℹ️ Describe cómo se implementará técnicamente el flujo funcional ya modelado en Structurizr (ver FDD).

- Inicia en: `src/pages/...`
- Llama a: `POST /api/...`
- Procesa: validaciones, lógica de negocio, persistencia, respuestas

### 📐 Decisiones Técnicas

ℹ️ Lista de decisiones clave tomadas en el diseño e implementación técnico.

- [x] Se utilizó la librería `X` por [razón]
- [x] Se aplicó inyección de dependencias para testear la lógica de forma aislada
- [x] Se encapsuló lógica en `user_service.py` para facilitar pruebas y reuso

### ⚠️ Consideraciones Técnicas / Supuestos

ℹ️ Anota supuestos importantes, límites actuales y cualquier dependencia técnica.

- [ ] El sistema de email debe estar operativo en entorno real (mockeado en test)
- [ ] No contempla usuarios con doble autenticación en esta etapa
- [ ] Requiere validación de formatos y unicidad a nivel de base de datos

---

## ✅ Especificación Técnica de Pruebas

ℹ️ Estos criterios derivan de los definidos en la FDD, y aquí se traducen en condiciones verificables mediante pruebas automatizadas.

### 🎯 Criterios Técnicos de Aceptación

- [ ] El endpoint responde correctamente ante datos válidos
- [ ] Los errores comunes (email duplicado, campos inválidos) se gestionan con códigos y mensajes claros
- [ ] La lógica se prueba en capas (unitaria, integración, E2E)

### 🧪 Tipos de Pruebas a Implementar

- **Pruebas Unitarias**
  - 🧪 *Backend:* `pytest` – validación de campos, servicios
  - 🧪 *Frontend:* `vitest` – validación local, feedback visual

- **Pruebas de Integración**
  - 🔌 *FastAPI:* uso de `TestClient`, pruebas contra base de datos de prueba

- **Pruebas End-to-End (E2E)**
  - 🌐 *Playwright:* simulación completa desde UI hasta backend, incluyendo validaciones visuales

---

## 📋 Casos de Prueba y Resultados Esperados

ℹ️ Documenta los escenarios clave que serán cubiertos por los tests.

| ID | Caso de Prueba                         | Entrada           | Resultado Esperado       |
|----|----------------------------------------|-------------------|---------------------------|
| 1  | Registro exitoso                       | JSON válido       | HTTP 201 + Usuario        |
| 2  | Email duplicado                        | Email existente   | HTTP 400 + Error          |
| 3  | Contraseña inválida                    | Menos de 6 chars  | HTTP 422                  |
| 4  | Campo opcional omitido                 | JSON sin teléfono | HTTP 201 (sin errores)    |

---

## 📊 Métricas de Pruebas

ℹ️ Registro de cobertura y observaciones relevantes para cada tipo de prueba.

| Tipo de Prueba | Herramienta     | Cobertura | Observaciones                     |
|----------------|------------------|-----------|-----------------------------------|
| Unitaria       | `pytest`         | 92%       | Validadores, lógica pura cubierta |
| Integración    | `pytest` + BD    | 87%       | Endpoints con validaciones        |
| Frontend       | `vitest`         | 88%       | Faltan pruebas visuales completas |
| E2E            | `Playwright`     | Parcial   | Flujo básico validado             |

---

## 👓 Validaciones de UX y Accesibilidad

ℹ️ Validaciones asociadas a la experiencia de usuario. Alineadas con los criterios visuales definidos en la FDD.

- [ ] Etiquetas correctamente asociadas (`<label>`)
- [ ] Mensajes de error visibles y accesibles
- [ ] Navegación completa con teclado
- [ ] Adaptabilidad en dispositivos móviles
- [ ] Feedback inmediato tras errores o éxito

---

## 🗂 Archivos Técnicos Relevantes

ℹ️ Lista de archivos modificados o creados durante el desarrollo de esta funcionalidad.

### Backend (FastAPI + Pytest)
- `app/api/routes/users.py` → Lógica del endpoint
- `app/schemas/user.py` → Modelos de validación
- `app/services/user_service.py` → Lógica de negocio desacoplada
- `tests/test_user_registration.py` → Tests unitarios e integración

### Frontend (Vue + Vitest)
- `src/views/Register.vue` → Formulario de registro
- `src/stores/auth.ts` → Acción `register`
- `src/components/__tests__/register.spec.ts` → Tests de componente

### E2E (Playwright)
- `e2e/register.spec.ts` → Pruebas completas del flujo de registro
- `playwright.config.ts` → Configuración del entorno de prueba

---

## 🔁 Iteraciones de Desarrollo (TDD)

ℹ️ Registro de pasos seguidos en el ciclo Red–Green–Refactor durante la implementación.

| 🧩 Fase       | 🛠️ Descripción                                                                                   | 📈 Estado | 🧾 Commit |
|--------------|---------------------------------------------------------------------------------------------------|-----------|-----------|
| 🔴 Red        | Se escribieron tests con `pytest` y `vitest` para validar email único y campos requeridos         | ❌ Fallan | `abc123`  |
| 🟢 Green      | Implementación mínima para que los tests pasen                                                    | ✅ OK     | `def456`  |
| 🛠️ Refactor   | Reorganización de lógica en un nuevo servicio (`user_service.py`)                                | ✅ OK     | `ghi789`  |
| 🟡 Red+Green  | Se añadió envío de correo con mocks (`pytest` + test visual en Playwright)                        | ✅ OK     | `jkl012`  |
| 🧹 Refactor 2 | Limpieza de código, mejora de cobertura y manejo de edge cases adicionales                        | ✅ OK     | `mno345`  |

---

## 🗒 Observaciones Técnicas / Decisiones Durante TDD

ℹ️ Registro de hallazgos, decisiones técnicas, bloqueos y posibles deudas técnicas.

- 🔍 *Se usaron fixtures con base en memoria (`pytest`) para aislar las pruebas.*
- ⚙️ *Se simula el backend en `Playwright` con mocks en entorno de test.*
- 💡 *División clara entre lógica de validación, servicios y endpoints facilitó el testing.*
- 📈 *Se agregaron métricas en CI para monitorear calidad de test.*
- 🧭 *Se identificaron duplicaciones en el store de frontend (posible deuda técnica futura).*

---

## 🔗 Recursos Relacionados

ℹ️ Documentación y referencias complementarias.

- 📄 Documento FDD vinculado: `/docs/fdd/[nombre-característica].md`
- 🗺️ Diagrama funcional: `/docs/diagrams/user-registration.drawio`
- 🔖 ADR relacionada: `docs/adr/0001-email-validacion.md`
- 📘 Guía de testing general: `/docs/testing-guidelines.md`
- ♿ Checklist de accesibilidad: `/docs/checklist-a11y.md`

---

### 📄 Plantilla de Características para FDD

#### ✨ **Nombre de la Característica**

> ℹ️ Formato recomendado: **\<acción> <resultado> <objeto>**
> Ejemplos:
> • “Mostrar detalles completos de empresa registrada”
> • “Enviar notificación de confirmación por correo al finalizar pedido”

---

#### 📝 **Propósito de la Característica**

ℹ️ Describe claramente qué problema resuelve esta funcionalidad, qué valor aporta al sistema y cómo lo usará el usuario. Incluye si aplica:

* Flujo funcional esperado
* Impacto en módulos existentes
* Criterios de aceptación funcionales
* Consideraciones visuales o técnicas

> 🔁 La implementación técnica y validación de esta funcionalidad mediante pruebas automatizadas se documenta en la plantilla TDD correspondiente.

---

#### 📌 Prioridad: \[Alta | Media | Baja]

#### ⏳ Estimación de Esfuerzo: \[Horas o días estimados]

#### 🌿 Rama Git asociada: `feature/[nombre-característica]`

#### 📍 Estado: \[Propuesta | En análisis | En desarrollo | En revisión | Completa]

---

### ✅ Criterios de Aceptación

* [ ] 🎯 Permite realizar correctamente la acción prevista por el usuario.
* [ ] 📋 Se validan todos los datos y escenarios definidos.
* [ ] 🧪 Las pruebas unitarias, de integración y E2E están completas y aprobadas. *(Ver plantilla TDD para detalles técnicos)*
* [ ] 🔒 Se garantiza la seguridad y privacidad de los datos.
* [ ] 👓 La experiencia de usuario ofrece retroalimentación clara, accesible y coherente.

> ℹ️ Puedes agregar más criterios si la funcionalidad lo requiere (por ejemplo: interoperabilidad, trazabilidad, rendimiento, accesibilidad, etc.)

---

### 🧩 Diseño Previo

> ℹ️ Se debe modelar el flujo funcional y técnico de esta característica mediante un **diagrama de secuencia dinámico en Structurizr**. Este diagrama será obligatorio como guía visual para el desarrollo y validación, representando la interacción entre:

* Usuario o actor
* Frontend (si aplica)
* Backend
* Base de datos u otros sistemas externos

> 🔗 El detalle de implementación técnica y arquitectura se completa en la sección de “Flujo o Arquitectura” de la plantilla TDD.

---

## 🔗 Dependencias

> ℹ️ Lista de módulos, endpoints, librerías u otros sistemas de los que depende esta característica:

* \[Ej: Servicio de autenticación configurado]
* \[Ej: API REST de catálogo de productos]
* \[Ej: Feature previa completada “Ver detalle de producto”]

> ℹ️ *También indicar si esta característica desbloquea o es prerequisito de otras.*

---

## 🛡️ Preocupaciones Transversales

**🔒 Seguridad**
ℹ️ Validaciones, roles de acceso, protección de datos, control de sesión, prevención de XSS/CSRF, etc.

**📈 Escalabilidad**
ℹ️ Consideraciones para crecimiento sostenido sin afectar rendimiento (caching, paginación, asincronía, etc.)

**🔄 Compatibilidad**
ℹ️ Alineación con versiones anteriores, navegación responsive, soporte multi-dispositivo, integración continua, etc.

> ℹ️ La implementación concreta de estas preocupaciones se detalla en la plantilla TDD (ver secciones de consideraciones técnicas y observaciones).

---

### 📌 Notas Adicionales

ℹ️ Usa esta sección para registrar cualquier aspecto importante del desarrollo:

* Decisiones tomadas con el equipo
* Riesgos técnicos o funcionales
* Consideraciones de rendimiento
* Limitaciones conocidas
* Reglas de negocio aún por definir
* Links a diseños (Figma, prototipos), documentación técnica u otros recursos
* 🔗 Documento técnico asociado: `/docs/tdd/[nombre-característica].md`

---

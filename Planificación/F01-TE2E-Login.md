# 📄 Tarea E2E - F01: Pruebas End-to-End del Login

---

#### **🧪 Validar el flujo completo de autenticación desde la interfaz hasta la API usando Playwright**

* **🎯 Objetivo:**
  Esta tarea tiene como propósito validar, mediante pruebas automatizadas con Playwright, que el inicio de sesión en el sistema GEIL funciona correctamente. Las pruebas simularán acciones reales de usuario para verificar credenciales, redirecciones, almacenamiento del token, restricción de acceso a rutas protegidas, comportamiento de cierre de sesión y renovación automática del token tras su expiración.

---

## ✅ Escenarios de Prueba a Implementar

> Todos los siguientes tests deben implementarse en `tests/login.spec.ts`.

---

### 1. `test_login_success_redirects_and_stores_token`

* Ingresar correo y contraseña válidos.
* Verificar redirección a `/dashboard`.
* Confirmar existencia del `access_token` en `localStorage`.

---

### 2. `test_login_invalid_credentials_shows_error`

* Ingresar contraseña incorrecta.
* Validar que se muestre el mensaje: `"Credenciales inválidas"`.

---

### 3. `test_login_inactive_user_blocked`

* Intentar acceder con usuario desactivado.
* Verificar mensaje: `"Cuenta inactiva"` o `"No autorizado"`.

---

### 4. `test_missing_fields_prevents_submission`

* Enviar formulario con campos vacíos.
* Validar que se muestran errores de campo requerido y no se realiza la petición.

---

### 5. `test_protected_route_redirects_to_login_if_no_token`

* Acceder directamente a `/dashboard` sin autenticarse.
* Verificar redirección automática a `/login`.

---

### 6. `test_token_persisted_after_reload`

* Hacer login exitoso.
* Recargar la página.
* Confirmar que el usuario sigue autenticado y permanece en `/dashboard`.

---

### 7. `test_logout_clears_token_and_redirects_to_login`

* Hacer login y luego cerrar sesión.
* Confirmar que:

  * Se elimina el token del `localStorage`.
  * El sistema redirige al login.

---

### 8. `test_refresh_token_renews_access_token_automatically` ⬜

* Hacer login y simular expiración del `access_token`.
* Interactuar con una ruta protegida.
* Verificar que se haya renovado automáticamente el `access_token` y que el usuario permanece autenticado.

---

### 9. `test_expired_refresh_token_redirects_to_login` ⬜

* Hacer login y luego simular expiración de ambos tokens.
* Acceder a una ruta protegida.
* Verificar redirección a `/login`.

---

### 10. `test_failed_request_retried_after_refresh` ⬜

* Simular un 401 por `access_token` vencido.
* Verificar que la petición se reintenta tras renovación exitosa con `refresh_token`.

---

## 📌 Requisitos Previos

* Backend disponible en `http://localhost:8000`.
* Frontend ejecutándose en `http://localhost:3000`.
* Base de datos de prueba con:

  * Usuario activo con credenciales conocidas.
  * Usuario inactivo.

---

## 🧰 Sugerencias Técnicas

* Usar `test.step` para describir fases del test.
* Definir función utilitaria `loginAs(email, password)` para evitar duplicación.
* Considerar `test.use({ storageState })` si se desea persistir sesión entre tests.
* Agregar etiquetas `@auth` para ejecución selectiva o filtrada.

---
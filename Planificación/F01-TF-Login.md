# 📄 Tarea F01-FE-Login: Implementar formulario de autenticación en frontend con soporte de renovación automática

---

#### **🎯 Objetivo general (acción 1):**

Desarrollar la interfaz de inicio de sesión en el frontend del sistema GEIL, conectada a un backend simulado y luego real. Se debe permitir el ingreso con correo y contraseña, validar los datos, emitir tokens y almacenarlos según la opción `"Recuérdame"`, así como implementar la renovación automática del `access_token` mediante un `refresh_token`.

---

### 🔴 Ciclo 1 – Objetivo general (🔗 Prueba de integración)

#### 🔴 **Prueba Inicial (Red):**

* \[✔] `test_login_success_stores_token`
  Valida que al enviar credenciales válidas se almacena el `access_token` en el store correctamente.

#### 🟢 **Implementación mínima (Green):**

* \[✔] Crear formulario `LoginForm.vue`, servicio de autenticación simulado, y store con `Pinia`.

#### 🔵 **Commit 1:**

```bash
git commit -m "feat(login): formulario con validación y autenticación simulada"
```

#### 🛠️ **Refactorización:**

* \[✔] Extraer lógica de validación, separar componente de página y store.

#### 🔵 Commit 2:

```bash
git commit -m "refactor(login): separación en componentes y mejoras en validación"
```

---

## 🔁 Acciones Secundarias (cada una con su ciclo TDD)

---

### 🔁 **\[✔] Acción 2: Validar campos del formulario**

* **🎯 Objetivo local:**
  Asegurar que email y contraseña sean requeridos y que el email tenga formato válido.

#### 🔴 Prueba Inicial (Red):

* \[✔] `test_login_form_validation_shows_errors`

#### 🟢 Implementación mínima:

* \[✔] Reglas en `useLoginValidation.ts`.

#### 🔵 Commit 1:

```bash
git commit -m "feat(validation): validación de campos del formulario de login"
```

#### 🛠️ Refactorización:

* \[✔] Centralizar reglas reusables.

#### 🔵 Commit 2:

```bash
git commit -m "refactor(validation): centralización en composable"
```

---

### 🔁 **\[✔] Acción 3: Implementar almacenamiento de tokens según 'rememberMe'**

* **🎯 Objetivo local:**
  Si el usuario marca `"Recuérdame"`, guardar el token en `localStorage`, si no, en `sessionStorage`.

#### 🔴 Prueba Inicial (Red):

* \[✔] `test_remember_me_stores_token_correctly`
* \[✔] `LoginForm.vue` emite correctamente el valor del checkbox.
* \[✔] Test UI: `debe emitir rememberMe como true si se marca el checkbox`.

#### 🟢 Implementación mínima:

* \[✔] Checkbox integrado en `LoginForm.vue`.
* \[✔] Adaptación de `authStore.login(...)` y `tokenStorage`.

#### 🔵 Commit 1:

```bash
git commit -m "feat(auth): almacenamiento condicional del token según rememberMe"
```

#### 🛠️ Refactorización:

* \[✔] Delegación del almacenamiento desde componente hasta utilitario.
* \[✔] Refactor de `saveTokens(...)` para admitir persistencia configurable.

#### 🔵 Commit 2:

```bash
git commit -m "refactor(auth): soporte completo rememberMe y limpieza de tokenStorage"
```

---

### 🔁 **\[✔] Acción 4: Renovar automáticamente el `access_token` con `refresh_token`**

* **🎯 Objetivo local:**
  Detectar expiración de `access_token` e invocar endpoint `/auth/refresh` para obtener uno nuevo sin interrumpir la sesión.

#### 🔴 Prueba Inicial (Red):

* \[✔] `test_access_token_auto_renewed_on_expiration`

#### 🟢 Implementación mínima:

* \[✔] Interceptor de Axios + `tokenRefreshService.ts`

#### 🔵 Commit 1:

```bash
git commit -m "feat(auth): renovación automática del token mediante refresh_token"
```

#### 🛠️ Refactorización:

* \[✔] Extraer lógica de persistencia en `utils/tokenStorage.ts`

#### 🔵 Commit 2:

```bash
git commit -m "refactor(auth): centraliza lógica de almacenamiento de tokens en utilitario compartido"
```

---

### 🔁 **\[✔] Acción 5: Redirigir al login si la renovación falla**

* **🎯 Objetivo local:**
  Si el `refresh_token` ha expirado o es inválido, borrar sesión y redirigir a `/login`.

#### 🔴 Prueba Inicial (Red):

* \[✔] `test_redirect_to_login_on_failed_token_refresh`

#### 🟢 Implementación mínima:

* \[✔] Manejo de autenticación en interceptor de `axiosInstance`, uso de `store.logout()` y redirección directa con `router.push('/login')`.

#### 🔵 Commit 1:

```bash
git commit -m "feat(auth): redirección a login si el refresh_token falla"
```

#### 🛠️ Refactorización:

* \[✔] Reemplazar importación dinámica de `router` para permitir pruebas.
* \[✔] Añadir soporte tipado para `refreshToken` en `AuthState`.

#### 🔵 Commit 2:

```bash
git commit -m "refactor(auth): redirección a /login testeable al fallar refresh_token y soporte tipado completo"
```

---

### 🧪 **Cobertura y Validación Final:**

* \[✔] Login exitoso y almacenamiento de token.
* \[✔] Feedback visual de error con credenciales inválidas.
* \[✔] Validación de campos obligatorios.
* \[✔] `rememberMe` en `localStorage` vs `sessionStorage`.
* \[✔] Persistencia tras reload.
* \[✔] Renovación automática al expirar `access_token`.
* \[✔] Redirección a `/login` si falla el refresh.
* \[✔] Reintento de peticiones protegidas tras renovación exitosa.

---

### 📝 Notas Adicionales sobre la Tarea

* El backend ya tiene implementado el endpoint `/auth/login` y en progreso `/auth/refresh` (ver tarea B-Login).
* Las pruebas E2E asociadas están definidas en la tarea `F01-TE2E-Login`.
* Se utiliza MSW para simular el backend durante los tests automáticos.

---
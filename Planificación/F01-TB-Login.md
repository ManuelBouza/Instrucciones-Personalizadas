# 📄 Tarea B-Login: Implementar backend completo de autenticación con JWT, logs de seguridad y renovación automática de token

---

#### **🎯 Objetivo general (acción 1):**

Permitir a los usuarios iniciar sesión de forma segura mediante correo y contraseña utilizando OAuth2 (Password Grant). Se debe emitir un `access_token` y registrar el intento en la base de datos. Este flujo es esencial para el control de acceso inicial al sistema GEIL.

---

### 🔴 Ciclo 1 – Objetivo general (🔗 Prueba de integración)

#### 🔴 **Prueba Inicial (Red):**

* \[✔] `test_login_success_returns_token` – Verifica que el login con credenciales válidas devuelve un JWT y responde con HTTP 200.

#### 🟢 **Implementación mínima (Green):**

* \[✔] Endpoint `/auth/login` con validación y emisión de token.

#### 🔵 **Commit 1:**

```bash
git commit -m "feat(auth): implementar login OAuth2 con emisión de JWT"
```

#### 🛠️ **Refactorización:**

* \[✔] Extraer funciones auxiliares de seguridad, tipado estricto, early return.

#### 🔵 **Commit 2:**

```bash
git commit -m "refactor(auth): limpieza y organización interna del flujo de login"
```

---

## 🔁 Acciones Secundarias (cada una con su ciclo TDD)

---

### 🔁 **\[✔] Acción 2: Validar credenciales cifradas con bcrypt**

* **🎯 Objetivo local:**
  Comparar la contraseña en texto plano contra el `password_hash` almacenado usando `bcrypt`.

#### 🔴 **Prueba Inicial (Red):**

* \[✔] `test_check_password_invalid_raises_error`

#### 🟢 **Implementación mínima (Green):**

* \[✔] Función `verify_password(...)` con `bcrypt.checkpw`

#### 🔵 **Commit 1 de acción:**

```bash
git commit -m "feat(auth): validación de credenciales con bcrypt"
```

#### 🛠️ **Refactorización local:**

* \[✔] Añadir type hints, docstrings.

#### 🔵 **Commit 2 de acción:**

```bash
git commit -m "refactor(auth): limpieza de verificación de contraseña"
```

---

### 🔁 **\[✔] Acción 3: Registrar logs de seguridad en base de datos**

* **🎯 Objetivo local:**
  Guardar en la tabla `security_log` el resultado del intento de autenticación: éxito o fallo, con IP y dispositivo.

#### 🔴 **Prueba Inicial (Red):**

* \[✔] `test_security_log_created_on_login_success_or_failure`

#### 🟢 **Implementación mínima (Green):**

* \[✔] Función `create_security_log(...)`

#### 🔵 **Commit 1 de acción:**

```bash
git commit -m "feat(log): registrar logs de intentos de login"
```

#### 🛠️ **Refactorización local:**

* \[✔] Extraer `get_client_ip()` de la request

#### 🔵 **Commit 2 de acción:**

```bash
git commit -m "refactor(log): funciones auxiliares para logging de seguridad"
```

---

### 🔁 **\[✔] Acción 4: Implementar generación y verificación de `refresh_token`**

* **🎯 Objetivo local:**
  Emitir y validar un `refresh_token` como mecanismo de renovación segura de sesión, asegurando su correcto formato, duración y tipo.

#### 🔴 **Prueba Inicial (Red):**

* \[✔] `test_refresh_token_can_be_verified_and_used`

#### 🟢 **Implementación mínima (Green):**

* \[✔] Funciones `create_refresh_token(...)` y `verify_refresh_token(...)` en `core/security.py`, con validación del tipo `"refresh"`.

#### 🔵 **Commit 1 de acción:**

```bash
git commit -m "feat(token): generación y validación de refresh_token"
```

#### 🛠️ **Refactorización local:**

* \[✔] Reutilizar lógica de generación de tokens mediante función `_build_token(...)`.
* \[✔] Uso de `Enum TokenType` para evitar hardcoded strings (`ruff S106`).

#### 🔵 **Commit 2 de acción:**

```bash
git commit -m "refactor(token): unificar lógica de emisión de tokens y evitar hardcoded con Enum TokenType"
```

---

### 🔁 **\[✔] Acción 5: Crear endpoint /auth/refresh para renovar tokens**

* **🎯 Objetivo local:**
  Permitir a los usuarios renovar su `access_token` usando un `refresh_token` válido, sin tener que volver a ingresar credenciales.

#### 🔴 **Prueba Inicial (Red):**

* \[✔] `test_refresh_token_success_returns_new_tokens`

#### 🟢 **Implementación mínima (Green):**

* \[✔] Endpoint `POST /auth/refresh` que valide el `refresh_token` recibido en el cuerpo y devuelva un nuevo `access_token`.

#### 🔵 **Commit 1 de acción:**

```bash
git commit -m "feat(auth): endpoint para renovación automática de sesión"
```

#### 🛠️ **Refactorización local:**

* \[✔] Preparar soporte futuro para validación de unicidad o rotación del `refresh_token` si se llegara a almacenar en base de datos.

#### 🔵 **Commit 2 de acción:**

```bash
git commit -m "refactor(auth): preparar lógica para posible rotación de refresh_token"
```


Aquí tienes la Tarea `B-Login` **actualizada e integrada con la nueva Acción 6**, diseñada formalmente con su ciclo TDD completo:

---

### 🔁 **\[✔] Acción 6: Incluir `refresh_token` en la respuesta del login**

* **🎯 Objetivo local:**
  Incluir en la respuesta del endpoint `/auth/login` tanto el `access_token` como el `refresh_token`, para permitir la renovación automática de sesión desde el frontend sin requerir otro paso previo.

#### 🔴 **Prueba Inicial (Red):**

* \[✔] `test_login_response_contains_refresh_token` – Verifica que la respuesta del login contiene `access_token`, `refresh_token` y el tipo correcto.

#### 🟢 **Implementación mínima (Green):**

* \[✔] Modificar el esquema `LoginResponse` para incluir el campo `refresh_token`.
* \[✔] Generar `refresh_token` en el endpoint `/auth/login` tras la validación del usuario.
* \[✔] Incluir ambos tokens en la respuesta.

#### 🔵 **Commit 1 de acción:**

```bash
git commit -m "feat(auth): incluir refresh_token en la respuesta del login"
```

#### 🛠️ **Refactorización local (opcional):**

* \[✔] Centralizar la lógica de emisión de `access_token` y `refresh_token` en una función auxiliar para evitar duplicación entre login y `/auth/refresh`.


#### 🔵 **Commit 2 de acción:**

```bash
git commit -m "refactor(auth): centralizar lógica de emisión de tokens múltiples"
```
---

### 🧪 **Cobertura y Validación Final:**

* \[✔] Login válido y emisión de token
* \[✔] Contraseña incorrecta → error
* \[✔] Usuario inactivo → error
* \[✔] Datos incompletos → error
* \[✔] Logs en `security_log`
* \[✔] Prueba de `get_client_ip`
* \[✔] Renovación exitosa con `refresh_token`
* \[✔] Token inválido o expirado
* \[✔] Token sin sub → error
* \[✔] Todos los tests actuales pasan con `pytest`

---

### 📝 Notas Adicionales sobre la Tarea

* Backend funcional para login con seguridad y trazabilidad.
* Se recomienda desarrollar Acción 4 y 5 antes de comenzar integración completa con el frontend.
* Actualmente **no se almacenan los `refresh_tokens` en base de datos**, por lo que no es posible invalidarlos o revocarlos de forma individual.
* En una implementación futura se podría incluir una tabla `session` o `token_store` para permitir:

  * Revocación manual de sesiones específicas.
  * Control de unicidad y rotación de `refresh_token`.
  * Auditoría de sesiones activas.

---
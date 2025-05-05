# 📄 Plantilla de Tarea para FDD + TDD por Acciones (🔁 Ciclo completo por cada paso)

---

#### **\[ ] Tarea \[N]: \[Nombre breve y descriptivo de la tarea]**

* **🎯 Objetivo general (acción 1):**
  \[Describir el propósito global de la tarea, su impacto dentro de la característica y qué comportamiento del sistema se busca validar.]

---

### 🔴 Ciclo 1 – Objetivo general (🔗 Prueba de integración)

#### 🔴 **Prueba Inicial (Red):**

* [ ] \[Escribir prueba de integración que valide el flujo general de la funcionalidad.]

#### 🟢 **Implementación mínima (Green):**

* [ ] \[Desarrollar lo mínimo necesario para que la prueba pase.]

#### 🔵 **Commit 1:**

```bash
git commit -m "feat: implementación inicial que pasa la prueba de integración"
```

#### 🛠️ **Refactorización:**

* [ ] Reorganizar código, eliminar duplicaciones, tipar, documentar.

#### 🔵 **Commit 2:**

```bash
git commit -m "refactor: mejoras internas tras pasar prueba de integración"
```

---

## 🔁 Acciones Secundarias (cada una con su ciclo TDD)

> Cada subacción debe definirse como una unidad atómica de funcionalidad. Repite el siguiente bloque por cada una:

---

### 🔁 **\[ ] Acción \[n]: \[Nombre de la acción específica]**

* **🎯 Objetivo local:**
  \[Qué hace esta acción y cómo contribuye al objetivo general.]

#### 🔴 **Prueba Inicial (Red):**

* [ ] \[Test unitario que valida la lógica específica de esta acción.]

#### 🟢 **Implementación mínima (Green):**

* [ ] \[Implementar la lógica necesaria para pasar el test.]

#### 🔵 **Commit 1 de acción:**

```bash
git commit -m "feat: [acción] pasa test unitario correspondiente"
```

#### 🛠️ **Refactorización local:**

* [ ] Reestructurar esta parte sin alterar funcionalidad.

#### 🔵 **Commit 2 de acción:**

```bash
git commit -m "refactor: mejoras internas en [acción específica]"
```

---

### 🧪 **Cobertura y Validación Final:**

* [ ] Test de casos válidos
* [ ] Test de errores o inputs inválidos
* [ ] Test de casos extremos o borde
* [ ] Validación de flujos alternativos (si aplica)
* [ ] Confirmar que **todas las pruebas** pasan (`vitest`, `pytest`, etc.)

---

### 📝 Notas Adicionales sobre la Tarea

\[Información extra relevante, como riesgos, decisiones del equipo o requisitos especiales.]

---

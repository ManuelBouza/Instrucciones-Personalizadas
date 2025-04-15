### **Plantilla de Características para FDD + TDD**

#### **[Nombre de la Característica]**  
**Descripción:**  
[Explica de manera concisa el propósito y funcionalidad de la característica dentro del sistema.]

---

**Rama Git asociada:** `feature/[nombre-característica]`  

---

**Prioridad:**  [Alta | Media | Baja]  
**Estimación de Esfuerzo:**  [Aproximación del tiempo requerido en horas o días.]  

---

### **Criterios de Aceptación:**  
La característica se considerará completada cuando se cumplan los siguientes criterios:  
- [ ] [Descripción clara de validación funcional]  
- [ ] [Comportamiento esperado]  
- [ ] [Cobertura de pruebas automatizadas]

---

### **Tareas Desglosadas (siguiendo la metodología TDD):**

#### **[ ] Tarea 1: [Descripción clara y concisa de la tarea]**
- **Objetivo:** [Qué se espera lograr con esta tarea.]  
Tareas Desglosadas (siguiendo la metodología TDD)- **Acciones a realizar:**  
  - [ ] Escribir pruebas automatizadas.  
  - [ ] Implementar funcionalidad.  
  - [ ] Refactorizar si es necesario.  
- **Pruebas Asociadas:**  
  - [ ] [Prueba: qué valida y qué se espera]  
  - [ ] [Prueba: qué valida y qué se espera]  
- **Commit final sugerido:**  
  - `git commit -m "feat: [descripción de la funcionalidad implementada cumpliendo TDD]"`

---

#### **[ ] Tarea 2: [Descripción clara y concisa de la tarea]**
- **Objetivo:** [Qué se espera lograr con esta tarea.]  
- **Acciones a realizar:**  
  - [ ] Escribir pruebas automatizadas.  
  - [ ] Implementar funcionalidad.  
  - [ ] Refactorizar si es necesario.  
- **Pruebas Asociadas:**  
  - [ ] [Prueba: qué valida y qué se espera]  
  - [ ] [Prueba: qué valida y qué se espera]  
- **Commit final sugerido:**  
  - `git commit -m "feat: [descripción de la funcionalidad implementada cumpliendo TDD]"`

---

#### **[ ] Tarea 3: [Descripción clara y concisa de la tarea]**
- **Objetivo:** [Qué se espera lograr con esta tarea.]  
- **Acciones a realizar:**  
  - [ ] Escribir pruebas automatizadas.  
  - [ ] Implementar funcionalidad.  
  - [ ] Refactorizar si es necesario.  
- **Pruebas Asociadas:**  
  - [ ] [Prueba: qué valida y qué se espera]  
  - [ ] [Prueba: qué valida y qué se espera]  
- **Commit final sugerido:**  
  - `git commit -m "feat: [descripción de la funcionalidad implementada cumpliendo TDD]"`

---

### **Dependencias:**  
- [Dependencia 1]  
- [Dependencia 2]

---

### **Preocupaciones Transversales:**  
- **Seguridad:** [Consideraciones de seguridad específicas.]  
- **Escalabilidad:** [Aspectos técnicos a considerar para escalar.]  
- **Compatibilidad:** [Con otros sistemas o versiones anteriores.]

---

### **Notas Adicionales:**  
[Cualquier información extra relevante, como riesgos, comentarios del equipo o requisitos especiales.]

---

### **Instrucciones para Usar la Plantilla:**  
1. Completa cada sección con información específica.  
2. Cada tarea debe seguir TDD:  
   - **Red** → prueba que falla  
   - **Green** → implementación mínima  
   - **Refactor** → mejoras de código  
3. Haz **un único commit final** por tarea:  
   - `feat: [descripción de lo desarrollado cumpliendo TDD]`  
4. Marca tareas y pruebas completadas con `[x]`.  
5. Usa `feature/[nombre-característica]` como nombre de rama.  
6. Integra esta plantilla con tu gestor de proyectos.  
7. Revisa y discute con el equipo antes de mergear.

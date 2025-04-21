### Plantilla de Tarea para FDD + TDD (Enfoque Red → Green → Refactor)

#### **[ ] Tarea [N]: [Nombre breve y descriptivo de la tarea]**

- **Objetivo:**  
  [Describir detalladamente el propósito de la tarea, su impacto dentro de la característica y qué comportamiento del sistema se busca validar y garantizar. El objetivo debe incluir el contexto funcional y técnico, y reflejar el valor que aporta al usuario final o a la arquitectura del sistema.]

---

- **Pruebas Iniciales (Red):**  
  [Define explícitamente las pruebas que deben escribirse **antes** de implementar la funcionalidad. Estas deben representar casos relevantes, útiles y medibles que en primera instancia **deberán fallar**.]  
  - [ ] [Prueba 1: qué valida y cuál es el resultado esperado]  
  - [ ] [Prueba 2: qué valida y cuál es el resultado esperado]  

---

- **Acciones para Hacer Pasar las Pruebas (Green):**  
  [Describe las acciones mínimas necesarias para implementar la lógica que permita que las pruebas anteriores pasen exitosamente. No se busca perfección, sino funcionalidad básica y verificable.]  
  - [ ] [Implementar funcionalidad base]  
  - [ ] [Integrar con otros componentes si es necesario]

---

- **Refactorización (Refactor):**  
  [Define las mejoras previstas para aplicar al código una vez que todas las pruebas pasen. Estas acciones buscan mejorar la legibilidad, mantenibilidad, rendimiento o adherencia a principios como SOLID sin alterar el comportamiento funcional.]  
  - [ ] [Reorganizar funciones, eliminar duplicación, mejorar nombres, etc.]

---

- **Verificación Final:**  
  - [ ] Ejecutar nuevamente **todas las pruebas automáticas** para asegurar que:  
    - Todas las pruebas nuevas pasan.  
    - No se ha roto ninguna prueba existente.  
    - El comportamiento del sistema sigue siendo consistente.

---

- **Commit final sugerido:**  
  - `git commit -m "feat: [descripción clara de la funcionalidad implementada cumpliendo TDD]"`

---

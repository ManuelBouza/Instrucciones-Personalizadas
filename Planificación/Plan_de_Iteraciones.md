# Plan de Iteraciones - Sistema GEIL

---

## Iteración 1: Seguridad, Autenticación y Administración Inicial

**Objetivo:** Establecer autenticación básica, gestión inicial de usuarios, roles y empresas.  
**Duración estimada:** 1.5 semanas  

**Características incluidas:**

### Gestión de Seguridad y Autenticación
- Autenticar acceso del usuario mediante correo electrónico y contraseña.
- Cerrar la sesión del usuario en el sistema.
- Certificado (buscar el mejor lugar para esta tarea)

### Gestión de Usuarios
- Registrar nuevo usuario con rol asignado.
- Visualizar la lista de usuarios registrados.
- Editar la información personal de un usuario.

### Gestión del Perfil de Usuario
- Visualizar la información del perfil del usuario autenticado.

### Gestión de Roles
- Asignar o revocar roles a usuarios existentes.
- Validar el acceso según tipo de rol asignado.

### Gestión de Empresas
- Crear una nueva empresa del sector turístico.
- Visualizar detalles de empresas registradas.
- Editar la información de una empresa registrada.

---

## Iteración 2: Configuración del Modelo MRL y Registro de Logs

**Objetivo:** Crear estructura lógica para evaluaciones y habilitar trazabilidad básica del sistema.  
**Duración estimada:** 1.5 semanas  

**Características incluidas:**

### Gestión de Módulos
- Crear un nuevo módulo de evaluación.
- Visualizar la lista de módulos registrados.
- Editar la información de un módulo existente.

### Gestión de Tipologías
- Crear nuevas tipologías de evaluación.
- Visualizar tipologías creadas.
- Editar información de una tipología existente.

### Gestión de Descriptores
- Agregar un descriptor a un módulo determinado.
- Visualizar la lista de descriptores por módulo.
- Editar la información de un descriptor agregado.

### Gestión de Logs del Sistema
- Registrar logs de acceso con IP, fecha, acción y dispositivo.
- Buscar logs por usuario, fecha o acción u otros valores identificativos.

---

## Iteración 3: Gestión de Evaluaciones y Respuestas

**Objetivo:** Habilitar flujo de trabajo real sobre las empresas evaluadas.  
**Duración estimada:** 1.5 semanas  

**Características incluidas:**

### Gestión de Evaluaciones
- Crear evaluaciones asociadas a una o varias empresas.
- Editar datos de una evaluación creada.
- Visualizar la lista de evaluaciones existentes por empresa o estado.

### Gestión de Respuestas a Evaluaciones
- Visualizar evaluaciones activas asignadas al usuario autenticado.
- Registrar respuestas con puntuaciones del 1 al 5 por descriptor con justificación opcional.
- Editar respuestas ingresadas en evaluaciones activas.

---

## Iteración 4: Reportes y Gráficos Básicos

**Objetivo:** Presentar y exportar resultados a través de visualizaciones iniciales.  
**Duración estimada:** 1.5 semanas  

**Características incluidas:**

### Generación de Reportes y Análisis Gráfico
- Calcular promedios por descriptor, módulo y empresa evaluada.
- Generar rankings de empresas según su desempeño logístico.
- Exportar reportes generados a archivo PDF.

### Visualización de Gráficos Especializados
- Generar gráficos de radar por empresa evaluada.
- Crear gráficos de barras comparativos por descriptor o módulo.
- Exportar reportes generados a archivo PDF.

---

## Iteración 5: Búsqueda, Filtros y Operaciones CSV

**Objetivo:** Incorporar búsqueda, filtrado e importación/exportación de información en entidades del sistema.  
**Duración estimada:** 2.5 semanas  

**Características incluidas:**  
(Ver versión completa para detalle por módulo)

Incluye funcionalidades de búsqueda, filtrado, importación y exportación CSV en:  
- Usuarios
- Perfil de usuario
- Roles
- Empresas
- Módulos
- Tipologías
- Descriptores

---

## Iteración 6: Evaluaciones y Respuestas Avanzadas

**Objetivo:** Mejorar la trazabilidad y acceso a información evaluativa.  
**Duración estimada:** 2 semanas  

**Características incluidas:**

### Evaluaciones
- Buscar evaluaciones por nombre u otros valores identificativos.
- Filtrar la lista de evaluaciones según estado (activo o inactivo).

### Respuestas a Evaluaciones
- Buscar respuestas específicas dentro de una evaluación.

---

## Iteración 7: Gestión de Notificaciones

**Objetivo:** Automatizar comunicaciones y alertas del sistema.  
**Duración estimada:** 1.5 semanas  

**Características incluidas:**

### Notificaciones
- Enviar enlace seguro al correo del usuario para restablecer su contraseña.
- Notificar la creación de nuevas evaluaciones a los usuarios asignados.
- Alertar el vencimiento de evaluaciones activas a los usuarios responsables.

---

## Iteración 8: Visualizaciones y Análisis Avanzado

**Objetivo:** Integrar análisis multivariable, temporal y comparativo.  
**Duración estimada:** 1.5 semanas  

**Características incluidas:**

### Reportes y Análisis
- Identificar fortalezas y debilidades de cada empresa evaluada.
- Comparar el desempeño entre empresas por módulo o descriptor.
- Analizar la evolución temporal de indicadores logísticos.
- Segmentar empresas según desempeño global.

### Gráficos Especializados
- Mapa de calor, líneas de tendencia y gráficos de dispersión avanzados.

---

## Iteración 9: Funcionalidades Adicionales

**Objetivo:** Incluir operaciones independientes que deben ser integradas tras completar reportes básicos.  
**Duración estimada:** 1 semana  

**Características incluidas:**

- Edición del perfil de usuario.
- Importación/exportación CSV en evaluaciones.
- Filtros avanzados en logs del sistema.

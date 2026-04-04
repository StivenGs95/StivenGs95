# Sprint 1 – ComuniApp

**Duración:** 1 semana  
**Repositorio de prueba:** [`StivenGs95/StivenGs95`](https://github.com/StivenGs95/StivenGs95)  
**Project (tablero de sprint):** [GitHub Project #5](https://github.com/users/StivenGs95/projects/5)

---

## Objetivo del Sprint

Iniciar la construcción del proyecto con un sistema inicial y funcional de registro e inicio de sesión, construyendo cada proceso para su gestión: bases de datos, visualizaciones y enrutamientos.

**Resultado esperado:**

- Login funcional (frontend + backend + BD).
- Vista principal accesible solo para usuarios autenticados.
- Gestión básica de perfil de usuario.
- Flujo de login/logout completo.
- Base lista para comenzar el CRUD de publicaciones en el siguiente sprint.

---

## Desglose de Tareas

### 1. Configuración Inicial

| # | Tarea | Descripción |
|---|-------|-------------|
| 1 | Crear repositorio de prueba para ComuniApp | Crear estructura básica dentro del repo `StivenGs95/StivenGs95`. Añadir `README.md` con descripción del objetivo. Configurar `.gitignore` según el stack. |
| 2 | Configurar entorno de desarrollo | Definir stack (frontend, backend, BD). Inicializar proyecto. Añadir instrucciones de instalación y ejecución en el `README.md`. Verificar que el proyecto corre localmente. |
| 3 | Definir estructura inicial del sistema | Crear estructura de carpetas (`backend/`, `frontend/`, `routes/`, `models/`, etc.). Definir rutas mínimas: `/login`, `/register`, `/home`. Crear layout base (plantilla o componente principal). |

---

### 2. Autenticación

| # | Tarea | Descripción |
|---|-------|-------------|
| 4 | Definir modelo de datos para usuarios y logins | Diseñar tabla `users` (id, nombre, email, contraseña hasheada, imagen, timestamps). Crear migraciones o script SQL. Ver [`docs/database.md`](./database.md) para el esquema completo. |
| 5 | Implementar endpoint backend de login | Endpoint `POST /api/login`. Validar credenciales contra tabla `users`. Responder con token/sesión. Manejo de errores (usuario no encontrado, contraseña incorrecta). |
| 6 | Implementar vista de inicio de sesión (UI) | Formulario con usuario/email y contraseña. Validaciones básicas en cliente. Llamar al endpoint de login. Redirigir a `/home` si el login es exitoso. |
| 7 | Mensajes de éxito y error en autenticación | Mostrar feedback visual claro: éxito → redirige al dashboard; error de credenciales → mensaje amigable; error de servidor → mensaje genérico. |

---

### 3. Vista Principal de la Aplicación

| # | Tarea | Descripción |
|---|-------|-------------|
| 8 | Crear layout principal con menú o sidebar | Componente principal con menú/sidebar. Opciones mínimas: "Publicaciones", "Perfil", "Cerrar sesión". Solo accesible con sesión activa (rutas protegidas). |
| 9 | Tablero dinámico inicial para publicaciones | Vista central con mensaje placeholder "Aquí irán las publicaciones". Preparar estructura para listar publicaciones. Integrar con el menú/sidebar. |
| 10 | Gestión básica de usuario (perfil) | Vista de perfil: nombre, email, imagen. Permitir actualizar nombre y contraseña. Subida de imagen (opcional o simulada en este sprint). |
| 11 | Gestión de logins – Cerrar sesión | Limpiar token/sesión en frontend. Invalidar token en backend (opcional). Redirigir al login al cerrar sesión. |

---

### 4. Pruebas

| # | Tarea | Descripción |
|---|-------|-------------|
| 12 | Pruebas de autenticación | Probar flujo de login: éxito, contraseña incorrecta, usuario inexistente. Ver casos detallados en [`docs/tests-auth.md`](./tests-auth.md). |
| 13 | Pruebas de navegación y vista principal | Confirmar que usuario no autenticado no accede al dashboard. Probar flujo de cierre de sesión. Verificar navegación entre secciones. |
| 14 | Corrección de bugs visuales y funcionales | Registrar bugs encontrados. Corregir errores críticos de autenticación y navegación. Ajustar detalles visuales que afecten usabilidad. |

---

## Mapeo al Project `projects/5`

### Columnas / Estados sugeridos

El Project `https://github.com/users/StivenGs95/projects/5` debe tener tres estados:

| Estado | Descripción |
|--------|-------------|
| **Por hacer** | Tareas pendientes de iniciar en el sprint |
| **En progreso** | Tareas actualmente en desarrollo |
| **Hecho** | Tareas completadas y validadas |

---

### Lista de ítems recomendados para el Project

Cada ítem se puede crear como **Issue vinculado al repo** `StivenGs95/StivenGs95` o como **Draft item** en el Project.

```
[Sprint 1] Crear repositorio de prueba para ComuniApp
[Sprint 1] Configurar entorno de desarrollo (stack + dependencias)
[Sprint 1] Definir estructura inicial del sistema (carpetas, rutas base)
[Sprint 1] Definir modelo de datos para usuarios y logins
[Sprint 1] Implementar endpoint backend de login (autenticación interna)
[Sprint 1] Implementar vista de inicio de sesión (UI)
[Sprint 1] Mensajes de éxito y error en autenticación
[Sprint 1] Crear layout principal con menú o sidebar
[Sprint 1] Tablero dinámico inicial para publicaciones (placeholder)
[Sprint 1] Gestión básica de usuario (perfil)
[Sprint 1] Gestión de logins – Cerrar sesión
[Sprint 1] Pruebas de autenticación
[Sprint 1] Pruebas de navegación y vista principal
[Sprint 1] Corrección de bugs visuales y funcionales del Sprint 1
```

---

### Pasos para configurar el Project manualmente

#### Opción A: Crear Issues vinculados (recomendado)

1. Ir a `https://github.com/StivenGs95/StivenGs95/issues/new`
2. Crear un issue por cada tarea de la lista anterior.
3. Asignar la etiqueta `sprint-1` y el milestone `Sprint 1` (créalos si no existen).
4. En el panel lateral del issue, asignar el Project `#5`.
5. El issue aparecerá en el Project automáticamente.

#### Opción B: Draft items en el Project

1. Ir a `https://github.com/users/StivenGs95/projects/5`
2. Hacer clic en **+ Add item** en la columna **Por hacer**.
3. Escribir el título del ítem (por ejemplo `[Sprint 1] Crear repositorio de prueba`).
4. Presionar Enter para guardar.
5. Hacer clic en el ítem → **Edit details** → pegar la descripción correspondiente.
6. Para vincular al repo: abrir el ítem → **Convert to issue** → seleccionar `StivenGs95/StivenGs95`.

---

### Referencia del Project

- **ID del Project:** `#5`
- **URL:** `https://github.com/users/StivenGs95/projects/5`
- **Repositorio de prueba:** `https://github.com/StivenGs95/StivenGs95`

---

## Archivos de referencia

| Archivo | Descripción |
|---------|-------------|
| [`docs/sprint-1-comuniapp.md`](./sprint-1-comuniapp.md) | Este documento: desglose y mapeo del Sprint 1 |
| [`docs/database.md`](./database.md) | Diseño inicial de tablas para usuarios y logins |
| [`docs/tests-auth.md`](./tests-auth.md) | Casos de prueba manuales para el flujo de autenticación |

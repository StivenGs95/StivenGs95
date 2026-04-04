# ComuniApp – Sprint 1: Guía del Project Board

> **Project oficial:** [ComuniApp – GitHub Project \#5](https://github.com/users/StivenGs95/projects/5)  
> **Repositorio de prueba:** [`StivenGs95/StivenGs95`](https://github.com/StivenGs95/StivenGs95)  
> **Duración del Sprint 1:** 1 semana  
> **Objetivo:** Sistema inicial y funcional de registro e inicio de sesión, con base de datos, vistas y rutas mínimas.

---

## 1. Vistas del Project

El Project `https://github.com/users/StivenGs95/projects/5` ya cuenta con cuatro vistas predefinidas. A continuación se explica el propósito de cada una dentro del Sprint 1:

### 1.1 Prioritized Backlog
Lista plana de todos los items del proyecto ordenados por prioridad. En esta vista se gestionan las tareas pendientes del Sprint 1 de mayor a menor importancia, arrastrando las tarjetas para reordenarlas. Todos los items del sprint deben estar aquí antes de que el sprint comience.

### 1.2 Status Board
Tablero Kanban con tres columnas:

| Columna | Significado |
|---------|-------------|
| `Todo` | Tarea pendiente, lista para ser iniciada. Aquí empiezan **todas** las tareas del Sprint 1. |
| `In progress` | Tarea en ejecución activa. Mueve la tarjeta aquí cuando comiences a trabajar en ella. |
| `Done` | Tarea finalizada y validada. Mueve la tarjeta aquí al completar y cerrar el issue correspondiente. |

### 1.3 Current Iteration
Misma vista de tablero Kanban, filtrada automáticamente por la iteración activa. Una vez que configures una iteración en el Project (ej. "Sprint 1", 1 semana), esta vista mostrará únicamente las tareas del sprint en curso, sin mostrar el backlog de sprints futuros.

### 1.4 Roadmap
Vista de línea de tiempo. Permite asignar fechas de inicio y fin a los items o grupos de items. Para el Sprint 1, es útil para:
- Agregar un item o milestone `Sprint 1 – Autenticación ComuniApp` con la fecha de inicio y fin de la semana del sprint.
- Visualizar cuándo se espera completar cada bloque de trabajo (Configuración, Autenticación, Vista principal, Pruebas).

---

## 2. Tipos de items y cómo asociarlos al repositorio

### Issues vinculados (recomendado)
Crea cada tarea como un **Issue** en el repositorio `StivenGs95/StivenGs95`:
1. Ve a [`StivenGs95/StivenGs95 → Issues → New issue`](https://github.com/StivenGs95/StivenGs95/issues/new).
2. Escribe el título y la descripción sugeridos en la sección 3.
3. En la barra lateral del issue, busca **Projects** y selecciona `ComuniApp`.
4. El issue aparecerá automáticamente en el **Prioritized Backlog** y en el **Status Board** con estado `Todo`.

### Draft items (alternativa rápida)
Si prefieres crear items directamente desde el Project sin crear un issue:
1. Abre el Project: `https://github.com/users/StivenGs95/projects/5`.
2. En la vista **Prioritized Backlog**, haz clic en `+ Add item`.
3. Escribe el título y presiona Enter.
4. Para añadir la descripción, abre el item y edítalo.
5. Puedes convertir un draft item en issue real haciendo clic en **Convert to issue** y seleccionando el repo `StivenGs95/StivenGs95`.

---

## 3. Tareas del Sprint 1

Todas las tareas comienzan con **Status = `Todo`**. A medida que avances en el sprint, muévelas a `In progress` y luego a `Done`.

### Bloque 1 – Configuración inicial

#### Tarea 1 – Crear estructura base del proyecto ComuniApp
**Estado inicial:** `Todo`  
**Descripción:**
- Crear la estructura de carpetas del proyecto dentro del repositorio `StivenGs95/StivenGs95` (ej. `comuniapp/` o similar).
- Añadir `README.md` interno con descripción del objetivo del proyecto.
- Configurar `.gitignore` según el stack elegido (Node, Python, PHP, etc.).
- Documentar convenciones de ramas a usar (`main`, `develop`, feature branches).

---

#### Tarea 2 – Configurar entorno de desarrollo
**Estado inicial:** `Todo`  
**Descripción:**
- Definir stack tecnológico (ej. frontend React/Vue, backend Node/Laravel, BD PostgreSQL/MySQL).
- Inicializar proyecto (`npm init`, `composer create-project`, etc.).
- Crear archivo `.env.example` con las variables de entorno necesarias.
- Documentar pasos de instalación y ejecución en el `README.md`.

---

#### Tarea 3 – Definir estructura inicial del sistema
**Estado inicial:** `Todo`  
**Descripción:**
- Crear estructura de carpetas (`frontend/`, `backend/`, `src/`, `routes/`, `models/`, etc.).
- Definir rutas base: `/login`, `/register`, `/home` (como placeholders si es necesario).
- Crear layout base (plantilla HTML o componente principal) que se usará para la vista principal.

---

### Bloque 2 – Autenticación

#### Tarea 4 – Definir modelo de datos para usuarios
**Estado inicial:** `Todo`  
**Descripción:**
- Diseñar tabla `users`: `id`, `nombre`, `email`, `contraseña` (hasheada), `imagen` (opcional), `timestamps`.
- (Opcional) Tabla `logins` o registros de sesión: `id`, `user_id`, `fecha`, `ip`.
- Crear migraciones o script SQL para generar las tablas.
- Documentar el esquema en `docs/database.md`.

---

#### Tarea 5 – Implementar endpoint backend de login
**Estado inicial:** `Todo`  
**Descripción:**
- Endpoint de autenticación (ej. `POST /api/login`).
- Validar credenciales contra la tabla `users` (verificar hash de contraseña).
- Responder con token/sesión o datos de usuario mínimos.
- Manejo de errores: usuario no encontrado, contraseña incorrecta, error de servidor.

---

#### Tarea 6 – Implementar vista de inicio de sesión (UI)
**Estado inicial:** `Todo`  
**Descripción:**
- Formulario de login con campos usuario/email y contraseña.
- Validaciones básicas en el cliente (campos requeridos, formato email).
- Llamar al endpoint de login del backend al enviar el formulario.
- Redirigir a la vista principal (`/home`) si el login es exitoso.

---

#### Tarea 7 – Mensajes de éxito y error en autenticación
**Estado inicial:** `Todo`  
**Descripción:**
- Mostrar mensaje de éxito y redirigir al dashboard tras un login correcto.
- Mostrar mensaje de error claro si las credenciales son incorrectas.
- Manejar errores de red o servidor con mensajes genéricos amigables.

---

### Bloque 3 – Vista principal de la aplicación

#### Tarea 8 – Crear layout principal con menú o sidebar
**Estado inicial:** `Todo`  
**Descripción:**
- Componente principal con menú o sidebar.
- Opciones mínimas: "Publicaciones", "Perfil", "Cerrar sesión".
- Rutas protegidas: solo usuarios autenticados acceden a esta vista.

---

#### Tarea 9 – Tablero dinámico inicial para publicaciones (placeholder)
**Estado inicial:** `Todo`  
**Descripción:**
- Vista con área central que muestre un mensaje tipo "Aquí irán las publicaciones".
- Preparar estructura básica para listar publicaciones en el futuro.
- Integrar la vista con el menú/sidebar del layout principal.

---

#### Tarea 10 – Gestión básica de usuario (perfil)
**Estado inicial:** `Todo`  
**Descripción:**
- Vista de perfil: mostrar nombre, email e imagen del usuario autenticado.
- Permitir actualizar nombre y contraseña (flujo sencillo).
- Manejo de imagen de perfil (puede ser opcional o simulado en este sprint).

---

#### Tarea 11 – Gestión de logins – Cerrar sesión
**Estado inicial:** `Todo`  
**Descripción:**
- Botón/acción de "Cerrar sesión" visible en el menú/sidebar.
- Limpiar token/sesión en frontend (localStorage, context, cookies, etc.).
- (Opcional) Invalidar token en backend si aplica.
- Redirigir al usuario a la pantalla de login.

---

### Bloque 4 – Pruebas

#### Tarea 12 – Pruebas de autenticación
**Estado inicial:** `Todo`  
**Descripción:**
- Probar caso de éxito: usuario y contraseña correctos.
- Probar caso de fallo: contraseña incorrecta.
- Probar caso de fallo: usuario no registrado.
- Documentar los casos probados y resultados (ej. en `docs/tests-auth.md`).

---

#### Tarea 13 – Pruebas de navegación y vista principal
**Estado inicial:** `Todo`  
**Descripción:**
- Verificar que un usuario no autenticado no puede acceder a la vista principal.
- Probar navegación entre "Publicaciones", "Perfil" y "Cerrar sesión".
- Confirmar que el estado de autenticación se mantiene mientras la sesión esté activa.

---

#### Tarea 14 – Corrección de bugs visuales y funcionales del Sprint 1
**Estado inicial:** `Todo`  
**Descripción:**
- Registrar bugs encontrados durante las pruebas (en issues o en `docs/bugs-sprint1.md`).
- Corregir errores críticos de autenticación y navegación.
- Ajustar detalles visuales básicos que afecten la usabilidad.

---

### Resumen de resultado esperado

#### Tarea 15 – Resultado Sprint 1 – Módulo de autenticación funcional
**Estado inicial:** `Todo` → mover a `Done` al final del sprint  
**Descripción:**
- Login funcional: frontend + backend + base de datos.
- Vista principal accesible solo para usuarios autenticados.
- Gestión básica de perfil de usuario.
- Flujo de login/logout completo.
- Base preparada para comenzar el CRUD de publicaciones en el siguiente sprint.

---

## 4. Flujo de trabajo durante el Sprint

```
Prioritized Backlog (todas las tareas ordenadas por prioridad)
        │
        ▼
   Status Board
   ┌──────────┬────────────┬──────┐
   │   Todo   │ In progress│ Done │
   │ Tarea 1  │            │      │
   │ Tarea 2  │            │      │
   │  ...     │            │      │
   └──────────┴────────────┴──────┘
        │
        ▼
  Al iniciar una tarea → moverla a "In progress"
  Al terminarla       → moverla a "Done" y cerrar el issue
```

**Regla práctica:** no tener más de 2–3 tareas en `In progress` al mismo tiempo para evitar bloqueos.

---

## 5. Cómo acceder y configurar el Project paso a paso

1. **Abre el Project:**  
   `https://github.com/users/StivenGs95/projects/5`

2. **Crea los items:**  
   - Ve a la vista **Prioritized Backlog**.  
   - Haz clic en `+ Add item` al final de la lista.  
   - Escribe el título de cada tarea de la sección 3 y presiona Enter.  
   - Abre cada item creado para añadir la descripción correspondiente.

3. **Configura una iteración (para "Current iteration"):**  
   - Ve a **Settings** del Project → **Fields** → `+ Add field` → **Iteration**.  
   - Crea una iteración llamada `Sprint 1` con la fecha de inicio y fin de la semana.  
   - Asigna todas las tareas del sprint a esa iteración.

4. **Configura el Roadmap:**  
   - En la vista **Roadmap**, selecciona el campo de fecha o iteración para visualizar las tareas en la línea de tiempo.  
   - Opcionalmente, añade un item `Sprint 1 – Autenticación ComuniApp` con la duración completa del sprint.

5. **Durante el sprint:**  
   - Mueve las tarjetas entre columnas en el **Status Board** según el progreso.  
   - Al finalizar un issue, ciérralo desde `StivenGs95/StivenGs95` → el status se actualizará automáticamente a `Done`.

---

## 6. Referencias

| Recurso | URL |
|---------|-----|
| Project ComuniApp | https://github.com/users/StivenGs95/projects/5 |
| Repositorio de prueba | https://github.com/StivenGs95/StivenGs95 |
| Issues del repositorio | https://github.com/StivenGs95/StivenGs95/issues |
| Crear nuevo issue | https://github.com/StivenGs95/StivenGs95/issues/new |

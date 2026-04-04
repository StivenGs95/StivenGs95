# Casos de Prueba – Autenticación ComuniApp (Sprint 1)

**Repositorio:** [`StivenGs95/StivenGs95`](https://github.com/StivenGs95/StivenGs95)  
**Relacionado:** [Sprint 1](./sprint-1-comuniapp.md) · Tareas #12 y #13

---

## Convenciones

| Símbolo | Significado |
|---------|-------------|
| ✅ | Resultado esperado alcanzado |
| ❌ | Resultado esperado NO alcanzado (bug) |
| ⏳ | Pendiente de ejecutar |

Registrar el estado real al ejecutar cada caso en la columna **Resultado**.

---

## CP-AUTH: Flujo de Login

### CP-AUTH-01 – Login exitoso con credenciales válidas

| Campo | Detalle |
|-------|---------|
| **Precondición** | Existe un usuario con email `test@comuniapp.com` y contraseña `Test1234!` en la BD. |
| **Pasos** | 1. Abrir la pantalla de login. 2. Ingresar email: `test@comuniapp.com`. 3. Ingresar contraseña: `Test1234!`. 4. Hacer clic en "Iniciar sesión". |
| **Resultado esperado** | El sistema autentica al usuario y redirige a la vista principal (`/home`). Se muestra el nombre del usuario en el menú/sidebar. |
| **Resultado real** | ⏳ |
| **Observaciones** | |

---

### CP-AUTH-02 – Login fallido con contraseña incorrecta

| Campo | Detalle |
|-------|---------|
| **Precondición** | Existe el usuario `test@comuniapp.com` en la BD. |
| **Pasos** | 1. Abrir la pantalla de login. 2. Ingresar email: `test@comuniapp.com`. 3. Ingresar contraseña incorrecta: `WrongPass!`. 4. Hacer clic en "Iniciar sesión". |
| **Resultado esperado** | El sistema muestra un mensaje de error claro (ej. "Credenciales incorrectas"). No se redirige al usuario. |
| **Resultado real** | ⏳ |
| **Observaciones** | |

---

### CP-AUTH-03 – Login con usuario inexistente

| Campo | Detalle |
|-------|---------|
| **Precondición** | No existe el email `noexiste@comuniapp.com` en la BD. |
| **Pasos** | 1. Abrir la pantalla de login. 2. Ingresar email: `noexiste@comuniapp.com`. 3. Ingresar cualquier contraseña. 4. Hacer clic en "Iniciar sesión". |
| **Resultado esperado** | El sistema muestra un mensaje de error (ej. "Credenciales incorrectas"). No revela si el email existe o no (seguridad). |
| **Resultado real** | ⏳ |
| **Observaciones** | |

---

### CP-AUTH-04 – Login con campos vacíos

| Campo | Detalle |
|-------|---------|
| **Precondición** | Pantalla de login disponible. |
| **Pasos** | 1. Abrir la pantalla de login. 2. Dejar todos los campos vacíos. 3. Hacer clic en "Iniciar sesión". |
| **Resultado esperado** | El sistema muestra mensajes de validación en el cliente (ej. "El email es requerido", "La contraseña es requerida"). No se realiza ninguna petición al backend. |
| **Resultado real** | ⏳ |
| **Observaciones** | |

---

### CP-AUTH-05 – Login con formato de email inválido

| Campo | Detalle |
|-------|---------|
| **Precondición** | Pantalla de login disponible. |
| **Pasos** | 1. Ingresar email con formato inválido: `correosinformato`. 2. Ingresar cualquier contraseña. 3. Hacer clic en "Iniciar sesión". |
| **Resultado esperado** | El sistema muestra una validación de formato de email en el cliente antes de enviar la petición. |
| **Resultado real** | ⏳ |
| **Observaciones** | |

---

## CP-NAV: Navegación y Vista Principal

### CP-NAV-01 – Acceso directo a vista principal sin autenticación

| Campo | Detalle |
|-------|---------|
| **Precondición** | El usuario no ha iniciado sesión (sin token/sesión activa). |
| **Pasos** | 1. Intentar acceder directamente a la URL `/home` sin estar autenticado. |
| **Resultado esperado** | El sistema redirige al usuario a la pantalla de login (`/login`). |
| **Resultado real** | ⏳ |
| **Observaciones** | |

---

### CP-NAV-02 – Navegación entre secciones desde el menú

| Campo | Detalle |
|-------|---------|
| **Precondición** | El usuario está autenticado y en la vista principal. |
| **Pasos** | 1. Hacer clic en "Publicaciones" en el menú/sidebar. 2. Hacer clic en "Perfil" en el menú/sidebar. 3. Hacer clic en "Cerrar sesión". |
| **Resultado esperado** | 1. Carga el tablero de publicaciones. 2. Carga la vista de perfil del usuario. 3. Cierra sesión y redirige al login. |
| **Resultado real** | ⏳ |
| **Observaciones** | |

---

### CP-NAV-03 – Sesión activa persiste al recargar la página

| Campo | Detalle |
|-------|---------|
| **Precondición** | El usuario está autenticado y en la vista principal. |
| **Pasos** | 1. Recargar la página (F5 / Ctrl+R). |
| **Resultado esperado** | El usuario permanece autenticado y en la vista principal (no es redirigido al login). |
| **Resultado real** | ⏳ |
| **Observaciones** | |

---

## CP-LOGOUT: Cierre de Sesión

### CP-LOGOUT-01 – Cerrar sesión desde el menú

| Campo | Detalle |
|-------|---------|
| **Precondición** | El usuario está autenticado. |
| **Pasos** | 1. Hacer clic en "Cerrar sesión" en el menú/sidebar. |
| **Resultado esperado** | La sesión/token es invalidada. El usuario es redirigido al login. |
| **Resultado real** | ⏳ |
| **Observaciones** | |

---

### CP-LOGOUT-02 – Acceso a vista principal después de cerrar sesión

| Campo | Detalle |
|-------|---------|
| **Precondición** | El usuario acaba de cerrar sesión. |
| **Pasos** | 1. Intentar acceder a `/home` usando el botón "Atrás" del navegador o escribiendo la URL directamente. |
| **Resultado esperado** | El sistema detecta que no hay sesión activa y redirige al login. No se muestra contenido protegido. |
| **Resultado real** | ⏳ |
| **Observaciones** | |

---

## Registro de Bugs Detectados

| # | Descripción | Prioridad | Estado | Sprint |
|---|-------------|-----------|--------|--------|
| - | *(Sin bugs registrados aún)* | - | - | - |

> Actualizar esta tabla durante la ejecución de las pruebas del Sprint 1.

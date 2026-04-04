# Diseño de Base de Datos – ComuniApp (Sprint 1)

**Repositorio:** [`StivenGs95/StivenGs95`](https://github.com/StivenGs95/StivenGs95)  
**Relacionado:** [Sprint 1](./sprint-1-comuniapp.md) · Tarea #4

---

## Tablas principales

### Tabla `users`

Almacena la información de cada usuario registrado en la aplicación.

| Columna | Tipo | Restricciones | Descripción |
|---------|------|---------------|-------------|
| `id` | `BIGINT UNSIGNED` | PK, AUTO_INCREMENT | Identificador único del usuario |
| `name` | `VARCHAR(100)` | NOT NULL | Nombre completo del usuario |
| `email` | `VARCHAR(150)` | NOT NULL, UNIQUE | Correo electrónico (usado para login) |
| `password` | `VARCHAR(255)` | NOT NULL | Contraseña hasheada (bcrypt / argon2) |
| `profile_image` | `VARCHAR(255)` | NULLABLE | Ruta o URL de la imagen de perfil |
| `is_active` | `TINYINT(1)` | NOT NULL, DEFAULT 1 | Estado del usuario (1 = activo, 0 = inactivo) |
| `created_at` | `TIMESTAMP` | DEFAULT CURRENT_TIMESTAMP | Fecha de registro |
| `updated_at` | `TIMESTAMP` | DEFAULT CURRENT_TIMESTAMP ON UPDATE | Última modificación |

**Script SQL:**

```sql
CREATE TABLE users (
    id BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(150) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    profile_image VARCHAR(255) NULL,
    is_active TINYINT(1) NOT NULL DEFAULT 1,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
```

---

### Tabla `login_logs` *(opcional en Sprint 1)*

Registra los intentos de inicio de sesión para trazabilidad y auditoría.

| Columna | Tipo | Restricciones | Descripción |
|---------|------|---------------|-------------|
| `id` | `BIGINT UNSIGNED` | PK, AUTO_INCREMENT | Identificador del registro |
| `user_id` | `BIGINT UNSIGNED` | FK → `users.id`, NULLABLE | Usuario que intentó el login (NULL si el usuario no existe) |
| `email_attempted` | `VARCHAR(150)` | NOT NULL | Email que se usó en el intento |
| `ip_address` | `VARCHAR(45)` | NULLABLE | Dirección IP del cliente (IPv4 o IPv6) |
| `success` | `TINYINT(1)` | NOT NULL, DEFAULT 0 | 1 = login exitoso, 0 = fallido |
| `attempted_at` | `TIMESTAMP` | DEFAULT CURRENT_TIMESTAMP | Fecha y hora del intento |

**Script SQL:**

```sql
CREATE TABLE login_logs (
    id BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    user_id BIGINT UNSIGNED NULL,
    email_attempted VARCHAR(150) NOT NULL,
    ip_address VARCHAR(45) NULL,
    success TINYINT(1) NOT NULL DEFAULT 0,
    attempted_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE SET NULL
);
```

---

## Diagrama de relaciones (simplificado)

```
users
 ├── id (PK)
 ├── name
 ├── email
 ├── password
 ├── profile_image
 ├── is_active
 ├── created_at
 └── updated_at
       │
       │ 1 : N
       ▼
login_logs
 ├── id (PK)
 ├── user_id (FK → users.id)
 ├── email_attempted
 ├── ip_address
 ├── success
 └── attempted_at
```

---

## Notas de implementación

- **Contraseñas:** nunca almacenar en texto plano. Usar `bcrypt` (factor de costo ≥ 10) o `argon2id`.
- **Tokens de sesión:** si se usan JWTs, no almacenarlos en la tabla `users`; gestionarlos en memoria/cliente. Si se usan sesiones de servidor, considerar una tabla `sessions` en sprints futuros.
- **Índices recomendados:**
  - `users.email` ya tiene índice UNIQUE.
  - `login_logs.user_id` para búsquedas por usuario.
  - `login_logs.attempted_at` si se consultan logs por fecha.
- **Para sprint 2+:** añadir tabla `posts` con FK a `users.id` para el módulo de publicaciones.

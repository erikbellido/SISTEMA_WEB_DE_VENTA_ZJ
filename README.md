# Sistema Web de Ventas — Zapatería Joselito

Sistema web de ventas para la zapatería Joselito, compuesto por una API REST en
Spring Boot y una aplicación Angular.

## Stack tecnológico

| Capa | Tecnología |
|------|------------|
| Base de datos | Microsoft SQL Server (puerto 1433, BD `ZapateriaJoselito`) |
| Backend | Java 17, Spring Boot (Web, Data JPA, Security, Validation, Mail) |
| Frontend | Angular 17, TypeScript 5.2 |

## Estructura del proyecto

```
.
├── ZapateriaJoselito.sql      # Script de esquema y datos de la BD
├── backend/                   # API REST (Maven)
│   ├── pom.xml
│   └── src/main/java/...
└── frontend/                  # SPA Angular
    ├── package.json
    └── src/...
```

## Ejecutar el proyecto

**Backend** (requiere SQL Server corriendo en `localhost:1433`):

```bash
cd backend
./mvnw spring-boot:run     # o mvn spring-boot:run
```

**Frontend:**

```bash
cd frontend
npm install
npm start
```

## Flujo de trabajo Git (2 desarrolladores)

Repositorio: <https://github.com/erikbellido/SISTEMA_WEB_DE_VENTA_ZJ.git>

Desarrolladores:

- **Parco Bellido Erikson** — `erikdd955@gmail.com`
- **Baez Chipana Jhon Ronald** — `72842924@elp.edu.pe`

### Reglas del equipo

1. **Siempre trabajar sobre `main` pero nunca hacer `git push` directo desde el equipo:**
   crear una rama por tarea y fusionar con Pull Request.
2. Nombre de rama: `tipo/descripcion-corta` (ej. `feature/listado-ventas`, `fix/login`).
3. Commits con mensaje en formato Conventional Commits:
   `tipo(scope): mensaje` donde el tipo es `feat`, `fix`, `refactor`, `docs` o `chore`.
4. Antes de hacer `pull`, hacer `git pull --rebase origin main` para evitar merges inútiles.
5. Nunca subir `node_modules/`, `target/`, `dist/` ni credenciales nuevas:
   el `.gitignore` del repo ya los excluye.

### Primera conexión (cada desarrollador)

```bash
git clone https://github.com/erikbellido/SISTEMA_WEB_DE_VENTA_ZJ.git
cd SISTEMA_WEB_DE_VENTA_ZJ
git config user.name  "Tu Nombre Completo"
git config user.email "tu-correo@ejemplo.com"
```

### Flujo diario

```bash
git checkout -b feature/mi-tarea       # crear rama
git add .
git commit -m "feat(backend): agregar endpoint de ventas"
git push -u origin feature/mi-tarea
# Abrir Pull Request en GitHub y pedir revisión al otro desarrollador
```

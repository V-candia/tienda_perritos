# tienda_perritos

Aplicación CRUD para la gestión de productos de una tienda de alimentos para perritos.

## Estructura
- `frontend/`: interfaz web servida con NGINX
- `backend/`: API en Node.js y Express
- `db/`: inicialización de MySQL
- `k8s/`: manifiestos para Kubernetes
- `.github/workflows/`: pipeline de GitHub Actions

## Entorno local
El proyecto se ejecuta localmente con Docker Compose.

Servicios:
- frontend en NGINX
- backend en Node.js
- base de datos MySQL

### Levantar el entorno local
```bash
docker compose up -d
```

### Validaciones locales
- frontend: `http://localhost:8080`
- backend: `http://localhost:3001/api/health`
- CRUD: `http://localhost:3001/api/productos`

## Producción
La arquitectura objetivo usa:
- Amazon EKS para frontend y backend
- Amazon RDS MySQL para la base de datos
- Amazon ECR para las imágenes
- GitHub Actions para CI/CD

## Variables de entorno del backend
- `PORT`
- `DB_HOST`
- `DB_USER`
- `DB_PASSWORD`
- `DB_NAME`
- `DB_PORT`

## CI/CD
El workflow debe ejecutarse sobre la rama `master`.

## Notas pendientes para AWS
- definir `AWS_REGION`
- definir `AWS_ACCOUNT_ID`
- definir `CLUSTER_NAME`
- definir `RDS_ENDPOINT`

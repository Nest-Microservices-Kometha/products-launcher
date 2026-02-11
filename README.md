# 🛒 Products App - Microservicios con NestJS

<p align="center">
  <img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" />
</p>

<p align="center">
  Aplicación de microservicios para gestión de productos y órdenes construida con <strong>NestJS</strong>, <strong>NATS</strong> y <strong>Docker</strong>.
</p>

---

## 📋 Descripción

Este proyecto implementa una arquitectura de microservicios que incluye:

| Servicio | Descripción | Puerto |
|----------|-------------|--------|
| 🌐 **Client Gateway** | API Gateway - Punto de entrada para todas las peticiones | 3000 |
| 📦 **Products MS** | Microservicio de gestión de productos (SQLite) | 3001 |
| 🧾 **Orders MS** | Microservicio de gestión de órdenes (PostgreSQL) | 3002 |
| 📡 **NATS Server** | Servidor de mensajería para comunicación entre servicios | 8222 |

---

## 🚀 Comenzando

### Prerrequisitos

Antes de comenzar, asegúrate de tener instalado:

- [Docker](https://www.docker.com/get-started) 🐳
- [Docker Compose](https://docs.docker.com/compose/install/) 🐙
- [Git](https://git-scm.com/) 📂

---

## 🛠️ Instalación para Desarrollo

Sigue estos pasos para configurar el entorno de desarrollo:

### 1️⃣ Clonar el repositorio

```bash
git clone <url-del-repositorio>
cd Products-App
```

### 2️⃣ Configurar variables de entorno

Crea un archivo `.env` basado en el archivo de ejemplo:

```bash
cp .env.example .env
```

Edita el archivo `.env` con tus configuraciones:

```env
CLIENT_GATEWAY_PORT=3000
```

### 3️⃣ Levantar los servicios

Ejecuta el siguiente comando para construir y levantar todos los contenedores:

```bash
docker compose up --build
```

> 💡 **Tip:** Usa `docker compose up --build -d` para ejecutar en segundo plano.

---

## ✅ Verificar la instalación

Una vez levantados los servicios, verifica que todo funcione correctamente:

| Servicio | URL | Estado |
|----------|-----|--------|
| Client Gateway | http://localhost:3000 | ✅ |
| NATS Monitoring | http://localhost:8222 | ✅ |

---

## 📁 Estructura del Proyecto

```
Products-App/
├── 📂 client-gateway/     # API Gateway
├── 📂 orders-ms/          # Microservicio de órdenes
├── 📂 products-ms/        # Microservicio de productos
├── 📄 docker-compose.yml  # Configuración de Docker
├── 📄 .env.example        # Variables de entorno de ejemplo
└── 📄 README.md           # Este archivo
```

---

## 🔧 Comandos Útiles

| Comando | Descripción |
|---------|-------------|
| `docker compose up --build` | Construir y levantar servicios |
| `docker compose up -d` | Levantar servicios en segundo plano |
| `docker compose down` | Detener y eliminar contenedores |
| `docker compose logs -f` | Ver logs en tiempo real |
| `docker compose ps` | Ver estado de los contenedores |

---

## 🧪 Endpoints Principales

### Products
- `GET /products` - Listar productos
- `GET /products/:id` - Obtener producto por ID
- `POST /products` - Crear producto
- `PATCH /products/:id` - Actualizar producto
- `DELETE /products/:id` - Eliminar producto

### Orders
- `GET /orders` - Listar órdenes
- `GET /orders/:id` - Obtener orden por ID
- `POST /orders` - Crear orden
- `PATCH /orders/:id` - Actualizar estado de orden

---

## 🤝 Contribuir

1. Haz un Fork del proyecto
2. Crea tu rama de feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add: nueva característica'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

---

## 📝 Licencia

Este proyecto está bajo la Licencia MIT.

---

<p align="center">
  Hecho con ❤️ usando NestJS
</p>

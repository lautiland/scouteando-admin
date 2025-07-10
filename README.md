# 🚀 Scouteando Backend

Backend de la aplicación Scouteando desarrollado con Strapi.

## 🔧 Configuración para Desarrollo Local

### 1. Instalar dependencias
```bash
npm install
```

### 2. Configurar variables de entorno
```bash
cp .env.example .env
```

Edita el archivo `.env` con tus valores locales (ya tienes uno configurado).

### 3. Ejecutar en modo desarrollo
```bash
npm run develop
```

La aplicación estará disponible en: http://localhost:1337

## 🚀 Despliegue en Producción

### Configuración Automática
El proyecto está configurado para usar GitHub Actions. Cuando hagas push a `main` o `master`, automáticamente:

1. ✅ Instala dependencias
2. ✅ Crea `.env.production` con los secretos del repositorio  
3. ✅ Construye la aplicación
4. ✅ Despliega automáticamente

### Secretos Requeridos en GitHub

Ve a tu repositorio → Settings → Secrets and variables → Actions y configura:

## 🔑 Lista de Secretos Necesarios

| Secret Name | Descripción | Cómo generar |
|-------------|-------------|--------------|
| `APP_KEYS` | Claves de la aplicación (separadas por comas) | `openssl rand -base64 32` (genera 4) |
| `API_TOKEN_SALT` | Salt para tokens de API | `openssl rand -base64 32` |
| `ADMIN_JWT_SECRET` | Secreto para JWT del admin | `openssl rand -base64 32` |
| `TRANSFER_TOKEN_SALT` | Salt para tokens de transferencia | `openssl rand -base64 32` |
| `JWT_SECRET` | Secreto principal para JWT | `openssl rand -base64 32` |
| `ENCRYPTION_KEY` | Clave de encriptación | `openssl rand -base64 32` |
| `DATABASE_URL` | URL de conexión a la base de datos | `postgresql://user:password@host:port/database` |

### Ejemplo de valores:
```bash
APP_KEYS=clave1,clave2,clave3,clave4
API_TOKEN_SALT=ABC123xyz789...
ADMIN_JWT_SECRET=DEF456abc012...
TRANSFER_TOKEN_SALT=GHI789def345...
JWT_SECRET=JKL012ghi678...
ENCRYPTION_KEY=MNO345jkl901...
DATABASE_URL=postgresql://usuario:contraseña@host:5432/scouteando_prod
```

### � Generar todas las claves de una vez:
```bash
echo "APP_KEYS=$(openssl rand -base64 32),$(openssl rand -base64 32),$(openssl rand -base64 32),$(openssl rand -base64 32)"
echo "API_TOKEN_SALT=$(openssl rand -base64 32)"
echo "ADMIN_JWT_SECRET=$(openssl rand -base64 32)"
echo "TRANSFER_TOKEN_SALT=$(openssl rand -base64 32)"
echo "JWT_SECRET=$(openssl rand -base64 32)"
echo "ENCRYPTION_KEY=$(openssl rand -base64 32)"
```

## 📁 Estructura de Archivos de Configuración

- `.env` - Desarrollo local (ignorado por git)
- `.env.example` - Template con ejemplos
- `.env.production` - Template para producción (usa secretos de GitHub)
- `.github/workflows/strapi-deploy.yml` - Pipeline de CI/CD

```
yarn strapi deploy
```

## 📚 Learn more

- [Resource center](https://strapi.io/resource-center) - Strapi resource center.
- [Strapi documentation](https://docs.strapi.io) - Official Strapi documentation.
- [Strapi tutorials](https://strapi.io/tutorials) - List of tutorials made by the core team and the community.
- [Strapi blog](https://strapi.io/blog) - Official Strapi blog containing articles made by the Strapi team and the community.
- [Changelog](https://strapi.io/changelog) - Find out about the Strapi product updates, new features and general improvements.

Feel free to check out the [Strapi GitHub repository](https://github.com/strapi/strapi). Your feedback and contributions are welcome!

## ✨ Community

- [Discord](https://discord.strapi.io) - Come chat with the Strapi community including the core team.
- [Forum](https://forum.strapi.io/) - Place to discuss, ask questions and find answers, show your Strapi project and get feedback or just talk with other Community members.
- [Awesome Strapi](https://github.com/strapi/awesome-strapi) - A curated list of awesome things related to Strapi.

---

<sub>🤫 Psst! [Strapi is hiring](https://strapi.io/careers).</sub>

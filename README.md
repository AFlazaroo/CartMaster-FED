# CartMaster-FED
Gestión financiera de clientes, desarrollado con Flask. Permite la interacción del usuario mediante formularios y vistas dinámicas, conectándose al backend REST en Spring Boot para realizar operaciones como consulta, registro y actualización de información.

# CartMaster Frontend

Sistema de gestión de tarjetas de crédito desarrollado con Flask. Esta aplicación frontend proporciona una interfaz de usuario intuitiva y segura para interactuar con el backend CartMaster (Spring Boot), permitiendo una gestión completa del ciclo de vida de tarjetas de crédito.

## 🚀 Características Principales

- **Autenticación Robusta**
  - Sistema de login y registro seguro
  - Roles diferenciados (Cliente/Administrador)
  - Gestión de sesiones con Flask-Login
  - Recuperación de contraseña

- **Gestión de Tarjetas**
  - Solicitud de nuevas tarjetas
  - Visualización del estado en tiempo real
  - Historial de transacciones
  - Bloqueo/desbloqueo de tarjetas
  - Reportes de pérdida o robo

- **Panel de Control**
  - Dashboard personalizado por usuario
  - Métricas y estadísticas de uso
  - Notificaciones en tiempo real
  - Gestión de límites de crédito

- **Interfaz de Usuario**
  - Diseño responsivo con Bootstrap 5
  - Temas claro/oscuro
  - Accesibilidad WCAG 2.1
  - Soporte multiidioma

## 🛠️ Requisitos Técnicos

- Python 3.8+
- pip (gestor de paquetes de Python)
- Node.js 14+ (para assets)
- Backend CartMaster (Spring Boot)
- Navegador moderno (Chrome, Firefox, Safari, Edge)

## ⚙️ Configuración del Entorno

1. **Clonar el Repositorio**
```bash
git clone <repository-url>
cd cartmaster-frontend
```

2. **Configurar Entorno Virtual**
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Unix/MacOS
source venv/bin/activate
```

3. **Instalar Dependencias**
```bash
pip install -r requirements.txt
npm install  # Para assets frontend
```

4. **Configuración del Entorno**
Crear archivo `.env`:
```env
FLASK_APP=app
FLASK_ENV=development
SECRET_KEY=tu-clave-secreta-aqui
BACKEND_URL=http://localhost:8080
JWT_SECRET_KEY=tu-jwt-secreto
REDIS_URL=redis://localhost:6379
MAIL_SERVER=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=tu-email@gmail.com
MAIL_PASSWORD=tu-password
```

## 🚀 Ejecución

1. **Iniciar Servicios Requeridos**
```bash
# Iniciar Redis (para caché y sesiones)
redis-server

# Iniciar Backend (en otra terminal)
cd cartmaster-backend
./mvnw spring-boot:run
```

2. **Iniciar Aplicación**
```bash
# Modo desarrollo
flask run

# Modo producción
gunicorn -w 4 "app:create_app()"
```

3. **Acceder a la Aplicación**
- Desarrollo: `http://localhost:5000`
- Producción: `http://tu-dominio.com`

## 📁 Estructura del Proyecto

```
cartmaster-frontend/
├── app/
│   ├── __init__.py          # Configuración de la aplicación
│   ├── models/              # Modelos de datos
│   │   ├── user.py
│   │   └── card.py
│   ├── routes/             # Rutas y controladores
│   │   ├── auth.py
│   │   ├── cards.py
│   │   └── admin.py
│   ├── services/          # Lógica de negocio
│   │   ├── card_service.py
│   │   └── user_service.py
│   ├── static/            # Assets estáticos
│   └── templates/         # Plantillas Jinja2
├── tests/                 # Tests unitarios y de integración
├── config.py             # Configuraciones
├── requirements.txt      # Dependencias Python
└── package.json         # Dependencias Node.js
```

## 🔒 Seguridad

- **Autenticación**
  - JWT para APIs
  - Sesiones seguras con Redis
  - Rate limiting
  - Protección CSRF

- **Datos Sensibles**
  - Encriptación en tránsito (HTTPS)
  - No almacenamiento de datos sensibles
  - Sanitización de inputs
  - Validación de datos

## 🔍 Monitoreo y Logs

- Integración con Sentry para errores
- Logs estructurados con logging
- Métricas de rendimiento
- Alertas automáticas

## 🤝 Contribución

1. Fork del repositorio
2. Crear rama feature (`git checkout -b feature/AmazingFeature`)
3. Commit cambios (`git commit -m 'Add AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abrir Pull Request

## 📝 Convenciones de Código

- PEP 8 para Python
- ESLint para JavaScript
- Conventional Commits
- Tests requeridos para PRs

## 📄 Licencia

Distribuido bajo la licencia MIT. Ver `LICENSE` para más información.

## 📞 Soporte

- Documentación: [link-to-docs]
- Issues: GitHub Issues
- Email: soporte@cartmaster.com
- Discord: [link-to-discord] 

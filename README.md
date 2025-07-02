# 🏟️ FutCamp - Sistema de Reserva de Canchas UCV

Sistema web completo para la gestión y reserva de canchas deportivas en la Universidad César Vallejo. Esta aplicación permite a estudiantes y administradores gestionar reservas de manera eficiente, con un sistema de autenticación robusto y una interfaz intuitiva.

## 🌟 Características Principales

### 👥 Gestión de Usuarios

- **Registro de estudiantes** con validación de datos
- **Sistema de autenticación** seguro
- **Recuperación de contraseñas** por email
- **Perfiles de usuario** personalizables
- **Gestión de administradores** con privilegios especiales

### 📅 Sistema de Reservas

- **Reserva de canchas** con selección de horarios
- **Visualización de disponibilidad** en tiempo real
- **Historial de reservas** completo
- **Gestión de reservas** por administradores
- **Notificaciones** automáticas

### 🎯 Funcionalidades Administrativas

- **Panel de administración** completo
- **Gestión de estudiantes** (activar/desactivar usuarios)
- **Control de reservas** y horarios
- **Reportes y estadísticas**
- **Configuración del sistema**

## 🛠️ Tecnologías Utilizadas

### Backend

- **PHP 8.0+** - Lógica del servidor
- **MySQL 8.0+** - Base de datos
- **PDO** - Conexión segura a base de datos
- **PHPMailer** - Envío de emails

### Frontend

- **HTML5** - Estructura de páginas
- **CSS3** - Estilos y diseño responsivo
- **JavaScript (ES6+)** - Interactividad del cliente
- **AJAX** - Comunicación asíncrona

### Arquitectura

- **Patrón MVC** - Modelo-Vista-Controlador
- **RESTful API** - Endpoints para operaciones CRUD
- **Responsive Design** - Compatible con móviles y tablets

## 📋 Requisitos del Sistema

### Software Necesario

- **[XAMPP](https://www.apachefriends.org/es/index.html)** (versión 8.0+)
  - Apache 2.4+
  - PHP 8.0+
  - MySQL 8.0+
- **[Visual Studio Code](https://code.visualstudio.com/)** (recomendado)
- **Git** (para control de versiones)

### Extensiones Recomendadas para VS Code

- PHP Extension Pack
- Live Server
- MySQL
- GitLens

## 🚀 Instalación y Configuración

### 1. Clonar el Repositorio

```bash
git clone https://github.com/ucv-renacyt/ucv-futcamp.git
cd ucv-futcamp
```

### 2. Configurar el Entorno Local

1. **Iniciar XAMPP**:

   - Abre XAMPP Control Panel
   - Inicia los servicios `Apache` y `MySQL`
   - Verifica que ambos servicios estén ejecutándose

2. **Copiar el proyecto**:

   ```bash
   # En Windows
   xcopy /E /I ucv-futcamp C:\xampp\htdocs\ucv-futcamp

   # En Linux/Mac
   cp -r ucv-futcamp /opt/lampp/htdocs/
   ```

### 3. Configurar la Base de Datos

1. **Acceder a phpMyAdmin**:

   - Abre tu navegador
   - Ve a `http://localhost/phpmyadmin`

2. **Crear la base de datos**:

   - Crea una nueva base de datos llamada `futcamp`
   - Selecciona el conjunto de caracteres `utf8mb4_unicode_ci`

3. **Importar la estructura**:
   - Ve a la pestaña "Importar"
   - Selecciona el archivo `futcamp(21).txt` que contiene la estructura completa de la base de datos
   - Haz clic en "Continuar"

**📁 Estructura de la Base de Datos:**
El archivo `futcamp(21).txt` contiene las siguientes tablas:

- `estudiantes` - Información de estudiantes registrados
- `horarios` - Horarios disponibles para reservas
- `registros` - Registro de actividades del sistema
- `reserva` - Reservas realizadas por los usuarios
- `usuarios` - Cuentas de usuario del sistema

### 4. Configurar la Conexión

Edita el archivo `Servidor/Modelo/database.php`:

```php
<?php
$hostname = "localhost";
$dbname = "futcamp";
$username = "root";  // Usuario por defecto de XAMPP
$password = "";      // Contraseña vacía por defecto
```

### 5. Ejecutar la Aplicación

Abre tu navegador y dirígete a:

```
http://localhost/ucv-futcamp/
```

## 📁 Estructura del Proyecto

```
ucv-futcamp/
├── 📄 index.html                 # Página de carga inicial
├── 📄 README.md                  # Documentación del proyecto
├── 📄 LICENSE                    # Licencia MIT
├── 📄 .gitignore                 # Archivos excluidos de Git
├── 📄 futcamp(21).txt           # Estructura de base de datos
│
├── 🗂️ Servidor/                  # Lógica del servidor (MVC)
│   ├── 🎮 Controlador/           # Controladores PHP
│   │   ├── Admin_login.php      # Autenticación de administradores
│   │   ├── Admin_registro.php   # Registro de administradores
│   │   ├── Registro_reserva.php # Gestión de reservas
│   │   ├── gestionReservas.php  # Administración de reservas
│   │   ├── gestionUsuarios.php  # Gestión de usuarios
│   │   └── ...                  # Otros controladores
│   │
│   ├── 🗄️ Modelo/               # Capa de datos
│   │   └── database.php         # Conexión a base de datos
│   │
│   └── 🎨 Vista/                # Interfaz de usuario
│       ├── 📄 index.html        # Página de login
│       ├── 📄 gestionReservas.html
│       ├── 📄 gestionEstudiantes.html
│       ├── 📄 historialReservas.html
│       ├── 📄 visualizacionHorarios.html
│       ├── 📁 css/              # Estilos CSS
│       ├── 📁 js/               # Scripts JavaScript
│       └── 📁 img/              # Imágenes y recursos
│
└── 🗂️ Api/                      # APIs y servicios
    └── 📁 phpMailer/            # Librería para envío de emails
```

## 👨‍💻 Uso del Sistema

### Para Estudiantes

1. **Registro**: Crear una cuenta con datos personales
2. **Login**: Iniciar sesión con usuario y contraseña
3. **Reservar**: Seleccionar cancha, fecha y horario disponible
4. **Gestionar**: Ver historial y cancelar reservas

### Para Administradores

1. **Login**: Acceder con credenciales de administrador
2. **Panel**: Gestionar usuarios, reservas y horarios
3. **Reportes**: Ver estadísticas y reportes del sistema
4. **Configuración**: Ajustar parámetros del sistema

## 🔧 Comandos Git Útiles

### Configuración Inicial

```bash
# Clonar el repositorio
git clone https://github.com/ucv-renacyt/ucv-futcamp.git

# Configurar usuario (si es necesario)
git config user.name "Tu Nombre"
git config user.email "tu.email@ejemplo.com"
```

### Flujo de Trabajo

```bash
# Ver estado del repositorio
git status

# Crear una nueva rama
git checkout -b feature/nueva-funcionalidad

# Agregar cambios
git add .

# Hacer commit
git commit -m "feat: agregar nueva funcionalidad de reservas"

# Subir cambios
git push origin feature/nueva-funcionalidad

# Cambiar a rama principal
git checkout main

# Actualizar repositorio local
git pull origin main
```

## 🐛 Solución de Problemas

### Error de Conexión a Base de Datos

- Verifica que MySQL esté ejecutándose en XAMPP
- Confirma las credenciales en `database.php`
- Asegúrate de que la base de datos `futcamp` existe
- Verifica que hayas importado correctamente el archivo `futcamp(21).txt`

### Error 404 - Página no encontrada

- Verifica que Apache esté ejecutándose
- Confirma la ruta del proyecto en `htdocs`
- Revisa los permisos de archivos

### Error de Permisos

```bash
# En Linux/Mac, dar permisos de escritura
chmod -R 755 /ruta/al/proyecto
chmod -R 777 /ruta/al/proyecto/logs
```

## 🤝 Contribución

1. **Fork** el proyecto
2. Crea una **rama** para tu feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. **Push** a la rama (`git push origin feature/AmazingFeature`)
5. Abre un **Pull Request**

## 📝 Convenciones de Código

- **PHP**: PSR-12 coding standards
- **JavaScript**: ES6+ con camelCase
- **CSS**: BEM methodology
- **Commits**: Conventional Commits format

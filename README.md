# Sistema Escolar BUAP 🎓

Sistema de gestión escolar desarrollado con Angular 16 para la administración integral de usuarios (administradores, maestros y alumnos) y eventos académicos.

![Angular](https://img.shields.io/badge/Angular-16.2.0-red?style=flat-square&logo=angular)
![TypeScript](https://img.shields.io/badge/TypeScript-5.1.3-blue?style=flat-square&logo=typescript)
![Material](https://img.shields.io/badge/Material-16.2.14-purple?style=flat-square&logo=material-design)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3.8-violet?style=flat-square&logo=bootstrap)

## 📋 Tabla de Contenidos

- [Características](#-características)
- [Tecnologías](#-tecnologías)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación](#-instalación)
- [Configuración](#-configuración)
- [Ejecución](#-ejecución)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Funcionalidades por Rol](#-funcionalidades-por-rol)

## Características

### Gestión de Usuarios

- **Registro y autenticación** con JWT
- **Tres tipos de usuarios**: Administrador, Maestro y Alumno
- **Perfiles personalizados** con datos específicos por rol
- **Edición de datos** con validaciones en tiempo real
- **Eliminación controlada** según permisos

### Eventos Académicos

- **Registro de eventos** (Conferencias, Talleres, Seminarios, Concursos)
- **Gestión de horarios** con validación de conflictos
- **Público objetivo** configurable (Estudiantes, Profesores, Público general)
- **Asignación de responsables** (Maestros o Administradores)
- **Control de cupos** y capacidad máxima

### Visualización de Datos

- **Gráficas interactivas** con Chart.js
- **Análisis de usuarios** por rol
- **Estadísticas de eventos** por tipo
- **Dashboard responsivo** adaptable a cualquier dispositivo

### Interfaz de Usuario

- **Diseño moderno** con Angular Material y Bootstrap
- **Tema claro/oscuro** configurable
- **Navegación intuitiva** con sidebar colapsable
- **Responsive design** optimizado para móviles y tablets
- **Animaciones fluidas** para mejor experiencia de usuario

## Tecnologías

### Frontend

- **Angular 16.2.0** - Framework principal
- **Angular Material 16.2.14** - Componentes UI
- **Bootstrap 5.3.8** - Framework CSS
- **Chart.js 3.6.0** - Gráficas y visualización
- **NgxMask 16.4.2** - Máscaras de entrada
- **RxJS 7.8.0** - Programación reactiva

### Herramientas

- **TypeScript 5.1.3** - Lenguaje de programación
- **SCSS** - Preprocesador CSS
- **Karma & Jasmine** - Testing
- **Angular CLI 16.2.11** - Herramientas de desarrollo

## Requisitos Previos

Antes de comenzar, asegúrate de tener instalado:

- **Node.js** (versión 16.x o superior)
- **npm** (versión 8.x o superior)
- **Angular CLI** (versión 16.x)

```bash
# Verificar versiones instaladas
node --version
npm --version
ng version
```

## Instalación

1. **Clonar el repositorio**

```bash
git clone https://github.com/tu-usuario/sistema-escolar-buap.git
cd sistema-escolar-buap
```

2. **Instalar dependencias**

```bash
npm install
```

## Configuración

### Variables de Entorno

El proyecto utiliza archivos de configuración para diferentes entornos:

**Desarrollo** (`src/environments/environment.ts`):

```typescript
export const environment = {
  production: false,
  url_api: "https://sistema-escolar-api-1wpx.onrender.com",
};
```

**Producción** (`src/environments/environment.prod.ts`):

```typescript
export const environment = {
  production: true,
  url_api: "https://sistema-escolar-api-1wpx.onrender.com/api",
};
```

### API Backend

El sistema está configurado para conectarse a una API REST desplegada en Render. Asegúrate de que la API esté disponible antes de ejecutar la aplicación.

## Ejecución

### Servidor de Desarrollo

```bash
ng serve
```

Navega a `http://localhost:4200/`. La aplicación se recargará automáticamente si realizas cambios en los archivos fuente.

### Build de Producción

```bash
ng build
```

Los archivos de distribución se generarán en el directorio `dist/`.

### Ejecutar Tests

```bash
# Tests unitarios
ng test

# Tests con cobertura
ng test --code-coverage
```

## 📁 Estructura del Proyecto

```
src/
├── app/
│   ├── layouts/              # Layouts principales
│   │   ├── auth-layout/      # Layout de autenticación
│   │   └── dashboard-layout/ # Layout del dashboard
│   ├── screens/              # Páginas principales
│   │   ├── login-screen/
│   │   ├── registro-usuarios-screen/
│   │   ├── admin-screen/
│   │   ├── maestros-screen/
│   │   ├── alumnos-screen/
│   │   ├── eventos-academicos/
│   │   ├── tabla-eventos-academicos/
│   │   └── graficas-screen/
│   ├── partials/             # Componentes reutilizables
│   │   ├── navbar-user/
│   │   ├── sidebar/
│   │   ├── registro-admin/
│   │   ├── registro-maestros/
│   │   └── registro-alumnos/
│   ├── modals/               # Modales
│   │   ├── eliminar-user-modal/
│   │   └── editar/
│   ├── services/             # Servicios
│   │   ├── facade.service.ts
│   │   ├── administradores.service.ts
│   │   ├── maestros.service.ts
│   │   ├── alumnos.service.ts
│   │   ├── eventos.service.ts
│   │   └── tools/
│   └── shared/               # Utilidades compartidas
├── assets/                   # Recursos estáticos
│   ├── fonts/
│   └── images/
├── environments/             # Configuraciones de entorno
└── styles.scss               # Estilos globales
```

## Funcionalidades por Rol

### Administrador

- ✅ Registro y gestión de todos los tipos de usuarios
- ✅ Eliminación de usuarios
- ✅ Creación, edición y eliminación de eventos académicos
- ✅ Visualización completa de gráficas y estadísticas
- ✅ Acceso total al sistema

### Maestro

- ✅ Registro de alumnos
- ✅ Edición de su propio perfil
- ✅ Visualización de eventos académicos (propios + públicos)
- ✅ Visualización de maestros y alumnos
- ✅ Acceso a gráficas y estadísticas

### Alumno

- ✅ Edición de su propio perfil
- ✅ Visualización de eventos académicos para estudiantes
- ✅ Visualización de otros alumnos
- ✅ Acceso limitado a funcionalidades administrativas

## Personalización

### Temas

El sistema soporta temas claro y oscuro. Para cambiar entre temas, utiliza el botón de paleta en la barra de navegación.

Las variables de tema están definidas en `src/app/partials/navbar-user/navbar-user.component.ts`:

```typescript
colorPalettes = {
  light: {
    "--background-main": "#f4f7fb",
    "--sidebar-bg": "#23395d",
    "--navbar-bg": "#fff",
    "--text-main": "#222",
    "--table-bg": "#fff",
    "--table-header-bg": "#cfe2ff",
  },
  dark: {
    "--background-main": "#181a1b",
    "--sidebar-bg": "#1a2636",
    "--navbar-bg": "#222",
    "--text-main": "#e4ecfa",
    "--table-bg": "#222",
    "--table-header-bg": "#30507a",
  },
};
```

## 📝 Validaciones Implementadas

### Contraseñas

- Mínimo 8 caracteres
- Al menos una letra minúscula
- Al menos una letra mayúscula
- Al menos un número
- Al menos un carácter especial (@$!%\*?&#)

### RFC

- 12 o 13 caracteres
- Formato válido: 3-4 letras + 6 dígitos + 2-3 caracteres alfanuméricos

### CURP (solo alumnos)

- Exactamente 18 caracteres
- Formato válido según estructura oficial

### Email

- Formato de email válido
- Máximo 100 caracteres

### Teléfono

- Exactamente 10 dígitos
- Solo números

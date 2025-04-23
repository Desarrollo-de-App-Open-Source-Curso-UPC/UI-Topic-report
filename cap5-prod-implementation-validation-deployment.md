## 5.1. Software Configuration Management.

### 5.1.1 Software Development Environment Configuration

A continuación, se listan las herramientas y estándares adoptados por el equipo para el desarrollo colaborativo del sistema:

| Actividad | Herramienta / Guía | Propósito | Tipo de acceso / Ruta |
|-----------|--------------------|-----------|------------------------|
| Project Management | Jira Software | Seguimiento de backlog, tareas y sprints. | SaaS – [https://www.atlassian.com/software/jira](https://www.atlassian.com/software/jira) |
| Requirements Management | Gherkin Conventions | Escritura legible de requisitos con formato Given/When/Then. | [https://cucumber.io/docs/gherkin/](https://cucumber.io/docs/gherkin/) |
| Product UX/UI Design | Figma | Prototipos y diseño responsive. | SaaS – [https://figma.com](https://figma.com) |
| Frontend Dev | HTML, CSS, JavaScript, TypeScript, Angular | Construcción del frontend del sistema. | [https://angular.io/guide/styleguide](https://angular.io/guide/styleguide) |
| Backend Dev | Java + Spring Boot | Lógica de negocio y servicios REST. | [https://spring.io/projects/spring-boot](https://spring.io/projects/spring-boot) |
| IDE | IntelliJ IDEA + WebStorm | Desarrollo, depuración y pruebas. | [https://www.jetbrains.com/idea](https://www.jetbrains.com/idea) / [https://www.jetbrains.com/webstorm](https://www.jetbrains.com/webstorm) |
| Code Standards | Google Java Style Guide, Google TypeScript Style Guide | Mantener un código consistente y legible. | [https://google.github.io/styleguide](https://google.github.io/styleguide) |
| Version Control | Git + GitHub | Gestión colaborativa del código fuente. | SaaS – [https://github.com](https://github.com) |
| Software Deployment | Railway / Render | Despliegue continuo del sistema en ambientes de testing. | SaaS – [https://railway.app](https://railway.app) / [https://render.com](https://render.com) |
| Software Documentation | Notion + Postman | Documentación de APIs, funcionalidades y criterios técnicos. | SaaS – [https://www.notion.so](https://www.notion.so) / [https://www.postman.com](https://www.postman.com) |

## 5.1.2. Source Code Management

En esta sección el equipo establece los medios y esquema de organización que aplicará para el seguimiento de modificaciones. Para ello se utilizará **GitHub** como plataforma y sistema de control de versiones.

A continuación se indican los URLs de los repositorios de GitHub para cada producto:

- **Landing Page**: [URL del repositorio aquí]
- **Web Services**: [URL del repositorio aquí]  
  _(Incluye el proyecto y los archivos de pruebas unitarias e integración/aceptación)_
- **Frontend Web Application**: [URL del repositorio aquí]

### GitFlow Workflow

Se implementará el modelo de ramificación propuesto por Vincent Driessen en su artículo *“A successful Git branching model”*, conocido como **GitFlow**. Este modelo organiza el trabajo en las siguientes ramas:

- `main`: Rama principal, contiene siempre el código en producción.
- `develop`: Rama de desarrollo principal, donde se integran las funcionalidades antes de pasar a producción.
- `feature/*`: Ramas creadas a partir de `develop` para desarrollar nuevas funcionalidades.  
  **Convención de nombres:** `feature/<nombre-corto-descriptivo>`  
  _Ejemplo: `feature/login-auth`_
- `release/*`: Ramas creadas desde `develop` cuando se prepara una nueva versión para producción.  
  **Convención de nombres:** `release/<versión>`  
  _Ejemplo: `release/1.2.0`_
- `hotfix/*`: Ramas creadas desde `main` para corregir errores críticos en producción.  
  **Convención de nombres:** `hotfix/<descripción-corta>`  
  _Ejemplo: `hotfix/fix-payment-bug`_

### Versionado Semántico

Se aplicará el esquema de **Semantic Versioning 2.0.0**, con el siguiente formato:

- **MAJOR**: Incompatibilidades en la API.
- **MINOR**: Nuevas funcionalidades sin romper compatibilidad.
- **PATCH**: Correcciones de errores menores y ajustes sin afectar funcionalidades.

_Ejemplo de versión:_ `v1.3.2`

### Convenciones de Commits

Se utilizará el estándar de **Conventional Commits** para los mensajes de commits. Esto facilitará la automatización en los procesos de integración continua y generación de changelogs.

**Ejemplos:**

- `feat: add login functionality`
- `fix: correct null pointer exception on user service`
- `chore: update dependencies`

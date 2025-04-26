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

### 5.1.2. Source Code Management

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


## 5.1.3. Source Code Style Guide & Conventions.

## 5.1.4. Software Deployment Configuration


# 5.2. Landing Page, Services & Applications Implementation

## 5.2.1 Sprint 1

### 5.2.1.1. Sprint Planning 1

A continuación, se presenta la planificación correspondiente a nuestro Sprint 1, el cual tiene como enfoque principal el desarrollo de la landing page de Restock. En esta etapa inicial, el equipo definió el objetivo del sprint, seleccionó las historias de usuario más relevantes y estableció los entregables clave que permitirán construir una primera versión funcional y visualmente atractiva de la página. Esta planificación busca asegurar un entendimiento compartido entre todos los miembros del equipo y sentar las bases para comunicar eficazmente el valor de la plataforma a los usuarios potenciales.

| Sprint #     | Sprint 1                   | 
|--------------|----------------------------|
| **Sprint Planning Background**                |      
| Date                  | 2025-04-23             | 
| Time                  | 19:00 pm (GMT-5)|
| Location | Modalidad remota mediante la plataforma Discord |
| Prepared By | Shapiama Rivera, Gabriela Nicole |
| Attendees (to planning meeting) | Avendaño Balarezo, Williams Eduardo / Castro Alejos / Julio, Guerra Perez, José Jahaziel / Guzmán Cabrejos, Yaku Mateo / Shapiama Rivera, Gabriela Nicole |
| Sprint 0 Review Summary  | Dado que este es el sprint inicial, no se presenta un resumen del sprint anterior. |
| Sprint 0 Retrospective Summary | Dado que este es el sprint inicial, no se presenta una retroalimentación del sprint anterior. |
| **Sprint Goal & User Stories** |
| Sprint 1 Goal | Nos enfocamos en implementar la estructura principal y las funcionalidades clave de la landing page pública de Restock.<br>Creemos que esto aportará una percepción más sólida del producto y despertará mayor interés entre los usuarios potenciales, al comunicar de forma clara el valor y los beneficios de la plataforma.<br>Esto se confirmará cuando los visitantes puedan navegar de manera fluida por la página, comprendan fácilmente qué ofrece Restock y muestren intención de interactuar o registrarse. |
| Sprint 1 Velocity | 27 puntos |
| Sum of Story Points |  27 puntos |

## 5.2.1.2 Aspect Leaders and Collaborators

# Aspect Leaders and Collaborators

Durante el Sprint 1, se han definido los principales aspectos a desarrollar, correspondientes a funcionalidades específicas como la visualización de contenido, navegación fluida, adaptabilidad responsiva y gestión de autenticación de usuarios.

Con el objetivo de asegurar una comunicación clara y eficiente dentro del equipo, se elaboró la siguiente matriz de liderazgo y colaboración (LACX), asignando para cada aspecto un líder responsable (L) y colaboradores de apoyo (C).

| Team Member (Last Name, First Name) | GitHub Username       | Mostrar Mensaje de Valor | Beneficios Segmentados | CTA con Redirección y Descarga | Barra de Navegación | Pasos del Funcionamiento | Video Explicativo | Footer Landing Page | Testimonios de Clientes | Preguntas Frecuentes | Formulario de Contacto | Navegación Fluida | Responsive Desktop | Responsive Móviles | Responsive Tablet | Registro | Inicio de Sesión | Recuperación de Contraseña |
|:------------------------------------|:----------------------|:------------------------|:------------------------|:-----------------------------|:-------------------|:------------------------|:-----------------|:--------------------|:------------------------|:--------------------|:----------------------|:------------------|:-------------------|:------------------|:------------------|:--------|:----------------|:---------------------------|
| Vendaño Balarezo, Williams Eduardo  | dev-willy-code         | L                        | C                        | C                             | C                   | C                        | L                 | C                    | C                        | C                    | C                      | L                  | C                   | C                  | C                  | C      | C                | C                         |
| Castro Alejos, Julio                | JulioXC4               | C                        | L                        | C                             | C                   | C                        | C                 | L                    | C                        | C                    | C                      | C                  | L                   | C                  | C                  | C      | C                | C                         |
| Guerra Perez, José Jahaziel         | jahazielgp             | C                        | C                        | L                             | C                   | L                        | C                 | C                    | L                        | C                    | C                      | C                  | C                   | L                  | C                  | C      | C                | C                         |
| Guzmán Cabrejos, Yaku Mateo         | yak-cod                | C                        | C                        | C                             | L                   | C                        | C                 | C                    | C                        | L                    | L                      | C                  | C                   | C                  | L                  | L      | C                | C                         |
| Shapiama Rivera, Gabriela Nicole    | GabrielaShapiama28     | C                        | C                        | C                             | C                   | C                        | C                 | C                    | C                        | C                    | C                      | C                  | C                   | C                  | C                  | C      | L                | L                         |


## 5.2.1.3 Sprint Backlog 1

El objetivo principal de este Sprint es diseñar, implementar y validar las secciones del landing page, asegurando una navegación fluida, una experiencia responsiva en todos los dispositivos y funcionalidades críticas como registro, inicio de sesión y recuperación de contraseña. Se busca garantizar que el usuario final pueda interactuar de manera sencilla y eficiente con la plataforma, mejorando su satisfacción y promoviendo el cumplimiento de los objetivos de negocio.

**screenshot del Board**

![Container Diagrams](assets/images/cap5/board-sprint.png)
![Container Diagrams](assets/images/cap5/board-sprint-detallado.png)

https://trello.com/invite/b/680c05f1fac416bfdb0ea024/ATTI41428da9336a1d11b0878438a247c3531DFD7E76/sprint-backlog-1

<br>

| User Story ID | User Story Title                                | Task ID | Task Title                   | Task Description                                                   | Estimated Hours |
|---------------|--------------------------------------------------|---------|------------------------------|--------------------------------------------------------------------|-----------------|
| US-08         | Mostrar Mensaje de Valor en la Sección Principal | T001     | Diseñar sección               | Crear diseño visual para 'mostrar mensaje de valor en la sección principal'. | 1/2 h |
|               |                                                  | T002     | Implementar funcionalidad     | Codificar el componente necesario para 'mostrar mensaje de valor en la sección principal'. | 1h |
|               |                                                  | T003     | Realizar pruebas              | Verificar que 'mostrar mensaje de valor en la sección principal' funcione correctamente. | 1/2h |
| US-09         | Mostrar Beneficios Segmentados por Tipo de Usuario | T004     | Diseñar sección               | Crear diseño visual para 'mostrar beneficios segmentados por tipo de usuario'. | 1/2h |
|               |                                                  | T005     | Implementar funcionalidad     | Codificar el componente necesario para 'mostrar beneficios segmentados por tipo de usuario'. | 1h |
|               |                                                  | T006     | Realizar pruebas              | Verificar que 'mostrar beneficios segmentados por tipo de usuario' funcione correctamente. | 1/2h |
| US-10         | Incluir Llamados a la Acción (CTA) con Redirección y Descarga | T007     | Diseñar sección               | Crear diseño visual para 'incluir llamados a la acción (cta) con redirección y descarga'. | 1/2h |
|               |                                                  | T008     | Implementar funcionalidad     | Codificar el componente necesario para 'incluir llamados a la acción (cta) con redirección y descarga'. | 1h |
|               |                                                  | T009     | Realizar pruebas              | Verificar que 'incluir llamados a la acción (cta) con redirección y descarga' funcione correctamente. | 1/2h |
| US-05         | Visualización de la barra de navegación         | T010     | Diseñar sección               | Crear diseño visual para 'visualización de la barra de navegación'. | 1/2h |
|               |                                                  | T011     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización de la barra de navegación'. | 1h |
|               |                                                  | T012     | Realizar pruebas              | Verificar que 'visualización de la barra de navegación' funcione correctamente. | 1/2h |
| US-06         | Visualización de pasos del funcionamiento       | T013     | Diseñar sección               | Crear diseño visual para 'visualización de pasos del funcionamiento'. | 1/2h |
|               |                                                  | T014     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización de pasos del funcionamiento'. | 1h |
|               |                                                  | T015     | Realizar pruebas              | Verificar que 'visualización de pasos del funcionamiento' funcione correctamente. | 1/2h |
| US-07         | Alternativa con video explicativo               | T016     | Diseñar sección               | Crear diseño visual para 'alternativa con video explicativo'. | 1/2h |
|               |                                                  | T017     | Implementar funcionalidad     | Codificar el componente necesario para 'alternativa con video explicativo'. | 1h |
|               |                                                  | T018     | Realizar pruebas              | Verificar que 'alternativa con video explicativo' funcione correctamente. | 1/2h |
| US-04         | Visualización de footer en landing page         | T019     | Diseñar sección               | Crear diseño visual para 'visualización de footer en landing page'. | 1/2h |
|               |                                                  | T020     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización de footer en landing page'. | 2h |
|               |                                                  | T021     | Realizar pruebas              | Verificar que 'visualización de footer en landing page' funcione correctamente. | 1/2h |
| US-01         | Ver testimonios de clientes                     | T022     | Diseñar sección               | Crear diseño visual para 'ver testimonios de clientes'. | 2h |
|               |                                                  | T023     | Implementar funcionalidad     | Codificar el componente necesario para 'ver testimonios de clientes'. | 1/2h |
|               |                                                  | T024     | Realizar pruebas              | Verificar que 'ver testimonios de clientes' funcione correctamente. | 1h |
| US-02         | Consultar Preguntas Frecuentes                  | T025     | Diseñar sección               | Crear diseño visual para 'consultar preguntas frecuentes'. | 1/2h |
|               |                                                  | T026     | Implementar funcionalidad     | Codificar el componente necesario para 'consultar preguntas frecuentes'. | 1h |
|               |                                                  | T027     | Realizar pruebas              | Verificar que 'consultar preguntas frecuentes' funcione correctamente. | 1/2h |
| US-03         | Enviar Formulario de Contacto                   | T028     | Diseñar sección               | Crear diseño visual para 'enviar formulario de contacto'. | 1h |
|               |                                                  | T029     | Implementar funcionalidad     | Codificar el componente necesario para 'enviar formulario de contacto'. | 1/2h |
|               |                                                  | T030     | Realizar pruebas              | Verificar que 'enviar formulario de contacto' funcione correctamente. | 1h |
| US-16         | Navegación fluida entre secciones               | T031     | Diseñar sección               | Crear diseño visual para 'navegación fluida entre secciones'. | 1/2h |
|               |                                                  | T032     | Implementar funcionalidad     | Codificar el componente necesario para 'navegación fluida entre secciones'. | 1h |
|               |                                                  | T033     | Realizar pruebas              | Verificar que 'navegación fluida entre secciones' funcione correctamente. | 1/2h |
| US-13         | Visualización responsive en desktop             | T034     | Diseñar sección               | Crear diseño visual para 'visualización responsive en desktop'. | 1/2h |
|               |                                                  | T035     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización responsive en desktop'. | 1h |
|               |                                                  | T036     | Realizar pruebas              | Verificar que 'visualización responsive en desktop' funcione correctamente. | 1/2h |
| US-15         | Visualización responsive en dispositivos móviles | T037     | Diseñar sección               | Crear diseño visual para 'visualización responsive en dispositivos móviles'. | 1h |
|               |                                                  | T038     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización responsive en dispositivos móviles'. | 1/2h |
|               |                                                  | T039     | Realizar pruebas              | Verificar que 'visualización responsive en dispositivos móviles' funcione correctamente. | 1/2h |
| US-14         | Visualización responsive en tablet              | T040     | Diseñar sección               | Crear diseño visual para 'visualización responsive en tablet'. | 1/2h |
|               |                                                  | T041     | Implementar funcionalidad     | Codificar el componente necesario para 'visualización responsive en tablet'. | 1h |
|               |                                                  | T042     | Realizar pruebas              | Verificar que 'visualización responsive en tablet' funcione correctamente. | 1/2h |
| US-17         | Registro                                         | T043     | Diseñar sección               | Crear diseño visual para 'registro'. | 2h |
|               |                                                  | T044     | Implementar funcionalidad     | Codificar el componente necesario para 'registro'. | 2h |
|               |                                                  | T045     | Realizar pruebas              | Verificar que 'registro' funcione correctamente. | 1h |
| US-18         | Inicio de sesión                                 | T046     | Diseñar sección               | Crear diseño visual para 'inicio de sesión'. | 2h |
|               |                                                  | T047     | Implementar funcionalidad     | Codificar el componente necesario para 'inicio de sesión'. | 1h |
|               |                                                  | T048     | Realizar pruebas              | Verificar que 'inicio de sesión' funcione correctamente. | 1h |
| US-19         | Recuperación de contraseña                      | T049     | Diseñar sección               | Crear diseño visual para 'recuperación de contraseña'. | 2h |
|               |                                                  | T050     | Implementar funcionalidad     | Codificar el componente necesario para 'recuperación de contraseña'. | 1/2h |
|               |                                                  | T051     | Realizar pruebas              | Verificar que 'recuperación de contraseña' funcione correctamente. | 1h |

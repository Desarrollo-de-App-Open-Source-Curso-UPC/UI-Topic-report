# Capítulo V: Product Implementation, Validation & Deployment

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
| Software Deployment | Github pages | Despliegue continuo del sistema en ambientes de testing. | SaaS – [https://railway.app](https://railway.app) / [https://render.com](https://render.com) |
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

## Frontend (Landing Page - HTML, CSS, JavaScript)

### Convenciones generales:
- **Idioma**: Todo el código, incluyendo nombres de variables, funciones y clases, está escrito en **inglés**.
- **Indentación**: 2 espacios.
- **Formato de archivos**: `.html`, `.css`, `.js`
- **Estilo de código adoptado**:
  - [W3Schools HTML Style Guide](https://www.w3schools.com/html/html5_syntax.asp)
  - [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html)

### Nomenclatura:
- **Clases CSS**: `kebab-case` (ej. `main-container`)
- **IDs HTML**: `camelCase` (ej. `mainContent`)
- **Variables JS**: `camelCase` (ej. `userName`)
- **Funciones JS**: `camelCase` (ej. `handleClick()`)

---

## Frontend Web App (Angular + TypeScript)

### Convenciones generales:
- **Idioma**: Código completamente en **inglés**.
- **Estructura de carpetas**: Segregación por módulos y componentes.
- **Indentación**: 2 espacios.
- **Formato de archivos**: `.ts`, `.html`, `.css`

### Estilo de código adoptado:
- [Angular Style Guide (Oficial)](https://angular.io/guide/styleguide)
- [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)

### Nomenclatura:
- **Componentes**: `PascalCase` (ej. `UserProfileComponent`)
- **Servicios**: `camelCase` + sufijo `Service` (ej. `authService`)
- **Interfaces**: `PascalCase`, prefijo `I` opcional (ej. `User`, `IUser`)
- **Archivos**: `kebab-case` (ej. `user-profile.component.ts`)
- **Variables y funciones**: `camelCase`

---

## Backend (Java + Spring Boot)

### Convenciones generales:
- **Idioma**: Código y documentación interna en **inglés**.
- **Indentación**: 4 espacios.
- **Formato de archivos**: `.java`

### Estilo de código adoptado:
- [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
- [Spring Boot Features & Best Practices](https://docs.spring.io/spring-boot/docs/current/reference/html/features.html)

### Nomenclatura:
- **Clases**: `PascalCase` (ej. `UserService`)
- **Variables**: `camelCase` (ej. `userRepository`)
- **Constantes**: `UPPER_SNAKE_CASE` (ej. `MAX_USERS`)
- **Endpoints**: `kebab-case` para URLs (ej. `/api/user-profile`)
- **Paquetes**: Todo en minúsculas y separados por punto (ej. `com.project.backend.controller`)

---



### 5.1.4. Software Deployment Configuration

Para la Landing Page desarrollada en HTML, CSS y JavaScript, la configuración del despliegue en GitHub Pages se define de la siguiente manera:

**Repositorio de Código Fuente**

Se debe crear un repositorio en GitHub y subir todos los archivos del proyecto (HTML, CSS, JS).  
Es obligatorio que el archivo `index.html` esté ubicado en la raíz del repositorio para poder realizar el despliegue correctamente.

<br/>

![Software Deployment Configuration](assets/images/cap5/repo-landing-github.png)

## 5.2. Landing Page, Services & Applications Implementation

### 5.2.1 Sprint 1

#### 5.2.1.1. Sprint Planning 1

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
| Sprint 1 Velocity | 56 puntos |
| Sum of Story Points |  56 puntos |

#### 5.2.1.2 Aspect Leaders and Collaborators

## Aspect Leaders and Collaborators

Durante el Sprint 1, se han definido los principales aspectos a desarrollar, correspondientes a funcionalidades específicas como la visualización de contenido, navegación fluida, adaptabilidad responsiva y gestión de autenticación de usuarios.

Con el objetivo de asegurar una comunicación clara y eficiente dentro del equipo, se elaboró la siguiente matriz de liderazgo y colaboración (LACX), asignando para cada aspecto un líder responsable (L) y colaboradores de apoyo (C).

| Team Member (Last Name, First Name) | GitHub Username       | Mostrar Mensaje de Valor | Beneficios Segmentados | CTA con Redirección y Descarga | Barra de Navegación | Pasos del Funcionamiento | Video Explicativo | Footer Landing Page | Testimonios de Clientes | Preguntas Frecuentes | Formulario de Contacto | Navegación Fluida | Responsive Desktop | Responsive Móviles | Responsive Tablet | Registro | Inicio de Sesión | Recuperación de Contraseña |
|:------------------------------------|:----------------------|:------------------------|:------------------------|:-----------------------------|:-------------------|:------------------------|:-----------------|:--------------------|:------------------------|:--------------------|:----------------------|:------------------|:-------------------|:------------------|:------------------|:--------|:----------------|:---------------------------|
| Vendaño Balarezo, Williams Eduardo  | dev-willy-code         | L                        | C                        | C                             | C                   | C                        | L                 | C                    | C                        | C                    | C                      | L                  | C                   | C                  | C                  | C      | C                | C                         |
| Castro Alejos, Julio                | JulioXC4               | C                        | L                        | C                             | C                   | C                        | C                 | L                    | C                        | C                    | C                      | C                  | L                   | C                  | C                  | C      | C                | C                         |
| Guerra Perez, José Jahaziel         | jahazielgp             | C                        | C                        | L                             | C                   | L                        | C                 | C                    | L                        | C                    | C                      | C                  | C                   | L                  | C                  | C      | C                | C                         |
| Guzmán Cabrejos, Yaku Mateo         | yak-cod                | C                        | C                        | C                             | L                   | C                        | C                 | C                    | C                        | L                    | L                      | C                  | C                   | C                  | L                  | L      | C                | C                         |
| Shapiama Rivera, Gabriela Nicole    | GabrielaShapiama28     | C                        | C                        | C                             | C                   | C                        | C                 | C                    | C                        | C                    | C                      | C                  | C                   | C                  | C                  | C      | L                | L                         |


#### 5.2.1.3 Sprint Backlog 1

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

#### 5.2.1.4. Development Evidence for Sprint Review

Durante el Sprint 1, el equipo se enfocó exclusivamente en el desarrollo de la Landing Page de la plataforma Restock.
El objetivo principal fue construir una página pública funcional, atractiva visualmente y completamente responsiva, que comunique eficazmente la propuesta de valor de la plataforma a los usuarios potenciales.
A lo largo del Sprint se diseñaron e implementaron secciones clave como Hero, Sobre Nosotros, Beneficios, Testimonios, Preguntas Frecuentes, Tutoriales, Contacto y el Footer.
También se trabajó en asegurar la adaptabilidad móvil, el cumplimiento de criterios de accesibilidad y la optimización inicial para motores de búsqueda (SEO).

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
|--- | --- | --- | --- | --- | --- |
| GabrielaShapiama/UI-Topic-landing | feature/acces | f3de2d0 | fix(access): remove incorrect image. | Removed an incorrect image that was incorrectly placed in the access module. | 26-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/tutorial-section | 1c1d5e2 | fix(tutorial-section): fix tutorial links width | Fixed the width issue affecting the layout of tutorial links on different screens. | 26-04-2025 |
| Williams/UI-Topic-landing | feature/seo-tags-meta-tags | b50e3c3 | feat(seo-tags-meta-tags): adding seo tags and meta tags | Added SEO and meta tags to improve page indexing and online visibility. | 26-04-2025 |
| JulioXC4/UI-Topic-landing | feature/voice-reader-accessibility | 936c01d | feat(voice): add file voice.js | Added a new JavaScript file to handle voice-related functionalities. | 26-04-2025 |
| JulioXC4/UI-Topic-landing | feature/language-toggle | 5bf2a4f | feat(navbar): add language switch icon and console log for future functionality | Introduced a language switcher icon and set up console logs for future multi-language support. | 26-04-2025 |
| GabrielaShapiama/UI-Topic-landing | feature/acces | 4fd9958 | fix(access): fix text position. | Adjusted the text alignment issues on the access screen. | 26-04-2025 |
| GabrielaShapiama/UI-Topic-landing | feature/acces | a9b89b2 | fix(access): remove incorrect css. | Removed unnecessary or incorrect CSS rules from the access styles. | 26-04-2025 |
| GabrielaShapiama/UI-Topic-landing | feature/acces | c0f15db | style(access): change buttons format. | Updated the button styles to align with the platform's visual guidelines. | 25-04-2025 |
| jahazielgp/UI-Topic-landing | feature/fix-navbar | e293098 | fix(navbar): fix navbar. | Fixed layout and functionality issues in the navigation bar. | 25-04-2025 |
| jahazielgp/UI-Topic-landing | feature/benefits-section | d6cee23 | feat(benefits): add benefits section. | Added HTML and CSS structure for the Benefits section. | 25-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/tutorial-section | 4d7e12d | fix(tutorial-section): add tutorial css file | Added a dedicated CSS file to improve the Tutorial section styling. | 25-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | a3187cc | fix(footer-section): fix link to css | Fixed broken or incorrect link to the footer’s CSS file. | 25-04-2025 |
| Williams/UI-Topic-landing | feature/preguntas | c307001 | fix(preguntas): adding other files | Added missing assets and files needed for the FAQ section. | 25-04-2025 |
| Williams/UI-Topic-landing | feature/preguntas | 057ba2e | fix(preguntas): adding add dropdown menu | Implemented the dropdown functionality for the FAQ section. | 25-04-2025 |
| GabrielaShapiama/UI-Topic-landing | feature/access | 57c525a | feat(access): add navebar. | Created and styled the navbar for the access page. | 25-04-2025 |
| GabrielaShapiama/UI-Topic-landing | feature/access | 1269f12 | chore(access): translate some comments. | Translated developer comments into English for better clarity. | 25-04-2025 |
| GabrielaShapiama/UI-Topic-landing | feature/access | e48c646 | fix(access): remove incorrect function. | Removed a non-functional or unnecessary JavaScript function. | 25-04-2025 |
| GabrielaShapiama/UI-Topic-landing | feature/access | 84764de | feat(access): add recovery password logic. | Implemented logic for the password recovery feature. | 25-04-2025 |
| GabrielaShapiama/UI-Topic-landing | feature/access | f787614 | feat(access): add access to plataform. | Added login and basic access functionality to the platform. | 25-04-2025 |
| Williams/UI-Topic-landing | feature/descargar | 06f232a | fix(descargar): make section fully responsive for all screen sizes | Made the Descargar section fully responsive across all devices. | 25-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | ef64a65 | fix(footer-section): fix vh | Adjusted viewport height (vh) settings in the footer section. | 23-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | 5bcde82 | feat(tutorial-section): add tutorial section | Built the complete Tutorial section (HTML and CSS). | 23-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | 7ecf4f2 | fix(footer-section): fix responsive | Fixed responsiveness issues in the footer layout. | 23-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | 1dea22f | feat(contacto-section): add responsive | Made the Contact section fully responsive. | 23-04-2025 |
| Williams/UI-Topic-landing | feature/descargar | e4598c3 | feat(descargar): create descargar section(html,css) | Created the Download section with full HTML and CSS styling. | 22-04-2025 |
| Williams/UI-Topic-landing | feature/preguntas | 64f1af0 | feat(preguntas): create preguntas frecuentes(html,css) | Developed the FAQ (Preguntas Frecuentes) section structure and style. | 22-04-2025 |
| Williams/UI-Topic-landing | feature/testimonios | 74f270e | fix(testimonios): moving section to main tag | Moved the Testimonials section to the main content area for better semantics. | 22-04-2025 |
| Williams/UI-Topic-landing | feature/testimonios | 9e3685a | fix(testimonios): updating testimonios(html) | Updated the Testimonials section HTML content. | 22-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | cdc23c1 | feat(footer-section): add responsive | Implemented responsive behavior for the footer section. | 22-04-2025 |
| jahazielgp/UI-Topic-landing | feature/about-us-section | 71e82c6 | feat(about-us): add about-us section. | Added the About Us section including structure and initial styling. | 22-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | 7bb7da7 | feat(footer-section): add icons | Added social media icons into the footer layout. | 22-04-2025 |
| jahazielgp/UI-Topic-landing | feature/develop | f6e104a | chore: refactor directories. | Restructured project folders for better organization and scalability. | 21-04-2025 |
| Williams/UI-Topic-landing | feature/testimonios | 27377d0 | feat(testimonios): add testimonios(html,css,img) | Created the Testimonials section including text and images. | 21-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/contacto-section | b469827 | feat(contacto-section): add contacto html and css | Built the Contact section with full HTML and CSS. | 21-04-2025 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | efd9aac | feat(footer/section): add footer html and css | Implemented the complete Footer section including structure and styles. | 21-04-2025 |
| jahazielgp/UI-Topic-landing | feature/hero-section | 9341bde | feat(hero-section): add responsive design. | Made the Hero section fully responsive for mobile and desktop. | 20-04-2025 |
| jahazielgp/UI-Topic-landing | feature/hero-section | 7746107 | feat(hero-section): add hero html, css and js components. | Built the Hero section with its respective HTML, CSS, and JavaScript. | 20-04-2025 |
| jahazielgp/UI-Topic-landing | feature/develop | 303ad89 | chore: initial commit | Project initialization with base structure. | 20-04-2025 |
| jahazielgp/UI-Topic-landing | main | 556268a | Initial commit | Setup initial project files and base structure. | 02-04-2025 |

#### Productos según alcance del Sprint:

##### Landing Page

Durante el Sprint 1 se implementó la Landing Page de Restock.
Los principales avances fueron:

- Diseño responsivo para diferentes tamaños de pantalla.

- Creación de secciones: Hero, Sobre Nosotros, Beneficios, Testimonios, Preguntas Frecuentes, Tutorial, Contacto y Footer.

- Aplicación de buenas prácticas de accesibilidad (etiquetado semántico, contraste adecuado).

- Optimización inicial para motores de búsqueda (SEO básico).

- Implementación de navegación fluida entre secciones.

- Validación de compatibilidad en navegadores y dispositivos.

#### 5.2.1.6 Services Documentation Evidence for Sprint Review

Durante este sprint se completó el diseño e implementación del Landing Page del sistema, el cual forma parte del acceso inicial al sistema y constituye un punto de entrada fundamental para los usuarios. Aunque no se implementaron endpoints tradicionales de tipo REST en este sprint, se documenta a continuación la URL del recurso publicado, junto con evidencia de despliegue, interacción y commits relacionados.

**Descripción del Logro:**

-Implementación del Landing Page estático.

-Deployment del landing page.

### Recursos del Sprint

| Recurso      | Acción implementada   | Método HTTP | URL / Endpoint                      | Link de repositorio         |
|--------------|------------------------|-------------|-------------------------------------|---------------------------|
| Landing Page | Visualización inicial | GET         | https://desarrollo-de-app-open-source-curso-upc.github.io/UI-Topic-landing/               | https://github.com/Desarrollo-de-App-Open-Source-Curso-UPC/UI-Topic-landing   |

#### 5.2.1.7. Software Deployment Evidence for Sprint Review.

Durante este Sprint, se realizaron actividades de despliegue de la Landing Page utilizando GitHub Pages como plataforma de hosting. A continuación, se detallan los pasos ejecutados:

1- Se accedió a la sección Settings del repositorio.
Dentro de Pages, se seleccionó la rama (main o master) y la carpeta (root o /docs) desde la cual GitHub Pages debía publicar el sitio.
Se guardaron los cambios para activar la publicación automática.

![Foto deployment step 1](assets/images/cap5/step-1.png) 
<br/>

2- por default ya esta activado el https

![Foto deployment step 2](assets/images/cap5/step-2.png) 
<br/>

3- En la seccion "All workflows" se puede ver que la app se esta deployando.

![Foto deployment step 3](assets/images/cap5/step-3.png) 
<br/>

4- El landing page fue exitosamente deployado

![Foto deployment step 4](assets/images/cap5/step-4.png) 
<br/>

5- Se obtuvo y verificó la URL pública proporcionada por GitHub Pages.

![Foto deployment step 5](assets/images/cap5/step-5.png) 
<br/>

#### 5.2.1.8 Team Collaboration Insights during Sprint

### Desarrollo de las Actividades de Implementación

Durante el Sprint 1, el equipo de Restock se enfocó en el desarrollo de la **Landing Page**.
Las actividades de implementación se llevaron a cabo de la siguiente manera:

- Se crearon ramas específicas para cada sección o funcionalidad (`feature/[nombre-de-seccion]`), permitiendo un trabajo paralelo organizado.
- Cada miembro del equipo asumió la responsabilidad de desarrollar una o más secciones de la Landing Page.
- Se realizaron commits frecuentes, registrando avances de manera continua y detallada.
- Las funcionalidades desarrolladas se integraron mediante Pull Requests hacia la rama `develop`.
- Se mantuvo una comunicación constante mediante la plataforma Discord para coordinar avances y resolver dudas en tiempo real.
- Se aplicaron buenas prácticas de programación, control de versiones y colaboración en equipo.

Gracias a esta organización, se logró cumplir de manera efectiva el objetivo del sprint, garantizando que todos los integrantes contribuyeran de forma activa en el desarrollo de la Landing Page.

---

### Evidencia de Colaboración en GitHub

Se presenta a continuación la captura de los insights del repositorio de GitHub, correspondiente al Sprint 1:

![Captura Insights](assets/images/evidencia-Team-Collaboration-Insights-during-Sprint.png)

**Insights:**
- **26 Pull Requests** fusionados correctamente.
- **5 autores** contribuyendo al repositorio.
- **39 commits** realizados en el periodo del Sprint.
- Participación activa de todos los miembros asignados al desarrollo de la Landing Page.
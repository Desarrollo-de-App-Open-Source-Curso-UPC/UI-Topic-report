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


## 5.1.3. Source Code Style Guide & Conventions.


## 5.1.4. Source Code Management

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

### 5.2.1.4. Development Evidence for Sprint Review

Durante el Sprint 1, el equipo se enfocó exclusivamente en el desarrollo de la Landing Page de la plataforma Restock.
El objetivo principal fue construir una página pública funcional, atractiva visualmente y completamente responsiva, que comunique eficazmente la propuesta de valor de la plataforma a los usuarios potenciales.
A lo largo del Sprint se diseñaron e implementaron secciones clave como Hero, Sobre Nosotros, Beneficios, Testimonios, Preguntas Frecuentes, Tutoriales, Contacto y el Footer.
También se trabajó en asegurar la adaptabilidad móvil, el cumplimiento de criterios de accesibilidad y la optimización inicial para motores de búsqueda (SEO).

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
|--- | --- | --- | --- | --- | --- |
| GabrielaShapiama/UI-Topic-landing | feature/acces | f3de2d0 | fix(access): remove incorrect image. | Removed an incorrect image that was incorrectly placed in the access module. | 2025-04-26 |
| Yaku Guzman/UI-Topic-landing | feature/tutorial-section | 1c1d5e2 | fix(tutorial-section): fix tutorial links width | Fixed the width issue affecting the layout of tutorial links on different screens. | 2025-04-26 |
| Williams/UI-Topic-landing | feature/seo-tags-meta-tags | b50e3c3 | feat(seo-tags-meta-tags): adding seo tags and meta tags | Added SEO and meta tags to improve page indexing and online visibility. | 2025-04-26 |
| JulioXC4/UI-Topic-landing | feature/voice-reader-accessibility | 936c01d | feat(voice): add file voice.js | Added a new JavaScript file to handle voice-related functionalities. | 2025-04-26 |
| JulioXC4/UI-Topic-landing | feature/language-toggle | 5bf2a4f | feat(navbar): add language switch icon and console log for future functionality | Introduced a language switcher icon and set up console logs for future multi-language support. | 2025-04-26 |
| GabrielaShapiama/UI-Topic-landing | feature/acces | 4fd9958 | fix(access): fix text position. | Adjusted the text alignment issues on the access screen. | 2025-04-26 |
| GabrielaShapiama/UI-Topic-landing | feature/acces | a9b89b2 | fix(access): remove incorrect css. | Removed unnecessary or incorrect CSS rules from the access styles. | 2025-04-26 |
| GabrielaShapiama/UI-Topic-landing | feature/acces | c0f15db | style(access): change buttons format. | Updated the button styles to align with the platform's visual guidelines. | 2025-04-25 |
| jahazielgp/UI-Topic-landing | feature/fix-navbar | e293098 | fix(navbar): fix navbar. | Fixed layout and functionality issues in the navigation bar. | 2025-04-25 |
| jahazielgp/UI-Topic-landing | feature/benefits-section | d6cee23 | feat(benefits): add benefits section. | Added HTML and CSS structure for the Benefits section. | 2025-04-25 |
| Yaku Guzman/UI-Topic-landing | feature/tutorial-section | 4d7e12d | fix(tutorial-section): add tutorial css file | Added a dedicated CSS file to improve the Tutorial section styling. | 2025-04-25 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | a3187cc | fix(footer-section): fix link to css | Fixed broken or incorrect link to the footer’s CSS file. | 2025-04-25 |
| Williams/UI-Topic-landing | feature/preguntas | c307001 | fix(preguntas): adding other files | Added missing assets and files needed for the FAQ section. | 2025-04-25 |
| Williams/UI-Topic-landing | feature/preguntas | 057ba2e | fix(preguntas): adding add dropdown menu | Implemented the dropdown functionality for the FAQ section. | 2025-04-25 |
| GabrielaShapiama/UI-Topic-landing | feature/access | 57c525a | feat(access): add navebar. | Created and styled the navbar for the access page. | 2025-04-25 |
| GabrielaShapiama/UI-Topic-landing | feature/access | 1269f12 | chore(access): translate some comments. | Translated developer comments into English for better clarity. | 2025-04-25 |
| GabrielaShapiama/UI-Topic-landing | feature/access | e48c646 | fix(access): remove incorrect function. | Removed a non-functional or unnecessary JavaScript function. | 2025-04-25 |
| GabrielaShapiama/UI-Topic-landing | feature/access | 84764de | feat(access): add recovery password logic. | Implemented logic for the password recovery feature. | 2025-04-25 |
| GabrielaShapiama/UI-Topic-landing | feature/access | f787614 | feat(access): add access to plataform. | Added login and basic access functionality to the platform. | 2025-04-25 |
| Williams/UI-Topic-landing | feature/descargar | 06f232a | fix(descargar): make section fully responsive for all screen sizes | Made the Descargar section fully responsive across all devices. | 2025-04-25 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | ef64a65 | fix(footer-section): fix vh | Adjusted viewport height (vh) settings in the footer section. | 2025-04-23 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | 5bcde82 | feat(tutorial-section): add tutorial section | Built the complete Tutorial section (HTML and CSS). | 2025-04-23 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | 7ecf4f2 | fix(footer-section): fix responsive | Fixed responsiveness issues in the footer layout. | 2025-04-23 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | 1dea22f | feat(contacto-section): add responsive | Made the Contact section fully responsive. | 2025-04-23 |
| Williams/UI-Topic-landing | feature/descargar | e4598c3 | feat(descargar): create descargar section(html,css) | Created the Download section with full HTML and CSS styling. | 2025-04-22 |
| Williams/UI-Topic-landing | feature/preguntas | 64f1af0 | feat(preguntas): create preguntas frecuentes(html,css) | Developed the FAQ (Preguntas Frecuentes) section structure and style. | 2025-04-22 |
| Williams/UI-Topic-landing | feature/testimonios | 74f270e | fix(testimonios): moving section to main tag | Moved the Testimonials section to the main content area for better semantics. | 2025-04-22 |
| Williams/UI-Topic-landing | feature/testimonios | 9e3685a | fix(testimonios): updating testimonios(html) | Updated the Testimonials section HTML content. | 2025-04-22 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | cdc23c1 | feat(footer-section): add responsive | Implemented responsive behavior for the footer section. | 2025-04-22 |
| jahazielgp/UI-Topic-landing | feature/about-us-section | 71e82c6 | feat(about-us): add about-us section. | Added the About Us section including structure and initial styling. | 2025-04-22 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | 7bb7da7 | feat(footer-section): add icons | Added social media icons into the footer layout. | 2025-04-22 |
| jahazielgp/UI-Topic-landing | feature/develop | f6e104a | chore: refactor directories. | Restructured project folders for better organization and scalability. | 2025-04-21 |
| Williams/UI-Topic-landing | feature/testimonios | 27377d0 | feat(testimonios): add testimonios(html,css,img) | Created the Testimonials section including text and images. | 2025-04-21 |
| Yaku Guzman/UI-Topic-landing | feature/contacto-section | b469827 | feat(contacto-section): add contacto html and css | Built the Contact section with full HTML and CSS. | 2025-04-21 |
| Yaku Guzman/UI-Topic-landing | feature/footer-section | efd9aac | feat(footer/section): add footer html and css | Implemented the complete Footer section including structure and styles. | 2025-04-21 |
| jahazielgp/UI-Topic-landing | feature/hero-section | 9341bde | feat(hero-section): add responsive design. | Made the Hero section fully responsive for mobile and desktop. | 2025-04-20 |
| jahazielgp/UI-Topic-landing | feature/hero-section | 7746107 | feat(hero-section): add hero html, css and js components. | Built the Hero section with its respective HTML, CSS, and JavaScript. | 2025-04-20 |
| jahazielgp/UI-Topic-landing | feature/develop | 303ad89 | chore: initial commit | Project initialization with base structure. | 2025-04-20 |
| jahazielgp/UI-Topic-landing | feature/develop | 556268a | Initial commit | Setup initial project files and base structure. | 2025-04-02 |

#### Productos según alcance del Sprint:

##### Landing Page

Durante el Sprint 1 se implementó la Landing Page de Restock.
Los principales avances fueron:

Diseño responsivo para diferentes tamaños de pantalla.

Creación de secciones: Hero, Sobre Nosotros, Beneficios, Testimonios, Preguntas Frecuentes, Tutorial, Contacto y Footer.

Aplicación de buenas prácticas de accesibilidad (etiquetado semántico, contraste adecuado).

Optimización inicial para motores de búsqueda (SEO básico).

Implementación de navegación fluida entre secciones.

Validación de compatibilidad en navegadores y dispositivos.
# Capítulo VI: Product Implementation, Validation & Deployment

## 6.1. Software Configuration Management

### 6.1.1. Software Development Environment Configuration

### 6.1.2. Source Code Management

### 6.1.3. Source Code Style Guide & Conventions

### 6.1.4. Software Deployment Configuration

## 6.2. Landing Page, Services & Applications Implementation

### 6.2.1. Sprint 1

#### 6.2.1.1. Sprint Planning 1
En esta sección especificaremos los aspectos principales del Sprint Planning Meeting. A continuación se coloca el cuadro de resumen del sprint planning meeting:

| **Sprint #**                          | Sprint 1                                   |
|--------------------------------------|--------------------------------------------|
| **Sprint Planning Background**       |                                            |
| **Date**                             | 2025-05-03                                 |
| **Time**                             | 10:00 AM/PM                                |
| **Location**                         | Lima, Perú |
| **Prepared By**                      | Valenzuela Vallejos, Stefano Alessandro              |
| **Attendees (to planning meeting)**  |Maria Alejandra Díaz Villacrez <br> Jose Daniel Mario Calderon Huaman <br> Jair Andreé Coraje Bayona <br> Stefano Alessandro Valenzuela Vallejos <br> Jeremi Jose Antonio Fretel  |
| **Sprint n – 1 Review Summary**      | No aplica, ya que este es el Sprint inicial del proyecto. |
| **Sprint n – 1 Retrospective Summary** | No aplica, ya que este es el Sprint inicial del proyecto. |
| **Sprint Goal & User Stories**       |                                            |
| **Sprint n Goal**                    | **Nuestro enfoque** está en entregar la primera versión funcional del sistema, incluyendo el registro, inicio de sesión y visualizaciones básicas de salud. <br> **Creemos que** esto brinda confianza y utilidad a los cuidadores y familiares. <br>**Esto se confirmará cuando** los usuarios puedan registrarse, iniciar sesión y visualizar los reportes iniciales y ubicación del paciente a través del landing page desplegado. |
| **Sprint n Velocity**                | 19 |
| **Sum of Story Points**              | 19 |

#### 6.2.1.2. Aspect Leaders and Collaborators
En esta sección el equipo incluiremos la elaboración de un artefacto Leadership-andCollaboration Matrix (LACX), que indique por cada aspecto dentro del alcance del Sprint.

| Team Member (Last Name, First Name)       | GitHub Username | Acceso a la cuenta	 Leader (L) / Collaborator (C) | Registro de cuenta Leader (L) / Collaborator (C) | Estadísticas del paciente	Leader (L) / Collaborator (C) | Último reporte del paciente	 Leader (L) / Collaborator (C) | Captura de ubicación Leader (L) / Collaborator (C) | 
|-------------------------------------------|-----------------|---------------------------------------------|---------------------------------------------|-----|---------------------------------------------|---------------------------------------------|
| Valenzuela Vallejos, Alessandro             | AlessandroUPC   | L                                           | L                                        | L |                               C              | C
| Coraje Bayona, Jair André              | drkdevv1          | C                                           | C                                           | C | L                                           | C
| Calderón Huamán, José Daniel           | Jair365          | C                                           | C                                           | C | C                                           | L

#### 6.2.1.3. Sprint Backlog 1
A continuación, la estructura de la tabla para el Sprint 1 :

| Sprint # | Sprint 1 | 
|----------------|------------------|

| User Story Id | User Story Title | Work-Item / Task Id | Work-Item / Task Title | Description | Estimation (Hours) | Assigned To | Status (To-do / In-Process / To-Review / Done) |
|----------------|------------------|----------------------|-------------------------|-------------|---------------------|--------------|-------------------------------------------------|
|     US001  |      Acceso a la cuenta (Web application)    |    T1            |      Desarrollar función de validación de credenciales del usuario                 |       Implementar función para acceder a cuenta de usuario. Y poder verificar las credenciales y datos de la persona.               |             4            |        Jair Andreé Coraje Bayona     |        Done             |              |                                                 |
|  US003        |  Registro de cuenta (Web Application)        |           T2     |         Desarrollar función de registro de usuario         |            Implementar función para registrio en el sistema.         |             4            |   Jair Andreé Coraje Bayona           |            Done         |              |                                                 |
|     US032     |       Estadísticas sobre reportes del paciente (Frontend)   |         T3       |           Desarrollar visualizaciones estadísticas que permitan a los usuarios analizar el estado de salud del paciente.        |             Implementar una tabla de visualizaciones estadísticas que permitan a los usuarios analizar el estado de salud del paciente mediante datos históricos.         |               8          |      Jose Daniel Mario Calderon Huaman       |           Done          |              |                                                 |
|     US033     |    Consulta del último reporte del paciente (Frontend)      |       T4         |       Desarrollar una función que muestre el reporte más reciente del paciente.            |          Implementar una función que muestre el reporte más reciente del paciente, proporcionando información actualizada sobre su condición.               |            estado de salud del paciente.	Implementar una tabla de visualizaciones estadísticas que permitan a los usuarios analizar el estado de salud del paciente mediante datos históricos.	8	Jose Daniel Mario Calderon Huaman	Done8             |     Jair Andreé Coraje Bayona         |         To-Review            |              |                                                 |
|     US034     |   Captura de Ubicación       |        T5        |           Desarollar la primera función de transmición para posición o ubicación del usuario.         |       Implementar la transmicion de la posición del usuario, con el fin de facilitar la localización en caso de emergencias.               |              5           |       Jose Daniel Mario Calderon Huaman      |           Done          |              |                                                 |


#### 6.2.1.4. Development Evidence for Sprint Review
| Repository            | Branch             | Commit Id | Commit Message                  | Commit Message Body                                                                 | Commited on (Date) |
|-----------------------|--------------------|-----------|----------------------------------|--------------------------------------------------------------------------------------|---------------------|
| user/repositoryname   | feature/loremipsum | 14ca4e3   | feat: consectetur adipiscing elit | Curabitur quis placerat nulla. Fusce malesuada faucibus quam, ut condimentum velit rutrum ut. | 04/09/2021          |

#### 6.2.1.5. Testing Suite Evidence for Sprint Review
| Repository            | Branch             | Commit Id | Commit Message                  | Commit Message Body                                                                 | Commited on (Date) |
|-----------------------|--------------------|-----------|----------------------------------|--------------------------------------------------------------------------------------|---------------------|
| user/repositoryname   | feature/loremipsum | 14ca4e3   | feat: consectetur adipiscing elit | Curabitur quis placerat nulla. Fusce malesuada faucibus quam, ut condimentum velit rutrum ut. | 04/09/2021          |

#### 6.2.1.6. Execution Evidence for Sprint Review
| Repository            | Branch             | Commit Id | Commit Message                  | Commit Message Body                                                                 | Commited on (Date) |
|-----------------------|--------------------|-----------|----------------------------------|--------------------------------------------------------------------------------------|---------------------|
| user/repositoryname   | feature/loremipsum | 14ca4e3   | feat: consectetur adipiscing elit | Curabitur quis placerat nulla. Fusce malesuada faucibus quam, ut condimentum velit rutrum ut. | 04/09/2021          |

#### 6.2.1.7. Services Documentation Evidence for Sprint Review

#### 6.2.1.8. Software Deployment Evidence for Sprint Review

#### 6.2.1.9. Team Collaboration Insights during Sprint

## 6.3. Validation Interviews

### 6.3.1. Diseño de Entrevistas

### 6.3.2. Registro de Entrevistas

### 6.3.3. Evaluaciones según heurísticas

## 6.4. Video About-the-Product

## 7. Conclusiones

### 7.1. Conclusiones y recomendaciones

**Conclusiones:**

- A lo largo del desarrollo del proyecto, se logró implementar una solución basada en Internet de las Cosas (IoT) que permite monitorear los niveles de glucosa en sangre y emitir alertas en tiempo real ante situaciones críticas, mejorando así la seguridad y calidad de vida de las personas con diabetes.
- El uso de arquitectura en capas, como se presentó en los diagramas C4, permitió una clara separación de responsabilidades entre interfaz, lógica de aplicación, dominio e infraestructura, facilitando la escalabilidad y mantenibilidad del sistema.
- El trabajo en equipo fue clave para el éxito del proyecto. Se logró una colaboración efectiva en la planificación, el diseño y el desarrollo, fomentando un entorno inclusivo y participativo.
- Las entrevistas realizadas y el enfoque en la experiencia del usuario aseguraron que el sistema cubriera necesidades reales del público objetivo, validando su utilidad y viabilidad.

**Recomendaciones:**

- Para futuras versiones del proyecto, se recomienda incluir inteligencia artificial que permita anticipar posibles eventos de riesgo con base en patrones históricos de medición.
- Considerar la integración del sensor con servicios de emergencia o aplicaciones móviles de terceros para una mejor respuesta ante situaciones críticas.
- Continuar con pruebas de campo que validen el comportamiento del sistema en diferentes contextos y condiciones ambientales.
- Desarrollar una versión portable y de bajo consumo energético que pueda ser usada de forma continua por los usuarios.

---

### 7.2. Video About-the-Team

>  Puedes ver nuestro video de presentación del equipo y el proyecto en el siguiente enlace:  
[Video About-the-Team]()  
>

---

### 8. Bibliografía

- Evans, E. (2004). *Domain-Driven Design: Tackling Complexity in the Heart of Software*. Addison-Wesley.
- Newman, S. (2015). *Building Microservices: Designing Fine-Grained Systems*. O’Reilly Media.
- Fielding, R. (2000). *Architectural Styles and the Design of Network-based Software Architectures* (Doctoral dissertation, University of California).
- IEEE Standards Association. (2020). *IEEE Standard for Software and System Test Documentation*.
- Organización Mundial de la Salud (OMS). (2023). *Informe mundial sobre la diabetes*. Recuperado de [https://www.who.int/es/news-room/fact-sheets/detail/diabetes](https://www.who.int/es/news-room/fact-sheets/detail/diabetes)
- Mayo Clinic. (2023). *Diabetes - Síntomas y causas*. Recuperado de [https://www.mayoclinic.org/es/diseases-conditions/diabetes/symptoms-causes/syc-20371444](https://www.mayoclinic.org/es/diseases-conditions/diabetes/symptoms-causes/syc-20371444)

---

### 9. Anexos

<table>
    <thead>
        <tr>
            <th>Sección</th>
            <th>Características del video</th>
            <th>Sobre el contenido</th>
            <th>Integración y entrega</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Capítulo II</td>
            <td>
                Cantidad de videos: 1 <br> 
                Nomenclatura: Needfinding Interviews <br>
                Formato: Needfinding Interviews.mp4 <br>
                Duración: 21:40
            </td>
            <td>
                En este video se visualizarán las entrevistas realizadas a los distintos segmentos establecidos en el informe.
            </td>
            <td>
                Link: 
                <a href="https://upcedupe-my.sharepoint.com/:v:/g/personal/u202214695_upc_edu_pe/Eao6yknAZXBCiO9G8dnmag8Bj83wFn--OjyjVKAQa41NUA?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=fafxFo" target="_blank">
                    Needfinding Interviews
                </a> 
                <br><br>
                <img src="../assets/img/Anexo/Anexo entrevista.png" width="1000"> 
            </td>
        </tr>
    </tbody>
</table>

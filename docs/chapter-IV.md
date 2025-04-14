# Capítulo IV: Solution Software Design

## 4.1. Strategic-Level Domain-Driven Design

### 4.1.1. EventStorming

#### 4.1.1.1. Candidate Context Discovery

#### 4.1.1.2. Domain Message Flows Modeling

#### 4.1.1.3. Bounded Context Canvases

### 4.1.2. Context Mapping

### 4.1.3. Software Architecture

#### 4.1.3.1. Software Architecture System Landscape Diagram
Este diagrama ofrece una visión general de alto nivel de todos los actores y sistemas involucrados en el ecosistema de Glucova. Incluye a los usuarios clave (Supervisor y Especialista Encargado), el sistema principal Glucova, y sistemas externos como Stripe. Permite comprender cómo interactúan estos elementos entre sí, proporcionando una perspectiva global de la arquitectura del sistema.​


<p align="center">
  <img src="../assets/img/chapter-IV/c4 models/SystemLandscape.png" width="1000">
</p>

#### 4.1.3.2. Software Architecture Context Level Diagrams
Este diagrama detalla cómo el sistema Glucova se relaciona con sus usuarios (Supervisor, Especialista Encargado y Paciente) y con sistemas externos como Azure IoT Hub, el Dispositivo IoT y Stripe. Proporciona una comprensión clara del entorno en el que opera Glucova y las interacciones clave que tiene con otros sistemas y actores.​


<p align="center">
  <img src="../assets/img/chapter-IV/c4 models/ContextDiagram.png" width="1000">
</p>

#### 4.1.3.3. Software Architecture Container Level Diagrams
Este diagrama descompone el sistema Glucova en sus principales contenedores o componentes, como la Aplicación Web, Aplicación Móvil, API REST, Base de Datos, Servicio de Autenticación, Aplicación Embebida (IoT), Servicio de Notificaciones y Servicio de Logs. Muestra cómo estos contenedores interactúan entre sí y con sistemas externos, proporcionando una visión detallada de la arquitectura interna de Glucova.​

<p align="center">
  <img src="../assets/img/chapter-IV/c4 models/Container Diagram.png" width="1000">
</p>



#### 4.1.3.4. Software Architecture Deployment Diagrams

## 4.2. Tactical-Level Domain-Driven Design

### 4.2.1. Bounded Context

#### 4.2.1.1. Domain Layer

#### 4.2.1.2. Interface Layer

#### 4.2.1.3. Application Layer

#### 4.2.1.4. Infrastructure Layer

#### 4.2.1.5. Bounded Context Software Architecture Component Level Diagrams

#### 4.2.1.6. Bounded Context Software Architecture Code Level Diagrams

##### 4.2.1.6.1. Bounded Context Domain Layer Class Diagrams

##### 4.2.1.6.2. Bounded Context Database Design Diagram
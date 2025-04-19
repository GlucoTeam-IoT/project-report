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
En esta parte se representa cómo se organizan físicamente los componentes de un sistema de software dentro del entorno donde será ejecutado.
<p align="center">
  <img src="../assets/img/chapter-IV/c4 models/Software Architecture Deployment Diagrams.png" width="1000">
</p>

## 4.2. Tactical-Level Domain-Driven Design

### 4.2.1. Bounded Context: Alerts

Este bounded context abarca todas las funcionalidades relacionadas con el sensor IoT. Incluye la gestión de sensores y envío de alertas, así como la
sincronización con la aplicación móvil y web.

### Clase Principal: `DeviceAlertSystem`

**Descripción**:  
Sistema de alertas responsable de detectar y notificar niveles críticos de glucosa al usuario y especialistas.

### Atributos

| Nombre                | Tipo de Dato                 | Descripción                                                  |
|-----------------------|------------------------------|--------------------------------------------------------------|
| `alertID`             | `String`                     | Identificador único de la alerta                             |
| `alertType`           | `String`                     | Tipo de alerta: "ALTA", "BAJA", "NORMAL"                     |
| `glucoseLevel`        | `Float`                      | Nivel de glucosa detectado                                   |
| `timestamp`           | `DateTime`                   | Fecha y hora en la que se generó la alerta                   |
| `status`              | `AlertStatus`                | Estado de la alerta (CREATED, SENT, ACKNOWLEDGED, ESCALATED) |
| `notificationChannel` | `List<NotificationChannel>`  | Canales para enviar la alerta                                |

### Relaciones

- **Composición**: `MonitoringDevice` (el dispositivo que envía los datos)
- **Agregación**: `User` (persona que recibe la alerta)
- **Agregación**: `Contact` (persona de emergencia notificada si no hay respuesta)

### Métodos

- `generateAlert()`: Evalúa el nivel de glucosa y crea una alerta si está fuera del rango.
- `sendNotification()`: Envía la notificación al usuario a través de canales definidos.
- `escalateAlert()`: Notifica a un contacto de emergencia si el usuario no responde.
- `acknowledge()`: Marca la alerta como respondida o controlada.

---

### Clases Relacionadas

#### MonitoringDevice

**Descripción**:  
Dispositivo que mide los niveles de glucosa.

##### Atributos

| Nombre         | Tipo de Dato | Descripción                      |
|----------------|--------------|----------------------------------|
| `deviceID`     | `String`     | Identificador del dispositivo    |
| `deviceName`   | `String`     | Nombre del dispositivo           |
| `location`     | `String`     | Ubicación del dispositivo        |
| `batteryLevel` | `Int`        | Nivel de batería del dispositivo |

##### Métodos

- `sendData()`: Envía los datos de glucosa.
- `syncSchedule()`: Sincroniza el horario de medicación.

#### User

##### Atributos

| Nombre     | Tipo de Dato | Descripción                 |
|------------|--------------|-----------------------------|
| `userID`   | `String`     | Identificador del usuario   |
| `name`     | `String`     | Nombre del usuario          |
| `phone`    | `String`     | Número de teléfono          |
| `email`    | `String`     | Correo electrónico          |

##### Métodos

- `receiveAlert(alert: DeviceAlertSystem)`: Recibe una alerta del sistema.

#### Contact

##### Atributos

| Nombre       | Tipo de Dato | Descripción                          |
|--------------|--------------|--------------------------------------|
| `contactID`  | `String`     | Identificador del contacto           |
| `relation`   | `String`     | Relación con el usuario              |
| `phone`      | `String`     | Número de teléfono del contacto      |

##### Métodos

- `notifyEmergency(alert: DeviceAlertSystem)`: Notifica al contacto en caso de emergencia.

####  NotificationChannel *(Interfaz o Clase Abstracta)*

#### Métodos

- `send(message: String, recipient: User)`: Envía un mensaje al usuario.

#### AlertStatus *(Enum)*

- `CREATED`
- `SENT`
- `ACKNOWLEDGED`
- `ESCALATED`

#### 4.2.1.1. Domain Layer
En el núcleo del sistema Glucova, la clase central identificada es `DeviceAlertSystem`, que representa el sensor inteligente utilizado para el monitoreo continuo de pacientes con diabetes. Esta entidad encapsula las reglas de negocio fundamentales relacionadas con la adquisición y gestión de datos fisiológicos críticos.

#### Reglas de Negocio

- **Componentes Obligatorios**: El dispositivo debe integrar sensores esenciales, incluyendo:
  - Sensor de localización
  - Sensor de alerta


- **Condiciones de Operación**: La funcionalidad completa del dispositivo se garantiza únicamente cuando:
  - Está conectado a la aplicación móvil correspondiente.
  - Dispone de una conexión activa a Internet para la transmisión y sincronización de datos.

Este diseño asegura que el dispositivo opere de manera eficiente dentro del ecosistema de Glucova, facilitando en tiempo real del estado de salud del paciente al respectivo encargado.
#### 4.2.1.2. Interface Layer
##### Entites
- DeviceAlertSystem: Representa la alerta del monitor de diabetes
##### Value Objects
- Alert: Representa la alerta enviada.
- Location: Representa la ubicación geográfica de un dispositivo.
##### Enums
- SensorType: Enumera los tipos de sensores disponibles.
##### Factories
- DeviceFactory: Fabrica para crear instancias de dispositivos.
##### Interfaces
- DeviceRepository: Interfaz para la gestión de datos.

#### 4.2.1.3. Application Layer
En esta sección se presentan las interfaces serán consumidas por la aplicación cliente para realizar cambios relacionados a los datos de la pulsera
- **DeviceController**: Define las funciones que serán consumidos por la aplicación cliente para realizar cambios relacionados a los datos de la pulsera.

**Aplicacition Layer** En esta sección presentamos los commandHandlers y EventHandlers encargados de manejar los comandos y eventos respectivos tras las solicitudes realizadas a las implementaciones de las interfaces del ítem anterior.
- **CreateDeviceCommandHandler**: Maneja el comando de crear un nuevo dispositivo.
- **DeviceCreatedEventHandler**: Maneja el evento de creación de un nuevo dispositivo.
#### 4.2.1.4. Infrastructure Layer
En esta sección presentamos las clases que se encargan de conectar con servicios externos:
- **LocationServiceProvider**: Proveedor de servicios externos para obtener datos de ubicación.
- **NotificationServiceProvider**: Proveedor de servicios externos para enviar notificaciones

#### 4.2.1.5. Bounded Context Software Architecture Component Level Diagrams

#### 4.2.1.6. Bounded Context Software Architecture Code Level Diagrams

##### 4.2.1.6.1. Bounded Context Domain Layer Class Diagrams

##### 4.2.1.6.2. Bounded Context Database Design Diagram
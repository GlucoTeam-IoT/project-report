# Capítulo III: Requirements Specification

## 3.1. To-Be Scenario Mapping

<strong>To-Be Scenario Mapping - Paciente con diabetes Tipo 2 :</strong><br><br>
<img src="../assets/img/chapter-III/To-Be Scenario/To Be Scenario Mapping-Paciente.png" >
<br><br><strong>To-Be Scenario Mapping - Medico Especializado:</strong><br><br>
<img src="../assets/img/chapter-III/To-Be Scenario/To Be Scenario Mapping-Medico.png" >

## 3.2. User Stories

<table>
    <thead>
        <tr>
            <th>Epic ID</th>
            <th>Título</th>
            <th>Descripción</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>EP01</td>
            <td>Desarrollo del Landing page</td>
            <td>Se centra en el desarrollo del sitio web estático para la empresa. Incluye la creación de las diferentes secciones y funcionalidades necesarias para proporcionar información relevante sobre la empresa y el producto.</td>
        </tr>
        <tr>
            <td>EP02</td>
            <td>Autenticación y Registro de Usuarios</td>
            <td>Abarca las funcionalidades relacionadas con la autenticación y el registro de usuarios en la aplicación, tanto en la versión web como móvil.</td>
        </tr>
        <tr>
            <td>EP03</td>
            <td>Monitorización y Seguimiento de la Persona Cuidada</td>
            <td>Se enfoca en las funcionalidades relacionadas con la monitorización y seguimiento en tiempo real de la persona a cuidar, así como la visualización de datos históricos y la configuración de alertas.</td>
        </tr>
        <tr>
            <td>EP04</td>
            <td>Gestión de Configuraciones y Notificaciones</td>
            <td>Las funcionalidades relacionadas con la configuración de notificaciones y alertas personalizadas, así como la gestión de configuraciones de cuenta y medicamentos.</td>
        </tr>
        <tr>
            <td>EP05</td>
            <td>Desarrollo del Back-end</td>
            <td>Se enfoca en el desarrollo del back-end de la aplicación incluyendo APIs, bases de datos y lógica de negocio.</td>
        </tr>
        <tr>
            <td>EP06</td>
            <td>Conexión con Dispositivos de Monitoreo</td>
            <td>La integración con dispositivos de monitoreo de salud externos, así como la implementación de notificaciones push y análisis de datos.</td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th>Epic / Story ID</th>
            <th>Título</th>
            <th>Descripción</th>
            <th>Criterios de Aceptación</th>
            <th>Relacionado con (Epic ID)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>US001</td>
            <td>Acceso a la cuenta (Web application)</td>
            <td>Como usuario de la aplicación. Quiero acceder a mi cuenta de usuario. Para poder verificar mi identidad y ver los datos de la persona cuidada.</td>
            <td>
                <ul>
                    <li><strong>Credenciales incorrectas:</strong> Cuando ingresa credenciales inválidas, muestra mensaje "Credenciales incorrectas" y no permite acceso</li>
                    <li><strong>Credenciales correctas:</strong> Con credenciales válidas, redirige al dashboard principal y envía notificación por email</li>
                    <li>Validar formato de email y contraseña (mínimo 8 caracteres)</li>
                </ul>
            </td>
            <td>EP01</td>
        </tr>
        <tr>
            <td>US002</td>
            <td>Acceso a la cuenta (Mobile application)</td>
            <td>Como usuario de la aplicación. Quiero acceder a mi cuenta de usuario. Para poder verificar mi identidad Y ver los datos de la persona cuidada.</td>
            <td>
                <ul>
                    <li><strong>Credenciales incorrectas:</strong> Muestra mensaje y vibra el dispositivo tras ingresar datos inválidos</li>
                    <li><strong>Credenciales correctas:</strong> Redirige al dashboard móvil y envía notificación push</li>
                    <li>Opción "Recordar contraseña" funcional</li>
                    <li>Bloqueo temporal tras 5 intentos fallidos</li>
                </ul>
            </td>
            <td>EP01</td>
        </tr>
        <tr>
            <td>US003</td>
            <td>Registro de cuenta (Web Application)</td>
            <td>Como usuario de la aplicación. Quiero poder registrarme en la aplicación. Para poder comenzar con el monitoreo de la persona a cuidar.</td>
            <td>
                <ul>
                    <li><strong>Registro exitoso:</strong> Al completar todos los campos, crea cuenta y redirige con tutorial inicial</li>
                    <li><strong>Vinculación de paciente:</strong> Permite ingresar código del paciente y muestra confirmación</li>
                    <li>Envía email de verificación con enlace (expira en 24h)</li>
                    <li>Valida unicidad de email y fortaleza de contraseña</li>
                </ul>
            </td>
            <td>EP01</td>
        </tr>
        <tr>
            <td>US004</td>
            <td>Registro de cuenta (Mobile Application)</td>
            <td>Como usuario de la aplicación. Quiero poder registrarme en la aplicación. Para poder comenzar con el monitoreo de la persona a cuidar.</td>
            <td>
                <ul>
                    <li><strong>Registro exitoso:</strong> Formulario completo redirige al dashboard móvil</li>
                    <li><strong>Vinculación por QR:</strong> Escanear código QR del paciente vincula perfiles y envía notificación push</li>
                    <li>Validación de formatos en tiempo real</li>
                    <li>Confirmación visual de cambios guardados</li>
                </ul>
            </td>
            <td>EP01</td>
        </tr>
        <tr>
            <td>US005</td>
            <td>Edición de datos de la cuenta</td>
            <td>Como usuario de la aplicación. Quiero poder editar ciertos datos de mi cuenta como contraseña. Para poder corregir errores Y renovar la contraseña.</td>
            <td>
                <ul>
                    <li><strong>Cambio de contraseña:</strong> Requiere contraseña anterior y reautenticación tras actualización</li>
                    <li><strong>Actualización de email:</strong> Envía email de verificación y bloquea funciones hasta confirmación</li>
                    <li>Permite cambiar nombre, apellidos y foto de perfil</li>
                    <li>Muestra confirmación de operaciones exitosas</li>
                </ul>
            </td>
            <td>EP02</td>
        </tr>
        <tr>
            <td>US006</td>
            <td>Obtención de la información sobre la persona cuidada</td>
            <td>Como usuario de la aplicación. Quiero poder recibir información. Para poder tener constancia de la situación de la persona que estoy cuidando.</td>
            <td>
                <ul>
                    <li><strong>Sincronización de datos:</strong> Recibe y procesa datos biométricos del paciente asociándolos a la cuenta</li>
                    <li><strong>Almacenamiento histórico:</strong> Guarda datos con marca de fecha/hora y ubicación</li>
                    <li>Manejo de conexiones intermitentes (offline-first)</li>
                    <li>Encriptación de datos sensibles</li>
                </ul>
            </td>
            <td>EP02</td>
        </tr>
        <tr>
            <td>US007</td>
            <td>Visualización de la información sobre la persona cuidada (Web application)</td>
            <td>Como usuario de la aplicación. Quiero poder visualizar la información en web. Para poder tener constancia de la situación de la persona que estoy cuidando. Y poder tomar medidas al respecto.</td>
            <td>
                <ul>
                    <li><strong>Dashboard principal:</strong> Muestra gráficos de presión arterial, ritmo cardíaco y ubicación</li>
                    <li><strong>Detalles históricos:</strong> Gráficos interactivos con filtros por fecha/rango horario</li>
                    <li>Exportación de datos en formatos PDF/CSV</li>
                    <li>Vista responsiva para diferentes tamaños de pantalla</li>
                </ul>
            </td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US008</td>
            <td>Visualización de la información sobre la persona cuidada (Mobile application)</td>
            <td>Como usuario de la aplicación. Quiero poder visualizar la información en la app. Para poder tener constancia de la situación de la persona que estoy cuidando. Y poder tomar medidas al respecto.</td>
            <td>
                <ul>
                    <li><strong>Vista resumida:</strong> Muestra indicadores clave, alertas recientes y mapa con ubicación</li>
                    <li><strong>Notificaciones push:</strong> Envía alertas con opciones de acción rápida</li>
                    <li>Sincronización en tiempo real con servidor</li>
                    <li>Modo oscuro/lectura accesible</li>
                </ul>
            </td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US009</td>
            <td>Generar alarmas cuando se detecten emergencias en la persona cuidada</td>
            <td>Como usuario de la aplicación. Quiero recibir alarmas en caso de que se suceda alguna emergencia. Para poder tomar medidas al respecto.</td>
            <td>
                <ul>
                    <li><strong>Alerta por parámetros:</strong> Activa alertas visuales/sonoras cuando biométricos superan umbrales</li>
                    <li><strong>Alerta por ubicación:</strong> Detecta salida de zona segura y activa protocolo de emergencia</li>
                    <li>Notificaciones multicanal (app, email, SMS)</li>
                    <li>Registro detallado de incidentes con datos contextuales</li>
                </ul>
            </td>
            <td>EP04</td>
        </tr>
        <tr>
            <td>US010</td>
            <td>Sección About Us</td>
            <td>Como visitante de la página destino. Quiero poder visualizar la información del grupo de desarrolladores. Para poder confirmar que los desarrolladores tienen experiencia anterior en el desarrollo de software.</td>
            <td>
                <ul>
                    <li><strong>Información corporativa:</strong> Muestra misión/visión, equipo técnico y certificaciones</li>
                    <li>Datos verificables de experiencia del equipo</li>
                    <li>Enlaces a portafolios y credenciales</li>
                    <li>Diseño profesional y accesible</li>
                </ul>
            </td>
            <td>EP05</td>
        </tr>
        <tr>
            <td>US011</td>
            <td>Sección About the Product</td>
            <td>Como visitante de la página de destino. Quiero poder visualizar la información del producto. Para poder verificar las funcionalidades de la aplicación antes de probarla.</td>
            <td>
                <ul>
                    <li><strong>Descripción del sistema:</strong> Explica funcionalidades clave y requisitos técnicos</li>
                    <li>Incluye sección de preguntas frecuentes (FAQ)</li>
                    <li>Muestra capturas de pantalla reales</li>
                    <li>Provee enlaces a políticas de privacidad y términos</li>
                </ul>
            </td>
            <td>EP05</td>
        </tr>
    </tbody>
    <tbody>
        <tr>
            <td>US012</td>
            <td>Sección Contacto</td>
            <td>Como visitante de la página de destino. Quiero poder enviar un mensaje. Para poder informar de errores o problemas.</td>
            <td>
                <ul>
                    <li><strong>Formulario de contacto:</strong> Campos obligatorios para nombre, email y mensaje</li>
                    <li><strong>Validación:</strong> Verifica formato de email antes de permitir envío</li>
                    <li><strong>Confirmación:</strong> Muestra mensaje de éxito y envía copia al remitente</li>
                    <li>Protección contra spam con CAPTCHA</li>
                </ul>
            </td>
            <td>EP05</td>
        </tr>
        <tr>
            <td>US013</td>
            <td>Sección de Redes Sociales</td>
            <td>Como visitante de la página. Quiero poder acceder a las redes sociales de la empresa. Para ver novedades relacionadas a políticas o cambios en la aplicación.</td>
            <td>
                <ul>
                    <li><strong>Enlaces verificados:</strong> Iconos de redes sociales que redirigen a perfiles oficiales</li>
                    <li><strong>Plataformas soportadas:</strong> Facebook, Instagram, Twitter/X como mínimo</li>
                    <li>Abre enlaces en nueva pestaña manteniendo el sitio principal</li>
                    <li>Actualización automática si cambian URLs de redes</li>
                </ul>
            </td>
            <td>EP05</td>
        </tr>
        <tr>
            <td>US014</td>
            <td>Configuración de Notificaciones de Medicamentos (Mobile)</td>
            <td>Como usuario de la app móvil, quiero configurar recordatorios de medicamentos del adulto mayor para asegurar su administración a tiempo.</td>
            <td>
                <ul>
                    <li><strong>Crear recordatorio:</strong> Permite establecer nombre, dosis, frecuencia y horarios</li>
                    <li><strong>Modificar medicamentos:</strong> Editar cualquier parámetro existente</li>
                    <li>Notificaciones push y sonoras personalizables</li>
                    <li>Sincronización entre dispositivos para el mismo usuario</li>
                </ul>
            </td>
            <td>EP02</td>
        </tr>
        <tr>
            <td>US015</td>
            <td>Configuración de notificaciones (Mobile)</td>
            <td>Como usuario de la app móvil, quiero configurar notificaciones de emergencia para adaptarlas a mis preferencias.</td>
            <td>
                <ul>
                    <li><strong>Personalización:</strong> Activar/desactivar por tipo de emergencia</li>
                    <li><strong>Preferencias:</strong> Elegir canales (app, SMS, email) para cada alerta</li>
                    <li>Configuración de horarios para notificaciones no urgentes</li>
                    <li>Guardado automático de preferencias</li>
                </ul>
            </td>
            <td>EP02</td>
        </tr>
        <tr>
            <td>US016</td>
            <td>Acceso a registros históricos (Mobile)</td>
            <td>Como usuario de la app móvil, quiero acceder a registros históricos de salud para seguimiento a largo plazo.</td>
            <td>
                <ul>
                    <li><strong>Filtrado:</strong> Por fecha, tipo de métrica o eventos</li>
                    <li><strong>Visualización:</strong> Gráficos interactivos y exportables</li>
                    <li>Búsqueda por rangos de fechas</li>
                    <li>Marcado de eventos significativos</li>
                </ul>
            </td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US017</td>
            <td>Registro de múltiples cuentas de cuidadores (Mobile)</td>
            <td>Como usuario de la app móvil, quiero registrar y alternar entre cuentas de cuidadores para supervisar diferentes adultos mayores.</td>
            <td>
                <ul>
                    <li><strong>Agregar cuentas:</strong> Hasta 5 perfiles de adultos mayores</li>
                    <li><strong>Cambio rápido:</strong> Selector accesible desde menú principal</li>
                    <li>Indicador visual claro del perfil activo</li>
                    <li>Configuración independiente por cada perfil</li>
                </ul>
            </td>
            <td>EP01</td>
        </tr>
        <tr>
            <td>US018</td>
            <td>Configurar alertas personalizadas (Mobile)</td>
            <td>Como usuario de la app móvil, quiero configurar alertas para recibir notificaciones específicas sobre salud y seguridad.</td>
            <td>
                <ul>
                    <li><strong>Umbrales personalizables:</strong> Para presión arterial, ritmo cardíaco, etc.</li>
                    <li><strong>Contactos de emergencia:</strong> Asignar diferentes contactos para distintos tipos de alertas</li>
                    <li>Prueba de notificaciones antes de guardar</li>
                    <li>Modo silencioso programable</li>
                </ul>
            </td>
            <td>EP04</td>
        </tr>
        <tr>
            <td>US019</td>
            <td>Seguimiento de ubicación (Mobile)</td>
            <td>Como usuario de la app móvil, quiero realizar seguimiento de ubicación en tiempo real para garantizar seguridad.</td>
            <td>
                <ul>
                    <li><strong>Mapa interactivo:</strong> Muestra ubicación actual con precisión de 10m</li>
                    <li><strong>Zonas seguras:</strong> Configuración de áreas permitidas con notificación de salida</li>
                    <li>Historial de rutinas diarias</li>
                    <li>Modo bajo consumo de batería</li>
                </ul>
            </td>
            <td>EP04</td>
        </tr>
        <tr>
            <td>US020</td>
            <td>Agregar lista de medicamentos con recordatorio (Mobile)</td>
            <td>Como usuario de la app, quiero agregar y gestionar lista de medicamentos para administrarlos correctamente.</td>
            <td>
                <ul>
                    <li><strong>Registro completo:</strong> Nombre, dosis, frecuencia, horarios, notas</li>
                    <li><strong>Recordatorios inteligentes:</strong> Ajustan según tomas omitidas</li>
                    <li>Base de datos de medicamentos comunes</li>
                    <li>Registro de administración con confirmación</li>
                </ul>
            </td>
            <td>EP02</td>
        </tr>
    </tbody>
    <tbody>
        <tr>
            <td>US021</td>
            <td>Historial de ubicaciones (Mobile)</td>
            <td>Como usuario de la app móvil, quiero acceder al historial de ubicaciones del adulto mayor para realizar seguimiento de sus movimientos y patrones de comportamiento.</td>
            <td>
                <ul>
                    <li><strong>Visualización temporal:</strong> Mapa interactivo con línea de tiempo de ubicaciones</li>
                    <li><strong>Filtrado:</strong> Por fechas específicas o rangos horarios</li>
                    <li>Exportación de rutas en formato KML/GPX</li>
                    <li>Marcado de ubicaciones frecuentes como "sitios importantes"</li>
                </ul>
            </td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US022</td>
            <td>Registrar nuevo usuario (Backend)</td>
            <td>Como desarrollador, quiero agregar un nuevo usuario al sistema mediante POST "API/V1/user" con nombre, email y contraseña para permitir login.</td>
            <td>
                <ul>
                    <li><strong>Registro exitoso:</strong> Devuelve status 201 y token JWT al completar campos obligatorios</li>
                    <li><strong>Validaciones:</strong> Email único, contraseña con hash seguro (bcrypt)</li>
                    <li>Envió de email de confirmación con enlace de verificación</li>
                    <li>Protección contra ataques de fuerza bruta</li>
                </ul>
            </td>
            <td>EP06</td>
        </tr>
        <tr>
            <td>US023</td>
            <td>Agregar personas enfermas (Backend)</td>
            <td>Como desarrollador, quiero agregar una persona al cuidado de un usuario mediante POST "API/V1/user/patient" con datos como nombre, edad y enfermedad.</td>
            <td>
                <ul>
                    <li><strong>Creación paciente:</strong> Campos obligatorios validados (nombre, edad, condición principal)</li>
                    <li><strong>Relación:</strong> Vincula automáticamente al usuario que realiza la solicitud</li>
                    <li>Encriptación de datos sensibles en reposo</li>
                    <li>Límite de 5 pacientes por cuenta básica</li>
                </ul>
            </td>
            <td>EP06</td>
        </tr>
        <tr>
            <td>US024</td>
            <td>Iniciar sesión (Backend)</td>
            <td>Como desarrollador, quiero implementar un endpoint POST "/API/V1/usuarios/login" para acceso seguro a la plataforma.</td>
            <td>
                <ul>
                    <li><strong>Login exitoso:</strong> Devuelve token JWT válido por 24h con credenciales correctas</li>
                    <li><strong>Seguridad:</strong> Límite de 5 intentos fallidos antes de bloqueo temporal</li>
                    <li>Registro de actividad de login</li>
                    <li>Detección de dispositivos nuevos con verificación en 2 pasos</li>
                </ul>
            </td>
            <td>EP06</td>
        </tr>
        <tr>
            <td>US025</td>
            <td>Recuperar contraseña (Backend)</td>
            <td>Como desarrollador, quiero diseñar un endpoint POST "/API/V1/usuarios/recuperarcontraseña" para recuperación segura de contraseñas.</td>
            <td>
                <ul>
                    <li><strong>Flujo seguro:</strong> Genera token temporal de un solo uso (expira en 1h)</li>
                    <li><strong>Notificación:</strong> Envía email con enlace seguro para restablecimiento</li>
                    <li>Invalidación de tokens JWT previos al cambio</li>
                    <li>Protección contra enumeración de emails</li>
                </ul>
            </td>
            <td>EP06</td>
        </tr>
        <tr>
            <td>US026</td>
            <td>Actualizar Información (Backend)</td>
            <td>Como desarrollador, quiero crear un endpoint PUT "/API/V1/usuarios/informacion" para actualización de perfiles.</td>
            <td>
                <ul>
                    <li><strong>Actualización parcial:</strong> Permite modificar campos individuales</li>
                    <li><strong>Validaciones:</strong> Formato de email, números telefónicos, etc.</li>
                    <li>Registro de cambios en historial de modificaciones</li>
                    <li>Notificación por email cuando cambian datos sensibles</li>
                </ul>
            </td>
            <td>EP06</td>
        </tr>
        <tr>
            <td>US027</td>
            <td>Eliminar Cuenta (Backend)</td>
            <td>Como desarrollador, quiero implementar un endpoint DELETE "/API/V1/usuarios/cuenta" para eliminación segura de cuentas.</td>
            <td>
                <ul>
                    <li><strong>Eliminación lógica:</strong> Marca registro como inactivo en lugar de borrado físico</li>
                    <li><strong>Verificación:</strong> Requiere confirmación por email o 2FA</li>
                    <li>Periodo de gracia de 30 días para recuperación</li>
                    <li>Eliminación anonimizada de datos personales tras 60 días</li>
                </ul>
            </td>
            <td>EP06</td>
        </tr>
        <tr>
            <td>US028</td>
            <td>Endpoint Soporte (Backend)</td>
            <td>Como desarrollador, quiero diseñar un endpoint POST "/API/V1/usuarios/solicitarayuda" para solicitudes de ayuda.</td>
            <td>
                <ul>
                    <li><strong>Clasificación:</strong> Categorización automática por tipo de problema</li>
                    <li><strong>Priorización:</strong> Urgencia determinada por NLP en descripción</li>
                    <li>Notificación en tiempo real al equipo de soporte</li>
                    <li>Sistema de tickets con seguimiento</li>
                </ul>
            </td>
            <td>EP06</td>
        </tr>
        <tr>
            <td>US029</td>
            <td>Proceso de ventas (Backend)</td>
            <td>Como desarrollador, quiero implementar un endpoint para procesar ventas actualizando inventario y registrando transacciones.</td>
            <td>
                <ul>
                    <li><strong>Transacción atómica:</strong> Actualiza inventario solo si el pago es exitoso</li>
                    <li><strong>Integraciones:</strong> Conexión con pasarelas de pago (Stripe, PayPal)</li>
                    <li>Generación de facturas en PDF</li>
                    <li>Notificaciones por email con detalles de compra</li>
                </ul>
            </td>
            <td>EP07</td>
        </tr>
        <tr>
            <td>US030</td>
            <td>Consulta de ubicación del paciente</td>
            <td>Como usuario, quiero consultar la ubicación actual de un paciente para saber dónde se encuentra en tiempo real.</td>
            <td>
                <ul>
                    <li><strong>Precisión:</strong> Muestra ubicación con margen de error <50 metros</li>
                    <li><strong>Actualización:</strong> Refresco automático cada 2 minutos (configurable)</li>
                    <li>Modo de bajo consumo de batería</li>
                    <li>Compartir ubicación temporal con terceros</li>
                </ul>
            </td>
            <td>EP03</td>
        </tr>
    </tbody>
                        <tbody>
        <tr>
            <td>US031</td>
            <td>Consulta de ubicación del paciente (Frontend)</td>
            <td>Como desarrollador, quiero integrar la API de Google Maps para visualizar la ubicación actual del paciente, permitiendo a los usuarios realizar seguimiento en tiempo real.</td>
            <td>
                <ul>
                    <li><strong>Visualización exitosa:</strong> Al recibir el ID del paciente, muestra marcador en mapa con ubicación exacta</li>
                    <li><strong>Datos contextuales:</strong> Muestra dirección exacta, historial de rutas y puntos de interés cercanos</li>
                    <li>Manejo de errores cuando el servicio de mapas no está disponible</li>
                    <li>Actualización automática cada 2 minutos (configurable)</li>
                </ul>
            </td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US032</td>
            <td>Estadísticas sobre reportes del paciente (Frontend)</td>
            <td>Como desarrollador, quiero implementar visualizaciones estadísticas que permitan a los usuarios analizar el estado de salud del paciente mediante datos históricos.</td>
            <td>
                <ul>
                    <li><strong>Gráficos interactivos:</strong> Muestra tendencias de salud con filtros por fecha/rango temporal</li>
                    <li><strong>Indicadores clave:</strong> Frecuencia cardíaca, presión arterial y otros parámetros vitales</li>
                    <li>Exportación de reportes en PDF/CSV</li>
                    <li>Notificaciones cuando se detectan anomalías estadísticas</li>
                </ul>
            </td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US033</td>
            <td>Consulta del último reporte del paciente (Frontend)</td>
            <td>Como desarrollador, quiero desarrollar una función que muestre el reporte más reciente del paciente, proporcionando información actualizada sobre su condición.</td>
            <td>
                <ul>
                    <li><strong>Datos completos:</strong> Muestra todos los parámetros médicos registrados en la última medición</li>
                    <li><strong>Comparativa:</strong> Contrasta con valores anteriores y rangos saludables</li>
                    <li>Acceso rápido desde el dashboard principal</li>
                    <li>Opción para compartir reporte con especialistas</li>
                </ul>
            </td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US034</td>
            <td>Captura de Ubicación</td>
            <td>Como usuario del sistema, necesito que el dispositivo registre y transmita mi posición para facilitar la localización en emergencias.</td>
            <td>
                <ul>
                    <li><strong>Precisión:</strong> Geolocalización con exactitud ≤15 metros en exteriores</li>
                    <li><strong>Frecuencia:</strong> Actualización cada 5 minutos (1 minuto en modo emergencia)</li>
                    <li>Funcionamiento en modo bajo consumo</li>
                    <li>Detección automática de caídas o inmovilidad prolongada</li>
                </ul>
            </td>
            <td>EP04</td>
        </tr>
        <tr>
            <td>US035</td>
            <td>Envío de ubicación mediante Edge Gateway</td>
            <td>Como desarrollador, necesito que el Edge Gateway capture y procese datos de ubicación del dispositivo para su transmisión al backend.</td>
            <td>
                <ul>
                    <li><strong>Adquisición:</strong> Recibe coordenadas GPS/Wi-Fi del dispositivo</li>
                    <li><strong>Optimización:</strong> Reduce frecuencia en zonas conocidas para ahorrar energía</li>
                    <li>Cifrado de datos en tránsito y reposo</li>
                    <li>Priorización de transmisión en modo emergencia</li>
                </ul>
            </td>
            <td>EP07</td>
        </tr>
        <tr>
        <td>TS01</td>
        <td>Configuración del entorno de desarrollo web</td>
        <td>Como desarrollador, necesito configurar y documentar un entorno de desarrollo común para facilitar la colaboración y consistencia del landing page.</td>
        <td>
            <ul>
                <li>Entorno reproducible para todos los miembros</li>
                <li>Instalación de herramientas base: Node.js, React, Git</li>
                <li>Documentación paso a paso incluida en el repositorio</li>
            </ul>
        </td>
        <td>EP01</td>
    </tr>
    <tr>
        <td>TS02</td>
        <td>Implementación de validaciones en el formulario de registro</td>
        <td>Como desarrollador, necesito aplicar validaciones del lado cliente para evitar datos inválidos durante el registro de usuarios.</td>
        <td>
            <ul>
                <li>Validación de campos: email, contraseña segura, campos obligatorios</li>
                <li>Mensajes de error claros y visibles</li>
                <li>No debe enviarse el formulario si hay errores</li>
            </ul>
        </td>
        <td>EP02</td>
    </tr>
    <tr>
        <td>TS03</td>
        <td>Diseño del modelo de base de datos para usuarios</td>
        <td>Como desarrollador, necesito diseñar el modelo de datos para gestionar información de usuarios y sus roles de acceso.</td>
        <td>
            <ul>
                <li>Modelo de entidades relacional implementado</li>
                <li>Soporte para roles como "cuidador" y "paciente"</li>
                <li>Migraciones listas para producción</li>
            </ul>
        </td>
        <td>EP02</td>
    </tr>
    <tr>
        <td>TS04</td>
        <td>Integración de sockets para seguimiento en tiempo real</td>
        <td>Como desarrollador, necesito usar sockets para transmitir datos de salud del paciente en tiempo real al front-end.</td>
        <td>
            <ul>
                <li>Recepción continua de datos simulados desde el backend</li>
                <li>Manejo de eventos de conexión y desconexión</li>
                <li>Visualización dinámica en el dashboard del cuidador</li>
            </ul>
        </td>
        <td>EP03</td>
    </tr>
    <tr>
        <td>TS05</td>
        <td>Configuración de alertas por umbrales de salud</td>
        <td>Implementar la lógica backend para enviar alertas cuando un dato de sensor exceda un umbral configurado.</td>
        <td>
            <ul>
                <li>Se generan alertas automáticamente.</li>
                <li>Las alertas son registradas en la base de datos.</li>
            </ul>
        </td>
        <td>EP04</td>
    </tr>
    <tr>
        <td>TS06</td>
        <td>Creación de API REST para notificaciones</td>
        <td>Diseñar e implementar una API REST para gestionar el envío de notificaciones desde el backend.</td>
        <td>
            <ul>
                <li>API con endpoints funcionales para crear, consultar y eliminar notificaciones.</li>
                <li>Pruebas unitarias incluidas.</li>
            </ul>
        </td>
        <td>EP04</td>
    </tr>
    <tr>
        <td>TS07</td>
        <td>Seguridad en la autenticación y sesiones</td>
        <td>Implementar el uso de tokens JWT y encriptación de contraseñas con bcrypt.</td>
        <td>
            <ul>
                <li>Contraseñas encriptadas en la base de datos.</li>
                <li>JWT generados y verificados correctamente.</li>
            </ul>
        </td>
        <td>EP02</td>
    </tr>
    <tr>
        <td>TS08</td>
        <td>Documentación técnica del backend</td>
        <td>Crear documentación de los servicios y rutas del backend con Swagger u otra herramienta.</td>
        <td>
            <ul>
                <li>Todos los endpoints documentados.</li>
                <li>Accesible para desarrolladores desde entorno local.</li>
            </ul>
        </td>
        <td>EP05</td>
    </tr>
    <tr>
        <td>TS09</td>
        <td>Integración de dispositivo BLE con aplicación móvil</td>
        <td>Implementar el módulo que permita conectar y leer datos desde dispositivos BLE (Bluetooth Low Energy).</td>
        <td>
            <ul>
                <li>La app detecta dispositivos BLE.</li>
                <li>Se reciben y visualizan datos correctamente.</li>
            </ul>
        </td>
        <td>EP06</td>
    </tr>
    <tr>
        <td>TS10</td>
        <td>Procesamiento de datos de sensores con filtrado</td>
        <td>Implementar un filtro (por ejemplo, media móvil) para suavizar los datos recibidos de los sensores antes de su almacenamiento.</td>
        <td>
            <ul>
                <li>Los datos se almacenan suavizados.</li>
                <li>Se puede comparar entre datos crudos y filtrados durante pruebas.</li>
            </ul>
        </td>
        <td>EP06</td>
    </tr>
    <tr>
    <td>TS11</td>
    <td>Interfaz de configuración de alertas</td>
    <td>Crear una vista en la web donde el usuario pueda configurar los umbrales de salud y preferencias de notificación.</td>
    <td>
        <ul>
            <li>Se puede seleccionar valores límites por parámetro.</li>
            <li>Se guarda la configuración correctamente.</li>
            <li>La vista se adapta a escritorio y tablet.</li>
        </ul>
    </td>
    <td>EP04</td>
    </tr>
    <tr>
        <td>TS12</td>
        <td>Visualización de alertas en panel web</td>
        <td>Desarrollar una sección que muestre las alertas activas e históricas con sus detalles (fecha, tipo, prioridad).</td>
        <td>
            <ul>
                <li>Se listan al menos 10 alertas por página.</li>
                <li>Se permite ordenar por fecha o severidad.</li>
                <li>Se muestra estado: activa o resuelta.</li>
            </ul>
        </td>
        <td>EP04</td>
    </tr>
    <tr>
        <td>TS13</td>
        <td>Historial gráfico de datos del paciente</td>
        <td>Diseñar un dashboard que permita visualizar gráficamente los datos recopilados por los sensores.</td>
        <td>
            <ul>
                <li>Incluye gráficos interactivos (línea, barras).</li>
                <li>Permite filtrar por fechas y tipo de dato.</li>
                <li>Datos se actualizan automáticamente al ingresar.</li>
            </ul>
        </td>
        <td>EP03</td>
    </tr>
    <tr>
        <td>TS14</td>
        <td>Página de inicio personalizada para usuario logueado</td>
        <td>Crear una landing page interna que muestre resumen del estado del paciente, últimas alertas y accesos rápidos.</td>
        <td>
            <ul>
                <li>Datos actualizados en tiempo real.</li>
                <li>Se adapta al rol del usuario (cuidador/familiar).</li>
                <li>Accesos rápidos a historial y configuración.</li>
            </ul>
        </td>
        <td>EP01</td>
    </tr>
    <tr>
        <td>TS15</td>
        <td>Gestión de sesiones y cierre de sesión seguro</td>
        <td>Implementar botón de logout con invalidación de sesión activa y redirección segura.</td>
        <td>
            <ul>
                <li>La sesión se invalida correctamente al cerrar sesión.</li>
                <li>Se redirige al usuario a la página de inicio.</li>
                <li>No se puede regresar con el botón "atrás".</li>
            </ul>
        </td>
        <td>EP02</td>
    </tr>
    </tbody>
</table>
</table>

## 3.3. Impact Mapping

<strong>Impact Mapping - Paciente con diabetes Tipo 2 :</strong><br><br>
<img src="../assets/img/chapter-III/Impact Mapping/Impact Mapping-Paciente.png" >
<br><br><strong>Impact Mapping - Medico Especializado:</strong><br><br>
<img src="../assets/img/chapter-III/Impact Mapping/Impact Mapping-Medico.png" >

## 3.4. Product Backlog

En esta sección se presenta el backlog del producto.

Enlace del Trello Product Backlog: https://trello.com/b/qBZuOZ98/upc-pre-202510-1asi0572-2952-glucoteam-trello#

<table>
    <thead>
        <tr>
            <th>#</th>
            <th>Epic/User Story</th>
            <th>Descripción</th>
            <th>Criterios de Aceptación</th>
            <th>Prioridad</th>
            <th>Story Points</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>US001</td>
            <td>Como usuario de la aplicación. Quiero acceder a mi cuenta de usuario. Para poder verificar mi identidad y ver los datos de la persona cuidada.</td>
            <td>
                <ul>
                    <li>Muestra mensaje "Credenciales incorrectas" con datos inválidos</li>
                    <li>Redirige al dashboard principal con credenciales válidas</li>
                    <li>Envía notificación por email al acceder</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>3</td>
        </tr>
        <tr>
            <td>2</td>
            <td>US002</td>
            <td>Como usuario de la aplicación. Quiero acceder a mi cuenta de usuario. Para poder verificar mi identidad Y ver los datos de la persona cuidada.</td>
            <td>
                <ul>
                    <li>Vibra el dispositivo con credenciales incorrectas</li>
                    <li>Redirige al dashboard móvil con credenciales válidas</li>
                    <li>Opción "Recordar contraseña" funcional</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>3</td>
        </tr>
        <tr>
            <td>3</td>
            <td>US003</td>
            <td>Como usuario de la aplicación. Quiero poder registrarme en la aplicación. Para poder comenzar con el monitoreo de la persona a cuidar.</td>
            <td>
                <ul>
                    <li>Crea cuenta al completar todos los campos</li>
                    <li>Envía email de verificación (expira en 24h)</li>
                    <li>Muestra tutorial inicial post-registro</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>4</td>
            <td>US004</td>
            <td>Como usuario de la aplicación. Quiero poder registrarme en la aplicación. Para poder comenzar con el monitoreo de la persona a cuidar.</td>
            <td>
                <ul>
                    <li>Escanear QR vincula perfiles automáticamente</li>
                    <li>Envía notificación push de confirmación</li>
                    <li>Validación de formatos en tiempo real</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>5</td>
            <td>US005</td>
            <td>Como usuario de la aplicación. Quiero poder editar ciertos datos de mi cuenta como contraseña. Para poder corregir errores Y renovar la contraseña.</td>
            <td>
                <ul>
                    <li>Requiere contraseña anterior para cambios</li>
                    <li>Envía email de verificación al cambiar email</li>
                    <li>Permite actualizar foto de perfil</li>
                </ul>
            </td>
            <td>Media</td>
            <td>3</td>
        </tr>
        <tr>
            <td>6</td>
            <td>US006</td>
            <td>Como usuario de la aplicación. Quiero poder recibir información. Para poder tener constancia de la situación de la persona que estoy cuidando.</td>
            <td>
                <ul>
                    <li>Sincroniza datos cada 5 minutos</li>
                    <li>Almacena histórico con marca de tiempo</li>
                    <li>Funciona offline y sincroniza después</li>
                </ul>
            </td>
            <td>Crítica</td>
            <td>8</td>
        </tr>
        <tr>
            <td>7</td>
            <td>US007</td>
            <td>Como usuario de la aplicación. Quiero poder visualizar la información en web. Para poder tener constancia de la situación de la persona que estoy cuidando. Y poder tomar medidas al respecto.</td>
            <td>
                <ul>
                    <li>Muestra gráficos de parámetros vitales</li>
                    <li>Permite filtrar por fecha/rango horario</li>
                    <li>Exporta datos en PDF/CSV</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>8</td>
            <td>US008</td>
            <td>Como usuario de la aplicación. Quiero poder visualizar la información en la app. Para poder tener constancia de la situación de la persona que estoy cuidando. Y poder tomar medidas al respecto.</td>
            <td>
                <ul>
                    <li>Muestra indicadores clave y alertas</li>
                    <li>Incluye mapa con ubicación actual</li>
                    <li>Soporta modo oscuro</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>9</td>
            <td>US009</td>
            <td>Como usuario de la aplicación. Quiero recibir alarmas en caso de que se suceda alguna emergencia. Para poder tomar medidas al respecto.</td>
            <td>
                <ul>
                    <li>Notifica cuando parámetros superan umbrales</li>
                    <li>Alerta por salida de zona segura</li>
                    <li>Envía notificaciones multicanal</li>
                </ul>
            </td>
            <td>Crítica</td>
            <td>8</td>
        </tr>
        <tr>
            <td>10</td>
            <td>US010</td>
            <td>Como visitante de la página destino. Quiero poder visualizar la información del grupo de desarrolladores. Para poder confirmar que los desarrolladores tienen experiencia anterior en el desarrollo de software.</td>
            <td>
                <ul>
                    <li>Muestra misión/visión y equipo técnico</li>
                    <li>Incluye certificaciones relevantes</li>
                    <li>Diseño profesional y accesible</li>
                </ul>
            </td>
            <td>Baja</td>
            <td>2</td>
        </tr>
        <tr>
            <td>11</td>
            <td>US011</td>
            <td>Como visitante de la página de destino. Quiero poder visualizar la información del producto. Para poder verificar las funcionalidades de la aplicación antes de probarla.</td>
            <td>
                <ul>
                    <li>Explica funcionalidades clave</li>
                    <li>Incluye sección de preguntas frecuentes</li>
                    <li>Muestra capturas de pantalla reales</li>
                </ul>
            </td>
            <td>Baja</td>
            <td>2</td>
        </tr>
        <tr>
            <td>12</td>
            <td>US012</td>
            <td>Como visitante de la página de destino. Quiero poder enviar un mensaje. Para poder informar de errores o problemas.</td>
            <td>
                <ul>
                    <li>Campos obligatorios para nombre, email y mensaje</li>
                    <li>Verifica formato de email</li>
                    <li>Muestra confirmación de envío</li>
                </ul>
            </td>
            <td>Baja</td>
            <td>2</td>
        </tr>
        <tr>
            <td>13</td>
            <td>US013</td>
            <td>Como visitante de la página. Quiero poder acceder a las redes sociales de la empresa. Para ver novedades relacionadas a políticas o cambios en la aplicación.</td>
            <td>
                <ul>
                    <li>Iconos con enlaces verificados</li>
                    <li>Soporta Facebook, Instagram, Twitter/X</li>
                    <li>Abre enlaces en nueva pestaña</li>
                </ul>
            </td>
            <td>Baja</td>
            <td>1</td>
        </tr>
        <tr>
            <td>14</td>
            <td>US014</td>
            <td>Como usuario de la app móvil, quiero configurar recordatorios de medicamentos del adulto mayor para asegurar su administración a tiempo.</td>
            <td>
                <ul>
                    <li>Permite establecer horarios específicos</li>
                    <li>Notificaciones push configurables</li>
                    <li>Sincronización entre dispositivos</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>15</td>
            <td>US015</td>
            <td>Como usuario de la app móvil, quiero configurar notificaciones de emergencia para adaptarlas a mis preferencias.</td>
            <td>
                <ul>
                    <li>Activar/desactivar por tipo de emergencia</li>
                    <li>Elegir canales (app/SMS/email)</li>
                    <li>Guardado automático de preferencias</li>
                </ul>
            </td>
            <td>Media</td>
            <td>3</td>
        </tr>
        <tr>
            <td>16</td>
            <td>US016</td>
            <td>Como usuario de la app móvil, quiero acceder a registros históricos de salud para seguimiento a largo plazo.</td>
            <td>
                <ul>
                    <li>Filtrado por fecha y tipo de métrica</li>
                    <li>Gráficos interactivos y exportables</li>
                    <li>Marcado de eventos significativos</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>17</td>
            <td>US017</td>
            <td>Como usuario de la app móvil, quiero registrar y alternar entre cuentas de cuidadores para supervisar diferentes adultos mayores.</td>
            <td>
                <ul>
                    <li>Hasta 5 perfiles de adultos mayores</li>
                    <li>Selector accesible desde menú principal</li>
                    <li>Configuración independiente por perfil</li>
                </ul>
            </td>
            <td>Media</td>
            <td>5</td>
        </tr>
        <tr>
            <td>18</td>
            <td>US018</td>
            <td>Como usuario de la app móvil, quiero configurar alertas para recibir notificaciones específicas sobre salud y seguridad.</td>
            <td>
                <ul>
                    <li>Umbrales personalizables por parámetro</li>
                    <li>Asignación de contactos de emergencia</li>
                    <li>Prueba de notificaciones</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>19</td>
            <td>US019</td>
            <td>Como usuario de la app móvil, quiero realizar seguimiento de ubicación en tiempo real para garantizar seguridad.</td>
            <td>
                <ul>
                    <li>Precisión de 10m en exteriores</li>
                    <li>Configuración de zonas seguras</li>
                    <li>Modo bajo consumo</li>
                </ul>
            </td>
            <td>Crítica</td>
            <td>8</td>
        </tr>
        <tr>
            <td>20</td>
            <td>US020</td>
            <td>Como usuario de la app, quiero agregar y gestionar lista de medicamentos para administrarlos correctamente.</td>
            <td>
                <ul>
                    <li>Registro completo de dosis y horarios</li>
                    <li>Base de datos de medicamentos comunes</li>
                    <li>Confirmación de administración</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>21</td>
            <td>US021</td>
            <td>Como usuario de la app móvil, quiero acceder al historial de ubicaciones del adulto mayor para realizar seguimiento de sus movimientos y patrones de comportamiento.</td>
            <td>
                <ul>
                    <li>Mapa con línea de tiempo</li>
                    <li>Exportación de rutas en KML/GPX</li>
                    <li>Marcado de lugares frecuentes</li>
                </ul>
            </td>
            <td>Media</td>
            <td>5</td>
        </tr>
        <tr>
            <td>22</td>
            <td>US022</td>
            <td>Como desarrollador, quiero agregar un nuevo usuario al sistema mediante POST "API/V1/user" con nombre, email y contraseña para permitir login.</td>
            <td>
                <ul>
                    <li>Valida email único</li>
                    <li>Encriptación de contraseñas</li>
                    <li>Genera token JWT</li>
                </ul>
            </td>
            <td>Crítica</td>
            <td>5</td>
        </tr>
        <tr>
            <td>23</td>
            <td>US023</td>
            <td>Como desarrollador, quiero agregar una persona al cuidado de un usuario mediante POST "API/V1/user/patient" con datos como nombre, edad y enfermedad.</td>
            <td>
                <ul>
                    <li>Validación de datos obligatorios</li>
                    <li>Vinculación automática a cuidador</li>
                    <li>Límite de 5 pacientes por cuenta</li>
                </ul>
            </td>
            <td>Crítica</td>
            <td>5</td>
        </tr>
        <tr>
            <td>24</td>
            <td>US024</td>
            <td>Como desarrollador, quiero implementar un endpoint POST "/API/V1/usuarios/login" para acceso seguro a la plataforma.</td>
            <td>
                <ul>
                    <li>Genera token válido por 24h</li>
                    <li>Límite de 5 intentos fallidos</li>
                    <li>Detección de nuevos dispositivos</li>
                </ul>
            </td>
            <td>Crítica</td>
            <td>5</td>
        </tr>
        <tr>
            <td>25</td>
            <td>US025</td>
            <td>Como desarrollador, quiero diseñar un endpoint POST "/API/V1/usuarios/recuperarcontraseña" para recuperación segura de contraseñas.</td>
            <td>
                <ul>
                    <li>Token temporal de un solo uso</li>
                    <li>Email con enlace seguro</li>
                    <li>Invalidación de tokens previos</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>3</td>
        </tr>
        <tr>
            <td>26</td>
            <td>US026</td>
            <td>Como desarrollador, quiero crear un endpoint PUT "/API/V1/usuarios/informacion" para actualización de perfiles.</td>
            <td>
                <ul>
                    <li>Actualización parcial de campos</li>
                    <li>Validación de formatos</li>
                    <li>Notificación por email</li>
                </ul>
            </td>
            <td>Media</td>
            <td>3</td>
        </tr>
        <tr>
            <td>27</td>
            <td>US027</td>
            <td>Como desarrollador, quiero implementar un endpoint DELETE "/API/V1/usuarios/cuenta" para eliminación segura de cuentas.</td>
            <td>
                <ul>
                    <li>Eliminación lógica (no física)</li>
                    <li>Confirmación por 2FA</li>
                    <li>Periodo de gracia de 30 días</li>
                </ul>
            </td>
            <td>Media</td>
            <td>3</td>
        </tr>
        <tr>
            <td>28</td>
            <td>US028</td>
            <td>Como desarrollador, quiero diseñar un endpoint POST "/API/V1/usuarios/solicitarayuda" para solicitudes de ayuda.</td>
            <td>
                <ul>
                    <li>Clasificación automática</li>
                    <li>Notificación en tiempo real</li>
                    <li>Sistema de tickets</li>
                </ul>
            </td>
            <td>Media</td>
            <td>3</td>
        </tr>
        <tr>
            <td>29</td>
            <td>US029</td>
            <td>Como desarrollador, quiero implementar un endpoint para procesar ventas actualizando inventario y registrando transacciones.</td>
            <td>
                <ul>
                    <li>Transacción atómica</li>
                    <li>Integración con pasarelas de pago</li>
                    <li>Generación de facturas</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>30</td>
            <td>US030</td>
            <td>Como usuario, quiero consultar la ubicación actual de un paciente para saber dónde se encuentra en tiempo real.</td>
            <td>
                <ul>
                    <li>Precisión de 50 metros</li>
                    <li>Actualización cada 2 minutos</li>
                    <li>Compartición temporal</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>31</td>
            <td>US031</td>
            <td>Como desarrollador, quiero integrar la API de Google Maps para visualizar la ubicación actual del paciente, permitiendo a los usuarios realizar seguimiento en tiempo real.</td>
            <td>
                <ul>
                    <li>Marcador con ubicación exacta</li>
                    <li>Datos contextuales</li>
                    <li>Actualización automática</li>
                </ul>
            </td>
            <td>Media</td>
            <td>5</td>
        </tr>
        <tr>
            <td>32</td>
            <td>US032</td>
            <td>Como desarrollador, quiero implementar visualizaciones estadísticas que permitan a los usuarios analizar el estado de salud del paciente mediante datos históricos.</td>
            <td>
                <ul>
                    <li>Gráficos interactivos</li>
                    <li>Indicadores clave</li>
                    <li>Detección de anomalías</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        <tr>
            <td>33</td>
            <td>US033</td>
            <td>Como desarrollador, quiero desarrollar una función que muestre el reporte más reciente del paciente, proporcionando información actualizada sobre su condición.</td>
            <td>
                <ul>
                    <li>Datos completos de última medición</li>
                    <li>Comparación con valores anteriores</li>
                    <li>Opción de compartir</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>3</td>
        </tr>
        <tr>
            <td>34</td>
            <td>US034</td>
            <td>Como usuario del sistema, necesito que el dispositivo registre y transmita mi posición para facilitar la localización en emergencias.</td>
            <td>
                <ul>
                    <li>Precisión de 15 metros</li>
                    <li>Frecuencia ajustable</li>
                    <li>Detección de caídas</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>3</td>
        </tr>
        <tr>
            <td>35</td>
            <td>US035</td>
            <td>Como desarrollador, necesito que el Edge Gateway capture y procese datos de ubicación del dispositivo para su transmisión al backend.</td>
            <td>
                <ul>
                    <li>Optimización de frecuencia</li>
                    <li>Cifrado de datos</li>
                    <li>Priorización en emergencias</li>
                </ul>
            </td>
            <td>Alta</td>
            <td>5</td>
        </tr>
        
    </tbody>
</table>

Sistema turnomatico
Descripcion 
El sistema de turnomático permite asignar turnos de forma automatizada mediante la emisión de tickets numerados,
ya sea a través de una pantalla táctil, aplicación web o dispensador físico.
Organiza la atención por orden de llegada o según prioridades definidas, mejorando la eficiencia del servicio y reduciendo los tiempos de espera. 
El sistema puede incluir pantallas informativas, alertas visuales y sonoras, y estadísticas de atención para mejorar la experiencia del usuario y optimizar los recursos humanos del establecimiento.
1.- Diagrama de caso de uso
(ss)

Análisis del diagrama de casos de uso:

Actores:
Cliente: Usuario principal que interactúa con el sistema para gestionar sus turnos.

Administrador: Encargado de definir y mantener la disponibilidad de turnos.
Sistema de notificación: Sistema externo que envía alertas sobre el estado del turno al cliente.

Casos de uso principales:
Tomar Turno: El cliente solicita un nuevo turno.
Consultar Estado de Turnos: El cliente verifica si hay turnos disponibles.
Includ: Administra disponibilidad de turnos.
Ver Turno: El cliente revisa los detalles del turno que ha tomado.
Extend: Cancelar Turno, en caso de que quiera anularlo.
Includ: Notifica estado de turno, para actualizar al cliente.
Administra disponibilidad de turnos: El administrador establece o modifica los turnos disponibles.
Notifica estado de turno: El sistema informa al cliente sobre el estado actual de su turno (por ejemplo, llamado, cancelado, etc.).

Explicación del diagrama de clases:
Clases principales:
Usuario: Representa al cliente. Contiene identificador (id) y RUT.
Turno (Prototype): Representa un turno individual con número, RUT del solicitante y estado.
Tiene un método Clonar() que indica uso del patrón Prototype, útil para duplicar turnos.
ControladorDeTurnos (Singleton):
Clase central que gestiona los turnos (crear, cancelar, ver disponibilidad).
Aplica el patrón Singleton para asegurar una única instancia que administre todos los turnos.

Notificación de turnos:
NotificadorDeTurnos (Observer + Bridge):
Maneja las notificaciones del estado de los turnos y comunica los cambios.
Usa el patrón Observer para actualizar métodos de notificación cuando hay cambios en el turno.

NotificarPorAltavoz / NotificarPorPantalla:
Clases concretas que implementan los métodos de notificación:

LlamarPorAltavoz(): Anuncia turnos por audio.

MostrarEnPantalla(): Muestra información visualmente.

Explicación del diagrama de implementación:
Componentes principales:
Administrador del sistema:
Tiene acceso completo para configurar y mantener el sistema, incluyendo la base de datos y el servidor.

Base de Datos:
Contiene dos entidades:

Turnos: Almacena información de los turnos generados.

Usuarios: Registra los datos de los usuarios que solicitan turnos.

Servidor Local:
Contiene los componentes lógicos del sistema:

Controlador de Turnos: Se encarga de crear, cancelar y gestionar turnos.

Notificador de turnos: Informa los cambios de estado de los turnos.

Totem de atención:
Punto de acceso del usuario para solicitar turnos. Se conecta al servidor local.

Altavoz y Pantalla:
Dispositivos de salida que ejecutan la notificación:

NotificarPorAltavoz: Anuncia los turnos por audio.

NotificarPorPantalla: Muestra visualmente el turno en pantalla.

📌 Descripción
El Sistema Turnomático es una solución tecnológica que asigna turnos de forma automatizada mediante la emisión de tickets numerados, ya sea a través de:

Pantallas táctiles

Aplicaciones web

Dispensadores físicos

Beneficios clave:
✔ Organiza la atención por orden de llegada o prioridades predefinidas
✔ Reduce tiempos de espera y mejora la eficiencia del servicio
✔ Incluye pantallas informativas, alertas visuales/sonoras y estadísticas de atención
✔ Optimiza la gestión de recursos humanos

📊 Diagrama de Casos de Uso
👥 Actores Principales

Actor	Descripción
------------------------------------------------------------------------
Cliente	Usuario que solicita y gestiona turnos                         |
------------------------------------------------------------------------
Administrador	Configura disponibilidad y parámetros del sistema        |
------------------------------------------------------------------------
Sistema de Notificación	Envía alertas sobre el estado de los turnos    |
------------------------------------------------------------------------

🔧 Casos de Uso

![image](/Turnomatico.drawio.png)

Función	Descripción
-------------------------------------------------------------
Tomar Turno	Genera un nuevo ticket numerado                 |
-------------------------------------------------------------
Consultar Estado	Verifica disponibilidad y posición en cola|
-------------------------------------------------------------
Cancelar Turno	Elimina un turno asignado                   |
-------------------------------------------------------------
Administrar Turnos	(Admin) Configura horarios y prioridades|
-------------------------------------------------------------
Notificar Estado	Alertas automáticas (pantalla/audio)      |
-------------------------------------------------------------
🧩 Diagrama de Clases (Estructura Principal)

![image](/DiagramadeclasesTurnomatico.drawio.png)

🔑 Patrones de Diseño Implementados
Patrón	Aplicación
------------------------------------------------------------------------
Singleton	ControladorDeTurnos (una única instancia global)             |
------------------------------------------------------------------------
Prototype	Turno (permite clonar turnos existentes)                     |
------------------------------------------------------------------------
Observer	NotificadorDeTurnos (actualiza métodos de alerta)            |
------------------------------------------------------------------------
Bridge	Separa notificaciones (audio/pantalla) de la lógica principal  |
------------------------------------------------------------------------
🖥️ Diagrama de Implementación

![image](/Diagramadeimplementacion.drawio.png)


🗃️ Estructura de Datos
-------------------------------------------------------------
Entidad	Campos                                              |
-------------------------------------------------------------
Turnos	ID, Número, RUT, Estado, Hora                       |
-------------------------------------------------------------
Usuarios	RUT, Nombre, Historial de Turnos                  |
-------------------------------------------------------------

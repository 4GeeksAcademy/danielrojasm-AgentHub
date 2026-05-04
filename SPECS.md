# AgentHub
- Es una plataforma de alquiler de agentes IA, asistentes inteligentes preconfigurados que pueden equiparse con distintas skills (habilidades como navegar por la web, leer documentos o gestionar calendarios) y desplegarse para tareas de negocio específicas.

Falta poner que puedes hacer como usuario admin

## Especificaciones
Stack:
- Usar HTML semantico
- Usar Tailwind via CDN

### Restricciones
- Solo Javascript vanilla
- Sin frameworks
- Sin backend

### Tarea
- Crear un index.html

### Requisitos 
- Toggle en la barra superior para cambiar toda la interfaz entre modo claro y modo oscuro usando las utilidades dark: de Tailwind
- Las siguientes  secciones deben ser accesibles desde una navegación lateral persistente
- El panel debe sentirse profesional e inmediatamente utilizable como referencia para el desarrollo futuro. Todos los datos deben estar hardcodeados

#### Dashboard
- Cuatro tarjetas de metrica visibles (ingresos totales generados del mes, pérdida total por descuentos y cupones, número de agentes activos en todos los clientes, y número de agentes actualmente marcados como fallando)

- Debajo de las tarjetas, incluye un área de marcador de posición para un gráfico de actividad semanal

- Las tarjetas unas colores distintos, con una sombra sutil

#### Gestión de usuarios
- Crear una tabla que lista todos los usuarios registrados (nombre, email, plan, estado).

- Cada fila debe tener un dropdown de acciones — un pequeño menú activado con un botón con al menos dos opciones: "Ver detalle" y "Eliminar"

- Al elegir "Ver detalle" se abre un modal overlay con el registro completo del usuario. El modal debe cerrarse mediante un botón y haciendo clic en el backdrop.

#### Gestión de agentes
- Crear un listado de todos los agentes registrados en la plataforma, mostrando nombre del agente, propietario, estado actual (activo / inactivo / fallando) y una lista de skills colapsada

-  Las skills asociadas a cada agente están ocultas por defecto; hacer clic en un control expandible las revela con una transición suave.

- Cada agente también tiene un dropdown de acciones con las opciones "Configurar" — que abre un modal con el prompt de sistema del agente — y "Eliminar".

#### Skills
- Una sección dedicada al catálogo de skills disponibles — las capacidades que se pueden adjuntar a los agentes. 

- Cada skill tiene un nombre, una descripción breve, y un indicador de cuántos agentes la tienen habilitada actualmente. Incluye una breve explicación dentro del panel sobre qué significa una "skill" en el contexto de AgentHub.

- Las skills también tienen un dropdown de acciones con "Ver detalle" y "Eliminar".

#### Contrataciones de agentes
- Crear una tabla que muestra todos los contratos de alquiler activos y pasados. 

- Cada fila debe mostrar el cliente, el agente alquilado, las skills contratadas, las fechas del contrato y el importe total pagado. 

- Cada fila tiene un dropdown de acciones. Al elegir "Ver detalle" se abre un modal con el desglose completo del contrato, incluyendo la lista desglosada de skills contratadas y sus precios individuales.

#### Log de errores
- Un registro de errores de ejecución de los agentes — mostrando timestamp, nombre del agente, tipo de error y una descripción breve. 

- Los errores deben categorizarse visualmente por tipo o gravedad usando badges con código de color. 

- Cada entrada tiene un dropdown de acciones con "Ver detalle" (abre un modal con la traza completa del error) y "Marcar como resuelto".
# SPECS - Prototipo Panel Admin AgentHub

## 1) Descripción del producto
AgentHub es una plataforma SaaS de alquiler de agentes IA para empresas. El usuario principal de este prototipo es un administrador interno que necesita supervisar negocio y operación en una sola interfaz: ingresos, usuarios, agentes, skills, contrataciones y errores.

Objetivo del entregable: construir un prototipo HTML navegable, visualmente consistente y con interacciones clave para validar UX/UI antes de integrar backend.

## 2) Stack tecnológico y restricciones
- HTML semántico (`header`, `nav`, `main`, `section`, `table`, `aside`, `button`, etc.).
- Tailwind CSS cargado exclusivamente por CDN.
- JavaScript vanilla para toda la interactividad.

Restricciones:
- Sin frameworks frontend (React/Vue/Angular/etc.).
- Sin jQuery.
- Sin backend ni llamadas a API.
- Todos los datos son hardcodeados.
- Sin archivos CSS personalizados ni estilos inline.

## 3) Estructura general de interfaz
- Layout principal de dos columnas: sidebar persistente a la izquierda y contenido principal a la derecha.
- Barra superior fija dentro del panel de contenido con título de la sección activa y toggle de modo claro/oscuro.
- Navegación lateral con seis entradas: Dashboard, Gestión de usuarios, Gestión de agentes, Skills, Contrataciones de agentes, Log de errores.
- Sección activa destacada visualmente.
- Diseño responsive para desktop y tablet.

## 4) Especificaciones por sección

### 4.1 Dashboard
1. Mostrar cuatro tarjetas de métricas en una grilla responsive (`1x4` en desktop, `2x2` en tablet): ingresos del mes, pérdidas por descuentos/cupones, agentes activos, agentes fallando.
2. Cada tarjeta incluye icono, etiqueta, valor hardcodeado y color de acento distinto; todas usan contenedor con borde y sombra sutil para jerarquía visual.
3. Debajo de las métricas, renderizar un bloque de ancho completo como placeholder de gráfico semanal con borde discontinuo, altura fija y etiqueta centrada "Actividad semanal".

### 4.2 Gestión de usuarios
1. Mostrar tabla con mínimo 5 usuarios hardcodeados y columnas: nombre, email, plan, estado y acciones.
2. La columna estado usa badges con color según estado (`activo`, `pendiente`, `suspendido`).
3. Cada fila tiene botón de acciones `⋮` que abre dropdown con `Ver detalle` y `Eliminar`.
4. `Ver detalle` abre modal overlay con ficha completa del usuario (ID, empresa, fecha de alta, plan, estado y notas).
5. El modal de usuario cierra con botón explícito y clic en backdrop.

### 4.3 Gestión de agentes
1. Renderizar listado con mínimo 4 agentes hardcodeados mostrando nombre, propietario, estado y acciones.
2. El estado del agente se representa con badge (`activo`, `inactivo`, `fallando`) y color consistente con su semántica.
3. Cada agente contiene un bloque colapsable de skills oculto por defecto; al expandir, mostrar lista de skills con transición suave de altura/opacidad.
4. Cada agente tiene dropdown `⋮` con `Configurar` y `Eliminar`.
5. `Configurar` abre modal con prompt de sistema del agente dentro de un `textarea` editable.

### 4.4 Skills
1. Mostrar catálogo con mínimo 4 skills en formato tarjeta o lista visual, cada una con nombre, descripción breve y contador de agentes habilitados.
2. Incluir bloque explicativo dentro de la sección que defina qué es una skill en el contexto de AgentHub.
3. Cada skill incluye dropdown `⋮` con acciones `Ver detalle` y `Eliminar`.
4. `Ver detalle` abre modal con información ampliada (casos de uso, límites, versión, última actualización).

### 4.5 Contrataciones de agentes
1. Mostrar tabla con mínimo 4 contratos hardcodeados y columnas: cliente, agente, skills contratadas, fechas inicio/fin, importe total y acciones.
2. Skills contratadas se muestran como lista compacta/badges dentro de la celda.
3. Cada fila incluye dropdown `⋮`; opción `Ver detalle` abre modal de desglose completo del contrato.
4. El modal de contrato detalla precio base del agente, precio individual por skill y total final.

### 4.6 Log de errores
1. Mostrar registro con mínimo 6 entradas de error hardcodeadas y campos: timestamp, agente, tipo, severidad y descripción breve.
2. Tipo/severidad se destaca con badges de color (`critico`, `error`, `advertencia`) para lectura rápida.
3. Cada entrada tiene dropdown `⋮` con `Ver detalle` y `Marcar como resuelto`.
4. `Ver detalle` abre modal con traza completa del error (stack trace multilinea).

## 5) Inventario de componentes reutilizables
- Sidebar de navegación persistente.
- Topbar con título de sección y toggle de tema.
- Tarjeta de métrica.
- Tabla de datos reutilizable.
- Badge de estado/severidad.
- Dropdown de acciones (`⋮`) con cierre por clic externo.
- Modal base reutilizable con overlay, encabezado, contenido y cierre.
- Ítem de lista colapsable (skills de agentes).
- Chips/badges para skills asociadas.

## 6) Comportamientos interactivos globales
- Toggle claro/oscuro: alterna clase `dark` en el elemento raíz y aplica clases `dark:` en toda la UI.
- Persistencia de tema: guardar preferencia en `localStorage` y restaurarla al recargar.
- Navegación interna: mostrar/ocultar secciones sin recarga y actualizar estado activo del sidebar.
- Dropdowns: solo uno abierto a la vez; cerrar al hacer clic fuera o al ejecutar acción.
- Modales: abrir por acción contextual y cerrar por botón o clic en backdrop.
- Colapsables de skills: iniciar cerrados y cambiar estado con transición visible al hacer clic.

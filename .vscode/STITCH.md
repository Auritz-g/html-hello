Diseñame una paltafor para una startup llamada AgentHub donde las empresas pueden alquilar agentes de IA
La plataforma debe contener:
Una navegación lateral persistente con enlaces de navegación a las 6 secciones y un indicador de sección activa (responsive para tablet y escritorio colapsando a solo iconos en tablet)
Un toggle en la barra superior para cambiar la interfaz entre modo claro y oscuro.
El panel debe sentirse profesional y utilizable
Tablas modernas
Tarjetas con esquinas redondeadas
Dropdown shadow elegante y sutil
Estructura elegante

Genera propuestas visuales para 
Dasboard
Gestión de usuarios
Gestión de agentes
Skills
Contrataciones de agentes
Log de errores
Manten coherencia y consistencia entre las vistas

# Especificación del Panel de Administración — AgentHub

## 1. Descripción del producto

**AgentHub** es una plataforma SaaS que permite a empresas contratar agentes de IA especializados para automatizar tareas específicas (atención al cliente, análisis de datos, moderación de contenido, etc.). Los clientes pueden navegar por un catálogo de agentes, cada uno equipado con un conjunto de habilidades ("skills") y contratarlos por períodos determinados.

El presente documento describe el **panel de administración** de AgentHub, una interfaz web destinada al **usuario administrador** de la plataforma. Este administrador necesita un panel unificado para supervisar métricas clave del negocio, gestionar usuarios registrados, administrar el catálogo de agentes y sus skills, revisar contrataciones activas y pasadas, y monitorizar errores de ejecución de los agentes.

## 2. Stack tecnológico y restricciones

| Aspecto | Decisión |
|---|---|
| **Lenguaje** | HTML5 semántico |
| **Estilos** | Tailwind CSS vía CDN (`@tailwindcss/browser` v4) — sin archivos CSS personalizados, sin atributos `style` en línea |
| **Interactividad** | JavaScript vanilla (ES6+) — sin frameworks, sin jQuery, sin build tools |
| **Backend** | Ninguno — todos los datos son hardcodeados en el frontend |
| **Iconos** | SVG inline desde la carpeta `/icons/` del proyecto |
| **Arquitectura** | Single Page Application (SPA) — el contenido de cada sección se muestra/oculta mediante JavaScript, sin recarga de página |
| **Formato** | Un único archivo `index.html` que contiene la estructura completa |

## 3. Layout global

### 3.1. Sidebar persistente (navegación lateral)

1. **Sidebar de ancho fijo (~240px en escritorio)** anclada al borde izquierdo del viewport. Contiene el logo de AgentHub en la parte superior, seguido de seis enlaces de navegación vertical, uno por sección: Dashboard, Gestión de usuarios, Gestión de agentes, Skills, Contrataciones de agentes y Log de errores. Cada enlace muestra un icono SVG (desde `/icons/`) a la izquierda y el nombre de la sección a la derecha.

2. **Indicador de sección activa:** El enlace correspondiente a la sección actualmente visible se resalta con un color de fondo distintivo (`bg-slate-100` en modo claro, `dark:bg-slate-800` en modo oscuro) y el texto en negrita. El estado activo se actualiza mediante JavaScript al hacer clic en cualquier enlace.

3. **Sidebar colapsable en tablet:** En viewports menores a 1024px, la sidebar se reduce a mostrar solo los iconos (sin texto), manteniendo su funcionalidad completa. Un botón de hamburguesa (icono de menú) en la barra superior permite expandirla para mostrar los nombres de las secciones cuando sea necesario. En viewports de escritorio (≥1024px) la sidebar siempre se muestra expandida con icono + texto.

### 3.2. Barra superior (top header)

4. **Barra superior fija** de altura ~64px, situada a la derecha de la sidebar, ocupando el ancho restante. Muestra a la izquierda el título de la sección activa y a la derecha un toggle de modo oscuro/claro representado por los iconos de luna (`/icons/dark mode.svg`) y sol (`/icons/light mode.svg`).

5. **Toggle de modo oscuro/claro:** Al hacer clic en el botón de la barra superior, se alterna la clase `dark` en el elemento `<html>`. El estado del modo se conserva al navegar entre secciones (no se pierde al cambiar de vista). Los estilos utilizan las utilidades `dark:` de Tailwind para todo el cambio de color.

### 3.3. Área de contenido principal

6. **Contenedor `<main>`** situado a la derecha de la sidebar, con padding interior de ~24px. Muestra únicamente el contenido de la sección activa. Las secciones no visibles permanecen en el DOM ocultas con `hidden` y se muestran/ocultan mediante clases CSS controladas por JavaScript.

### 3.4. Paleta de colores (definida en DESIGN.md)

Los colores exactos, sus roles (fondo, superficie, texto, bordes, backdrop) y su equivalencia con clases de Tailwind tanto en modo claro como oscuro se documentan en el archivo `DESIGN.md` de la raíz del proyecto.

## 4. Especificaciones por sección

### 4.1. Dashboard ("De un vistazo")

1. **Cuatro tarjetas de métrica en cuadrícula responsive 2×2.** Cada tarjeta contiene un icono SVG (de `/icons/earnings.svg`, `/icons/loss.svg`, `/icons/active.svg`, `/icons/failing agents.svg`), una etiqueta descriptiva (ej. "Ingresos totales"), y un valor numérico hardcodeado (ej. "$48,250"). Las tarjetas miden el mismo alto y ancho, tienen fondo blanco (`bg-white` en modo claro, `dark:bg-slate-900` en modo oscuro), borde sutil (`border border-slate-200`), y una sombra ligera (`shadow-sm`). Se disponen en una cuadrícula de 2 columnas en escritorio y 1 columna en tablet/móvil.

2. **Colores de acento por tipo de métrica:** Cada tarjeta incorpora un detalle visual distintivo —un borde izquierdo de 4px de ancho— con un color diferente según la métrica: azul (`bg-blue-500`) para ingresos, naranja (`bg-orange-500`) para pérdidas, verde (`bg-green-500`) para agentes activos, y rojo (`bg-red-500`) para agentes fallando.

3. **Área de marcador de posición para gráfico de actividad semanal:** Debajo de las tarjetas, un div de ancho completo con un borde discontinuo (`border-dashed border-slate-300`), altura de 200px, y fondo ligeramente tintado (`bg-slate-50` en modo claro, `dark:bg-slate-800` en modo oscuro). En el centro del área se muestra una etiqueta "Gráfico de actividad semanal" en texto secundario. Este componente es puramente decorativo y no implementa un gráfico real.

### 4.2. Gestión de usuarios

1. **Tabla de usuarios con al menos 5 filas hardcodeadas.** La tabla incluye cuatro columnas: Nombre, Email, Plan (con valores "Starter", "Professional", "Enterprise"), y Estado (mostrado como badge de color). La tabla usa una cabecera con fondo `bg-slate-100` y filas sin color adicional. Es responsiva horizontalmente con overflow-x en viewports estrechos.

2. **Badges de estado con código de color:** La columna "Estado" usa un badge de texto pequeño con fondo de color: verde (`bg-green-100 text-green-800`) para "Activo", rojo (`bg-red-100 text-red-800`) para "Inactivo", y amarillo (`bg-yellow-100 text-yellow-800`) para "Pendiente". Cada badge incorpora el icono correspondiente: `/icons/active.svg` para Activo, `/icons/failing agents.svg` para Inactivo, y el icono de error para Pendiente.

3. **Dropdown de acciones (⋮) por fila:** La última columna de cada fila contiene un botón con el icono `/icons/vertical dots.svg`. Al hacer clic, se despliega un menú contextual con las opciones "Ver detalle" y "Eliminar". El menú se posiciona debajo del botón y se cierra al hacer clic en cualquier parte fuera de su área.

4. **Modal "Ver detalle":** Al seleccionar "Ver detalle", se abre un modal overlay centrado que muestra la información completa del usuario: nombre, email, plan, estado, fecha de registro y empresa asociada. El modal contiene un botón de cierre (icono `/icons/close.svg`) en la esquina superior derecha. Se cierra al hacer clic en el botón de cierre, al hacer clic en el backdrop (fondo semitransparente), y al presionar la tecla Escape.

5. **Confirmación de "Eliminar":** Al seleccionar "Eliminar", se abre un modal de confirmación con el mensaje "¿Estás seguro de que deseas eliminar a [nombre]?" y dos botones: "Cancelar" (con estilo secundario, fondo `bg-slate-100`) y "Eliminar" (con estilo destructivo, fondo `bg-red-600 text-white`). El modal se cierra con cualquiera de los dos botones, con el backdrop, o con Escape.

### 4.3. Gestión de agentes

1. **Listado de al menos 4 agentes en formato de tarjetas.** Cada agente muestra: nombre del agente (ej. "SupportBot Alpha"), propietario (nombre del usuario que lo creó), badge de estado (Activo/Inactivo/Fallando con código de color y icono), y una lista de skills colapsada por defecto.

2. **Lista de skills colapsable con transición suave:** Cada tarjeta de agente tiene un botón de expandir/colapsar (icono `/icons/expand.svg`). Por defecto, las skills están ocultas. Al hacer clic en el botón, las skills se revelan con una transición de altura suave (usando `max-height` y `overflow-hidden` con transición CSS). Al hacer clic nuevamente, se colapsan con la misma transición.

3. **Dropdown de acciones (⋮) por agente:** Similar al de usuarios, con botón de tres puntos verticales y las opciones "Configurar" y "Eliminar". El menú se cierra al hacer clic fuera.

4. **Modal "Configurar":** Al seleccionar "Configurar", se abre un modal con el prompt de sistema del agente en un `<textarea>` editable. El textarea ocupa la mayor parte del modal y contiene el texto del prompt hardcodeado (ej. "Eres un asistente de soporte técnico especializado en..."). El modal tiene botón "Guardar" (que no persiste los cambios por ser simulado) y "Cerrar".

5. **Confirmación de "Eliminar":** Mismo patrón que en usuarios: modal de confirmación con "Cancelar" y "Eliminar" (estilo destructivo rojo).

### 4.4. Skills

1. **Explicación contextual de "skill":** En la parte superior de la sección, un párrafo explicativo con fondo informativo suave (`bg-blue-50 dark:bg-blue-900/20`) que dice: "Las skills son capacidades especializadas que pueden asignarse a los agentes de IA. Cada skill define un área de conocimiento o una tarea específica que el agente puede ejecutar, como análisis de sentimiento, traducción automática o generación de informes."

2. **Catálogo de al menos 4 skills en formato de tarjetas.** Cada tarjeta muestra: nombre de la skill, descripción breve, y un indicador numérico de cuántos agentes la tienen habilitada (ej. "Habilitada en 3 agentes").

3. **Dropdown de acciones (⋮) por skill:** Botón de tres puntos verticales con opciones "Ver detalle" y "Eliminar".

4. **Modal "Ver detalle" de skill:** Muestra la información completa de la skill: nombre, descripción detallada, lista de agentes que la tienen habilitada (nombres hardcodeados) y fecha de creación.

5. **Confirmación de "Eliminar":** Mismo patrón de modal de confirmación destructiva.

### 4.5. Contrataciones de agentes

1. **Tabla de al menos 4 contratos.** Columnas: Cliente (nombre de empresa), Agente (nombre del agente), Skills contratadas (lista abreviada separada por comas), Fecha de inicio, Fecha de fin, e Importe pagado (formato moneda, ej. "$1,200"). La tabla sigue el mismo estilo que la de usuarios.

2. **Dropdown de acciones (⋮) por fila:** Botón de tres puntos verticales con opción "Ver detalle".

3. **Modal "Ver detalle" con desglose del contrato:** Al seleccionar "Ver detalle", se abre un modal que muestra: cliente, agente, fechas del contrato, y un desglose detallado de las skills contratadas con sus precios individuales (ej. "Análisis de sentimiento — $400/mes") y el total pagado. El desglose usa una tabla interna o lista con bordes sutiles.

### 4.6. Log de errores

1. **Listado de al menos 6 entradas de error.** Cada entrada muestra: timestamp (ej. "2026-11-20 14:32:01"), nombre del agente, badge de tipo de error con código de color (ej. "Timeout" en naranja, "Crash" en rojo, "API Error" en amarillo, "Validation" en azul), y una descripción breve del error.

2. **Badges de tipo de error con código de color:** Cada badge usa un color distinto según la categoría: rojo (`bg-red-100 text-red-800`) para "Crash", naranja (`bg-orange-100 text-orange-800`) para "Timeout", amarillo (`bg-yellow-100 text-yellow-800`) para "API Error", y azul (`bg-blue-100 text-blue-800`) para "Validation".

3. **Dropdown de acciones (⋮) por entrada:** Botón de tres puntos verticales con opciones "Ver detalle" y "Marcar como resuelto".

4. **Modal "Ver detalle" de error:** Muestra la traza completa del error: timestamp, agente, tipo de error, descripción, stack trace simulado (bloque de texto monoespaciado en un contenedor con scroll), y el ID del contrato asociado.

5. **Feedback de "Marcar como resuelto":** Al seleccionar "Marcar como resuelto", la entrada de error se atenúa visualmente (opacidad reducida y badge "Resuelto" añadido). No se requiere persistencia.

## 5. Componentes de UI reutilizables

| Componente | Descripción | Secciones donde aparece |
|---|---|---|
| **Sidebar** | Barra lateral de navegación con icono + texto, colapsable a solo iconos en tablet | Global (todas las secciones) |
| **Barra superior (Header)** | Barra superior con título de sección y toggle de modo oscuro | Global (todas las secciones) |
| **Tarjeta de métrica** | Tarjeta con icono SVG, etiqueta, valor numérico y borde izquierdo de acento de 4px | Dashboard |
| **Badge de estado** | Etiqueta pequeña con color de fondo, texto e icono para indicar estado (Activo/Inactivo/Pendiente) | Usuarios, Agentes, Log de errores |
| **Dropdown de acciones** | Menú contextual posicionado debajo del botón ⋮, con cierre al hacer clic fuera (event listener en documento) | Usuarios, Agentes, Skills, Contrataciones, Log de errores |
| **Modal** | Overlay centrado con backdrop semitransparente, cierre por botón X (icono close.svg), clic en backdrop y tecla Escape | Usuarios (detalle/eliminar), Agentes (configurar/eliminar), Skills (detalle/eliminar), Contrataciones (detalle), Log de errores (detalle) |
| **Lista de skills colapsable** | Lista expandible/colapsable con transición suave de altura (max-height + overflow-hidden + transition) | Gestión de agentes |
| **Toggle de modo oscuro** | Botón que alterna la clase `dark` en `<html>` usando iconos de luna (`/icons/dark mode.svg`) y sol (`/icons/light mode.svg`) | Barra superior (global) |
| **Tabla** | Tabla responsiva con cabecera (`<thead>`) y filas de datos (`<tbody>`), con scroll horizontal en viewports estrechos | Usuarios, Contrataciones |
| **Textarea editable** | Área de texto multilínea dentro de modal para editar el system prompt del agente | Gestión de agentes (modal Configurar) |

## 6. Datos hardcodeados

Los datos deben ser coherentes entre secciones. Los mismos nombres de agentes, usuarios y skills deben aparecer en todas las vistas donde sean relevantes.

### 6.1 Usuarios (5+)

| Nombre | Email | Plan | Estado |
|---|---|---|---|
| Ana Martínez | ana@techcorp.com | Enterprise | Activo |
| Carlos López | carlos@dataflow.io | Professional | Activo |
| Elena García | elena@innovatech.es | Starter | Pendiente |
| David Kim | david@cloudnine.dev | Enterprise | Activo |
| Sofía Torres | sofia@nexusai.co | Professional | Inactivo |

### 6.2 Agentes (4+)

| Nombre | Propietario | Estado | Skills |
|---|---|---|---|
| SupportBot Alpha | Ana Martínez | Activo | Análisis de sentimiento, Atención al cliente |
| DataMiner X | David Kim | Fallando | Análisis de datos, Generación de informes |
| TransLingua Pro | Carlos López | Activo | Traducción automática, Detección de idiomas |
| ModGuard 3000 | Elena García | Inactivo | Moderación de contenido, Filtro de toxicidad |

### 6.3 Skills (4+)

| Skill | Descripción | Agentes que la usan |
|---|---|---|
| Análisis de sentimiento | Detecta emociones y tono en texto | 2 (SupportBot Alpha, DataMiner X) |
| Traducción automática | Traduce entre más de 50 idiomas | 1 (TransLingua Pro) |
| Moderación de contenido | Identifica contenido inapropiado | 1 (ModGuard 3000) |
| Generación de informes | Crea reportes estructurados a partir de datos | 2 (DataMiner X, SupportBot Alpha) |
| Atención al cliente | Responde consultas usando base de conocimiento | 1 (SupportBot Alpha) |
| Detección de idiomas | Identifica el idioma de un texto automáticamente | 1 (TransLingua Pro) |
| Filtro de toxicidad | Detecta lenguaje dañino u ofensivo | 1 (ModGuard 3000) |
| Análisis de datos | Extrae patrones y tendencias de grandes volúmenes de datos | 1 (DataMiner X) |

### 6.4 Contratos (4+)

| Cliente | Agente | Skills contratadas | Inicio | Fin | Importe |
|---|---|---|---|---|---|
| TechCorp Inc. | SupportBot Alpha | Análisis de sentimiento, Atención al cliente | 2026-10-01 | 2027-03-31 | $2,400 |
| CloudNine Dev | DataMiner X | Análisis de datos, Generación de informes | 2026-09-15 | 2026-12-15 | $1,800 |
| DataFlow Solutions | TransLingua Pro | Traducción automática, Detección de idiomas | 2026-11-01 | 2027-04-30 | $2,100 |
| NovaTech ES | ModGuard 3000 | Moderación de contenido, Filtro de toxicidad | 2026-08-01 | 2026-10-31 | $900 |

### 6.5 Errores (6+)

| Timestamp | Agente | Tipo | Descripción |
|---|---|---|---|
| 2026-11-20 14:32:01 | DataMiner X | Timeout | El agente no respondió dentro del tiempo límite de 30s |
| 2026-11-20 12:15:44 | DataMiner X | Crash | Excepción no controlada en el módulo de análisis |
| 2026-11-19 09:47:22 | SupportBot Alpha | API Error | La API de sentimiento devolvió un código 503 |
| 2026-11-18 22:05:13 | TransLingua Pro | Validation | El texto de entrada supera el límite de 10k caracteres |
| 2026-11-18 16:30:59 | DataMiner X | Timeout | Timeout en consulta a base de datos externa |
| 2026-11-17 08:12:36 | ModGuard 3000 | Crash | Fallo en el motor de filtrado de toxicidad |
| 2026-11-16 19:45:00 | SupportBot Alpha | API Error | La API de conocimiento base no está disponible |

## 7. Criterios de aceptación

1. **Sidebar navegable:** Las seis secciones son accesibles desde la sidebar. Al hacer clic en un enlace, el contenido de la sección correspondiente se muestra y el enlace se marca como activo visualmente.

2. **Sidebar colapsable en tablet:** En viewports menores a 1024px, la sidebar se reduce a iconos. Un botón de menú (hamburguesa) permite expandirla para mostrar los nombres de las secciones.

3. **Dropdowns funcionales:** Todas las filas y tarjetas de listados (usuarios, agentes, skills, contratos, errores) tienen un botón ⋮ que despliega un menú contextual. Los menús se cierran al hacer clic en cualquier área fuera del menú.

4. **Modales de detalle:** En al menos cuatro secciones diferentes (usuarios, agentes, contrataciones y log de errores), al seleccionar "Ver detalle" en el dropdown, se abre un modal overlay con la información completa del registro.

5. **Cierre de modales:** Todos los modales se cierran mediante: (a) el botón de cierre (icono X con `/icons/close.svg`), (b) clic en el backdrop, y (c) tecla Escape.

6. **Confirmación de acciones destructivas:** Al seleccionar "Eliminar" en cualquier dropdown, se muestra un modal de confirmación con botones "Cancelar" (estilo secundario, `bg-slate-100`) y "Eliminar" (estilo destructivo, `bg-red-600 text-white`).

7. **Skills colapsables:** Las listas de skills de los agentes están colapsadas por defecto. Al hacer clic en el control expandible, las skills se revelan con una transición suave de altura. Al hacer clic nuevamente, se colapsan.

8. **Modal "Configurar" con textarea editable:** En Gestión de agentes, al seleccionar "Configurar" del dropdown, se abre un modal con el system prompt del agente en un `<textarea>` HTML editable.

9. **Toggle de modo oscuro/claro:** El botón en la barra superior alterna entre modo claro y oscuro usando la clase `dark` en `<html>`. El cambio es global e instantáneo, y el estado persiste al navegar entre secciones (no se pierde al cambiar de vista).

10. **Coherencia de datos:** Los mismos nombres de agentes (SupportBot Alpha, DataMiner X, TransLingua Pro, ModGuard 3000), usuarios (Ana Martínez, David Kim, etc.) y skills aparecen consistentemente en todas las secciones donde son referenciados.

11. **HTML semántico:** El documento usa etiquetas semánticas HTML5 correctamente: `section` para cada sección, `table` para tablas, `nav` para la sidebar, `header` para la barra superior, `main` para el contenido principal.

12. **Sin estilos en línea:** No se utilizan atributos `style` en línea ni archivos CSS personalizados. Todos los estilos se aplican exclusivamente mediante clases utilitarias de Tailwind cargadas vía CDN.

13. **Layout responsivo:** El panel es funcional en viewports de escritorio (≥1024px) y tablet (≥640px). Las tablas tienen scroll horizontal en viewports estrechos. Las tarjetas de métrica se apilan en una columna en tablet.

14. **Marcar error como resuelto:** Al seleccionar "Marcar como resuelto" en el log de errores, la entrada se atenúa visualmente (opacidad reducida y badge "Resuelto" superpuesto).

15. **Desglose de contrato:** El modal "Ver detalle" de contrataciones muestra las skills desglosadas con sus precios individuales y el total pagado.

16. **Stack trace en modal de error:** El modal "Ver detalle" del log de errores muestra un stack trace simulado en formato monoespaciado dentro de un contenedor con scroll.
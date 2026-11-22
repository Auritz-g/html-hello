## 💻 Qué debes hacer

### Escribe la especificación primero
- [x] Crea un archivo llamado `SPECS.md` en la raíz del repositorio.
- [x] En `SPECS.md`, escribe una especificación estructurada que incluya:
  - [x] Una breve descripción del producto (qué es AgentHub y quién es el usuario administrador).
  - [x] El stack tecnológico y las restricciones (HTML, Tailwind vía CDN, solo JS vanilla, sin frameworks, sin backend).
  - [x] **Al menos 3 especificaciones por sección** — cada una describiendo un requisito visual o interactivo concreto para esa vista. Una buena entrada de spec nombra un componente, describe su contenido y define su comportamiento. Por ejemplo, para el Dashboard: *(1) cuatro tarjetas de métricas en una cuadrícula responsive 2×2, cada una con un icono, una etiqueta y un valor hardcodeado; (2) las tarjetas usan colores de acento distintos por tipo de métrica e incluyen una sombra sutil; (3) debajo de las tarjetas, un div de ancho completo con borde discontinuo y una etiqueta centrada representa el gráfico de actividad semanal.* Aplica este nivel de detalle a las seis secciones.
  - [x] Un inventario de componentes: una lista de los componentes de UI reutilizables que aparecen en varias secciones (sidebar, tarjeta de métrica, dropdown de acciones, modal, badge, lista de skills colapsable, toggle de modo oscuro).
  - [x] Criterios de aceptación: una lista numerada de condiciones verificables que deben cumplirse para que el prototipo se considere completo — incluye al menos un criterio por comportamiento interactivo (dropdown, modal, colapsable, modo oscuro).
- [x] Commitea `SPECS.md` al repositorio **antes** de comenzar cualquier trabajo en HTML.
- [x] Usa el contenido de `SPECS.md` para generar una propuesta visual en [Google Stitch](https://stitch.withgoogle.com/) y úsala como guía de diseño (no como entrega final).

> ⚠️ **IMPORTANTE:** La especificación debe estar commiteada antes del primer archivo HTML. Usa un commit separado para la spec — se revisará el historial de Git. Un agente de código IA debería poder leer tu `SPECS.md` y construir el panel desde él sin hacer ninguna pregunta. Ese es tu estándar de calidad.
> ⚠️ **IMPORTANTE:** La propuesta visual de Stitch es solo un punto de partida. Debes adaptar estructura, componentes e interacciones para que coincidan exactamente con los requisitos de este proyecto.

---

### Construye el prototipo
- [x] Construye el panel de administración como un único archivo `index.html` (o varios archivos HTML enlazados, uno por sección).
- [x] Usa **Tailwind CSS vía CDN** para todos los estilos — sin archivos CSS personalizados, sin atributos `style` en línea.
- [x] Implementa una **barra lateral (sidebar)** persistente con enlaces de navegación a las seis secciones y un indicador de sección activa.

#### Dashboard
- [x] Cuatro tarjetas de métricas (ingresos totales, pérdidas por descuentos, agentes activos, agentes fallando), cada una con un icono, una etiqueta y un valor hardcodeado.
- [x] Un área de ancho completo debajo de las tarjetas que representa un gráfico de actividad semanal.

#### Gestión de usuarios
- [x] Una tabla con al menos 5 filas de usuarios hardcodeados mostrando nombre, email, plan y badge de estado.
- [x] Cada fila tiene un dropdown `⋮` con "Ver detalle" y "Eliminar".
- [x] "Ver detalle" abre un modal con el registro completo del usuario. El modal se cierra con el botón de cierre y haciendo clic en el backdrop.

#### Gestión de agentes
- [x] Un listado con al menos 4 agentes, cada uno mostrando nombre, propietario, badge de estado y una lista de skills colapsada.
- [x] Hacer clic en el control expandible revela las skills del agente con una transición suave; volver a hacer clic las colapsa.
- [x] Cada agente tiene un dropdown `⋮` con "Configurar" y "Eliminar". "Configurar" abre un modal con el prompt de sistema del agente en un `<textarea>` editable.

#### Skills
- [x] Un catálogo de al menos 4 skills, cada una mostrando nombre, descripción y el número de agentes que la tienen habilitada.
- [x] Una breve explicación dentro del panel sobre qué es una "skill" en el contexto de AgentHub.
- [x] Cada skill tiene un dropdown `⋮` con "Ver detalle" y "Eliminar".

#### Contrataciones de agentes
- [x] Una tabla con al menos 4 contratos mostrando cliente, agente, skills contratadas, fechas de inicio/fin e importe pagado.
- [x] Cada fila tiene un dropdown `⋮`. "Ver detalle" abre un modal con el desglose completo del contrato, incluyendo skills desglosadas y sus precios individuales.

#### Log de errores
- [x] Al menos 6 entradas de error hardcodeadas mostrando timestamp, nombre del agente, badge de tipo de error con código de color, y descripción breve.
- [x] Cada entrada tiene un dropdown `⋮` con "Ver detalle" y "Marcar como resuelto".

#### Interacciones globales
- [x] Un toggle de modo oscuro/claro en la barra superior cambia todo el panel entre esquemas de color usando las utilidades `dark:` de Tailwind. El modo elegido se conserva al navegar entre secciones.
- [x] Todos los dropdowns de acciones se cierran al hacer clic fuera de su área.
- [x] Todos los modales se cierran al hacer clic en el backdrop.

> ⚠️ **IMPORTANTE:** Toda la interactividad debe implementarse con **JavaScript vanilla** únicamente — sin frameworks (React, Vue, etc.), sin jQuery, sin herramientas de build. Tailwind debe cargarse solo vía CDN.

---

## ✅ Qué vamos a evaluar
- [x] `SPECS.md` fue commiteado antes de cualquier archivo HTML (verificado mediante el historial de Git).
- [x] La spec contiene al menos 3 especificaciones concretas por sección, un inventario de componentes y una lista numerada de criterios de aceptación.
- [x] Las seis secciones del panel están presentes y son accesibles desde la barra lateral.
- [x] Las clases utilitarias de Tailwind se usan de forma consistente en todo el proyecto — sin estilos en línea, sin archivos CSS externos.
- [x] Todas las filas de los listados tienen un dropdown `⋮` funcional que se abre, se cierra al hacer clic y se cierra al hacer clic fuera.
- [x] "Ver detalle" abre un modal en al menos cuatro secciones diferentes.
- [x] Los modales se cierran con el botón de cierre y con clic en el backdrop.
- [x] Las listas de skills de los agentes están colapsadas por defecto y se expanden/colapsan al hacer clic con una transición visible.
- [x] El toggle de modo oscuro/claro cambia todo el panel y el estado se mantiene entre secciones.
- [x] Los datos hardcodeados son consistentes entre secciones (el mismo nombre de agente aparece en Gestión de agentes, Contrataciones y Log de errores).
- [x] El HTML usa etiquetas semánticas correctamente — `section`, `table`, `nav`, `header`, `main` y similares.
- [x] El layout es usable en viewports de escritorio y tablet.

> Nota: El envío de formularios, la búsqueda en vivo y la navegación real entre páginas no se evalúan. Los comportamientos interactivos descritos arriba — dropdowns, modales, colapsables, modo oscuro — son obligatorios y se comprobarán manualmente.
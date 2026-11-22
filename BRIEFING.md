# Requisitos del Panel de Administración — AgentHub
El panel debe incluir las siguientes seis secciones, accesibles desde una navegación lateral persistente. 
Un toggle **en la barra superior** debe permitir cambiar toda la interfaz entre modo claro y modo oscuro **usando las utilidades dark: de Tailwind**.

1. **Dashboard De un vistazo**
  1.1. El administrador debe poder ver:
    - Ingresos totales generados (este mes)
    - Pérdida total por descuentos y cupones
    - Número de agentes activos en todos los clientes
    - Número de agentes actualmente marcados como fallando
  1.2. Cada uno de estos debe ser una tarjeta de métrica visible.
    - Debajo de las tarjetas, incluye un área de marcador de posición para un gráfico de actividad semanal.

2. **Gestión de usuarios**
  2.1. Una tabla que lista todos los usuarios registrados:
    - Nombre
    - E-mail
    - Plan
    - Estado
  2.2. Cada fila debe tener un dropdown de acciones:
    - Un pequeño menú activado con un botón `⋮`
    - Debe tener al menos dos opciones:
      - "Ver detalle"
        - Al elegir "Ver detalle" se abre un modal overlay con el registro completo del usuario.
        - El modal debe cerrarse mediante un botón y haciendo clic en el backdrop.
      - "Eliminar"

3. **Gestión de agentes**
  3.1. Un listado de todos los agentes registrados en la plataforma, mostrando:
    - Nombre del agente
    - Propietario
    - Estado actual (`activo` / `inactivo` / `fallando`)
    - Lista de skills colapsada
      - Las skills asociadas a cada agente están ocultas por defecto.
      - Hacer clic en un control expandible las revela con una transición suave.
  3.2. Cada agente también tiene un dropdown de acciones:
    - Un pequeño menú activado con un botón `⋮`
    - Debe tener al menos dos opciones:
      - "Configurar"
        - Abre un modal con el prompt de sistema del agente.
      - "Eliminar"

4. **Skills**
  4.1. Una sección dedicada al catálogo de skills disponibles (las capacidades que se pueden adjuntar a los agentes).
    - Incluye una breve explicación dentro del panel sobre qué significa una "skill" en el contexto de AgentHub.
  4.2. Cada skill debe mostrar:
    - Nombre
    - Descripción breve
    - Indicador de cuántos agentes la tienen habilitada actualmente
  4.3. Cada skill tiene un dropdown de acciones:
    - Un pequeño menú activado con un botón `⋮`
    - Debe tener las opciones:
      - "Ver detalle"
      - "Eliminar"

5. **Contrataciones de agentes**
  5.1. Una tabla que muestra todos los contratos de alquiler activos y pasados, donde cada fila debe mostrar:
    - Cliente
    - Agente alquilado
    - Skills contratadas
    - Fechas del contrato
    - Importe total pagado
  5.2. Cada fila tiene un dropdown de acciones:
    - Un pequeño menú activado con un botón `⋮`
    - Al elegir "Ver detalle":
      - Se abre un modal con el desglose completo del contrato.
      - Debe incluir la lista desglosada de skills contratadas y sus precios individuales.

6. **Log de errores**
  6.1. Un registro de errores de ejecución de los agentes, mostrando:
    - Timestamp
    - Nombre del agente
    - Tipo de error
    - Descripción breve
  6.2. Categorización visual:
    - Los errores deben categorizarse visualmente por tipo o gravedad usando badges con código de color.
  6.3. Cada entrada tiene un dropdown de acciones:
    - Un pequeño menú activado con un botón `⋮`
    - Debe tener las opciones:
      - "Ver detalle"
        - Abre un modal con la traza completa del error.
      - "Marcar como resuelto"
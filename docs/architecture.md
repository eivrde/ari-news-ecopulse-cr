\# 📐 Arquitectura del Flujo de Nodos (Google Opal)

El sistema \*\*ARI NEWS: EcoPulse CR\*\* está estructurado mediante una arquitectura distribuida de 7 nodos interconectados dentro del entorno de \*\*Google Opal\*\*, que abarcan desde la captura de variables de usuario hasta la búsqueda fundamentada (\*grounded search\*), la generación conceptual de imágenes y el renderizado web final.

\---

\#\# 🗺️ Diagrama General del Flujo

\`\`\`text  
┌──────────────┐  
│  1\. Sector   │─────┐  
└──────────────┘     │  
┌──────────────┐     │     ┌────────────────────────────────┐  
│  2\. Region   │─────┼────\>│ 7\. Hero Image Generator        │─────┐  
└──────────────┘     │     │    (Image Generation)          │     │  
┌──────────────┐     │     └────────────────────────────────┘     │  
│   3\. Date    │─────┤                                            │  
└──────────────┘     │                                            │  
┌──────────────┐     │     ┌────────────────────────────────┐     │     ┌────────────────────────────────┐  
│ 4\. Quantity  │─────┴────\>│ 6\. Fetch News Articles         │─────┴────\>│ 5\. Render News Cards           │  
└──────────────┘           │    (Grounded Search & Text)    │           │    (Webpage / HTML Render)     │  
                           └────────────────────────────────┘           └────────────────────────────────┘  
\`\`\`

\---

\#\# 🧩 Descripción Detallada de los 7 Nodos

\#\#\# 1\. Sector (User Input Node)  
\* \*\*Tipo:\*\* Entrada de Usuario (Dropdown / Selector).  
\* \*\*Función:\*\* Captura la vertical de negocio o tema ambiental seleccionado por el usuario.  
\* \*\*Opciones disponibles:\*\* \*Energías Renovables\*, \*Biotecnología\*, \*Movilidad Eléctrica\*, \*Economía Circular\*, \*Agricultura Sostenible\*.  
\* \*\*Conexiones de Salida:\*\*  
  \* Al \*\*Nodo 6 (Fetch News Articles)\*\* para filtrar los temas de búsqueda.  
  \* Al \*\*Nodo 7 (Hero Image Generator)\*\* para contextualizar la generación de la imagen principal.  
  \* Al \*\*Nodo 5 (Render News Cards)\*\* para mostrar la etiqueta informativa en la cabecera.

\#\#\# 2\. Region (User Input Node)  
\* \*\*Tipo:\*\* Entrada de Usuario (Texto / Selector).  
\* \*\*Función:\*\* Define la delimitación geográfica para el filtrado de noticias.  
\* \*\*Opciones principales:\*\* \*Costa Rica\*, \*América Latina\*, \*Global\*.  
\* \*\*Conexiones de Salida:\*\*  
  \* Al \*\*Nodo 6 (Fetch News Articles)\*\* para acotar la búsqueda geográfica.  
  \* Al \*\*Nodo 5 (Render News Cards)\*\* para mostrar la insignia geográfica en la cabecera.

\#\#\# 3\. Date (User Input Node)  
\* \*\*Tipo:\*\* Entrada de Usuario (Texto / Fecha).  
\* \*\*Función:\*\* Establece la fecha límite o de corte para asegurar la actualidad de las publicaciones.  
\* \*\*Formato exigido:\*\* \`AAAA-MM-DD\` (ej. \`2026-10-08\`).  
\* \*\*Conexiones de Salida:\*\*  
  \* Al \*\*Nodo 6 (Fetch News Articles)\*\* como parámetro estricto de filtrado temporal.  
  \* Al \*\*Nodo 5 (Render News Cards)\*\* para la metainformación de la sesión.

\#\#\# 4\. Quantity (User Input Node)  
\* \*\*Tipo:\*\* Entrada de Usuario (Número / Slider).  
\* \*\*Función:\*\* Controla dinámicamente la cantidad de tarjetas de noticias que deben buscarse y mostrarse en el carrusel.  
\* \*\*Rango:\*\* Mínimo \`3\` a máximo \`10\` noticias.  
\* \*\*Conexiones de Salida:\*\*  
  \* Al \*\*Nodo 6 (Fetch News Articles)\*\* para indicar cuántos artículos procesar.  
  \* Al \*\*Nodo 5 (Render News Cards)\*\* para calcular la estructura e índices del carrusel (\`01 / N\`).

\#\#\# 5\. Fetch News Articles (Grounded Search Node)  
\* \*\*Tipo:\*\* Generación de Texto con Búsqueda Conectada (\*Google Search Grounding\*).  
\* \*\*Entradas Recibidas:\*\*  
  \* \`Sector\` (Nodo 1\)  
  \* \`Region\` (Nodo 2\)  
  \* \`Date\` (Nodo 3\)  
  \* \`Quantity\` (Nodo 4\)  
\* \*\*Función:\*\* Realiza la búsqueda web de noticias en tiempo real, filtra resultados veraces y recientes en español, y sintetiza la información estructurada por noticia (Título, Fuente, Fecha, Resumen de impacto).  
\* \*\*Conexión de Salida:\*\*  
  \* Al \*\*Nodo 5 (Render News Cards)\*\* enviando los datos procesados en la variable \`\[news\_data\]\`.

\#\#\# 6\. Hero Image Generator (Image Generation Node)  
\* \*\*Tipo:\*\* Generador de Imagen Multimodal (Imagen / Gemini).  
\* \*\*Entrada Recibida:\*\*  
  \* \`Sector\` (Nodo 1\)  
\* \*\*Función:\*\* Crea un banner conceptual y abstracto en orientación horizontal (pantalla ancha) optimizado para la cabecera del dashboard. Sigue la paleta \*Charcoal, Blanco Puro y Verde Esmeralda\*, omitiendo estrictamente cualquier texto visible en la imagen.  
\* \*\*Conexión de Salida:\*\*  
  \* Al \*\*Nodo 5 (Render News Cards)\*\* enviando el recurso visual en la variable \`\[hero\_image\]\`.

\#\#\# 7\. Render News Cards (Webpage / HTML Render Node)  
\* \*\*Tipo:\*\* Renderizador Web Ejecutable (\`iframe\` interactivo HTML5/CSS3/JS).  
\* \*\*Entradas Recibidas:\*\*  
  \* \`hero\_image\` (Nodo 7\)  
  \* \`news\_data\` (Nodo 6\)  
  \* \`Sector\` (Nodo 1\)  
  \* \`Region\` (Nodo 2\)  
  \* \`Date\` (Nodo 3\)  
  \* \`Quantity\` (Nodo 4\)  
\* \*\*Función:\*\* Es el nodo compilador final. Integra la imagen conceptual, inyecta las noticias en tarjetas interactivas con scroll horizontal, habilita el conmutador de \*\*Modo Claro / Modo Oscuro\*\*, formatea dinámicamente las URLs seguras en slugs de Google Search (\`target="\_blank"\`) y renderiza el footer institucional.

\---

\#\# 🔄 Flujo de Datos y Conexiones Lógicas

1\. El usuario interactúa con los \*\*Nodos 1 a 4\*\* seleccionando los parámetros deseados.  
2\. Los \*\*Nodos 6 y 7\*\* ejecutan sus procesos en paralelo:  
   \* El \*\*Nodo 6\*\* consulta la web y formatea las noticias en español.  
   \* El \*\*Nodo 7\*\* sintetiza el banner visual basado en la vertical temática.  
3\. El \*\*Nodo 5\*\* recibe todas las salidas, construye el DOM interactivo y despliega la aplicación web lista para el usuario.  

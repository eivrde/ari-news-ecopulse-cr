\# 🎨 Guía del Sistema de Diseño (Design System)  
\> \*\*ARI NEWS: EcoPulse CR\*\* — \*Estética Premium Sustainable Editorial\*

Este documento establece los lineamientos visuales, la estructura tipográfica, el comportamiento adaptativo (\*responsive\*) y las especificaciones de interfaz implementadas en la solución.

\---

\#\# 🎨 Paleta de Colores y Tokens CSS

La interfaz utiliza variables CSS personalizadas para gestionar el contraste y los temas (\*Light/Dark Mode\*) sin necesidad de recargar el navegador.

\#\#\# ☀️ Modo Claro (Light Mode)  
\* \*\*Fondo Principal (\`--bg-primary\`):\*\* \`\#F8FAFC\` (Gris neutro de tono frío para reducir la fatiga visual).  
\* \*\*Superficie de Tarjetas (\`--card-bg\`):\*\* \`\#FFFFFF\` (Blanco puro para destacar las noticias).  
\* \*\*Texto Principal (\`--text-primary\`):\*\* \`\#0F172A\` (Charcoal / Grafito profundo).  
\* \*\*Texto Secundario (\`--text-secondary\`):\*\* \`\#64748B\` (Gris medio para fuentes, fechas y metadatos).  
\* \*\*Acento Principal (\`--accent-color\`):\*\* \`\#059669\` (Verde Esmeralda Sostenible).  
\* \*\*Bordes / Divisores (\`--border-color\`):\*\* \`\#E2E8F0\` (Gris claro).

\#\#\# 🌙 Modo Oscuro (Dark Mode)  
\* \*\*Fondo Principal (\`--bg-primary\`):\*\* \`\#0F172A\` (Charcoal profundo).  
\* \*\*Superficie de Tarjetas (\`--card-bg\`):\*\* \`\#1E293B\` (Slate oscuro para capas de información).  
\* \*\*Texto Principal (\`--text-primary\`):\*\* \`\#F8FAFC\` (Blanco suave de alto contraste).  
\* \*\*Texto Secundario (\`--text-secondary\`):\*\* \`\#94A3B8\` (Gris claro tenue).  
\* \*\*Acento Principal (\`--accent-color\`):\*\* \`\#10B981\` (Verde Esmeralda Vibrante para destacar en fondos oscuros).  
\* \*\*Bordes / Divisores (\`--border-color\`):\*\* \`\#334155\` (Slate medio).

\---

\#\# 📱 Diseños y Comportamiento Responsive

El diseño adopta un enfoque \*\*Mobile-First\*\* con ajustes progresivos para tablets y pantallas de escritorio.

\* \*\*Espaciado y Padding:\*\* Mantenimiento de márgenes exteriores uniformes (mínimo \`16px\` en móvil, \`32px\` en escritorio) para asegurar que el contenido no colisione con los bordes de la pantalla.  
\* \*\*Componentes Flexibles:\*\*  
  \* La cabecera (\*Header\*) reorganiza los distintivos (\*badges\*) y el conmutador de tema mediante \`flex-wrap: wrap;\`.  
  \* La imagen de portada (\*Hero Image\*) mantiene un marco con radio de curvatura (\`border-radius: 8px\`) y proporción horizontal constante.

\---

\#\# 🎠 Carrusel y Navegación Horizontal

El carrusel de noticias aprovecha las propiedades nativas de CSS3 para lograr un desplazamiento fluido en pantallas táctiles y con ratón:

\* \*\*Contenedor Principal:\*\*  
  \`\`\`css  
  display: flex;  
  overflow-x: auto;  
  scroll-snap-type: x mandatory;  
  gap: 24px;  
  padding-bottom: 16px;  
  \`\`\`  
\* \*\*Alineación de Tarjetas:\*\*  
  \* Propiedad en tarjeta: \`scroll-snap-align: start;\`  
  \* Ancho en escritorio: \`flex: 0 0 340px;\`  
  \* Ancho en móviles: \`flex: 0 0 85vw;\`  
\* \*\*Barra de Desplazamiento Personalizada (\`::-webkit-scrollbar\`):\*\*  
  \* Altura/Grosor: \`6px\`.  
  \* Relleno (\*Track\*): Transparente o adaptado al color de fondo.  
  \* Tirador (\*Thumb\*): Color del acento esmeralda con opacidad suave para una interacción discreta.

\---

\#\# 🌓 Switch de Modo Claro / Modo Oscuro

La conmutación de temas se ejecuta mediante JavaScript (\*Vanilla JS\*) aplicando o removiendo la clase \`.dark-mode\` en el elemento raíz (\`\<body\>\` o \`\<html\>\`):

1\. \*\*Interacción:\*\* El usuario acciona el interruptor en la esquina superior derecha.  
2\. \*\*Transición Suave:\*\* Se aplica la regla CSS \`transition: background-color 0.3s ease, color 0.3s ease;\` para evitar saltos bruscos de brillo.  
3\. \*\*Persistencia Visual:\*\* Todos los elementos (tarjetas, distintivos, barra de desplazamiento y pie de página) adaptan dinámicamente sus tokens de color.  

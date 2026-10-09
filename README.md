# 🌿 ARI NEWS: EcoPulse CR

> **Green Business Intelligence & Sustainability Dashboard**  
> *Desarrollado en Google Opal para la inmersión ONE AI For Business (2026).*

![ARI News Banner](docs/dashboard-dark.png)

---

## 📌 Descripción del Proyecto

**ARI NEWS: EcoPulse CR** es un dashboard web interactivo diseñado para actuar como un radar táctico de inteligencia verde para negocios. La plataforma procesa búsquedas de noticias en tiempo real sobre sostenibilidad, energías limpias e innovación ambiental, presentando la información bajo una interfaz con estética **Premium Sustainable Editorial**.

El proyecto combina lógica de inteligencia artificial generativa, arquitectura de nodos en **Google Opal** y principios de desarrollo **Front-End** y **Diseño Gráfico** para ofrecer una experiencia de usuario limpia, responsiva y adaptable.

---

## ⚙️ Características Clave

* 🎛️ **Inputs Configurables:** Permite personalizar la búsqueda por Sector (*Energías Renovables, Biotecnología, Movilidad Eléctrica, Economía Circular, Agricultura Sostenible*), Región (*Costa Rica, América Latina, Global*), Fecha de corte (`AAAA-MM-DD`) y Cantidad de noticias (3 a 10).
* 🖼️ **Generación de Imagen Hero (Nodo 7):** Banner conceptual abstracto creado con IA según el sector seleccionado, sin texto visible.
* 🌓 **Modo Claro / Modo Oscuro:** Switch interactivo en JavaScript que conmuta paletas de colores, tarjetas, scrollbars y contraste sin recargar la página.
* 📱 **Layout Responsive & Scroll Horizontal:** Navegación fluidizada mediante carrusel CSS (`scroll-snap`) pensado para escritorios y dispositivos móviles.
* 🔗 **Formateo Seguro de URLs:** Generación dinámica de slugs para redirigir a búsquedas seguras en Google en pestañas independientes (`target="_blank"`).

---

## 🛠️ Tecnologías y Herramientas

* **Plataforma AI:** [Google Opal](https://opal.google/) (Workflow de Nodos Multimodal)
* **Modelos & Grounding:** Gemini / Google Search Grounding & Imagen Generation
* **Front-End:** HTML5, CSS3 (Flexbox, Variables CSS, Webkit Scrollbars), JavaScript (Vanilla JS ES6)
* **Diseño UI/UX:** Paleta Charcoal (`#0F172A`), Pure White (`#FFFFFF`) y Emerald Accent (`#059669` / `#10B981`)

---

## 📐 Arquitectura del Flujo (Opal Workflow)

El sistema opera mediante una arquitectura distribuida de nodos en Google Opal:

```text
[Sector] ────────+───> [Nodo 7: Hero Image Generator] ─────+
[Region] ────────|                                         |
[Date] ──────────+───> [Fetch News Articles] ────────────> [Render News Cards]
[Quantity] ──────┘
```

---

## 👤 Autora

* **Keisy Valverde** — *Front-End Developer & Visual Designer*
* Proyecto presentado para la inmersión **ONE AI For Business** (2026).

---

## 🙏 Agradecimientos

[![Oracle](https://img.shields.io/badge/Oracle-F80000?style=for-the-badge&logo=oracle&logoColor=white)](https://github.com/oracle)
[![Alura](https://img.shields.io/badge/Alura_Latam-0070F3?style=for-the-badge&logo=codecademy&logoColor=white)](https://github.com/alura-es)

Mi más sincero agradecimiento a **Alura Latam** y **Oracle** por impulsar el programa **ONE (Oracle Next Education)** y brindar este espacio de aprendizaje continuo. Gracias a su compromiso con la educación tecnológica, pude explorar el potencial de los agentes de Inteligencia Artificial para negocios y desarrollar este proyecto.

---

## 📬 Contacto

¿Tienes preguntas o sugerencias sobre el proyecto? Puedes contactarme por aquí:

- **Autora:** Keisy Valverde Amador
- **GitHub:** [@eivrde](https://github.com/eivrde)
- **LinkedIn:** [Keisy Valverde](https://www.linkedin.com/in/eivalverde/)
- **Email:** [eivalverdea@outlook.com](mailto:eivalverdea@outlook.com)

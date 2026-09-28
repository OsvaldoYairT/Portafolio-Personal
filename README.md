# Portafolio Personal - Osvaldo Torres

Sitio web estático que presenta los servicios de desarrollo web, sistemas y
automatización de Osvaldo Torres, dirigido a pequeñas y medianas empresas.

No hay proceso de compilación ni dependencias que instalar: el sitio se abre
directamente en el navegador o se sirve con cualquier servidor estático.

---

## Estructura del proyecto

```
.
├── index.html          # Pagina principal en español
├── index-en.html       # Version en ingles
├── css/
│   ├── bootstrap.min.css
│   ├── font-awesome.min.css
│   └── style.css       # Estilos propios del sitio (unico CSS cargado por las paginas)
├── js/
│   ├── jquery.min.js
│   ├── bootstrap.min.js
│   ├── jquery.countTo.min.js
│   ├── jquery.easing.min.js
│   ├── jquery.shuffle.min.js
│   ├── slick.min.js
│   ├── touchswipe.min.js
│   └── script.js       # Logica propia: navegacion, contadores, carrusel y filtros
├── img/                # Imagenes usadas por las paginas
├── docs/               # Plan de mejoras por fases
├── assets/             # Copia antigua sin usar, ver "Pendientes"
└── README.md
```

Las dos paginas son estructuralmente identicas: cualquier cambio en
`index.html` debe replicarse en `index-en.html` y viceversa.

---

## Secciones del sitio

El orden esta pensado para un recorrido de venta:

1. **Portada** - cargo, propuesta de valor y llamadas a la accion.
2. **Servicios** - oferta principal (desarrollo web, sistemas y bases de datos,
   automatizacion e integracion) y servicios complementarios (soporte y
   mantenimiento, contenido visual, redes sociales). Cada servicio indica para
   quien es, que incluye y como solicitarlo.
3. **Trabajos** - 11 proyectos filtrables. Cada tarjeta abre una ficha con
   cliente, descripcion, problema, solucion, tecnologias y, cuando existe, un
   enlace a la demo.
4. **Empresas** - logos de clientes y agencias.
5. **Contadores** - cifras de experiencia.
6. **Principios de trabajo** - como se trabaja.
7. **Equipo** - colaborador con autorizacion para aparecer.
8. **Acerca de** - biografia.
9. **Tecnologias y herramientas** - stack tecnologico.
10. **Historia** - trayectoria profesional, como respaldo.
11. **Contacto** - correo, formulario e indicacion de que datos conviene enviar.

---

## Como verlo en local

Abrir `index.html` directamente funciona, pero para probar los enlaces y el
formulario conviene servirlo:

```bash
# Con Python
python -m http.server 8000

# O con Node
npx serve .
```

Luego abrir `http://localhost:8000`.

---

## Personalizacion

| Que cambiar | Donde |
|---|---|
| Nombre, cargo y textos del encabezado | `index.html` y `index-en.html`, bloque `#top` |
| Servicios y sus detalles | Seccion `#services` |
| Proyectos y fichas | Seccion `#works` y los modales `portfolioItem*` |
| Colores y espaciados | `css/style.css` (color principal `#196fc2`) |
| Correo de contacto | Buscar `osvaldoyts20@gmail.com` en ambas paginas |
| Formulario | Enlace a Google Forms en la seccion `#contact` |
| Metadatos de redes | Bloque Open Graph en el `<head>` de ambas paginas |

Al agregar un proyecto hay que crear la tarjeta **y** su modal, y el `id` del
modal debe coincidir con el `data-target` de la tarjeta.

---

## Reglas del proyecto

- No inventar precios, metricas, testimonios, resultados ni disponibilidad.
- Todo lo publicado debe poder respaldarse con evidencia real.
- Mantener el sitio estatico. No agregar backend, CMS, pagos ni cambiar de
  framework sin una necesidad concreta.
- Cualquier contenido visible en `index.html` debe existir tambien en
  `index-en.html`.

---

## Accesibilidad

- Enlace de salto al contenido principal en ambas paginas.
- Foco de teclado visible mediante `:focus-visible` (el tema base eliminaba el
  indicador de foco con `outline: 0`).
- Todos los enlaces que solo contienen un icono tienen `aria-label`.
- Los enlaces que abren en pestaña nueva usan `rel="noopener noreferrer"`.
- Las imagenes decorativas usan `alt=""`; las informativas describen su
  contenido.

---

## Publicacion

El repositorio esta en `github.com/OsvaldoYairT/Portafolio-Personal` y se
publica con GitHub Pages. La URL base es:

```
https://osvaldoyairt.github.io/Portafolio-Personal/
```

La version en ingles queda en `index-en.html` dentro de la misma ruta.

---

## Pendientes

- Confirmar la configuracion de la rama de publicacion de GitHub Pages: el
  repositorio no tiene rama `gh-pages` ni flujo de trabajo, y la rama activa
  localmente es `develop` mientras `origin/HEAD` apunta a `master`.
- Falta una imagen de vista previa de 1200x630 px para Open Graph. No hay
  ninguna captura del sitio en `img/`.
- `assets/` es una copia antigua sin referencias desde las paginas (61
  archivos, ~5.16 MB). Se conserva por decision del autor, pero se puede
  eliminar.
- Las imagenes no usan `loading="lazy"`, lo que penaliza la carga inicial.
- Falta un texto alternativo para `img/client-6.png`: se desconoce a qué
  empresa corresponde ese logo.

---

## Contacto

Osvaldo Torres - `osvaldoyts20@gmail.com`

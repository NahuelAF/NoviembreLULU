# 🎃 Feliz Halloween, mi amor

Una página web romántica con temática de Halloween, pensada para regalarle una carta a tu pareja. Es un único archivo HTML, sin dependencias ni proceso de compilación.

## Cómo funciona la experiencia

1. **Inicio:** luna brillante, título y un botón "Entrar a la noche". Al pulsarlo empieza la música.
2. **Escena:** luna de fondo, árboles secos, lápidas, niebla, luciérnagas, una pareja abrazada y tres calabazas en el suelo.
3. **Calabazas:** al tocar cada una se enciende con su brillo y suena una nota distinta.
4. **Fantasmita:** al encender las tres, cada una lanza una estela que se junta en el centro y forma un fantasmita que dice "¡Tienes un mensaje!".
5. **Sobre:** al tocarlo se rompe el sello, la carta sale y se abre en el centro de la pantalla.
6. **Guardar la carta:** vuelve al sobre y este se cierra. Se puede releer cuantas veces quieras.

## Archivos

| Archivo | Descripción |
|---|---|
| `halloween-amor.html` | La página completa (HTML, CSS y JavaScript en un solo archivo) |
| `README.md` | Este documento |

## Personalizar el mensaje

Abre `halloween-amor.html` y busca el objeto `CARTA` al principio del bloque `<script>`:

```js
const CARTA = {
  para: "mi amor",
  mensaje: [
    "Primer párrafo de tu carta…",
    "Segundo párrafo…",
    "Tercer párrafo…"
  ],
  firma: "Tu monstruito favorito 🧡"
};
```

- `para`: nombre o apodo. Aparece en el título del inicio y en el encabezado de la carta.
- `mensaje`: lista de párrafos. Puedes añadir o quitar los que quieras, cada uno aparece con una animación escalonada.
- `firma`: la despedida, alineada a la derecha.

Si cambias el nombre, actualiza también el `<title>` y las etiquetas `og:title` del `<head>`.

## Personalizar el aspecto

Los colores principales están en variables CSS al inicio de la hoja de estilos:

```css
--bg:#160a2e;   /* cielo, parte alta */
--bg2:#2b1150;  /* cielo, parte media */
--org:#ff8a1f;  /* naranja de calabazas y títulos */
--cream:#f8ecd0;/* papel de la carta */
--ink:#3b1f12;  /* tinta de la carta */
```

Otros ajustes útiles:

- **Tipografías:** Creepster (títulos), Caveat (texto de la carta) y Quicksand (interfaz). Se cargan desde Google Fonts y tienen alternativas del sistema si no hay conexión.
- **Tiempos de la secuencia:** en la función `summon()` están las pausas de las estelas y del fantasmita. En `openLetter()` está la espera antes de que salga la carta (1500 ms).
- **Notas de las calabazas:** objeto `notes` (`p1`, `p2`, `p3`) con números de nota MIDI.

## Música

La música de fondo se genera en el navegador con la Web Audio API, así que no hay archivos de audio. Es una melodía tipo cajita de música en La menor con un zumbido grave de fondo.

- Los acordes están en `CH` y la melodía en `ML`. El ritmo está en `nextT += .55`.
- El botón de arriba a la derecha la silencia o la reactiva.
- La música solo puede empezar después de un toque del usuario, por eso arranca con el botón "Entrar". Es una restricción de los navegadores.
- Se pausa sola si cambias de pestaña.

## Publicarla

Como es un solo archivo, funciona en cualquier alojamiento estático:

1. Renombra `halloween-amor.html` a `index.html`.
2. Súbelo a GitHub Pages, Netlify, Vercel o Cloudflare Pages. En Netlify basta con arrastrar el archivo en Netlify Drop.
3. Comparte el enlace por WhatsApp, mensaje o código QR.

## SEO y redes sociales

La página ya incluye:

- `lang="es"`, título y meta descripción.
- Etiquetas Open Graph y Twitter para la vista previa al compartir el enlace.
- `theme-color` para la barra del navegador en móvil.
- Estructura semántica (`header`, `main`, encabezados) y textos alternativos para lectores de pantalla.

Una vez publicada con su dirección definitiva, conviene añadir en el `<head>`:

```html
<link rel="canonical" href="https://tu-dominio.com/">
<meta property="og:url" content="https://tu-dominio.com/">
<meta property="og:image" content="https://tu-dominio.com/preview.jpg">
```

La imagen de vista previa (`preview.jpg`, de unos 1200×630 px) no está incluida.

## Responsive y accesibilidad

- Diseñada primero para móvil. La escena se ajusta a cualquier pantalla y respeta las zonas seguras de iPhone.
- Zonas táctiles grandes en calabazas, sobre y botones.
- Se puede usar con teclado: `Tab` para moverse, `Enter` o `Espacio` para encender calabazas y abrir el sobre, `Esc` para guardar la carta.
- Respeta la preferencia del sistema de reducir movimiento.

## Compatibilidad

Funciona en las versiones actuales de Chrome, Edge, Firefox y Safari (iOS 14.5 o superior). Si el navegador es muy antiguo, los murciélagos y algunas animaciones pueden no verse igual.

## Créditos

Todo el dibujo (siluetas, calabazas, fantasma, sobre) está hecho con SVG y CSS, y el sonido con la Web Audio API. Solo se usan las tipografías de Google Fonts mencionadas arriba.

Hecho con 🧡 para una noche de Halloween.

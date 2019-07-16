# Icons
--------

Los iconos que estaremos usando son SVG y provienen de [Feather Icons](https://feathericons.com/).

?> **Nota:** Los iconos son básicos, pero si se requiere uno especifico, se busca.

## ¿Como usar los iconos en HTML?

1. Descargar el icono de [Feather Icons](https://feathericons.com/).
2. Usar la herramienta para comprimir el SVG, [SVGOMG](https://jakearchibald.github.io/svgomg/)
3. Agregar `viewBox="0 0 24 24"` a la etiqueta `svg`, con el fin de que conserve su aspecto y ratio.

## Ejemplo: {docsify-ignore}

```html
<svg xmlns="http://www.w3.org/2000/svg"
    viewBox="0 0 24 24" width="16" height="16" fill="none"
    stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
    class="feather feather-plus">
    <path d="M12 5v14M5 12h14" />
</svg>
```
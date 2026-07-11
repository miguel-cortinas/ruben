# Diseño de Ajustes: Mapa y Animación

## Resumen
Simplificar el diseño temporalmente removiendo animaciones para enfocarnos en la maquetación estática, y mejorar la limpieza de la interfaz reemplazando el mapa interactivo grande por un botón de acción directo.

## 1. Eliminación de Animaciones
- **Objetivo**: Hacer la imagen `centro.png` estática.
- **Acción**: Eliminar o comentar la animación de entrada de GSAP (slide-up y opacidad) y desactivar el efecto Parallax que responde al movimiento del mouse.

## 2. Reemplazo del Mapa por un Botón
- **Objetivo**: Eliminar el bloque del `iframe` de Google Maps (`.event-map`) que ocupa mucho espacio visual.
- **Acción**: En la celda de la dirección ("Granja Las Flechas"), añadir un botón interactivo que enlace a Google Maps.

### Opciones de Diseño para el Botón:

**Opción A (Recomendada): Botón "Brutalista" Sólido**
- Fondo azul vibrante (`var(--red)` que ahora es `#3B00FF`).
- Texto blanco.
- Borde negro grueso y sombra dura negra (sombra brutalista).
- Icono de pin de ubicación en formato SVG.
- *Por qué lo recomiendo*: Sigue el estilo editorial y llamativo del resto del póster, manteniendo la jerarquía de un botón de llamada a la acción (CTA) fuerte.

**Opción B: Botón Contorneado (Ghost Button)**
- Fondo transparente.
- Texto azul.
- Borde negro grueso.
- Icono SVG.
- *Trade-off*: Es más sutil y le quita peso visual a la sección de la dirección, pero podría confundirse con una etiqueta en lugar de un botón clickeable si los usuarios leen rápido.

## Cambios a Nivel de Código
1. **HTML**: Borrar el `div.event-map`. Modificar el contenido de `.event-address-value` para incluir el tag `<a>` del botón.
2. **CSS**: Añadir la clase `.btn-maps` con los tokens de diseño ya existentes (`--border-thick`, `--sh-sm`, etc.).
3. **JS**: Eliminar el script de GSAP vinculado a `.photo-centro` y el *Event Listener* de *mousemove* de `.collage-section`.

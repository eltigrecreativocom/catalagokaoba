# Catálogo Kaoba - Guía Rápida

Este proyecto es un catálogo digital tipo flipbook. Aquí aprenderás cómo agregar nuevas imágenes de páginas y miniaturas.

## Estructura de Carpetas

- `imagenes/` — Contiene las imágenes de las páginas del catálogo (por ejemplo, `1.jpg`, `2.jpg`, ...).
- `miniaturas/` — Contiene las miniaturas que se muestran en la barra de navegación (por ejemplo, `min-01.jpg`, `min-02.jpg`, ...).


## Cómo agregar imágenes de páginas

### Opción 1: Manualmente en el HTML

Abre el archivo `index.html` y dentro del `<div id="flipbook" class="ui-flipbook">` agrega tus imágenes así:

```html
<div id="flipbook" class="ui-flipbook">
		<!-- Aquí van las imágenes de las páginas -->
		<img src="imagenes/ca-01.jpg" alt="Página 1">
		<img src="imagenes/ca-02.jpg" alt="Página 2">
		<!-- ...y así sucesivamente -->
</div>
```

### Opción 2: Automáticamente con JavaScript (recomendado si tienes muchas páginas)

Puedes generar las imágenes automáticamente con un bucle. Por ejemplo, agrega este script antes de cerrar el `</body>` en tu `index.html`:

```html
<script>
	const flipbook = document.getElementById('flipbook');
	for(let i=1; i<=15; i++) {
		const img = document.createElement('img');
		img.src = `imagenes/ca-${i.toString().padStart(2, '0')}.jpg`;
		img.alt = `Página ${i}`;
		flipbook.appendChild(img);
	}
</script>
```

Así no tienes que escribir cada `<img>` a mano.

## Cómo agregar miniaturas

Coloca las miniaturas en la carpeta `miniaturas/` y nómbralas igual que las páginas pero con el prefijo `min-` y dos dígitos, por ejemplo: `min-01.jpg`, `min-02.jpg`, etc.

## Relación entre imágenes y miniaturas

- La miniatura `min-01.jpg` corresponde a la página `ca-01.jpg`.
- La miniatura `min-02.jpg` corresponde a la página `ca-02.jpg`.
- Y así sucesivamente.

## Recomendaciones

- Usa imágenes optimizadas para web (JPG o PNG).
- Si agregas o quitas páginas, actualiza también las miniaturas.
- Si cambias la cantidad de páginas, ajusta el bucle o el HTML según corresponda.

## Vista previa

Abre `index.html` en tu navegador para ver el catálogo funcionando.

---

¿Dudas o problemas? Contacta al desarrollador.

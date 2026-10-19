# Dota 2 Atlas

Proyecto estático independiente del vault de Obsidian. Escribir documentación y contenido en español.

## Estructura y diseño

- Publicar únicamente `site/`.
- Mantener el diseño Órbita, Geist, cifras de ancho tabular, firma novem en Allura y formato de impresión 16:9.
- `site/index.html` contiene actualmente datos y presentación juntos. Separarlos es una mejora pendiente.
- No usar la exploración de `archive/` como fuente de cifras actuales.
- No agregar dependencias o un framework sin una necesidad concreta.

## Actualización de datos

Seguir `docs/MANTENIMIENTO.md`. Consultar fuentes actuales cuando se solicite actualizar; no asumir que el parche del HTML sigue vigente.

Identificar el último parche estable con Valve y registrar fecha, enlaces y revisiones de fuentes. Leer los cambios generales completos entre la última revisión y el parche objetivo; una búsqueda por nombre puede omitir cambios relevantes.

Distinguir datos verificados, estimaciones y pendientes. Un archivo extraído puede contener valores base modificados por reglas del motor. No declarar toda la guía validada porque se haya revisado una parte.

Conservar el snapshot publicado ante fallos de fuentes. No inventar cifras ni actualizar la fecha de revisión como si todos los datos se hubieran comprobado.

## Verificación

Para cambios de datos, comprobar fórmulas y límites afectados. Para oleadas revisar 0:00, 2:00, 5:00, 5:30, 15:00, 30:00, 30:30, 35:00, 40:00, 45:00 y 60:00.

Si cambia la lámina, revisar en navegador, impresión a PDF de una sola página 16:9 y PNG final de 2560 × 1440. Mantener sincronizadas guía y exportación.

No publicar remotos, elegir una licencia del producto ni crear organizaciones salvo autorización del usuario.

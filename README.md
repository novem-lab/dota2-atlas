# Dota 2 Atlas

Guía visual de economía, creeps, experiencia y objetivos de Dota 2, hecha por **novem**. Incluye una lámina 16:9, guía con búsqueda y filtros, simulador de oleadas y calculadora de buyback.

## Estado

Base local preparada para GitHub Pages. La versión importada conserva el diseño **Órbita**, Geist con números tabulares y la firma Allura.

La guía declara como referencia el parche **7.41f** y una revisión del **18/10/2026**. Esta migración conserva el contenido; no constituye una nueva verificación de todas las cifras ni confirma que ese parche siga siendo el último disponible.

Las actualizaciones de datos todavía son manuales. La detección periódica con GitHub Actions es una mejora propuesta; no hay un proceso automático instalado.

## Estructura

- `site/index.html`: web autónoma con estilos, fuentes y JavaScript incorporados.
- `site/downloads/dota2-economia-1440p.png`: lámina de 2560 × 1440.
- `site/fonts/`: licencias de las fuentes.
- `archive/Dota-2-Estilos.html`: exploración de diseño anterior, con datos históricos. No se publica.
- `docs/MANTENIMIENTO.md`: fuentes y procedimiento de actualización.
- `.github/workflows/pages.yml`: publicación de la carpeta `site/`.

No requiere npm, compilación ni backend.

## Vista local

Abrí `site/index.html` directamente o ejecutá desde la raíz:

```sh
python3 -m http.server 8080 --directory site
```

Después visitá `http://localhost:8080`.

## Publicar en GitHub Pages

1. Creá un repositorio llamado `dota2-atlas` en tu cuenta o en tu organización. Con GitHub Free, Pages requiere un repositorio público.
2. Subí este proyecto a la rama `main`. Si ya creaste archivos remotos, integrá ese historial antes de hacer push.
3. En **Settings → Pages → Build and deployment → Source**, elegí **GitHub Actions**.
4. Ejecutá **Publicar en GitHub Pages** desde **Actions → Run workflow**, o hacé un nuevo push a `main`.

El workflow publica solamente `site/`. La dirección habitual será `https://ORGANIZACION.github.io/dota2-atlas/`; reemplazá ORGANIZACION por el nombre elegido. No hay una organización, remoto ni sitio creado por esta preparación local.

Referencia: [workflows de Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages).

## Actualizar la guía

Seguí [Mantenimiento](docs/MANTENIMIENTO.md). Podés pedirle al asistente:

> Actualizá Dota 2 Atlas al último parche estable de Valve. Identificá el parche y revisá las cifras afectadas con fuentes enlazadas y revisiones fijadas. Informá qué verificaste y qué sigue pendiente. Conservá el diseño Órbita, los números tabulares y la firma novem. Regenerá el PNG si cambia la lámina.

## Autoría y licencias

Autor: **novem**. La licencia del código y del contenido propio está pendiente de elección; no se agregó una licencia abierta por defecto. Los datos y nombres de Dota 2 y las fuentes tipográficas tienen sus propios titulares y condiciones.

Geist, Allura, Manrope y Space Grotesk proceden de Google Fonts; sus avisos SIL Open Font License se conservan en `site/fonts/`. Manrope y Space Grotesk se utilizan en la exploración archivada.

Que un repositorio sea público no determina por sí solo todos los permisos de reutilización. [Documentación de licencias de GitHub](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository).

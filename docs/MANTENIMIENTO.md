# Mantenimiento de Dota 2 Atlas

## Fuentes y alcance

| Fuente | Uso | Precaución |
|---|---|---|
| [Parches oficiales de Valve](https://www.dota2.com/patches) | Identificar cambios de reglas y parche objetivo. | Las notas describen cambios; no son una base completa del estado actual. |
| [Listado de parches de Valve](https://www.dota2.com/datafeed/patchnoteslist?language=english) | Posible detección de una nueva versión. | Endpoint del sitio; no asumir un contrato estable ni ordenar versiones alfabéticamente. |
| [dotabuff/d2vpkr](https://github.com/dotabuff/d2vpkr) | Contrastar valores de archivos extraídos del juego. | Fuente comunitaria; fijar commit. Los valores base pueden ser alterados por reglas del motor. |
| [OpenDota dotaconstants](https://github.com/odota/dotaconstants) | Contrastar tablas, por ejemplo XP por nivel. | Fuente comunitaria con datos generados y manuales. Fijar revisión y comprobar vigencia. |
| [Liquipedia: neutrales](https://liquipedia.net/dota2/Neutral_Creeps) | Explicaciones y contraste de campamentos. | Fuente comunitaria. Respetar condiciones de acceso y atribución; no consultar desde cada visita a la web. |
| Cliente de Dota 2 | Reproducir una mecánica ante contradicciones. | Registrar parche y procedimiento. Una prueba aislada no verifica toda la guía. |

La guía importada enlaza `npc_units.txt` en el commit `4c0b3dc12ff027e70c5faa4ffd447a1b52a425ed` de d2vpkr. Es un antecedente, no una garantía de vigencia para un parche nuevo.

## Procedimiento manual

1. Identificar el último parche estable de Valve y la fecha de consulta.
2. Guardar la versión de partida y revisar todas las notas intermedias, incluidas las secciones generales.
3. Enumerar los campos afectados y contrastarlos con fuentes fijadas por commit o revisión.
4. Resolver discrepancias con contexto de reglas y, cuando sea necesario, una prueba reproducible en el cliente.
5. Actualizar valores y cálculos relacionados. Registrar evidencia y distinguir estimaciones o datos pendientes.
6. Revisar la guía y los casos límite afectados. Si cambia la lámina, exportar PDF 16:9 y PNG de 2560 × 1440.
7. Revisar el cambio antes de integrarlo a `main`, cuya publicación activa Pages.

Ejemplo que motivó este criterio: el Tormentor pasó de aparición inicial a 15:00 en 7.38 a 20:00 en 7.39. Consultar solo el primer cambio o buscar únicamente la palabra «Tormentor» puede perder contexto de una sección general.

## Automatización propuesta

Todavía no implementada. Un workflow periódico y manual podría consultar el listado de Valve y las revisiones de los archivos seleccionados, compararlas con una referencia aprobada y generar un informe.

Detectar que cambió un archivo no demuestra que cambió una mecánica concreta. El informe debe conservar valores anteriores, referencias nuevas y campos por revisar; no debe sobrescribir cifras publicadas ni marcar toda la guía como verificada.

Separar «última comprobación de novedades» de «última verificación de un dato». Si una fuente falla, mostrar el fallo y conservar la referencia anterior.

GitHub puede retrasar ejecuciones programadas y desactivar workflows programados de repositorios públicos tras 60 días sin actividad. Referencia: [eventos programados de Actions](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule).

## Modelo de datos propuesto

Cuando se separen los datos del HTML, cada afirmación debería incluir identificador, valor, unidad, condiciones, parche, fecha de revisión, estado de verificación y evidencia enlazada a una revisión fija. Guardar también el motivo del cambio.

La separación de datos, el historial y el detector son próximos incrementos; la migración inicial conserva el HTML existente.

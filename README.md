# ICN292 - Laboratorio 3: MVP de triage de devoluciones en n8n

**Nombre:** Fernanda Sáez Cabrera
**Semilla S:** 092 (U = $72.000, D = 7 días)
**Fecha:** 23 de septiembre de 2026

## Descripción
Este repositorio contiene el desarrollo del Laboratorio 3 del curso ICN292: un producto mínimo viable (MVP) en n8n para automatizar el triage de solicitudes de devolución del canal e-commerce de AndesHogar SpA.

## Contenido del repositorio
- `ICN292-Lab3-Saez-Fernanda.pdf` — Informe en PDF
- `ICN292-Lab3-Saez-Fernanda.docx` — Informe en Word
- `ICN292-Lab3-Saez-Fernanda-triage.json` — Workflow principal de clasificación
- `ICN292-Lab3-Saez-Fernanda-emisor.json` — Workflow que envía las 15 solicitudes
- `ICN292-Lab3-Saez-Fernanda-resumen.json` — Workflow de resumen diario
- `ICN292-Lab3-Saez-Fernanda-bonus.json` — Versión alternativa del triage con un nodo Code (bonus)
- `/capturas` — Capturas de todas las ejecuciones incluidas en el informe

## Cómo reproducir los workflows
1. Iniciar n8n en local habilitando el acceso a archivos (necesario para guardar y leer los registros):
   `N8N_BLOCK_FILE_ACCESS_TO_N8N_FILES=false N8N_RESTRICT_FILE_ACCESS_TO="" npx n8n`
2. Abrir `http://localhost:5678` en el navegador.
3. Importar cada `.json` desde el menú del workflow → *Import from File*.
4. Ajustar la ruta de registros: en el nodo *Guardar registro* (triage) y en *Leer registros* (resumen), reemplazar `/Users/fernanda/.n8n/registro/` por una carpeta existente en el equipo.
5. Publicar el workflow de triage (*Publish*) para habilitar la URL de producción `http://localhost:5678/webhook/triage-devoluciones`.
6. Ejecutar el workflow emisor, que ya apunta a esa URL y envía las 15 solicitudes.
7. Ejecutar el workflow de resumen manualmente o esperar su ejecución programada (20:00 h).

**Notas:**
- El resumen lee todos los archivos de la carpeta de registros; para reproducir los resultados del informe, la carpeta debe contener solo los registros de las 15 solicitudes.
- El workflow bonus (`ICN292-Lab3-Saez-Fernanda-bonus.json`) tiene su propio webhook. Para probarlo, se debe importar, publicar y enviar las solicitudes a `http://localhost:5678/webhook/triage-bonus`, cambiando la URL en el nodo HTTP Request del emisor.

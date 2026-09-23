# ICN292 - Laboratorio 3: MVP de triage de devoluciones en n8n

**Nombre:** Fernanda Sáez Cabrera
**Semilla S:** 92 (U = $72.000, D = 7 días)
**Fecha:** 23 de septiembre de 2026

## Descripción

Este repositorio contiene el desarrollo del Laboratorio 3 del curso ICN292, que consiste en un producto mínimo viable (MVP) en n8n para automatizar el triage de solicitudes de devolución del canal e-commerce de AndesHogar SpA.

## Contenido del repositorio

- `ICN292-Lab3-Saez-Fernanda.pdf` — Informe en formato PDF
- `ICN292-Lab3-Saez-Fernanda.docx` — Informe en formato Word
- `ICN292-Lab3-Saez-Fernanda-triage.json` — Workflow principal de clasificación
- `ICN292-Lab3-Saez-Fernanda-emisor.json` — Workflow que envía las 15 solicitudes
- `ICN292-Lab3-Saez-Fernanda-resumen.json` — Workflow de resumen diario
- `/capturas` — Capturas de ejecuciones exitosas y fallidas

## Cómo reproducir los workflows

1. Instalar y ejecutar n8n de forma local: `npx n8n`
2. Abrir n8n en el navegador: `http://localhost:5678`
3. Importar cada archivo `.json` desde el menú del workflow seleccionando Import from File.
4. En el workflow de triage, activar el webhook y copiar la URL de producción.
5. En el workflow emisor, pegar esa URL en el nodo HTTP Request y ejecutarlo para enviar las 15 solicitudes.
6. Ejecutar el workflow de resumen manualmente o esperar su activación programada mediante Schedule Trigger.

**Nota:** uno de los nodos guarda el registro en el computador, por lo que n8n debe ejecutarse en modo local con permiso para acceder a archivos. Si al reproducirlo aparece un error de acceso, basta con habilitar ese permiso al iniciar el programa.

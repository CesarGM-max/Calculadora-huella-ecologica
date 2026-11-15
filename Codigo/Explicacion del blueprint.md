# Escenario `Huella_Ecologica_Equipo`

Flujo de 3 módulos: **Página web → Webhook de Make → Make AI Agent → Webhook Response → Página web**.

| # | Módulo | Qué hace |
|---|--------|----------|
| 1 | **Webhooks → Custom webhook** | Recibe el formulario de la página (10 campos: `carne`, `local`, `transporte`, `km`, `vuelos`, `aire`, `personas`, `ropa`, `celular`, `separa`) enviado como `URLSearchParams`. |
| 2 | **Make AI Agent** (conexión *Make's AI Provider*) | Recibe una línea por campo (`Carne: {{1.carne}}`, `Comida local: {{1.local}}`, …) y estima la huella con el formato del prompt. `tokenLimit` bajo para gastar pocos créditos. |
| 3 | **Webhooks → Webhook Response** | Status 200, body `{{2.response}}`, headers `Content-Type: text/plain; charset=utf-8` y `Access-Control-Allow-Origin: *` (este último permite que el navegador acepte la respuesta). |

## Prompt del agente
Parte del prompt de la práctica (rol de analista de huella ecológica para alumnos del TecNM Mazatlán, formato de salida con huella estimada, planetas, impacto por área, 3 acciones y oportunidad económica). Se le agregaron **referencias de calibración** porque en una prueba inicial la IA dio 12 gha y, a la vez, "1.7 planetas" (cifras incompatibles):

- promedio mundial ≈ 2.5 gha y México ≈ 2.65 gha por persona; biocapacidad ≈ 1.6 gha por persona;
- fórmula explícita: planetas = hectáreas globales / 1.6;
- el aire acondicionado se reparte entre las personas de la casa;
- instrucción de no copiar el texto de las plantillas (en otra prueba repitió "alto y por qué, en 1 línea" en lugar de explicar).

Después de esos ajustes la misma entrada dio 4.2 gha y 2.6 planetas, consistente (4.2 / 1.6 ≈ 2.6), con una razón concreta por área.

## Importar
En Make: *Create a new scenario → ⋯ → Import Blueprint*, seleccionar `blueprint.json`, crear un webhook nuevo en el módulo 1, elegir la conexión *Make's AI Provider* en el módulo 2, activar con *Immediately as data arrives* y pegar la URL del webhook en `WEBHOOK_URL` de `index.html`.

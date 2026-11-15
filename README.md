# Práctica 4.5 — Calculadora de huella ecológica

- **Alumno:** Cesar Jesus Gamez Mendoza
- **Materia:** Desarrollo Sustentable (ACD-0908)
- **Profesor:** Mtro. Miguel Ángel Barrón Hernández
- **Institución:** Tecnológico Nacional de México — Campus Mazatlán

## Descripción
Página web con un cuestionario de estilo de vida (alimentación, transporte, energía, consumo y residuos). Al presionar **Calcular mi huella**, la página envía las respuestas a un webhook de Make; un agente de IA estima la huella en hectáreas globales y los planetas Tierra necesarios, ordena las áreas por impacto, propone 3 acciones y una oportunidad económica local. Después el equipo compara el resultado con la calculadora oficial de Global Footprint Network.

**Flujo:** Página web → Webhook de Make → Make AI Agent → Webhook Response → Página web.

## Objetivo
Que el alumno calcule y compare su huella ecológica, identifique qué hábitos la elevan y proponga estrategias económicas y personales para reducirla, evaluando la precisión de una estimación hecha con IA.

## Material utilizado
- Computadora con navegador
- Cuenta de Make (conexión *Make's AI Provider*)
- Repositorio de GitHub con GitHub Pages
- Calculadora oficial: https://www.footprintcalculator.org

## Código
- [`Codigo/index.html`](Codigo/index.html): página web (HTML, CSS y JavaScript en un solo archivo).
- [`Codigo/blueprint.json`](Codigo/blueprint.json): escenario de Make exportado (importable con *Import Blueprint*).
- [`Codigo/Explicacion del blueprint.md`](Codigo/Explicacion%20del%20blueprint.md): explicación módulo por módulo y ajustes al prompt.

## Imágenes
<!-- Captura del escenario completo en Make, ordenado, con los 3 módulos visibles -->
<!-- Captura de la página con un resultado -->
<!-- Captura de la calculadora oficial -->

## Video
[`Video/enlace.txt`](Video/enlace.txt)

## Resultados
[`Resultados/Resultados.pdf`](Resultados/Resultados.pdf): investigación previa, tabla comparativa (página vs. calculadora oficial) y respuestas a las 5 preguntas del informe.

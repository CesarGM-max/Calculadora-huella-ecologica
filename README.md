# Práctica 4.5 — Calculadora de huella ecológica

- **Alumno:** Cesar Jesus Gamez Mendoza
- **Materia:** Desarrollo Sustentable (ACD-0908)
- **Profesor:** Mtro. Miguel Ángel Barrón Hernández
- **Institución:** Tecnológico Nacional de México — Campus Mazatlán


> **AVISO — datos estimados con IA:** las respuestas del cuestionario que se capturaron en la página y en la calculadora oficial (carne 3-5 veces por semana, comida local la mitad, camión urbano 12 km al día, 1 vuelo al año, aire acondicionado 6 h al día, 4 personas en casa, 2 prendas nuevas al mes, celular cada 3 años, separo la basura a veces) son **valores estimados y simulados con ayuda de IA**, no una medición real de mis hábitos. Las cifras de los resultados (planetas, hectáreas globales) son las que devolvieron realmente la página y la calculadora oficial con esas respuestas el 14 de noviembre de 2026.

## Descripción
Página web con un cuestionario de estilo de vida (alimentación, transporte, energía, consumo y residuos). Al presionar **Calcular mi huella**, la página envía las respuestas a un webhook de Make; un agente de IA estima la huella en hectáreas globales y los planetas Tierra necesarios, ordena las áreas por impacto, propone 3 acciones y una oportunidad económica local. Después comparo el resultado con la calculadora oficial de Global Footprint Network.

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
| # | Archivo | Contenido |
|---|---------|-----------|
| 1 | `Imagenes/01-formulario-parte1.jpg` | Página publicada: alimentación y transporte con las respuestas estimadas |
| 2 | `Imagenes/02-formulario-parte2.jpg` | Página publicada: energía, consumo, residuos y botón *Calcular mi huella* |
| 3 | `Imagenes/03-resultado-calculadora.jpg` | Resultado de la página: 4.0 gha por año y 2.5 planetas, áreas ordenadas por impacto |
| 4 | `Imagenes/04-escenario-make.jpg` | Escenario completo en Make: Webhook → Make AI Agent → Webhook response (activo, ejecución exitosa) |
| 5 | `Imagenes/05-calculadora-oficial-resultado.jpg` | Calculadora oficial: 3.4 Tierras y día de sobregiro personal el 17 de abril |
| 6 | `Imagenes/06-calculadora-oficial-detalle.jpg` | Calculadora oficial: 5.8 gha, 9.1 t de CO2 al año, desglose por categoría |

## Video
[`Video/enlace.txt`](Video/enlace.txt)

## Resultados
Informe completo (investigación previa, tabla comparativa y respuestas): [`Resultados/Resultados.pdf`](Resultados/Resultados.pdf).

### Tabla comparativa

| Medición | Planetas según mi página | Planetas según la calculadora oficial | Diferencia | Área de mayor impacto |
|----------|--------------------------|----------------------------------------|------------|-----------------------|
| Respuestas estimadas del 14/11/2026 | 2.5 (4.0 gha) | 3.4 (5.8 gha) | 0.9 planetas (la página da ≈ 26 % menos) | Página: **Energía** (alto). Oficial: **Comida**, seguida de vivienda (*Abrigo*) |

**Comparación con el promedio:** el promedio mundial es de ≈ 1.7 planetas (2.51 gha de huella ÷ 1.48 gha de biocapacidad por persona) y la huella promedio de México es de ≈ 2.65 gha por persona (≈ 1.6 planetas con 1.6 gha). Con ambas calculadoras me ubico **por encima** de los dos promedios (2.5 y 3.4 planetas).

## Respuestas a las preguntas de reflexión

**1. ¿Qué área de su estilo de vida genera la mayor huella? ¿Coincide con lo que esperaba?**
Mi página marcó **Energía** como la única área de impacto alto, por el aire acondicionado 6 horas al día en clima cálido; Alimentación, Transporte, Consumo y Residuos quedaron en nivel medio. La calculadora oficial, en cambio, muestra como barra más alta **Comida** (carne 3-5 veces por semana) y después la vivienda (*Abrigo*); *Movilidad* fue la más baja, lo que tiene sentido porque en este caso el transporte principal es el camión urbano. Esperaba que energía fuera lo más pesado por vivir en Mazatlán; solo coincidió en parte, y me llamó la atención el peso de la comida, que la IA calificó solo como medio.

**2. ¿Por qué el aire acondicionado pesa tanto en la huella de una persona en Mazatlán? ¿Qué alternativas hay?**
Mazatlán tiene clima cálido y húmedo gran parte del año, así que el aire acondicionado se usa muchas horas y es uno de los aparatos que más electricidad consumen en una casa. Esa electricidad viene en buena parte de combustibles fósiles: el factor de emisión del Sistema Eléctrico Nacional 2024 es de 0.444 kg de CO2e por kWh, así que cada hora de aire se traduce en emisiones y en hectáreas necesarias para absorberlas. Alternativas: ventiladores y ventilación cruzada, cortinas y sombra en ventanas al sol, mejor aislamiento del techo, equipos inverter más eficientes, termostato en una temperatura moderada, encenderlo solo las horas necesarias y, a mediano plazo, paneles solares aprovechando la alta radiación de la región.

**3. ¿Qué tan cerca estuvo la estimación de la IA de la calculadora oficial? ¿A qué se debe la diferencia?**
La IA estuvo a 0.9 planetas de la oficial (2.5 contra 3.4; 4.0 contra 5.8 gha), es decir, subestimó la huella en cerca de una cuarta parte, aunque ambas dan el mismo diagnóstico general: más de dos planetas, por encima del promedio. Las causas probables: (a) la IA solo recibe 10 respuestas y supone el resto, mientras que la oficial pregunta por vivienda, tamaño de la casa, porcentaje de energía renovable, bienes y servicios, y usa factores propios; (b) para la oficial tuve que completar datos que mi página no pide (casa tipo duplex de ladrillo y 84 m², 12 % de energía renovable por defecto, 5 km semanales en moto, 6 horas de vuelo al año), que también suman; (c) cada calculadora usa una biocapacidad distinta (la mía 1.6 gha por persona, la oficial ≈ 1.7 gha, porque 5.8 ÷ 3.4); y (d) como se vio en la primera prueba, la IA puede dar cifras con apariencia de precisión pero inconsistentes hasta que se calibra el prompt. Por eso la usaría como estimación rápida y no como medición.

**4. ¿Qué estrategia económica ayudaría más a reducir la huella de su comunidad?**
Para Mazatlán, la de más efecto es la eficiencia y generación de energía limpia en hogares y comercios: empresas locales con diagnósticos de consumo de aire acondicionado, mejoras de aislamiento y paneles solares. Como segunda línea, la economía circular (centros de reparación y reutilización de aparatos y ropa, acopio de residuos electrónicos, composta de residuos orgánicos de restaurantes y mercados) y, como tercera, los servicios ambientales y el consumo local, apoyando la pesca y la agricultura de temporada de la región. Las tres reducen gastos de las familias y crean negocios locales.

**5. ¿Qué acción concreta harán durante el próximo mes y cómo medirán si funcionó?**
Plan propuesto: bajar el uso del aire acondicionado de 6 a 4 horas diarias usando ventilador y cortinas el resto del tiempo, y comer carne máximo 2 veces por semana en lugar de 3-5. Para medirlo compararé los kilowatts-hora del recibo de la CFE del periodo anterior con el siguiente y volveré a capturar el mismo cuestionario en mi página y en la calculadora oficial para ver cuánto bajan los planetas.

## Conclusión
La huella ecológica convierte hábitos cotidianos en una cifra comparable con lo que el planeta puede regenerar. Con mis respuestas estimadas, la página dio 2.5 planetas y la calculadora oficial 3.4; las dos coinciden en que estaría por encima del promedio mundial y de México, pero difieren en qué pesa más (energía contra comida) y en la magnitud. Una IA permite estimarla rápido y dar recomendaciones locales, pero sus cifras son aproximadas y deben contrastarse con una calculadora oficial. Lo que más puedo reducir es el uso del aire acondicionado y la frecuencia de carne.

## Fuentes
- Global Footprint Network, *Earth Overshoot Day 2026 falls on July 30*: https://footprintnetwork.org/2026/06/05/announcement-earth-overshoot-day-2026-falls-on-july-30/
- Calculadora oficial: https://www.footprintcalculator.org
- Wikipedia, *List of countries by ecological footprint*: https://en.wikipedia.org/wiki/List_of_countries_by_ecological_footprint
- SEMARNAT, Informe de la Situación del Medio Ambiente en México: https://apps1.semarnat.gob.mx:8443/dgeia/informe_12eng/01_poblacion/recuadro3.html

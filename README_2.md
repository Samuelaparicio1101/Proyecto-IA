# Analisis de liquidez bancaria y sistema de alerta temprana en Colombia

## Objetivo 
Evaluar la evolución de la liquidez y la solvencia de los bancos comerciales en Colombia y diseñar un modelo automatizado de alerta temprana que identifique señales de riesgo financiero en el período y sea capaz de predecir el comportamiento de la liquidez bancaria frente a choques externos

### Objetivos especificos

- **Caracterizar la evolución de la liquidez bancaria en Colombia, identificando tendencias y episodios críticos.** en el período de estudio, identificando sus tendencias, ciclos y puntos de inflexión más relevantes
- **Identificar y evaluar el impacto de los factores macroeconómicos** (como la tasa de intervención del Banco de la República, el crecimiento del PIB, la tasa de desempleo y la tasa de cambio) sobre la liquidez del sistema.
- **Construir y probar indicadores de alerta temprana** combinando ratios de liquidez y rentabilidad..
- **Examinar el efecto de la normativa y regulación financiera** impuesta por la Superintendencia Financiera de Colombia (como los requisitos de capital -COLCAP- y de liquidez) sobre la profitability del sector.
- **Automatizar el proceso de monitoreo** mediante scripts en Python que descarguen, limpien y analicen los datos periódicamente.
- **Proponer conclusiones y, en base a los hallazgos, esbozar recomendaciones** dirigidas a la gestión de las entidades bancarias y a los entes reguladores, orientadas a la sostenibilidad financiera del sector.

## 1. Planteamiento del Problema:
El sector bancario colombiano es un pilar de la estabilidad económica. Sin embargo, la liquidez de las entidades puede verse afectada por cambios en las tasas de interés, ciclos económicos, choques externos y regulaciones. Una reducción abrupta de liquidez puede generar desconfianza y riesgos sistémicos.
Por eso, es crucial contar con un sistema que permita monitorear periódicamente los indicadores financieros y detectar señales tempranas de deterioro.

Comprender la naturaleza y el grado de influencia de estos factores es crucial no solo para la gestión estratégica de los propios bancos, sino también para los reguladores que buscan preservar la estabilidad del sistema financiero y para los inversionistas que evalúan oportunidades. 

## 2. Justificación:
Este estudio es relevante por las siguientes razones:
- **Para la gestión bancaria:** Proporcionará a los administradores de entidades financieras evidencia concreta sobre qué variables impactan más su liquidez y su capacidad de desembolso, permitiéndoles optimizar sus estrategias de asignación de capital, gestión de riesgos y control de gastos, brindando herramientas de monitoreo preventivo que apoyan la gestion de riesgos.
- **Para los reguladores:** Ofrecerá insights valiosos sobre cómo las políticas regulatorias y monetarias afectan la salud financiera del sector, contribuyendo al diseño de marcos normativos más efectivos que promuevan un equilibrio entre solvencia y capacidad para cubrir sus obligaciones, permite detectar deterioros de liquidez antes de que se conviertan en crisis..
- **Para la academia y análisis económico:** Contribuirá a la literatura especializada sobre banca en contextos emergentes como el colombiano, sirviendo como base para investigaciones futuras y para un mejor entendimiento del canal de transmisión de la política económica, ejemplificando cómo aplicar técnicas de análisis de datos y automatización a un problema económico real.
- **Para los inversionistas:** Ayudará a construir modelos más precisos para evaluar el desempeño y la estbilidad de las entidades financieras listadas en la bolsa colombiana, contribuye a la confianza en el sistema financiero al asegurar vigilancia constante..

## 3. Alcance:
La investigación se centrará en el sistema bancario comercial colombiano. El análisis cubrirá el período marzo 2020 a diciembre del 2022, un lapso que permite capturar diferentes fases del ciclo económico el alcance incluye:Limpieza y preparación de datos, construcción de indicadores de liquidez y solvencia, exploración de patrones históricos y diseño de un prototipo de alerta temprana con Python. El estudio utilizará datos secundarios de acceso público de fuentes oficiales.

## 4. Desafíos:
-	Acceso y calidad de los datos (series incompletas, cambios metodológicos en fuentes oficiales)
-  Selección de variables relevantes (evitar multicolinealidad o ruido).
-	Construcción de un modelo robusto que combine información macroeconómica y microeconómica.
-	Incorporar choques externos (pandemia, volatilidad internacional, tasas de la FED).
-	Medición de rezagos temporales (ej: efecto de tasas de interés sobre utilidades puede no ser inmediato).
-  Escasez de casos reales de quiebra → necesidad de construir un proxy de alerta.

## 5. Entrega de valor:
Este proyecto busca entregar beneficios tanto a nivel académico como práctico:
1. **Para los bancos comerciales:**
   - Identificación de los principales factores internos y externos que afectan la liquidez.
   - Herramientas para mejorar la planificación financiera y la gestión de riesgos con un sistema sencillo de monitoreo de su liquidez con indicadores claros.
2. **Para reguladores (Superintendencia Financiera, Banco de la República):**
   - Monitoreo más preciso de la estabilidad financiera del sistema.
   - Apoyo para diseñar políticas monetarias y prudenciales que reduzcan riesgos bancarios con un prototipo de herramienta para vigilar tendencias de solvencia y liquidez.
3. **Para inversionistas y accionistas:**
   - Proyecciones sobre el desempeño futuro de los bancos.
   - Mejor comprensión del impacto de la coyuntura macroeconómica en la liquidez del sistema y facilitar herramientas que den informacion de que se espera para un futuro.
4. **Valor académico y de investigación:**
   - Ofrecer un marco de referencia para futuros estudios en el sector bancario colombiano.
   - mayor seguridad y estabilidad del sistema financiero con un caso de estudio reproducible que combina economía y programación.

## 6. Stakeholders:
### *Internos (del sector financiero):*
-	**Bancos comerciales:** gerentes financieros, departamentos de riesgos, planeación estratégica.
-	**Accionistas:** interesados en maximizar el retorno de su inversión.
-	**Analistas financieros:** encargados de valorar desempeño bancario.
### *Externos (reguladores y mercado):*
- **Superintendencia Financiera de Colombia (SFC):** vigilancia del sistema financiero.
-	**Banco de la República:** encargado de política monetaria y estabilidad macroeconómica.
-	**Ministerio de Hacienda y Crédito Público:** para políticas fiscales relacionadas con el sector.
-	**Inversionistas institucionales:** fondos de inversión, calificadoras de riesgo.

## 7. técnicas que utilizaremos: 
Iniciamos con la metodología CRISP – DM con el fin de inicialmente poder entender los bancos y cómo se comportan, entender que la mayoría de sus activos son pasivos y no generar falsas alarmas combase a que su sistema funciona	diferente. A sí podemos incluso encontrar estrategias que nos ayuden a predecir las tasas de ellos y de esa manera por parte del Banco de la Republica poder preparar una mejor estrategia.

Para el modelo de predicción que utilizaremos un modelo supervisado con el fin de identificar influencia de las variables independeientes sobre la independiente, nuestra variable dependiente sera el IRL (indice de riesgo de liquidez). Mediante una regresion logistica que nos permitira asignarle una probabilidad a cada entidad sobre si esta en riesgo de liquidez o no.
## 8. Fuentes:
Utilizaremos fuentes del Banco de la República, DANE, Superintendencia Financiera de Colombia y Noticia Reuters, con el fin de utilizar fuentes de datos oficiales para darle credibilidad al modelo y evitar problemas de la veracidad de la información

## 9 Las variables:
- IRL
- Activos
- Pasivos
- Patrimonio
- Indicadores de liquidez
- Tasa de politica monetaria
- Encajes bancarios






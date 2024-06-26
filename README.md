# Análisis para disminuir la cantidad de víctimas fatales de siniestros viales en Buenos Aires, Argentina

## Introducción

En este proyecto, simulamos el rol de un Data Analyst en el equipo de analistas de datos de una empresa consultora que trabaja para el Observatorio de Movilidad y Seguridad Vial (OMSV). Se nos encomendó la tarea de realizar un análisis de datos sobre homicidios en siniestros viales ocurridos en Buenos Aires entre 2016 y 2021.

El objetivo principal es proporcionar información que permita a las autoridades locales tomar medidas para reducir la cantidad de víctimas fatales en accidentes de tráfico. Se presentará un informe detallado de las tareas realizadas, las metodologías adoptadas y las conclusiones clave. Además, se desarrollará un dashboard interactivo para facilitar la interpretación de los datos y su análisis.

## Contexto
Los percances viales, también denominados incidentes de tráfico, siniestros viales o accidentes de tránsito, representan situaciones donde vehículos se ven involucrados en espacios públicos. Estos eventos pueden ser desencadenados por diversas causas, como colisiones entre automóviles, motocicletas, bicicletas o peatones, atropellos, impactos contra objetos fijos o incluso caídas de vehículos. Las consecuencias abarcan desde daños materiales hasta lesiones graves o, lamentablemente, pérdidas fatales para los afectados.
Los siniestros viales son una preocupación importante en la Ciudad Autónoma de Buenos Aires debido al alto volumen de tráfico y la densidad poblacional. La población de CABA corroborada en el ultimo censo realizado (2022) es de 3,120,612 habitantes en una superficie de 200 km².

## Datos

Se trabajó con la Base de Víctimas Fatales en Siniestros Viales en formato Excel, que contiene dos pestañas de datos: "HECHOS" y "VICTIMAS". Estas incluyen información sobre los eventos, víctimas, edad, sexo, modo de desplazamiento, etc. El análisis se basó en la exploración y limpieza de datos utilizando Python y Pandas.

## Limpieza de datos

Python y Pandas se emplearon para la extracción, transformación y carga [ETL](1_ETL_HOMICIDIOS.ipynb) de datos. Para el análisis exploratorio de datos [EDA](2_EDA.ipynb) se utilizaron librerias como Seaborn, Matplotlib, numpy y pandas. Por ultimo para lo que represento la creacion del [dashboard](4_PI2_Siniestros.pbix) se utilizo PowerBi

## Proceso de trabajo

### ETL y EDA

Se realizó un exhaustivo proceso ETL para estandarizar nombres de variables, analizar nulos y duplicados, y eliminar columnas redundantes. Posteriormente, se llevó a cabo un análisis exploratorio para identificar patrones y tendencias que ayuden a tomar medidas preventivas.

### Análisis de los Datos

El análisis integral de los datos sobre siniestros viales en la Ciudad de Buenos Aires revela patrones y tendencias significativas:

**Datos Generales:**
- El conjunto de datos cuenta con 707 registros y 25 columnas, proporcionando información detallada sobre accidentes, víctimas, ubicación y detalles temporales.

**Características Temporales:**
- Los accidentes parecen distribuirse de manera relativamente uniforme a lo largo de los años, meses y días, con un promedio de 1.06 víctimas por incidente. Sin embargo analizando cada año en particular el 2020 fue un año donde disminuyo mucho la tasa de siniestros viales, esto puede ser consecuencia de la cuarentena impuesta por las autoridades en base a la pandemia de COVID-19.

**Ubicación y Franja Horaria:**
- La mayoría de los accidentes ocurren en las franjas horarias de 6:00 a 12:00 y de 18:00 a 24:00 horas, y la Comuna 1 es la más afectada.
- Las avenidas son escenarios comunes de accidentes, representando el 62% de las víctimas, con un pico los sabados.

**Edad:**
- La edad promedio de las víctimas es de aproximadamente 42 años.
- La mayoría de las víctimas tienen edades comprendidas entre 20 y 40 años, destacando la importancia de dirigir estrategias de seguridad vial a este grupo.

**Género:**
- El 76.6% de las víctimas son masculinas, siendo este género predominante en todos los roles, ya sea conductor, pasajero o peatón.

**Roles y Responsabilidad:**
- El 48% de las víctimas desempeñaba el rol de conductor, principalmente en motos.
- Los conductores de automóviles, colectivos y camiones son responsables del 75% de los casos donde se señala un vehículo como responsable.

**Distribución Espacial:**
- La alta frecuencia de accidentes en avenidas en la mayoría de las comunas de la Ciudad de Buenos Aires indica posibles áreas críticas con alto flujo vehicular y, por ende, mayores riesgos de siniestros viales. .

**Patrones Temporales:**
- Se observa un aumento en la cantidad de accidentes en diciembre.
- A nivel mensual, la distribución varía, con picos de accidentes en diferentes meses en distintos años. Aunque se puede observar un patrón anual en la distribución de incidentes, destacando un pico significativo en diciembre, lo que indica que este mes experimentó la mayor cantidad de incidentes. Contrastando con esta tendencia, abril emerge como el mes con la menor cantidad de incidentes registrados. Este análisis revela una tendencia general de disminución gradual de incidentes desde enero hasta abril, seguida de un aumento progresivo en los meses de mayo, junio, agosto y noviembre.

**Relación entre Víctimas y Acusados:**
- Las motos son frecuentes víctimas pero raramente acusadas. Los autos, por otro lado, son comunes en ambos roles.

Este análisis integral proporciona una visión completa de la problemática de los siniestros viales en la Ciudad Autónoma de Buenos Aires, ofreciendo insights valiosos para orientar acciones preventivas y mejorar la seguridad vial en la región.


### KPI (Indicadores Clave de Rendimiento)

En el marco del análisis de los siniestros viales y con el objetivo de reducir la cantidad de víctimas fatales, se han definido dos Indicadores Clave de Rendimiento (KPI) que abordan aspectos específicos de la seguridad vial en CABA. Para poder realizar el analisis de los indicadores se crearon [Tablas de KPI´s](3_KPI.ipynb) para facilitar dicho proceso

**KPI 1 - Métrica de Seguridad en Accidentes Vehiculares:** 

La métrica de seguridad en accidentes vehiculares se configura como un indicador esencial, evaluando el número de víctimas fatales en incidentes de tráfico por cada 100,000 habitantes durante un semestre. La meta consiste en reducir esta métrica en un 10% en el segundo semestre de 2021 en comparación con el primer semestre. El análisis demuestra que al alcanzar una métrica de 1.35, se superó con éxito el objetivo de disminuir en un 10% la tasa de fatalidades, ya que la métrica previa era de 1.73, logrando así una reducción del 22.22%.

**KPI 2 - Incidentes Mortales Involucrando Motociclistas:**

El segundo KPI se enfoca en supervisar la cantidad de incidentes mortales relacionados con motociclistas. El propósito es reducir en un 7% la cantidad de accidentes mortales de motociclistas durante el último año. No obstante, los resultados indican un aumento del 79.21% en la cifra de fallecimientos de motociclistas en 2021, señalando la necesidad de estrategias adicionales. Es importante tener en cuenta que el año 2020 estuvo marcado por una pandemia y restricciones de movimiento, lo cual impactó la circulación en las calles.

En resumen, la implementación de estrategias para mejorar la seguridad vial en CABA ha tenido éxito en ciertos aspectos, como la disminución de la tasa de fatalidades en accidentes vehiculares. Sin embargo, se requieren acciones más efectivas para abordar el incremento de incidentes mortales con motociclistas. Se hace imperativo ajustar las estrategias existentes y desarrollar nuevas iniciativas para hacer frente a los desafíos identificados por los KPI.

## Reflexiones:

1. **Contextualización de Datos Temporales:**
   - La observación detallada de los datos revela que el año 2020 presenta una disminución significativa en la tasa de siniestros viales, atribuible a las restricciones implementadas durante la cuarentena por la pandemia de COVID-19. Esta información es crucial para entender la variabilidad de los datos y considerar factores externos que pueden influir en la seguridad vial.

2. **Comportamiento Temporal y Espacial:**
   - La distribución uniforme de accidentes a lo largo de los años y meses sugiere una necesidad constante de atención a la seguridad vial. No obstante, la concentración de incidentes en ciertas franjas horarias y áreas específicas, como la Comuna 1 y las avenidas, destaca la importancia de estrategias focalizadas en momentos y lugares específicos.

3. **Roles y Edades de las Víctimas:**
   - El análisis detallado de los roles y edades de las víctimas revela que el grupo de edad entre 20 y 40 años es particularmente vulnerable. Es esencial dirigir las estrategias de seguridad vial específicamente a este segmento de la población para lograr un impacto significativo.

4. **Género y Responsabilidad:**
   - La predominancia de víctimas masculinas y el hecho de que los conductores de diversos vehículos son responsables del 75% de los casos subraya la necesidad de abordar patrones de comportamiento específicos. Las estrategias deben considerar diferencias de género y roles vehiculares para maximizar la efectividad.

## Sugerencias:

1. **Educación y Concientización Específica:**
   - Desarrollar campañas educativas específicas, enfocadas en la franja horaria de mayor incidencia, dirigidas a los grupos de edad más afectados. Esto podría incluir programas de concientización en escuelas y espacios públicos.

2. **Infraestructura y Señalización Mejorada:**
   - Implementar mejoras en la infraestructura vial y señalización, especialmente en áreas críticas identificadas, como las avenidas con alto flujo vehicular. Medidas como carriles exclusivos para motocicletas y señales claras pueden reducir la probabilidad de incidentes.

3. **Monitoreo Activo en Diciembre:**
   - Dada la tendencia anual de aumento en diciembre, intensificar las medidas de seguridad y aplicación de la ley durante este mes. La presencia policial y campañas de seguridad específicas podrían contribuir a mitigar este aumento estacional.

4. **Participación Comunitaria Continua:**
   - Fomentar la participación activa de la comunidad en la identificación de áreas problemáticas y en la promoción de comportamientos seguros. Establecer canales de retroalimentación y colaboración puede fortalecer las iniciativas de seguridad vial.

5. **Análisis Continuo de Datos:**
   - Establecer un sistema de análisis continuo de datos para detectar patrones emergentes y ajustar estrategias según la evolución de la situación. La tecnología y el análisis de big data pueden ser herramientas valiosas en este sentido.

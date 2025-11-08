# Malaria_GEO
## Análisis Geoespacial de la Prevalencia de la Malaria
### Descripción general del proyecto
La intención de este proyecto es examinar la prevalencia y el reparto espacial de la malaria a escala global, centrándose en detectar correlaciones ambientales y geográficas que impacten su transmisión y carga patológica.
La investigación pretende comprender la relación entre la aparición de malaria en varias zonas y elementos como la temperatura, las precipitaciones, la densidad poblacional, la altitud y la hidrografía. El proyecto tiene un alcance mundial, pero se enfocará particularmente en las áreas endémicas de Asia, América del Sur y África.

### Contexto y motivo del estudio
La malaria, causada por parásitos del género Plasmodium y transmitida por mosquitos Anopheles, sigue siendo una de las principales amenazas para la salud pública. La transmisión de la enfermedad es intrínsecamente ligada a la geografía, ya que el mosquito vector es sensible a las condiciones climáticas y ambientales.
El análisis geográfico (o geoespacial) de la malaria es fundamental porque:
1. Permite identificar puntos críticos (hotspots) de alta transmisión que requieren intervención prioritaria.
2. Facilita la comprensión de los impulsores ambientales y socioeconómicos de la enfermedad.
3. Proporciona la base para el desarrollo de modelos predictivos y sistemas de alerta temprana localizados.

### Fuentes de datos
Los datos utilizados en este estudio provienen de fuentes públicas y registros abiertos, cubriendo un período temporal significativo para identificar tendencias.
1. 'Malaria Atlas Project': https://data.malariaatlas.org/trends?year=2024&metricGroup=Malaria&geographicLevel=admin0&metricSubcategory=Pf&metricType=rate&metricName=incidence
2. Repositorio 'Malaria Atlas Project' en cran: https://cran.r-project.org/web/packages/malariaAtlas/index.html
3. Repositorio 'Malaria Atlas Project' en github: https://github.com/malaria-atlas-project/malariaAtlas

### Metodología 
Para los países africanos con mayor carga de malaria, comenzamos modelando la prevalencia de infección por Plasmodium falciparum en niños de 2 a 10 años mediante un enfoque geoestadístico. El modelo se alimentó con una amplia base de datos que incluía mediciones espaciotemporales de prevalencia en comunidades, variables ambientales y humanas, así como coberturas estimadas de intervenciones clave (mosquiteros impregnados con insecticida, rociado residual intradomiciliario y acceso a tratamiento antimalárico eficaz).

Se añadió un módulo adicional para capturar el impacto de las interrupciones en la atención de la malaria provocadas por la pandemia de COVID-19. Los mapas de alta resolución obtenidos para el periodo 2000–2022 fueron después convertidos en estimaciones de incidencia clínica y mortalidad.

En el caso de los demás países endémicos y para Plasmodium vivax, el análisis se basó en datos rutinarios de vigilancia sanitaria, a partir de los cuales se modeló la incidencia anual a escala administrativa. Posteriormente, esos valores se transformaron en prevalencia y mortalidad, y se desagregaron espacialmente para generar mapas detallados.

Finalmente, todos los resultados fueron integrados para producir mapas globales y tablas resumen, lo que permite evaluar la evolución de la carga de malaria tanto a nivel local como mundial.

### Estructura del Repositorio
Este repositorio está estructurado de la siguiente forma:
1.	Un directorio principal en el que nos encontramos los archivos _README.md_, _.gitignore_ (que nos permite crear una lista de archivos que se van a ignorar), _LICENSE_ (con la licencia elegica, en este caso MIT) y el archivo _environment.yml_
2.	Una carpeta de referencias en la que se adjunta el trabajo que se usa como base.
3.	Una carpera _data_ en la que encontramos tanto una subcarpeta _raw_ con los datos brutos y una subcarpeta _processed_ con los datos limpios. 
4.	Una carpeta _results_ en la que se encuentran los resultados de nuestra investigación. Esta está a su vez dividida en dos subcarpetas que diferencian entre resultados gráficos (_figures_) y tablas de datos (_tables_)
5.	Una carpeta _scripts_ que contiene tanto el script encargado de descargar nuestros datos brutos como el encargado de limpiar estos datos brutos.

### Limitaciones del estudio
Este análisis está sujeto a las siguientes limitaciones:
1. Calidad y Heterogeneidad de los Datos: La precisión de los resultados depende en gran medida de la calidad y la resolución espacial de los datos de prevalencia, que pueden variar entre países.
2. Problema de Unidad de Área Modificable (MAUP): La elección de las unidades geográficas de análisis (p. ej., distritos, países) puede influir en los resultados de la autocorrelación espacial y el modelado.
3. Variables No Incluidas: El modelo no puede capturar todas las complejidades biológicas, sociales y políticas que afectan a la malaria (p. ej., resistencia a medicamentos, efectividad de los programas de control local).

### Autores del proyecto
Autores: Alba Xiaohe Elias Rodriguez/AlbaEliasRod , Alejandro Pascual Hernandez/Alex-PH-Lau , Ana Sofia Santos Tedim Sousa Pedrosa/AnaPTedim , y Ainhoa Artetxe Izaguirre/aartetxeizaguirre-max

### Licencia
Este proyecto está bajo la Licencia MIT. Eres libre de usar, modificar y distribuir este código, siempre que se incluya la nota de copyright y la declaración de la licencia.

### Referencias
1. Weiss DJ, Dzianach PA, Saddler A, Lubinda J, Browne A, McPhail M, et al. Mapping the global prevalence, incidence, and mortality of Plasmodium falciparum and Plasmodium vivax malaria, 2000–22: a spatial and temporal modelling study. Lancet [Internet]. 2025 Mar 22 [cited 2025 Nov 8];405(10483):979. Available from: https://pmc.ncbi.nlm.nih.gov/articles/PMC11928297/

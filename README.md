* Recursos NILM
Una lista de repositorios con algoritmos de desagregación de energía implementados en Python o en forma de cuadernos de Jupyter Notebook
Repositorios de código sobre el NILM en Jupyter Notebook  (Python)
** Nilmtk (2014)
Github
⚠ La última versión está disponible a través de https://github.com/nilmtk/nilmtk/releases/latest 
Resumen
Kit de herramientas de monitoreo de carga no intrusivo. El monitoreo de carga no intrusiva (NILM) es el proceso de estimar la energía consumida por los aparatos individuales con solo una lectura del medidor de potencia de toda la casa. En otras palabras, produce una factura de energía (estimada) detallada a partir de un solo medidor de energía para toda la casa. NILMTK es un conjunto de herramientas diseñado para ayudar a los investigadores a evaluar la precisión de los algoritmos NILM.
⚠️ Los últimos pasos en el desarrollo de la próxima versión de NILMTK (0.4) se están realizando en la rama maestra de git. Si es un usuario nuevo, consulte la rama de la versión 0.3.x en https://github.com/nilmtk/nilmtk/tree/0.3.x  
Documentación de NILMTK
La comparación empírica de los algoritmos de desagregación es prácticamente imposible en la actualidad. Esto se debe a los diferentes conjuntos de datos utilizados, la falta de implementaciones de referencia de estos algoritmos y la variedad de métricas de precisión empleadas.
Para abordar este desafío, se presenta el Kit de herramientas de monitoreo de carga no intrusivo (NILMTK); un conjunto de herramientas de código abierto diseñado específicamente para permitir la comparación de algoritmos de desagregación de energía de una manera reproducible. Este trabajo es la primera investigación que compara múltiples enfoques de desagregación en múltiples conjuntos de datos disponibles públicamente.
NILMTK incluye:
- Analizadores para una variedad de conjuntos de datos existentes (8 y contando)
- Una colección de algoritmos de pre procesamiento
- Un conjunto de estadísticas para describir conjuntos de datos
- Una serie de algoritmos de desagregación de puntos de referencia de referencia
- Un conjunto común de métricas de precisión
Tenga en cuenta que NILMTK ha evolucionado mucho desde que se publicaron estos artículos. Utilice los documentos en línea como guía para la API actual.
Historia
•	Agosto de 2019: versión 0.4 con la nueva API. Consulte también NILMTK-Contrib .
•	Junio de 2019: v0.3.1 lanzada en Anaconda Cloud .
•	Jav 2018: compatibilidad inicial con Python 3 en la rama v0.3
•	Noviembre de 2014: NILMTK gana el premio a la mejor demostración en ACM BuildSys
•	Julio de 2014: versión 0.2 publicada
•	Junio de 2014: NILMTK presentado en ACM e-Energy
•	Abril de 2014: versión 0.1 publicada
Cuadernos de jupyter
En la ruta nilmtk/docs/manual/user_guide/ tenemos los siguientes cuadernos:
comparing_nilm_algorithms.ipynb 
data.ipynb
disaggregation_and_metrics.ipynb
elecmeter_and_metergroup.ipynb
hart_disaggregation_demo.ipynb
loading_data_into_memory.ipynb
nilmtk_api_tutorial.ipynb    <-sin datos de prueba
siteonlyapi_tutorial.ipynb  <-sin datos de prueba

** Buildsys2019 (2019)
Github
Enlace a github: https://github.com/nilmtk/buildsys2019-paper-notebooks 
Resumen 
En este repositorio puede encontrar los cuadernos que están asociados con los resultados del documento Buildsys 2019 de NILMTK. Los cuadernos en jupyter notebook demuestran el poder de la nueva API.
Los algoritmos utilizados en el artículo son los siguientes:
-	Algoritmo medio
-	Algoritmo de Hart
-	Optimización combinatoria
-	FHMM exacto
-	Codificación dispersa discriminativa
-	Aditivo FHMM
-	FHMM aditivo con SAC (restricciones agregadas de señal)
-	Codificador automático de reducción de ruido
-	RNN
-	VentanaGRU
-	Seq2Point
-	Seq2Seq
 Cuadernos de jupyter notebooks:
Los algoritmos como AFHMM, AFHMM con SAC y Codificación Discriminativa Dispersa son intensivos en CPU. Todas las redes neuronales son intensivas en GPU, por lo que un solo experimento tuvo que ejecutarse en diferentes tipos de máquinas. Todos los algoritmos intensivos de la CPU se ejecutaron en un sistema de CPU muy potente y todos los demás algoritmos se ejecutaron en un sistema con una GPU. Entonces, para cada experimento tenemos dos portátiles diferentes: uno para los algoritmos de CPU y otro para todo lo demás.
Estos son los notebooks que contiene el repositorio de Github en /nilmtk/buildsys2019-paper-notebooks/ :
-	Across Homes FHMM's and DSC.ipynb
-	Across Homes Neurals, CO, Hart, FHMM.ipynb
-	Cross Dataset FHMM's and DSC.ipynb
-	Cross Dataset Neurals, CO, Hart, FHMM.ipynb
-	Same homes Artificial Aggregate FHMM's and DSC.ipynb
-	Same homes Artificial Aggregate Neurals, CO, Hart, FHMM.ipynb
-	Same homes Real Aggregate Neurals, CO, Hart, FHMM.ipynb
-	Same homes Real Aggregate FHMM's and DSC.ipynb

** nilmtk-contrib (2019)

Github
Enlace a github:  https://github.com/nilmtk/nilmtk-contrib 
Resumen
Este repositorio contiene todos los algoritmos de última generación para la tarea de desagregación de energía implementados utilizando la API de Experimentación Rápida de NILMTK. Todos los cuadernos a los que estaba acostumbrado se pueden encontrar aquí.
Con NILMTK-contrib puede utilizar los siguientes algoritmos:
-	Modelo de Markov oculto factorial aditivo
-	Modelo de Markov oculto factorial aditivo con restricciones de señal agregada
-	Codificación dispersa discriminativa
-	RNN
-	Codificador automático de reducción de ruido
-	Seq2Point
-	Seq2Seq
-	VentanaGRU
Los algoritmos de vanguardia anteriores se han agregado a este repositorio.
Puede hacer lo siguiente utilizando la nueva API de experimentación rápida de NILMTK:
-	Capacitación y pruebas en múltiples dispositivos
-	Capacitación y pruebas en múltiples conjuntos de datos (aprendizaje de transferencia)
-	Capacitación y pruebas en varios edificios
-	Entrenamiento y pruebas con agregado artificial
-	Entrenamiento y pruebas con diferentes frecuencias de muestreo
-	Consulte este cuaderno para saber más sobre el uso de la API.
Detalles de instalación
Actualmente estamos probando un paquete conda. Puede instalarlo en su entorno actual con:
conda install -c conda-forge -c nilmtk nilmtk-contrib
o cree un entorno dedicado (recomendado) con:
conda create -n nilm -c conda-forge -c nilmtk nilmtk-contrib
Consulte este cuaderno para utilizar los algoritmos nilmtk-contrib, utilizando la nueva NILMTK-API. A menos que sea un usuario avanzado, prefiera usar el paquete Conda en lugar del repositorio de Git, ya que este último puede contener cambios de trabajo en progreso.
Dependencias:
- NILMTK> = 0,4
- scikit-learn> = 0.21 (ya requerido por NILMTK)
- Keras> = 2.2.4
- cvxpy> = 1.0.0
Nota: para un cálculo más rápido de las redes neuronales, se sugiere que instale keras-gpu, ya que puede aprovechar las GPU. Los algoritmos AFHMM, AFHMM_SAC y DSC son intensivos en CPU, use un sistema con buena CPU para estos algoritmos.
Notebooks:
En el directorio nilmtk-contrib/sample_notebooks/
 - NILMTK API Tutorial.ipynb (Create NILMTK API Tutorial.ipynb)
 - Using the API with NILMTK-CONTRIB.ipynb  (Removed Mean, CO, FHMM and Hart)

** Klemenjak
Github
Enlaces a github: https://github.com/klemenjak/SynD/blob/master/examples/simple_disaggregation.ipynb      
Papers y código  https://github.com/klemenjak/nilm-papers-with-code 
SynD https://github.com/klemenjak/SynD  
Resumen
Con el despliegue de medidores inteligentes, la importancia de las técnicas efectivas de monitoreo de carga no intrusivo (NILM) ha aumentado rápidamente. NILM estima el consumo de energía de dispositivos individuales dado su consumo agregado. De esta manera, el consumo combinado solo debe ser monitoreado en un único punto central en el hogar, brindando diversas ventajas, como un costo reducido para los equipos de medición.
Como problemas relacionados con el aprendizaje automático, la investigación y el desarrollo requieren una cantidad suficiente de datos para entrenar y validar nuevos enfoques. Como alternativa viable a la recopilación de conjuntos de datos en edificios durante campañas de medición costosas y que requieren mucho tiempo, la idea de generar conjuntos de datos sintéticos para NILM ganó impulso recientemente.
Aspecto	Hecho sobre SynD
Cantidad de electrodomésticos	21
Duración	180
Tasa de muestreo	5 Hz
Alcance	residencial NILM
¿Compatible con NILMTK?	sí
Con SynD, se presenta como un conjunto de datos de energía sintética con enfoque en edificios residenciales. Publicaron 180 días de datos de energía sintética a nivel agregado (es decir, red eléctrica) y electrodomésticos individuales. SynD es el resultado de un proceso de simulación personalizado que se basa en rastros de energía de electrodomésticos reales.
Notas de uso: Proporcionan material complementario para los nuevos usuarios de NILMTK. ¡Informe cualquier error en el material proporcionado o en el conjunto de datos!
•	Explorando SynD con NILMTK
•	Ejemplo de desagregación simple usando NILMTK
Historia
•	Abril de 2020: ¡SynD se hace público!
•	Octubre de 2019: ¡el repositorio se activa!
Cuadernos Notebooks
Los tenemos en  SynD/examples/
 - simple_disaggregation.ipynb
 - synd_exploration.ipynb

** JackKelly ( 6años)
Github
Enlaces a github:  Prototipo Neuralnilm https://github.com/JackKelly/neuralnilm_prototype 
indice :https://github.com/JackKelly/neuralnilm 
Resumen
Neuralnilm: Redes neuronales profundas aplicadas a la desagregación energética .¡Tenga en cuenta que este código nunca se terminó! ¡Está incompleto y sin soporte! Por favor, no lo use a menos que realmente sepa lo que está haciendo. ¡Consulte su código de prototipo de Neural NILM para ver exactamente lo que implementé en el artículo de Neural NILM! Su mejor opción si desea volver a implementar Neural NILM probablemente sería comenzar desde cero utilizando un marco moderno como TensorFlow, y tal vez usar nilmtk para ayudar a cargar los conjuntos de datos. Esta es una reescritura completa del prototipo Neural NILM .
Tenga en cuenta también que este código neuralnilm solo se proporciona como prueba de concepto y como referencia. Todavía no está en un estado en el que sea fácil para otras personas ejecutar el código. Desafortunadamente, el autor no tendrá tiempo para trabajar en el código Neural NILM o para brindar soporte en cualquier momento en el futuro previsible. Por lo tanto, el código se proporciona 'tal cual' sin ningún soporte en este momento. Tal vez algún día tenga tiempo para admitir el código o para actualizar el código.
Dicho esto, si está realmente decidido a leer y comprender este código, aquí hay una descripción detallada de la arquitectura básica:
Cada 'experimento' se define en un script de Python en experiment_definitions/. Cada uno de estos archivos debe tener una run función que, bueno, ¡ejecuta el experimento!
experiment_definitions/también debe incluir un archivo de texto llamado job_list.txt que es solo una lista de nombres de experimentos como e575. La secuencia de comandos scripts/run_experiments.py mira job_list.txt para encontrar el próximo trabajo que se ejecutará. Después de que se completa cada trabajo, run_experiments.py elimina ese trabajo del job_list. De esta manera, es posible agregar, eliminar o reordenar trabajos job_list mientras se está ejecutando un experimento.
El código reutilizable que constituye la mayor parte del paquete NeuralNILM vive en neuralnilm/neuralnilm. net.py incluye una Net clase que maneja la construcción de cada red neuronal. trainer.py incluye una Trainer clase que entrena cada red y envía métricas a la base de datos de Mongo.
neuralnilm/neuralnilm/data incluye los mecanismos de carga y transformación de datos. Está diseñado para ser muy modular para que pueda mezclar y combinar fácilmente fuentes de datos, pasos de preprocesamiento y redes. Para obtener una descripción general rápida de cómo funciona todo esto, eche un vistazo a algunos de los archivos de Python en el experiment_definitions directorio.
neuralnilm/neuralnilm/monitor contiene los mecanismos para cargar métricas y metadatos de la base de datos de Mongo y trazarlos.
Requisitos : Consulte requirements.txt los paquetes de Python necesarios. También requiere Mongo DB.
Configuración: Necesita crear un ~/.neuralnilm archivo de texto para especificar algunos parámetros. Por favor mira example_config_file.
Acceso remoto a MongoDB: Ver http://www.mkyong.com/mongodb/mongodb-allow-remote-access/
Notebooks
Empezando: Aquí hay un breve cuaderno de iPython para mostrar cómo cargar activaciones desde UKDALE 
Monitor.ipynb
Neural NILM test.ipynb  make num_seqs_to_plot a member variable
NeuralNILM design.ipynb Now sending metrics to a Mongo DB :)
extract_activations.ipynb adding notebook to show how to load activations
sockets-client.ipynb playing with sockets
sockets.ipynb playing with sockets

** GJW (hace 6 años)
Github
Enlace a github: https://github.com/gjwo/nilm_gjw_data 
Enlace a Gjw metadata https://github.com/gjwo/nilm_metadata 
Resumen
Repositorio de datos de monitoreo de carga no intrusiva y convertidor de datos para NILMTK Este repositorio son datos de monitoreo de electricidad recopilados por el autor, y los metadatos y el convertidor necesarios para importar los datos al kit de herramientas de monitoreo de carga no intrusiva https://github.com/nilmtk/nilmtk /  Puede encontrar más información sobre los metadatos aquí https://github.com/nilmtk/nilm_metadata  y la documentación se puede encontrar aquí https://github.com/nilmtk/nilmtk.github.io 
    directory and file structure
    nilm_gjw_data
        building<1>
            elec
                4-POWER_REAL_FINE <date> Dump.csv
                5-POWER_REACTIVE_STANDARD <date> Dump.csv
                ...
                meter1.data <----------------- output file in CSV format
        ...
        building<n>
        HDF5
            nilm_gjw_data.hdf5 <-------------- output file in HDM5 format
        metadata
            building1.yaml
            dataset.yaml
            meter_devices.yaml
        <other files such as>
        gjw_converter.py  <------------------ the converter code
        gjw_converter_test.ipnb <------------ runs of the converter code in iPython Notebook

Notebooks 
 NOTEBOOK 6 años atrás en  https://github.com/gjwo/nilm_gjw_data/tree/master/notebooks 
-	Building 1 power sequencing.ipynb  .Initial load of power sequence data for 2013-12-03
-	Building_1_power_sequencing.ipynb  experimatation with disaggregation
-	Refresh_metadata.ipynb . production run with updated energy data and metadata
-	Untitled.ipynb  experimatation with disaggregation
-	converter_experiments.ipynb . notebooks moved to separate folder, graphing two metrics FAQ answer a…
-	disaggregation-CO.ipynb . experimatation with disaggregation
-	disaggregation-hart-CO-active_only.ipynb experimatation with disaggregation
-	disaggregation-hart-active_and_reactive(holiday).ipynb .experimatation with disaggregation .
-	disaggregation-hart-active_and_reactive(normal).ipynb . experimatation with disaggregation
-	disaggregation-hart-active_only.ipynb experimatation with disaggregation
-	disaggregation.ipynb. initial attempt at disaggregation training with errors
-	gjw_converter_test.ipynb . experimatation with disaggregation
-	graphing_two_metrics.ipynb. experimatation with disaggregation
-	test_gjw.ipynb.notebooks moved to separate folder, graphing two metrics FAQ answer a…

** OdysseasKr  (2019)
Github
Enlace a github: Desagregador Neuronal https://github.com/OdysseasKr/neural-disaggregator 
Resumen
desagregador neuronal. Implementaciones de desagregadores NILM usando Neural Networks, usando NILMTK y Keras. La mayoría de las arquitecturas se basan en Neural Nilm:Deeep Neural Networks Applied to Energy Disaggregation  por Jack Kelly y Willian Knottenbelt
Los modelos implementados son:
•	Denoising autoencoder (DAE) como se menciona en Neural NILM (ver ejemplo )
•	Red recurrente con neuronas LSTM como se menciona en Neural NILM (ver ejemplo )
•	Red recurrente con GRU. Una variación de la red LSTM para comparar los dos tipos de RNN (ver ejemplo )
•	Ventana GRU. Una variación de la red GRU que utiliza una ventana de datos como entrada. Como se describe en Enfoque de ventana deslizante para la desagregación de energía en línea utilizando redes neuronales artificiales de Krystalakos, Nalmpantis y Vrakas (ver ejemplo )
•	Secuencia corta a red de puntos basada en la arquitectura en papel original (ver ejemplo )
Nota: Si está buscando la carpeta LookbackGRU, se ha movido a http://github.com/OdysseasKr/online-nilm . Intento mantener limpio este repositorio utilizando el mismo tren y conjuntos de prueba para todas las arquitecturas.
Notebooks
neural-disaggregator/DAE/ DAE-example.ipynb
neural-disaggregator/GRU/ GRU-example.ipynb
neural-disaggregator/RNN/ RNN-example.ipynb
neural-disaggregator/ShortSeq2Point/ ShortSeq2Point-example.ipynb
neural-disaggregator/WindowGRU/ Window-GRU-example.ipynb

** Josemao (2016)
Github
Enlace a github: Nilmtk en 4 pasos https://github.com/josemao/nilmtk_practicas 
Resumen 
Non-Intrusive Load Monitoring (NILM) es una colección de técnicas y algoritmos de machine learning orientados a desagregar el consumo total de una casa en consumos individuales de electrodomésticos.Estas prácticas sigue algunos de los ejemplos propuestos en: http://nilmtk.github.io/ 
1 - Python científico: Aquí explica algunos de los conceptos básicos para el uso de las librerías necesarias de NILM.
-	numpy: operaciones matemáticas de arrays y matrices
-	matploblib: para gráficas
-	pandas: herramienta de análisis de datos a gran escala de manera eficiente
2 - Introducción a NILMTK: NILMTK es una herramienta de análisis de datasets de NILM. Contiene funciones específicas para el análisis detallado y rápido del consumo eléctrico. Además, sirve de plataforma para los investigadores de NILM para comparar sus algoritmos con métricas estándar sobre varios datasets. Aprenderemos los conceptos básicos. Para más información, consultar la documentación en: https://github.com/nilmtk/nilmtk 
Los datasets que utiliza son:
-REDD: monitorización del consumo energético de 6 casas diferentes en Estados Unidos: 2 casas a alta frecuencia (12KHz de corriente y voltaje) y 4 casas a baja frecuencia (10 segundos por muestra de la potencia activa) http://redd.csail.mit.edu/
-UK-DALE : Monitorización de una casa en Inglaterra durante 2 años a alta frecuencia y baja frecuencia: 16KHz de corriente y voltaje y 1 segundo de potencia activa, reactiva y aparente. http://www.doc.ic.ac.uk/~dk3810/data/
-IAWE:  Monitorización de una en India durante 73 días a 1 segundo. Parámetros: potencias activa, reactiva y aparente, voltaje, corriente y factor de potencia. http://iawe.github.io/
3 - Previo a la desagregación: gráficas y estadísticas: Antes de realizar la desagregación, podemos analizar el consumo general desde el smart meter para obtener información interesante sobre la actividad en la vivienda. Asímismo, si se tiene información sobre el consumo individual de algunos dispositivos (groundtruth) mediante la instalación de smart-plugs, podemos obtener los patrones de consumo de distintos dispositivos que nos ayude a mejorar nuestro algoritmo.
4 - Desagregación: Métodos supervisados y no supervisados. Aquí se estudiará distintos algoritmos de desagregación. Primeramente, se introducirá una extensión del algoritmo de Hart para desagregar de forma supervisada. A continuación, se presentan dos algoritmos no supervisados: cadenas factoriales de Markov (FHMM) y optimización combinatoria (CO); comparándolos mediante el uso del mismo dataset y de las mismas métricas.
Notas: Máquina virtual Linux: usr(nilm) y pwd(nilm). Enlazar carpeta data como carpeta compartida en Virtual Box. Mantener el nombre data. Es necesaria la instalación previa de nilmtk: https://github.com/nilmtk/nilmtk/blob/master/docs/manual/user_guide/install.md 
Cuadernos de Jupyter
1 - Python cientifico (Introduccion) (solucion).ipynb
1 - Python cientifico (Introduccion).ipynb
2 - Introdución a NILMTK (solucion).ipynb
2 - Introdución a NILMTK.ipynb
3 - Estudio previo a la desagregacion (busqueda de patrones) (solucion).ipynb
3 - Estudio previo a la desagregacion (busqueda de patrones).ipynb
4a - Desagregacion y metricas (algoritmo supervisado).ipynb
4b - Desagregacion y metricas en NILMTK (algoritmos no supervisados).ipynb

** AriasSilva (2020)
Github
Enlace a github: Nilmtk en 6 pasos  https://github.com/AriasSilva/nilmtk 
Resumen 
DEPS: NILM Dataset
Este repositorio es parte del Trabajo Final de Máster: "Desagregación de la demanda usando Non-Intrusive Load Monitoring Toolkit (NILMTK)” conducente al grado de Máster en Sistemas Inteligentes de Energía y Transporte con especialidad en Smart Cities del alumno Andrés Arias Silva. El proyecto cuenta con la colaboración de los docentes Dr. Enrique Personal y D. Antonio Parejo de la Universidad de Sevilla.
El objetivo de este trabajo es mostrar el uso y potenciales aplicaciones de la herramienta de desagregación de la demanda Non-Intrusive Load Monitoring Toolkit (NILMTK) a través de la implementación de un caso real que involucra la creación de un dataset de uso público con datos de energía del Aula 2.2 Bis de la Escuela Politécnica Superior de la Universidad de Sevilla.
El dataset denominado DEPS (Dataset de la Escuela Politécnica Superior) se encuentra en formato HDF5 y puede ser descargado en el siguiente enlace usando la contraseña deps2020. Adicionalmente, se proporciona un convertidor para ser utilizado en NILMTK en caso de ser requerido el cual se encuentra en este repositorio.
NILM
La desagregación de la demanda, también conocida como Non-Intrusive Load Monitoring (NILM), se define como una técnica computacional para estimar el consumo individual de energía eléctrica de diversos dispositivos utilizando la lectura agregada de un solo medidor [1][2]. Este concepto ha tomado relevancia entre los investigadores en la última década tal como lo indica este análisis de publicaciones NILM:
Dentro de sus beneficios se destacan los siguientes:
•	Información detallada de la factura eléctrica al consumidor (prosumidor)
•	Aplicaciones en programas de respuesta a la demanda o demand response (DR)
•	Identificación de averías y consumo ilegal de energía
En la siguiente figura se muestra un ejemplo de desagregación de la demanda usando el dataset REDD:
   
NILMTK
NILMTK es un kit de herramientas de código abierto diseñado específicamente para permitir un acceso fácil y brindar un análisis comparativo de algoritmos de desagregación de demanda en diversos datasets. NILMTK proporciona un pipeline completo, intérpretes de diversos datasets y métricas de precisión, lo que reduce la barrera de entrada para investigadores y desarrolladores. La siguiente figura muestra el pipeline de NILMTK:
   
Se recomienda instalar NILMTK bajo un enviroment de paquetes de Python, específicamente Anaconda. Una guía de instalación de NILMTK en Windows se encuentra en el siguiente enlace.
Adicionalmente, toda la información sobre NILMTK se encuentra en nilmtk.github.io.
Nuevo Dataset DEPS
Dentro de las instalaciones de la Escuela Politécnica Superior de la Universidad de Sevilla se encuentra el Aula 2.2 Bis, la cual está equipada con un cuadro eléctrico con diversos medidores. Estos medidores registran el consumo agregado y consumos individuales de determinados dispositivos del aula. Gracias a esto, se han registrado datos de consumo y se han almacenado junto con sus metadatos en un dataset que considera las siguientes fechas:
Desde el lunes 24/02/2020 a las 00:00:00 hrs. al jueves 27/02/2020 a las 23:59:59 hrs.
Desde el lunes 02/03/2020 a las 00:00:00 hrs. al viernes 06/03/2020 a las 23:59:59 hrs.
Adquisición de datos
DEPS contiene datos agregados y metadatos de un sistema trifásico (R, S ,T) de seis dispositivos de consumo, conectados a diferentes fases. La siguiente tabla resume las medidas registradas en el dataset.
Medidor	Medidas Registradas	Periodo de Muestreo
1x Medidor principal trifásico (RST)	P, Q	1 segundo
3 x Medidores de fase (R, S y T)	P, Q, V, I	1 segundo
6 x Medidores de Dispositivos	P, Q, V, I	1 segundo
El medidor principal (Main_RST) mide la potencia P y Q agregada, también opera como medidor por fase (Main_R, Main_S y Main_T) permitiendo registrar P, Q, V e I para cada una de ellas. En cuanto a los dispositivos, se cuenta con mediciones de P de dos grupos de iluminación (Lights_1 y Lights_2), mediciones de P, Q, V e I para tres equipos de aire acondicionado (HVAC_1, HVAC_2 y HVAC_4) y un rack de equipos informáticos (Rack).
En la siguiente figura se muestra un esquema unilineal eléctrico de los medidores.
   
Convertidor NILMTK
Para la creación de un dataset compatible con NILMTK es necesario contar con un convertidor que estructure los datos y sus metadatos en el formato HDF5. En el presente trabajo se utiliza como referencia el convertidor REDD previamente desarrollado, incorporándole modificaciones para que los datos extraídos desde el Aula 2.2 Bis sean compatibles.
El convertidor y los metadatos se pueden descargar desde este enlace.
Para su mejor comprensión, se ha elaborado una guía de implementación y uso del convertidor
Análisis y modelos de desagregación
Con la ayuda de las diversas funciones de NILMTK se analizan datos y metadatos del dataset DEPS. En los siguientes notebooks se presentan diversos análisis y preprocesamiento necesario para posteriormente generar y comparar diversos modelos de desagregación usando varios periodos y métodos de muestreo basados en los algoritmos CO (Combinatorial Optimisation) y FHMM (Factorial Hidden Markov Model):
Análisis - NILMTK-DF
Análisis - Diagnóstico y Estadísticas
Preprocesamiento
Entrenamiento
Validación
Desagregación
Los resultados de los análisis de los diferentes modelos muestran, bajo diferentes métricas, que el rendimiento del modelo FHMM entrenado con datos de la mediana de la potencia activa con un periodo de 30 minutos posee un buen desempeño para su implementación. En la siguiente imagen se muestra un extracto de los análisis a las métricas obtenidas de los diferentes modelos implementados.
Reporte de desagregación
Utilizando el modelo con el mejor desempeño en el dataset DEPS, se ha implementado un código para generar un reporte interactivo básico en HTML de los resultados de la desagregación.
A continuación se muestra una captura de pantalla del reporte, el cual puede ser consultado en el siguiente enlace y cuyo código escrito en Python se encuentra acá.
 
Conclusiones del Trabajo
La desagregación de la demanda se presenta como una técnica innovadora capaz de enfrentar de manera directa el problema de la eficiencia energética brindando información sobre los consumos eléctricos utilizando métodos no intrusivos.
Este trabajo demuestra que el uso de una herramienta como NILMTK, dedicada a la investigación, puede utilizarse en aplicaciones reales sin perder su esencia. Adicionalmente, como principal aporte del presente trabajo, se encuentra a implementación del nuevo dataset DEPS. Este dataset es de carácter público, por lo cual se ponen a disposición de quienes estén interesados, los datos recolectados y las herramientas necesarias para que estos sean compatibles con NILMTK.
Cuadernos de Jupyter
1.Análisis - NILMTK-DF.ipynb
2.Análisis - Diagnóstico y Estadísticas.ipynb
3.Preprocesamiento.ipynb
4.Entrenamiento.ipynb
5.Validación.ipynb
6.Desagregación.ipynb
Funciones modificadas en NILMTK.ipynb

** bhushan23 (2017)
*** Github
Enlace a github  LSTM-SplitterdData Microhondas https://github.com/bhushan23/SmartOff/ 
*** Resumen
SmartOff Enfoque de aprendizaje automático e Internet de las cosas para apagar los dispositivos cuando no se utilizan para ahorrar consumo de energía.
*** Objetivo
La idea es construir un sistema combinando métodos de IoT y Machine Learning para una predicción precisa del uso de un dispositivo en particular a partir de datos residenciales, y cortar el suministro de energía a ese dispositivo cuando no se esté usando. Esto ayudará a reducir el desperdicio de energía de todos los dispositivos que consumen algo de energía en el modo de espera durante la mayor parte del día cuando no están en uso.
*** Acercarse
•	El proyecto se divide en partes de hardware (IoT) y software (aprendizaje automático) de la siguiente manera: Internet de las cosas: el objetivo final es crear un sistema que no necesite mucha intervención humana para funcionar correctamente. Proponemos los siguientes dos enfoques:
•	Conecte localmente un dispositivo inteligente al dispositivo que se conectará a una red central. Centralice todo y gestione los dispositivos desde una red inteligente. El objetivo en ambos enfoques es el mismo, es decir, cortar el suministro de energía al aparato cuando no esté en uso. Aprendizaje automático: para hacer que los dispositivos sean inteligentes, utilizamos el aprendizaje automático para analizar el comportamiento del consumidor. Analizar el comportamiento, aquí, significa reconocer los patrones de uso del usuario de un dispositivo en particular, como los rangos de tiempo cuando los dispositivos se usan más o los rangos de tiempo cuando los dispositivos están en modo de espera la mayoría de las veces y pronto. Así, el sistema sabrá cuándo se usa más el dispositivo y cuándo no. Entonces, podemos cortar la fuente de alimentación. Planeamos hacer que los modelos se adapten fácilmente a los nuevos patrones de uso. Por lo tanto, incorporaremos Transfer Learning.
Colaboradores
•	Bhushan Sonawane
•	Nishant Borude
•	Ishupreet Singh
Sobre
Enfoque de aprendizaje automático e Internet de las cosas para apagar los dispositivos cuando no se utilizan para ahorrar consumo de energía.

*** Cuaderno de Jupyter
https://github.com/bhushan23/SmartOff/blob/master/LSTM-SplittedData-Microwave.ipynb 
 
 Repositorios de código sobre el NILM en Python 


** Gissemari (2018)
*** Github
Enlace a github: Desagregación vrnn https://bitbucket.org/gissemari/disaggregation-vrnn/src/master/ 
VRNN-DIS1 y VRNN-DIS-ALL
Resumen
ALGUNOS CONOCIMIENTOS PREVIOS SOBRE EL MODELO
Estos modelos se construyen en base al modelo VRNN implementado en theano por sus autores aquí: https://github.com/jych/nips2015_vrnn. Se ejecuta con python2.7 y el resto de las versiones de las bibliotecas se pueden verificar en el archivo .yml.    Crear y activar el entorno desde latentVar.yml
 ESTRUCTURA DE ESTE REPOSITORIO
bibliotecas auxiliares: donde se guardan los repositorios mencionados anteriormente
Desagregación- [conjunto de datos]: están organizados de manera similar, una carpeta para los metadatos, una carpeta donde se guardan los archivos originales y preprocesados del conjunto de datos, el código y la salida.
latentVar.yml: entorno conda con todos los módulos y bibliotecas instalados
BIBLIOTECAS AUXILIARES
Este modelo utiliza algunos otros módulos que han sido modificados e incluidos en este repositorio:
1) NEURALNILM: cargue el archivo .h5 con el módulo NIMLTK y luego procese el conjunto de datos UKDALE para obtener instancias con cierta activación de destino (dispositivo) o sin ella. Repositorio original en https://github.com/JackKelly/neuralnilm  
2) NILMTK y NILM_METADATA: Carga los archivos .h5, se realizan pocos cambios basados en los originales principalmente por problemas de versiones. Originales https://github.com/nilmtk/nilmtk  y https://github.com/nilmtk/nilm_metadata 
2) CLE: Usado para entrenamiento y monitoreo modificado principalmente para agregar variables a monitorear y los mecanismos de muestreo de programación. Repositorio original: https://github.com/jych/cle )
2)  SUB REPOSITORIOS. Cada uno de los repositorios de conjuntos de datos se divide en 3 subcarpetas:
 1) Metadatos: estadísticas y cifras para respaldar algunos de los parámetros que seleccionamos, como la longitud de las instancias (secuencias), el valor mínimo a considerar que el dispositivo está encendido, el valor máximo a considerar es apagado, etc.
 2) Conjuntos de datos: carpeta donde deben colocarse los datos originales (.h5). También contiene una subcarpeta PICKLES para guardar algunos datos preprocesados, especialmente para experimentos repetidos. 
 3) Preprocesamiento: donde se almacena la lógica del preprocesamiento. Su función principal es muestrear las instancias en función de los parámetros del archivo de configuración, como la frecuencia de muestreo (período), la longitud de la secuencia, la superposición o no para el entrenamiento, etc. 
 4)  VRNN_theano_version: donde se almacenan los modelos y la salida de los modelos VRNN. . También contiene
PARAMETROS
Los parámetros se definen dentro de los archivos de código como edificios, ELECTRODOMÉSTICOS (en el archivo de preprocesamiento), ventanas (rango de fechas para cargar y / o rangos para separar para entrenamiento y prueba). Sin embargo, la mayoría de los parámetros son similares en todos los modelos vrnn y se leen desde un archivo de configuración:
[PATHS] – pickle Model es el archivo con el modelo mejor guardado a partir del cual leer los parámetros aprendidos. Se usa principalmente en los archivos de prueba - data_path es la ruta de los archivos de datos: ... / PecanStreet-dataport / datasets - save_path es la carpeta donde se guardará la salida, generalmente ... / VRNN_theano_version / output
[PREPROCESSING] - period: la tasa de frecuencia a la que se recopilan los pasos de tiempo en los datos
 - n_steps: longitud de la secuencia 
- stride_train: paso o espacio entre instancias en el conjunto de entrenamiento .- 1: cuando typeLoad es 0 (porque usará 1 para tienen instancias superpuestas en el entrenamiento, pero usarán n_steps para el paso en las instancias de prueba)
 - n_steps: cuando typeLoad es 1 (porque como elegimos instancias al azar, debemos garantizar que las instancias de prueba o cualquier parte de ellas también sean parte del conjunto de entrenamiento) 
- stride_test: paso o espacio entre instancias en el conjunto de prueba (tiene que ser igual o mayor que la longitud de la secuencia para evitar la superposición) 
- typeLoad: - 0 para la carga original donde el conjunto total se divide en formación, validación y pruebas en un orden específico. - 2 Construyendo instancias de forma aleatoria, sin solapamientos y asignando un número específico para entrenar, probar y validar. A diferencia del trabajo de Kelly, decidimos no dividir el entrenamiento, los conjuntos de validación por ventanas de tiempo, sino tener una ventana única donde dividimos por porcentaje las instancias obtenidas para los conjuntos de entrenamiento y validación. - 1 (no se usa para este conjunto de datos. Para ukdale: carga de Kelly)
[ALGORITMO] - monitoring_freq: número de lotes de entrenamiento tras los cuales se realiza un proceso de validación. Digamos que tenemos 100 mini-lotes y el monitoring_freq es 20. El proceso de validación se haría solo después del proceso de los 10 mini-lotes. - época: número de iteraciones en las que se procesaron todos los mini lotes. Significa que, en una época, se procesaron 100 mini lotes. - batch_size: tamaño del mini-lote - kSchedSamp: velocidad de convergencia para la desintegración sigmoidea inversa. Tomado de https://arxiv.org/abs/1506.03099 - lr: tasa de aprendizaje inicial
[MODELO] - x_dim: señal agregada (1) - y_dim: señal desagregada (número de aparatos) - z_dim: unidades en la capa z - k_target_dim: (num_k) número de distribuciones gaussianas de mezcla - rnn_dim: número de unidades para el laye recurrente - q_z_dim: tamaño de unints para el extractor de características de la distribución del codificador - p_z_dim: tamaño de unints para el extractor de características de la distribución anterior - p_x_dim: tamaño de las unidades para la distribución del decodificador - x2s_dim: tamaño del extractor de características para la señal x - y2s_dim: tamaño del extractor de características para las señales y (desagregadas) - z2s_dim: tamaño del extractor de características para la z (variable latente) - typeActivFunc: función de activación para el mu (parámetro theta) de la distribución del decodificador
UTILS - SOLUCIONES DE ERRORES
PARA INSTALACION:Al instalar theano con conda, falta instalar python2x. Así que cópialo de algún lado
 NILM en línea  https://github.com/OdysseasKr/online-nilm
Aquí puede encontrar el código para las dos arquitecturas de redes neuronales propuestas  :"Enfoque de ventana deslizante para la desagregación de energía en línea utilizando redes neuronales artificiales, O. Krystalakos, C. Nalmpantis y D. Vrakas, SETN, 2018" (Documento completo: 3200947.3201011)
Todo el código está escrito con Keras y Tensorflow.
Puede encontrar versiones compatibles con NILMTK de estas redes en https://github.com/OdysseasKr/neural-disaggregator.Requiere NILMTK para ejecutarse. Puede encontrarlo aquí: https://github.com/nilmtk/nilmtk .
Las redes
En cada carpeta puede encontrar un archivo README con instrucciones sobre cómo ejecutar los experimentos. Para cada red encontrará 4 archivos Python:
-	experiment.py: Código para ejecutar el experimento. Cada experimento incluye entrenamiento y evaluación de la red.
-	gen.py: Descarga todos los recursos necesarios y genera un conjunto de trenes y un conjunto de pruebas.
-	model.py: La arquitectura de red.
-	metrics.py: las métricas utilizadas para evaluar la red.
Los experimentos están disponibles para los siguientes dispositivos del conjunto de datos UKDALE:
-	Lavavajillas
-	Nevera
-	Pava
-	Microonda
-	Lavadora
Obras relacionadas en NILM neuronal: https://arxiv.org/pdf/1507.06594.pdf  y Secuencia original a punto: https://arxiv.org/pdf/1612.09106v3.pdf   

** Maechler (2018)
*** Github
Enlace a github Nnilm https://github.com/maechler/nnilm 
*** Resumen
NNILM - Monitoreo de carga neuronal no intrusiva.Este proyecto es una reimplementación de la arquitectura de rectángulos de Jack Kelly basada en Keras y NILMToolkit .
Descripción general de la red
Comparación de referencia
Una comparación de la arquitectura de rectángulos en este repositorio con la implementación original de Jack Kelly en el conjunto de datos UK-DALE.
Predicciones
Predicciones para un verdadero positivo, un verdadero negativo y un ejemplo de falso positivo para un lavavajillas.
Visualización de la primera capa de convolución
Filtros aprendidos
La siguiente imagen muestra los 16 filtros aprendidos de la primera capa de convolución.
 
Activaciones para una muestra negativa
La siguiente imagen muestra las activaciones de la primera capa de convolución dada una muestra negativa.
 
Activaciones para una muestra positiva
La siguiente imagen muestra las activaciones de la primera capa de convolución dada una muestra positiva. Por tanto, los dos filtros resaltados son interesantes. El primer filtro parece haber aprendido a detectar cambios escalonados en la señal de entrada. El segundo filtro parece haber aprendido a pasar la señal de entrada sin procesar a la siguiente capa.
 
Desarrollo
Configurar virtualenv
Usamos Python 2 como lenguaje de programación, porque hay algunas dependencias que no son compatibles con Python 3.
pip install virtualenv
python -m virtualenv env
source env/bin/activate
Si configura virtualenv con Python 3, debe cambiar a Python 2: virtualenv --python=/usr/bin/python2.7 env
Instalar dependencias
Debido a una dependencia fallida hmmlearn, usamos la opción --no-dependencies. El módulo hmmlearnno es realmente necesario en esta implementación.
pip install --no-dependencies -r requirements.txt
pip install -e .
Deja virtualenv
deactivate
Conjunto de datos
Es posible utilizar cualquier conjunto de datos compatible con NILMToolkit. Debe convertir el conjunto de datos a un archivo .h5 utilizando los convertidores proporcionados por NILMToolkit y luego colocarlo en la carpeta ./data: https://github.com/nilmtk/nilmtk/tree/master/nilmtk/dataset_converters
Ejecutar entrenamiento
Ejecutar entrenamiento durante 30 épocas: python nnilm/train.py dish_washer_redd -s0 -e30
Reanudar el entrenamiento a partir de la época 30: python nnilm/train.py dish_washer_redd -s30 -e40
Ejecute el entrenamiento en el clúster de GPU: nohup python nnilm/experiments/train_hpc.py --gpu=2 &
Ejecutar predicción
Conjunto de datos públicos: python predict.py dish_washer_eco
Predicción CSV: python nnilm/experiments/csv_predictor.py -ddish_washer_redd -idata/aggregated_power.csv -s01-04-2018 -e08-04-2018
Experimentos
La carpeta nnilm/experimentscontiene archivos que se han utilizado para ejecutar mis experimentos. Muestra cómo los scripts de este repositorio se pueden usar en otro proyecto.

** Compsust ( ojo está escrito en matlab)

*** Github
Enlace a github ALIP_NILM https://github.com/compsust/ALIP_NILM 
*** Resumen
ALIP_NILM:Programación de enteros lineales asistidos (ALIP) Monitoreo de carga no intrusivo (NILM)
Copyright (C) 2016 por Md Zulfiquar Ali Bhotto.
Si utiliza  el código en su investigación, cite este artículo. Los detalles actuales de la cita son:
MZA Bhotto, S. Makonin e I. Bajic, “Disgregación de carga basada en la programación de enteros lineales asistida”, IEEE Transactions on Circuits and Systems II: Express Briefs , vol. 64, no. 7, págs. 792-796, 2016.
DOI: 10.1109 / TCSII.2016.2603479
URL de preimpresión: http://arxiv.org/abs/1603.07417




** Loneharoon (2018)
*** Github
Enlace a github:  Desagregador de energia GSP  https://github.com/loneharoon/GSP_energy_disaggregator 
Resumen GSP_energy_disaggregator
Este código de Python se implementó traduciendo el código de Matlab desarrollado por los autores del artículo titulado "En una solución sin entrenamiento para el monitoreo de carga de dispositivos no intrusivos utilizando procesamiento de señales de gráficos". Tenga en cuenta que no tengo el código de Matlab conmigo ahora, así que no me envíe un correo electrónico para obtener los archivos de Matlab.
Uso
El directorio contiene dos archivos py: 
	gsp_disaggregator.py: es el archivo principal. 
	 gsp_support.py: Contiene las funciones de apoyo llamadas por gsp_disaggregator. Además, contiene un archivo de datos de demostración utilizado por gsp_disaggregator.py. Lea los comentarios proporcionados en gsp_disaggregator.py para comprender qué hacen las diferentes funciones.
Citación
Si usa esta copia del código en su trabajo, cite el documento "En una solución sin entrenamiento para el monitoreo de carga de dispositivos no intrusivos usando procesamiento de señales de gráficos".
Lanzamientos
2018-12-29 Se agregó la capacidad de etiquetar dispositivos desagregados en comparación con una base de datos de firmas usando DTW o FastDTW y algunas características pequeñas. @aleonnet

** Louisyuze
*** Github
Enlace a github  Machine LeaRNING https://github.com/louisyuzhe/MachineLearning_NILM 
*** Resumen
Neural NILM: redes neuronales profundas aplicadas a la desagregación energética
Campo de investigación: enfoques de aprendizaje automático para NILM (monitoreo de carga no intrusivo)
Presentado por: Yuzhe Lim
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 


Jonathanrpereira
Github
Enlace a github  Smart energy Monitor https://github.com/jonathanrjpereira/Smart-Energy-Monitor 
Resumen
El objetivo del Smart Energy Monitor es predecir con precisión la factura de electricidad mensual del hogar utilizando un hardware mínimo y adquiriendo datos eléctricos en una única ubicación (en lugar de sensores individuales por aparato). Hacemos esto analizando las firmas de corriente y potencia de todos los dispositivos activos y pasamos esta información a través de un clasificador Naive Bayes que nos ayuda a obtener los dispositivos activos que pueden usarse para calcular la cantidad de unidades consumidas por dispositivos de carga individuales.
Características:
•	Detecta cuándo un dispositivo en particular ha cambiado de estado (Encendido / Apagado / Otro).
•	Clasifica los aparatos de carga activa analizando las señales eléctricas medidas que se han obtenido de un solo lugar.
•	Seguimiento del consumo a nivel de dispositivo individual.
•	Predicción de facturas de electricidad.
•	Hardware utilizado para obtener firmas de potencia actual, activa y reactiva de dispositivos individuales para crear conjuntos de datos de alta calidad.
Prerrequisitos
Hardware:
•	Raspberry Pi con Raspbian
•	Arduino Nano
•	Transformadores de corriente y voltaje
•	Componentes electrónicos adicionales necesarios para el circuito de detección de cruce por cero.
Software:
•	Matraz - Microframework de aplicaciones web
•	Dash by Plotly: marco analítico de aplicaciones web (opcional)
Laboral
Algoritmo combinatorio (CA):
El algoritmo combinatorio es un método de fuerza bruta para determinar los dispositivos activos. CA encuentra la combinación óptima de estados del dispositivo, lo que minimiza la diferencia entre la suma de la potencia prevista del dispositivo y la potencia agregada observada, sujeto a un conjunto de modelos de dispositivo. La complejidad de la desagregación para T intervalos de tiempo es:
 
donde N es el número de dispositivos y K es el número de estados del dispositivo. Dado que la complejidad de CA es exponencial al número de dispositivos, el enfoque solo es manejable computacionalmente para una pequeña cantidad de dispositivos modelados. Por lo tanto, optamos por utilizar un clasificador Naive Bayes para determinar los dispositivos activos. Se utiliza un ejemplo de demostración de juguete para visualizar cómo aumenta el número de cálculos a medida que aumenta el número de aparatos.
Medición de potencia:
Podemos medir la corriente pico muestreando la línea de alimentación principal hasta que obtengamos los valores máximos y mínimos de tensión pico (es decir, el valor máximo medido en cada dirección). Luego podemos calcular el valor de voltaje RMS a partir del voltaje pico a pico. Para el ACS712 podemos convertir el valor de voltaje RMS en un valor de corriente RMS usando el factor de escala dado en la hoja de datos [ 1 ]. A continuación, podemos medir la potencia que se consume utilizando los valores RMS de voltaje y corriente.
 
Pasos para encontrar la potencia de una onda sinusoidal con una compensación de cero voltios:
•	Encuentre el voltaje pico a pico (Vpp) del sensor de corriente ACS712.
•	Divida Vpp por 2 para obtener el voltaje máximo en una dirección.
•	Multiplique el voltaje pico por 0.707 para obtener el voltaje RMS para el ACS712.
•	Convierta el voltaje RMS en corriente RMS multiplicando por el factor de escala dado para el modelo ACS712 en particular.
•	Multiplique el voltaje medido con la corriente RMS para encontrar la potencia consumida por las cargas.
 
Análisis de estado estable: 
La potencia real y la potencia reactiva son dos de las firmas de estado estable más utilizadas en NILM para rastrear el funcionamiento de encendido / apagado de los electrodomésticos. La potencia real es la cantidad de energía consumida por un aparato durante su funcionamiento. Si la carga es puramente resistiva, las formas de onda de corriente y voltaje siempre estarán en fase y no habrá energía reactiva. Para una carga puramente reactiva, el cambio de fase será de 90 grados y no habrá transferencia de potencia real. Por otro lado, debido a los elementos inductivos y capacitivos de la carga, siempre hay un cambio de fase entre las formas de onda de corriente y voltaje que genera o consume una potencia reactiva respectivamente. [ 2 ]
Supervisión de cambios en la corriente y la potencia:
La corriente consumida por la carga es el primer parámetro que se utiliza para clasificar los distintos dispositivos de carga. El sensor de corriente nos proporcionará el valor instantáneo de la corriente total consumida por todas las cargas conectadas al Smart Energy Monitor. Para obtener el valor de la corriente consumida por cada dispositivo de carga individual, debemos calcular la diferencia entre cada una de las muestras de corriente consecutivas.
 
Como se muestra en la figura anterior, podemos ver que cuando se enciende el aparato de carga A, el cambio en la corriente es 10, cuando B se enciende después de A, el cambio en la corriente es 25 pero la corriente total es 35 y finalmente cuando B se APAGA el cambio en la corriente es 25 mientras que la corriente total consumida es 10.
El cambio total en la corriente que ocurre cuando un aparato de carga se enciende / apaga puede no reflejarse correctamente entre las dos muestras consecutivas. En cambio, el cambio total en la corriente puede reflejarse en más de dos muestras de corriente consecutivas, dependiendo de la velocidad de conmutación o el tiempo transitorio de los aparatos de carga. Por lo tanto, ocasionalmente se producen grandes errores al medir la diferencia de corriente entre dos muestras de corriente consecutivas. Para reducir el error, la frecuencia de muestreo puede ajustarse en consecuencia. Pero calibrar la frecuencia de muestreo puede ser difícil ya que varios dispositivos de carga tienen diferentes tiempos transitorios, así como el tiempo necesario para diferentes instrucciones de software puede diferir con diferentes hardware y sensores.
 
Un método más eficaz para reducir este error será encontrar la suma de N muestras de corriente consecutivas de modo que la suma de todos los errores sea cero (o cercana a cero). Es posible que el usuario tenga que esperar un período muy breve antes de que se pueda encender / apagar el siguiente aparato de carga. El pequeño error que queda no entrará en vigor ya que el algoritmo de clasificación lo descartará en función de los valores de desviación estándar y media de todos los datos etiquetados. Como se muestra en la figura anterior, cargue el aparato A durante su estado transitorio como un cambio de corriente total de 10. Pero este valor no se refleja entre dos muestras de corriente consecutivas. En cambio, el cambio en la corriente observada entre dos muestras de corriente consecutivas para el dispositivo de carga A es 2,3 y 5 respectivamente. Por tanto, el valor del error producido será 3 o 5.Pero si tomamos la suma de N muestras consecutivas donde en N en este caso es igual a 3, entonces obtendremos un valor de error de 0.
Potencia activa y reactiva:
Usar solo la corriente consumida por una carga como parámetro de clasificación causará problemas cuando dos o más dispositivos de carga completamente diferentes (con diferentes aplicaciones) consuman la misma cantidad de corriente. Esto se debe a que la diferencia de corriente entre N muestras consecutivas para ambos dispositivos puede ser igual, lo que puede producir un resultado incorrecto.
Por lo tanto, para diferenciar con mayor precisión los dispositivos de carga que consumen la misma cantidad de corriente, también consideramos el valor de la potencia activa y la potencia reactiva consumidas por cada dispositivo de carga individual. Será muy poco probable que dos aparatos de carga completamente diferentes con diferentes aplicaciones tengan el mismo consumo de corriente, así como los valores de potencia activa y reactiva.
 
Para calcular la potencia activa y la potencia reactiva consumidas por los dispositivos de carga, primero debemos encontrar la diferencia de fase entre el voltaje y la corriente. Hacemos esto implementando un detector de cruce por cero (ZCD) simple tanto para el voltaje como para la corriente.
El ZCD se construye utilizando el LM339. La amplitud de las señales de voltaje y corriente medidas se reduce para alcanzar el valor de entrada máximo permitido por el LM339. Se muestra una captura de pantalla del circuito de medición del ángulo de fase.
 
 
La salida del ZCD se alimenta a una sola puerta Ex-OR de un EXOR IC 7486 que producirá pulsos cuando haya un cambio de fase. es decir, los dos niveles lógicos de las entradas a la puerta EXOR no son iguales entre sí.
 
El período de tiempo de estos pulsos se puede utilizar para encontrar el ángulo de fase entre las formas de onda de voltaje y corriente.
 
Creación del conjunto de datos:
Cada dispositivo tendrá al menos dos etiquetas de clase asociadas según el número de 'estados de actividad' que pueda experimentar durante el funcionamiento normal. Normalmente, la mayoría de los electrodomésticos solo tendrán dos estados. Por ejemplo: una bombilla tendrá solo dos estados: encendido y apagado. Considerando que, una batidora de cocina puede tener varios estados dependiendo del modo de batidora ajustable. Cada estado se define por sus atributos de corriente y potencia separados. Cada muestra es una medida del cambio en la corriente, la potencia activa o la potencia reactiva, siendo la etiqueta de verdad de tierra uno de los estados de actividad del aparato.
Determinación del estado del dispositivo:
 
Usamos un algoritmo de clasificación Naive Bayes para determinar qué dispositivos están activos y en qué estado de actividad están operando. Las predicciones se hacen eligiendo la clase con la media y la desviación estándar más cercanas para cada característica en comparación con los datos de entrenamiento usando una probabilidad gaussiana Función de densidad. es decir, combinamos la probabilidad de cada característica para determinar la probabilidad de clase.
En el ejemplo de demostración , usamos un conjunto de datos de entrenamiento de demostración que contiene las características medidas para 3 dispositivos con un total de 6 estados, a saber, dos bombillas CFL y un taladro eléctrico.
Puede encontrar el video de este ejemplo de demostración : Video de demostración
Funciones de clasificación adicionales:
podemos utilizar funciones adicionales como el tiempo, el tiempo y la habitación para mejorar la precisión de la predicción.
 
Estas características adicionales se pueden usar como características dentro de un árbol de decisión para usarse como un conjunto junto con el clasificador Naive Bayes existente.
Estimación de la factura de la luz:
Una vez que hemos determinado los dispositivos activos. Podemos usar medir la energía total que consumen individualmente midiendo su tiempo de inicio y parada (tiempo activo total = tiempo de inicio - tiempo de parada) y simplemente multiplicando la energía consumida por el dispositivo para cada estado de actividad por el tiempo activo total para un estado en particular. . Luego, podemos estimar la factura de electricidad mensual multiplicando la energía consumida durante todo el mes por la tarifa por unidad. A continuación, se muestra un ejemplo de una tabla en blanco para el ejemplo de demostración.
 
 
Interfaz de usuario:
La interfaz de usuario utiliza un Python Micro-Framework llamado Flask que se utiliza para crear aplicaciones web. El marco Flask codifica las variables de Python en tiempo real en una cadena de notación de objetos JavaScript (JSON). Luego, la cadena JSON se lee en el archivo HTML mediante solicitudes Asynchronous JavaScript And XML (AJAX). Estas solicitudes se actualizan periódicamente mediante la función de actualización automática en AJAX. La demostración básica del generador de datos automático de la interfaz de usuario utiliza la información de fecha / hora de actualización automática como datos ficticios que se envían a la demostración del panel HTML .
Trabajo futuro
La precisión de la clasificación se puede mejorar mediante el análisis de patrones mediante el seguimiento de la forma de la trayectoria VI. Las características de la forma, como el área bajo la curva VI y el pico de los segmentos, se pueden analizar más a fondo. [ 2 ]
El análisis del ruido de voltaje en estado estacionario, como las firmas EMI, puede mejorar la detección de dispositivos basados en motores como ventiladores, batidoras de alimentos y lavadoras. Aunque esto requeriría sensores EMI adicionales para cada aparato, lo que estaría en contradicción con el objetivo inicial de este proyecto.
Uso de modelos ocultos de Markov [ 3 ] y redes neuronales [ 4 ] para determinar los dispositivos activos.
Gráficos de energía consumida por mes por electrodoméstico.
Contribuyendo
¿Es usted un programador, ingeniero o aficionado que tiene una gran idea para una nueva función en este proyecto? ¿Quizás tienes una buena idea para corregir un error? Siéntase libre de tomar nuestro código de Github y jugar con él. No olvides aplastar esos ⭐️ & Botones Pull Request. Lista de colaboradores
Hecho con ❤️ por Jonathan Pereira
Referencias
1.	Hoja de datos del ACS712
2.	Enfoques de monitoreo de carga no intrusiva para detección de energía desagregada: una encuesta
3.	NILM usando modelos ocultos de Markov
4.	NILM neuronal




Gokulshriyan (2017)
Github
Enlace a github  Minion https://github.com/gokulshriyam/Minion 
Resumen
Minion es para todos los consumidores de electricidad en todo el mundo para ayudar a reducir sus costos de energía a un precio asequible utilizando productos y análisis "fáciles de usar".
Como hay muchos dispositivos de energía inteligente de IOT en el mercado que garantizan la eficiencia energética y el ahorro de costos, pero hacen que las facturas eléctricas mensuales se dupliquen o tripliquen todos los meses, sin aumentar el uso de energía.
Habíamos leído detenidamente las soluciones de todos los contadores inteligentes existentes en todo el mundo e identificamos el caso de uso perfecto que garantiza una eficiencia energética del 100% y un ahorro de costes para los consumidores de electricidad.
Minion es un dispositivo único (tamaño: 39x49 milímetros, el auditor de energía de bolsillo más pequeño del mundo) con conectividad Wi-Fi, LORA, 3G / 4G que encajará dentro del panel de interruptores (al lado del medidor de servicios públicos como complemento) con conexión de abrazadera de sensor único después del medidor de utilidad.
Este Minion realizará análisis de energía en tiempo real de dispositivos / dispositivos / herramientas / equipos. También realizará análisis predictivos y mantenimiento de activos (hospitalarios, industriales, fabricación / fábricas, hostelería, venta minorista) que rescata los activos de alto coste de averías y también reduce los costes de seguros. Programa el mantenimiento que asegurará y extenderá la vida útil de los activos más allá del tiempo del seguro.
Nuestro Minion también es compatible con la energía solar. Tiene la capacidad de medir lecturas de generación y consumo (actúa como medidor neto) y realiza análisis predictivos y en tiempo real.
Todos los análisis se realizan en la nube y permiten a los usuarios experimentar los resultados a través de nuestro SaaS: aplicación de Windows, aplicaciones de Android e IoS.
Nuestro Minion proporciona tres pasos para garantizar el 100% de eficiencia energética y ahorro de costes.
1.	Análisis en tiempo real: hagamos saber al usuario en qué está gastando a nivel de electrodomésticos en cualquier sector (residencial, hotelero, hospitalario, industrial y más)
2.	Análisis predictivo: reduce las sorpresas en las facturas de energía y el usuario puede predecir fácilmente el uso y las facturas de energía y programar en consecuencia. Esto sería muy útil para los sectores que ejecutan activos de alto costo, lo que evitará la rotura y aumentará la eficiencia de los activos.
3.	Sistema operativo (SO): el análisis predictivo con datos y sensores conduce al sistema operativo que garantiza el 100% de eficiencia y ahorro de costos. Sin la ayuda de la interferencia humana, nuestro sistema operativo realizará la automatización dentro de los edificios.
Sobre Minion: el auditor de energía de IA más pequeño del mundo





ZhangRaymond (en chino)
Github
Enlace a github  neural NILM https://github.com/ZhangRaymond/Neural-NILM 
Resumen
Neural-NILM:Un método de monitoreo de carga no intrusivo (NILM) (también llamado desagregación de carga no intrusiva) basado en la red neuronal. Se proponen un modelo de secuencia a secuencia y un modelo de secuencia a punto. El proyecto está basado en Keras y la versión de tensorflow está en camino.
Archivos
|-- Seq2Seq.py            // define a Seq2Seq Class
|-- Seq2point.py          // define a Seq2point Class
|-- model.py              // define some neural networks
|-- lib.py                // Some necessary helper functions
|-- main.py               // main function
Marco de red neuronal:Keras con tensorflow como backend
Conjunto de datos : REDD ：http://redd.csail.mit.edu/

Debido a que los datos utilizados en la capacitación son aproximadamente 2 G, no subido. Vaya al enlace anterior y descárguelo usted mismo.
Uso 
Llame a cada archivo desde la función principal y lea los datos de entrenamiento para iniciar el entrenamiento. Después del entrenamiento, el mejor modelo de rendimiento y los archivos de peso en el conjunto de datos de validación se guardarán automáticamente, y el historial de entrenamiento y otros datos se guardarán como archivos CSV.


Compsust
Github
Enlace a github  Kp-nilm https://github.com/compsust/KP-NILM/blob/master/KP-NILM.py 
Resumen
KP-NILM:NILM utilizando el problema de la mochila de opción múltiple (MCKP).
Este es un prototipo / demostración ingenuo que se utilizó inicialmente al explorar diferentes conceptos de UNILM.
Si usa  el código en su investigación, cite nuestro trabajo de investigación de UNILM (ejemplo de IEEE):
A. Rodríguez-Silva y S. Makonin, “Monitoreo universal de carga no intrusiva (UNILM) usando tuberías de filtro, mochila probabilística y mapas de particiones etiquetadas”, p. 6 de enero de 2019.
Lea más sobre UNILM en arXiv en https://arxiv.org/abs/1907.06299 .
Notas
•	Debe instalar los siguientes paquetes a través de pip : prettytable, statistics, scipy, numpy
•	Descargue el house1_power_blk1.csv archivo del conjunto de datos RAE de Dataverse

Mieskolainen (hace 8 meses)
Github
Enlace a github  algo-NILM https://github.com/mieskolainen/algo-NILM 
ResumenDescomposición inversa del consumo de energía.
La idea detrás del Monitoreo de Carga No Intrusiva (NILM) es resolver un problema inverso de descomponer una superposición de diferentes cargas de energía eléctrica doméstica, basado en observar solo las series de tiempo de la carga total. Este objetivo fue iniciado por GW Hart, MIT. Resolver este problema teórico también tiene motivaciones prácticas de gran alcance, que van desde la comprensión de las grandes cargas de los sistemas industriales hasta la reducción del consumo mundial de energía en general.


 
Figura 1: Una interfaz web integrada con datos en tiempo real.
Algoritmos
Los algoritmos integrados aquí incluyen técnicas básicas de aprendizaje automático supervisadas y no supervisadas ( K-means , Fuzzy K-means , EM-clustering , clasificador de Bayes ), procesamiento de señales lineales y no lineales ( filtrado , detección de bordes ) y una optimización combinatoria del tipo de algoritmo genético para aprender la máquina de estados finitos .
 
Figura 2: Un diagrama de autómata finito inequívoco (de Wikipedia).
¡Constrúyelo!
Se realizó un prototipo funcional con una tarjeta de desarrollo integrada ARM-linux Artila iPAC5010 junto con un circuito de fotodiodo personalizado que se activa en la salida óptica de un medidor de energía doméstico estándar (1k pulsos / kWh). Además, se incluye un soporte de red de 1 cable con sensores de temperatura de un cable de "conexión en caliente". La interfaz de usuario es proporcionada por un servidor web integrado ( front-end asíncrono de Javascript , back-end de PHP y C ++ ). Se utiliza una base de datos SQL ( SQLite3 ) para guardar los datos de medición. Se recomienda una placa ARM moderna con soporte de punto flotante.

Este sistema prototipo fue presentado y premiado en 2009 en un concurso de innovación técnica IIDA09 en la Universidad Tecnológica de Tampere (TUT), Finlandia.

 
Figura 3: Una interfaz web incorporada con datos de series de tiempo.


Para acabar
•	  Cargue todos los datos recopilados entre 2009-2021
•	  Cambiar todos los comentarios del código al inglés
•	  Adapte el código para Rasperry Pi (solo las interfaces GPIO necesitan modificación)
•	  Implementar algoritmos modernos, por ejemplo, aprendizaje profundo con autosupervisión / factorizaciones matriciales.


Instalación completa
1.	Copie todo lo que hay debajo /mnt/en la placa ARM con la tarjeta SD
2.	Use el puerto GPIO 8 para el circuito de activación del medidor de energía
3.	Conectar ethernet
4.	Conecte el adaptador de un cable al puerto serie (opcional)
Dirección de arranque del sistema
Los scripts en las siguientes rutas controlan el inicio
/mnt/disk/etc/
/mnt/disk/
Fuentes del programa
Programas de back-end web y en tiempo real de C ++
/source/{*.c, *.h, Makefile}
PHP web back-end + javascript front-end
/mnt/disk/home/
Bases de datos
Archivos de base de datos (sqlite3) recopilados con el prototipo. Extrae .dbarchivos de .tar.xzarchivos.
/mnt/mmc/{*.db}
Binarios
Programas compilados en tiempo real multiproceso
/mnt/disk/powercalc
/mnt/disk/cluster
Programas de back-end web compilados
/mnt/disk/home/httpd/apps/get_file_archive.cgi
/mnt/disk/home/httpd/apps/get_statistics.cgi
/mnt/disk/home/httpd/apps/socket_client.cgi
Programas estándar adicionales utilizados
/mnt/disk/php
/mnt/disk/openssl
/mnt/disk/cron
/mnt/disk/ntpclient
/mnt/disk/lighttpd/*
/mnt/disk/ntpd/*
/mnt/mmc/sqlite3 (for manually inspecting database files)
Circuito de disparo de salida óptica del medidor de energía
Los componentes del circuito de lectura son
•	Diodo PN fotosensible con polarización inversa
•	Transistor bipolar + resistencias de polarización
•	Fuente de voltaje
•	Cableado
Bibliotecas externas utilizadas
Bibliotecas C
Database: SQLite3 https://www.sqlite.org/ (Public domain)
1-Wire: Dallas/Maxim  driver C-libraries ((C) 2000 Dallas Semiconductor Corporation)
Javascript
JQuery https://jquery.com/ (MIT license)
prototype.js http://prototypejs.org/ (MIT license)
script.aculo.us https://script.aculo.us/ (MIT license)
ContentFlow http://contentflow.eu (MIT license)
DHTML calendar (LGPL license)


Daniprec  2021
Github
Enlace a github Nilm https://github.com/UCA-Datalab/nilm-thresholding 

Resumen NILM: clasificación VS regresión
El monitoreo de carga no intrusiva (NILM) tiene como objetivo predecir el estado o el consumo de electrodomésticos en un hogar solo conociendo la carga de energía agregada. NILM se puede formular como un problema de regresión o, con mayor frecuencia, como un problema de clasificación. La mayoría de los conjuntos de datos recopilados por medidores inteligentes permiten definir de forma natural un problema de regresión, pero el problema de clasificación correspondiente es uno derivado, ya que requiere una conversión de la señal de potencia al estado de cada dispositivo mediante un método de umbralización. Trata tres métodos de umbral diferentes para realizar esta tarea, discutiendo sus diferencias en varios dispositivos del conjunto de datos UK-DALE. Analizamos el rendimiento de las arquitecturas de vanguardia de aprendizaje profundo en los problemas de regresión y clasificación, introduciendo criterios para seleccionar el método de umbral más conveniente.
Configurar
•	Crea el ambiente usando Conda
•	Instalar miniconda : curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh | bash
•	Diga sí a todo y acepte las ubicaciones predeterminadas. Actualizar el shell de bash conbash -l
•	Actualizar conda: conda update -n base -c defaults conda
•	Clona este repositorio y cd en la carpeta
•	Cree y active el entorno de conda (eliminando el env que ya existía con el mismo nombre)
•	conda remove --name nilm-thresholding --all
•	conda env create -f environment.yml --force
•	conda activate nilm-thresholding
Datos REINO UNIDO-DALE (Descarga UK-DALE)
El conjunto de datos UK-DALE está alojado en el siguiente enlace: https://data.ukedc.rl.ac.uk/browse/edc/efficiency/residential / EnergyConsumption / Domestic / UK-DALE-2017 / UK-DALE-FULL-disaggregated
Los archivos que necesita este módulo son ukdale.zip y ukdale.h5.zip . Descargue ambos y descomprímalos en una carpeta llamada datos dentro de la raíz. Una vez que haya terminado, su directorio local debería verse así:
nilm-thresholding
|_ nilmth
   |_ [python scripts and subfolders]
|_ data
   |_ ukdale
      |_ [house_1 to house_5]
   |_ ukdale.h5
Crédito: Jack Kelly
Preproceso
Una vez descargados los datos sin procesar de cualquiera de las fuentes anteriores, debe preprocesarlos. Esto se hace ejecutando el siguiente script:
python nilmth/preprocess.py
Esto generará una nueva carpeta, llamada 'data-prep', que contiene todos los datos preprocesados.
Entrenamiento
La carpeta nilmth contiene un script ejecutable para entrenar los modelos. Ejecute la siguiente línea en la carpeta raíz (asegúrese de tener el entorno activo y los datos descargados):
python nilmth/train.py
Esto entrenará el modelo CONV usando los parámetros predeterminados. El script almacena varias salidas en la carpeta de salidas , que incluyen:
•	archivos .txt con las puntuaciones del modelo sobre los datos de validación
•	archivos .pth que contienen los pesos del modelo
•	archivos .png con una sección de los datos de validación y la predicción del modelo
La lista con todos los parámetros disponibles y sus valores predeterminados se almacena en el archivo de configuración .
Si desea utilizar su propio conjunto de parámetros, duplique el archivo de configuración mencionado anteriormente y modifique los parámetros que desea cambiar (sin eliminar ningún parámetro). Luego puede usar ese archivo de configuración con el siguiente comando:
python nilmth/train.py  --path_config <path to your config file>
Para obtener más información sobre el script, ejecute:
python nilmth/train.py  --help
Una vez entrenados los modelos, pruébelos con:
python nilmth/test.py  --path_config <path to your config file>
Para reproducir los resultados que se muestran en nuestro artículo , active el entorno y luego ejecute:
nohup sh train_sequential.sh > log.out & 
Esto primero creará una carpeta llamada configs, donde se almacenan las diferentes configuraciones de los modelos. Luego, train.pyse llamará al script , usando cada configuración cada uno. Esto almacenará los pesos del modelo, que se utilizarán nuevamente durante la fase de prueba:
nohup sh test_sequential.sh > log.out & 
Métodos de umbralización
Hay tres métodos de umbral disponibles. Lea nuestro artículo para comprender cómo funciona cada umbral.
•	'mp', punto medio
•	'vs', sensible a la variación
•	'at', tiempo de activación



Yilingjia 
Github
Enlace a github  TreeCNN https://github.com/yilingjia/TreeCN N-for-Energy-Breakdown 
Resumen
TreeCNN-for-Energy-Breakdown.WWW19 'Un modelo de red neuronal estructurada en árbol para el desglose energético de los hogares

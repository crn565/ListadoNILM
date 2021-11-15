## Recursos NILM
Una lista de repositorios con algoritmos de desagregación de energía implementados


# Cuadernos Juyter Notebooks

### Nilmtk
  
 buildsys2019 
https://github.com/nilmtk/buildsys2019-paper-notebooks

 nilmtk-contrib
https://github.com/nilmtk/nilmtk-contrib


## Klemenjak
 simple desagregacion
 https://github.com/klemenjak/SynD/blob/master/examples/simple_disaggregation.ipynb 
 Papers
 https://github.com/klemenjak/nilm-papers-with-code
SynD
https://github.com/klemenjak/SynD 


## JackKelly

 Prototipo Neuralnilm

https://github.com/JackKelly/neuralnilm_prototype

https://github.com/JackKelly/neuralnilm

## GJW
 Gjw data
https://github.com/gjwo/nilm_gjw_data
 Gjw metadata
https://github.com/gjwo/nilm_metadata





## OdysseasKr  

Desagregador Neuronal https://github.com/OdysseasKr/neural-disaggregator





## Josemao
Nilmtk en 4 pasos https://github.com/josemao/nilmtk_practicas

Non-Intrusive Load Monitoring (NILM) es una colección de técnicas y algoritmos de machine learning orientados a desagregar el consumo total de una casa en consumos individuales de electrodomésticos.

Estas prácticas sigue algunos de los ejemplos propuestos en: http://nilmtk.github.io/

1 - Python científico:Aquí explicaremos algunos de los conceptos básicos para el uso de las librerías necesarias de NILM.
numpy: operaciones matemáticas de arrays y matrices
matploblib: para gráficas
pandas: herramienta de análisis de datos a gran escala de manera eficiente

2 - Introducción a NILMTK:NILMTK es una herramienta de análisis de datasets de NILM. Contiene funciones específicas para el análisis detallado y rápido del consumo eléctrico. Además, sirve de plataforma para los investigadores de NILM para comparar sus algoritmos con métricas estándar sobre varios datasets.Aprenderemos los conceptos básicos. Para más información, consultar la documentación en: https://github.com/nilmtk/nilmtk

Los datasets que utilizaremos son:
-REDD: monitorización del consumo energético de 6 casas diferentes en Estados Unidos: 2 casas a alta frequencia (12KHz de corriente y voltage) y 4 casas a baja frequencia (10 segundos por muestra de la potencia activa) http://redd.csail.mit.edu/
-UK-DALE Monitorización de una casa en Inglaterra durante 2 años a alta frequencia y baja frequencia: 16KHz de corriente y voltage y 1 segundo de potencia activa, reactiva y aparente. http://www.doc.ic.ac.uk/~dk3810/data/
-IAWE Monitorización de una en India durante 73 días a 1 segundo. Parámetros: potencias activa, reactiva y aparente, voltage, corriente y factor de potencia. http://iawe.github.io/

3 - Previo a la desagregación: gráficas y estadísticas.
Antes de realizar la desagregación, podemos analizar el consumo general desde el smart meter para obtener información interesante sobre la actividad en la vivienda. Asímismo, si se tiene información sobre el consumo individual de algunos dispositivos (groundtruth) mediante la instalación de smart-plugs, podemos obtener los patrones de consumo de distintos dispositivos que nos ayude a mejorar nuestro algoritmo.

4 - Desagregación: Métodos supervisados y no supervisados. Aquí se estdudiará distintos algoritmos de desagregación. Primeramente se introducirá una extensión del algoritmo de Hart para desagregar de forma supervisada. A continuación, se presentan dos algoritmos no supervisados: cadenas factoriales de Markov (FHMM) y optimización combinatoria (CO); comparándolos mediante el uso del mismo dataset y de las mismas métricas.

Notas:Máquina virtual Linux: usr(nilm) y pwd(nilm)
Enlazar carpeta data como carpeta compartida en Virtual Box. Mantener el nombre data
Es necesaria la installación previa de nilmtk: https://github.com/nilmtk/nilmtk/blob/master/docs/manual/user_guide/install.md


# Codigo en Python 

## Gissemari  Desagregacion vrnn
https://bitbucket.org/gissemari/disaggregation-vrnn/src/master/
VRNN-DIS1 y VRNN-DIS-ALL

######## ALGUNOS CONOCIMIENTOS PREVIOS SOBRE EL MODELO
Estos modelos se construyen en base al modelo VRNN implementado en theano por sus autores aquí: https://github.com/jych/nips2015_vrnn.
Se ejecuta con python2.7 y el resto de las versiones de las bibliotecas se pueden verificar en el archivo .yml
Crea y activa el entorno desde latentVar.yml
####### ESTRUCTURA DE ESTE REPOSITORIO
bibliotecas auxiliares: donde se guardan los repositorios mencionados anteriormente
Desagregación- [conjunto de datos]: están organizados de manera similar, una carpeta para los metadatos, una carpeta donde se guardan los archivos originales y preprocesados ​​del conjunto de datos, el código y la salida.
latentVar.yml: entorno conda con todos los módulos y bibliotecas instalados
#### BIBLIOTECAS AUXILIARES
Este modelo utiliza algunos otros módulos que han sido modificados e incluidos en este repositorio:

1) NEURALNILM: cargue el archivo .h5 con el módulo NIMLTK y luego procese el conjunto de datos UKDALE para obtener instancias con cierta activación de destino (dispositivo) o sin ella. Repositorio original en https://github.com/JackKelly/neuralnilm 2) NILMTK y NILM_METADATA: Carga los archivos .h5, se realizan pocos cambios basados ​​en los originales principalmente por problemas de versiones. Originales https://github.com/nilmtk/nilmtk y https://github.com/nilmtk/nilm_metadata 2) CLE: Usado para entrenamiento y monitoreo modificado principalmente para agregar variables a monitorear y los mecanismos de muestreo de programación. Repositorio original: https://github.com/jych/cle)
2) ####### SUB REPOSITORIOS
Cada uno de los repositorios de conjuntos de datos se divide en 3 subcarpetas:

1) Metadatos: estadísticas y cifras para respaldar algunos de los parámetros que seleccionamos, como la longitud de las instancias (secuencias), el valor mínimo a considerar que el dispositivo está encendido, el valor máximo a considerar es apagado, etc. 2) Conjuntos de datos: carpeta donde deben colocarse los datos originales (.h5). También contiene una subcarpeta PICKLES para guardar algunos datos preprocesados, especialmente para experimentos repetidos. 3) Preprocesamiento: donde se almacena la lógica del preprocesamiento. Su función principal es muestrear las instancias en función de los parámetros del archivo de configuración, como la frecuencia de muestreo (período), la longitud de la secuencia, la superposición o no para el entrenamiento, etc. 4) VRNN_theano_version: donde se almacenan los modelos y la salida de los modelos VRNN. . También contiene

##### PARAMETROS
Los parámetros se definen dentro de los archivos de código como edificios, ELECTRODOMÉSTICOS (en el archivo de preprocesamiento), ventanas (rango de fechas para cargar y / o rangos para separar para entrenamiento y prueba). Sin embargo, la mayoría de los parámetros son similares en todos los modelos vrnn y se leen desde un archivo de configuración:

[PATHS] - pickleModel es el archivo con el modelo mejor guardado a partir del cual leer los parámetros aprendidos. Se usa principalmente en los archivos de prueba - data_path es la ruta de los archivos de datos: ... / PecanStreet-dataport / datasets - save_path es la carpeta donde se guardará la salida, generalmente ... / VRNN_theano_version / output

[PREPROCESSING] - period: la tasa de frecuencia a la que se recopilan los pasos de tiempo en los datos - n_steps: longitud de la secuencia - stride_train: paso o espacio entre instancias en el conjunto de entrenamiento - 1: cuando typeLoad es 0 (porque usará 1 para tienen instancias superpuestas en el entrenamiento, pero usarán n_steps para el paso en las instancias de prueba) - n_steps: cuando typeLoad es 1 (porque como elegimos instancias al azar, debemos garantizar que las instancias de prueba o cualquier parte de ellas también sean parte del conjunto de entrenamiento) - stride_test: paso o espacio entre instancias en el conjunto de prueba (tiene que ser igual o mayor que la longitud de la secuencia para evitar la superposición) - typeLoad: - 0 para la carga original donde el conjunto total se divide en formación, validación y pruebas en un orden específico. - 2 Construyendo instancias de forma aleatoria, sin solapamientos y asignando un número específico para entrenar, probar y validar. A diferencia del trabajo de Kelly, decidimos no dividir el entrenamiento, los conjuntos de validación por ventanas de tiempo, sino tener una ventana única donde dividimos por porcentaje las instancias obtenidas para los conjuntos de entrenamiento y validación. - 1 (no se usa para este conjunto de datos. Para ukdale: carga de Kelly)

[ALGORITMO] - monitoring_freq: número de lotes de entrenamiento tras los cuales se realiza un proceso de validación. Digamos que tenemos 100 mini-lotes y el monitoring_freq es 20. El proceso de validación se haría solo después del proceso de los 10 mini-lotes. - época: número de iteraciones en las que se procesaron todos los mini lotes. Significa que, en una época, se procesaron 100 mini lotes. - batch_size: tamaño del mini-lote - kSchedSamp: velocidad de convergencia para la desintegración sigmoidea inversa. Tomado de https://arxiv.org/abs/1506.03099 - lr: tasa de aprendizaje inicial

[MODELO] - x_dim: señal agregada (1) - y_dim: señal desagregada (número de aparatos) - z_dim: unidades en la capa z - k_target_dim: (num_k) número de distribuciones gaussianas de mezcla - rnn_dim: número de unidades para el laye recurrente - q_z_dim: tamaño de unints para el extractor de características de la distribución del codificador - p_z_dim: tamaño de unints para el extractor de características de la distribución anterior - p_x_dim: tamaño de las unidades para la distribución del decodificador - x2s_dim: tamaño del extractor de características para la señal x - y2s_dim: tamaño del extractor de características para las señales y (desagregadas) - z2s_dim: tamaño del extractor de características para la z (variable latente) - typeActivFunc: función de activación para el mu (parámetro theta) de la distribución del decodificador

###### UTILS - SOLUCIONES DE ERRORES
PARA INSTALACION

Al instalar theano con conda, falta instalar python2x. Así que cópialo de algún lado

## NILM en línea 
https://github.com/OdysseasKr/online-nilm
Aquí puede encontrar el código para las dos arquitecturas de redes neuronales propuestas  :"Enfoque de ventana deslizante para la desagregación de energía en línea utilizando redes neuronales artificiales, O. Krystalakos, C. Nalmpantis y D. Vrakas, SETN, 2018" (Documento completo: 3200947.3201011)
Todo el código está escrito con Keras y Tensorflow.
Puede encontrar versiones compatibles con NILMTK de estas redes en https://github.com/OdysseasKr/neural-disaggregator .
Requiere NILMTK para ejecutarse. Puede encontrarlo aquí: https://github.com/nilmtk/nilmtk .
#Las redes
En cada carpeta puede encontrar un archivo README con instrucciones sobre cómo ejecutar los experimentos. Para cada red encontrará 4 archivos Python:
> experiment.py: Código para ejecutar el experimento. Cada experimento incluye entrenamiento y evaluación de la red.
> gen.py: Descarga todos los recursos necesarios y genera un conjunto de trenes y un conjunto de pruebas.
> model.py: La arquitectura de red.
> metrics.py: las métricas utilizadas para evaluar la red.
Los experimentos están disponibles para los siguientes dispositivos del conjunto de datos UKDALE:
-Lavavajillas
-Nevera
-Pava
-Microonda
-Lavadora
Obras relacionadas en NILM neuronal: https://arxiv.org/pdf/1507.06594.pdf y Secuencia original a punto: https://arxiv.org/pdf/1612.09106v3.pdf 



## Yilingjia 

 TreeCNN
https://github.com/yilingjia/TreeCNN-for-Energy-Breakdown

## Maechler

 Nnilm
https://github.com/maechler/nnilm



## Compsust

ALIP_NILM
https://github.com/compsust/ALIP_NILM




## Loneharoon
 Desagregador de energia GSP 
https://github.com/loneharoon/GSP_energy_disaggregator

## Louisyuze
 Machine LeaRNING
https://github.com/louisyuzhe/MachineLearning_NILM

## Jonathanrpereira
 Smart energy Monitor
https://github.com/jonathanrjpereira/Smart-Energy-Monitor


## bhushan23 
 LSTM-SplitterdData Microhondas
https://github.com/bhushan23/SmartOff/blob/master/LSTM-SplittedData-Microwave.ipynb

## gokulshriyan
 Minion
https://github.com/gokulshriyam/Minion


## ZhangRaymond
 neural NILM
https://github.com/ZhangRaymond/Neural-NILM


## Maechler
 NNILM
https://github.com/maechler/nnilm

## Compsust
 Kp-nilm
https://github.com/compsust/KP-NILM/blob/master/KP-NILM.py

## Mieskolainen
 algo-NILM
https://github.com/mieskolainen/algo-NILM


## Daniprec
Nilm  
https://github.com/daniprec/nilm




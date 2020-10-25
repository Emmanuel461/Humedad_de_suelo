<img src="ucrea.jpg" width="200" height="150"><img src="eg.jpg" width="250" height="100"><img src="ucr.jpg" width="200" height="150"><img src="iica.png" width="200" height="150">

<h1>Introducción al uso de imágenes de Radar de Apertura Sintética aplicado a la agricultura</h1> 
<h2>Manual de cálculo de humedad de suelo</h2> 

<p>Este manual fue elaborado por la Escuela de Geografía de la Universidad de Costa Rica, para el cual colaboraron Emmanuel Jesús Céspedes-Rivera y Cristian Aguilar-Barboza en calidad de asistentes avanzados del proyecto "Transformación digital: Incorporación de tecnología SAR en la gestión de riesgos, agricultura y recursos naturales para Centroamérica", en el marco del proyecto UCREA-IICA.</p>
<p>Este proyecto está coordinado por el Dr Edgar Espinoza Cisneros y co-cordinado por MSc María José Molina Montero. Para mayor información contactar a maria.molinamontero@ucr.ac.cr .</p>


<p>Índice</p> 

<p><li><a href="#Sección1">1. Prerrequisitos</a></li>
<li><a href="#Sección2">2. Introducción</a></li>
<li><a href="#Sección3">3. Procesamiento y análisis</a></li>
<li><a href="#Sección4">4. Librería Soil Moisture</a></li>
<li><a href="#Sección5">5. Estimación Humedad de suelo</a></li>
<li><a href="#Sección6">6. Recomendaciones</a></li>
<li><a href="#Sección7">7. Bibliografía</a></li></p> 

<p><h2 id="Sección1">1. Prerrequisitos</h2></p>

<p>Para ejecutar esta rutina el usuario debe instalar previamente el software Sentinel Toolbox (SNAP), el cual es un software de procesamiento para el análisis y observación de la tierra, con herramientas enfocadas en extensibilidad de datos, portabilidad, procesamiento en marcos gráficos, entre otras herramientas (ESA, 2020).</p>

<img src="SNAP.png" />
<h4 id="Sección3">Fig. 1. Sentinel Toolbox (SNAP).</h4>

<p>La descarga del software SNAP se puede realizar en la siguiente dirección electrónica</p> 
<p><a href="http://step.esa.int/main/download/snap-download/" target="_blank">http://step.esa.int/main/download/snap-download/</a></p> 

<p>Los requisitos computacionales mínimos son:
<li>Sistema operativo: Linux, Mac, Windows.</li>
<li>RAM: 8 GB Procesador Intel® Core™ i5-5 o sus equivalentes.</li>
<li>Espacio en disco mínimo 5GB</li></p>

<p><h2 id="Sección2">2. Introducción</h2></p>

<p>La humedad del suelo es un parámetro clave en la regulación del ciclo del agua en la tierra, ya que está en función de las tasas de evaporación y precipitación sobre el suelo, por lo tanto, la disponibilidad de agua en el suelo es esencial para estudios en agricultura, hidrología, meteorología, entre otras (Alexakis et al., 2017). Las imágenes Radar de Apertura Sintética (SAR por sus siglas en inglés) de Sentinel-1, tienen el potencial de estimar de forma indirecta la humedad de suelo debido a características de resolución espacial, temporal y polarización.</p>

<p>La detección remota con sensores ópticos requieren de observaciones con productos de buena calidad, libre de nubes o sombras de nubes para minimizar la confusión espectral de los datos (Shen et al., 2019), sin embargo, en zonas tropicales las coberturas nubosas son constantes y abundantes, su aplicación resulta limitada (Flores et al., 2019). Debido a este aspecto, se ha implementado el uso de la imágenes SAR, la cual despeja la limitante de la nubosidad y permite la obtención continua de información (Flores et al., 2019).</p>

<p>En este caso se aplicó una metodología para la detección de humedad de suelo basada en dos imágenes, una en órbita ascendente y otra en órbita descendente, con una diferencia temporal de aproximada de 12 horas. Lo anterior, con el objetivo de evitar cambios abruptos en las condiciones humedad de la superficie. Por otro lado, se utilizó la polarización VV, ya que el algoritmo IEM (Inversión de ángulo múltiple), no permite procesar imágenes con polarizaciones cruzadas. La ejecución de esta rutina requiere utilizar el software Sentinel Toolbox (SNAP), el cual contiene la librería Soil Moisture, elaborada por la Agencia Espacial Europea (ESA por sus siglas en inglés). Se consideró como área de estudio un sector de la cuenca del río Tempisque, en el que prevalecen cultivos como caña y arroz, así como la presencia de pastos.</p>

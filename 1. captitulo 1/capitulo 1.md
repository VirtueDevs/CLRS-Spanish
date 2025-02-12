# Capítulo 1

##### ¿Qué son los algoritmos? ¿Por qué merece la pena estudiar los algoritmos? ¿Cuál es el papel de los algoritmos en relación con otras tecnologías utilizadas en informática? Este capítulo responderá a estas preguntas. 

## 1.1 Algoritmos

**Informalmente**, un **algoritmo** es cualquier procedimiento computacional bien definido que toma algún valor, o conjunto de valores, como **entrada** y produce algún valor, o conjunto de valores, como **salida** en una cantidad finita de tiempo. Un algoritmo es, por lo tanto, una secuencia de pasos computacionales que transforman la entrada en la salida.

También puedes ver un algoritmo como una herramienta para resolver un **problema computacional** bien especificado. El enunciado del problema especifica en términos generales la relación entrada/salida deseada para instancias del problema, típicamente de tamaño arbitrariamente grande. El algoritmo describe un procedimiento computacional específico para lograr esa relación entrada/salida para todas las instancias del problema.

Como ejemplo, supongamos que necesitas ordenar una secuencia de números en orden monótonamente creciente. Este problema surge frecuentemente en la práctica y proporciona un terreno fértil para introducir muchas técnicas de diseño estándar y herramientas de análisis. Así es como definimos formalmente el _problema de ordenación_:

**Entrada:** Una secuencia de <i>n</i> números ⟨a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>n</sub>⟩.

**Salida:** Una permutación (reordenamiento) ⟨a′<sub>1</sub>, a′<sub>2</sub>, ..., a′<sub>n</sub>⟩ de la secuencia de entrada tal que a′<sub>1</sub> ≤ a′<sub>2</sub> ≤ ... ≤ a′<sub>n</sub>.

Por lo tanto, dada la secuencia de entrada ⟨31, 41, 59, 26, 41, 58⟩, un algoritmo de ordenación correcto devuelve como salida la secuencia ⟨26, 31, 41, 41, 58, 59⟩. Tal secuencia de entrada se denomina _instancia_ del problema de ordenación. En general, una _instancia de un problema_ consiste en la entrada (que satisface las restricciones impuestas en el enunciado del problema) necesaria para calcular una solución al problema.

Dado que muchos programas lo utilizan como un paso intermedio, la ordenación es una operación fundamental en la informática. Como resultado, tienes a tu disposición una gran cantidad de buenos algoritmos de ordenación. Cuál algoritmo es el mejor para una aplicación dada depende de _entre otros factores_ el número de elementos a ordenar, el grado en que los elementos ya están algo ordenados, las posibles restricciones sobre los valores de los elementos, la arquitectura de la computadora y el tipo de dispositivos de almacenamiento que se utilizarán: memoria principal, discos o incluso *de manera arcaica* cintas.

Un algoritmo para un problema computacional es _correcto_ si, para cada instancia del problema proporcionada como entrada, se _detiene_—finaliza su cómputo en un tiempo finito—y produce la solución correcta a la instancia del problema. Un algoritmo correcto _resuelve_ el problema computacional dado. Un algoritmo incorrecto podría no detenerse en absoluto en algunas instancias de entrada, o podría detenerse con una respuesta incorrecta. Contrario a lo que podrías esperar, los algoritmos incorrectos pueden ser útiles en ocasiones, si puedes controlar su tasa de error. Veremos un ejemplo de un algoritmo con una tasa de error controlable en el Capítulo 31, cuando estudiemos algoritmos para encontrar números primos grandes. Sin embargo, normalmente nos preocuparemos únicamente por algoritmos correctos.

Un algoritmo puede especificarse en inglés, como un programa de computadora o incluso como un diseño de hardware. El único requisito es que la especificación debe proporcionar una descripción precisa del procedimiento computacional a seguir.

_¿Qué tipos de problemas se resuelven con algoritmos?_

La ordenación no es, de ninguna manera, el único problema computacional para el cual se han desarrollado algoritmos. (Probablemente sospechabas esto cuando viste el tamaño de este libro). Las aplicaciones prácticas de los algoritmos son omnipresentes e incluyen los siguientes ejemplos:

* **El Proyecto del Genoma Humano** ha logrado un gran progreso hacia los objetivos de identificar todos los aproximadamente 30,000 genes en el ADN humano, determinar las secuencias de los aproximadamente 3 mil millones de pares de bases químicas que componen el ADN humano, almacenar esta información en bases de datos y desarrollar herramientas para el análisis de datos. Cada uno de estos pasos requiere algoritmos sofisticados. Aunque las soluciones a los diversos problemas involucrados están más allá del alcance de este libro, muchos métodos para resolver estos problemas biológicos utilizan ideas presentadas aquí, permitiendo a los científicos realizar tareas utilizando recursos de manera eficiente. La **programación dinámica**, como en el Capítulo 14, se presenta una técnica importante para resolver varios problemas biológicos, especialmente aquellos que implican determinar la similitud entre secuencias de ADN. Los ahorros realizados son significativos, tanto para los humanos como para las máquinas, y en términos monetarios, ya que se puede extraer más información mediante técnicas de laboratorio.

Internet permite a las personas de todo el mundo acceder y recuperar rápidamente grandes volúmenes de información. Con la ayuda de algoritmos inteligentes, los sitios en internet pueden gestionar y manipular estos grandes volúmenes de datos. Ejemplos de problemas que hacen un uso esencial de los algoritmos incluyen encontrar las mejores rutas por las que viajan los datos (las técnicas para resolver estos problemas aparecen en el Capítulo 22) y usar un motor de búsqueda para localizar rápidamente páginas en las que reside información en particular (técnicas relacionadas están en los Capítulos 11 y 32).

- **El comercio electrónico** permite que bienes y servicios sean negociados e intercambiados electrónicamente, y depende de la privacidad de la información personal como números de tarjetas de crédito, contraseñas y estados bancarios. Las tecnologías centrales utilizadas en el comercio electrónico incluyen la criptografía de clave pública y las firmas digitales (cubiertas en el Capítulo 31), que se basan en algoritmos numéricos y teoría de números.

- **La manufactura y otras empresas comerciales** a menudo necesitan asignar recursos escasos de la manera más beneficiosa. Una compañía petrolera podría necesitar saber dónde colocar sus pozos para maximizar su beneficio esperado. Un candidato político podría querer determinar dónde gastar dinero en publicidad de campaña para maximizar sus posibilidades de ganar una elección. Una aerolínea podría necesitar asignar tripulaciones a vuelos de la manera más económica posible, asegurándose de que cada vuelo esté cubierto y que se cumplan las regulaciones gubernamentales sobre la programación de tripulaciones. Un proveedor de servicios de internet podría necesitar determinar dónde colocar recursos adicionales para atender mejor a sus clientes. Todos estos son ejemplos de problemas que pueden resolverse modelándolos como **programas lineales**, lo cual se explora en el Capítulo 29.

Aunque algunos detalles de estos ejemplos están fuera del alcance de este libro, proporcionamos técnicas subyacentes que se aplican a estos problemas y áreas de problemas. También mostramos cómo resolver muchos problemas específicos, incluyendo el siguiente:

- Dado un diseño mecánico en términos de una biblioteca de piezas, donde cada pieza puede incluir instancias de otras piezas, lista las piezas en orden para que cada pieza aparezca antes que cualquier parte que la utilice. Si el diseño consta de *n* piezas, entonces hay *n!* órdenes posibles, donde *n!* denota la función factorial. Dado que la función factorial crece más rápido que una función exponencial, no se puede generar y verificar cada orden posible. Este problema es un caso de ordenación topológica y el Capítulo 20 muestra cómo resolverlo eficientemente.

- Un médico necesita determinar si una imagen representa un tumor canceroso o benigno. El médico cuenta con imágenes de muchos otros tumores, algunos conocidos como cancerosos y otros como benignos. Un tumor canceroso es más similar a otros tumores cancerosos que a los benignos, y un tumor benigno es más similar a otros tumores benignos. Usando un algoritmo de clustering, como en el Capítulo 33, el médico puede identificar cuál es el resultado más probable.

- Se necesita comprimir un archivo grande de texto para que ocupe menos espacio. Existen varias técnicas, incluyendo la "compresión LZW", que busca secuencias de caracteres repetidas. El Capítulo 15 estudia otro enfoque, el "código de Huffman", que codifica caracteres por secuencias de bits de diferentes longitudes, donde los caracteres más frecuentes se codifican con secuencias de bits más cortas.

Estas listas no son exhaustivas, pero exhiben dos características comunes en muchos problemas algorítmicos interesantes:

1. Tienen muchas soluciones candidatas, y la gran mayoría de ellas no resuelve el problema de manera eficiente. Encontrar una solución óptima sin examinar explícitamente cada posibilidad puede ser un desafío.
2. Tienen aplicaciones prácticas. De los problemas mencionados, encontrar la ruta más corta es un ejemplo claro. Una empresa de transporte, como una de camiones o ferrocarriles, tiene interés financiero en encontrar rutas más cortas para reducir costos de combustible y mano de obra. O un nodo de enrutamiento en internet podría necesitar encontrar la ruta más corta en la red para entregar un mensaje con rapidez. Incluso un conductor que quiera viajar de Nueva York a Boston puede buscar direcciones en una aplicación de navegación.

No todos los problemas resueltos por algoritmos tienen una identificación sencilla de soluciones candidatas. Por ejemplo, en una señal representada por valores numéricos tomados a intervalos regulares, la transformada discreta de Fourier convierte estos valores en una representación frecuencial. Este método aproxima la señal como una suma ponderada de sinusoides, produciendo la intensidad de varias frecuencias que, al sumarse, aproximan la señal original. Además de su papel clave en el procesamiento de señales, las transformadas de Fourier discretas tienen aplicaciones en la compresión de datos y en la multiplicación de grandes polinomios y enteros. El Capítulo 30 presenta un algoritmo eficiente, la transformada rápida de Fourier (conocida como FFT), para resolver este problema. También se bosqueja el diseño de un circuito de hardware para la FFT.

### Estructuras de datos

Este libro también presenta varias estructuras de datos. Una **estructura de datos** es una forma de almacenar y organizar datos para facilitar su acceso y modificación. Utilizar la estructura de datos adecuada es una parte fundamental del diseño de algoritmos. Ninguna estructura de datos única es adecuada para todos los propósitos, por lo que es importante conocer las fortalezas y limitaciones de cada una.

### Técnica

Aunque puedes usar este libro como un "recetario" de algoritmos, es posible que en algún momento enfrentes un problema para el cual no puedas encontrar un algoritmo publicado fácilmente (como muchos de los ejercicios y problemas en este libro). Este libro te enseñará técnicas de diseño y análisis de algoritmos para que puedas desarrollar algoritmos por tu cuenta, demostrar que dan la respuesta correcta y analizar su eficiencia. Diferentes capítulos abordan distintos aspectos de la resolución de problemas algorítmicos. Algunos capítulos tratan problemas específicos, como la búsqueda de medianas y estadísticas de orden en el Capítulo 9, el cálculo de árboles de expansión mínima en el Capítulo 21 y la determinación de un flujo máximo en una red en el Capítulo 24. Otros capítulos introducen técnicas generales, como divide y vencerás en los Capítulos 2 y 4, la programación dinámica en el Capítulo 14 y el análisis amortizado en el Capítulo 16.

### Problemas difíciles

La mayoría de este libro trata sobre algoritmos eficientes. Nuestra medida habitual de eficiencia es la velocidad: ¿cuánto tiempo tarda un algoritmo en producir su resultado? Sin embargo, existen problemas para los cuales no se conoce ningún algoritmo que los resuelva en un tiempo razonable. Estos problemas se conocen como **NP-completos**.

¿Por qué son interesantes los problemas NP-completos? Primero, aunque nunca se ha encontrado un algoritmo eficiente para un problema NP-completo, nadie ha demostrado que un algoritmo eficiente no pueda existir. En otras palabras, nadie sabe si existen algoritmos eficientes para problemas NP-completos. Segundo, el conjunto de problemas **NP-completos** 

Los problemas NP-completos tienen la notable propiedad de que si existe un algoritmo eficiente para cualquiera de ellos, entonces existen algoritmos eficientes para todos ellos. Esta relación entre los problemas NP-completos hace que la falta de soluciones eficientes sea aún más intrigante. En tercer lugar, varios problemas NP-completos son similares, pero no idénticos, a problemas para los que sí conocemos algoritmos eficientes. Los informáticos están intrigados por cómo un pequeño cambio en el enunciado del problema puede causar un gran cambio en la eficiencia del mejor algoritmo conocido.

Debes conocer los problemas NP-completos porque algunos de ellos surgen sorprendentemente a menudo en aplicaciones reales. Si te piden que produzcas un algoritmo eficiente para un problema NP-completo, es probable que pases mucho tiempo en una búsqueda infructuosa. Si, en cambio, puedes demostrar que el problema es NP-completo, puedes dedicar tu tiempo a desarrollar un algoritmo de aproximación eficiente, es decir, un algoritmo que ofrece una buena solución, aunque no necesariamente la mejor posible.

Como ejemplo concreto, considera una empresa de reparto con un depósito central. Cada día, carga camiones de reparto en el depósito y los envía a entregar mercancías a varias direcciones. Al final del día, cada camión debe regresar al depósito para estar listo para ser cargado al día siguiente. Para reducir costos, la empresa quiere seleccionar un orden de paradas de entrega que resulte en la menor distancia total recorrida por cada camión. Este problema es el conocido "problema del viajante de comercio" y es NP-completo. No tiene un algoritmo eficiente conocido. Sin embargo, bajo ciertas suposiciones, conocemos algoritmos eficientes que calculan distancias totales cercanas a la mínima posible. El Capítulo 35 discute tales "algoritmos de aproximación".

_Nota al pie 2_: Para ser precisos, solo los problemas de decisión – aquellos con una respuesta de "sí/no" – pueden ser NP-completos. La versión de decisión del problema del viajante de comercio pregunta si existe un orden de paradas cuya distancia total sea como máximo una cantidad dada.

## Modelos de computación alternativos

Durante muchos años, pudimos contar con que las velocidades de los procesadores aumentarían a un ritmo constante. Sin embargo, las limitaciones físicas presentan un obstáculo fundamental para el aumento continuo de las velocidades de reloj: dado que la densidad de potencia aumenta de manera superlineal con la velocidad del reloj, los chips corren el riesgo de derretirse una vez que sus velocidades de reloj son lo suficientemente altas. Por lo tanto, para realizar más cálculos por segundo, los chips están siendo diseñados para contener no solo uno, sino varios "núcleos" de procesamiento. Podemos comparar estas computadoras multi-núcleo con varias computadoras secuenciales en un solo chip. En otras palabras, son un tipo de "computadora paralela". Para obtener el mejor rendimiento de las computadoras multi-núcleo, necesitamos diseñar algoritmos teniendo en cuenta el paralelismo. El Capítulo 26 presenta un modelo para algoritmos "paralelos por tareas", que aprovechan múltiples núcleos de procesamiento. Este modelo tiene ventajas tanto desde el punto de vista teórico como desde el punto de vista práctico, y muchas plataformas modernas de programación paralela adoptan algo similar a este modelo de paralelismo.

La mayoría de los ejemplos en este libro asumen que todos los datos de entrada están disponibles cuando un algoritmo comienza a ejecutarse. Gran parte del trabajo en el diseño de algoritmos hace la misma suposición. Sin embargo, para muchos ejemplos importantes del mundo real, la entrada llega con el tiempo, y el algoritmo debe decidir cómo proceder sin saber qué datos llegarán en el futuro. En un centro de datos, los trabajos llegan y se van constantemente, y un algoritmo de planificación debe decidir cuándo y dónde ejecutar un trabajo, sin saber qué trabajos llegarán en el futuro. El tráfico debe ser enrutado en Internet basándose en el estado actual, sin saber dónde llegará el tráfico en el futuro. Las salas de emergencias de los hospitales toman decisiones de triaje sobre qué pacientes tratar primero sin saber cuándo llegarán otros pacientes en el futuro y qué tratamientos necesitarán. Los algoritmos que reciben su entrada a lo largo del tiempo, en lugar de tener toda la entrada presente al inicio, son _algoritmos en línea_, que el Capítulo 27 examina.

## Ejercicios

### 1.1-1

Describe tu propio ejemplo del mundo real que requiera ordenar. Describe uno que requiera encontrar la distancia más corta entre dos puntos.

### 1.1-2

Además de la velocidad, ¿qué otras medidas de eficiencia podrías necesitar considerar en un entorno del mundo real?

### 1.1-3

Selecciona una estructura de datos que hayas visto y discute sus fortalezas y limitaciones.

### 1.1-4

¿En qué se parecen los problemas del camino más corto y del viajante de comercio mencionados anteriormente? ¿En qué se diferencian?

### 1.1-5

Sugiere un problema del mundo real en el que solo la mejor solución sea aceptable. Luego, propón uno en el que una solución "aproximadamente" buena sea suficiente.

### 1.1-6

Describe un problema del mundo real en el que a veces toda la entrada esté disponible antes de que necesites resolver el problema, pero otras veces la entrada no esté completamente disponible de antemano y llegue con el tiempo.


# Los algoritmos como tecnología

Si las computadoras fueran infinitamente rápidas y la memoria de la computadora fuera gratuita, ¿tendrías alguna razón para estudiar algoritmos? La respuesta es sí, aunque solo sea porque aún querrías estar seguro de que tu método de solución termina y lo hace con la respuesta correcta.

Si las computadoras fueran infinitamente rápidas, cualquier método correcto para resolver un problema sería válido. Probablemente querrías que tu implementación estuviera dentro de los límites de las buenas prácticas de ingeniería de software (por ejemplo, tu implementación debería estar bien diseñada y documentada), pero la mayoría de las veces usarías el método que fuera más fácil de implementar.

Por supuesto, las computadoras pueden ser rápidas, pero no son infinitamente rápidas. Por lo tanto, el tiempo de computación es un recurso limitado, lo que lo hace precioso. Aunque el dicho dice: "El tiempo es dinero", el tiempo es incluso más valioso que el dinero: puedes recuperar el dinero después de gastarlo, pero una vez que el tiempo se ha gastado, nunca puedes recuperarlo. La memoria puede ser económica, pero no es infinita ni gratuita. Debes elegir algoritmos que utilicen los recursos de tiempo y espacio de manera eficiente.

## Eficiencia

Diferentes algoritmos diseñados para resolver el mismo problema a menudo difieren dramáticamente en su eficiencia. Estas diferencias pueden ser mucho más significativas que las diferencias debidas al hardware y al software.

### Algoritmos como tecnología

Si las computadoras fueran infinitamente rápidas y la memoria de la computadora fuera gratuita, ¿tendrías alguna razón para estudiar algoritmos? La respuesta es sí, aunque solo fuera para asegurarte de que tu método de solución termina y lo hace con la respuesta correcta.

Si las computadoras fueran infinitamente rápidas, cualquier método correcto para resolver un problema sería válido. Probablemente querrías que tu implementación estuviera dentro de los límites de las buenas prácticas de ingeniería de software (por ejemplo, tu implementación debería estar bien diseñada y documentada), pero la mayoría de las veces usarías el método que fuera más fácil de implementar.

Por supuesto, las computadoras pueden ser rápidas, pero no infinitamente rápidas. Por lo tanto, el tiempo de computación es un recurso limitado, lo que lo hace valioso. Aunque el dicho dice: "El tiempo es dinero", el tiempo es incluso más valioso que el dinero: puedes recuperar el dinero después de gastarlo, pero una vez que se gasta el tiempo, nunca puedes recuperarlo. La memoria puede ser económica, pero no es infinita ni gratuita. Debes elegir algoritmos que utilicen los recursos de tiempo y espacio de manera eficiente.

#### Eficiencia

Diferentes algoritmos diseñados para resolver el mismo problema a menudo difieren dramáticamente en su eficiencia. Estas diferencias pueden ser mucho más significativas que las diferencias debidas al hardware y al software.

Como ejemplo, el Capítulo 2 introduce dos algoritmos para ordenar. El primero, conocido como <u>insertion sort</u>, toma un tiempo aproximadamente igual a c<sub>1</sub>n<sup>2</sup> para ordenar n elementos, donde c<sub>1</sub> es una constante que no depende de n. Es decir, toma un tiempo aproximadamente proporcional a n<sup>2</sup>. El segundo, <u>merge sort</u>, toma un tiempo aproximadamente igual a c<sub>2</sub>n log n, donde log n representa log<sub>2</sub>n y c<sub>2</sub> es otra constante que tampoco depende de n. El <u>insertion sort</u> generalmente tiene un factor constante más pequeño que el <u>merge sort</u>, de modo que c<sub>1</sub> < c<sub>2</sub>. Veremos que los factores constantes pueden tener un impacto mucho menor en el tiempo de ejecución que la dependencia del tamaño de la entrada n. Escribamos el tiempo de ejecución del <u>insertion sort</u> como c<sub>1</sub>n * n y el tiempo de ejecución del <u>merge sort</u> como c<sub>2</sub>n * log n. Entonces vemos que donde el <u>insertion sort</u> tiene un factor de n en su tiempo de ejecución, el <u>merge sort</u> tiene un factor de log n, que es mucho más pequeño. Por ejemplo, cuando n es 1000, log n es aproximadamente 10, y cuando n es 1,000,000, log n es aproximadamente solo 20. Aunque el <u>insertion sort</u> generalmente se ejecuta más rápido que el <u>merge sort</u> para tamaños de entrada pequeños, una vez que el tamaño de la entrada n se vuelve lo suficientemente grande, la ventaja del <u>merge sort</u> de log n versus n más que compensa la diferencia en los factores constantes. No importa cuánto más pequeño sea c<sub>1</sub> que c<sub>2</sub>, siempre hay un punto de cruce más allá del cual el <u>merge sort</u> es más rápido.

Para un ejemplo concreto, comparemos una computadora más rápida (computadora A) que ejecuta **insertion sort** contra una computadora más lenta (computadora B) que ejecuta **merge sort**. Ambas deben ordenar un arreglo de 10 millones de números. (Aunque 10 millones de números puedan parecer muchos, si los números son enteros de ocho bytes, entonces la entrada ocupa aproximadamente 80 megabytes, lo que cabe en la memoria de incluso una computadora portátil económica varias veces). Supongamos que la computadora A ejecuta 10 mil millones de instrucciones por segundo (más rápido que cualquier computadora secuencial en el momento de escribir esto) y la computadora B ejecuta solo 10 millones de instrucciones por segundo (mucho más lenta que la mayoría de las computadoras contemporáneas), por lo que la computadora A es 1000 veces más rápida que la computadora B en potencia de cálculo bruta. Para hacer la diferencia aún más dramática, supongamos que el programador más hábil del mundo codifica **insertion sort** en lenguaje de máquina para la computadora A, y el código resultante requiere 2n<sup>2</sup> instrucciones para ordenar n números. Supongamos además que un programador promedio implementa **merge sort**, usando un lenguaje de alto nivel con un compilador ineficiente, y el código resultante toma 50n log n instrucciones. Para ordenar 10 millones de números, la computadora A toma:

(2 * (10<sup>7</sup>)<sup>2</sup> instrucciones) / (10<sup>10</sup> instrucciones/segundo) = 20,000 segundos (más de 5.5 horas),

mientras que la computadora B toma:

(50 * 10<sup>7</sup> log 10<sup>7</sup> instrucciones) / (10<sup>7</sup> instrucciones/segundo) ≈ 1163 segundos (menos de 20 minutos).

Al usar un algoritmo cuyo tiempo de ejecución crece más lentamente, incluso con un compilador deficiente, la computadora B funciona más de 17 veces más rápido que la computadora A. La ventaja de **merge sort** es aún más pronunciada al ordenar 100 millones de números: mientras que **insertion sort** toma más de 23 días, **merge sort** toma menos de cuatro horas. Aunque 100 millones pueda parecer un número grande, hay más de 100 millones de búsquedas web cada media hora, más de 100 millones de correos electrónicos enviados cada minuto, y algunas de las galaxias más pequeñas (conocidas como galaxias enanas ultracompactas) contienen alrededor de 100 millones de estrellas. En general, a medida que aumenta el tamaño del problema, también lo hace la ventaja relativa de **merge sort**.

### Algoritmos y otras tecnologías

El ejemplo anterior muestra que debes considerar los algoritmos, al igual que el hardware de la computadora, como una _tecnología_. El rendimiento total del sistema depende tanto de elegir algoritmos eficientes como de elegir hardware rápido. Así como se están logrando avances rápidos en otras tecnologías informáticas, también se están logrando en algoritmos.

Podrías preguntarte si los algoritmos son realmente tan importantes en las computadoras contemporáneas a la luz de otras tecnologías avanzadas, como:

* arquitecturas de computadoras avanzadas y tecnologías de fabricación,

* interfaces gráficas de usuario (GUIs) intuitivas y fáciles de usar,

* sistemas orientados a objetos,

* tecnologías web integradas,

* redes rápidas, tanto cableadas como inalámbricas,

* aprendizaje automático (machine learning),

* y dispositivos móviles.

La respuesta es sí. Aunque algunas aplicaciones no requieren explícitamente contenido algorítmico a nivel de aplicación (como algunas aplicaciones web simples), muchas sí lo hacen. Por ejemplo, considera un servicio basado en la web que determina cómo viajar de un lugar a otro. Su implementación dependería de hardware rápido, una interfaz gráfica de usuario, redes de área amplia y posiblemente también de la orientación a objetos. También requeriría algoritmos para operaciones como encontrar rutas (probablemente usando un algoritmo de camino más corto), renderizar mapas e interpolar direcciones.

Además, incluso una aplicación que no requiere contenido algorítmico a nivel de aplicación depende en gran medida de algoritmos. ¿La aplicación depende de hardware rápido? El diseño del hardware utiliza algoritmos. ¿La aplicación depende de interfaces gráficas de usuario? El diseño de cualquier GUI depende de algoritmos. ¿La aplicación depende de redes? El enrutamiento en redes depende en gran medida de algoritmos. ¿La aplicación fue escrita en un lenguaje distinto al código de máquina? Entonces fue procesada por un compilador, intérprete o ensamblador, todos los cuales hacen un uso extensivo de algoritmos. Los algoritmos están en el núcleo de la mayoría de las tecnologías utilizadas en las computadoras contemporáneas.

El aprendizaje automático (machine learning) puede considerarse como un método para realizar tareas algorítmicas sin diseñar explícitamente un algoritmo, sino infiriendo patrones a partir de datos y, por lo tanto, aprendiendo automáticamente una solución. A primera vista, el aprendizaje automático, que automatiza el proceso de diseño de algoritmos, puede parecer que hace obsoleto el aprendizaje sobre algoritmos. Sin embargo, lo contrario es cierto. El aprendizaje automático es en sí mismo una colección de algoritmos, solo que bajo un nombre diferente. Además, actualmente parece que los éxitos del aprendizaje automático son principalmente para problemas en los que nosotros, como humanos, no entendemos realmente cuál es el algoritmo correcto. Ejemplos prominentes incluyen la visión por computadora y la traducción automática de idiomas. Para problemas algorítmicos que los humanos comprenden bien, como la mayoría de los problemas en este libro, los algoritmos eficientes diseñados para resolver un problema específico suelen ser más exitosos que los enfoques de aprendizaje automático.

La ciencia de datos es un campo interdisciplinario con el objetivo de extraer conocimiento y percepciones de datos estructurados y no estructurados. La ciencia de datos utiliza métodos de estadística, informática y optimización. El diseño y análisis de algoritmos es fundamental para este campo. Las técnicas centrales de la ciencia de datos, que se superponen significativamente con las del aprendizaje automático, incluyen muchos de los algoritmos presentados en este libro.

Además, con las capacidades cada vez mayores de las computadoras, las utilizamos para resolver problemas más grandes que nunca. Como vimos en la comparación anterior entre **insertion sort** y **merge sort**, es en tamaños de problemas más grandes donde las diferencias en eficiencia entre los algoritmos se vuelven particularmente prominentes.

Tener una base sólida de conocimiento y técnica algorítmica es una característica que define al programador verdaderamente hábil. Con la tecnología informática moderna, puedes realizar algunas tareas sin saber mucho sobre algoritmos, pero con un buen conocimiento de algoritmos, puedes hacer mucho, mucho más.

#### Ejercicios

_1.2-1_

Da un ejemplo de una aplicación que requiera contenido algorítmico a nivel de aplicación y discute la función de los algoritmos involucrados.

_1.2-2_

Supongamos que, para entradas de tamaño _n_ en una computadora en particular, **insertion sort** se ejecuta en 8n<sup>2</sup> pasos y **merge sort** se ejecuta en 64n log n pasos. ¿Para qué valores de _n_ **insertion sort** supera a **merge sort**?

_1.2-3_

¿Cuál es el valor más pequeño de _n_ tal que un algoritmo cuyo tiempo de ejecución es 100n<sup>2</sup> se ejecute más rápido que un algoritmo cuyo tiempo de ejecución es 2<sup>n</sup> en la misma máquina?

## Problemas

### Comparación de tiempos de ejecución

Para cada función _f(n)_ y tiempo _t_ en la siguiente tabla, determina el tamaño más grande _n_ de un problema que puede resolverse en el tiempo _t_, asumiendo que el algoritmo para resolver el problema toma _f(n)_ microsegundos.

| Función       | 1 segundo | 1 minuto | 1 hora | 1 día | 1 mes | 1 año | 1 siglo |
|---------------|-----------|----------|--------|-------|-------|-------|---------|
| log n         |           |          |        |       |       |       |         |
| sqrt(n)       |           |          |        |       |       |       |         |
| n             |           |          |        |       |       |       |         |
| n log n       |           |          |        |       |       |       |         |
| n²            |           |          |        |       |       |       |         |
| n³            |           |          |        |       |       |       |         |
| 2ⁿ            |           |          |        |       |       |       |         |
| n!            |           |          |        |       |       |       |         |

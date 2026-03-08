
ISEÑO E IMPLEMENTACIÓN DE UNA PLATAFORMA DE ESTABILIZACIÓN PARA UNA BICICLETA UTILIZANDO UN VOLANTE DE INERCIA
Nombre_Empresa[JH1.1] 





 





Autor
Jeferson Hernan Hernandez Moreno 
Fabian Andrés Reyes Romero 




UNIVERSIDAD DISTRITAL FRANCISCO JOSÉ DE CALDAS
Facultad Tecnológica 
Ingeniería en (Control/ Telecomunicaciones)


Bogotá D.C. Enero,2026
 
DISEÑO E IMPLEMENTACIÓN DE UNA PLATAFORMA DE ESTABILIZACIÓN PARA UNA BICICLETA UTILIZANDO UN VOLANTE DE INERCIA

Nombre_Empresa


 



Autor
Jeferson Hernan Hernandez Moreno Código: 20201383013 
jhhernandezm@udistrital.edu.co
Fabian Andrés Reyes Romero Código: 20201383011
fareyesr@udistrital.edu.co


INFORME FINAL DE PASANTÍA

Presentado para optar al título de: Ingeniero en Control y Automatización
 

Director Interno
Alexander Jiménez Triana, PhD

Director Externo
Alexander Jiménez[JH2.1] Triana, PhD


UNIVERSIDAD DISTRITAL FRANCISCO JOSÉ DE CALDAS
Facultad Tecnológica 
Ingeniería en Ingeniero en Control y Automatización
Bogotá D.C. Enero, 2026 
Dedicatoria
Dedicamos este proyecto a Dios por ser el inspirador para cada uno de nuestros pasos dados en nuestro convivir diario; a nuestros padres por ser los guías en el sendero de cada acto que realizamos hoy, mañana y siempre; a nuestras parejas, a nuestras familias, por ser el incentivo para seguir adelante con este objetivo, a nuestro director Alexander Jiménez Triana,, por entregarnos sus conocimientos para realizar y cumplir los  propósitos hemos planteado durante el proyecto.
 
Índice
/*en esta sección se detallan todos los capítulos que son desarrollados en el texto, deben tener interlineado simple como se muestra a continuación*/
Dedicatoria	i
Índice	ii
Índice de Figuras	iii
Índice de Tablas	iv
Índice de Anexos	v
Glosario	vi
Lista de Abreviaturas y Siglas	vii
Resumen	viii
1.	Introducción	1
2.	Presentación de la Empresa	2
3.	Planteamiento del problema en la Empresa	3
4.	Justificación	4
5.	Objetivos	5
5.1.	Objetivo General	5
5.2.	Objetivos específicos	5
6.	Marco de referencia	6
6.1.	Antecedentes	6
6.2.	Marco teórico	6
6.3.	Marco Legal	6
7.	Actividades realizadas durante la pasantía	7
8.	Resultados	8
9.	Conclusiones y Recomendaciones	9
10.	Referencias	10
11.	Anexos	11

 
Índice de Figuras
/*en esta sección se detallan todas las figuras que son expuestas en el texto, deben tener interlineado simple como se muestra a continuación */
Figura 2.1: Imagen del logo de la Universidad	5
 
Índice de Tablas
/*Listado de todas las tablas que son presentadas en el texto, deben tener interlineado simple como se muestra a continuación */
Tabla 2.1: Ejemplo simple de Tabla	5
 
Índice de Anexos

Los Anexos se incorporan como  textos al final del documento o hipervínculos dentro del texto.

Anexo 1……………………………………………...……………………………………………15
 
Glosario

Sistema de control	Un conjunto de componentes, incluyendo sensores y actuadores, que permiten al sistema ajustar su comportamiento para lograr un objetivo específico.
Sistema de estabilización	Un conjunto de componentes que permite al sistema mantener su equilibrio y evitar que se caiga.
 Sensores	Dispositivos que permiten al sistema recopilar datos sobre su entorno y su estado, como acelerómetros, giroscopios, sensores de presión, etc.
 Actuadores	Componentes que permiten al sistema interactuar con su entorno, como motores eléctricos, frenos, etc.
 Controlador	El componente central del sistema de control que procesa los datos de los sensores y envía comandos a los actuadores para ajustar el comportamiento del sistema.
Algoritmos de control	Software que permite al controlador tomar decisiones y ajustar los movimientos del sistema en función de los datos de los sensores.
 Retroalimentación	El proceso de utilizar información del estado actual del sistema para ajustar su comportamiento y lograr un objetivo específico.
 Estabilidad	La capacidad del sistema para mantener su equilibrio y evitar caerse.
Centro de gravedad	El punto en el que se concentra todo el peso del sistema, y que es fundamental para su estabilidad.
 Posicionamiento	La posición y orientación del sistema, que es importante para mantener su equilibrio y evitar caídas.

 
 Lista de Abreviaturas y Siglas
Sigla/Abreviatura	Significado
ADRC	Control por Rechazo Activo de Perturbaciones (Active Disturbance Rejection Control)
BMS	Sistema de Gestión de Baterías (Battery Management System)
CMG	Giroscopio de Control de Momento (Control Moment Gyroscope)
DC	Corriente Continua (Direct Current)
DMP	Procesador de Movimiento Digital (Digital Motion Processor)
ESO	Observador de Estado Extendido (Extended State Observer)
ESP32	Microcontrolador de doble núcleo con conectividad inalámbrica integrada
I2C	Protocolo de comunicación serie Inter-Integrated Circuit
IMU	Unidad de Medición Inercial (Inertial Measurement Unit)
LiFePO4	Batería de Litio-Ferrofosfato
LQR	Regulador Cuadrático Lineal (Linear Quadratic Regulator)
MARG	Sistema de Referencia de Actitud Magnético, Angular y Gravitatorio
MPU9250	Sensor inercial de 9 grados de libertad (Acelerómetro + Giroscopio + Magnetómetro)
PCB	Placa de Circuito Impreso (Printed Circuit Board)
PID	Controlador Proporcional-Integral-Derivativo
PSoC	Sistema Programable en un Chip (Programmable System-on-Chip)
PWM	Modulación por Ancho de Pulsos (Pulse Width Modulation)
RPM	Revoluciones por Minuto
SMC	Control por Modos Deslizantes (Sliding Mode Control)

 
Resumen
Este trabajo de grado se alinea al contexto de desarrollo e implementación de sistemas integrados de control, los cuales se han sido participes en el contexto de ejecución de actividades de los distintos sectores de desarrollo económico y social de una población, brindando calidad y eficiencia a la prestación de servicios o la creación de nuevos productos emergentes o actuales, pues si bien el ser humano ha dedicado su tiempo en la historia a la creación de nuevos sistemas los cuales ayudan a mejorar nuestra calidad de vida o su vez toma algunos sistemas y los potencializa generando así una gran variedad de posibles soluciones a una problemática.

A partir de lo anterior, el desarrollo profesional de un estudiante en automatización y control es el saber del control y debe contemplar la teoría con la práctica de una manera integrada lo más realista posible, con el fin de poder generar competencias necesarias y disponibles en el mercado laboral actual, en conclusión, surge la necesidad buscar y dar solución a un problema, como lo es la movilidad en la ciudad de Bogotá, por ello se ha planteado ayudar a dar solución a este problema con vehículos autónomos capaces de realizar un desplazamiento por si solos y previniendo algún tipo de choco o accidente, por ello en este trabajo se da un inicio de esto con un modelo de una bicicleta que es capaz de mantenerse estable sin alguna tipo de intervención por el hombre.

Como solución a esta necesidad, se desarrolló el modelo de un volante el cual aprovecha la velocidad y momento angular para mantener estable cualquier tipo de bicicleta. El volante fue acoplado a una bicicleta y por medio de un controlador (PID) cuyo deber es mantener controlado un motor DC y permitir jugar con la posición de dicho volante, esto con la finalidad de guiar y aprovechar al máximo el torque generado a partir de momento angular a la dirección que necesita la bicicleta para mantenerse estable.


 
	Introducción

En un mundo en constante evolución, la búsqueda de soluciones innovadoras y eficientes ha impulsado el desarrollo de tecnologías disruptivas que transforman diversas áreas de la vida cotidiana. Uno de los campos que ha experimentado una revolución constante es el diseño de vehículos de transporte personal, con la bicicleta como uno de los pilares fundamentales de la movilidad sostenible. En este contexto, surge un proyecto visionario: el diseño de una bicicleta autónoma y estable, capaz de recorrer distancias cortas sin intervención humana.

El objetivo principal de este proyecto es desarrollar una bicicleta que aproveche principios de física y tecnología avanzada para garantizar su estabilidad y autonomía en recorridos cortos. Para lograrlo, se ha implementado un sistema ingenioso basado en un volante de inercia en constante rotación, este juega un papel esencial en el mantenimiento de la estabilidad de la bicicleta. Este volante de inercia genera una fuerza angular significativa, que se aprovecha para contrarrestar los desequilibrios y mantener la estabilidad de la bicicleta durante su movimiento.

Un componente crucial en este diseño es el conjunto formado por sensores de movimiento, aceleración y velocidad, que trabajan en conjunto para recopilar información sobre la posición y el ángulo de inclinación de la bicicleta. Estos sensores permiten una monitorización constante y precisa de la bicicleta, lo que es esencial para ajustar el sistema y mantenerla en posición vertical durante el trayecto.

La información recopilada por los sensores se utiliza para controlar el giroscopio, un mecanismo que regula la rotación constante del volante de inercia. El giroscopio es esencialmente el encargado de la autonomía de la bicicleta, ya que ajusta la velocidad y la dirección de rotación del volante para contrarrestar los movimientos no deseados de la bicicleta. Esta interacción precisa entre los sensores y el giroscopio permite una respuesta rápida y fluida a los cambios en el terreno y las condiciones de movimiento.

El sistema de control que gobierna esta interacción se basa en un controlador Proporcional-Integral-Derivativo (PID). Este controlador calcula y ajusta continuamente las señales de control necesarias para mantener la bicicleta en equilibrio y en la dirección correcta. El microcontrolador juega un papel central en este proceso, ya que utiliza el ángulo de inclinación detectado para regular la acción del giroscopio a través del controlador PID.

A medida que avanzamos en este documento, exploraremos en detalle los componentes clave de este diseño innovador de bicicleta autónoma. Analizaremos cómo el volante de inercia, los sensores de movimiento, el giroscopio y el controlador PID interactúan en armonía para lograr un equilibrio excepcional y una autonomía confiable en recorridos cortos. Además, examinaremos los desafíos técnicos, las soluciones implementadas y las posibles aplicaciones futuras de esta tecnología.

En resumen, este proyecto representa un paso audaz hacia la transformación de la movilidad personal. La combinación de principios físicos, tecnología avanzada y un diseño ingenioso da como resultado una bicicleta autónoma capaz de mantenerse estable y seguir recorriendo distancias cortas sin intervención humana. Este documento se sumerge en los aspectos técnicos y conceptuales de esta innovación, explorando su funcionamiento interno y su potencial para revolucionar la forma en que concebimos el transporte personal y sostenible.


 
	Presentación de la Empresa
En esta sección se debe presentar la empresa, describiendo por lo menos los siguientes elementos:

	Razón Social
	Actividad a la que se dedica
	Reseña Histórica
	Misión
	Visión
	Estructura organizacional 
	Área o grupo de trabajo en el cual el estudiante desarrolló su pasantía. [JH3.1]


	Planteamiento del problema en la Empresa

En el complejo entramado urbano de Bogotá, el auge de la movilidad ha dado origen a desafíos de envergadura que afectan la calidad de vida de sus ciudadanos y la sostenibilidad del entorno. La proliferación de vehículos, la congestión del tráfico y la preocupación por la salud ambiental han encendido las alarmas, creando un llamado urgente para encontrar soluciones innovadoras y efectivas. Entre las alternativas que han surgido para mitigar estos problemas, la bicicleta se presenta como una opción atractiva, pero su adopción no está exenta de obstáculos.

A pesar de las innegables ventajas que ofrece, el uso de la bicicleta en el contexto urbano plantea retos sustanciales en lo que respecta a la seguridad y la estabilidad de los ciclistas. La interacción con otros vehículos, las condiciones cambiantes de las vías y los imprevistos del entorno pueden dar lugar a situaciones peligrosas y a la pérdida de equilibrio, resultando en accidentes y lesiones. La falta de seguridad en el desplazamiento en bicicleta no solo pone en riesgo la integridad física de los usuarios, sino que también puede disuadir a una parte de la población de adoptar este medio de transporte.

Este planteamiento del problema se centra en la necesidad apremiante de abordar los desafíos de seguridad y estabilidad que enfrentan los biciusuarios en Bogotá. La idea central consiste en desarrollar una bicicleta autónoma que, mediante tecnologías avanzadas y un sistema de control inteligente, pueda mantenerse estable sin requerir la intervención constante del ciclista. Este enfoque de diseño tiene como objetivo principal ofrecer una solución que responda directamente a las problemáticas actuales, proporcionando a los usuarios un medio de transporte seguro y confiable.

La investigación propuesta se enfocará en la creación y el desarrollo de esta bicicleta autónoma. Esto involucra aspectos técnicos de vanguardia, como la integración de sensores de alta precisión para monitorear el movimiento, la aceleración y la velocidad. Asimismo, se explorará la implementación de un sistema de control autónomo que se adapte en tiempo real a las condiciones variables del entorno. El objetivo final es concebir una bicicleta que no solo brinde estabilidad, sino que también colabore activamente con el usuario para prevenir accidentes y mejorar la experiencia de viaje.

El impacto deseado de esta investigación es doble: por un lado, se busca fomentar la seguridad y la confianza de los biciusuarios en las calles de Bogotá, incentivando su participación activa en una movilidad sostenible. Por otro lado, se aspira a establecer un precedente para el desarrollo de tecnologías que aborden problemáticas urbanas complejas, utilizando la bicicleta autónoma como una solución piloto.

En resumen, este estudio tiene como objetivo el diseño y desarrollo de una bicicleta autónoma que aborde los desafíos de seguridad y estabilidad de los biciusuarios en Bogotá. La creación de esta bicicleta no solo pretende ofrecer una solución concreta, sino también sentar las bases para una movilidad urbana más segura, sostenible e inteligente en la ciudad.
 
 
	Justificación

La problemática de la frecuencia de los accidentes y la mortalidad entre los biciusuarios en la ciudad de Bogotá es un desafío inaplazable que requiere una solución efectiva y específica. A pesar de la creciente adopción de la bicicleta como medio de transporte alternativo, persisten obstáculos significativos que afectan la seguridad y la confianza de quienes optan por este modo de movilidad. En respuesta a esta problemática, se propone llevar a cabo un estudio que aborde de manera integral la inestabilidad de las bicicletas en situaciones de pérdida de equilibrio, presentando una solución innovadora a través de un sistema de asistencia y estabilización.

La justificación de esta investigación se basa en la evidencia proporcionada por los resultados del estado del arte, los cuales revelan la ausencia de una solución integral para la problemática planteada. A pesar de los esfuerzos realizados, los estudios actuales no han logrado implementar un sistema que proporcione una asistencia adecuada a los biciusuarios en momentos críticos de inestabilidad. Esta falta de una solución efectiva demuestra la necesidad imperante de desarrollar un enfoque específico para abordar esta problemática.

Además de la falta de una solución viable, otro argumento sustancial para justificar esta investigación es la creciente preocupación por el medio ambiente en la ciudad de Bogotá. El aumento de emisiones de gases y la contaminación generada por vehículos a combustión han exacerbado la calidad del aire y amenazan la salud de los ciudadanos. En este sentido, la promoción del uso de bicicletas eléctricas como una alternativa más amigable con el medio ambiente se convierte en un motivo adicional para desarrollar un sistema de estabilización que incentive la adopción masiva de este medio de transporte.

Esta investigación también tiene el potencial de transformar la movilidad en la ciudad y mejorar el tráfico vehicular. La naturaleza versátil y ágil de la bicicleta ofrece la posibilidad de reducir la congestión, mejorar los tiempos de desplazamiento y contribuir a la optimización de los recursos de infraestructura urbana. La implementación exitosa de sistemas de estabilidad para bicicletas podría conducir a un cambio cultural en la elección de medios de transporte, alentando a más ciudadanos a adoptar la bicicleta como una opción confiable y segura.

Es importante destacar que esta investigación no solo busca ofrecer una solución práctica a un problema crítico de la ciudad, sino que también busca llenar un vacío académico y tecnológico. A nivel nacional, no existen desarrollos con el mismo tipo de actuador propuesto en esta investigación. La oportunidad de llevar a cabo un estudio académico en profundidad y lograr una implementación efectiva de un sistema de estabilización para bicicletas podría tener un impacto significativo tanto en el ámbito científico como en el tecnológico.

En resumen, la justificación de esta investigación se basa en la necesidad demostrada de abordar la inestabilidad de las bicicletas en situaciones críticas, la falta de soluciones efectivas actuales, la urgencia de promover alternativas amigables con el medio ambiente, el potencial de transformar la movilidad urbana y la oportunidad de contribuir a la academia y la tecnología nacional. Este estudio no solo responde a una problemática real y actual, sino que también ofrece perspectivas innovadoras para mejorar la calidad de vida en la ciudad de Bogotá.

 
	Objetivos
	Objetivo General
Diseñar una plataforma mecánica capaz de estabilizar una bicicleta durante un corto periodo de tiempo, simulando condiciones de equilibrio en estado de reposo o baja velocidad. La estabilización se logrará mediante un volante de inercia que, por medio de un sistema de control, aprovechará el momento angular generado por su rotación, junto con el efecto giroscópico, para oponerse activamente a las perturbaciones que puedan afectar el balance del sistema. Este diseño permitirá analizar y validar el comportamiento dinámico de la bicicleta frente a pequeñas variaciones.
	Objetivos específicos

1. Diseñar y construir un modelo físico funcional de la planta, que permita la integración de un sistema de control para analizar el comportamiento dinámico de una bicicleta en condiciones de equilibrio inestables. 	
2. Diseñar e implementar un volante de inercia adecuado al sistema, realizando las modificaciones necesarias a la estructura de la bicicleta para mantener el centro de masa lo más centrado posible, optimizando así el control y la estabilidad.
3. Evaluar experimentalmente la respuesta del sistema bajo diferentes condiciones de funcionamiento, midiendo variables clave como el ángulo de inclinación, la velocidad de respuesta y la efectividad del sistema.


















	Marco de referencia
	Antecedentes

A continuación, vamos a presentar el estado del arte en particular del control y estabilidad de las bicicletas, en donde se realiza una investigación de sobre proyectos similares a nivel nacional e internacional, en ellos evidenciamos los sistemas de control usados para este tipo de sistema además de observar el análisis del modelo matemático las etapas de simulación y los resultados en cada uno de los proyectos, posteriormente se mencionan algunos de los proyectos más relevantes y de los cuales se tomaron en cuenta para la realización de este proyecto.

DISEÑO E IMPLEMENTACIÓN DE UNA ESTRATEGIA AVANZADA DE CONTROL, 
PARA RESOLVER EL PROBLEMA DE ESTABILIDAD DE UNA BICICLETA DURANTE UN RECORRIDO LIBRE, SIN CONDUCTOR Y A VELOCIDAD CONSTANTE

A nivel nacional se encuentran trabajos muy buenos los cuales brindan una solución ala auto 
estabilización de una bicicleta, un ejemplo de ello es en la universidad Nacional de Colombia en el 
cual se realizó un proyecto en donde se propone una técnica avanzada de control para estabilizar la inclinación de una bicicleta que se desplaza libremente a una velocidad constante mínima. Se 
analizaron varios modelos matemáticos de la dinámica del sistema y luego desarrollaron un prototipo. En el cual lo expusieron ante las posibles perturbaciones e incertidumbres más relevantes 
que afectarían a la planta. A partir del comportamiento inestable y no lineal en la posición vertical de la bicicleta, dedujeron que puede ser modelado como un sistema lineal de parámetros variantes en el tiempo (LPV) que depende de la velocidad de avance.
Con esta información obtenida a través del análisis se enfocaron en el Control por Rechazo Activo 
de Perturbaciones (ADRC) y optaron por un control basado en observador GPI este controlador con una estructura robusta permitió minimizar el error de seguimiento y rechazo de perturbaciones ante las incertidumbres y dinámicas no modeladas. Este controlador básicamente gira hacia la derecha o izquierda la dirección de la bicicleta para contrarrestar su inclinación de forma similar a un péndulo invertido, pero con un desplazamiento sobre el suelo.
Los resultados que obtuvieron al adoptar la estrategia de control basada en observador GPI mostro 
mediante las simulaciones y los resultados experimentales, su contundencia a la solución del problema de estabilización de la bicicleta, con un desempeño superior a otras estrategias de control 
que también se implementaron, las cuales fueron, PID, con compensador en atraso, compensador en adelanto y realimentación por variables de estado. [1]


CONTROL POR RECHAZO ACTIVO DE PERTURBACIONES PARA ESTABILIZAR UNA BICICLETA EMPLEANDO UN GIROSCOPIO DE CONTROL DE MOMENTO DE UN EJE 

Para el año 2018 en la Universidad de San Buenaventura sede Bogotá, se plantea una de las maneras para abordar el problema de estabilizarla una bicicleta en reposo. A través del análisis de la dinámica no lineal e inherentemente inestable del sistema, se aborda solucionar este problema por medio de la utilización de un sistema del rechazo activo de perturbaciones (ADR) sobre la base del control convencional en cascada usando observadores de estados extendidos (ESO) y sintonización optima, con el método regulación cuadrática lineal (LQR). Además del método de control se realiza un giroscopio de control de momento (CMG) como actuador. En este documento se obtuvo como resultado un control robusto que fue capaz de auto estabilizar la bicicleta en el entorno de simulación ADAMS. así como también se evidencio que la filosofía ADR mostró ser efectiva, debido a que doto al sistema de control con la habilidad de rechazar en línea, de manera aproximada, las incertidumbres, no linealidades y perturbaciones, por medio de la inyección de su estimación en la ley de control.[2]

DISEÑO DE UNA PLATAFORMA DIDÁCTICA PARA EL ESTUDIO DEL EQUILIBRIO DE UNA BICICLETA A TRAVÉS DE TÉCNICAS DE CONTROL 

Por otra parte, en latino América uno de los trabajos importantes que vale la pena mencionar, se realizó en la Universidad del valle de Guatemala, el cual consiste analizar los efectos de distintos controladores que actúan sobre una bicicleta por medio de simulaciones gráficas. Fue implementado un programa con secciones editables por el usuario en donde pueden modificarse los parámetros que definen una bicicleta como por ejemplo su geometría, sus parámetros físicos, condiciones iniciales; adicionalmente se incluyó una sección en donde pueden seleccionarse distintos controladores a utilizar para luego ser modificarlos individualmente, permitiendo observar el comportamiento de cada uno en el sistema de la bicicleta, donde este se observa mediante una simulación 3D y al final de cada prueba se provee al usuario una sección de resultados, así como gráficas representativas del comportamiento del sistema.[3]

CONTROL MOMENT GYROSCOPE STABILIZATION AND MANEUVERABILITY OF INHERENTLY UNSTABLE VEHICLES AND MOBILE ROBOTS 

En la Universidad de estado de Ohio - Departamento de Mecánica y Ingeniería Aeroespacial en el estado de Ohio – Columbus (Estados unidos). En el laboratorio de investigación de la fuerza aérea a través de un programa conocido como transporte de operaciones especiales, se propone en diseñar y fabricar vehículos todo terreno semiautónomo capaces de transportar soldados para algunas de sus misiones más importantes en donde ellos puedan recopilar información sin necesidad de maniobrar los vehículos o por el contrario vehículos autónomos no tripulados los cuales puedan recopilar información.
A partir de este programa surge la idea de esta tesis de investigación, la cual está dedicada a demostrar una prueba de concepto para la tecnología de estabilización giroscópica y validar su capacidad para equilibrar de forma autónoma en una bicicleta estática no tripulada. Esta tesis también analizará el diseño de un sistema giroscópico capaz de inducir y mantener temporalmente un movimiento de tipo "caballito" en una bicicleta. Desarrollan la teoría detrás de cómo funciona la tecnología de giroscopio de control de momento y cómo se puede estabilizar una bicicleta utilizando un sistema configurado CMG de cardán de un solo eje accionado, Se realiza el diseño y el control teórico de un sistema CMG capaz de inducir maniobras avanzadas en una bicicleta. Se presentarán los cálculos y la metodología utilizada para diseñar el hardware y los componentes de la plataforma de la bicicleta.[4]
SELF-STABILIZATION OF A RIDERLESS BICYCLE WITH A CONTROL MOMENT GYROSCOPE VIA MODEL-BASED ACTIVE DISTURBANCE REJECTION CONTROL
 
En este artículo publicado en el 2017 de la revista IEEE se analiza el problema de la auto estabilización a velocidad cero de una bicicleta sin tripulante, con un control de momento giroscópico (CMG). Ya que las bicicletas son sistemas inciertos altamente no lineales afectados por factores de perturbaciones externas, por ello implementan controladores robustos los cuales proporcionan adecuado auto equilibrio y rechazo a las perturbaciones. En este artículo proponen un modelo de rechazo activo de perturbaciones de dos lazos de enfoque de control (ADR), compuesto principalmente por dos observadores estatales y dos leyes estatales de control de retroalimentación con activos e inyección de rechazo de alteraciones. El esquema propuesto proporciona estimación y rechazo en línea de perturbaciones que afecten al bucle de control internos y externos. Los resultados muestran que el control ADR propuesto el enfoque es robusto y eficaz para estabilizar la bicicleta, pero también para rechazar perturbaciones externas.[5]

GYROSCOPIC STABILIZATION OF AN UNMANNED BICYCLE 

En junio de 2014 en la American Control Conferencia (ACC), Oregon, USA, se presenta un artículo en el cual se analiza cómo se puede estabilizar un vehículo de dos ruedas proponen un control de momento giroscopio (CMG) y una estabilización dinámica. Expresan que la estabilización dinámica utiliza técnicas de dirección táctica para activar una inclinación en el vehículo en la dirección prevista para el equilibrio, mientras que la estabilización CMG emplea el par de precesión reactiva de un volante de alta velocidad alrededor de un eje que actuará para equilibrar el vehículo. Este artículo propone un diseño de controlador de modo deslizante (SMC) de primer orden para controlar el CMG y estabilizar una bicicleta a velocidad de avance cero. Este estudio también compara el método SMC con un controlador PID para validar las ventajas del controlador SMC para la dinámica de un sistema no lineal de estabilización estática. Para corroborar esto mencionado se realizaron dos experimentos, uno con un sistema de péndulo invertido con un grado de libertad y otro con un sistema de péndulo invertido con tres grados de libertad, como resultados obtenidos en se menciona que de los dos controladores PID y SMC, resulta el SMC como ventajoso para la estabilización al ofrecer un sobre impulso reducido y tiempos de ascenso y asentamiento más cortos. Las pruebas validan que CMG se puede utilizar la estabilización de un volante cardán de eje único para controlar y estabilizar activamente cuerpos inherentemente inestables (por ejemplo, péndulos invertidos, bicicletas, motocicletas, etc.). El estudio valida la viabilidad y las sólidas capacidades de CMG. estabilización para estos sistemas. [6]

GYROSCOPIC STABILIZATION OF A KID-SIZE BICYCLE 

Para este documento se logra el auto equilibrio de una pequeña bicicleta en la cual esta bicicleta está equipada con sensores para detectar el ángulo de balanceo de la bicicleta y actuadores para devolverlo a la posición de equilibrio siempre que se desvíe de él. En este documento el sistema se analiza muy similar a un péndulo invertido con más de dos grados de libertad. En este informe, se presentamos, como método de solución a la no lineal inestable del sistema, un controlador derivativo proporcional (PD) y se centran en uno de los mecanismos que implican el uso de un (CMG) como actuador para equilibrar el sistema, Los resultados experimentales muestran robustez y eficiencia del controlador (PD), a diferencia de un controlador (PID) que disminuiría drásticamente el margen de fase y el sistema se volvería inestable y no podría equilibrar la bicicleta. [7]

A GYROSCOPE-BASED INVERTED PENDULUM WITH APPLICATION TO POSTURE STABILIZATION OF BICYCLE VEHICLE 

Este artículo presenta un sistema de péndulo invertido, cuyo dispositivo estabilizador de núcleo está diseñado en base al efecto de precesión giroscópica. El sistema obtiene el equilibrio requerido mediante el control de la aceleración y desaceleración de la rueda de inercia. Presenta una respuesta rápida y alta eficiencia en el control. El efecto de precesión giroscópica del rotor de alta velocidad proporciona efectivamente un gran par para realizar el equilibrio estable del sistema de péndulo invertido. En este artículo se presentan los experimentos de equilibrio de perturbación y no perturbación del prototipo físico y la aplicación del dispositivo estabilizador para la estabilización de la postura de un vehículo de bicicleta. Los resultados mostraron que el dispositivo estabilizador respondió rápidamente y logró un equilibrio estable del sistema de péndulo invertido de manera eficiente. Además, la consecuencia de la aplicación validó que el dispositivo estabilizador posee una fuerte capacidad anti interferente y una buena aplicabilidad.[8]
	Marco teórico

LA BICICLETA
 
Estudios históricos relatan la importancia científica y el impacto social que ha tenido este medio de transporte. La primera invención de la bicicleta, apodada “Draisiana”, fue en 1817 por el investigador alemán Baron Karl von Drais, inspirado por la idea “deslizarse sin Introducción nieve” y de buscar una solución más sencilla para transportarse, sin necesidad de vehículos pesados de cuatro ruedas potenciados por caballos, viento, o vapor. El 12 de Enero de 1818, Von Drais recibió su primera patente en el estado de Baden por tal invención y solución a la movilidad de las personas en ese entonces.[9]
 
Fig 1. Primera bicicleta (Draisiana)[10]

Esta primera invención, encaminó a muchos personajes históricos reconocidos por sus investigaciones para que comenzaran a innovar sobre este mecanismo, buscando comodidad, eficiencia y seguridad para su conductor. Se pueden destacar algunos diseños de impacto al público en su historia, tales como, la primera bicicleta de pedal creada en 1840 por el escocés Kirkpatrick Macmillan. También, la creación de Pierre Michaux en 1861 llamada “Velocípedo”, que fue una de las más populares bicicletas de la historia con pedales en la rueda frontal, cuya localización ocasionaba que las piernas del conductor se atascaran en la rueda cuando se cruzaba a altas velocidades. [11]

 
Fig.2 : Bicicleta Penny Farthing [11].


Dinámica de la Bicicleta

La dinámica de montar y equilibrar una bicicleta implica un complejo proceso de control físico y neuromecánico en el que el ciclista mantiene activo el equilibrio del sistema bicicleta-ciclista. Aunque una bicicleta puede mostrar cierta autoestabilidad cuando está en movimiento debido a sus características de diseño, la estabilidad real con un ciclista montado es más difícil de describir matemáticamente, ya que depende de las acciones de control realizadas por el propio ciclista (Cain, 2016). Un aspecto fundamental de este control es la posición del centro de masa del sistema, que debe permanecer sobre la base de apoyo formada por las ruedas para evitar la caída; esto se consigue mediante ajustes continuos en la dirección y en la postura del cuerpo (Cain, 2016). En este contexto, el giro del manillar tiene un papel especialmente crítico, ya que permite reposicionar la bicicleta lateralmente para alinear la base de apoyo bajo el centro de masa cuando se presenta un desequilibrio (Cain, 2016).
Además de la dirección, los ciclistas también emplean movimientos corporales, como inclinarse hacia un lado u otro, para modificar la posición de su centro de masa y ayudar a mantener el equilibrio, aunque estos tienen un efecto menor en comparación con el giro del manillar (Cain, 2016). Estudios experimentales comparando ciclistas expertos y principiantes han demostrado diferencias claras: mientras que ambos grupos pueden mantener el equilibrio a bajas velocidades, los ciclistas expertos emplean movimientos más pequeños y coordinados tanto en la dirección como en el cuerpo, lo que les permite estabilizar la bicicleta con mayor eficiencia a velocidades mayores (Cain, 2016). Estos resultados sugieren que la habilidad y la práctica influyen en las estrategias de control utilizadas para mantener la estabilidad dinámicamente.




MOVIMIENTO GIROSCÓPICO

El giróscopo o giroscopio es un dispositivo mecánico formado esencialmente por un cuerpo con simetría de rotación que gira alrededor de su eje de simetría y cuyo eje de giro no es fijo, sino que puede cambiar de orientación en el espacio. Cuando se somete el giroscopio a un momento de fuerza que tiende a cambiar la orientación del eje de rotación su comportamiento es aparentemente paradójico ya que el eje de rotación, en lugar de cambiar de dirección como lo haría un cuerpo que no girase, cambia de orientación en una dirección perpendicular a la dirección "intuitiva". Este principio se ha utilizado en diversas aplicaciones, particularmente en relación con el control y guía de aeroplanos, sistema de navegación avanzado, proyectiles, etc. 

Los giróscopos son objetos muy interesantes debido a que parecen desafiar la gravedad; Además, en ellos actúan diversos fenómenos físicos a causa de que el eje de rotación cambia de dirección en todo momento. [12], [13]. Un ejemplo es como se muestra en la Fig. 3 de un giróscopo:[AR4.1]

 
Fig.3 : Ejemplo de un volante con eje horizontal[12]


En este ejemplo el volante se sostiene con un eje horizontal el cual queda libre cuando el volante no está girando, el extremo libre del eje cae debido a la gravedad. Si la volante gira, se produce un movimiento circular uniforme del eje en un plano horizontal, combinado con la rotación del volante alrededor del eje. Este movimiento del eje, no intuitivo, se denomina precesión.


 
La precesión o movimiento de precesión es el movimiento asociado con el cambio de dirección en el espacio, que experimenta el eje instantáneo de rotación de un cuerpo. Un ejemplo de precesión lo tenemos en el movimiento que realiza un trompo en rotación. Cuando su eje de rotación no es vertical, el trompo posee un movimiento de «cabeceo» similar al de precesión.


El efecto giroscópico es uno de los fenómenos más fascinantes de la física rotacional y es el principio que permite que tu proyecto (como un péndulo o un vehículo) mantenga el equilibrio.
Según textos clásicos de física universitaria como Sears-Zemansky o Serway, este efecto se basa en la conservación del momento angular. Aquí tienes la explicación estructurada para tu marco teórico:

1. Momento Angular (\mathbit{L})
Cuando un objeto (como el volante de inercia en tu proyecto) gira rápidamente alrededor de su eje de simetría, posee una magnitud vectorial llamada momento angular. Su dirección se determina por la regla de la mano derecha: si envuelves el eje con tus dedos en la dirección del giro, tu pulgar apunta en la dirección de L.
	Ecuación: L=I\omega (donde es el momento de inercia y es la velocidad angular).
2. Rigidez en el Espacio
Un cuerpo en rotación tiende a mantener la dirección de su eje de giro a menos que se le aplique un torque externo. Cuanto más rápido gira el volante (mayor ), más "rígido" es el eje y más difícil es cambiar su orientación. Esto es lo que estabiliza tu sistema ante pequeñas perturbaciones.
3. Precesión (\mathbit{\Omega p})
Es el movimiento más característico del efecto giroscópico. Si intentas inclinar el eje de un objeto que gira (aplicando un torque  ), el eje no se moverá en la dirección en la que lo empujas, sino en una dirección perpendicular tanto al torque como al momento angular original.
	Explicación física: El torque aplicado produce un cambio en el momento angular (  ). Como el nuevo vector momento angular es la suma del original más el cambio, el eje "precesa" o describe un círculo.
	Ecuación de la velocidad de precesión: 

\Omega_p=\frac{\tau}{L}=\frac{mgr}{I\omega}




Estimación de Orientación mediante Filtros Complementarios

1. Estimación de la Orientación en Sistemas Inerciales
La estimación precisa del ángulo de inclinación u orientación es fundamental en el control de sistemas dinámicos, como el péndulo invertido. Para lograr esto, se emplean comúnmente sensores inerciales que incluyen acelerómetros y giroscopios. Sin embargo, cada uno de estos sensores presenta limitaciones inherentes que impiden su uso aislado de manera eficiente en sistemas de control de retroalimentación (Adams, s.f.).
2. El Acelerómetro y la Medición de Inclinación
El acelerómetro mide la aceleración debida a la gravedad para determinar la orientación con respecto al centro de la Tierra. En condiciones estáticas, el ángulo de inclinación se puede calcular mediante la relación entre los ejes de aceleración (ax,ay): 
			\theta=arctanayax
Ventajas y Limitaciones:
	Estabilidad a largo plazo: Dado que la gravedad es una referencia constante, el error de medición no se acumula, manteniendo una media de error de cero.
	Sensibilidad al ruido: El acelerómetro es extremadamente sensible al ruido mecánico (vibraciones de motores, por ejemplo), lo que genera señales "sucias" que son difíciles de procesar directamente en un controlador (Adams, s.f.).
3. El Giroscopio y la Velocidad Angular
El giroscopio mide la velocidad de rotación (grados por segundo). Para obtener el ángulo de inclinación, se debe integrar la medición en el tiempo: 

				\theta=\theta0+gzΔt
Ventajas y Limitaciones:
	Precisión a corto plazo: Ofrece mediciones muy fluidas y con muy bajo ruido en intervalos cortos de tiempo.
	Deriva (Drift): Al integrar las mediciones, cualquier pequeño error o sesgo en el sensor se acumula con el tiempo, lo que provoca que la estimación del ángulo se desvíe progresivamente del valor real, incluso si el sistema está en reposo (Adams, s.f.).
4. Filtro Complementario
El filtro complementario surge como una solución eficiente y de bajo costo computacional para mitigar las deficiencias de ambos sensores. Su función principal es combinar las señales mediante el uso de un filtro de paso bajo para el acelerómetro y un filtro de paso alto para el giroscopio.
Según Adams (s.f.), el algoritmo combina la estabilidad del acelerómetro a largo plazo con la precisión del giroscopio a corto plazo mediante un promedio ponderado: 

		\mathrm{Ángulo=W⋅Ánguloprev+ω⋅Δt+1-W⋅Ánguloaccel
			
Donde es un peso (típicamente cercano a 0.99) que permite que el sistema ignore el ruido de alta frecuencia del acelerómetro mientras corrige la deriva del giroscopio utilizando la referencia gravitacional.


PID
De acuerdo con National Instruments (2025), el algoritmo PID es el controlador más utilizado en la industria debido a su robustez y simplicidad. Su funcionamiento se basa en un mecanismo de retroalimentación que calcula continuamente el valor de un "error" como la diferencia entre una variable de proceso medida y un punto de consigna deseado. El controlador intenta minimizar este error ajustando las entradas de control del sistema a través de la suma de tres parámetros: el proporcional, que determina la reacción al error actual; el integral, que permite eliminar el error de estado estacionario acumulado; y el derivativo, que actúa como un amortiguador al predecir el comportamiento futuro del error basado en su tasa de cambio.
Asimismo, la implementación de este controlador requiere una sintonización precisa para equilibrar la velocidad de respuesta con la estabilidad del sistema. Un ajuste excesivo de la ganancia proporcional o integral puede provocar que el sistema se vuelva inestable y oscile, mientras que una acción derivativa muy alta puede hacer que el sistema sea excesivamente sensible al ruido de los sensores. Por ello, el uso de herramientas de simulación y métodos de ajuste es fundamental para garantizar que el controlador PID mantenga el sistema en su punto óptimo de operación, permitiendo que el proceso regrese a su estado deseado de forma rápida y eficiente tras una perturbación (National Instruments, 2025).

Para completar tu marco teórico, aquí tienes la expresión matemática estándar de un controlador PID y la explicación detallada de cada uno de sus componentes, basándose en la literatura técnica de National Instruments.
La Ecuación General del PID
En el dominio del tiempo, la señal de control se define mediante la siguiente ecuación:
				u\left(t\right)=K_pe\left(t\right)+K_i\int_{0}^{t}e\left(\tau\right)d\tau+K_d\frac{de\left(t\right)}{dt}

Análisis de los Componentes
La ecuación representa la suma de tres formas de procesar el error (), que es la diferencia entre el valor deseado y el valor medido por tus sensores:
1. Término Proporcional (\mathbit{Kp} .et)
Es el componente principal del control. La salida es simplemente el error multiplicado por una ganancia ().
	Función: Proporciona una respuesta inmediata. Si el error es grande, la corrección es fuerte.
	Limitación: Si se usa solo, el sistema suele detenerse antes de llegar al objetivo (error de estado estacionario) porque, a medida que el error se hace pequeño, la fuerza de corrección también desaparece. 
2. Término Integral (\mathbit{Ki}\ \int\mathbit{e}\left(\mathbit{\tau}\right)\mathbit{d\tau})
Este término suma (integra) el error a lo largo del tiempo.
	Función: Su objetivo es eliminar el error residual que el término proporcional no pudo corregir. Incluso si el error es muy pequeño, al sumarse continuamente en el tiempo, la parte integral crecerá lo suficiente para empujar el sistema hasta el punto exacto deseado.
	Efecto: Logra que el error final sea cero.
3. Término Derivativo (\mathbit{Kd}detdt)
Este término calcula la velocidad a la que cambia el error (su derivada).
	Función: Actúa como un "freno". Si el error está disminuyendo muy rápido (lo que significa que el sistema se mueve velozmente hacia el objetivo), la derivada será negativa y restará fuerza a la ecuación.
	Efecto: Evita que el sistema se pase de largo (overshoot) y reduce las oscilaciones, permitiendo una estabilidad mucho más suave.

Microcontrolador (ESP32)
El ESP32 representa una evolución significativa respecto a arquitecturas anteriores (como el PSoC o Arduino), ofreciendo una infraestructura diseñada para el procesamiento paralelo y el control de precisión.
5.1. Arquitectura Xtensa® Dual-Core de 32 bits
A diferencia de los microcontroladores de un solo núcleo, el ESP32 integra dos núcleos de procesamiento (denominados Protocol CPU y App CPU) que pueden operar de forma independiente hasta a 240 MHz.
	Ventaja para el Control: En sistemas de equilibrio dinámico, el determinismo es crítico. Esta arquitectura permite dedicar un núcleo exclusivamente a la lectura de sensores (IMU) y el cálculo del filtro complementario, mientras el segundo núcleo se encarga de ejecutar el algoritmo PID y el movimiento de los actuadores. Esto evita que las tareas de comunicación o procesos del sistema operativo interrumpan el bucle de control, eliminando retardos (jitter) que podrían desestabilizar el sistema.
5.2. Resolución PWM y Periférico LEDC
Para que el movimiento de una rueda de reacción o un servo sea fluido, se requiere un control de pulsos extremadamente fino. El ESP32 cuenta con el periférico LEDC (LED Control), que destaca por su versatilidad en la generación de señales PWM.
	Precisión de 16 bits: Mientras que muchos microcontroladores estándar operan a 8 bits (256 pasos), el ESP32 permite configurar una resolución de hasta 16 bits (65,536 pasos).
	Impacto en el movimiento: Esta alta resolución permite que el volante de inercia o el servo realicen ajustes de posición casi imperceptibles. En lugar de moverse "a saltos" o pasos discretos, el movimiento es continuo y fluido, lo que es vital para mantener un equilibrio estable y evitar vibraciones mecánicas inducidas por una baja resolución de control.
5.3. Protocolo I2C (Inter-Integrated Circuit)
El protocolo I2C es el bus de comunicación serie utilizado para la transferencia de datos entre el ESP32 (Maestro) y el sensor MPU9250 (Esclavo).
	Funcionamiento: Utiliza solo dos líneas de señal: SDA (datos) y SCL (reloj). El ESP32 permite configurar la velocidad de este bus (típicamente a 400 kHz en modo Fast Mode), lo que garantiza que los datos de aceleración y velocidad angular lleguen al procesador con la latencia mínima necesaria para el cálculo en tiempo real del ángulo de inclinación.

5.4. Sensor de Movimiento Integral (MPU9250)
El MPU9250 es un dispositivo de seguimiento de movimiento de 9 ejes (9-DOF) que combina dos chips en un solo paquete: un acelerómetro y giroscopio de 3 ejes (MPU6500) y un magnetómetro de 3 ejes (AK8963). Esta integración lo convierte en un sistema MARG (Magnetic, Angular Rate, and Gravity), ideal para aplicaciones de navegación y equilibrio (InvenSense, 2016).
Componentes y Especificaciones Técnicas
	Giroscopio (3 ejes): Mide la velocidad angular con rangos programables de hasta ±2000 °/s. Es el encargado de detectar las rotaciones rápidas del volante de inercia o los cambios bruscos de inclinación.
	Acelerómetro (3 ejes): Mide la aceleración lineal (incluyendo la gravedad) con rangos de hasta ±16g. Su función principal en el proyecto es proporcionar una referencia absoluta hacia el centro de la Tierra (el vector de gravedad).
	Magnetómetro (3 ejes): A diferencia de sensores como el MPU6050, el MPU9250 incluye una brújula digital que mide el campo magnético terrestre. Esto permite corregir la deriva (drift) en el eje de guiñada (yaw), ofreciendo una orientación completa en el espacio 3D.
Ventajas para el Control de Estabilidad
	Resolución de 16 bits: Cada uno de los 9 ejes cuenta con convertidores analógico-digitales (ADC) de 16 bits dedicados. Esto permite capturar variaciones de movimiento extremadamente pequeñas, lo que se traduce en un error menor al alimentar el algoritmo PID.
	Digital Motion Processor™ (DMP): El chip incluye un procesador interno que puede realizar cálculos complejos de "fusión de sensores" de forma autónoma. Esto libera de carga de trabajo al procesador principal (ESP32), entregando directamente cuaterniones o ángulos de Euler ya filtrados.
	Frecuencia de Muestreo: Capaz de operar a altas frecuencias a través del bus I2C (hasta 400 kHz), permitiendo que el bucle de control del ESP32 reciba actualizaciones constantes de la posición del sistema en intervalos de milisegundos.






6.3. Marco Legal
El desarrollo del presente proyecto de investigación se encuentra enmarcado bajo normatividades nacionales e internacionales que regulan tanto el diseño mecánico como la implementación de sistemas electrónicos de control. A continuación, se detallan las normas que intervienen en la ejecución de la plataforma de estabilización:
Normativa de Control y Programación
	IEC 61131-3: Esta norma internacional es el estándar para la programación de controladores industriales. Se aplica a los controladores programables y sus periféricos asociados, tales como herramientas de programación, depuración e interfaces hombre-máquina (HMI). En este proyecto, fundamenta la estructuración lógica y funcional del sistema de control y el mando de la planta, asegurando que las características funcionales cumplan con los protocolos de la ingeniería de automatización.
Normativa de Representación Gráfica y Diseño Mecánico
	NTC 1580 (Dibujo Técnico. Escalas): Esta norma establece las escalas y su designación para uso en dibujos técnicos en cualquier rama de la ingeniería. Está regida por la norma ISO 5455, y fue fundamental para la elaboración de los planos de despiece y ensamble de la estructura de la bicicleta y el soporte del volante de inercia, garantizando la correcta interpretación de las dimensiones.
	NTC 1832 (Representación Convencional de Engranajes): Establece las reglas para la representación de la parte dentada de los engranajes, incluyendo tornillos sinfín y ruedas de cadena. Siendo equivalente a la ISO 2203, se aplicó en el diseño de los sistemas de transmisión por piñón y cadena utilizados en las primeras etapas de la planta física.
	NTC 2529 (Tolerancias Geométricas): Proporciona las guías para la verificación de tolerancias de forma, orientación, posición y desarrollo. Esta norma es crucial para asegurar que el mecanizado del volante de inercia y el eje de dirección tengan la precisión necesaria para evitar vibraciones excesivas que puedan desestabilizar el sistema de control.

6.3. Marco Legal (Continuación)
Normativa de Seguridad en Baterías y Sistemas de Potencia
	IEC 62133-2: Es el estándar internacional para celdas y baterías de litio recargables. En el proyecto, esta norma fundamenta los requisitos de seguridad para el pack de baterías lifepo4, minimizando riesgos de fuga térmica o cortocircuitos mediante el uso del sistema BMS (Battery Management System).
	NTC 2054 (Material de Transporte. Bicicletas): Define los requisitos de seguridad y métodos de ensayo para bicicletas. Se aplicó para asegurar que las modificaciones estructurales (como el soporte del volante) no comprometieran la integridad del marco ni la capacidad de frenado del vehículo original.
Estándares de Ingeniería de Control y Software
	IEEE Std 1016-2009: Proporciona los lineamientos para la documentación de diseño de software. Se utilizó como base para documentar la lógica del controlador PID y la integración de la librería del sensor MPU9250, garantizando que el código sea modular y escalable.



 
	Actividades realizadas durante la pasantía

Presentación del cómo se llevó a cabo la pasantía. Se deben presentar las actividades organizadas por fases en un diagrama de Gantt de acuerdo con la propuesta aprobada. Se debe incluir una descripción y análisis de cada una de las actividades que incluya los métodos, técnicas, estándares y normas empleadas.

7.1 Investigación de sistemas similares para la obtención de criterios de diseño	

A partir del estudio de los diferentes proyectos implementados, los cuales se mencionan en el presente documento en el Capítulo 6 (Marco de Referencia), se optó por tomar como base dos modelos de diseño mecánico diferentes. En esta sección se describe el procedimiento y el paso a paso seguido para la implementación de cada uno de estos diseños. La selección del diseño más adecuado se definió de manera progresiva, con base en las pruebas realizadas a lo largo del desarrollo del proyecto, permitiendo identificar aquel que ofrecía mejores condiciones de eficiencia y un comportamiento más estable del sistema.


7.1.1 Diseño Del Volante 
para este diseño en primera instancia se decido usar una bicicleta tipo carreras la cual tiene como dimensiones las mencionadas en la figura (), tomando en cuanta estas dimensiones, se realiza un análisis y se determina que como primera muestra de datos bajo el comportamiento de la planta se podría adecuar, un soporte vertical en el cual se podría adecuar un motor que en primera instancia se en cargo de mover  un volente de inercia con un peso aproximado de 2 kilogramos. Figrura ().



  




Para este modelo inicial se lograron identificar varias falencias con el modelo, el cual por el peso del volante y las dimensiones de la bicicleta, no contaba con el torque necesario, para realizar el control o la estabilidad deseada en la bicicleta.
Esta primera prueba de la planta fue indispensable ya que se lograron identificar grandes falencias en el modelo, una de las grandes falencias que se identifico que al ubicar el volante de inercia en esta posición, no ayudaba mucho a la estabilidad de la bicicleta ya que su centro de gravedad se veía afectado e interfería con la estabilidad, además que por su diseño el controlador debería ser mas robusto y capaz de controlar movimientos bruscos solo con la cambio de sentido de giro del motor y este  a su vez controlar con la inercia generada por la velocidad del volante.

7.2Análisis del modelo matemático del sistema y Diseño tridimensional (3D) del modelo de la planta

A partir de los resultados obtenidos en la primera planta, se optó por construir un segundo modelo el cual su diseño se caracterizó ubicar el volante en la parte superior de la bicicleta, este diseño a diferencia del anterior acoplaba el movimiento de giro del volante a través de un motor DC, el cual solo giraba en un solo sentido, figura 

cómo se observa en la figura el motor DC esta acoplado directamente al volante de inercia, este a través de su eje. La intención en esta segunda etapa fue verificar el cambio del comportamiento de la estabilidad de la bicicleta, ya que el volante fue remplazado con otro de mayor peso este cuenta con un peso estimado de 10 kilogramos, a diferencia del volante anterior este cuenta con un diseño totalmente diferente  y su material es de hierro. 
Este nuevo diseño esta pensado en que el sistema Pueda aprovechar al máximo el momento de inercia, cuyo diseño se compone de un volante tipo anillo, el cual cuenta con un anillo exterior mayor al al resto del volante que en su parte interior tiene un anillo de menor grosor en comparación al exterior. Figura 




Este diseño permite Maximizar el Momento de Inercia 

	Mayor Momento Angular  Momento Angular es la "cantidad de rotación" almacenada y el factor fundamental para la estabilidad. mayor resistencia del volante a ser inclinado o perturbado.
	Mayor Torque Giroscópico de Estabilización 	
Esto significa  que puede contrarrestar fuerzas externas (como un viento lateral o una inclinación rápida) con mayor eficacia, logrando una estabilización más robusta. 
	 Mayor Almacenamiento de Energía Cinética 
Esto le da al sistema una mayor reserva de energía para mantener la velocidad durante los picos de demanda de torque de corrección y para absorber las variaciones de velocidad.
Con este nuevo diseño del volante de inercia es indispensable disponer y calcular el momento de inercia generado por este mismo, a continuación se hace mención de cómo se realizó el cálculo de este mismo, en la figuras (), se hace en detalle el cálculo de estos mismos. 















Al realizar los cálculos corroboramos que el nuevo volante de inercia al tener un giro aproximado de 3000 RPM podría suministrar un momento de inercia de 25.36 kgm2/s, este parámetro es super indispensable, ya se depende de el, directamente para aplicar  el giro de la estructura de donde esta aplicado para aplicar la precesión giroscópica y realizar el control de esta directamente.
este dato será calculado más adelante y será el que directamente nos brinde si nuestro volante tiene la capacidad para estabilizar el sistema.

7.3 Mecanizado y ensamble de la planta física
	

En esta segunda etapa se realizó un diseño mecánico el cual permite acoplar directamente la bicicleta a la estructura que asegura el volante y motor. En esta etapa la estructura inicialmente se instala en la parte superior de la bicicleta ver figura(), adicionalmente la estructura acopla directamente el motor de tracción del volante.
Por otra parte esta estructura es la que directamente se encargó de realizar el movimiento de todo el conjunto, esto se logró a través de un eje de dirección vertical con rodamientos, tipo chumacera, este  instalado directamente sobre el marco de la bicicleta, este fue instalado manteniendo las mismas dimensiones estructurales de la bicicleta y tratando de ubicarlo lo mas centrado posible con respecto a la bicicleta, esto nos facilita  la condiciones de realizar un contro ya que entre mas centrado sea el centro de masa de la bicicleta no se ve tan afectado y por consiguiente mejora la estabilidad de ella misma. 














Para esta etapa tambien fue incluido un motor reductor, el cual cumple como función principal controlar la dirección de la estructura motor- volante , este cambia el sentido de girto de la estructura a través de un piñon ubicado en el eje del motor de control y otro en el eje de dirección instalado, estos dos se comincan entre si por medio de una cadena, que transmite el movimiento del motor reductor al eje de dirección ver Figura ().



En esta etapa del proyecto se realizan verías modificaciones significativas ya que el mecanismo implementado para la dirección, carecía de las condiciones necesarias para poder ejercer el movimiento a todo el conjunto, a partir de ello se realizó el cambo del mecanismo por un mecanismo tipo polea en el cual se realizó el cambio de los piñones y se remplazó la cadena por una correa de arrastre. 	

7.3.1 Control sistema de dirección	

A partir de esta, comenzaron los primeros pasos para controlar la dirección de la estructura motor- volante, para ello se realizó un control de dirección del motor por medio de un controlador PSoC y un driver BTS7960, en esta prueba el controlador de potencia en conjunto con micro controlador PSoC, tuvieron un comportamiento bastante aceptable de la misma manera que el conjunto piñón polea a través de la correa.














para esta etapa inicialmente se realizaron pruebas para verificar el funcionamiento del control de giro cuando el volante estaba en movimiento, esta se realizó con las siguientes condiciones:

	Control de giro mediante PWM con el microcontrolador PSOC
	Motor de volante con velocidad constante
	Alimentación directa al sistema con una fuente de alimentación de 12 a 24 voltios variables 
Para esta prueba se obtuvieron los siguientes resultados:
Se evidenció una carencia de agarre en el sistema piñón-correa. El peso y la fuerza ejercida por la estructura resultaron ser superiores a la capacidad de arrastre de la polea y la correa acopladas al motor. Al realizar cambios bruscos en la dirección del motor de control, la correa patinaba, perdía sujeción y no generaba la fuerza de arrastre necesaria para mover la estructura del anclaje del motor.
Estos resultados nos obligaron al realizar un cambio en el diseño del sistema de rotación del conjunto de motor polea. Además de implementar un nuevo sistema que permita facilitar  el cambio de sentido de la estructura.











En este diseño se realizaron cambios tanto en la estructura  de soporte motor y como la versión de la bicicleta, para esta versión de la bicicleta se redujo el tamaño  para lograr establecer la planta mas estable, su diseño  acopla un estructura de base motor más reducida y más liviana, logrando asi un menor esfuerzo en el motor que cambia de dirección en la estructura motor.	
 
Por otra parte el diseño redujo perdidas de energía en la transmisión de potencia, ya que en esta etapa se remplazó el sistema de polea y el motor reductor por un servo motor que se acopla directamente al eje vertical, este permitió mejorar la eficiencia de la planta al mover la estructura. 
A continuación  se logró poner a prueba el cambio de giro del motor de una manera más eficiente y con ello continuar con la siguiente etapa del proyecto la cual constaba en sensar la posición exacta de la bicicleta.


7.4 Implementación del sistema de comunicación

7.4.1 Sensado de la posición de la bicicleta.	

Para verificar la posición de la bicleta se pusieron aprueba dos sensores tipo acelerómetro 

	MMA7361


Inicialmente, se incorporó a la planta el sensor MMA7361, con el cual se realizaron las primeras mediciones de la inclinación en el eje Z. Estas mediciones permitieron determinar la posición inicial del sistema y, a partir de dicha referencia, implementar el sistema de control encargado de mantener la estabilidad de la planta, estos datos a su vez fueron  adquiridos e interpretados mediante el microcontrolador PSoC 5 LP. No obstante gracias a la incorporación de estos dos elementos, fue posible llevar a cabo las primeras pruebas del control de movimiento de la estructura volante–motor.


Como se mencionaba anteriormente en el documento la señal generada por el MMA7361 es una señal  análoga, que fue procesada a través del módulo de conversión analógica-digital (ADC) del microcontrolador, y  posterior interpretada y tratada por este mismo  para obtener la información del Angulo de la plant.
A partir de la información de Angulo se realizaron las pruebas iniciales donde se determinó que el sensor analógico presentaba una alta susceptibilidad al ruido, ya que se filtraban múltiples señales parásitas que eran interpretadas erróneamente por el sistema como variaciones reales de inclinación. Este comportamiento afectaba directamente la eficiencia del control, generando respuestas imprecisas e inestabilidad en la planta.
Como primera estrategia para mitigar este problema, se implementaron filtros digitales[JH5.1] con el objetivo de atenuar las señales parásitas y permitir que el sistema trabajara únicamente con la señal útil proveniente del sensor. Esta etapa de filtrado mejoró considerablemente la eficiencia del microcontrolador en la lectura de los datos. Sin embargo, a pesar de esta mejora, el sistema continuó presentando un comportamiento inestable durante su operación.
Tras realizar un análisis más detallado del sistema y llevar a cabo nuevas pruebas experimentales, se concluyó que la principal fuente del problema era el uso de un sensor analógico. Por esta razón, se decidió reemplazarlo por un sensor digital, el cual transmite la información mediante comunicación I²C directamente al microcontrolador. Esta modificación permitió reducir significativamente la influencia del ruido y mejorar la confiabilidad de las mediciones, contribuyendo a un desempeño más estable del sistema de control.




	MPU9250


Para esta etapa del proyecto se implementó el sensor digital MPU9250, el cual integra un acelerómetro y un giroscopio en los tres eje (x,y,z), permitiendo la medición de aceleraciones lineales y velocidades angulares en los tres ejes,  A través de la información proporcionada por estos sensores, es posible estimar la orientación y la inclinación de la bicicleta.



Como se mencionaba anteriormente El MPU9250 y el microcontrolador, realiza e intercambian información mediante el protocolo I²C, lo cual permite una transmisión digital de los datos, reduciendo significativamente la susceptibilidad al ruido eléctrico en comparación con el sensor MMA7361. Al realizar la lectura de datos de manera digital mejora considerable en la calidad y estabilidad de las mediciones utilizadas por el controlador.

A continuación en la figuras (----), se realiza una comparación de la adquisición de la señal de Angulo con los dos sensores, en la cual se puede apreciar la diferencia entre la calidad de las dos señales, además de observar el comportamiento de la señal antes de aplicar el filtro y posteriormente a aplicar el filtro.















A partir del análisis anterior y como revelan las gráficas de la señal de Angulo, la calidad de la señal emitida por el sensor digital es mucho más limpia y presenta una mejor condición para  que el microcontrolador, pueda interpretarla de una mejor manera. Sin embargo la implementación de este sensor, se logró identificar que gran parte del ruido presente en las mediciones no provenía del sistema de adquisición ni de la comunicación digital, sino de las vibraciones mecánicas generadas por el volante de inercia durante su operación. Dichas vibraciones afectaban principalmente las lecturas del acelerómetro, introduciendo componentes de alta frecuencia que interferían con la estimación precisa de la inclinación del sistema.
Con el fin de mitigar estos efectos, se implementó nuevamente un filtro digital orientado a atenuar las señales parásitas generadas por las vibraciones mecánicas de la planta. Sin embargo, se observó que las vibraciones constantes producidas durante el movimiento del volante de inercia generaban un margen de error significativo en las mediciones, lo que continuaba afectando la estimación del ángulo proporcionada por el sensor. Debido a esto, se determinó la necesidad de realizar una modificación mecánica en la planta, que a su vez se orienta a minimizar al máximo las vibraciones transmitidas por el volante de inercia hacia la estructura y, en consecuencia, hacia el sistema de sensado.

7.5 Implementación del sistema de control	

Con base en los resultados obtenidos en el apartado 7.4, y ante la necesidad de implementar un sistema de control eficiente, se determinó en una primera instancia realizar diversas modificaciones en la planta física. Esto se debe a que el desempeño del sistema de control depende en gran medida de que la planta se encuentre en condiciones óptimas de operación. En consecuencia, a continuación, se describen las modificaciones necesarias implementadas, con el objetivo de garantizar un funcionamiento adecuado y estable del sistema.	

7.5.1 Modificaciones estructurales	

Tal como se mencionó anteriormente en el apartado 7.3, se realizaron diversas modificaciones en el diseño mecánico de la planta. No obstante, durante la etapa de pruebas experimentales se identificó que, desde el punto de vista estructural, la planta presentaba una transmisión significativa de vibraciones mecánicas, las cuales afectaban directamente el desempeño del sistema de sensado y contribuían a un comportamiento inestable del sistema de control.
Con el objetivo de abordar esta problemática, se llevó a cabo un análisis estructural de carácter experimental y de observación, basado en la inspección visual del sistema durante su operación, así como en la evaluación del comportamiento dinámico de la planta ante diferentes condiciones de funcionamiento. Este análisis permitió identificar los componentes mecánicos y los puntos críticos de la estructura que presentaban mayor susceptibilidad a vibraciones y deformaciones, afectando la estabilidad general del sistema.
A partir del análisis se revelaron y  se determinó que los principales puntos de inestabilidad se encontraban en las zonas de sujeción y los puntos de acople de la estructura de dirección y la estructura de motor - volante con el marco de la bicicleta . Como se hace mención en el apartado 1,3 dicho acople se realiza mediante un rodamiento tipo chumacera, en cuyo eje de rotación se fijaban tanto la estructura motor de dirección, como la estructura motor - volante. Sin embargo, se evidenció que estos componentes no contaban con una base de sujeción suficientemente robusta, lo que facilitaba la transmisión y amplificación de las vibraciones generadas durante el giro del volante.
Debido a esto, las vibraciones producidas por el movimiento del volante de inercia se propagaban fácilmente hacia el resto de la estructura, afectando tanto la estabilidad mecánica de la planta como la calidad de las mediciones obtenidas por el sistema de sensado.
A partir de la identificación de estos puntos críticos, se procedió a realizar modificaciones en la estructura mecánica utilizando el software de diseño SolidWorks. En esta etapa se plantearon nuevos planos estructurales y se realizaron ajustes en el diseño del soporte del conjunto motor–volante, con el objetivo de mejorar la rigidez estructural y aumentar el número de puntos de sujeción.



En la Figura --- se presentan los resultados del nuevo diseño estructural, en el cual se observa que el soporte del conjunto motor–volante se vuelve más compacto y ligero. Este diseño incorpora tres soportes estructurales que se anclan entre sí mediante múltiples puntos de fijación, conformando una estructura más robusta y rígida. Adicionalmente, se mejoro un eje solidario del volante de inercia, el cual se encuentra acoplado mediante un sistema de cuña con pinado y tornillo tipo prisionero, evitando el desplazamiento del eje con respecto al volante durante la operación.
Por otra parte, la nueva estructura fue diseñada considerando la facilidad de ensamble y desensamble, lo que permite un mantenimiento más eficiente tanto de los rodamientos del eje como del motor. En conjunto, estas modificaciones estructurales permiten reducir de manera significativa las vibraciones transmitidas a la planta, contribuyendo a un comportamiento más estable del sistema y a una mejora en la calidad de las señales adquiridas por los sensores.

7.5.2 Adquisición de datos t tratamiento de la señal 	

Como se mencionó anteriormente, en una etapa inicial la adquisición de la señal de inclinación se realizaba mediante el sensor analógico MMA7361. Sin embargo, debido a limitaciones en la eficiencia y confiabilidad de la adquisición de la señal, se decidió migrar hacia el uso del sensor digital MPU9250. Este sensor proporciona la información en formato digital, lo que permitió mejorar la calidad de los datos adquiridos y facilitar su procesamiento por parte del microcontrolador PSoC 5 LP.
Dado que el MPU9250 transmite la información mediante el protocolo de comunicación I²C, fue necesario incorporar en la programación del microcontrolador el correspondiente bloque de comunicación I²C, Figura ---  el cual, en sincronía con el sensor, permitía la recepción de los datos asociados al ángulo de inclinación de la bicicleta. En esta etapa se garantizó una correcta adquisición e interpretación de la señal digital proveniente del sistema de sensado.



Adicionalmente, con el propósito de visualizar y analizar los datos adquiridos, se implementó un bloque de comunicación RS-232, mediante el cual se enviaban los valores de inclinación al computador. Esto permitió graficar y verificar el comportamiento de la señal del sensor, asegurando que los datos recibidos correspondieran adecuadamente a las variaciones reales de la inclinación de la bicicleta.


Una vez verificada la correcta adquisición e interpretación de la señal del sensor, los valores fueron utilizados para el cálculo de las señales de salida destinadas al actuador del sistema, el cual corresponde al motor de dirección del conjunto volante–motor. Las señales de control generadas fueron entregadas a través de uno de los bloques de salida PWM del microcontrolador, lo que permitió regular de manera adecuada la señal de control y, en consecuencia, obtener un manejo más preciso de la corriente aplicada al actuador.	



7.5.3 Sistema de dirección y actuador 

El primer actuador incorporado en la planta fue un motor reductor, el cual se acoplaba en su eje un piñón, que a su vez transmitía el movimiento por medio de una cadenilla hacia un segundo piñón acoplado a una estructura tipo chumacera. Esta estructura hacía parte del conjunto del sistema de dirección que soporta el mecanismo motor–volante. Figura xxx



A partir de la señal emitida por el microcontrolador, al accionar el motor reductor, se evidenció un comportamiento limitado y poco eficiente del sistema. En particular, el tiempo de respuesta ante la inversión del sentido de giro resultaba demasiado lento para los requerimientos del control, lo que afectaba negativamente la capacidad de estabilización de la planta. Como se menciona en el capítulo 1, [JH6.1]durante esta etapa el sistema de transmisión mediante cadenilla fue reemplazado por un sistema de polea–correa, en un intento por mejorar el desempeño mecánico del actuador.
Sin embargo, tanto el sistema de transmisión por cadenilla como el sistema de polea–correa presentaron dificultades similares, ya que en ambos casos se perdía la correcta sujeción entre la transmisión mecánica y el eje giratorio, lo que ocasionaba deslizamientos y reducía la precisión del control.
En contraste a esta limitaciones evidenciadas, se determinó la necesidad de reemplazar el motor reductor por un servomotor, el cual ofrecía una mejor respuesta dinámica, mayor precisión en el control de posición y una integración más adecuada con el sistema de control implementado.
Para lograr implementar el servo motor, fue necesario diseñar un soporte para el servomotor, en forma de L con un ajuste de distancia con respecto al marco de la bicicleta, a su vez el soporte se asegura a la base del marco de la bicicleta. Además estar acoplado a un soporte en el cual se asegura el eje del servomotor al mismo tiempo alinea el centro del eje de la chumacera y el servomotor. A continuación, en la figura __ se ilustra el diseño y casa uno de los componentes los cuales hacen parte del sistema de dirección y acople del servomotor.  









Inicialmente se implementó un servomotor con un ángulo de giro de 270° y una capacidad de carga aproximada de 10 kg, lo cual representaba una ventaja significativa debido al amplio rango de movimiento disponible y a que el actuador contaba con la fuerza suficiente para accionar el sistema de dirección de la planta. Estas características permitieron realizar las primeras pruebas de control del conjunto motor–volante de manera satisfactoria.
No obstante, durante las pruebas realizadas con la señal de salida generada por el microcontrolador, se evidenció un desgaste prematuro en el sistema interno de engranajes del servomotor. Este fenómeno se presentó debido a los cambios bruscos en el sentido de giro, los cuales generaban esfuerzos mecánicos superiores a la capacidad de diseño del servomotor, tal como se ilustra en la Figura X.




Como consecuencia, se decidió aumentar la capacidad de carga del actuador, reemplazando el servomotor inicial por un servomotor con una capacidad de carga de 20 kg, el cual ofrecía una mayor resistencia mecánica y un mejor desempeño ante las exigencias del control.	

En comparación con el motor reductor utilizado en la etapa inicial del proyecto, el servomotor presentó ventajas significativas en términos de tiempo de respuesta, precisión en el control del ángulo y facilidad de integración con el sistema de control basado en señales PWM. Mientras que el motor reductor mostraba una respuesta lenta ante la inversión del sentido de giro y dificultades en la transmisión mecánica, el servomotor permitió un control más directo y preciso del sistema de dirección. Sin embargo, estas ventajas también implicaron mayores exigencias mecánicas sobre el actuador, lo que hizo necesario seleccionar un servomotor con mayor capacidad de carga y robustez estructural.
Finalmente, el diseño de la estructura del sistema de dirección se ilustra en la figura ----

Este nuevo diseño del sistema de dirección fue acoplado directamente a la planta, de tal manera que su implementación no afectara de forma significativa el confort ni la maniobrabilidad de la bicicleta. Una vez finalizado el proceso de ensamblaje y adaptación de las nuevas modificaciones estructurales, se procedió a realizar las pruebas de funcionamiento de la planta junto con el sistema de control.
Al iniciar las pruebas del sistema de control con las nuevas modificaciones implementadas en el actuador y en los soportes mecánicos, se evidenció una mejora significativa en la estabilidad de la planta, ya que su comportamiento fue más estable y permitió cumplir de manera adecuada con los objetivos de diseño establecidos para el sistema.	

Integración de los componentes electrónicos en la planta	

Una vez alcanzados los objetivos de diseño y confort de la planta, se procedió al montaje de todos los componentes electrónicos del sistema. Entre estos se encuentra el sensor de ángulo de dirección, el cual fue ubicado en la parte trasera de la bicicleta, tomando como punto de referencia la posición de la silla del operador, con el fin de garantizar una medición adecuada de la inclinación y orientación del sistema.
Adicionalmente, se diseñó una platina de soporte destinada a alojar los principales componentes electrónicos de la planta, tales como el microcontrolador, los convertidores DC-DC y otros elementos de acondicionamiento de señal. En una etapa inicial, la planta fue probada utilizando una fuente de alimentación externa, la cual proporcionaba un voltaje de salida de 24 V, correspondiente al voltaje máximo de operación del motor del volante de inercia.
Una vez integrados todos los componentes electrónicos en la planta, se realizaron las adecuaciones necesarias para el diseño e implementación del controlador, considerando además la posibilidad de incorporar mejoras y ampliaciones en una segunda etapa del proyecto.



Diseño del sistema de baterías de alimentación	

Como se mencionó anteriormente, durante las primeras pruebas todos los circuitos electrónicos eran alimentados mediante una fuente externa, lo cual generaba la presencia de ruido eléctrico y requería que el sistema permaneciera conectado de manera permanente a la red eléctrica. Debido a estas limitaciones, se procedió al diseño e implementación de un sistema de alimentación basado en baterías.
El sistema de baterías fue diseñado utilizando celdas de fosfato de hierro-litio (LiFePO₄), cada una con un voltaje nominal aproximado de 3,2 V. Para este diseño, se conectaron seis celdas en serie, obteniendo un voltaje total cercano a 20 V, valor suficiente para alimentar el sistema electrónico y proporcionar la energía necesaria al controlador para mantener la estabilidad de la planta.










Además, el conjunto de baterías incorpora un sistema de gestión de baterías (BMS), el cual permite supervisar y proteger cada celda de manera individual, garantizando un proceso de carga balanceada y segura, y prolongando la vida útil de las baterías sin comprometer su desempeño.













 

Implementación del control PID y verificación de la señal

La incorporación del sistema de baterías proporcionó un mejor desempeño general de la planta, ya que permitió eliminar el exceso de cableado y hacer el sistema más compacto y portátil. A pesar de que la planta cumplía con el objetivo de diseño, aún carecía de un control óptimo y robusto, lo que motivó la implementación de un sistema de control adicional a los objetivos inicialmente propuestos, esto como para dar un valor agregado al proyecto
.
En consecuencia, se iniciaron diferentes pruebas en el circuito de control, lo que condujo a la implementación de un controlador (PID), cuyo objetivo principal fue mejorar la estabilidad del sistema y ampliar el alcance funcional del proyecto.
A continuación, se describe el procedimiento utilizado para la sintonización de los parámetros P I D del controlador.

Verificación de la señal y control de corriente en la salida de control

Una vez obtenidos los valores de la señal del sensor de ángulo dentro del microcontrolador, se procedió a implementar el control PDI, con el cual se buscaba regular tanto la corriente aplicada al motor del sistema de dirección como la posición del motor del sistema de dirección.










La salida del controlador, generada en forma de una señal PWM, fue inyectada directamente a la entrada de control del servomotor. Por la parte para la alimentación
, se implementó un convertidor DC-DC de 5 A, el cual, en principio, resultaba adecuado para suministrar la corriente de trabajo requerida por el servomotor.

Dentro del control se tomó como referencia una posición de 140° del motor, definida como el punto medio del rango de operación del sistema de dirección. Este punto de referencia se estableció interpretando los valores de la salida de control en porcentajes de grados de giro del motor. Por ejemplo, cuando la salida del controlador era positiva, los grados de giro se incrementaban a partir de los 140°, y cuando la salida era negativa, los grados disminuían desde los 140° hacia atrás, manteniendo así los 140° como posición central del servomotor.
Con el control de posicionamiento del servo motor, básicamente, se buscaba que el controlador de mantuviera la planta con un ángulo de inclinación cercano a 0°, el cual fue definido como el set point del sistema.

Resultados iniciales y limitaciones identificadas	

Al obtener los primeros resultados con el controlador PID, se identificaron ciertas limitaciones en el microcontrolador, ya que en algunas ocasiones este respondía de manera lenta a la señal de control con respecto a la señal de referencia (set point). Además, se observó que el controlador generaba en varias ocasiones un bloqueo intermitente, posiblemente asociado a la corriente demandada al invertir el sentido de giro del servomotor.




7.7 Diseño de la placa electrónica (PCB)
7.8 Montaje y pruebas de la placa electrónica
7.9 Acople e integración del sistema completo




Resultados 

NALISIS DEL SISTEMA 
DISEÑO DE LA PARTE ELECTRONICA
PRUEBAS, RESULTADOS 
MODIFICACIONES 
DISEÑO NUEVA ESTRUTURA 
PRUEBAS ANALISIS 





	Resultados
Se deben documentar detalladamente los resultados obtenidos, producto de las actividades desarrolladas durante la pasantía. Incluir soportes como fotografías, diagramas de flujo y todas aquellas evidencias que el estudiante considere relevantes. 
1, Diseño mecánico planta 	
2. adaptación de los dispositivo de control 	a la planta	
3.construccion del controlador PID a la planta	
4.adapctacion y construcción de batería de alimentación a la planta.


El desarrollo del proyecto se ejecutó de manera secuencial mediante cuatro fases fundamentales, integrando la ingeniería mecánica con la electrónica de potencia y control.

Fase 1: Diseño y Construcción Mecánica de la Planta
Como resultado de la primera fase, se logró una planta mecánica eficiente mediante las siguientes intervenciones:
	Reducción de Inercia Estructural: Se seleccionó y adaptó un marco de bajo peso con el objetivo de minimizar la inercia total del sistema. Esto permite que el par de torsión generado por el efecto giroscópico del volante realice la corrección de verticalidad con un menor consumo energético y una respuesta más rápida.
	Centralización del Centro de Masa (CoM): Se modificó la geometría central del marco para alojar el volante de inercia en la parte inferior-central. Esta decisión de diseño permite bajar el centro de gravedad del conjunto, aumentando la estabilidad estática y facilitando el control dinámico durante las pruebas de equilibrio.
	Sistemas de Protección y Seguridad: Se implementaron ruedas auxiliares en el eje trasero. Estos elementos actúan como limitadores de inclinación (topes mecánicos), evitando daños estructurales en los componentes críticos o golpes en el volante de inercia ante posibles fallos en el lazo de control durante la etapa de pruebas.
	Acondicionamiento para Electrónica: Se retiró el sillín original para integrar una plataforma de soporte personalizada. Este espacio se optimizó para el anclaje seguro de la unidad de control, los sensores inerciales y el pack de baterías LiFePO4, garantizando que el cableado no interfiera con las partes móviles y que el sensor MPU9250 esté alineado con el eje de simetría del vehículo.

 

El diseño del volante de inercia se centró en optimizar la distribución de masa para maximizar el efecto giroscópico. Los resultados y detalles técnicos se describen a continuación:
	Optimización de la Distribución de Masa: Se diseñó un volante con geometría tipo anillo, concentrando la mayor parte de la masa en el perímetro exterior y minimizando el peso en el núcleo central. Técnicamente, esto se realizó para aumentar el Radio de Giro, lo que permite obtener un mayor Momento de Inercia () con el mismo peso total. Esto garantiza que cualquier cambio en la velocidad angular genere un torque de corrección más potente.
	Proceso de Fabricación y Ajuste Mecánico: Partiendo de un bloque sólido de acero, se utilizó un proceso de torneado de precisión para dar forma al disco. Se integró un agujero concéntrico y un sistema de pasador (pin) de seguridad para asegurar que el volante sea solidario al eje, evitando deslizamientos rotacionales por inercia.
	Soporte y Alineación Estructural: El eje del volante está soportado por dos piezas de acero mecanizadas a medida, las cuales alojan rodamientos de alta velocidad para reducir la fricción. Este conjunto garantiza que el eje se mantenga rígido y alineado, soportando las fuerzas centrífugas generadas a altas RPM.
	Acople y Centrado del Motor: El motor se integró directamente en una de las piezas de soporte, logrando una alineación coaxial perfecta con el eje del volante. Para la transmisión de potencia, se utilizó un ajuste a presión combinado con una ranura de chaveta (chavetero). Este diseño permite que el sistema sea separable para mantenimiento, pero garantiza que no haya deslizamiento mecánico cuando el motor realiza cambios bruscos de dirección o velocidad.
	Balanceo Estático y Dinámico: Durante el diseño y montaje de la estructura, se priorizó el equilibrio simétrico de las piezas de soporte. Esto asegura que el peso esté distribuido uniformemente en ambos lados del eje central de la bicicleta, evitando momentos de vuelco parásitos que complicarían la tarea del controlador PID.



Para permitir que el volante de inercia genere el par de torsión necesario para equilibrar la bicicleta, se diseñó un sistema de dirección vertical basado en el principio de precesión giroscópica. Los detalles de su implementación son los siguientes:
	Implementación del Eje de Giro Vertical: Se integró un eje vertical mediante la soldadura de una caja de pedalier estándar al marco de la bicicleta en posición vertical. Esta solución técnica aprovecha los rodamientos internos de alta resistencia del centro de pedales, garantizando un movimiento de rotación suave y con mínima fricción para todo el conjunto motor-volante.
	Optimización del Centro de Masa (CoM): El conjunto del volante de inercia se instaló en el extremo inferior de este eje vertical. Esta configuración desplaza el centro de masa del sistema hacia la parte baja de la bicicleta, lo cual reduce el momento de vuelco y otorga al sistema de control un mayor margen de maniobra para corregir desviaciones de la verticalidad.
	Integración del Actuador de Alto Torque: En el extremo superior del eje vertical se diseñó un acople mecánico de precisión para conectar un servomotor digital de 80 kg-cm (modelo DS5180). Este servomotor actúa como el elemento final de control, encargándose de variar el ángulo de inclinación del volante de inercia de manera rápida y precisa.
	Capacidad de Respuesta y Torque: La elección del actuador DS5180, con engranajes metálicos y un torque de bloqueo de hasta 80 kg-cm, garantiza que el sistema pueda vencer la resistencia inercial del volante durante las maniobras de corrección. La velocidad de respuesta del servo (hasta 0.15 s/60°) es crítica para que el controlador PID realice ajustes en tiempo real ante perturbaciones externas, manteniendo así el equilibrio dinámico.
 

Fase 2: Instrumentación y Procesamiento de Señales (Cerebralización)
Una vez consolidada la estructura mecánica, se procedió a la implementación del sistema de percepción. Esta etapa se centró en la obtención de una lectura de inclinación fiable y en tiempo real para dotar de "inteligencia" a la planta.
Implementación de la Unidad de Medición Inercial (IMU)
Para la captura del ángulo de inclinación se utilizó la IMU MPU9250, un dispositivo que integra acelerómetro, magnetómetro y giroscopio. La comunicación con el microcontrolador se estableció mediante el protocolo I2C, permitiendo una transferencia de datos digital y robusta. La elección de este sensor se basó específicamente en la posibilidad de complementar las medidas de aceleración y velocidad angular para aproximar el ángulo de inclinación con alta precisión.
Estrategia de Fusión de Datos: Filtro Complementario
Debido a las propiedades físicas de cada sensor, se implementó un algoritmo de fusión de datos que permite obtener una medida más precisa que si se usaran de forma aislada:
	Acelerómetro (Ventajas y Limitaciones): Permite calcular el ángulo de inclinación respecto a la gravedad mediante funciones trigonométricas (como se observa en el cálculo de accelX y accelY). Su principal ventaja es que proporciona una referencia estable a largo plazo; sin embargo, es muy susceptible al ruido de alta frecuencia y a las vibraciones mecánicas producidas por el volante de inercia, lo que genera lecturas "sucias" en movimiento.
	Giroscopio (Ventajas y Limitaciones): Mide la velocidad angular en grados por segundo. Al integrar este valor en el tiempo, se obtiene un ángulo de respuesta inmediata y muy fluido, ideal para cambios rápidos de posición. No obstante, su gran desventaja es la deriva (drift), donde pequeños errores de medición se acumulan con el tiempo, causando que el ángulo se desvíe del valor real incluso si la bicicleta está estática.
Unión de medidas mediante Filtro Complementario: El código implementado utiliza la constante ALPHA para balancear ambas señales en cada ciclo de ejecución de aproximadamente 5 milisegundos (200 Hz). De esta forma, el sistema aplica un filtro pasa-bajo al acelerómetro para quedarse solo con su estabilidad, y un filtro pasa-alto al giroscopio para eliminar su deriva. El resultado final se almacena en angleX, el cual se ajusta con un offset de -3 grados para corregir la alineación mecánica del montaje, convirtiéndose finalmente en la variable pidInput que alimenta al controlador.

Montaje e Integración del Microcontrolador
Para la gestión de procesos y el control de la planta, se integró un microcontrolador ESP32 montado sobre una base central diseñada para aislar los componentes electrónicos de las vibraciones mecánicas. La transición hacia esta plataforma ofreció ventajas tecnológicas determinantes para el rendimiento del sistema:
	Capacidad de Procesamiento y Velocidad: El ESP32 opera con un reloj de hasta 240 MHz, lo que garantiza una velocidad de ejecución significativamente superior para el lazo de control PID. Esto permite procesar los algoritmos de filtrado y las leyes de control con una latencia mínima, asegurando que el tiempo de respuesta del servomotor sea casi instantáneo respecto a la detección del ángulo de inclinación.
	Periféricos y Escalabilidad: Se utilizaron los periféricos de PWM de alta resolución para generar la señal de control del servomotor de 80 kg, permitiendo movimientos fluidos y precisos. Además, la presencia de conectividad Wi-Fi y Bluetooth integrada abre la posibilidad para futuras actualizaciones, como la implementación de un sistema de telemetría o un control remoto tipo Radio Control (RC) para manejar la bicicleta a distancia sin necesidad de hardware adicional.
	Depuración y Monitoreo en Tiempo Real: Gracias a la comunicación vía serial a través de la interfaz USB, fue posible realizar una depuración (debugging) exhaustiva. Esto permitió visualizar en tiempo real los datos provenientes de la IMU MPU9250 y el comportamiento de la señal de salida del PID, facilitando la sintonización fina de las constantes de control.
	Gestión de Energía e Independencia Eléctrica: Para la alimentación del microcontrolador, se implementó un regulador DC-DC conmutado (buck) ajustado a 5V. El uso de una fuente conmutada garantiza un voltaje estable y una alta eficiencia energética, independizando la electrónica lógica de la etapa de potencia. Esto es fundamental para evitar reinicios o errores de lectura provocados por las caídas de tensión que ocurren cuando el servomotor de alto torque demanda corrientes pico durante las correcciones de equilibrio.

Interfaz de Actuación y Acople de Potencia
La interfaz de actuación constituye el vínculo físico entre las decisiones del microcontrolador y la respuesta dinámica de la planta. Para garantizar que el torque de corrección fuera efectivo, se implementaron las siguientes soluciones técnicas:
	Acople Directo y Eliminación de "Backlash": El servomotor de 80 kg-cm se vinculó al eje de dirección mediante un acople diseñado a medida con tolerancia mínima. Esta unión de alta precisión permite una transferencia directa de potencia, eliminando el juego mecánico (backlash). En sistemas de control de equilibrio, la ausencia de juego es vital, ya que cualquier desfase entre la orden del PID y el movimiento real del volante de inercia podría generar oscilaciones incontrolables o inestabilidad en el lazo cerrado.
	Gestión de Torque con Engranajes de Acero: Debido a la gran inercia del conjunto volante-motor, el actuador se ve sometido a esfuerzos mecánicos considerables durante las correcciones rápidas. Se seleccionó un servomotor con tren de engranajes fabricado íntegramente en acero, lo que le permite soportar el torque de bloqueo y las fuerzas de reacción del efecto giroscópico sin sufrir deformaciones o roturas en los dientes de los piñones.
	Etapa de Potencia Independiente: La alimentación del motor se configuró a un voltaje de 6V mediante un regulador DC-DC independiente capaz de suministrar hasta 10 Amperios. Esta separación de fuentes es fundamental; al ser un motor de alto torque, las demandas de corriente pico durante los cambios de dirección podrían causar caídas de tensión que afectarían la estabilidad del microcontrolador si compartieran la misma línea de alimentación.
	Filtrado y Supresión de Ruido Eléctrico: Se instaló un arreglo de condensadores en paralelo entre las líneas de VCC y GND de la etapa de potencia. Estos actúan como filtros de desacople, absorbiendo los picos de ruido electromagnético producidos por las conmutaciones internas del motor y las inversiones de marcha bruscas. Esta medida protege la integridad de las señales lógicas y evita que el ruido parásito interfiera con las lecturas de alta precisión del sensor MPU9250.



Fase 3: Construcción y Sintonización del Controlador PID

Esta fase consistió en el desarrollo del algoritmo que permite el equilibrio autónomo:
	Fusión de Sensores: Se programó un Filtro Complementario para combinar la estabilidad del acelerómetro con la rapidez del giroscopio.
	Cálculo del Error: Se definió el Set Point en 140° (equilibrio vertical). El controlador calcula la diferencia entre el ángulo real y el deseado.
	Sintonización de Constantes: Se ajustaron experimentalmente las ganancias , y para lograr una respuesta amortiguada que evite oscilaciones violentas.

Fase 4: Adaptación y Construcción del Sistema de Alimentación
Para garantizar la portabilidad (operación unplugged), se desarrolló un sistema de energía independiente:
	Ensamblaje del Pack LiFePO4: Se configuraron 6 celdas en serie para obtener un voltaje nominal de 20V-24V.
	Gestión de Carga (BMS): Se instaló un sistema de protección para monitorear el balanceo de las celdas y evitar descargas profundas.
	Regulación de Voltaje: Se implementaron convertidores DC-DC para separar la etapa de potencia (motores) de la etapa lógica (sensores y microcontrolador), evitando que el ruido eléctrico reinicie el sistema.


	Conclusiones y Recomendaciones
Esta sección se nutre de las implicaciones de la pasantía en la práctica, de las lecciones metodológicas aprendidas, de las limitaciones de la pasantía, de los aspectos no resueltos y nuevas preguntas o necesidades creadas a partir del mismo, propuestas de nuevos proyectos a partir de los resultados actuales.
 
	Referencias
Las referencias deben estar en normas APA, se recomienda utilizar un gestor de referencias.
 
	Anexos
De ser necesario, se pueden preparar Anexos en orden alfabético (Anexo 1, Anexo 2, etc.). Pueden ser utilizados para presentar mayor detalle sobre algún aspecto del documento sin romper el hilo conductor del texto principal. Por ejemplo, se puede usar para presentar el formato de encuesta que se espera usar en el proyecto, o un protocolo de observación, etc.

 
PAUTAS PARA LA REDACCIÓN DEL DOCUMENTO
Se propone el seguimiento de las normas de la APA. En general se espera que la ortografía sea impecable (no confiarse del corrector de MS Word). Las propuestas deben estar bien presentadas; se debe cuidar: la unidad del estilo del texto, títulos y sub-títulos a lo largo del documento.

Cada capítulo debe comenzar en una nueva página. El fin de una sección y el encabezado de la próxima no deben ser separados por espacios adicionales. Cuándo una sección comienza al final de la página, ésta debe ser trasladada a la página siguiente si el primer párrafo de la sección no alcanza a tener dos líneas de texto.

La extensión del documento no debe superar las 60 páginas sugerido (70 páginas máximo) sin incluir los preliminares (portada, contraportada, índices, dedicatoria, glosario, siglas); Listado de referencias bibliográficas  ni  Anexos

Estilo y formato:
Redacción: La propuesta debe ser redactada en tercera persona. 
Texto y formato de los párrafos: La letra del documento es Times New Roman tamaño 12 o equivalente, el interlineado es sencillo. Además, se deben parametrizar el párrafo con los siguientes valores:
	Alineación: Justificada.
	Espaciado: Anterior: 12 pto, Posterior: 12 pto, Interlineado: 1,0
	Viñetas y significado de variables y parámetros de fórmulas: Espaciado (Anterior: 6 pto, Posterior: 6 pto)
Títulos:   A continuación, una descripción de los tipos de títulos y sus características:
	Título 1 (Sección primaria o Capítulo): Times New Roman Negrita tamaño 14
	Titulo 2 (sección secundaria o Sub-capítulo): Times New Roman Negrita tamaño 13.
	Título 3 (sección terciaria): Times New Roman Negrita tamaño 12
Número de Página Todas las páginas deben estar numeradas excepto la portada. Las páginas previas al capítulo de introducción deben ser numeradas en números romanos (i, ii, iii, iv, v,…) en minúsculas, mientras que a partir de la introducción debe ser arábiga (1,2,3…).
Notas al pie de página. Las notas al pie de página tienen por finalidad brindar una información extra o aclarar un concepto dentro del cuerpo principal. Son una herramienta útil para agregar contenido que para un lector lego puede ser de utilidad para interpretar o entender lo que se está presentando. Las notas al pie de página deberán ser referenciadas utilizando un superíndice y la nota al pie de página deberán tener un tamaño de letra entre 10 a 8. Utilizar la funcionalidad pie de página para esta parte del texto.
Figuras y Tablas en el texto. La resolución adecuada de fotos y figuras que permitan leer y entender el mensaje que se desea entregar. Toda tabla y figura debe tener un título. Además, toda tabla y figura debe ser anunciada en el texto del documento antes de aparecer en el mismo, no olvide referenciarla

Ejemplo:
Se evaluó la simulación de la marcha normal, al igual que las diferentes fases de un ciclo, trazando la flexión y extensión de la cadera contra la flexión y extensión de la rodilla. La cadera está en el eje x y la rodilla está en el eje y; La magnitud de los gráficos se indica en ángulos. El resultado del ciclograma mostrado en la Figura 6 concuerda con los resultados reportados en la literatura, ya que los ángulos de rodilla y cadera están dentro de los límites de los valores observados en estudios previos.

 
Figura 6. Ciclograma para analizar la marcha. a) Contacto inicial; b) Respuesta de carga; c) Apoyo media; d) Apoyo terminal; e) Prebalanceo f) Balanceo inicial; g) Balanceo medio; h) Balanceo terminal. (Camargo, 2018)
En el caso de las tablas se sigue un criterio similar a las figuras, el tamaño mínimo de la letra al interior de la tabla es 11.
Ejemplo:
Como se muestra en la Tabla 1, los valores de t para un nivel de confidencia del 95%, depende de los grados de libertad asociados con la desviación estándar.
Grados de Libertad	Nivel de confidencia
2	4.303
4	2.776
6	2.447
Tabla 3. Variables de medición. Fuente: El Autor

Ecuaciones y Fórmulas. Las ecuaciones deben ser elaboradas en un editor de ecuaciones apropiado. Si utiliza Word, use o bien Microsoft Editor de Ecuaciones o  MathType. Numere las ecuaciones consecutivamente, deben estar centradas, por orden de aparición, con números arábigos entre paréntesis justificado al margen derecho. Las ecuaciones al igual que las figuras y tablas deben ser anunciadas en el texto del documento antes de aparecer en el mismo. 

Ejemplo:
La curva de frecuencia (1) de los valores medios  \bar{x}  está centrada alrededor del valor límite medio m y tiene un factor de escala\sfrac{s}{\sqrt n}

t=\frac{\bar{x}-m}{\sfrac{s}{\sqrt n}}	(1)
Citaciones Las citaciones son referencias a textos realizados por otras personas, las podemos clasificar en tres grandes grupos:
	Formales: donde se transcriben literalmente textos. Es imprescindible que éstas sean colocadas entre comillas e indicar su fuente.
	Conceptuales: en este caso se reproduce el concepto utilizando palabras propias, es una síntesis personal de una idea basándose en otra idea, es necesario referenciar usando normas APA.

Referencias Las referencias bibliográficas constituyen una parte importante del texto donde se detallan todas las fuentes consultadas en el trabajo que se está presentando. Es importante detallarlo adecuadamente para que posteriormente otros lectores puedan realizar búsquedas de esas referencias. 
Las referencias deberán ser ordenadas considerando el apellido del primer autor, en caso de que el autor tenga más de un artículo o trabajo referenciado en el informe se debe ordenar por el año de publicación. Para mayor información sobre la forma de referenciar se les sugiere que revisen las normas APA.
Especificando las referencias 
Considere los siguientes ejemplos que se detallan a continuación para realizar las referencias. El autor debe dejar un espacio entre una y otra referencia.




Referencias de libros: 
Young, H. D., & Freedman, R. A. (2018). Física universitaria con física moderna (14.ª ed.). Pearson Educación.
Serway, R. A., & Jewett, J. W. (2015). Física para ciencias e ingeniería (9.ª ed.). Cengage Learning.

Referencia de  páginas web:
Cain, S. (2016). The mysterious biomechanics of riding – and balancing – a bicycle. University of Michigan Mechanical Engineering. Recuperado de https://me.engin.umich.edu/news-events/news/mysterious-biomechanics-riding-and-balancing-bicycle/
Adams, V. H. (s.f.). Complementary filters. Van Hunter Adams - Cornell University. Recuperado de https://vanhunteradams.com/Pico/ReactionWheel/Complementary_Filters.html
National Instruments. (2025). Explicación sobre el controlador PID y la teoría. Recuperado de https://www.ni.com/es/shop/labview/pid-theory-explained.html
Espressif Systems. (2024). ESP32 Series Datasheet. Recuperado de https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf
InvenSense. (2016). MPU-9250 Product Specification Revision 1.1. TDK Corporation. Recuperado de https://invensense.tdk.com/download-pdf/mpu-9250-datasheet/





# Investigación: ClassMate AI — Organizador académico inteligente



## 1. Planteamiento del problema



Los estudiantes universitarios reciben constantemente información relacionada con sus actividades académicas. Esta información puede llegar mediante correos electrónicos, plataformas educativas, grupos de mensajería, documentos compartidos y avisos de profesores. Entre los mensajes que reciben se encuentran instrucciones para realizar tareas, fechas de exámenes, cambios de horario, recordatorios de entregas y materiales para estudiar.



Aunque estos medios facilitan la comunicación, también pueden provocar que la información importante quede distribuida en diferentes lugares. Como consecuencia, los estudiantes pueden invertir tiempo buscando mensajes anteriores, revisar varias plataformas para encontrar una instrucción o tener dificultades para distinguir cuáles actividades requieren atención primero.



La acumulación de información digital en el entorno universitario ha sido estudiada por Sillence, Dawson, McKellar y Neave (2023). Su investigación incluyó entrevistas individuales y grupales con 18 estudiantes universitarios. Los autores identificaron diferentes formas de almacenar y organizar información digital, así como dificultades relacionadas con la acumulación de datos. Entre los temas encontrados se mencionan la sobrecarga de información, la pérdida de productividad y la sensación de sentirse abrumado. El estudio también señala la importancia de ofrecer mayor orientación a los estudiantes para administrar su información académica.



Otro antecedente relevante es la investigación de Álvarez-Flores, Magdaleno Moreno y Núñez-Gómez (2024), que analizó las competencias informacionales de 746 estudiantes universitarios de seis países hispanohablantes. Los resultados identificaron áreas de oportunidad en la búsqueda, evaluación y gestión de información digital. Aunque el estudio se enfoca principalmente en el uso de bibliotecas digitales, permite reconocer que la administración de información sigue siendo un reto dentro de la educación universitaria.

Para dimensionar el contexto, la Encuesta Nacional sobre Disponibilidad y Uso de Tecnologías de la Información en los Hogares (ENDUTIH) 2025 del INEGI estimó que **86.1 %** de la población mexicana de 6 años y más usó internet, lo que equivale a **104.9 millones de personas** ([INEGI, 2026](https://www.inegi.org.mx/contenidos/saladeprensa/boletines/2026/endutih/ENDUTIH_25.pdf)). Esto indica que la mayor parte de la población, incluidos los estudiantes universitarios, recibe información por canales digitales, lo que vuelve relevante contar con herramientas que ayuden a ordenarla. Estas cifras muestran el alcance de los medios digitales, pero no miden por sí solas la sobrecarga de información; por eso se complementan con los estudios anteriores.




A partir de estos antecedentes, se identifica una oportunidad para desarrollar una herramienta que facilite la clasificación inicial de mensajes académicos. El proyecto ClassMate AI propone utilizar inteligencia artificial para analizar textos proporcionados por el estudiante y sugerir una categoría relacionada con su contenido. Las categorías iniciales serán tareas, exámenes, recordatorios y temas de estudio.



El objetivo no es sustituir los calendarios, las plataformas escolares ni la responsabilidad del estudiante de revisar sus actividades. La intención es ofrecer un apoyo adicional para reconocer con mayor facilidad qué tipo de información contiene un mensaje. De esta manera, se busca reducir parte del trabajo manual relacionado con la organización de textos académicos.



## 2. Soluciones existentes

| Solución | Qué ofrece | Limitaciones |
|:---|:---|:---|
| Notas y listas manuales (cuaderno, notas del celular) | Control total y sin costo | Hay que clasificar cada aviso a mano; es fácil olvidar o perder información |
| Calendarios digitales (por ejemplo, Google Calendar) | Fechas de entrega y recordatorios | Cada evento se captura a mano; no interpretan el texto de un mensaje |
| Aplicaciones de tareas y notas (por ejemplo, Notion o Todoist) | Listas, etiquetas y proyectos | El usuario define y asigna las categorías; no clasifican el contenido automáticamente |
| Plataformas educativas (por ejemplo, Moodle o Google Classroom) | Centralizan tareas y avisos de cada curso | Solo cubren los cursos de esa plataforma; no integran mensajes de otros canales |




Actualmente existen diferentes herramientas digitales que ayudan a los estudiantes a administrar sus actividades. Entre ellas se encuentran los calendarios electrónicos, las aplicaciones de listas de pendientes, las plataformas educativas y los servicios de correo electrónico.



Los calendarios permiten registrar fechas importantes y consultar actividades programadas. Las aplicaciones de tareas ayudan a crear listas, establecer prioridades y marcar actividades como terminadas. Por su parte, las plataformas educativas permiten consultar materiales, instrucciones, calificaciones y avisos relacionados con las materias.



Sin embargo, estas herramientas no siempre resuelven el problema de identificar automáticamente el contenido de los mensajes que recibe un estudiante. En muchos casos, el usuario debe leer la información, decidir qué significa y registrarla manualmente en el lugar correspondiente. Si recibe muchos mensajes en diferentes medios, este procedimiento puede convertirse en una actividad repetitiva.



ClassMate AI busca complementar las soluciones existentes mediante la clasificación automática de texto. Su propuesta consiste en permitir que el estudiante introduzca un mensaje académico y reciba una categoría sugerida por el modelo. Por ejemplo, un texto que indique la entrega de un trabajo podría clasificarse como tarea, mientras que un aviso sobre una evaluación podría identificarse como examen.



La principal diferencia de la propuesta es que la clasificación se realiza a partir del contenido escrito, en lugar de depender exclusivamente de que el usuario seleccione una categoría desde el principio. No obstante, ClassMate AI no pretende reemplazar las herramientas mencionadas ni ofrecer todas sus funciones. Su alcance inicial será más específico: apoyar la identificación y organización de información académica mediante clasificación de texto.



También es importante reconocer que una clasificación automática no garantiza que el resultado sea correcto. Por esa razón, la propuesta contempla que el usuario pueda revisar la categoría sugerida y corregirla cuando sea necesario.



## 3. Uso de inteligencia artificial y selección del modelo

Comparación del modelo elegido con una alternativa multilingüe, según sus Model Cards en Hugging Face ([DeBERTa](https://huggingface.co/MoritzLaurer/deberta-v3-base-zeroshot-v2.0) y [BGE-M3](https://huggingface.co/MoritzLaurer/bge-m3-zeroshot-v2.0)):

| Característica | deberta-v3-base-zeroshot-v2.0 | bge-m3-zeroshot-v2.0 |
|:---|:---|:---|
| Parámetros | Aproximadamente 0.2B | Aproximadamente 0.6B |
| Memoria estimada (16 bits) | Cerca de 0.4 GB | Cerca de 1.2 GB |
| Licencia | MIT | MIT |
| Idiomas | Pensado para inglés | Multilingüe |
| Texto máximo | 512 tokens | 8192 tokens |
| Ventajas | Más ligero y rápido; mejor desempeño que los multilingües en inglés | Admite español y textos más largos |
| Desventajas | Puede rendir peor con textos en español | Más pesado; su Model Card advierte que los multilingües rinden peor que los de solo inglés |

El equipo mantiene DeBERTa como candidato inicial por ser más ligero, y en el Parcial III lo comparará con BGE-M3 usando textos académicos en español.




La inteligencia artificial puede utilizarse para analizar información escrita y reconocer patrones relacionados con el significado de un texto. Dentro del procesamiento del lenguaje natural existe una tarea conocida como clasificación de texto, que consiste en asignar una o varias categorías a una entrada escrita de acuerdo con su contenido.



Para ClassMate AI se propone utilizar clasificación de texto de tipo \*zero-shot\* o clasificación sin ejemplos específicos de entrenamiento para cada categoría. Este enfoque permite proporcionar un texto y un conjunto de etiquetas posibles para que el modelo estime cuál se relaciona mejor con el contenido.



La documentación de Hugging Face explica que la clasificación \*zero-shot\* permite proporcionar una oración o un párrafo junto con las etiquetas candidatas, incluso cuando el modelo no fue entrenado específicamente con esas etiquetas. Esto resulta útil para explorar categorías propias de un proyecto sin tener que construir desde el inicio un conjunto amplio de datos etiquetados.



Una ventaja de este enfoque es que permite comenzar con categorías definidas para el contexto académico, como tareas, exámenes, recordatorios y temas de estudio. Además, facilita realizar pruebas iniciales con ejemplos escritos en español y observar si el modelo distingue correctamente las categorías.



Sin embargo, no se debe asumir que todos los modelos de clasificación funcionan igual de bien. Ma, Yao, Lin y Zhao (2021) analizaron dificultades de la clasificación \*zero-shot\* basada en inferencia de lenguaje natural. Los autores identificaron variaciones importantes en el desempeño entre conjuntos de datos y señalaron que algunos modelos pueden depender de patrones de palabras que no necesariamente representan el significado completo del texto.



Por esta razón, la selección del modelo deberá considerar su capacidad para procesar español, su licencia, el número de parámetros, sus requerimientos computacionales y sus limitaciones documentadas. También será necesario probarlo con mensajes académicos de diferentes materias y estilos de redacción.



Como candidato inicial se propone evaluar modelos disponibles en Hugging Face que estén diseñados para clasificación \*zero-shot\*. La elección definitiva se realizará después de comparar los resultados obtenidos con ejemplos en español. No se considerará suficiente que un modelo tenga buenos resultados en otros idiomas o tareas: deberá demostrar un comportamiento adecuado para las categorías específicas de ClassMate AI.



La evaluación podrá realizarse mediante un conjunto de ejemplos escritos o recopilados para las pruebas del proyecto. Cada ejemplo tendrá una categoría esperada definida previamente por el equipo. Después se comparará la categoría sugerida por el modelo con la categoría asignada como referencia.



Se podrán registrar los aciertos, errores y casos ambiguos para calcular el porcentaje de clasificaciones correctas y observar qué categorías presentan más dificultades. También será importante revisar ejemplos en los que un mismo mensaje pueda relacionarse con más de una categoría.



La investigación de Edwards y Camacho-Collados (2024), publicada en las actas de LREC-COLING, compara distintos enfoques de clasificación de texto mediante modelos de lenguaje y métodos tradicionales. Su trabajo muestra que los enfoques de mayor tamaño no necesariamente superan a modelos más pequeños y eficientes en todas las tareas. Este antecedente respalda la necesidad de comparar alternativas y seleccionar el modelo según los resultados y recursos disponibles, en lugar de elegirlo únicamente por su tamaño.



## 4. Usuarios y requisitos del sistema

**Requisitos funcionales**

- Recibir un texto pegado por el estudiante (mensaje, aviso o apunte).
- Clasificarlo en una categoría: tarea, examen, recordatorio o tema de estudio.
- Mostrar la categoría sugerida de forma clara.
- Permitir que el usuario corrija la categoría manualmente.
- Funcionar con textos escritos en español.

**Requisitos no funcionales**

- No pedir datos personales innecesarios.
- Responder en pocos segundos.
- Tener una interfaz sencilla, sin configuración técnica.




Los usuarios principales de ClassMate AI serán estudiantes universitarios que reciben mensajes e instrucciones relacionados con sus materias. La herramienta estará orientada a personas que necesitan identificar y organizar información académica escrita en diferentes formatos de comunicación.



El funcionamiento propuesto comienza cuando el estudiante introduce un mensaje o una instrucción académica en un campo de texto. Posteriormente, el sistema enviará el contenido al modelo de clasificación para que analice el texto y estime cuál de las categorías disponibles se relaciona mejor con él.



Como resultado, el sistema mostrará una categoría sugerida. Las categorías iniciales serán:



\- \*\*Tarea:\*\* instrucciones para realizar actividades, ejercicios, proyectos o trabajos.

\- \*\*Examen:\*\* información relacionada con evaluaciones, pruebas o parciales.

\- \*\*Recordatorio:\*\* avisos sobre fechas, pendientes o actividades que requieren atención.

\- \*\*Tema de estudio:\*\* contenidos, lecturas o conceptos que el estudiante debe revisar o aprender.



El usuario podrá revisar la sugerencia y corregirla si considera que no corresponde al mensaje. Esta posibilidad es importante porque los textos académicos pueden ser ambiguos o contener información relacionada con más de una categoría.



Los requisitos funcionales iniciales serán los siguientes:



1\. Permitir que el usuario introduzca un mensaje académico.

2\. Procesar el texto mediante un modelo de clasificación.

3\. Comparar el contenido con las categorías disponibles.

4\. Mostrar la categoría sugerida.

5\. Permitir que el usuario revise y corrija la clasificación.



Entre los requisitos no funcionales se encuentran la facilidad de uso, la claridad de los resultados y un tiempo de respuesta adecuado para realizar pruebas. También será importante que la herramienta informe al usuario cuando no pueda realizar una clasificación confiable, en lugar de presentar cualquier resultado como si fuera completamente correcto.



El alcance inicial será limitado para facilitar su desarrollo y evaluación. Funciones adicionales, como extraer fechas automáticamente, crear eventos en calendarios, detectar prioridades o resumir mensajes, podrán considerarse como mejoras futuras, pero no se presentarán como características existentes hasta que sean desarrolladas y probadas.



## 5. Consideraciones éticas y riesgos



El uso de inteligencia artificial en un contexto académico implica responsabilidades relacionadas con la precisión, la privacidad y la intervención humana. Aunque ClassMate AI tiene como finalidad apoyar la organización de información, sus resultados pueden influir en la manera en que un estudiante interpreta sus pendientes.



Uno de los principales riesgos es la clasificación incorrecta de un mensaje. Por ejemplo, una instrucción que indique la entrega de un proyecto y mencione una fecha de evaluación podría ser interpretada de manera equivocada. Si el estudiante confía completamente en la sugerencia, podría organizar incorrectamente esa información.



Para disminuir este riesgo, las categorías generadas por el modelo deberán presentarse como sugerencias y no como decisiones definitivas. El usuario conservará la responsabilidad de revisar el resultado y podrá corregirlo cuando sea necesario. Además, el equipo deberá evaluar el sistema con ejemplos variados y registrar los errores encontrados para identificar sus limitaciones.



Otro riesgo importante es la privacidad de los datos. Los mensajes académicos pueden incluir nombres, direcciones de correo electrónico, datos de profesores, información institucional o detalles personales. Por ello, se recomienda utilizar ejemplos ficticios o textos previamente anonimizados durante las pruebas y evitar introducir información confidencial que no sea necesaria para evaluar el modelo.



La UNESCO (2023), en su documento de orientación sobre inteligencia artificial generativa en educación e investigación, destaca la importancia de mantener un enfoque centrado en las personas. También señala la necesidad de considerar la protección de datos, la transparencia y la intervención humana al incorporar inteligencia artificial en contextos educativos. Aunque ClassMate AI propone clasificación de texto y no necesariamente generación de contenido, estos principios sirven como referencia para orientar el diseño responsable del proyecto.



También debe considerarse que los modelos pueden presentar diferencias de desempeño dependiendo del idioma, la forma de redactar y el contexto de los mensajes. Un modelo que funciona adecuadamente con textos formales podría tener dificultades con abreviaturas, errores ortográficos o expresiones comunes en conversaciones estudiantiles. Para atender este riesgo, se deberán incluir ejemplos variados en las pruebas y evitar afirmar que el sistema funciona correctamente en todos los casos.



Finalmente, ClassMate AI deberá utilizarse como una herramienta de apoyo y no como sustituto de la revisión personal de las actividades académicas. La decisión final sobre la interpretación de un aviso o una instrucción deberá permanecer en manos del estudiante.



## 6. Referencias



Álvarez-Flores, E. P., Magdaleno Moreno, M., \& Núñez-Gómez, P. (2024). Competencia y comportamiento informacionales de estudiantes para el uso de las bibliotecas digitales universitarias. \*Investigación Bibliotecológica: Archivonomía, Bibliotecología e Información, 38\*(99), 129–144. https://doi.org/10.22201/iibi.24488321xe.2024.99.58881



Edwards, A., \& Camacho-Collados, J. (2024). Language Models for Text Classification: Is In-Context Learning Enough? \*Proceedings of the 2024 Joint International Conference on Computational Linguistics, Language Resources and Evaluation (LREC-COLING)\*, 10058–10072. https://aclanthology.org/2024.lrec-main.879/



Hugging Face. (s. f.). \*Zero-Shot Classification\*. https://huggingface.co/docs/inference-providers/main/tasks/zero-shot-classification



Ma, T., Yao, J.-G., Lin, C.-Y., \& Zhao, T. (2021). Issues with Entailment-based Zero-shot Text Classification. \*Proceedings of the 2021 Conference on Empirical Methods in Natural Language Processing\*. Association for Computational Linguistics. https://www.microsoft.com/en-us/research/publication/issues-with-entailment-based-zero-shot-text-classification/



Sillence, E., Dawson, J. A., McKellar, K., \& Neave, N. (2023). How do students use digital technology to manage their university-based data: Strategies, accumulation difficulties and feelings of overload? \*Behaviour \& Information Technology, 42\*(14), 2442–2451. https://doi.org/10.1080/0144929X.2022.2126948



UNESCO. (2023). \*Guidance for generative AI in education and research\*. https://unesdoc.unesco.org/ark:/48223/pf0000386693

- INEGI. (2026). [Encuesta Nacional sobre Disponibilidad y Uso de Tecnologías de la Información en los Hogares (ENDUTIH) 2025](https://www.inegi.org.mx/contenidos/saladeprensa/boletines/2026/endutih/ENDUTIH_25.pdf).

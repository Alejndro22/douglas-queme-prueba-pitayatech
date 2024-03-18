## Caso 1

1. Como primer paso, reuniría requerimientos en conjunto con los clientes. De esta forma identificaría la información que el negocio considera relevantes para el reporte, así como determinar las fuentes de información más confiables.

2. Luego, realizaría un análisis a a información guardada en la base de datos del sistema. En caso de contener toda la información necesaria, se podría seguir al siguiente paso. En caso de que no se cumpla esto, se podría plantear un rediseño a las tablas ya existentes, o plantear la posibilidad de crear nuevas que contengan esta información.

3. Determinar la herramienta más adecuada para realizar el reporte. En caso de necesitar un reporte estándar, podríamos construirlo con herramientas que ya provee Odoo como QWeb Reports que ya usa templates. Si necesitamos un reporte demasiado específico, podría plantearse la integración de un módulo nativo escrito en Python, donde se usen herramientas como Numpy, Pandas, Matplotlib y Seaborn para generar el reporte.

4. Realizaría pruebas en ambos casos para determinar que el funcionamiento es correcto. Estas pruebas deben abarcar tanto el rendimiento de la aplicación como la estimación del costo, pues siempre que se pueda se deben hacer optimizaciones que reduzcan el uso de servidores.

**_Comentario:_** Un reporte es una funcionalidad muy pedida en los sistemas empresariales, por lo que su construcción idealmente debería ser de entre 1 y 2 sprints de 15 días, aunque esto puede variar en base a la complejidad del mismo.

## Caso 2

1. Inicialmente, se debe generar una planificación para almacenar la información de contacto de los clientes. En caso de ya existir, asegurarse de que permita almacenar número de teléfono y/o correo electrónico.

2. Determinar cuál será el trigger que dispare la acción. Con esto me refiero a si se hará automáticamente cuando se registre la venta, cuando cambie algún valor en la base de datos, o si el usuario del sistema debe autorizar el envío del correo manualmente.

3. Si es una encuesta simple, determinar si es mejor almacenarla en herramientas como Google Forms, o crear una plantilla sencilla almacenada en los servidores de la empresa.

4. El envío de correos automatizados puede llevarse a cabo por medio de scripts de Python con librerías como _smtplib_ . Aunque para su funcionamiento correcto, deberíamos asegurarnos de contar con algún correo institucional que permita acceso y credenciales por el protocolo de envío de correos _SMTP_, o contar con un servidor _SMTP_ y configurarlo. Alternativamente, podríamos hacer una investigación para encontrar algún módulo de Odoo que ya esté optimizado para esta tarea.

5. Comparar costos de implementación y monetarios para ambas propuestas, y elegir la que nos sea más conveniente.

6. Finalmente, asegurarnos de obtener insights relevantes con la encuesta. Nuevamente, podemos realizar análisis de datos con la información obtenida para descubrir nuevas tendencias o servicios que no están funcionando como esperamos.

**_Comentario:_** Esta funcionalidad es más compleja, pues puede tener algunas complicaciones como clasificar los correos como spam, bloqueo del correo por lo mismo de detectarlo como envío masivo de spam, etc. Entonces para tener este módulo personalmente considero que si tomaría al menos 3 sprints de 15 días para su funcionalidad finalizada. Pero para tenerlo completo y con todo funcionando, estimo una holgura de otros 2 sprints.

## Caso 3

1. Realizar un análisis exploratorio de la información recolectada, principalmente para asegurarse de que mantiene una estructura estandarizada.

2. El problema se facilita pues la aplicación ya genera los archivos como reportes de Excel. En este caso podíamos considerar generar el reporte directamente como csv, o sino hacer una conversión que no es nada compleja.

3. Ya con los datos en csv, es mucho más sencillo cargarlos a la aplicación. Esto se podría hacer mediante un script que use pandas para extraer la información e insertarla directamente en la base de datos.

4. Sin embargo, si se desea un enfoque más interactivo y fácil de entender para el usuario común, podemos crear un pequeño módulo que tenga esta funcionalidad en métodos, y que el usuario solo tenga que cargar el archivo csv como si cargara un archivo en una petición a una API REST.

5. Otra alternativa sería almacenar este reporte, ya sea de Excel o CSV en Amazon S3 y obtener el enlace del recurso, para evitar que el usuario descargue muchos archivos, y trabajar únicamente con los enlaces generados. Esta opción reduce el uso de almacenamiento local, pero aumenta el uso en la nube, aunque por el tamaño relativamente bajo de los archivos .xls y .csv me parece una opción a tener en cuenta.

**_Comentario:_** Valdría la pena evaluar si hay alguna integración nativa entre Odoo y archivos .xls o .csv, pero en cualquier caso, es factible hacer un módulo específico. Para realizar esto considero que un sprint sería un buen tiempo para realizarlo, y dejar una holgura de otro sprint para asegurarse de que todo esté bien, o por si se necesita tiempo extra para familiarizarse con el output que tiene el archivo Excel.

### Comentarios finales

- Para todos los casos, es importante resolver los problemas dividiendolos en subproblemas que sean más sencillos de resolver. Esto también facilita el trabajo en equipo.

- Siguiendo con el punto anterior, podría sugerir el uso de gitflow para mantener el trabajo remoto coordinado del equipo de trabajo, uso de commits descriptivos y manejo de ramas.

- Otro aspecto importante es tomarse el tiempo necesario para crear interfaces intuitivas para los usuarios, evitar sobrecargar pantallas de información, y proveer las instrucciones necesarias para el usuario se sienta más cómodo.

- También para todos recomendaría generar documentación por cada nueva funcionalidad, para que a los clientes se les facilite interactuar con ellas. En caso de que no sea suficiente, considerar planificar algunas inducciones.

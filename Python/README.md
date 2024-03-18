### 1. Mencione 3 normas pertenecientes a la guía de estilos PEP8 y brinde ejemplos de su uso e importancia.

1.  **Convenciones en los nombres:** Esta me parece una norma de suma importancia porque brinda consistencia al código.
    Es por esto que brinda agilidad al momento de escribir y escalar el código, pues si las variables son descriptivas y siguen el case
    debido, se puede comprender al leerse, evitando la necesidad de leer todo el código para comprenderlo.

    **_Ejemplos:_**

    - Nombre de variable: python_variable
    - Nombre de clase: PythonClass
    - Nombre de constante: PY_CONSTANT

2.  **Comentarios:** Los comentarios son una herramienta para mantener documentación a nivel de código. Es por esto, que deben centrarse
    principalmente en describir el funcionamiento principal de métodos, variables, etc. No se recomienda una descripción detallada, pues puede hacer mucho ruido en el código, y para ello el lugar adecuado sería la documentación técnica del proyecto.

    **_Ejemplo:_**

    `# Se genera una consulta a la base de datos tomando como parámetro la fecha actual. Con los resultados de la consulta se construye un reporte siguiendo el formato establecido`

    def create_monthly_report(self):

3.  **Identación y largo máximo de línea:** Se recomienda usar 4 espacios para la identación, y en largo máximo de línea no exceder los 79 carácteres. Así mismo, cuando se tienen métodos que toman muchos parámetros, se recomienda dividir el código en varias líneas. Estas convenciones facilitan la lectura de código, y por tanto contribuyen a un desarrollo más rápido del código.

        def create_monthly_report(self, date,

                                  user, language,

                                  primary_colors, photo,

                                  type):

### 2. Describa los tipos de datos mutables de Python

Este tipo de datos permiten su modificación luego de ser creados. Los ejemplos más comunos de estos son las listas, diccionatios, sets y clases. Cuando trabajamos con funciones, Python pasa este tipo de datos por referencia.

### 3. Describa los tipos de datos mutables de Python

Este tipo de datos es más estricto, por lo que no permite su modificación luego de ser creados. Un ejemplo son las tuplas, que no permiten modificación luego de ser declaradas. Aquí con respecto a las funciones, si se pasan por valor.

### 4. Complete la palabra reservada de Python en el siguiente programa:

La palabra reservada faltante es **_elif_**

### 5. ¿Cuál de las opciones es equivalente al código de Python mostrado?

La opción equivalente es:

`print("Si") if 5 == 5 else print("No")`

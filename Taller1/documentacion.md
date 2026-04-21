# Transformaciones
## Transform 1: Json Input con Select Values transformation

### 1. Input (Entrada)
Para la primera transformación se utilizó el paso **JSON input**. 

* **Configuración técnica:** Se cargó el archivo fuente y se configuraron los campos en la pestaña *Fields*. 

![alt text](Imagenes/Transform1/image2.png)

### 2. Transform (Transformación)
Se utilizó el paso **Select values** para la limpieza y normalización de los metadatos.

* **Conversión de tipos:** Se accedió a la pestaña *Meta-data* para transformar el campo **CEDULA**. Originalmente detectado como numérico (Integer), se forzó a tipo **String** (Texto)

![alt text](Imagenes/Transform1/image3.png)

### 3. Output (Salida)
Como destino final se configuró el paso **JSON output**.

* **Consolidación:** Para evitar que el sistema generara archivos individuales por cada fila de datos, se configuró el parámetro **"Nr of rows in a block"** en **0**. Esto permite que todos los registros se agrupen en un único array dentro de un solo archivo de salida.

![alt text](Imagenes/Transform1/image4.png)
### 4. Resultado
La transformación toma un archivo JSON crudo, corrige las rutas de acceso, normaliza la identificación del estudiante (cédula) a texto y genera un archivo final consolidado y listo para ser utilizado en el Taller de Business Intelligence.

![alt text](Imagenes/Transform1/image.png)

## Transform 2: CSV con mapper transformation

### 1. Input (Entrada)
Para esta transformación se utilizó  el formato **CSV file input**.
![Carga del archivo csv](Imagenes/Transform2/Capture.PNG)
![Carga del archivo csv](Imagenes/Transform2/Capture2.PNG)
![Carga del archivo csv](Imagenes/Transform2/Capture1.PNG)

### 2. Transform (Transformación)
* **Conversión de datos**: En el campos de entrada ingresamos los valores que se encuentran dentro del archivo, y en el de salida con los valores que queremos reemplazar
![Transformación del archivo csv](Imagenes/Transform2/Capture3.PNG)
![Transformación del archivo csv](Imagenes/Transform2/Capture4.PNG)

### 3. Output (Salida)
* **Comparación de los resultados**:
![Carga del archivo csv](Imagenes/Transform2/Capture5.PNG)

## Transform 3: Generación de datos de prueba con identificador secuencial y valores aleatorios exportados a archivo txt

### 1. Input (Entrada)
Para esta transformación se utilizó  el formato **Generate Rows** este módulo genera filas artificiales que son necesarias para el flujo de la transformación.

![Carga del generaterows](Imagenes/Transform3/generaterows.png)


### 2. Transform (Transformación)
* **Add Sequence**: Se añade el modulo de add sequence para agregar una secuencia de datos con un identificador único incremental, donde el valor inicial es 1 y el incremento es 1.
* **Generate Random Value**: Este módulo genera valores aleatorios que se agregan a cada fila, Cada registro contiene un valor aleatorio diferente, útil para pruebas o simulaciones. El tipo de dato del valor aleatorio es interger.

![Carga del addsequence](Imagenes/Transform3/addsequence.png)
![Carga del generaterandomvalue](Imagenes/Transform3/generaterandomvalue.png)


### 3. Output (Salida)
* **Text File Output**: Este módulo exporta los datos procesados a un archivo en formato txt.
* **Configuración:**
- Nombre del archivo: `${Internal.Entry.Current.Directory}/output_datos`
- Extensión: `txt`
- Separador: `,`
- Encabezado: Activado

**Campos exportados:**
- `id`
- `dummy`
- `valor_random`
![Carga de la configuracion1](Imagenes/Transform3/output1.png)
![Carga de la configuracion2](Imagenes/Transform3/output2.png)
![Carga de la configuracion3](Imagenes/Transform3/output3.png)
![Carga de la transformacion](Imagenes/Transform3/transformacion.png)

* **Reaultados Obtenidos**:

![Carga del archivo txt](Imagenes/Transform3/resultado.png)

## Transform 4: Property Input con Add characters transformation

### 1. Input (Entrada)
Para esta transformación se utilizó el paso Property Input
* **Configuración técnica:** En la pestaña File se cargó el archivo de propiedades y en la pestaña Fields se utilizaron los nombres de las variables para mapear el contenido.
  
![alt text](Imagenes/Transform4/Imagen1.png)

# Transformaciones
## Transform 1: Procesamiento de Datos de Estudiantes

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

## Transform 2: Procesamiento de datos de Laptops

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
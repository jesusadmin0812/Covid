1. Debemos entrar en la carpeta Data Source y ejecutar los siguientes archivos:
        - covid_download.ipynb
        - Generar_tablas_ciudades_paises.ipynb
    
    Estos archivos nos permitirán generar los registros JSON de ciudades y países. 

    También descargaremos los registros de Covid en un archivo llamado "registroscovid.json" 

    (podemos especificar la fecha de descarga).

2. Una vez que tengamos los datos de origen, ejecutaremos el archivo Agregar_ciudad_pais.ipynb. 

    Este archivo agregará una ciudad a cada registro de Covid y luego buscará el país correspondiente para añadirlo. 

    Se generará un nuevo archivo en la carpeta "2.Json+ciudad+pais", el cual se llamará "df_con_ciudad_pais_registroscovid.json".

3. Ahora procederemos a ejecutar el archivo Agregar_fecha_exp_and_fecha_formato.ipynb, 

    que añadirá la fecha de procesamiento y generará tres nuevas columnas: una para el año, otra para el mes 

    y una última para el día. También se creará la columna "parámetro" para el control de registros, 

    permitiéndonos subir solo los que deseemos.


El resultado se guardará en formato Parquet en la ruta "3.parquet_historico", 

con subrutas diferentes según el país y luego por ciudad.


4. Utilizaremos el script "create_table_historico.sql" que se encuentra en la carpeta "Crear tabla SQL en MySQL" 

    para generar la tabla donde se guardarán los datos en MySQL.

5. Usaremos el script "Subir_datos_a_mysql.ipynb" para guardar los datos Parquet en el servidor MySQL.

6. Por último, podremos abrir el archivo "Powerbi_Covid.pbix" que está en la carpeta "PBI" para conectar MySQL 

    y los archivos de ciudades y países, obteniendo así los datos y mostrándolos en gráficos.

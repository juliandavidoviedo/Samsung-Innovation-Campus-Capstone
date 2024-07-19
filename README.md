![image](https://github.com/user-attachments/assets/81843cd4-cf8c-4ddd-8848-431e55d7eec9)

# Samsung-Innovation-Campus-Capstone
Capstone Project para Búsqueda Rápida de Convocatorias en SECOP II
**Introducción**
El propósito del proyecto es crear un sistema que permita buscar convocatorias relevantes utilizando palabras clave específicas. El sistema debe:

*Actualizar y almacenar datos desde una API.
*Preprocesar el texto para la búsqueda.
*Utilizar TF-IDF para la vectorización y cálculo de similitudes.
*Formatear y presentar los resultados de las búsquedas.
*Generar y descargar archivos CSV con los resultados.

Descripción de las Funciones y Módulos
1.	Instalación de Librerías:
o	!pip install pandas requests scikit-learn nltk: Instala las librerías necesarias para la ejecución del código.
2.	Importación de Librerías:
o	Importa las librerías requests, pandas, scikit-learn, nltk, re, os, y csv para la manipulación de datos, procesamiento de texto, y cálculos de similitud.
3.	Descarga de Datos NLTK:
o	nltk.download('stopwords') y nltk.download('wordnet'): Descarga las palabras vacías y el lematizador de WordNet necesarios para el preprocesamiento de texto.
4.	Actualización y Almacenamiento de Datos:
o	update_data(): Función para actualizar y almacenar los datos desde la API de Secop II en un archivo CSV.
5.	Verificación y Carga de Datos:
o	Verifica si el archivo CSV existe. Si no, llama a update_data() para crear el archivo. Luego, carga los datos en un DataFrame de pandas.
6.	Preprocesamiento de Texto:
o	preprocess_text(text): Función que convierte el texto a minúsculas, elimina caracteres no alfanuméricos y palabras vacías, y lematiza los tokens.
7.	Preprocesamiento de Descripciones:
o	Verifica si las columnas necesarias existen en el DataFrame. Si existen, combina y preprocesa las columnas nombre_del_procedimiento y descripci_n_del_procedimiento.
8.	Vectorización TF-IDF:
o	Crea un vectorizador TF-IDF y ajusta el modelo a los datos preprocesados.
9.	Búsqueda de Convocatorias:
o	search_tenders(query): Busca convocatorias relevantes para una consulta dada utilizando la similitud coseno entre el vector de consulta y los vectores de las descripciones preprocesadas.
10.	Formateo de Información:
o	format_tender_info(results): Formatea la información de las convocatorias encontradas en una lista de cadenas formateadas.
11.	Generación de CSV:
o	generate_csv(formatted_results, filename): Genera un archivo CSV con los resultados formateados de la búsqueda.
12.	Simulación de Descarga de CSV:
o	download_csv(filename): Simula la descarga de un archivo CSV mostrando un enlace de descarga placeholder.
13.	Función Principal:
o	main(): Verifica si los datos existen, de lo contrario, los actualiza. Carga los datos preprocesados, obtiene palabras clave del usuario, realiza la búsqueda, formatea los resultados, y genera un archivo CSV con los resultados.
Ejecución del Código
•	El código se ejecuta al llamar a la función main() cuando el archivo es ejecutado directamente.

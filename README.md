# Web Scraping en Tauret Computadores con BeautifulSoup

## Descripción del proyecto

Este proyecto se desarrolló con el propósito de aplicar técnicas de extracción automatizada de datos (*Web Scraping*) sobre un portal real de comercio electrónico. A través del análisis sintáctico del documento HTML, se captura y estructura información comercial, de inventario y de especificaciones técnicas del artículo **Tarjeta Gráfica ASUS TUF Gaming GeForce RTX 5090 32GB GDDR7** comercializado en la tienda colombiana **Tauret Computadores**.

El trabajo parte de un script desarrollado en Python, organizado en un notebook de Jupyter, que transforma contenido web no estructurado en un registro normalizado en formato JSON listo para procesos de monitoreo de precios y análisis de mercado.

## Objetivo

Implementar una solución automatizada de Web Scraping en Python utilizando las librerías **BeautifulSoup4** y **Requests** para extraer, limpiar y estructurar los datos comerciales, de disponibilidad (`Stock`), códigos de catálogo (`EAN`, `SKU`, `P/N`) y especificaciones técnicas de hardware de alto rendimiento en Tauret Computadores.

## Tecnologías utilizadas

Para el desarrollo del proyecto se utilizaron las siguientes herramientas:

- **Python 3:** lenguaje de programación principal utilizado para el scraper.
- **Google Colab y Jupyter Notebook:** entorno de ejecución y documentación del código.
- **Git y GitHub:** control de versiones y alojamiento del repositorio[cite: 6, 8].
- **Requests:** gestión de peticiones HTTP `GET` y configuración de cabeceras (`User-Agent`).
- **BeautifulSoup4 (`bs4`):** análisis sintáctico (*parsing*) y recorrido del árbol DOM HTML.
- **Re (Expresiones Regulares):** filtrado de precisión y conversión de tipos de datos numéricos y alfanuméricos.
- **JSON y Datetime:** serialización de datos en formato estructurado UTF-8 y registro de marca temporal de extracción[cite: 1, 2].

## Estructura del proyecto

Los archivos principales del repositorio son[cite: 4, 8]:

- `Garces_Sebastian_Analizando_EA1.ipynb`: notebook principal con la implementación del scraper, limpieza de datos y exportación[cite: 2, 8].
- `resultado_rtx5090_tauret.json`: archivo de salida generado con los atributos reales extraídos del producto[cite: 2, 8].
- `requirements.txt`: listado de dependencias necesarias para ejecutar el proyecto[cite: 4, 8].

## Metodología y desarrollo

El flujo de extracción implementado se divide en cuatro etapas principales[cite: 1, 2]:

1. **Inspección del DOM y petición HTTP:** envío de una solicitud `GET` al servidor de Tauret Computadores simulando un navegador legítimo mediante cabeceras personalizadas (`headers`)[cite: 1, 2].
2. **Parsing con BeautifulSoup:** instanciación del objeto `BeautifulSoup(respuesta.text, "html.parser")` para localizar el título principal (`<h1>`) y extraer el texto estructurado del árbol DOM[cite: 1, 2].
3. **Limpieza y tipado con Regex:** extracción de variables clave convirtiendo el precio (`COP 19.999.000`) y las existencias (`5 unidades disponibles`) a valores numéricos enteros, además de aislar los identificadores universales (`EAN`, `SKU`, `P/N`)[cite: 1, 2].
4. **Persistencia en JSON:** organización jerárquica de los datos en cuatro categorías (`informacion_comercial`, `identificadores_catalogo`, `dimensiones_empaque` y `especificaciones_tecnicas`) y almacenamiento en disco[cite: 1, 2].

## Funciones principales del código

| Función / Componente | Descripción |
|---|---|
| `extraer_producto_tauret_bs4(url)` | Función principal que gestiona la petición HTTP, el análisis con BeautifulSoup y el retorno del diccionario estructurado[cite: 1, 2]. |
| `buscar_patron(expresion, texto)` | Función auxiliar basada en expresiones regulares (`re.search`) para aislar atributos específicos dentro del texto del DOM[cite: 1, 2]. |
| `json.dump()` | Exporta el diccionario final al archivo `resultado_rtx5090_tauret.json` con codificación UTF-8[cite: 1, 2]. |

## Ejecución del proyecto

### Desde Google Colab

1. Abrir el archivo `Garces_Sebastian_Analizando_EA1.ipynb` en Google Colab[cite: 2, 8].
2. Ejecutar la celda de código para instalar las dependencias, realizar el scraping en tiempo real y generar el archivo `.json`[cite: 2].

### Desde entorno local (Visual Studio Code / Terminal)
## Autor
Sebastián Garcés Cadavid

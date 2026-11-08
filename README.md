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
- **Git y GitHub:** control de versiones y alojamiento del repositorio.
- **Requests:** gestión de peticiones HTTP `GET` y configuración de cabeceras (`User-Agent`).
- **BeautifulSoup4 (`bs4`):** análisis sintáctico (*parsing*) y recorrido del árbol DOM HTML.
- **Re (Expresiones Regulares):** filtrado de precisión y conversión de tipos de datos numéricos y alfanuméricos.
- **JSON y Datetime:** serialización de datos en formato estructurado UTF-8 y registro de marca temporal de extracción.

## Estructura del proyecto

Los archivos principales del repositorio son:

- `Garces_Sebastian_Analizando_EA1.ipynb`: notebook principal con la implementación del scraper, limpieza de datos y exportación.
- `resultado_rtx5090_tauret.json`: archivo de salida generado con los atributos reales extraídos del producto.


## Metodología y desarrollo

El flujo de extracción implementado se divide en cuatro etapas principales:

1. **Inspección del DOM y petición HTTP:** envío de una solicitud `GET` al servidor de Tauret Computadores simulando un navegador legítimo mediante cabeceras personalizadas (`headers`).
2. **Parsing con BeautifulSoup:** instanciación del objeto `BeautifulSoup(respuesta.text, "html.parser")` para localizar el título principal (`<h1>`) y extraer el texto estructurado del árbol DOM.
3. **Limpieza y tipado con Regex:** extracción de variables clave convirtiendo el precio (`COP 19.999.000`) y las existencias (`5 unidades disponibles`) a valores numéricos enteros, además de aislar los identificadores universales (`EAN`, `SKU`, `P/N`).
4. **Persistencia en JSON:** organización jerárquica de los datos en cuatro categorías (`informacion_comercial`, `identificadores_catalogo`, `dimensiones_empaque` y `especificaciones_tecnicas`) y almacenamiento en disco.

## Funciones principales del código

| Función / Componente | Descripción |
|---|---|
| `extraer_producto_tauret_bs4(url)` | Función principal que gestiona la petición HTTP, el análisis con BeautifulSoup y el retorno del diccionario estructurado. |
| `buscar_patron(expresion, texto)` | Función auxiliar basada en expresiones regulares (`re.search`) para aislar atributos específicos dentro del texto del DOM. |
| `json.dump()` | Exporta el diccionario final al archivo `resultado_rtx5090_tauret.json` con codificación UTF-8. |

## Ejecución del proyecto

### Desde Google Colab

1. Abrir el archivo `Garces_Sebastian_Analizando_EA1.ipynb` en Google Colab.
2. Ejecutar la celda de código para instalar las dependencias, realizar el scraping en tiempo real y generar el archivo `.json`.

### Desde entorno local (Visual Studio Code / Terminal)

1. Clonar el repositorio:
git clone [https://github.com/sebasgarcesc/Garces_Sebastian_Analizando_EA1.git](https://github.com/sebasgarcesc/Garces_Sebastian_Analizando_EA1.git).

## Autor
Sebastián Garcés Cadavid








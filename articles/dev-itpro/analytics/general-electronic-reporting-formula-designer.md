---
title: "Diseñador de fórmulas en los informes electrónicos"
description: "Este tema explica cómo usar el diseñador de fórmula en Informes electrónicos (ER). Cuando diseña un formato para un documento electrónico específico en ER, puede usar fórmulas del tipo de Microsoft Excel para que la transformación de datos cumpla los requisitos para el cumplimiento y el formato de ese documento. Se admiten diversos tipos de funciones: texto, fecha y hora, lógica matemática, información, conversión de tipo de datos y otras (funciones específicas de dominio empresarial)."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 37c860599ad555846d11711e9f3cfb29c599131e
ms.openlocfilehash: 7704b0545f4264be1f844ed6ad9e4b44df0c4ef8
ms.contentlocale: es-es
ms.lasthandoff: 10/05/2017

---

# <a name="formula-designer-in-electronic-reporting"></a>Diseñador de fórmulas en los informes electrónicos

[!include[banner](../includes/banner.md)]


Este tema explica cómo usar el diseñador de fórmula en Informes electrónicos (ER). Cuando diseña un formato para un documento electrónico específico en ER, puede usar fórmulas del tipo de Microsoft Excel para que la transformación de datos cumpla los requisitos para el cumplimiento y el formato de ese documento. Se admiten diversos tipos de funciones: texto, fecha y hora, lógica matemática, información, conversión de tipo de datos y otras (funciones específicas de dominio empresarial).

<a name="formula-designer-overview"></a>Visión general del diseñador de fórmulas
-------------------------

Los informes electrónicos admiten el diseñador de fórmulas. Por tanto, en el momento del diseño, puede configurar las expresiones que se pueden usar para las siguientes tareas en tiempo de ejecución:

-   Transformar datos recibidos de una base de datos de Microsoft Dynamics 365 for Finance and Operations y que se deben rellenar en un modelo de datos de ER que se ha diseñado para ser un origen de datos para formatos de ER (filtrado, agrupación, conversión de tipos de datos, etc.).
-   Formatear datos que se deben enviar a un documento electrónico de generación de acuerdo con el diseño y las condiciones del formato específico de ER (de acuerdo con el idioma o la cultura solicitados, codificación, etc.).
-   Controlar el proceso de generación de documentos electrónicos (activando o desactivando la salida de elementos específicos del formato en función del procesamiento de datos, la interrupción de la creación del documento, el lanzamiento de mensajes para usuarios finales, etc.).

La página del diseñador de fórmulas se puede abrir si realiza alguna de las siguientes acciones:

-   Enlazar artículos del origen de datos a los componentes del modelo de datos.
-   Enlazar artículos del origen de datos a componentes de formato.
-   Completar el mantenimiento de campos calculados como parte de orígenes de datos.
-   Definir las condiciones de visibilidad para los parámetros de entrada del usuario.
-   Diseñar las transformaciones de un formato.
-   Definir las condiciones de habilitación para los componentes del formato.
-   Definir los nombres de archivo para los componentes de ARCHIVO de formato.
-   Definir las condiciones para las validaciones de control de proceso.
-   Definir el texto de mensaje para las validaciones de control de proceso.

## <a name="designing-er-formulas"></a>Diseño de las fórmulas de ER
### <a name="data-binding"></a>Vinculación de datos

El diseñador de fórmula de ER se puede usar para definir una expresión que transforma datos que se reciben de orígenes de datos, para que se puedan rellenar los datos en el consumidor de datos en tiempo de ejecución:

-   Desde los orígenes de datos de Finance and Operations y los parámetros de tiempo de ejecución a un modelo de datos de ER.
-   Desde un modelo de datos de ER a un formato de ER.
-   Desde los orígenes de datos de Finance and Operations y los parámetros de tiempo de ejecución a un formato de ER.

En la ilustración siguiente se muestra el diseño de una expresión de este tipo. En este ejemplo, la expresión devuelve el valor del campo **Intrastat.AmountMST** de la tabla **Intrastat** de Finance and Operations después de que el valor se haya redondeado a dos posiciones decimales. [![picture-expression-binding](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg) La siguiente ilustración muestra cómo una expresión de este tipo se puede usar. En este ejemplo, el resultado de la expresión diseñada se rellena en el componente **Transaction.InvoicedAmount** del modelo de datos **Modelo de notificación tributaria**. [![picture-expression-binding2](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg) En tiempo de ejecución, la fórmula diseñada, **ROUND (Intrastat.AmountMST, 2)**, redondeará el valor del campo **AmountMST** para cada registro de la tabla **Intrastat** a dos posiciones decimales y rellenará el valor redondeado al componente **Transaction.InvoicedAmount** del modelo de datos de la **Notificación tributaria**.

### <a name="data-formatting"></a>Formato de datos

El diseñador de fórmula de ER se puede usar para definir una expresión que formatea datos que se reciben de orígenes de datos, para que se puedan enviar como parte de la generación de un documento electrónico. Si tiene formato que se debe aplicar como una regla típica que se debe volver a usar para un formato, puede presentar ese formato una vez en la configuración del formato como una transformación con nombre que tenga una expresión de formato. Esta transformación con nombre se puede vincular a continuación a varios componentes de formato para los que se debe formatear el resultado de acuerdo con la expresión creada. En la ilustración siguiente se muestra el diseño de una transformación de este tipo. En este ejemplo, la transformación **TrimmedString** obtiene datos entrantes del tipo de datos **Secuencia** y trunca los espacios de principio y final cuando devuelve el valor de la cadena. [![picture-transformation-design](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg) En la ilustración siguiente se muestra cómo usar una transformación de este tipo. En este ejemplo, varios componentes de formato que envían texto como salida al documento electrónico de generación en tiempo de ejecución hacen referencia a la transformación **TrimmedString** por nombre. [![picture-transformation-usage](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg) Cuando los componentes del formato hacen referencia a la transformación **TrimmedString** (por ejemplo, el componente **partyName** de la ilustración anterior) se envía texto como resultado al documento que lo genera. El texto no incluye espacios principales y finales. Si tiene un formato que se debe aplicar de forma individual, puede introducir ese formato como una expresión individual de una vinculación de un componente de formato concreto. En la ilustración siguiente se muestra una expresión de este tipo. En este ejemplo, el componente del formato **partyType** se vincula al origen de datos mediante una expresión que convierte los datos entrantes del campo **Model.Company.RegistrationType** del origen de datos en texto en mayúsculas y envía ese texto como salida al documento electrónico. [![picture-binding-with-formula](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Control de flujo de proceso

El diseñador de fórmulas de ER se puede usar para definir las expresiones que controlan el flujo de proceso de la generación de documentos. El usuario puede:

-   Definir las condiciones que determinan cuándo un proceso de creación de documento se debe detener.
-   Especifique expresiones que creen mensajes para el usuario final acerca de los procesos detenidos o lancen mensajes de registro de ejecución acerca de continuar con el proceso de la generación del informe.
-   Especifique los nombres de archivo de los documentos de generación y las condiciones de control de su creación.

Cada regla de control de flujo de proceso está diseñada como validación individual. En la ilustración siguiente se muestra una validación de este tipo. Esta es una explicación de la configuración de este ejemplo:

-   La validación se evalúa cuando se crea el nodo **INSTAT** en el archivo XML de generación.
-   Si la lista de transacciones está vacía, la validación detiene el proceso de ejecución y devuelve **FALSE**.
-   La validación devuelve un mensaje de error que incluye el texto de la etiqueta SYS70894 en el idioma preferido del usuario.

[![picture-validation](./media/picture-validation.jpg)](./media/picture-validation.jpg) El diseñador de fórmulas de ER también se puede usar para especificar un nombre de archivo para un documento electrónico de generación y para controlar el proceso de creación del archivo. En la ilustración siguiente se muestra el diseño de un control de flujo de proceso de este tipo. Esta es una explicación de la configuración de este ejemplo:

-   La lista de registros del origen de datos **modelo. Intrastat** se dividida en lotes, cada uno de los cuales contiene hasta 1000 registros.
-   La salida crea un archivo zip que contiene un archivo en formato XML para cada lote que se ha creado.
-   Una expresión devuelve un nombre de archivo para generar documentos electrónicos concatenando el nombre de archivo y la extensión de archivo. Para el segundo lote y todos los lotes posteriores, el nombre de archivo contiene el id. de lote como sufijo.
-   Una expresión habilita (devolviendo **TRUE**) el proceso de creación de archivos para lotes que contengan al menos un registro.

[![picture-file-control](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Sintaxis básica

Las expresiones de ER pueden contener todo los elementos siguientes o cualquiera de ellos:

-   Constantes
-   Operadores
-   Referencias
-   Rutas
-   Funciones

#### <a name="constants"></a>Constantes

Puede usar constantes de texto y numéricas (valores que no se calculan) al diseñar expresiones. Por ejemplo, la expresión **VALUE ("100") + 20**usa la constante numérica 20 y la constante de cadena “100” y devuelve el valor numérico **120**. El diseñador de fórmulas de ER admite secuencias de escape, lo que significa que puede especificar esa parte de la cadena de expresión que se debe gestionar de forma diferente. Por ejemplo, la expresión **"Leo Tolstoy ""Guerra y paz"" Volumen 1"** devuelve la cadena de texto **Leo Tolstoy "Guerra y paz" Volumen 1**.

#### <a name="operators"></a>Operadores

La tabla siguiente muestra los operadores aritméticos que puede usar para realizar operaciones matemáticas básicas, como suma, resta, división y multiplicación.

| Operador | Significado              | Ejemplo |
|----------|----------------------|---------|
| +        | Adición             | 1+2     |
| -        | Resta Negación | 5-2 -1  |
| \*       | Multiplicación       | 7\*8    |
| /        | División             | 9/3     |

La tabla siguiente muestra los operadores de comparación que se admiten y que puede usar para comparar dos valores.

| Operador | Significado                  | Ejemplo    |
|----------|--------------------------|------------|
| =        | Igual                    | X=Y        |
| &gt;     | Mayor que             | X&gt;Y     |
| &lt;     | Menor que                | X&lt;Y     |
| &gt;=    | Superior a o igual a | X&gt;=Y    |
| &lt;=    | Inferior a o igual a    | X&lt;=Y    |
| &lt;&gt; | No igual que             | X&lt;&gt;Y |

Además, puede usar una Y comercial (&) como operador de concatenación de texto para unir, o concatenar, una o más cadenas de texto en una pieza única de texto.

| Operador | Significado     | Ejemplo                                        |
|----------|-------------|------------------------------------------------|
| &        | Concatenar | "No hay nada que imprimir" & ": " & "No se encuentran registros" |

#### <a name="operator-precedence"></a>Prevalencia del operador

El orden en el que se evalúan las partes de una expresión compuesta es importante. Por ejemplo, el resultado de la expresión**1 + 4 / 2** varía en función de si la operación de adición o la operación de división se realiza primero. Puede usar paréntesis para definir explícitamente la manera en que se evalúa una expresión. Por ejemplo, para indicar que la operación de adición debe llevarse a cabo primero, puede modificar la expresión precedente a **(1 + 4)/2**. Si el orden de las operaciones que se deben realizar en una expresión no se define explícitamente, el pedido se basa en la prioridad predeterminada que se asigna a los operadores admitidos. En las siguientes tablas se muestran los operadores y prioridad que se asigna a cada uno. Los operadores que tienen mayor prioridad (por ejemplo, 7) se evalúan antes que los operadores que tienen prioridad más baja (por ejemplo, 1).

| Precedencia | Operadores      | Sintaxis                                                   |
|------------|----------------|----------------------------------------------------------|
| 7          | Agrupación       | ( … )                                                    |
| 6          | Acceso a miembros  | … . …                                                    |
| 5          | Llamada de función  | … ( … )                                                  |
| 4          | Multiplicativa | … \* … … / …                                             |
| 3          | Aditivo       | … + … … - …                                              |
| 2          | Comparación     | … &lt; … … &lt;= … … =&gt; … … &gt; … … = … … &lt;&gt; … |
| 1          | Separación     | … , …                                                    |

Los operadores de la misma línea tienen igual prioridad. Si una expresión incluye más de uno de estos operadores, la expresión se evalúa de izquierda a derecha. Por ejemplo, la expresión **1 + 6 / 2 \* 3 &gt; 5** devuelve **true**. Se recomienda usar paréntesis para indicar explícitamente el pedido deseado de evaluación para expresiones, para facilitar la lectura y el mantenimiento de las expresiones.

#### <a name="references"></a>Referencias

Todos los orígenes de datos del componente del ER actual (un modelo o un formato) que están disponibles durante el diseño de una expresión se pueden usar como referencias con nombre. Por ejemplo, el modelo de datos actual de ER contiene el origen de datos **ReportingDate**, que devuelve el valor del tipo de datos **DATETIME**. Para dar un formato correcto a ese valor en el documento de generación, puede hacer referencia al origen de datos en la expresión del modo siguiente: **DATETIMEFORMAT (ReportingDate, “dd-MM-aaaa”)** Todos los caracteres del nombre del origen de datos de referencia que no representan una letra del alfabeto, deben empezar con comillas simples ('). Si el nombre de un origen de datos de referencia incluye al menos un símbolo que no representa una letra del alfabeto (por ejemplo, signos de puntuación o cualquier otro símbolo escrito) el nombre debe estar entre comillas simples. A continuación se incluyen algunos ejemplos:

-   Se debe hacer referencia al origen de datos **Hora y día hoy** en una expresión de ER de la siguiente manera: **'Hora y día hoy'**
-   Debe hacerse referencia al método **name()** del origen de datos **Clientes** en una expresión de ER como se indica a continuación: **Customers.'name()'**

Tenga en cuenta que la siguiente sintaxis se utiliza para llamar a métodos de los orígenes de datos de Dynamics 365 for Operations con parámetros:

- Se debe hacer referencia al método isLanguageRTL del origen de datos del sistema con un parámetro EN-US del tipo de datos de la cadena se en una expresión de ER modo sigue: System.’isLanguageRTL’(“EN-US”).
- Las comillas no son obligatorias cuando un nombre del método solo contiene símbolos alfanuméricos. Son obligatorias para un método de una tabla cuando el nombre incluye corchetes.

Cuando se agrega el origen de datos del sistema a la asignación de ER que hace referencia a Dynamics 365 for Operations para la clase de aplicación Global, la expresión devuelve el valor booleano FALSE. La expresión modificada, System.’ isLanguageRTL’(“AR”) devuelve el valor booleano TRUE.

Tenga en cuenta que pasar a estos parámetros de métodos se puede definir con las siguientes limitaciones:

- Únicamente las constantes se pueden pasar a estos métodos y su valor se define en tiempo de diseño.
- Solo se admiten los tipos de datos primitivos (básicos) para tales parámetros (entero, real, booleano, cadena, etc.).

#### <a name="path"></a>Ruta

Cuando una expresión hace referencia a un origen de datos estructurado, puede usar la definición de ruta para seleccionar un elemento primitivo específico de ese origen de datos. Un carácter de punto (.) se usa para separar elementos individuales de un origen de datos estructurado. Por ejemplo, el modelo de datos actual de ER contiene el origen de datos **InvoiceTransactions** que devuelve una lista de registros. La estructura de registros **InvoiceTransactions** contiene los campos **AmountDebit** y **AmountCredit** que devuelven valores numéricos. Por tanto, puede diseñar la siguiente expresión para calcular el importe facturado: **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**

#### <a name="functions"></a>Funciones

La sección siguiente describe las funciones que se pueden usar en expresiones de ER. Todos los orígenes de datos del contexto de la expresión (el modelo de datos de ER o formato actual de ER) así como las constantes pueden usarse como parámetros de funciones de llamada de acuerdo con la lista de argumentos de la función de llamada. Por ejemplo, el modelo de datos actual de ER contiene el origen de datos **InvoiceTransactions** que devuelve una lista de registros. La estructura de registros **InvoiceTransactions** contiene los campos **AmountDebit** y **AmountCredit** que devuelven valores numéricos. Por tanto, para calcular el importe facturado, puede diseñar la siguiente expresión que usa la función de redondeo incorporada de ER: **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**

## <a name="supported-functions"></a>Funciones no permitidas.
Las siguientes tablas describen las funciones de manipulación de datos que puede usar para diseñar modelos de datos de ER e informes de ER. La lista de funciones no es fija y se puede ampliar por los desarrolladores. Para ver la lista de funciones que puede usar, acceda al panel de funciones del diseñador de fórmulas de ER.

### <a name="date-and-time-functions"></a>Funciones de fecha y de tiempo

| Función                                   | Descripción                                                                                                                                                                                                                                                                                                                                                      | Ejemplo                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ADDDAYS (fecha y hora, días)                   | Agregar el número específico de días al valor especificado de fecha y hora.                                                                                                                                                                                                                                                                                                | **ADDDAYS (NOW(), 7)** devuelve la fecha y la hora siete días en el futuro.                                                                                                                                                                                                                            |
| DATETODATETIME (fecha)                      | Convertir el valor de la fecha especificada en un valor de fecha y hora.                                                                                                                                                                                                                                                                                                            | **DATETODATETIME (CompInfo. 'getCurrentDate()')** devuelve la fecha de la sesión actual de Finance and Operations, 12/24/2015, como **12/24/2015 12:00:00 AM**. En este ejemplo, **CompInfo** es un origen de datos de ER del tipo **Finance and Operations/Tabla** que hace referencia a la tabla CompanyInfo. |
| NOW ()                                     | Devolver la fecha y hora actuales del servidor de aplicaciones de Finance and Operations como valor de fecha y hora.                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                       |
| TODAY ()                                   | Devolver la fecha y hora actuales del servidor de aplicaciones de Finance and Operations como valor de fecha-                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                       |
| NULLDATE ()                                | Devolver un valor de fecha **nulo**.                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                       |
| NULLDATETIME ()                            | Devolver un valor de fecha y hora **nulo**.                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                       |
| DATETIMEFORMAT (fecha y hora, formato)          | Convertir el valor de fecha y hora especificado a una cadena en el formato especificado. (Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).)                                                                        | **DATETIMEFORMAT (NOW(), "dd-MM-aaaa”)** devuelve la fecha del servidor actual de Finance and Operations, 12/24/2015, como **“24-12-2015”**, según el formato personalizado especificado.                                                                                                          |
| DATETIMEFORMAT (fecha y hora, formato, cultura) | Convertir el valor de fecha y hora especificado a una cadena en el formato y [cultura](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) especificados. (Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (AHORA(), "d", "de")** devuelve la fecha actual del servidor de aplicaciones de Finance and Operations, 12/24/2015, como **“24.12.2015"**, según la cultura alemana seleccionada.                                                                                                             |
| SESSIONTODAY ()                            | Devuelve la fecha y hora actual de la sesión de Finance and Operations como valor de fecha.                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                       |
| SESSIONNOW ()                              | Devuelve la fecha y hora actual de la sesión de Finance and Operations como valor de fecha y hora.                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                       |
| DATEFORMAT (fecha, formato)                  | Devuelve la representación de cadena de la fecha con el formato especificado.                                                                                                                                                                                                                                                                                                    | **DATEFORMAT (SESSIONTODAY (), "dd-MM-aaaa")** devuelve la fecha actual de la sesión de Finance and Operations 12/24/2015 como “**24-12-2015**” según el formato personalizado especificado.                                                                                                                      |
| DATEFORMAT (fecha, formato, cultura)         | Convertir el valor de fecha especificado en una cadena en el formato y cultura [especificados](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)).     | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** devuelve la fecha de la sesión de Finance and Operations, 12/24/2015, como **“24.12.2015”**, según la cultura alemana seleccionada.                                                                                                                       |
| DAYOFYEAR (fecha)              | Devuelve una representación de número entero de los días entre el 1 de enero y la fecha especificada.       | **DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-aaaa"))** devuelve **61**. **DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-aaaa"))** devuelve **1**. 
                                                                                                                      |

**Funciones de conversión de datos**

| Función                                   | Descripción                                                                                                                                                                                                                                                                                                                                                      | Ejemplo                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DATETODATETIME (fecha)                 | Convertir el valor de la fecha especificada en un valor de fecha y hora.           | **DATETODATETIME (CompInfo. 'getCurrentDate()')** devuelve la fecha de la sesión actual de Finance and Operations, 12/24/2015, como **12/24/2015 12:00:00 AM**. En este ejemplo, **CompInfo** es un origen de datos de ER del tipo **Finance and Operations/Tabla** que hace referencia a la tabla **CompanyInfo**.                                                                                                                       |
| DATEVALUE (cadena, formato)              | Devuelve la representación de cadena de la fecha con el formato especificado.       | **DATEVALUE ("21-Dic-2016", "dd-MMM-aaaa")** devuelve la fecha 12/21/2016 de acuerdo con un formato especificado y la cultura predeterminada **EN-US** de la aplicación.                                                                                                                       |
| DATEVALUE (cadena, formato, cultura)              | Devuelve la representación de fecha de la cadena con el formato y la cultura especificados.       | **DATEVALUE ("21-Gen-2016", "dd-MMM-aaaa", “IT”)** devuelve la fecha 01/21/2016 según un formato personalizado y cultura especificada. Una excepción se producirá para la llamada de esta función, **DATEVALUE ("21-Gen-2016", "dd-MMM-aaaa", “EN-US”)** que indica que una cadena determinada no se reconoce como fecha válida.                                                                                                                       |
| DATETIMEVALUE (cadena, formato)              | Devuelve la representación de fecha y hora de la cadena con el formato especificado.       | **DATETIMEVALUE ("21-Dic-2016 02:55:00", "dd-MMM-aaaa hh:mm:ss")** devuelve las 2:55:00 a.m. del 21 de diciembre de 2016 según un formato personalizado y la cultura predeterminada **EN-US** de la aplicación.                                                                                                                       |
| DATETIMEVALUE (cadena, formato, cultura)              | Devuelve la representación de fecha y hora de la cadena con el formato y la cultura especificados.       | **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-aaaa hh:mm:ss", “IT”)** devuelve las 2:55:00 a.m. del 21 de diciembre de 2016 según un formato y la cultura predeterminada. Una excepción se producirá para la llamada de esta función, **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-aaaa hh:mm:ss", “EN-US”)** que indica que una cadena determinada no se reconoce como fecha válida.                                                                                                                       |
### <a name="list-functions"></a>Funciones de lista

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Función</th>
<th>Descripción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SPLIT (entrada, longitud)</td>
<td>Dividir la cadena de entrada especificada en subcadenas y cada una de las cuales tiene la duración especificada. Devolver el resultado como nueva lista.</td>
<td><strong>SPLIT (&quot;abcd&quot;, 3)</strong> devuelve una nueva lista que consta de dos registros que tienen un campo <strong>STRING</strong>. El campo del primer registro contiene el texto <strong>&quot;abc&quot;</strong> y el campo del segundo registro contiene el texto <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr class="even">
<td>SPLITLIST (lista, número)</td>
<td>Dividir la lista especificada en lotes que contenga cada uno el número de registros especificado. Devolver el resultado como nueva lista de lotes que contenga los elementos siguientes:
<ul>
<li>Lotes como listas regulares (componente <strong>Valor</strong>)</li>
<li>El número de lote actual (componente <strong>BatchNumber</strong>)</li>
</ul></td>
<td>En el siguiente ejemplo, se crea el origen de datos <strong>Líneas</strong> como una lista de tres registros, que se divide en lotes, y que cada uno de los cuales contiene hasta dos registros. 
<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a> 

Esto muestra el diseño del formato donde se crean enlaces de la fuente de datos a las <strong>Líneas</strong> para generar la salida en formato XML que presenta nodos individuales para cada lote y los registros que incluye. 
<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a> 

Este es el resultado de la ejecución del formato diseñado. 
<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LIST (registro 1 [, registro 2, ...])</td>
<td>Devolver una nueva lista creada a partir de argumentos especificados.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> devuelve un registro vacío, en el que la lista de campos contiene todos los campos de las listas de registros <strong>MainData</strong> y <strong>OtherData</strong>.</td>
</tr>
<tr class="even">
<td>LISTJOIN (lista 1, lista 2, ...)</td>
<td>Devolver una nueva lista combinada que se crea a partir de argumentos especificados.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> devuelve la lista de seis registros, donde un campo del tipo de datos <strong>STRING</strong> contiene letras individuales.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (lista)</td>
<td>Devolver <strong>TRUE</strong> si la lista especificada no contiene elementos. En caso contrario, devuelva <strong>FALSE</strong>.</td>
<td></td>
</tr>
<tr class="even">
<td>EMPTYLIST (lista)</td>
<td>Devolver una lista vacía mediante la lista especificada como origen para la estructura de la lista.</td>
<td><strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> devuelve una nueva lista vacía que tiene la misma estructura que la lista que se devuelve por la función <strong>SPLIT</strong>.</td>
</tr>
<tr class="odd">
<td>FIRST (lista)</td>
<td>Devolver el primer registro de la lista especificada, si dicho registro no está vacío. En caso contrario, genera una excepción.</td>
<td></td>
</tr>
<tr class="even">
<td>FIRSTORNULL (lista)</td>
<td>Devolver el primer registro de la lista especificada, si dicho registro no está vacío. En caso contrario, devuelve un registro <strong>nulo</strong>.</td>
<td></td>
</tr>
<tr class="odd">
<td>LISTOFFIRSTITEM (lista)</td>
<td>Devuelve una lista que contiene solo el primer elemento de la lista especificada.</td>
<td></td>
</tr>
<tr class="even">
<td>ALLITEMS (ruta)</td>
<td>Devuelve una lista nueva aplanada que representa todos los elementos correspondientes a la ruta de acceso especificada. La ruta se debe definir como ruta válida del origen de datos a un elemento de origen de datos del tipo de datos de la lista de registro. La ruta de los elementos de datos de cadena, fecha, etc. debería activar un error en el tiempo de diseño del generador de expresiones de ER.</td>
<td>Si especifica <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> como origen de datos (DS), <strong>COUNT( ALLITEMS (DS.Value))</strong> devuelve <strong>3</strong>.</td>
</tr>
<tr class="odd">
<td>ORDERBY (lista [, expresión 1, expresión 2, …])</td>
<td>Devolver la lista especificada, que se clasifica según los argumentos especificados que se pueden definir como expresiones.</td>
<td>Cuando <strong>Proveedor</strong> se configura como origen de datos de ER que hace referencia a la tabla VendTable, <strong>ORDERBY (Vendors, Vendors.'name()')</strong> devuelva la lista de proveedores que se clasifica por nombre en orden ascendente.</td>
</tr>
<tr class="even">
<td>REVERSE (lista)</td>
<td>Devolver la lista especificada en orden de clasificación invertido.</td>
<td>Cuando <strong>Proveedor </strong>se configura como origen de datos de ER que hace referencia a la tabla VendTable, <strong>REVERSE (ORDERBY (Vendors, Vendors.'name()')) )</strong> devuelva la lista de proveedores que se clasifica por nombre en orden descendente.</td>
</tr>
<tr class="odd">
<td>WHERE (lista, condición)</td>
<td>Devolver la lista especificada, que se filtra según la condición determinada. A diferencia de la función de <strong>FILTRO</strong>, la condición especificada se aplica a la lista de la memoria.</td>
<td>Cuando <strong>Proveedor</strong> se configura como origen de datos de ER que hace referencia a la tabla VendTable, <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> devuelve la lista de proveedores que pertenece al grupo de proveedores 40.</td>
</tr>
<tr class="even">
<td>ENUMERATE (lista)</td>
<td>Devolver una nueva lista que consta de los registros enumerados de la lista especificada y que expone los siguientes elementos:
<ul>
<li>Registros especificados como listas regulares (componente <strong>Valor</strong>)</li>
<li>El índice de registros actual (componente <strong>Número</strong>)</li>
</ul></td>
<td>En el ejemplo siguiente, el origen de datos <strong>Enumerado</strong> se crea como una lista enumerada de registros de proveedor desde el origen de los datos <strong>Proveedores</strong> que hace referencia a la tabla <strong>VendTable</strong>. 
<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a> 

Este es el formato donde se crean los enlaces de datos para generar resultados en formato XML, que presenta proveedores individuales como nodos enumerados. 
<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a> 

Este es el resultado de la ejecución del formato diseñado. 
<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>COUNT (lista)</td>
<td>Devolver el número de registros de la lista especificada, si la lista no está vacía. En caso contrario, devuelva <strong>0</strong> (cero).</td>
<td><strong>COUNT (SPLIT(&quot;abcd&quot; , 3))</strong> devuelve <strong>2</strong>, porque la función <strong>SPLIT</strong> crea una lista que consta de dos registros.</td>
</tr>
<tr class="even">
<td>LISTOFFIELDS (ruta)</td>
<td>Devuelve una lista de los registros creada debido a uno de los siguientes tipos:
<ul>
<li>Enumeración de modelo</li>
<li>Enumeración de formato</li>
<li>Contenedor</li>
</ul>
La lista creada consistirá en registros con los siguientes campos:
<ul>
<li>Nombre</li>
<li>Etiqueta</li>
<li>Descripción</li>
</ul>
Los campos de Etiqueta y Descripción se devolverán a los valores de tiempo de ejecución según la configuración de idioma del formato.</td>
<td>El siguiente ejemplo muestra la enumeración introducida en un modelo de datos. 
<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="GER LISTOFFIELDS function - model enumeration" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

El siguiente ejemplo muestra:
<ul>
<li>Enumeración de modelo insertada en un informe como origen de datos.</li>
<li>La expresión del ER diseñado para usar la enumeración de modelo como parámetro de esta función.</li>
<li>Origen de datos de tipo lista de registro insertado en un informe mediante la expresión de ER creada.</li>
</ul>
<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="GER LISTOFFIELDS function - in format expression" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a> 

El siguiente ejemplo muestra los elementos del formato de ER que están enlazados al origen de datos de tipo lista de registro creado mediante la función de LISTOFFIELDS.
<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="GER LISTOFFIELDS function - format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

Este es el resultado de la ejecución del formato diseñado.
<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="GER LISTOFFIELDS function - format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a><strong>

Nota:</strong> El texto traducido para las etiquetas y las descripciones se forma en la producción de formato de ER de acuerdo con la configuración de idioma configurada para los elementos del formato del ARCHIVO principal y de la CARPETA.</td>
</tr>
<tr class="odd">
<td>STRINGJOIN (lista, nombre de campo, delimitador)</td>
<td>Devuelve la cadena de valores concatenados de un campo desde una lista independiente con un delimitador seleccionado.</td>
<td>Si ha especificado la DIVISIÓN (“abc”, 1) como fuente de datos DS, la expresión STRINGJOIN (DS, DS.Value, “:”) devuelve “a:b:c”</td>
</tr>
<tr class="even">
<td>SPLITLISTBYLIMIT (lista, valor límite, origen del límite)</td>
<td>Divide la lista proporcionada en una nueva lista de sublistas y devuelve el resultado en contenido de la lista del registro. El parámetro de valor límite especifica el valor del límite para dividir la lista de origen. El parámetro de origen del límite especifica el paso en que la suma total aumenta. El límite no se aplica a un único artículo de la lista proporcionada cuando el origen del límite supera el límite definido.</td>
<td>El ejemplo siguiente muestra el formato de ejemplo mediante orígenes de datos. 
<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="GER SPLITLISTBYLIMIT - format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="GER SPLITLISTBYLIMIT - datasources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

Es la ejecución del formato del resultado que muestra la lista plana de artículos de mercancía.
<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="GER SPLITLISTBYLIMIT - output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

El siguiente ejemplo muestra el mismo formato que se ajustó para mostrar la lista de artículos de mercancía en lotes cuando un único lote debe incluir mercancías con el peso total que no debe superar el límite de 9.
<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="GER SPLITLISTBYLIMIT - format 1" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="GER SPLITLISTBYLIMIT - datasources 1" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

Este es el resultado de la ejecución del formato ajustado. <a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="GER SPLITLISTBYLIMIT - output 1" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

<strong>Nota:</strong> El límite no se aplica al último artículo de la lista de origen ya que el valor (11) del origen de su límite (peso) supera el límite definido (9). Use la función <strong>DONDE</strong> o la expresión <strong>Habilitado</strong> del elemento de formato correspondiente para omitir (saltar) las sublistas durante la generación de informes (si es necesario).</td>
</tr>
<tr class="odd">
<td>FILTRAR (lista, condición)</td>
<td>Devuelve la lista filtrada proporcionada para la condición especificada modificando la consulta. A diferencia de la función <strong>DONDE</strong>, la condición especificada se aplica a nivel de base de datos a cualquier origen de datos de ER del tipo de registros de la tabla.</td>
<td>FILTRAR (Vendors, Vendors.VendGroup = &quot;40&quot;) devuelve solo la lista de los proveedores que pertenecen al grupo "40" de proveedores cuando <strong>Proveedor</strong> está configurado como origen de datos de ER que se refiere a la tabla <strong>VendTable</strong></td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Funciones lógicas

| Función                                                                                | Descripción                                                                                                                                                                                                                                                                     | Ejemplo                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CASE (expresión, opción 1, resultado 1 \[, opción 2, resultado 2\] ... \[, resultado predeterminado\]) | Evaluar el valor de la expresión especificado con las opciones alternativas especificadas. Devolver el resultado de la opción que es igual al valor de la expresión. En caso contrario, devolver el resultado predeterminado introducido opcionalmente (el último parámetro al que no le antecede una opción). | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "INVIERNO", "11", "INVIERNO", "12", "INVIERNO", "")** devuelve la cadena **"INVIERNO"** cuando la fecha de la sesión de Finance and Operations actual se encuentra entre octubre y diciembre. En caso contrario, devuelve una cadena en blanco. |
| SI (condición, valor 1, valor 2)                                                        | Devuelve el valor especificado 1 cuando se cumple la condición determinada. En caso contrario, devuelve el valor 2. Si el valor 1 y el valor 2 son registros o listas de registro, el resultado tendrá solo los campos que existan en ambas listas.                                                                     | **IF (1=2, "se cumple la condición", "no se cumple la condición")** devuelve la cadena **"no se cumple la condición"**.                                                                                                                                                      |
| NOT (condición)                                                                         | Devuelve el valor lógico invertido de la condición determinada.                                                                                                                                                                                                                   | **NOT (TRUE)** devuelve **FALSE**.                                                                                                                                                                                                                            |
| AND (condición 1\[, condición 2, ...\])                                                 | Devolver **TRUE** si *todas* las condiciones especificadas son verdaderas. En caso contrario, devuelva **FALSE**.                                                                                                                                                                                            | **AND (1=1, "a"="a")** devuelve **TRUE**. **AND (1=2, "a"="a")** devuelve **FALSE**.                                                                                                                                                                           |
| OR (condición 1\[, condición 2, ...\])                                                  | Devolver **FALSE** si *todas* las condiciones especificadas son falsa. Devolver **TRUE** si *cualquier* condición especificada es verdadera.                                                                                                                                                                 | **OR (1=2, "a"="a")** devuelve **TRUE**.                                                                                                                                                                                                                      |

### <a name="mathematical-functions"></a>Funciones matemáticas

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Función</th>
<th>Descripción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ABS (número)</td>
<td>Devuelve el valor absoluto del número especificado (el número sin signo).</td>
<td><strong>ABS (-1)</strong> devuelve <strong>1</strong>.</td>
</tr>
<tr class="even">
<td>POWER (número, potencia)</td>
<td>Devolver el resultado de elevar el número positivo especificado a la potencia especificada.</td>
<td><strong>POWER (10, 2)</strong> devuelve <strong>100</strong>.</td>
</tr>
<tr class="odd">
<td>NUMBERVALUE (cadena, separador decimal, separador de agrupación de dígitos)</td>
<td>Convertir la cadena especificada en un número. El símbolo especificado se usa para separar el número entero y las partes fraccionarias de un número decimal, y también se usa el separador de millares especificado.</td>
<td><strong>NUMBERVALUE(&quot;1 234,56&quot;, &quot;,&quot;, &quot; &quot;)</strong> devuelve el valor <strong>1234,56</strong>.</td>
</tr>
<tr class="even">
<td>VALUE (cadena)</td>
<td>Convertir la cadena especificada en un número. Las comas y los caracteres de punto (.) se consideran separadores decimales y los guiones iniciales (-) se usan como signo negativo. Genere una excepción si se encuentran otros caracteres no numéricos en la cadena especificada.</td>
<td><strong>VALUE (&quot;1 234,56&quot;)</strong> genera una excepción.</td>
</tr>
<tr class="odd">
<td>ROUND (número, decimales)</td>
<td>Devolver el número especificado, que se redondea al número especificado de posiciones decimales:
<ul>
<li>Si el valor de decimales especificado es superior a 0 (cero), el número especificado se redondea al número especificado de decimales.</li>
<li>Si el valor de decimales especificado es 0 (cero), el número especificado se redondea al número entero más cercano.</li>
<li>Si el valor de decimales especificado es inferior a 0 (cero), el número especificado se redondea a la izquierda de la coma decimal.</li>
</ul></td>
<td><strong>ROUND (1200,767, 2)</strong> redondea a dos lugares decimales y devuelve <strong>1200,77</strong>. <strong>ROUND (1200.767, -3)</strong> redondea al múltiplo más cercano de 1.000 y devuelve <strong>1000</strong>.</td>
</tr>
<tr class="even">
<td>ROUNDDOWN (número, decimales)</td>
<td>Devolver el número especificado, que se redondea hacia abajo (hacia cero) al número especificado de posiciones decimales. <strong>Nota:</strong> Esta función se comporta como <strong>ROUND</strong>, pero siempre redondea hacia abajo del número especificado.</td>
<td><strong>ROUNDDOWN (1200,767, 2)</strong> redondea hacia abajo a dos lugares decimales y devuelve <strong>1200,76</strong>. <strong>ROUNDDOWN (1700.767, -3)</strong> redondea hacia abajo al múltiplo más cercano de 1.000 y devuelve <strong>1000</strong>.</td>
</tr>
<tr class="odd">
<td>ROUNDUP (número, decimales)</td>
<td>Devolver el número especificado, que se redondea hacia arriba (lejos de cero) al número especificado de posiciones decimales. <strong>Nota:</strong> Esta función se comporta como <strong>ROUND</strong>, pero siempre redondea hacia arriba del número especificado.</td>
<td><strong>ROUNDUP (1200,763, 2)</strong> redondea hacia arriba a dos lugares decimales y devuelve <strong>1200,77</strong>. <strong>ROUNDUP (1200.767, -3)</strong> redondea hacia arriba al múltiplo más cercano de 1.000 y devuelve <strong>2000</strong>.</td>
</tr>
</tbody>
</table>

**Funciones de conversión de datos**

| Función             | Descripción                                                                                                                                                                                                                                     | Ejemplo                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| VALUE (cadena) | Convertir la cadena especificada en un número. Las comas y los caracteres de punto (.) se consideran separadores decimales y los guiones iniciales (-) se usan como signo negativo. Si se encuentran otros caracteres no numéricos en la cadena especificada, se produce un error.                                                                                  | **VALUE ("1 234,56")** genera una excepción.   |
| NUMBERVALUE (cadena, separador decimal, separador de agrupación de dígitos) | Convertir la cadena especificada en un número. El símbolo especificado se usa para separar el número entero y las partes fraccionarias de un número decimal, y también se usa el separador de millares especificado.                                                                                  | **NUMBERVALUE("1 234,56", ",", " ")** devuelve el valor **1234,56**.    |
| INTVALUE (cadena) | Devuelve la representación de un entero de una cadena. Cualquier parte decimal disponible será truncada.                                                                                  | **INTVALUE (“100,77 ")** devuelve **100**. |
| INTVALUE (número) | Devuelve la representación de un número. Cualquier parte decimal disponible será truncada.                                                                                  | **INTVALUE (-100,77)** devuelve **100**. |
| INT64VALUE (cadena) | Devuelve la representación de int64 de una cadena. Cualquier parte decimal disponible será truncada.                                                                                  | **INT64VALUE (“22565422744”)** devuelve **22565422744**. |
| INT64VALUE (número) | Devuelve la representación de int64 de un número. Cualquier parte decimal disponible será truncada.                                                                                  | **INT64VALUE (22565422744.00)** devuelve **22565422744**. |



### <a name="record-functions"></a>Funciones de registro

| Función             | Descripción                                                                                                                                                                                                                                     | Ejemplo                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| NULLCONTAINER (lista) | Devolver un registro **nulo** con la misma estructura que el registro o la lista de registros especificada. **Nota:** Esta función es obsoleta. Use **EMPTYRECORD** en su lugar.                                                                                  | **NULLCONTAINER (SPLIT ("abc", 1))** devuelve un nuevo registro vacía que tiene la misma estructura que la lista que se devuelve por la función **SPLIT**. |
| EMPTYRECORD (registro) | Devolver un registro **nulo** con la misma estructura que el registro o la lista de registros especificada. **Nota:** Un registro **nulo** es un registro donde todos los campos tienen un valor vacío (**0** \[cero\] para números, una cadena vacía para cadenas, etc.). | **EMPTYRECORD (SPLIT ("abc", 1))** devuelve un nuevo registro vacía que tiene la misma estructura que la lista que se devuelve por la función **SPLIT**.   |

### <a name="text-functions"></a>Funciones de texto

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Función</th>
<th>Descripción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>UPPER (cadena)</td>
<td>Devuelve la cadena especificada, que se convierte en letras mayúsculas.</td>
<td><strong>UPPER (&quot;Muestra&quot;)</strong> devuelve <strong>&quot;MUESTRA&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LOWER (cadena)</td>
<td>Devuelve la cadena especificada, que se convierte en letras minúsculas.</td>
<td><strong>LOWER (&quot;Muestra&quot;)</strong> devuelve <strong>&quot;muestra&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>LEFT (cadena, número de caracteres)</td>
<td>Devuelve el número especificado de caracteres desde el inicio de la cadena especificada.</td>
<td><strong>LEFT (&quot;Muestra&quot;, 3)</strong> devuelve <strong>&quot;Sam&quot;</strong>.</td>
</tr>
<tr class="even">
<td>RIGHT (cadena, número de caracteres)</td>
<td>Devuelve el número especificado de caracteres desde el final de la cadena especificada.</td>
<td><strong>RIGHT (&quot;Muestra&quot;, 3)</strong> devuelve <strong>&quot;ple&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>MID (cadena, posición inicial, número de caracteres)</td>
<td>Devuelve el número especificado de caracteres desde la cadena especificada, empezando por la posición especificada.</td>
<td><strong>MID (&quot;Muestra&quot;, 2, 3)</strong> devuelve <strong>&quot;amp&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LEN (cadena)</td>
<td>Devuelve el número de caracteres de la cadena especificada.</td>
<td><strong>LEN (&quot;Muestra&quot;)</strong> devuelve <strong>6</strong>.</td>
</tr>
<tr class="odd">
<td>CHAR (número)</td>
<td>Devuelve la cadena de caracteres a la que hace referencia el número Unicode especificado.</td>
<td><strong>CHAR (255)</strong> devuelve <strong>&quot;ÿ&quot;</strong>. <strong>Nota:</strong> la cadena devuelta depende de la codificación seleccionada en el elemento de formato del ARCHIVO principal. La lista de codificaciones admitidas se puede encontrar en el tema <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Clase de codificación</a>.</td>
</tr>
<tr class="even">
<td>CONCATENATE (cadena 1 [, cadena 2, …])</td>
<td>Devolver todas las cadenas de texto especificadas, que se unen en una cadena.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> devuelve <strong>&quot;abcdef&quot;</strong>. <strong>Nota:</strong> La expresión <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> también devuelve <strong>&quot;abcdef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TRANSLATE (cadena, patrón, sustitución)</td>
<td>Devuelve la cadena especificada, en la que todas las apariciones de los caracteres de la cadena de patrones especificados se sustituyen por los caracteres del puesto correspondiente de la cadena de sustitución especificada.</td>
<td><strong>TRANSLATE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> reemplaza el patrón <strong>&quot;cd&quot;</strong> por la cadena <strong>&quot;GH&quot;</strong> y devuelve <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="even">
<td>REPLACE (cadena, patrón, sustitución, indicador de expresión regular)</td>
<td>Cuando es el indicador de expresión regular especificada es <strong>verdadero</strong>, devuelve la cadena especificada, que se modifica aplicando la expresión normal que se especifica como argumento de patrón para esta función. Esta expresión se usa para buscar los caracteres que se deben sustituir. Los caracteres del argumento de sustitución especificado se usan para reemplazar los caracteres que se encuentran. Cuando el indicador de la expresión regular especificada es <strong>falso</strong>, esta función se comporta como <strong>TRANSLATE</strong>.</td>
<td>  <strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, true)</strong> aplica una expresión regular que quita todos los símbolos no numéricos y devuelve <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, false)</strong> reemplaza el patrón <strong>&quot;cd&quot;</strong> por la cadena <strong>&quot;GH&quot;</strong> y devuelve <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TEXT (entrada)</td>
<td>Devuelve la entrada especificada, que se convierte en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de Finance and Operations. Para los valores del tipo <strong>real</strong>, la conversión de la cadena se limita a dos decimales.</td>
<td>Si se define la configuración regional del servidor de instancias de Finance and Operations como <strong>EN-US</strong>, <strong>TEXT (NOW ())</strong> devuelve la fecha de la sesión de Finance and Operations actual, 17/12/2015, como la cadena de texto <strong>&quot;17/12/2015 07:59:23 a.m.&quot;</strong>. <strong>TEXT (1/3)</strong> devuelve <strong>&quot;0,33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMAT (cadena 1, cadena 2 [, cadena 3,…])</td>
<td>Devuelve la cadena especificada, que se formatea sustituyendo cualquier aparición de <strong>%N</strong> con el argumento <em>n</em>-ésimo. Los argumentos son cadenas. Si no se proporciona un argumento para un parámetro, el parámetro se devuelve como <strong>&quot;%N&quot;</strong> en la cadena. Para los valores del tipo <strong>real</strong>, la conversión de la cadena se limita a dos decimales.</td>
<td>En este ejemplo, el origen de datos <strong>PaymentModel</strong> devuelve la lista de registros de clientes mediante el componente <strong>Cliente</strong> y el valor de la fecha de procesamiento mediante el campo <strong>ProcessingDate</strong>. 
<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a> 

En el formato ER diseñado para generar un archivo electrónico para los clientes seleccionados, <strong>PaymentModel</strong> se selecciona como origen de datos y controla el flujo de proceso. Se genera una excepción para los usuarios finales cuando se detiene un cliente seleccionado para la fecha en la que se procesa el informe. La fórmula que está diseñada para este tipo de control de proceso puede usar los recursos siguientes:
<ul>
<li>La etiqueta SYS70894 de Finance and Operations tiene el siguiente texto:
<ul>
<li><strong>Para el idioma EN-US:</strong> &quot;Nothing to print&quot;</li>
<li><strong>Para el idioma DE:</strong> &quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>La etiqueta SYS18389 de Finance and Operations tiene el siguiente texto:
<ul>
<li><strong>Para el idioma EN-US:</strong> &quot;Customer %1 is stopped for %2.&quot;</li>
<li><strong>Para el idioma DE:</strong> &quot;Debitor '%1' wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
Esta es la fórmula que se puede diseñar: FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;)) Si se procesa un informe para el <strong>cliente de Litware Retail</strong> el 17 de diciembre de 2015, en la referencia cultural <strong>EN-US</strong> y el idioma <strong>EN-US</strong>, esta fórmula devuelve el siguiente texto, que se puede presentar como mensaje de excepción para el usuario final: &quot;Nothing to print. Customer Litware Retail se detiene 17/12/2015.&quot; Si el mismo informe se procesa para el<strong> cliente de Litware Retail</strong> el 17 de diciembre de 2015, en la referencia cultural <strong>DE</strong> y el idioma <strong>DE</strong>, esta fórmula devuelve el siguiente texto, que usa un formato de fecha diferente: &quot;Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.&quot; <strong>Nota:</strong> La siguiente sintaxis se aplica en fórmulas de ER para etiquetas:
<ul>
<li><strong>Para las etiquetas de los recursos de Finance and Operations:</strong> <strong>@&quot;X&quot;</strong>, donde la X es el identificador de la etiqueta en el Árbol de objetos de aplicación (AOT)</li>
<li><strong>Para las etiquetas que se encuentran en las configuraciones de ER:</strong> <strong>@&quot;GER_LABEL:X&quot;</strong>, donde X es el id. de etiqueta de la configuración de ER</li>
</ul></td>
</tr>
<tr class="odd">
<td>NUMBERFORMAT (número, formato)</td>
<td>Devuelve la representación de la cadena del número especificado en el formato especificado. (Para obtener información sobre los formatos admitidos, consulte <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">estándar</a> y <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">personalizado</a>). El contexto en el que se ejecuta esta función determina la cultura que se usa para el formato de los números.</td>
<td>Para la referencia cultural EN-US, <strong>NUMBERFORMAT (0,45, &quot;p&quot;)</strong> devuelve <strong>&quot;45,00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> devuelve <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (número, idioma, divisa, indicador del nombre de la divisa de impresión, separadores decimales)</td>
<td>Devuelve el número explicado (convertido) a las cadenas de texto en el idioma definido. El código de idioma es opcional: cuando se define como cadena vacía, el código de idioma actual de contexto (definido para una carpeta o un archivo que genera) se usará en su lugar. El código de divisa es opcional. Cuando se define como cadena vacía, se usa la divisa de la empresa. Tenga en cuenta que, el parámetro <strong>Nombre de la divisa de impresión</strong> y el parámetro <strong>Separadores decimales</strong> se analizan solo para los códigos de idioma siguientes: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong>, <strong>RU</strong>. Tenga en cuenta que, el parámetro <strong>Nombre de la divisa de impresión</strong> se analiza solo para las empresas de Finance and Operations con el contexto del país que admite la declinación de la divisa.</td>
<td>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2) devuelve “One Thousand Two Hundred Thirty Four and 56” NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0) devuelve “Sto dwadzieścia” NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2) devuelve “Сто двадцать евро 21 евроцент”</td>
</tr>
<tr class="odd">
<td>PADLEFT (cadena, longitud, caracteres de relleno)</td>
<td>Devuelve una cadena con la longitud especificada en la que el comienzo de la cadena actual se rellena con los caracteres especificados.</td>
<td>PADLEFT (“1234”, 10, “ “) devuelve la cadena de texto ” 1234”</td>
</tr>
<tr class="even">
<td>TRIM (cadena)</td>
<td>Devuelve un texto determinado tras el truncamiento de espacios iniciales y finales, y la eliminación de múltiples espacios entre palabras. </td>
<td><strong>TRIM ("     Texto     ejemplo     ")</strong> devuelve <strong>"Texto de ejemplo".</strong></td>
</tr>
<tr class="odd">
<td>GETENUMVALUEBYNAME (ruta del origen de datos de enumeración, texto de etiqueta del valor de enumeración)</td>
<td>Devuelve un valor de un origen de datos de enumeración especificado por el texto especificado de esta etiqueta de enumeración.</td>
<td>El siguiente ejemplo muestra la enumeración ReportDirection introducida en un modelo de datos. Tenga en cuenta que las etiquetas se definen por valores de enumeración.
<a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a> Los siguientes ejemplos muestran:
<ul><li>Enumeración de modelo <strong>ReportDirection</strong> insertada en un informe como origen de datos <strong>$Direction</strong></li>
<li>La expresión del ER <strong>$IsArrivals</strong> diseñada para usar la enumeración de modelo como parámetro de esta función. El valor de esta expresión es <strong>TRUE</strong>.

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></li></ul></td>
</tr>
</tbody>
</table>

**Funciones de conversión de datos**

| Función             | Descripción                                                                                                                                                                                                                                     | Ejemplo                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| TEXT (entrada) | Devuelve la entrada especificada, que se convierte en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de Finance and Operations.
Para los valores del tipo real, la conversión de la cadena se limita a dos decimales.| Si se define la configuración regional del servidor de instancias de Finance and Operations como **EN-US, TEXT (NOW ())**, la fecha de sesión actual de Finance and Operations 17/12/2015 se devuelve como la cadena de texto **"17/12/2015 07:59:23 AM"**.
**TEXT (1/3) devuelve "0,33"**. |
| QRCODE (cadena) | Produce una imagen de código QR en formato binario base64 de una determinada cadena. | **QRCODE (“texto de muestra ")** devuelve **U2FtcGxlIHRleHQ=**.   |

### <a name="data-collection-functions"></a>Funciones de recopilación de datos

| Función             | Descripción                                                                                                                                                                                                                                     | Ejemplo                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| FORMATELEMENTNAME () | Devuelve el nombre del elemento de formato actual. Devuelve la cadena vacía cuando el indicador **Recopilar de los detalles de salida** de los archivos actuales está desactivado.| Consulte los **los datos de uso de ER del formato generados para contar y calcular** (parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**) la guía de tareas para obtener más información acerca del uso de estas funciones. |
| SUMIFS (cadena clave para sumar, cadena de criterio range1, cadena de criterio value1 \[ cadena de criterio range2, cadena de criterio value2, …\]) |Devuelve una suma de los valores de nodos (con el nombre especificado como una clave) de XML, que se ha obtenido durante esta ejecución de formato y que cumple con las condiciones especificadas (pares de rango y de valor). Devuelve un valor cero cuando el indicador **Recopilar detalles de salida** de los archivos actuales está desactivado. |            |
| SUMIF (cadena clave para sumar, cadena de criterio de rango, cadena de criterio de valor) | Devuelve una suma de los valores de nodos (con el nombre especificado como una clave) de XML, que se ha obtenido durante esta ejecución de formato y que cumple con la condición especificada (rango y valor). Devuelve un valor cero cuando el indicador **Recopilar detalles de salida** de los archivos actuales está desactivado.|           |
| COUNTIFS (cadena de criterio range1, cadena de criterio value1 \[, cadena de criterio range2, cadena de criterio value2, …\]) | Devuelve un número de XML, que se ha obtenido durante esta ejecución de formato y que cumple con las condiciones especificadas (pares de rango y de valor). Devuelve un valor cero cuando el indicador **Recopilar detalles de salida** de los archivos actuales está desactivado.|     |
| COUNTIF (cadena de criterios de rango, cadena de criterios de valor) | Devuelve un número de nodos de XML, que se ha obtenido durante esta ejecución de formato y que cumple con la condición especificada (rango y valor). Devuelve un valor cero cuando el indicador **Recopilar detalles de salida** de los archivos actuales está desactivado.|          |
| COLLECTEDLIST (cadena de criterio range1, cadena de criterio value1 \[, cadena de criterio range2, cadena de criterio value2, …\]) | Devuelve una lista de valores de XML, que se ha obtenido durante esta ejecución de formato y que cumple con las condiciones especificadas (rango y valor). Devuelve una lista vacía cuando el indicador **Recopilar detalles de salida** de los archivos actuales está desactivado.|               |   




### <a name="other-business-domainspecific-functions"></a>Otras funciones (específicas de dominio empresarial)

| Función                                                                         | Descripción                                                                                                                                                                                                                                                        | Ejemplo                                                                                                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CONVERTCURRENCY (importe, divisa de origen, divisa de destino, fecha, empresa)        | Convertir el importe monetario especificado de la divisa de origen a la divisa de destino con la configuración de la empresa especificada de Finance and Operations en la fecha especificada.                                                                            | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** devuelve el equivalente de un euro en dólares estadounidenses en la fecha de la sesión actual, en función de la configuración para la empresa de DEMF.                                                                                                                                  |
| ROUNDAMOUNT (número, decimales, regla de redondeo)                                       | Redondee el importe especificado de acuerdo con la regla de redondeo especificada y el número especificado de decimales. **Nota:** La regla de redondeo se debe especificar como un valor de la enumeración **RoundOffType** de Finance and Operations.                          | Si el parámetro **model.RoundOff** se establece en ****Hacia abajo****, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** devuelve el valor **1000,78**. Si el parámetro **model.RoundOff** se establece en **Normal** o **Redondeo por arriba**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** devuelve el valor **1000,79**. |
| CURCredRef (dígitos)                                                              | Devuelve una referencia de acreedor basada en los dígitos del número de factura especificado.                                                                                                                                                                                  | **CURCredRef (“VEND-200002”)** devuelve **“2200002"**.                                                                                                                                                                                                                                                         |
| MOD\_97 (dígitos)                                                                 | Devuelve una referencia de acreedor como expresión MOD97, basada en los dígitos del número de factura especificado.                                                                                                                                                            | **MOD\_97 ("VEND-200002")** devuelve **"20000285"**.                                                                                                                                                                                                                                                           |
| ISOCredRef (dígitos)                                                              | Devuelve una referencia de acreedor ISO, basada en los dígitos y los símbolos alfabéticos del número de factura especificado. **Nota:** Para anular símbolos de los alfabetos que no son compatibles con ISO, el parámetro de entrada se debe traducir antes de que se pase a esta función. | **ISOCredRef (“VEND-200002”)** devuelve **“RF23VEND-200002"**.                                                                                                                                                                                                                                                 |
| CN\_GBT\_AdditionalDimensionID (cadena, número)                                  | Obtener el identificador de dimensión financiera adicional. Las dimensiones se representan en esta cadena como identificadores separados por comas. Los números definen el código de la secuencia de la dimensión solicitada en esta cadena.                                                                            | CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3) devuelve “CC”                                                                                                                                                                                                                                      |
| GetCurrentCompany ()                                                             | Devuelve la representación de texto de un código de una entidad jurídica (empresa) en la que un usuario ha iniciado su sesión actual.                                                                                                                                                                                                                    | **GETCURRENTCOMPANY ()** devuelve **USMF** para un usuario que inició sesión en la empresa de Finance and Operations **Contoso Entertainment System USA**.                                                                                                                                                                                                                                                                                                              |
| CH\_BANK\_MOD\_10 (dígitos)                                                       | Devuelve una referencia de acreedor como expresión MOD10 en función del número de factura proporcionado.                                                                                                                                                                      | CH\_BANK\_MOD\_10 ("VEND-200002") devuelve 3                                                                                                                                                                                                                                                                   |
| FA\_SUM (código de activo fijo, código del modelo de valor, fecha inicial, fecha final)               | Devuelve el contenedor de datos preparado de los importes de un activo fijo para un período.                                                                                                                                                                                         | FA\_SUM ("COMP-000001", “Actual”, Date1, Date2) devuelve el contenedor de datos preparado del activo fijo “COMP-000001” con el modelo de valor “Actual” para un período desde Date1 a Date2.                                                                                                                        |
| FA\_BALANCE (código de activo fijo, código del modelo de valor, año de notificación, fecha de notificación) | Devuelve el contenedor de datos preparado de los saldos de activos fijos. El año de notificación debe especificarse como valor de la enumeración de Finance and Operations **AssetYear**.                                                                                           | FA\_SUM ("COMP-000001", “Actual”, AxEnumAssetYear.ThisYear, SESSIONTODAY ()) devuelve el contenedor preparado de los datos de los saldos del activo fijo “COMP-000001” con el modelo de valor “Actual” en la fecha de la sesión actual de Finance and Operations.                                                                |
| TABLENAME2ID (cadena)                                                       | Devuelve la representación en entero del ID de una tabla para un nombre de tabla dado.                                                                                                                                                                      | **TABLENAME2ID (“Intrastat”)** devuelve **1510**.                                                                                                                                                                                                                                                                   |
| ISVALIDCHARACTERISO7064 (cadena)                                                       | Devuelve el valor booleano **TRUE** cuando una cadena dada representa un número internacional de cuenta bancaria válido (IBAN). De lo contrario, devuelve un valor booleano **FALSE**.                                                                                                                                                                      | **ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")** devuelve **TRUE**. **ISVALIDCHARACTERISO7064 ("AT61")** devuelve **FALSE**.                                                                                                                                                                                                                                                                   |

### <a name="functions-list-extension"></a>Extensión de la lista de funciones

ER le permite ampliar la lista de funciones que se usan en las expresiones de ER. Son necesarios algunos esfuerzos de ingeniería. Para obtener información detallada, vea [Ampliar la lista de funciones de informes electrónicos](general-electronic-reporting-formulas-list-extension.md).

<a name="see-also"></a>Consulte también
--------

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Ampliar la lista de funciones de Informes electrónicos (ER)](general-electronic-reporting-formulas-list-extension.md)





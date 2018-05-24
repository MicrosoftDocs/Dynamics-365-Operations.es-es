---
title: "Diseñador de fórmulas en los informes electrónicos"
description: "Este tema explica cómo usar el diseñador de fórmula en Informes electrónicos (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3988c437afda3d57e56a03264d3c1588af497920
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="formula-designer-in-electronic-reporting"></a>Diseñador de fórmulas en los informes electrónicos

[!include [banner](../includes/banner.md)]

Este tema explica cómo usar el diseñador de fórmula en Informes electrónicos (ER). Cuando diseña un formato para un documento electrónico específico en ER, puede usar fórmulas para transformar datos de modo que cumplan los requisitos para el cumplimiento y el formato de ese documento. Estas fórmulas se asemejan a fórmulas en Microsoft Excel. Se admiten diversos tipos de funciones en las fórmulas: texto, fecha y hora, lógica matemática, información, conversión de tipo de datos y otras (funciones específicas de dominio empresarial).

## <a name="formula-designer-overview"></a>Visión general del diseñador de fórmulas

Los ER admiten el diseñador de fórmulas. Por tanto, en el momento del diseño, puede configurar las expresiones que se pueden usar para las siguientes tareas en tiempo de ejecución:

- Transforme datos recibidos de una base de datos de Microsoft Dynamics 365 for Finance and Operations, que se deben introducir en un modelo de datos de ER que se ha diseñado para ser un origen de datos para formatos de ER. (Por ejemplo, estas transformaciones pueden incluir el filtrado, la agrupación y la conversión de tipos de datos.)
- Formatee los datos que deben enviarse a un documento electrónico de generación de acuerdo con el diseño y las condiciones de un formato de ER específico. (Por ejemplo, el formato puede realizarse de acuerdo con el idioma o la cultura solicitada, o la codificación).
- Controle el proceso de creación de documentos electrónicos. (Por ejemplo, las expresiones pueden habilitar o deshabilitar la salida de elementos específicos del formato, en función de datos de procesamiento. También pueden interrumpir el proceso de creación del documento o enviar mensajes a los usuarios.)

Puede abrir la página **Diseñador de fómulas** cuando realice cualquiera de las siguientes acciones:

- Enlazar artículos del origen de datos a los componentes del modelo de datos.
- Enlazar artículos del origen de datos a componentes de formato.
- Completar el mantenimiento de campos calculados que forman parte de orígenes de datos.
- Definir las condiciones de visibilidad para los parámetros de entrada del usuario.
- Diseñar las transformaciones de un formato.
- Definir las condiciones de habilitación para los componentes del formato.
- Definir los nombres de archivo para los componentes de ARCHIVO de formato.
- Definir las condiciones para las validaciones de control de proceso.
- Definir el texto de mensaje para las validaciones de control de proceso.

## <a name="designing-er-formulas"></a>Diseño de las fórmulas de ER

### <a name="data-binding"></a>Vinculación de datos

El diseñador de fórmula de ER se puede usar para definir una expresión que transforma datos que se reciben de orígenes de datos, para que se puedan introducir los datos en el consumidor de datos en tiempo de ejecución:

- Desde los orígenes de datos de Finance and Operations y los parámetros de tiempo de ejecución a un modelo de datos de ER.
- Desde un modelo de datos de ER a un formato de ER
- Desde los orígenes de datos de Finance and Operations y los parámetros de tiempo de ejecución a un formato de ER

En la ilustración siguiente se muestra el diseño de una expresión de este tipo. En este ejemplo, la expresión redondea el valor del campo **Intrastat.AmountMST** de la tabla Intrastat de Finance and Operations hasta dos posiciones decimales y luego devuelve el valor redondeado.

[![Vinculación de datos](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

En la ilustración siguiente se muestra cómo usar una expresión de este tipo. En este ejemplo, el resultado de la expresión diseñada se introduce en el componente **Transaction.InvoicedAmount** del modelo de datos **Modelo de notificación tributaria**.

[![Vinculación de datos empleada](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

En el tiempo de ejecución, la fórmula diseñada, **ROUND (Intrastat.AmountMST, 2)**, redondea el valor del campo **AmountMST** para cada registro de la tabla Intrastat con dos posiciones decimales. A continuación, especifique el valor redondeado en el componente **Transaction.InvoicedAmount** del modelo de datos **Informe de impuestos** .

### <a name="data-formatting"></a>Formato de datos

El diseñador de fórmula de ER se puede usar para definir una expresión que formatea datos que se reciben de orígenes de datos, para que se puedan enviar como parte de la generación de un documento electrónico. Es posible que tenga un formato que debe aplicarse como regla típica que se debe volver a usar para un formato. En este caso, puede introducir ese formato una vez en la configuración del formato, como una transformación nombrada que tiene una expresión del formato. Esta transformación nombrada se puede vincular a continuación a varios componentes de formato si el resultado debe formatearse de acuerdo con la expresión que creó.

En la ilustración siguiente se muestra el diseño de una transformación de este tipo. En este ejemplo, la transformación **TrimmedString** trunca datos entrantes del tipo de datos **Secuencia** eliminando espacios principales y finales. A continuación, Itd devuelve el valor de cadena truncado.

[![Transformación](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

En la ilustración siguiente se muestra cómo usar una transformación de este tipo. En este ejemplo, varios componentes de formato envían texto como salida al documento electrónico de generación en el tiempo de ejecución. Todos estos componentes de formato hacen referencia a la transformación **TrimmedString** por nombre.

[![Transformación que se usa](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Cuando los componentes del formato, como el componente **partyName** en la ilustración anterior, hacen referencia a la transformación **TrimmedString**, la transformación envía texto como salida al documento electrónico de generación. Este texto no incluye espacios principales y finales.

Si tiene un formato que se debe aplicar de forma individual, puede introducir ese formato como una expresión individual de una vinculación de un componente de formato concreto. En la ilustración siguiente se muestra una expresión de este tipo. En este ejemplo, el componente del formato **partyType** se vincula al origen de datos mediante una expresión que convierte los datos entrantes del campo **Model.Company.RegistrationType** del origen de datos en texto en mayúsculas. A continuación, la expresión envía ese texto como salida al documento electrónico de generación.

[![Aplicar formato a un componente individual](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Control de flujo de proceso

El diseñador de fórmulas de ER se puede usar para definir las expresiones que controlan el flujo de proceso de documentos electrónicos de generación. Se pueden llevar a cabo las siguientes tareas:

- Definir las condiciones que determinan cuándo un proceso de creación de documento se debe detener.
- Especifique expresiones que creen mensajes para el usuario acerca de los procesos detenidos o lancen mensajes de registro de ejecución acerca de continuar con el proceso de la generación del informe.
- Especifique los nombres de archivo de los documentos electrónicos de generación y las condiciones de control de su creación.

Cada regla de control de flujo de proceso está diseñada como validación individual. En la ilustración siguiente se muestra una validación de este tipo. Esta es una explicación de la configuración de este ejemplo:

- La validación se evalúa cuando se crea el nodo **INSTAT** durante la generación del archivo XML.
- Si la lista de transacciones está vacía, la validación detiene el proceso de ejecución y devuelve **FALSE**.
- La validación devuelve un mensaje de error que incluye el texto de la etiqueta SYS70894 de Finance and Operations en el idioma preferido del usuario.

[![Validación](./media/picture-validation.jpg)](./media/picture-validation.jpg)

El diseñador de fórmulas de ER también se puede usar para generar un nombre de archivo para un documento electrónico de generación y para controlar el proceso de creación del archivo. En la ilustración siguiente se muestra el diseño de un control de flujo de proceso de este tipo. Esta es una explicación de la configuración de este ejemplo:

- La lista de registros de origen de datos **model.intrastat** se divide en lotes. Cada lote contiene hasta 1000 registros.
- La salida crea un archivo zip que contiene un archivo en formato XML para cada lote que se ha creado.
- Una expresión devuelve un nombre de archivo para documentos electrónicos de generación concatenando el nombre de archivo y la extensión del nombre de archivo. Para el segundo lote y todos los lotes posteriores, el nombre de archivo contiene el id. de lote como sufijo.
- Una expresión habilita (devolviendo **TRUE**) el proceso de creación de archivos para lotes que contengan al menos un registro.

[![Control del archivo](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Sintaxis básica

Las expresiones de ER pueden contener todo los elementos siguientes o cualquiera de ellos:

- Constantes
- Operadores
- Referencias
- Rutas
- Funciones

#### <a name="constants"></a>Constantes

Cuando diseñe expresiones, puede usar constantes de texto y numéricas (es decir, valores que no se calculan). Por ejemplo, la expresión **VALUE ("100") + 20** usa la constante numérica **20** y la constante de cadena **"100"** y devuelve el valor numérico **120**. El diseñador de fórmulas de ER admite secuencias de escape. Por lo tanto, puede especificar una cadena de expresión que debe gestionarse de forma diferente. Por ejemplo, la expresión **"Leo Tolstoy ""Guerra y paz"" Volumen 1"** devuelve la cadena de texto **Leo Tolstoy "Guerra y paz" Volumen 1**.

#### <a name="operators"></a>Operadores

La tabla siguiente muestra los operadores aritméticos que puede usar para realizar operaciones matemáticas básicas, como suma, resta, multiplicación y división.

| Operador | Significado               | Ejemplo |
|----------|-----------------------|---------|
| +        | Adición              | 1+2     |
| -        | Resta, negación | 5-2, -1 |
| \*       | Multiplicación        | 7\*8    |
| /        | División              | 9/3     |

La tabla siguiente muestra los operadores de comparación que se admiten. Puede utilizar estos operadores para comparar dos valores.

| Operador | Significado                  | Ejemplo    |
|----------|--------------------------|------------|
| =        | Igual                    | X=Y        |
| &gt;     | Mayor que             | X&gt;Y     |
| &lt;     | Menor que                | X&lt;Y     |
| &gt;=    | Superior a o igual a | X&gt;=Y    |
| &lt;=    | Inferior a o igual a    | X&lt;=Y    |
| &lt;&gt; | No igual que             | X&lt;&gt;Y |

Además, puede usar un signo (&) como operador de concatenación de texto. De esta manera, puede unir, o concatenar, una o más cadenas de texto en una única pieza de texto.

| Operador | Significado     | Ejemplo                                             |
|----------|-------------|-----------------------------------------------------|
| &        | Concatenar | "No hay nada que imprimir" & ":&nbsp;" & "no se encuentran registros" |

##### <a name="operator-precedence"></a>Prevalencia del operador

El orden en el que se evalúan las partes de una expresión compuesta es importante. Por ejemplo, el resultado de la expresión **1 + 4/2** varía en función de si la operación de adición o la operación la división se realiza primero. Puede usar paréntesis para definir explícitamente la manera en que se evalúa una expresión. Por ejemplo, para indicar que la operación de adición debe realizarse primero, puede cambiar la expresión precedente a **(1 + 4) / 2**. Si no indica explícitamente el orden de las operaciones en una expresión, el orden se basa en la prioridad predeterminada que se asigna a los operadores admitidos. En la siguiente tabla se muestra la prioridad que se asigna a cada operador. Los operadores que tienen una mayor prioridad (por ejemplo, 7) se evalúan antes que los operadores que tienen una prioridad más baja (por ejemplo, 1).

| Precedencia | Operadores      | Sintaxis                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Agrupación       | ( … )                                                                   |
| 6          | Acceso a miembros  | … . …                                                                   |
| 5          | Llamada de función  | … ( … )                                                                 |
| 4          | Multiplicativa | … \* …<br>… / …                                                         |
| 3          | Aditivo       | … + …<br>… - …                                                          |
| 2          | Comparación     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Separación     | … , …                                                                   |

Si una expresión incluye múltiples operadores consecutivos que tienen la misma prioridad, dichas operaciones se evalúan de izquierda a derecha. Por ejemplo, la expresión **1 + 6 / 2 \* 3 &gt; 5** devuelve **true**. Se recomienda usar paréntesis para indicar explícitamente el orden deseado de operaciones en las expresiones, de manera que las expresiones resulten más sencills de leer y mantener.

#### <a name="references"></a>Referencias

Todos los orígenes de datos del componente del ER actual que están disponibles durante el diseño de una expresión se pueden usar como referencias con nombre. (El componente actual de ER puede ser un modelo o un formato). Por ejemplo, el modelo de datos actual de ER contiene el origen de datos **ReportingDate**, y este origen de datos devuelve un valor del tipo de datos **DATETIME**. Para dar formato correctamente ese valor en el documento que lo genera, puede hacer referencia el origen de datos en la expresión **DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")**.

Todos los caracteres en el nombre de un origen de datos de referencia que no representan una letra del alfabeto deben venir precedidos de una comilla simple ('). Si el nombre de un origen de datos de referencia incluye al menos un símbolo que no representa una letra del alfabeto, el nombre debe estar entre comillas simples. (Por ejemplo, estos símbolos no alfabéticos pueden ser signos de puntuación u otros símbolos escritos.) A continuación se muestran algunos ejemplos:

- Se debe hacer referencia al origen de datos **Hora y día hoy** en una expresión de ER de la siguiente manera: **'Hora y día hoy'**.
- Debe hacerse referencia al método **name()** del origen de datos **Clientes** en una expresión de ER de la siguiente manera: **Customers.'name()'**.

Si los métodos de orígenes de datos de Finance and Operations tienen parámetros, la siguiente sintaxis se utiliza para asignar un nombre a dichos métodos:

- Si el método **isLanguageRTL** del origen de datos **Sistema** tiene un parámetro **EN-US** del tipo de datos **Cadena**, este método debe hacer referencia a una expresió de ER como **System.'isLanguageRTL'("EN-US")**.
- Las comillas no son necesarias cuando un nombre del método solo contiene símbolos alfanuméricos. Sin embargo, se requieren para un método de una tabla si el nombre incluye corchetes.

Cuando se agrega el origen de datos **Sistema** a la asignación de ER que hace referencia a la clase de aplicación de Finance and Operations **Global**, la expresión devuelve el valor booleano **FALSE**. La expresión modificada **System.' isLanguageRTL'("AR")** devuelve el valor booleano **TRUE**.

Puede limitar la forma en que los valores se pasan a los parámetros de este tipo de método:

- Únicamente las constantes se pueden pasar a los métodos de este tipo. Los valores de las constantes se definen en el tiempo de diseño.
- Solo se admiten tipos de datos primitivos (básicos) para los parámetros de este tipo. (Los tipos de datos primitivos son entero, real, booleano, cadena, etc.).

#### <a name="paths"></a>Rutas

Cuando una expresión hace referencia a un origen de datos estructurado, puede usar la definición de ruta para seleccionar un elemento primitivo específico de ese origen de datos. Un carácter de punto (.) se usa para separar elementos individuales de un origen de datos estructurado. Por ejemplo, el modelo de datos actual de ER contiene el origen de datos **InvoiceTransactions**, y este origen de datos devuelve una lista de registros. La estructura de registros **InvoiceTransactions** contiene los campos **AmountDebit** y **AmountCredit**, y estos campos devuelven valores numéricos. Por tanto, puede diseñar la siguiente expresión para calcular el importe facturado: **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**.

#### <a name="functions"></a>Funciones

La sección siguiente describe las funciones que se pueden usar en expresiones de ER. Todos los orígenes de datos del contexto de la expresión (el modelo de datos de ER o formato actual de ER) pueden usarse como parámetros de funciones de llamada de acuerdo con la lista de argumentos de las funciones de llamada. Las constantes también se pueden usar como parámetros de las funciones de llamada. Por ejemplo, el modelo de datos actual de ER contiene el origen de datos **InvoiceTransactions**, y este origen de datos devuelve una lista de registros. La estructura de registros **InvoiceTransactions** contiene los campos **AmountDebit** y **AmountCredit**, y estos campos devuelven valores numéricos. Por tanto, para calcular el importe facturado, puede diseñar la siguiente expresión que usa la función de redondeo incorporada de ER: **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**.

## <a name="supported-functions"></a>Funciones no permitidas.

Las siguientes tablas describen las funciones de manipulación de datos que puede usar para diseñar modelos de datos de ER e informes de ER. La lista de funciones no es fija. Los desarrolladores pueden ampliarlo. Para ver la lista de funciones que puede usar, abra el panel de funciones del diseñador de fórmulas de ER.

### <a name="date-and-time-functions"></a>Funciones de fecha y de tiempo

| Función | Descripción | Ejemplo |
|----------|-------------|---------|
| ADDDAYS (fecha y hora, días) | Agregar el número específico de días al valor especificado de fecha/hora. | **ADDDAYS (NOW(), 7)** devuelve la fecha y la hora siete días en el futuro. |
| DATETODATETIME (fecha) | Convertir el valor de la fecha especificada en un valor de fecha/hora. | **DATETODATETIME (CompInfo. 'getCurrentDate()')** devuelve la fecha de la sesión actual de Finance and Operations, 24 de diciembre de 2015, como **12/24/2015 12:00:00 AM**. En este ejemplo, **CompInfo** es un origen de datos de ER del tipo **Finance and Operations/Tabla** y hace referencia a la tabla CompanyInfo. |
| NOW () | Devolver la fecha y hora actuales del servidor de aplicaciones de Finance and Operations como valor de fecha/hora. | |
| TODAY () | Devolver la fecha y hora actuales del servidor de aplicaciones de Finance and Operations como valor de fecha- | |
| NULLDATE () | Devolver un valor de fecha **nulo**. | |
| NULLDATETIME () | Devuelve un valor de fecha/hora **nulo**. | |
| DATETIMEFORMAT (fecha y hora, formato) | Convertir el valor de fecha/hora especificado a una cadena en el formato especificado. (Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), "dd-MM-yyyy”)** devuelve la fecha del servidor actual de Finance and Operations, 24 de diciembre de 2015, como **“24-12-2015”**, basado en el formato personalizado especificado. |
| DATETIMEFORMAT (fecha y hora, formato, cultura) | Convertir el valor de fecha/hora especificado a una cadena en el formato y [cultura](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) especificados. (Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (AHORA(), "d", "de")** devuelve la fecha actual del servidor de aplicaciones de Finance and Operations, 24 de diciembre de 2015, como **“24.12.2015"**, basada en la cultura alemana seleccionada. |
| SESSIONTODAY () | Devolver la fecha de sesión actual de Finance and Operations como valor de fecha. | |
| SESSIONNOW () | Devuelve la fecha y la hora de sesión actual de Finance and Operations como valor de fecha/hora. | |
| DATEFORMAT (fecha, formato) | Devuelve una representación de cadena de la fecha especificada en el formato especificado. | **DATEFORMAT (SESSIONTODAY (), "dd-MM-yyyy”)** devuelve la fecha de sesión actual de Finance and Operations, 24 de diciembre de 2015, como **“24-12-2015”**, basado en el formato personalizado especificado. |
| DATEFORMAT (fecha, formato, cultura) | Convertir el valor de fecha especificado en una cadena en el formato y cultura [especificados](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** devuelve la fecha de sesión actual de Finance and Operations, 24 de diciembre de 2015, como **“24.12.2015"**, basada en la cultura alemana seleccionada. |
| DAYOFYEAR (fecha) | Devuelve una representación de número entero de los días entre el 1 de enero y la fecha especificada. | **DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-aaaa"))** devuelve **61**. **DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-aaaa"))** devuelve **1**. |
| DAYS (date 1, date 2) | Devuelve el número de días entre la primera fecha especificada y la segunda fecha especificada. Devuelve un valor positivo cuando la primera fecha es posterior a la segunda fecha, devuelve **0** (cero) cuando la primera fecha es igual a la segunda fecha, o devuelve un valor negativo de otro modo. | **DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS(NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))** devuelve **-1**. |

### <a name="data-conversion-functions"></a>Funciones de conversión de datos

| Función | Descripción | Ejemplo |
|----------|-------------|---------|
| DATETODATETIME (fecha) | Convertir el valor de la fecha especificada en un valor de fecha/hora. | **DATETODATETIME (CompInfo. 'getCurrentDate()')** devuelve la fecha de la sesión actual de Finance and Operations, 24 de diciembre de 2015, como **12/24/2015 12:00:00 AM**. En este ejemplo, **CompInfo** es un origen de datos de ER del tipo **Finance and Operations/Tabla** y hace referencia a la tabla CompanyInfo. |
| DATEVALUE (cadena, formato) | Devuelve una representación de fecha de la cadena especificada en el formato especificado. | **DATEVALUE ("21-Dic-2016", "dd-MMM-yyyy")** devuelve la fecha 21 de diciembre de 2016 basada en un formato especificado y la cultura predeterminada **EN-US** de la aplicación. |
| DATEVALUE (cadena, formato, cultura) | Devuelve una representación de la fecha de la cadena especificada en el formato y la cultura personalizados y especificados. | **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")** devuelve la fecha 21 de enero de 2016 basada en el formato y la cultura personalizados Sin embargo, **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")** generará una excepción para informar al usuario de que la cadena especificada no se reconoce como fecha válida. |
| DATETIMEVALUE (cadena, formato) | Devuelve una representación de fecha/hora de la cadena especificada en el formato especificado. | **DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")** devuelve las 2:55:00 a.m. del 21 de diciembre de 2016, según el formato personalizado y especificado y la cultura predeterminada **EN-US** de la aplicación. |
| DATETIMEVALUE (cadena, formato, cultura) | Devuelve una representación de la fecha/hora de la cadena especificada en el formato y la cultura especificados. | **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")** devuelve las 2:55:00 a.m. del 21 de diciembre de 2016, según el formato y la cultura personalizados y especificados. Sin embargo, **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")** generará una excepción para informar al usuario de que la cadena especificada no se reconoce como fecha/hora válida. |

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
<td>En la siguiente ilustración, se crea un origen de datos <strong>Líneas</strong> como una lista de registro de tres registros. Esta lista se divide en lotes, cada uno contiene hasta dos registros.
<p><a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>La siguiente ilustración muestra el diseño del formato. En este diseño de formato, se crean enlaces al origen de datos <strong>Líneas</strong> para generar una salida en formato XML. Esta salida presenta nodos individuales para cada lote y los registros en él.</p>
<p><a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a></p>
<p>La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado.</p>
<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LIST (registro 1 [, registro 2, …])</td>
<td>Devolver una nueva lista creada a partir de argumentos especificados.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> devuelve un registro vacío, en el que la lista de campos contiene todos los campos de las listas de registros <strong>MainData</strong> y <strong>OtherData</strong>.</td>
</tr>
<tr class="even">
<td>LISTJOIN (lista 1, lista 2, …])</td>
<td>Devolver una nueva lista combinada que se crea a partir de argumentos especificados.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> devuelve una lista de seis registros, donde un campo del tipo de datos <strong>STRING</strong> contiene letras individuales.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (lista)</td>
<td>Devuelve <strong>TRUE</strong> si la lista especificada no contiene elementos. En caso contrario, devuelva <strong>FALSE</strong>.</td>
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
<td>Devuelve una lista nueva aplanada que representa todos los elementos correspondientes a la ruta de acceso especificada. La ruta se debe definir como ruta válida de un origen de datos a un elemento de origen de datos del tipo de datos de la lista de registro. Elementos de datos como la cadena de ruta y la fecha deberían activar un error en el tiempo de diseño del generador de expresiones de ER.</td>
<td>Si especifica <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> como origen de datos (DS), <strong>COUNT( ALLITEMS (DS.Value))</strong> devuelve <strong>3</strong>.</td>
</tr>
<tr class="odd">
<td>ORDERBY (lista [, expresión 1, expresión 2, …])</td>
<td>Devuelve la lista especificada después de que se haya clasificado de acuerdo con los argumentos especificados. Estos argumentos se pueden definir como expresiones.</td>
<td>Si <strong>Proveedor</strong> se configura como un origen de datos de ER que hace referencia a la tabla VendTable, <strong>ORDERBY (Proveedores, nombre de proveedores()</strong> devuelve una lista de proveedores que se clasifica por nombre en orden ascendente.</td>
</tr>
<tr class="even">
<td>REVERSE (lista)</td>
<td>Devolver la lista especificada en orden de clasificación invertido.</td>
<td>Cuando <strong>Proveedor</strong> se configura como origen de datos de ER que hace referencia a la tabla VendTable, <strong>REVERSE (ORDERBY (Proveedores, nombre de proveedores()) )</strong> devuelve la lista de proveedores que se clasifica por nombre en orden descendente.</td>
</tr>
<tr class="odd">
<td>WHERE (lista, condición)</td>
<td>Devuelve la lista especificada después de que se haya filtrado de acuerdo con la condición especificada. La condición especificada se aplica a la lista en memoria. De esta manera, la función <strong>DONDE</strong> se diferencia de la función <strong>FILTRO</strong>.</td>
<td>Si <strong>Proveedor</strong> se configura como origen de datos de ER que hace referencia a la tabla VendTable, <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> devuelve una lista solo de proveedores que pertenece al grupo de proveedores 40.</td>
</tr>
<tr class="even">
<td>ENUMERATE (lista)</td>
<td>Devolver una nueva lista que consta de los registros enumerados de la lista especificada y que expone los siguientes elementos:
<ul>
<li>Registros especificados como listas regulares (componente <strong>Valor</strong>)</li>
<li>El índice de registros actual (componente <strong>Número</strong>)</li>
</ul></td>
<td>En la ilustración siguiente, un origen de datos <strong>Enumerado</strong> se crea como una lista enumerada de registros de proveedor desde el origen de los datos <strong>Proveedores</strong> que hace referencia a la tabla VendTable.
<p><a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a></p>
<p>La siguiente ilustración muestra el formato. En este formato, se crean vínculos de datos para generar una salida en formato XML. Esta salida presenta proveedores individuales como nodos enumerados.</p>
<p><a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a></p>
<p>La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado.</p>
<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>COUNT (lista)</td>
<td>Devuelva el número de registros de la lista especificada, si la lista no está vacía. En caso contrario, devuelva <strong>0</strong> (cero).</td>
<td><strong>COUNT (SPLIT(&quot;abcd&quot; , 3))</strong> devuelve <strong>2</strong>, porque la función <strong>SPLIT</strong> crea una lista que consta de dos registros.</td>
</tr>
<tr class="even">
<td>LISTOFFIELDS (ruta)</td>
<td>Devuelve una lista de registros que se crea a partir de un argumento de uno de los siguientes tipos:
<ul>
<li>Enumeración de modelo</li>
<li>Enumeración de formato</li>
<li>Contenedor</li>
</ul>
<p>La lista que se crea consta de registros con los siguientes campos:</p>
<ul>
<li>Nombre</li>
<li>Etiqueta</li>
<li>Descripción</li>
</ul>
En el tiempo de ejecución, los campos de <strong>Etiqueta</strong> y <strong>Descripción</strong> devuelven valores que se basan en la configuración de idioma del formato.</td>
<td>En la siguiente ilustración, se introduce una enumeración en un modelo de datos.
<p><a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a></p>
<p>La siguiente ilustración muestra estos detalles:</p>
<ul>
<li>La enumeración del modelo se inserta en un informe como origen de datos.</li>
<li>Una expresión del ER utiliza la enumeración de modelo como un parámetro de la función <strong>LISTOFFIELDS</strong>.</li>
<li>Un origen de datos del tipo lista de registro se inserta en un informe mediante la expresión de ER que se crea.</li>
</ul>
<p><a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a></p>
<p>El siguiente ejemplo muestra los elementos del formato de ER que están enlazados al origen de datos del tipo lista de registro creado mediante la función de <strong>LISTOFFIELDS</strong>.</p>
<p><a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a></p>
<p>La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado.</p>
<p><a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a></p>
<blockquote>[!NOTE]<br>
Basado en la configuración de idioma de los elementos del formato del ARCHIVO principal y de la CARPETA, el texto traducido para las etiquetas y las descripciones se introduce en la salida del formato de ER.</blockquote></td>
</tr>
<tr class="odd">
<td>LISTOFFIELDS (ruta, idioma)</td>
<td>Devuelve una lista de registros que se crea desde un argumento, como una enumeración de modelo, una enumeración de formato o un contenedor. La lista que se crea consta de registros con los siguientes campos:
<ul>
<li>Nombre</li>
<li>Etiqueta</li>
<li>Descripción</li>
<li>Traducido</li>
</ul>
<p>En el tiempo de ejecución, los campos de <strong>Etiqueta</strong> y <strong>Descripción</strong> devuelven valores que se basan en la configuración de idioma del formato y el idioma especificado. El campo <strong>Traducido</strong> indica que el campo <strong>Etiqueta</strong> se ha traducido al idioma especificado.</td>
<td>Por ejemplo, utiliza el tipo de origen de datos <strong>Campo calculado</strong> para configurar los orígenes de datos <strong>enumType_de</strong> y <strong>enumType_deCH</strong> para la enumeración del modelo de datos <strong>enumType</strong>:
<ul>
<li>enumType_de = <strong>LISTOFFIELDS</strong> (enumType, &quot;de&quot;)</li>
<li>enumType_deCH = <strong>LISTOFFIELDS</strong> (enumType, &quot;de-CH&quot;)</li>
</ul>
En este caso, puede usar la siguienteexpresión para obtener la etiqueta del valor de enumeración en alemán suizo, si esta traducción está disponible. Si la traducción en alemán suizo no está disponible, la etiqueta está en alemán: <strong>Si (No (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)</strong>.</td>
</tr>
<tr class="even">
<td>STRINGJOIN (lista, nombre de campo, delimitador)</td>
<td>Devuelve una cadena que consta de valores concatenados del campo especificado de la lista especificada. Los valores están separados por el delimitador especificado.</td>

<td>Si introduce <strong>SPLIT(&quot;abc&quot; , 1)</strong> como un origen de datos (DS), la expresión <strong>STRINGJOIN (DS, DS.Value, &quot;:&quot;)</strong> devuelve <strong>&quot;a</strong><strong>:b</strong><strong>:c&quot;</strong>.</td>

</tr>
<tr class="odd">
<td>SPLITLISTBYLIMIT (lista, valor límite, origen del límite)</td>
<td>Divide la lista especificada en una nueva lista de sublistas y devuelve el resultado en contenido de la lista del registro. El parámetro de valor límite define el valor del límite para dividir la lista original. El parámetro de origen del límite define el paso en que la suma total aumenta. El límite no se aplica a un único artículo de la lista original si el origen del límite supera el límite definido.</td>
<td>Las siguientes ilustraciones muestran un formato y los orígenes de datos que se usan para este. 
<p><a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a></p>
<p><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a></p>
<p>La siguiente ilustración muestra el resultado cuando se ejecuta el formato. En este caso, la salida es una lista plana de artículos de mercancía.</p>
<p><a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a></p>
<p>En las siguientes ilustraciones, se ha ajustado el mismo formato para que presente la lista de artículos de mercancía en lotes cuando un único lote debe incluir mercancías y el peso total no debe superar el límite de 9.</p>
<p><a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a></p>
<p><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a></p>
<p>La siguiente ilustración muestra el resultado cuando se ejecuta el formato ajustado.</p>
<p><a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a></p>
<blockquote>[!NOTE]<br>
El límite no se aplica al último artículo de la lista original ya que el valor (11) del origen de su límite (peso) supera el límite definido (9). Use la función <strong>DONDE</strong> o la expresión <strong>Habilitado</strong> del elemento de formato correspondiente para omitir (saltar) las sublistas durante la generación de informes, si es necesario.</blockquote></td>
</tr>
<tr class="even">
<td>FILTRAR (lista, condición)</td>
<td>Devuelve la lista especificada después de que se haya modificado la consulta para filtrar por la condición especificada. Esta función difiere de la función <strong>DONDE</strong>, ya que la condición especificada se aplica a cualquier origen de datos de ER del tipo <strong>Registros de la tabla</strong> a nivel de la base de datos. La lista y la condición se pueden definir mediante tablas y relaciones.</td>
  <td>Si <strong>Proveedor</strong> se configura como origen de datos de ER que hace referencia a la tabla VendTable, <strong>FILTER (Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> devuelve una lista solo de proveedores que pertenece al grupo de proveedores 40. Si <strong>Proveedor</strong> se configura como origen de datos de ER que hace referencia a la tabla <strong>VendTable</strong> y al <strong>parmVendorBankGroup</strong> que está configurado como origen de datos de ER devuelve el valor en el tipo de datos de la cadena, <strong>FILTRO (Vendor.'&lt;Relations'.VendBankAccount, Vendor.'&lt;Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)</strong> devuelve una lista solo de cuentas de proveedores que pertenecen a un grupo bancario específico.</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Funciones lógicas

| Función | Descripción | Ejemplo |
|----------|-------------|---------|
| CASE (expression, option 1, result 1 \[, option 2, result 2\] … \[, default result\]) | Evaluar el valor de la expresión especificado con las opciones alternativas especificadas. Devolver el resultado de la opción que es igual al valor de la expresión. De lo contrario, devuelve el resultado predeterminado opcional, si se especifica un resultado predeterminado. (El resultado predeterminado es el último parámetro al que no le antecede una opción.) | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "INVIERNO", "11", "INVIERNO", "12", "INVIERNO", "")** devuelve la cadena **"INVIERNO"** cuando la fecha de la sesión de Finance and Operations actual se encuentra entre octubre y diciembre. En caso contrario, devuelve una cadena en blanco. |
| SI (condición, valor 1, valor 2) | Devuelve el primer valor especificado cuando se cumple la condición especificada. De lo contrario, devuelva el segundo valor especificado. Si el valor 1 y el valor 2 son registros o listas de registro, el resultado tiene solo los campos que existan en ambas listas. | **IF (1=2, "se cumple la condición", "no se cumple la condición")** devuelve la cadena **"no se cumple la condición"**. |
| NOT (condición) | Devuelve el valor lógico invertido de la condición determinada. | **NOT (TRUE)** devuelve **FALSE**. |
| AND (condición 1\[, condición 2, …\]) | Devolver **TRUE** si *todas* las condiciones especificadas son verdaderas. En caso contrario, devuelva **FALSE**. | **AND (1=1, "a"="a")** devuelve **TRUE**. **AND (1=2, "a"="a")** devuelve **FALSE**. |
| OR (condición 1\[, condición 2, …\]) | Devolver **FALSE** si *todas* las condiciones especificadas son falsa. Devolver **TRUE** si *cualquier* condición especificada es verdadera. | **OR (1=2, "a"="a")** devuelve **TRUE**. |

### <a name="mathematical-functions"></a>Funciones matemáticas

| Función | Descripción | Ejemplo |
|----------|-------------|---------|
| ABS (número) | Devuelve el valor absoluto del número especificado. (Es decir, devuelva el número sin su signo). | **ABS (-1)** devuelve **1**. |
| POWER (número, potencia) | Devolver el resultado de elevar el número positivo especificado a la potencia especificada. | **POWER (10, 2)** devuelve **100**. |
| NUMBERVALUE (cadena, separador decimal, separador de agrupación de dígitos) | Convertir la cadena especificada en un número. El separador decimal especificado se utiliza entre el número entero y las partes fraccionarias de un número decimal. El separador de agrupación de dígitos especificado se utiliza como separador de millares. | **NUMBERVALUE("1 234,56", ",", " ")** devuelve el valor **1234,56**. |
| VALUE (cadena) | Convertir la cadena especificada en un número. Las comas y los caracteres de punto (.) se consideran separadores decimales y los guiones iniciales (-) se usan como signo negativo. Genere una excepción si la cadena especificada contiene otros caracteres no numéricos. | **VALUE ("1 234,56")** genera una excepción. |
| ROUND (número, decimales) | Devuelve el número especificado después de que se haya redondeado al número especificado de posiciones decimales:<ul><li>Si el valor de los parámetros decimales es superior a 0 (cero), el número especificado se redondea a ese número de decimales.</li><li>Si el valor de los parámetros decimales es **0** (cero), el número especificado se redondea al número entero más cercano.</li><li>Si el valor de los parámetros decimales es inferior a 0 (cero), el número especificado se redondea a la izquierda de la coma decimal.</li></ul> | **ROUND (1200,767, 2)** redondea a dos lugares decimales y devuelve **1200,77**. **ROUND (1200.767, -3)** redondea al múltiplo más cercano de 1.000 y devuelve **1000**. |
| ROUNDDOWN (número, decimales) | Devolve el número especificado después de que se haya redondeado hacia abajo al número especificado de posiciones decimales.<blockquote>[!NOTE]<br>Esta función se comporta como <strong>ROUND</strong>, pero siempre redondea hacia abajo del número especificado (hacia cero).</blockquote> | **ROUNDDOWN (1200,767, 2)** redondea hacia abajo a dos lugares decimales y devuelve **1200,76**. **ROUNDDOWN (1700.767, -3)** redondea hacia abajo al múltiplo más cercano de 1.000 y devuelve **1000**. |
| ROUNDUP (número, decimales) | Devuelve el número especificado después de que se haya redondeado hacia arriba al número especificado de posiciones decimales.<blockquote>[!NOTE]<br>Esta función se comporta como <strong>ROUND</strong>, pero siempre redondea hacia arriba el número especificado (lejos de cero).</blockquote> | **ROUNDUP (1200,763, 2)** redondea hacia arriba a dos lugares decimales y devuelve **1200,77**. **ROUNDUP (1200.767, -3)** redondea hacia arriba al múltiplo más cercano de 1.000 y devuelve **2000**. |

### <a name="data-conversion-functions"></a>Funciones de conversión de datos

| Función | Descripción | Ejemplo |
|----------|-------------|---------|
| VALUE (cadena) | Convertir la cadena especificada en un número. Las comas y los caracteres de punto (.) se consideran separadores decimales y los guiones iniciales (-) se usan como signo negativo. Genere una excepción si la cadena especificada contiene otros caracteres no numéricos. | **VALUE ("1 234,56")** genera una excepción. |
| NUMBERVALUE (cadena, separador decimal, separador de agrupación de dígitos) | Convertir la cadena especificada en un número. El separador decimal especificado se utiliza entre el número entero y las partes fraccionarias de un número decimal. El separador de agrupación de dígitos especificado se utiliza como separador de millares. | **NUMBERVALUE("1 234,56", ",", " ")** devuelve **1234.56**. |
| INTVALUE (cadena) | Devuelve una representación de un entero de la cadena especificada. Se trunca cualquier posición decimal. | **INTVALUE ("100.77")** devuelve **100**. |
| INTVALUE (número) | Devuelve una representación de un entero del número especificado. Se trunca cualquier posición decimal. | **INTVALUE (-100,77)** devuelve **100**. |
| INT64VALUE (cadena) | Devuelve una representación int64 de la cadena especificada. Se trunca cualquier posición decimal. | **INT64VALUE ("22565422744")** devuelve **22565422744**. |
| INT64VALUE (número) | Devuelve una representación int64 del número especificado. Se trunca cualquier posición decimal. | **INT64VALUE (22565422744.00)** devuelve **22565422744**. |

### <a name="record-functions"></a>Funciones de registro

| Función | Descripción | Ejemplo |
|----------|-------------|---------|
| NULLCONTAINER (lista) | Devolver un registro **nulo** con la misma estructura que el registro o la lista de registros especificada.<blockquote>[!NOTE]<br>Esta función es obsoleta. Use <strong>EMPTYRECORD</strong> en su lugar.</blockquote> | **NULLCONTAINER (SPLIT ("abc", 1))** devuelve un nuevo registro vacía que tiene la misma estructura que la lista que se devuelve por la función **SPLIT**. |
| EMPTYRECORD (registro) | Devolver un registro **nulo** con la misma estructura que el registro o la lista de registros especificada.<blockquote>[!NOTE]<br>Un registro <strong>nulo</strong> es un registro donde todos los campos tienen un valor vacío. Un valor vacío es <strong>0</strong> (cero) para números, una cadena vacía para las cadenas, y así sucesivamente.</blockquote> | **EMPTYRECORD (SPLIT ("abc", 1))** devuelve un nuevo registro vacía que tiene la misma estructura que la lista que se devuelve por la función **SPLIT**. |

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
<td>Devuelve la cadena especificada después de que se haya convertido en letras mayúsculas.</td>
<td><strong>UPPER (&quot;Muestra&quot;)</strong> devuelve <strong>&quot;MUESTRA&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LOWER (cadena)</td>
<td>Devuelve la cadena especificada después de que se haya convertido en letras minúsculas.</td>
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
<td><strong>CHAR (255)</strong> devuelve <strong>&quot;ÿ&quot;</strong>.
<blockquote>[!NOTE]<br>
La cadena que esta función devuelve depende de la codificación seleccionada en el elemento de formato del ARCHIVO principal. Para la lista de codificaciones admitidas, consulte <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Clase de codificación</a>.</blockquote>
</td>
</tr>
<tr class="even">
<td>CONCATENATE (cadena 1 [, cadena 2, …])</td>
<td>Devolve todas las cadenas de texto especificadas después de que hayan unido en una cadena.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> devuelve <strong>&quot;abcdef&quot;</strong>.
<blockquote>[!NOTE]<br>
La expresión <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> también devuelve <strong>&quot;abcdef&quot;</strong>.</blockquote>
</td>
</tr>
<tr class="odd">
<td>TRANSLATE (cadena, patrón, sustitución)</td>
<td>Devuelve la cadena especificada después de que todas las apariciones de los caracteres de la cadena de patrones especificados se hayan sustituido por los caracteres del puesto correspondiente en la cadena de sustitución especificada.</td>
<td><strong>TRANSLATE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> reemplaza el patrón <strong>&quot;cd&quot;</strong> por la cadena <strong>&quot;GH&quot;</strong> y devuelve <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="even">
<td>REPLACE (cadena, patrón, sustitución, indicador de expresión regular)</td>
<td>Cuando es el indicador de expresión regular especificada es <strong>verdadero</strong>, devuelve la cadena especificada después de que se haya modificado aplicando la expresión normal que se especifica como argumento de patrón para esta función. Esta expresión se usa para buscar los caracteres que se deben sustituir. Los caracteres del argumento de sustitución especificado se usan para reemplazar los caracteres que se encuentran. Cuando el indicador de la expresión regular especificada es <strong>falso</strong>, esta función se comporta como <strong>TRANSLATE</strong>.</td>
<td><strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, true)</strong> aplica una expresión regular que quita todos los símbolos no numéricos y devuelve <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, false)</strong> reemplaza el patrón <strong>&quot;cd&quot;</strong> por la cadena <strong>&quot;GH&quot;</strong> y devuelve <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TEXT (entrada)</td>
<td>Devuelve la entrada especificada después de que se haya convertido en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de Finance and Operations. Para los valores del tipo <strong>real</strong>, la conversión de la cadena se limita a dos decimales.</td>
<td>Si se define la configuración regional del servidor de instancias de Finance and Operations como <strong>EN-US</strong>, <strong>TEXT (NOW ())</strong> devuelve la fecha de la sesión de Finance and Operations actual, el 17 de diciembre de 2015, como la cadena de texto <strong>&quot;17/12/2015 07:59:23 a.m&quot;</strong>. <strong>TEXT (1/3)</strong> devuelve <strong>&quot;0,33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMAT (cadena 1, cadena 2 [, cadena 3, …])</td>
<td>Devuelve la cadena especificada después de que se haya formateado sustituyendo cualquier aparición de <strong>%N</strong> con el argumento <em>n</em>ésimo. Los argumentos son cadenas. Si no se proporciona un argumento para un parámetro, el parámetro se devuelve como <strong>&quot;%N&quot;</strong> en la cadena. Para los valores del tipo <strong>real</strong>, la conversión de la cadena se limita a dos decimales.</td>
<td>En la siguiente ilustración, el origen de datos <strong>PaymentModel</strong> devuelve la lista de registros de clientes mediante el componente <strong>Cliente</strong> y el valor de la fecha de procesamiento mediante el campo <strong>ProcessingDate</strong>.
<p><a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a></p>
<p>En el formato ER diseñado para generar un archivo electrónico para los clientes seleccionados, <strong>PaymentModel</strong> se selecciona como origen de datos y controla el flujo de proceso. Se genera una excepción para informar al usuario cuando se detiene un cliente seleccionado para la fecha en la que se procesa el informe. La fórmula que está diseñada para este tipo de control de proceso puede usar los recursos siguientes:</p>
<ul>
<li>La etiqueta SYS70894 de Finance and Operations tiene el siguiente texto:
<ul>
<li><strong>Para el idioma EN-US:</strong> &quot;Nothing to print&quot;</li>
<li><strong>Para el idioma DE:</strong> &quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>La etiqueta SYS18389 de Finance and Operations tiene el siguiente texto:
<ul>
<li><strong>Para el idioma EN-US:</strong> &quot;Customer %1 is stopped for %2.&quot;</li>
<li><strong>Para el idioma DE:</strong> &quot;Debitor &#39;%1&#39; wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
<p>Esta es la fórmula que se puede diseñar:</p>
<p>FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;))</p>
<p>Si se procesa un informe para el cliente <strong>Litware Retail</strong> el 17 de diciembre de 2015, en la cultura <strong>EN-US</strong> y el idioma <strong>EN-US</strong>, esta fórmula devuelve el siguiente texto, que puede presentarse como mensaje de excepción para el usuario:</p>
<p>&quot;Nothing to print. Customer Litware Retail is stopped for 12/17/2015.&quot;</p>
<p>Si el mismo informe se procesa para el cliente <strong>Litware Retail</strong> el 17 de diciembre de 2015, en la cultura <strong>DE</strong> y el idioma <strong>DE</strong>, esta fórmula devuelve el siguiente texto, que usa un formato de fecha diferente:</p>
<p>&quot;Nichts zu drucken. Debitor &#39;Litware Retail&#39; wird für 17.12.2015 gesperrt.&quot;</p>
<blockquote>[!NOTE]<br>
La sintaxis siguiente se aplica en las fórmulas de ER para las etiquetas:
<ul>
<li><strong>Para las etiquetas de los recursos de Finance and Operations:</strong> <strong>@&quot;X&quot;</strong>, donde la X es el identificador de la etiqueta en el Árbol de objetos de aplicación (AOT)</li>
<li><strong>Para las etiquetas que se encuentran en las configuraciones de ER:</strong> <strong>@&quot;GER_LABEL:X&quot;</strong>, donde X es el id. de etiqueta de la configuración de ER</li>
</ul></blockquote></td>
</tr>
<tr class="odd">
<td>NUMBERFORMAT (número, formato)</td>
<td>Devuelve una representación de la cadena del número especificado en el formato especificado. (Para obtener información sobre los formatos admitidos, consulte <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">estándar</a> y <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">personalizado</a>). El contexto en el que se ejecuta esta función determina la cultura que se usa para el formato de los números.</td>
<td>Para la referencia cultural EN-US, <strong>NUMBERFORMAT (0,45, &quot;p&quot;)</strong> devuelve <strong>&quot;45,00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> devuelve <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (número, idioma, divisa, indicador del nombre de la divisa de impresión, separadores decimales)</td>
<td>Devuelve el número específico después de que se haya explicado (convertido) a cadenas de texto en el idioma especificado. El código de idioma es opcional. Cuando se define como una cadena vacía, en su lugar se utiliza el código de idioma para el contexto en ejecución. (El código de idioma del contexto en ejecución se define para una carpeta o un archivo que genera.) El código de divisa también es opcional. Cuando se define como una cadena vacía, se utiliza la divisa de la empresa.
<blockquote>[!NOTE]<br>
Los parámetros de indicador del nombre de la divisa de impresión y de puntos decimales se analizan solo para los códigos de idioma siguientes: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong>, and <strong>RU</strong>. Asimismo, el parámetro de indicador del nombre de la divisa de impesión se analiza solo para las empresas de Finance and Operations en las que el contexto del país o la región admite la declinación de nombres de divisa.</blockquote></td>
<td><strong>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2)</strong> devuelve <strong>&quot;Mil doscientos treinta y cuatro con 56&quot;</strong>. <strong>NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0)</strong> devuelve <strong>&quot;Sto dwadzieścia&quot;</strong>. <strong>NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2)</strong> devuelve <strong>&quot;Сто двадцать евро 21 евроцент&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>PADLEFT (cadena, longitud, caracteres de relleno)</td>
<td>Devuelve una cadena de la longitud especificada en la que el inicio de la cadena especificada se rellena con los caracteres especificados.</td>
<td><strong>PADLEFT (&quot;1234&quot;, 10, &quot;&nbsp;&quot;)</strong> devuelve la cadena de texto <strong>&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234&quot;</strong>.</td>
</tr>
<tr class="even">
<td>TRIM (cadena)</td>
<td>Devuelve la cadena de texto especificada después de haber truncado los espacios principales y finales, y después de haber quitado múltiples espacios entre palabras.</td>
<td><strong>TRIM (&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Sample&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;text&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&quot;)</strong> devuelve <strong>&quot;Texto de ejemplo&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>GETENUMVALUEBYNAME (ruta del origen de datos de enumeración, texto de etiqueta del valor de enumeración)</td>
<td>Devuelve un valor del origen de datos de enumeración especificado por el texto especificado basado en el texto especificado de la etiqueta de enumeración.</td>
<td>En la siguiente ilustración, la enumeración <strong>ReportDirection</strong> se introduce en un modelo de datos. Tenga en cuenta que las etiquetas se definen por valores de enumeración.
<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>La siguiente ilustración muestra estos detalles:</p>
<ul>
<li>La enumeración del modelo <strong>ReportDirection</strong> se inserta en un informe como un origen de datos, <strong>$Direction</strong>.</li>
<li>Una expresión del ER, <strong>$IsArrivals</strong>, está diseñada para usar la enumeración de modelo como un parámetro de esta función. El valor de esta expresión es <strong>TRUE</strong>.</li>
</ul>
<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></td>
</tr>
</tbody>
</table>

### <a name="data-conversion-functions"></a>Funciones de conversión de datos

| Función | Descripción | Ejemplo |
|----------|-------------|---------|
| TEXT (entrada) | Devuelve la entrada especificada después de que se haya convertido en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de Finance and Operations. Para los valores del tipo **real**, la conversión de la cadena se limita a dos decimales. | Si se define la configuración regional del servidor de instancias de Finance and Operations como **EN-US**, **TEXT (NOW ())** devuelve la fecha de la sesión de Finance and Operations actual, el 17 de diciembre de 2015, como la cadena de texto **"17/12/2015 07:59:23 a.m"**. **TEXT (1/3)** devuelve **"0,33"**. |
| QRCODE (cadena) | Devuelve una imagen de código QR en formato binario base64 para la cadena especificada. | **QRCODE ("Texto de muestra")** devuelve **U2FtcGxlIHRleHQ=**. |

### <a name="data-collection-functions"></a>Funciones de recopilación de datos

| Función | Descripción | Ejemplo |
|----------|-------------|---------|
| FORMATELEMENTNAME () | Devuelve el nombre del elemento de formato actual. Devuelve una cadena vacía cuando el indicador **Recopilar de los detalles de salida** de los archivos actuales está desactivado. | Para obtener más información sobre cómo usar esta función, consulte la guía de tareas de los **datos de uso de ER del formato generados para contar y calcular**, que forma parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**. |
| SUMIFS (cadena clave para sumar, cadena de criterio range1, cadena de criterio value1 \[ cadena de criterio range2, cadena de criterio value2, …\]) | Devuelve la suma de los valores de nodos XML (donde el nombre se define como una clave) que se ha obtenido durante la ejecución del formato y que cumple con las condiciones especificadas (pares de rangos y de valores). Devuelve un valor **0** (cero) cuando el indicador **Recopilar detalles de salida** de los archivos actuales está desactivado. | |
| SUMIF (cadena clave para sumar, cadena de criterio de rango, cadena de criterio de valor) | Devuelve la suma de los valores de nodos XML (donde el nombre se define como una clave) que se ha obtenido durante la ejecución del formato y que cumple con la condición especificada (rango y valor). Devuelve un valor **0** (cero) cuando el indicador **Recopilar detalles de salida** de los archivos actuales está desactivado. | |
| COUNTIFS (cadena de criterio range1, cadena de criterio value1 \[, cadena de criterio range2, cadena de criterio value2, …\]) | Devuelve el número de nodos XML que se ha obtenido durante esta ejecución del formato y que cumple con las condiciones especificadas (pares de rangos y de valores). Devuelve un valor **0** (cero) cuando el indicador **Recopilar detalles de salida** de los archivos actuales está desactivado. | |
| COUNTIF (cadena de criterios de rango, cadena de criterios de valor) | Devuelve un número de nodos de XML que se ha obtenido durante esta ejecución del formato y que cumple con la condición especificada (rango y valor). Devuelve un valor **0** (cero) cuando el indicador **Recopilar detalles de salida** de los archivos actuales está desactivado. | |
| COLLECTEDLIST (cadena de criterio range1, cadena de criterio value1 \[, cadena de criterio range2, cadena de criterio value2, …\]) | Devuelve la lista de valores de nodos de XML que se ha obtenido durante esta ejecución del formato y que cumple con las condiciones introducidas (rango y valor). Devuelve una lista vacía cuando el indicador **Recopilar detalles de salida** de los archivos actuales está desactivado. | |

### <a name="other-business-domainspecific-functions"></a>Otras funciones (específicas de dominio empresarial)

| Función | Descripción | Ejemplo |
|----------|-------------|---------|
| CONVERTCURRENCY (importe, divisa de origen, divisa de destino, fecha, empresa) | Convierta el importe monetario especificado de la divisa de origen especificada a la divisa de destino especificada con la configuración de la empresa especificada de Finance and Operations en la fecha especificada. | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** devuelve el equivalente de un euro en dólares estadounidenses en la fecha de la sesión actual, en función de la configuración para la empresa de DEMF. |
| ROUNDAMOUNT (número, decimales, regla de redondeo) | Redondee el importe especificado para el número de posiciones decimales especificadas de acuerdo con la regla de redondeo especificada.<blockquote>[!NOTE]<br>La regla de redondeo se debe especificar como un valor de la enumeración <strong>RoundOffType</strong> de Finance and Operations.</blockquote> | Si el parámetro **model.RoundOff** se establece en **Hacia abajo**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** devuelve el valor **1000,78**. Si el parámetro **model.RoundOff** se establece en **Normal** o **Redondeo por arriba**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** devuelve el valor **1000,79**. |
| CURCredRef (dígitos) | Devuelve una referencia de acreedor basada en los dígitos del número de factura especificado. | **CURCredRef (“VEND-200002”)** devuelve **“2200002"**. |
| MOD\_97 (dígitos) | Devuelve una referencia de acreedor como expresión MOD97, basada en los dígitos del número de factura especificado. | **MOD\_97 ("VEND-200002")** devuelve **"20000285"**. |
| ISOCredRef (dígitos) | Devuelve una referencia de acreedor de la Organización Internacional de Normalización (ISO), basada en los dígitos y los símbolos alfabéticos del número de factura especificado.<blockquote>[!NOTE]<br>Para anular símbolos de los alfabetos que no son compatibles con ISO, el parámetro de entrada se debe traducir antes de que se pase a esta función.</blockquote> | **ISOCredRef (“VEND-200002”)** devuelve **“RF23VEND-200002"**. |
| CN\_GBT\_AdditionalDimensionID (cadena, número) | Obtener el identificador de dimensión financiera adicional. Las dimensiones se representan en esta cadena como identificadores separados por comas. En esta cadena, los números definen el código de la secuencia de la dimensión solicitada. | **CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3)** devuelve **"CC"**. |
| GetCurrentCompany () | Devuelve la representación de texto del código para la entidad jurídica (empresa) con la que el usuario está registrado actualmente. | **GETCURRENTCOMPANY ()** devuelve **USMF** para un usuario que está registrado en la empresa **Contoso Entertainment System USA** en Finance and Operations. |
| CH\_BANK\_MOD\_10 (dígitos) | Devuelve una referencia de acreedor como una expresión MOD10, basada en los dígitos del número de factura especificado. | **CH\_BANK\_MOD\_10 ("VEND-200002")** devuelve **3**. |
| FA\_SUM (código de activo fijo, código del modelo de valor, fecha inicial, fecha final) | Devuelve el contenedor de datos preparado del importe de activos fijos para un período especificado. | **FA\_SUM ("COMP-000001", "Actual", Date1, Date2)** devuelve el contenedor de datos preparado del activo fijo **"COMP-000001"** que tiene el modelo de valor **"Actual"** para un período desde **Date1** a **Date2**. |
| FA\_BALANCE (código de activo fijo, código del modelo de valor, año de notificación, fecha de notificación) | Devuelve el contenedor de datos preparado del saldo de activos fijos. El año de notificación debe especificarse como valor de la enumeración de Finance and Operations **AssetYear**. | **FA\_SUM ("COMP-000001", "Actual", AxEnumAssetYear.ThisYear, SESSIONTODAY ())** devuelve el contenedor preparado de los datos de los saldos del activo fijo **"COMP-000001"** que tiene el modelo de valor **"Actual"** en la fecha de la sesión actual de Finance and Operations. |
| TABLENAME2ID (cadena) | Devuelve la representación en entero del Id. de una tabla para el nombre de tabla especificado. | **TABLENAME2ID ("Intrastat")** devuelve **1510**. |
| ISVALIDCHARACTERISO7064 (cadena) | Devuelve el valor booleano **TRUE** cuando la cadena especificada representa un número internacional de cuenta bancaria válido (IBAN). De lo contrario, devuelva el valor booleano **FALSE**. | **ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")** devuelve **TRUE**. **ISVALIDCHARACTERISO7064 ("AT61")** devuelve **FALSE**. |

### <a name="functions-list-extension"></a>Extensión de la lista de funciones

ER le permite ampliar la lista de funciones que se usan en las expresiones de ER. Son necesarios algunos esfuerzos de ingeniería. Para obtener información detallada, vea [Ampliar la lista de funciones de informes electrónicos](general-electronic-reporting-formulas-list-extension.md).

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Ampliar la lista de funciones de Informes electrónicos (ER)](general-electronic-reporting-formulas-list-extension.md)


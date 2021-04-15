---
title: Diseñador de fórmulas en los informes electrónicos (ER)
description: Este tema proporciona información general sobre cómo usar el diseñador de fórmulas en los informes electrónicos (ER).
author: NickSelin
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dcede0818630329a5608c2d294c9c9f4f749f13
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750141"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>Diseñador de fórmulas en los informes electrónicos (ER)

[!include [banner](../includes/banner.md)]

Este tema explica cómo usar el diseñador de fórmula en Informes electrónicos (ER). Cuando diseña un formato para un documento electrónico específico en ER, puede usar fórmulas para transformar datos de modo que cumplan los requisitos para el cumplimiento y el formato de ese documento. Estas fórmulas se asemejan a fórmulas en Microsoft Excel. Se admiten diversos tipos de funciones en las fórmulas: de texto, de fecha y hora, matemáticas, lógicas, de información y de conversión de tipos de datos, así como otras funciones específicas del dominio empresarial.

## <a name="formula-designer-overview"></a>Visión general del diseñador de fórmulas

Los ER admiten el diseñador de fórmulas. Por tanto, en el momento del diseño, puede configurar las expresiones que se pueden usar para las siguientes tareas en tiempo de ejecución:

- Transforme los datos que se reciben de una base de datos de una aplicación, y que se deben introducir en un modelo de datos de ER designado para ser un origen de datos para los formatos de ER. (Por ejemplo, estas transformaciones pueden incluir el filtrado, la agrupación y la conversión de tipos de datos.)
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

## <a name="data-binding"></a><a name="Binding"></a>Vinculación de datos

El diseñador de fórmulas de ER se puede usar para definir una expresión que transforme los datos que se reciben desde orígenes de datos de forma que se puedan introducir en el consumidor de datos en tiempo de ejecución:

- Desde los orígenes de datos de la aplicación y los parámetros de tiempo de ejecución a un modelo de datos de ER
- Desde un modelo de datos de ER a un formato de ER
- Desde los orígenes de datos de la aplicación y los parámetros de tiempo de ejecución a un modelo de datos de formato ER

En la ilustración siguiente se muestra el diseño de una expresión de este tipo. En este ejemplo, la expresión redondea el valor del campo **Intrastat.AmountMST** de la tabla Intrastat hasta dos posiciones decimales y luego devuelve el valor redondeado.

[![Expresión de vinculación de datos](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

En la ilustración siguiente se muestra cómo usar una expresión de este tipo. En este ejemplo, el resultado de la expresión diseñada se introduce en el componente **Transaction.InvoicedAmount** del modelo de datos **Modelo de notificación tributaria**.

[![Expresión de vinculación de datos empleada](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

En tiempo de ejecución, la fórmula designada, `ROUND (Intrastat.AmountMST, 2)`, redondea el valor del campo **AmountMST** para cada registro de la tabla Intrastat a dos posiciones decimales. A continuación, especifique el valor redondeado en el componente **Transaction.InvoicedAmount** del modelo de datos **Informe de impuestos** .

## <a name="data-formatting"></a><a name="Transformation"></a>Formato de datos

El diseñador de fórmula de ER se puede usar para definir una expresión que formatea datos que se reciben de orígenes de datos, para que se puedan enviar como parte de la generación de un documento electrónico. Es posible que tenga un formato que debe aplicarse como regla típica que se debe volver a usar para un formato. En este caso, puede introducir ese formato una vez en la configuración del formato, como una transformación nombrada que tiene una expresión del formato. Esta transformación nombrada se puede vincular a continuación a varios componentes de formato si el resultado debe formatearse de acuerdo con la expresión que creó.

En la ilustración siguiente se muestra el diseño de una transformación de este tipo. En este ejemplo, la transformación **TrimmedString** trunca datos entrantes del tipo de datos *Secuencia* eliminando espacios principales y finales. A continuación, devuelve el valor de cadena truncado.

[![Transformación](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

En la ilustración siguiente se muestra cómo usar una transformación de este tipo. En este ejemplo, varios componentes de formato envían texto como salida al documento electrónico de generación en el tiempo de ejecución. Todos estos componentes de formato hacen referencia a la transformación **TrimmedString** por nombre.

[![Transformación que se usa](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Cuando los componentes del formato, como el componente **partyName** en la ilustración anterior, hacen referencia a la transformación **TrimmedString**, la transformación envía texto como salida al documento electrónico de generación. Este texto no incluye espacios principales y finales.

Si tiene un formato que se debe aplicar de forma individual, puede introducir ese formato como una expresión individual de una vinculación de un componente de formato concreto. En la ilustración siguiente se muestra una expresión de este tipo. En este ejemplo, el componente del formato **partyType** se vincula al origen de datos mediante una expresión que convierte los datos entrantes del campo **Model.Company.RegistrationType** del origen de datos en texto en mayúsculas. A continuación, la expresión envía ese texto como salida al documento electrónico de generación.

[![Aplicar formato a un componente individual](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

## <a name="process-flow-control"></a><a name="Validation"></a>Control de flujo de proceso

El diseñador de fórmulas de ER se puede usar para definir las expresiones que controlan el flujo de proceso de documentos electrónicos de generación. Se pueden llevar a cabo las siguientes tareas:

- Definir las condiciones que determinan cuándo un proceso de creación de documento se debe detener.
- Especifique expresiones que creen mensajes para el usuario acerca de los procesos detenidos o lancen mensajes de registro de ejecución acerca de continuar con el proceso de la generación del informe.
- Especifique los nombres de archivo de los documentos electrónicos de generación y las condiciones de control de su creación.

Cada regla de control de flujo de proceso está diseñada como validación individual. En la ilustración siguiente se muestra una validación de este tipo. Esta es una explicación de la configuración de este ejemplo:

- La validación se evalúa cuando se crea el nodo **INSTAT** durante la generación del archivo XML.
- Si la lista de transacciones está vacía, la validación detiene el proceso de ejecución y devuelve **FALSE**.
- La validación devuelve un mensaje de error que incluye el texto de la etiqueta SYS70894 en el idioma preferido del usuario.

[![Validación](./media/picture-validation.jpg)](./media/picture-validation.jpg)

El diseñador de fórmulas de ER también se puede usar para generar un nombre de archivo para un documento electrónico que se está generando y para controlar el proceso de creación del archivo. En la ilustración siguiente se muestra el diseño de un control de flujo de proceso de este tipo. Esta es una explicación de la configuración de este ejemplo:

- La lista de registros de origen de datos **model.intrastat** se divide en lotes. Cada lote contiene hasta 1000 registros.
- La salida crea un archivo zip que contiene un archivo en formato XML para cada lote que se ha creado.
- Una expresión devuelve un nombre de archivo para documentos electrónicos de generación concatenando el nombre de archivo y la extensión del nombre de archivo. Para el segundo lote y todos los lotes posteriores, el nombre de archivo contiene el id. de lote como sufijo.
- Una expresión habilita (devolviendo **TRUE**) el proceso de creación de archivos para lotes que contengan al menos un registro.

[![Control de flujo de proceso](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

## <a name="document-content-control"></a><a name="Enabled"></a>Control del contenido de los documentos

El diseñador de fórmulas de ER se puede usar para configurar expresiones que controlan qué datos se colocarán en los documentos electrónicos generados en tiempo de ejecución. Las expresiones pueden habilitar o deshabilitar la salida de elementos específicos del formato, en función de datos de procesamiento y la lógica configurada. Estas expresiones se puede especificar para un único elemento de formato en el campo **Habilitado** en la pestaña **Asignación** en la página **Diseñador de operaciones**. Puede introducir las expresiones como una condición lógica que devuelve un valor de tipo *Booleano*:

- Si la condición devuelve **Verdadero**, se ejecuta el elemento de formato actual.
- Si la condición devuelve **Falso**, se omite el elemento de formato actual.

En la ilustración siguiente se muestran expresiones de este tipo. (Se utiliza como ejemplo la versión 11.12.11 de la configuración de formato **Transferencia de crédito ISO20022 (NO)** que proporciona Microsoft). El componente de formato **XMLHeader** se configura para describir la estructura del mensaje de transferencia de crédito de acuerdo con los estándares de mensajes XML ISO 20022. El componente de formato **XMLHeader/Document/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/Ustrd** se configura para agregar el elemento XML **Ustrd** al mensaje generado y colocar la información del remitente en un formato no estructurado como texto de los siguientes elementos XML:

- El componente **PaymentNotes** se usa para generar el texto de notas de pago.
- El componente **DelimitedSequence** genera números de factura separados por comas que se utilizan para liquidar la transferencia de crédito actual.

[![Notas de pago y componentes DelimitedSequence](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> Los componentes **PaymentNotes** y **DelimitedSequence** se etiquetan con un signo de interrogación. Un signo de interrogación indica que el uso de un componente es condicional. En este caso, el uso de los componentes se basa en los siguientes criterios:
>
> - La expresión `@.PaymentsNotes <> ""` que se define para el componente **PaymentNotes** habilita (devolviendo **TRUE**) el elemento XML **Ustrd** que se debe rellenar con el texto de las notas de pago, si el texto no está vacío para la transferencia de crédito actual.
>
>    [![Expresión para el componente PaymentNotes](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)
>
> - La expresión `@.PaymentsNotes = ""` que se define para el componente **DelimitedSequence** habilita (devolviendo **TRUE**) el elemento XML **Ustrd** que se rellenará con una lista de números de factura separados por comas que se utilizan para liquidar la transferencia de crédito actual, si el texto de las notas de pago para esa transferencia de crédito está vacío.
>
>    [![Expresión para el componente DelimitedSequence](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)
> 
> Según esta configuración, el mensaje que se genera para cada pago del deudor, el elemento XML **Ustrd**, contendrá el texto de las notas de pago o, si ese texto estuviera vacío, una lista de números de factura separados por comas que se usan para liquidar el pago.

## <a name="validation-of-configured-formulas"></a><a name="TestFormula"></a>Validación de las fórmulas configuradas

En la página **Diseñador de fórmulas**, seleccione **Probar** para validar cómo funciona la fórmula configurada.

[![Selección Probar para validar una fórmula](./media/ER-FormulaTest-Start.png)](./media/ER-FormulaTest-Start.png)

Cuando se requieren los valores de los argumentos de la fórmula, puede abrir el cuadro de diálogo **Probar expresión** de la página **Diseñador de fórmulas**. En la mayoría de los casos, estos argumentos deben definirse manualmente, ya que los enlaces configurados no se ejecutan en tiempo de diseño. La pestaña **Resultado de prueba** de la página **Diseñador de fórmulas** muestra el resultado de la ejecución de la fórmula configurada.

El siguiente ejemplo muestra cómo puede probar la fórmula configurada para el dominio de comercio exterior a fin de asegurarse de que el código de mercancías intrastat contenga solo dígitos.

Cuando pruebe esta fórmula, puede usar el cuadro de diálogo **Probar expresión** para especificar el valor del código de mercancías intrastat para la prueba.

[![Especificar el código de mercancías intrastat para pruebas](./media/ER-FormulaTest-Start-EnterArguments.png)](./media/ER-FormulaTest-Start-EnterArguments.png)

Después de especificar el código de mercancías intrastat y seleccionar **Aceptar**, la pestaña **Resultado de prueba** de la página **Diseñador de fórmulas** muestra el resultado de la ejecución de la fórmula configurada. Después puede evaluar si el resultado es aceptable. Si el resultado no es aceptable, puede actualizar la fórmula y probarla nuevamente.

[![Resultado de prueba](./media/ER-FormulaTest-Result.png)](./media/ER-FormulaTest-Result.png)

Algunas fórmulas no se pueden probar en tiempo de diseño. Por ejemplo, una fórmula puede devolver un resultado de un tipo de datos que no se puede mostrar en la pestaña **Resultado de prueba**. En este caso, recibirá un mensaje de error que indica que la fórmula no se puede probar.

[![Mensaje de error](./media/ER-FormulaTest-Error.png)](./media/ER-FormulaTest-Error.png)

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Idioma de fórmulas en los informes electrónicos](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
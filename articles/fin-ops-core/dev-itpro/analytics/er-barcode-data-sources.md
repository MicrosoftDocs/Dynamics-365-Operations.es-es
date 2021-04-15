---
title: Usar fuentes de datos de código de barras para generar imágenes de código de barras
description: Este tema explica cómo usar las fuentes de datos de código de barras para generar imágenes de código de barras.
author: NickSelin
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.13
ms.openlocfilehash: 08b9d03517a600cf46b1093cfa3bc454621eabd0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748374"
---
# <a name="use-barcode-data-sources-to-generate-bar-code-images"></a>Usar fuentes de datos de código de barras para generar imágenes de código de barras

[!include[banner](../includes/banner.md)]

Puede usar el marco del [Informe electrónico (ER)](general-electronic-reporting.md) para diseñar [Componentes de formato ER](general-electronic-reporting.md#FormatComponentOutbound) que puede ejecutar para generar los documentos salientes electrónicos e imprimibles que necesita. Para generar un documento saliente en formato Microsoft Office, debe especificar el diseño del informe utilizando un documento de Microsoft Excel o Microsoft Word como plantilla de informe. El [diseñador de operaciones de ER](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) le permite adjuntar un documento de Excel o Word como plantilla para un formato ER. Los siguientes elementos con nombre en la plantilla adjunta están asociados con los elementos del componente de formato configurado:

- Controles de contenido en Word
- Hojas, rangos, celdas, formas e imágenes con nombre en Excel

Estos elementos con nombre se usan como marcadores de posición para los datos que se ingresan en un documento generado cuando se ejecuta un formato ER. Los elementos de formato ER está vinculados a orígenes de datos. Estas fuentes de datos especifican los datos que se ingresarán en los documentos generados en tiempo de ejecución. Para obtener más información, consulte [Insertar imágenes y formas en los documentos generados con ER](electronic-reporting-embed-images-shapes.md).

ER ahora admite el tipo de origen de datos **Código de barras**. Por lo tanto, ahora puede generar una imagen que represente el código de barras para el texto especificado. Cuando configura un formato ER, puede especificar las fuentes de datos del tipo **Código de barras** para generar imágenes de código de barras. Luego puede agregar esas imágenes a los documentos comerciales generados, como pedidos, facturas, albaranes y recibos. También puede agregarlos a varios tipos de etiquetas, como etiquetas de productos y estantes, y etiquetas de embalaje y envío.

Los siguientes marcadores de posición pueden usarse en plantillas de informes para ingresar imágenes de código de barras:

- [Imagen](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word), control de contenido para Word
- [Imagen](https://support.office.com/article/insert-pictures-3c51edf4-22e1-460a-b372-9329a8724344), objeto en Excel

Mediante el uso de un origen de datos del tipo **Código de barras**, puede generar códigos de barras en los siguientes formatos:

- Códigos de barras unidimensionales:

    - Codabar
    - Code 39
    - Code 93
    - Code 128
    - EAN-8
    - EAN-13
    - ITF-14
    - Intelligent Mail
    - MSI
    - Plessey
    - PDF417
    - UPC-A
    - UPC-E

- Códigos de barras bidimensionales:

    - Aztec
    - Data Matrix
    - Código QR

Cuando configura un origen de datos de **Código de barras**, puede definir parámetros de representación específicos que se utilizan para generar una imagen:

- **Ancho**: especifique el ancho del código de barras en píxeles. Un valor de **0** (cero) indica que se utiliza el ancho predeterminado. El significado puede variar para diferentes formatos.
- **Alto**: especifique el alto del código de barras en píxeles. Un valor de **0** (cero) indica que se utiliza el alto predeterminado. El significado puede variar para diferentes formatos.
- **Margen**: especifique el tamaño del margen del código de barras en píxeles. El margen es el área a cada lado de un código de barras que debe mantenerse libre (zona silenciosa). Un valor de **0** (cero) indica que se utiliza el margen predeterminado. El significado puede variar para diferentes formatos.
- **Contenido de salida**: establezca el valor en **Sí** para generar una imagen de código de barras que contiene la información codificada como texto. El valor predeterminado es **No**.
- **Codificación**: especifique el tipo de caracteres que están codificados en la imagen de código de barras generada. De forma predeterminada, se usa la codificación **UTF-8**.

> [!IMPORTANT]
> Cuando agrega un nuevo origen de datos de **Código de barras**, debe colocarlo debajo de otro elemento (contenedor) como un elemento anidado.
>
> Cuando vincula un origen de datos de **Código de barras** a un elemento de celda en un formato, y el elemento de celda representa un control de contenido de Word o una imagen de Excel, el origen de datos se presenta en ese vínculo como una función que tiene un único parámetro de tipo **Cadena**. Debe usar este parámetro para especificar el texto que debe transformarse en una imagen de código de barras y leerse cuando se escanea un código de barras generado.

Para obtener más información acerca de esta característica, complete los ejemplos de este tema.

## <a name="example-generate-a-payment-check-that-contains-a-bar-code-that-encodes-the-payable-amount"></a>Ejemplo: Generar un cheque de pago que contenga un código de barras que codifique el monto a pagar

Este ejemplo muestra cómo un usuario en el rol **Administrador de sistema** o **Consultor funcional de informes electrónicos** puede configurar un formato ER que contiene una plantilla que se utiliza para generar un documento saliente en formato Excel que contiene un código de barras. A continuación, se ofrece una descripción general de los pasos que se emprenden.

1. [Completar los requisitos previos](#ExamplePrerequisites).
2. [Activar un proveedor de configuración](#ExampleProvider).
3. [Importar la solución de ER proporcionada](#ExampleImportSolution).
4. [Generar un cheque de pago](#ExampleGenerateCheque).
5. [Revisar el cheque de pago generado](#ExampleReviewGeneratedCheque).
6. [Modificar el formato de la solución ER proporcionada](#ExampleModifyFormat).

    1. [Aplicar una nueva plantilla de cheques](#ExampleModifyFormatApplyTemplate).
    2. [Agregar un nuevo origen de datos del código de barras](#ExampleModifyFormatAddDataSource).
    3. [Vincular un nuevo elemento de formato](#ExampleModifyFormatBindFormatElement).
    4. [Hacer que la versión modificada esté disponible para pruebas](#ExampleModifyFormatMakeVersionAvailable).

        1. [Completar la versión del formato modificado](#CompleteToRun).
        2. [Hacer que la versión borrador esté disponible para su uso](#MarkToRun).

7. [Generar un cheque de pago](#ExampleGenerateCheque2).
8. [Convertir el cheque generado a un PDF](#ExampleConvertToPDF).

En este ejemplo, utilizará la solución ER proporcionada que se ha configurado para generar cheques de pago. Esta solución genera cheques de pago donde el importe a pagar se escribe como un número y como texto. Modificará esta solución de ER para que el cheque también incluya un código de barras generado donde el importe a pagar esté codificado y pueda leerse utilizando un escáner de códigos de barras.

Los pasos se pueden completar en la empresa **USMF** de Microsoft Dynamics 365 Finance.

### <a name="complete-the-prerequisites"></a><a name="ExamplePrerequisites"></a>Completar los requisitos previos

Para este ejemplo, debe tener acceso a la empresa USMF de Finance para uno de los roles siguientes:

- Consultor funcional de informes electrónicos
- Administrador del sistema

Si aún no ha completado el ejemplo del tema [Insertar imágenes y formas en documentos que genera con ER](electronic-reporting-embed-images-shapes.md), descargue las siguientes configuraciones de la solución ER de ejemplo.

| Descripción del contenido         | Nombre de archivo                   |
|-----------------------------|-----------------------------|
| Configuración del modelo datos de ER | Model for cheques.xml       |
| Configuración del formato de ER     | Cheques printing format.xml |

Adicionalmente, descargue el siguiente archivo de Excel que contiene la plantilla modificada para la solución ER proporcionada.

| Descripción del contenido | Nombre de archivo                 |
|---------------------|---------------------------|
| Plantilla de informe     | Consulte la plantilla Excel.xlsx |

### <a name="activate-a-configuration-provider"></a><a name="ExampleProvider"></a>Activar un proveedor de configuración

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, compruebe que aparece el [proveedor de la configuración](general-electronic-reporting.md#Provider) para la empresa de ejemplo **Litware, Inc.** y que se ha marcado como activo. Si no aparece en la lista o si no está marcado como activo, siga los pasos de [Crear un proveedor de configuración y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Establecer la empresa de ejemplo como activa en la página Configuraciones de localización](./media/er-barcode-data-source-active-provider.png)

### <a name="import-the-provided-er-solution"></a><a name="ExampleImportSolution"></a>Importar la solución de ER proporcionada

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.
3. En la página **Configuraciones**, si la configuración **Modelo para cheques** no está disponible en el árbol de configuración, siga estos pasos para importar la configuración del modelo de datos ER:

    1. En el panel Acción, seleccione **Exchange** \> **Cargar del archivo XML**.
    2. En el cuadro de diálogo, seleccione **Examinar**, encuentre y seleccione el archivo **Model for cheques.xml** y luego seleccione **Aceptar**.

4. Si la configuración **Formato de impresión de cheques** no está disponible en el árbol de configuración, siga estos pasos para importar la configuración del modelo de datos ER:

    1. En el panel Acción, seleccione **Exchange** \> **Cargar del archivo XML**.
    2. En el cuadro de diálogo, seleccione **Examinar**, encuentre y seleccione el archivo **Cheques printing format.xml** y luego seleccione **Aceptar**.

5. En el árbol de configuración, expanda **Modelo para cheques**.
6. Revise la lista de configuraciones de ER importadas en el árbol de configuración.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque"></a>Generar un cheque de pago

1. Vaya a **Gestión de efectivo y de banco** \> **Cuentas bancarias** \> **Cuentas bancarias**.
2. En la página **Cuentas bancarias**, seleccione la cuenta **USMF OPER**.
3. En la página detalles de la cuenta bancaria, en el panel de acciones, en la pestaña **Configurar**, en el grupo **Diseño**, seleccione **Comprobar**.
4. En la página **Comprobar diseño**, seleccione **Editar**.
5. En la ficha desplegable **General**, establezca la opción **Formato de exportación electrónica genérica** en **Sí**.
6. En el campo **Configuración de formato de exportación**, seleccione el formato de ER **Formato de impresión de cheques** que importó anteriormente.
7. En el panel de acciones, seleccione **Imprimir prueba**.
8. En el cuadro de diálogo, establezca la opción **Formato de cheque negociable** en **Sí** y luego seleccione **Aceptar**.

    ![Comprobar diseño: cuadro de diálogo de prueba de impresión](./media/er-barcode-data-source-check-layout.png)

### <a name="review-the-generated-payment-check"></a><a name="ExampleReviewGeneratedCheque"></a>Revisar el cheque de pago generado

- Abra el cheque generado en Excel.
2. Revise el cheque generado.

    ![Cheque generado en Excel](./media/er-barcode-data-source-cheque1.png)

### <a name="modify-the-format-of-the-provided-er-solution"></a><a name="ExampleModifyFormat"></a>Modificar el formato de la solución ER proporcionada

#### <a name="apply-a-new-check-template"></a><a name="ExampleModifyFormatApplyTemplate"></a>Aplicar una nueva plantilla de cheques

Puede usar la aplicación de escritorio de Excel para abrir el archivo **Cheque template Excel.xlsx** que importó anteriormente. Tenga en cuenta que esta plantilla difiere de la plantilla que utilizó para generar un cheque de pago en la solución ER proporcionada. Además, incluye un elemento **AmountBarcode** para la imagen del código de barras.

![Elemento AmountBarcode en la plantilla de Excel](./media/er-barcode-data-source-cheque2.png)

Ahora debe modificar la solución ER y luego [aplicar de nuevo](modify-electronic-reporting-format-reapply-excel-template.md) la plantilla modificada.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione **Configuraciones de informes**.
3. En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo para cheques** y seleccione **Formato de impresión de cheques**.
4. En el panel de acciones, haga clic en **Diseñador**.
5. En el diseñador de operaciones de ER, seleccione la pestaña **Asignación** en el lado derecho de la página, y luego, en el panel del árbol de formato a la izquierda, seleccione **Expandir/contraer**.
6. Tenga en cuenta que todos los elementos de formato de celda están vinculados a las fuentes de datos apropiadas.

    ![Vincular elementos de formato de celda a orígenes de datos en el diseñador de operaciones de ER](./media/er-barcode-data-source-cells-bound.png)

7. Seleccione la pestaña **Formato** en el lado derecho de la página.
8. En el Panel de acciones, seleccione los puntos suspensivos (**...**) y luego seleccione **Importar**.
9. En el grupo **Importar**, seleccione **Actualizar desde Excel** y luego seleccione **Actualizar plantilla**.
10. En el cuadro de diálogo, busque el archivo **Cheque template Excel.xlsx** que está guardado en su computadora, selecciónelo y luego seleccione **Aceptar** para confirmar que se debe aplicar la plantilla seleccionada.
11. Seleccione la pestaña **Asignación** en el lado derecho de la página, y luego, en el panel del árbol de formato a la izquierda, seleccione **Expandir/contraer**.
12. Tenga en cuenta que el elemento de celda **AmountBarcode** se ha agregado al formato. Este elemento está asociado con el elemento **AmountBarcode** que se ha agregado a la plantilla de Excel modificada como marcador de posición para una imagen de código de barras.

    ![Elemento de celda AmountBarcode agregado al formato en el diseñador de operaciones ER](./media/er-barcode-data-source-cell-added.png)

#### <a name="add-a-new-barcode-data-source"></a><a name="ExampleModifyFormatAddDataSource"></a>Agregar un nuevo origen de datos del código de barras

A continuación, debe agregar un nuevo origen de datos de tipo **Código de barras**.

1. En el diseñador de operaciones de ER, en la pestaña **Asignación** en el lado derecho de la página, seleccione el origen de datos **imprimir**.
2. Seleccione **Añadir**, y luego, en el grupo **Funciones**, seleccione el tipo de origen de datos **Código de barras**.

    ![Seleccionar el tipo de origen de datos código de barras](./media/er-barcode-data-source-add.png)

3. En el cuadro de diálogo desplegable, en el campo **Nombre**, escriba **código de barras**.
4. En **Formato del código de barras**, seleccione **Código 128**.
5. En el campo **Ancho**, especifique **500**.
6. Seleccione **Aceptar**.

    ![Cuadro de diálogo Propiedades del origen de datos](./media/er-barcode-data-source-add2.png)

#### <a name="bind-a-new-format-element"></a><a name="ExampleModifyFormatBindFormatElement"></a>Vincular un nuevo elemento de formato

A continuación, debe vincular el nuevo elemento de formato al origen de datos que acaba de agregar.

1. En el diseñador de operaciones de ER, en la pestaña **Asignación** en el lado derecho de la página, seleccione el origen de datos **imprimir\\código de barras**.
2. En el panel de árbol de formato a la izquierda, seleccione el elemento de celda **AmountBarcode** y luego seleccione **Vincular**.
3. En el panel de acciones, seleccione **Mostrar detalles**.
4. Tenga en cuenta que, dado que el origen de datos **Código de barras** se representa en el enlace como una función que contiene un único parámetro, el nombre del elemento de formato enlazado se ha tomado automáticamente como argumento de ese parámetro.

    ![Detalles del origen de datos de código de barras en el diseñador de operaciones de ER](./media/er-barcode-data-source-bind1.png)

5. Seleccione **Editar fórmula** para ajustar el enlace.

    No quiere que se devuelva el nombre del elemento de celda. Por lo tanto, debe configurar una expresión que devuelva texto que contenga la cantidad a pagar del cheque actual. Dado que el rango **ChequeLines** principal está vinculado al origen de datos **model.cheques**, el importe a pagar del cheque actual está disponible en el campo **model.cheques.attributes.amount** del tipo de datos **Real**.

6. En el campo **Fórmula**, especifique **print.barcode(NUMBERFORMAT(@.attributes.amount, "F2"))**.
7. Seleccione **Guardar** y, después, cierre el [diseñador de fórmulas ER](general-electronic-reporting-formula-designer.md).
8. Tenga en cuenta que el enlace se ha ajustado.

    ![Enlace ajustado en el diseñador de operaciones de ER](./media/er-barcode-data-source-bind2.png)

9. Seleccione **Guardar** y, después, cierre el diseñador de operaciones ER.

#### <a name="make-the-modified-version-available-for-test-runs"></a><a name="ExampleModifyFormatMakeVersionAvailable"></a>Hacer que la versión modificada esté disponible para pruebas

De forma predeterminada, las únicas versiones que tienen un estado de **Terminado** y **Compartido** se usan cuando ejecuta un formato ER.

Si ha finalizado sus cambios, puede completar su trabajo con la versión borrador actual y hacer que sus cambios estén disponibles para su uso. Para obtener instrucciones, consulte la sección [Completar la versión del formato modificado](#CompleteToRun) a continuación.

Si desea continuar trabajando con la versión borrador actual, pero tiene que usarla para generar comprobaciones, debe especificar explícitamente que desea usar la versión borrador del formato para la ejecución. Para obtener instrucciones, consulte la sección [Hacer que la versión borrador esté disponible para su uso](#MarkToRun).

##### <a name="complete-the-modified-format-version"></a><a name="CompleteToRun"></a>Completar la versión del formato modificado

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione **Configuraciones de informes**.
3. En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo para cheques** y seleccione **Formato de impresión de cheques**.
4. En la ficha desplegable **Versiones**, seleccione el registro que tenga un estado de **Borrador**.
5. Seleccione **Cambiar Estado** y luego seleccione **Completar**.
6. En el cuadro de diálogo, seleccione **Aceptar**.

El estado de la versión actual cambia de **Borrador** a **Completado** y se crea una nueva versión que tiene un estado de **Borrador**. Puede usar esta nueva versión de borrador para aplicar cambios adicionales.

##### <a name="make-the-draft-version-available-for-use"></a><a name="MarkToRun"></a>Hacer que la versión borrador esté disponible para su uso

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione **Configuraciones de informes**.
3. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
4. En el cuadro de diálogo, establezca las opciones **Ejecutar configuración** en **Sí** y luego seleccione **Aceptar**.
5. En el árbol de configuración, expanda **Modelo para cheques** y seleccione **Formato de impresión de cheques**.
6. Establezca la opción **Ejecutar borrador** en **Sí**.
7. Seleccione **Guardar**.

La versión borrador del formato seleccionado se marca como disponible para su uso cuando se ejecuta el formato seleccionado.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque2"></a>Generar un cheque de pago

1. Vaya a **Gestión de efectivo y de banco** \> **Cuentas bancarias** \> **Cuentas bancarias**.
2. En la página **Cuentas bancarias**, seleccione la cuenta **USMF OPER**.
3. En la página detalles de la cuenta bancaria, en el panel de acciones, en la pestaña **Configurar**, en el grupo **Diseño**, seleccione **Comprobar**.
4. En la página **Comprobar diseño**, en el panel de acciones, seleccione **Prueba de impresión**.
5. En el cuadro de diálogo, establezca la opción **Formato de cheque negociable** en **Sí**.
6. Seleccione **Aceptar**.
7. Revise el cheque generado. Observe que se ha generado un código de barras para codificar el importe a pagar del cheque.

    ![Cheque de pago generado con código de barras en Excel](./media/er-barcode-data-source-cheque3.png)

> [!IMPORTANT]
> Se lanza una excepción si el argumento de un origen de datos **Código de barras** no cumple los requisitos apropiados que son específicos del formato del código de barras. Por ejemplo, cuando el origen de datos **Código de barras** se llama para generar un código de barras [EAN-8](https://wikipedia.org/wiki/EAN-8) para el texto proporcionado, se produce una excepción si la longitud del texto supera los siete caracteres.

### <a name="convert-the-generated-check-to-a-pdf"></a><a name="ExampleConvertToPDF"></a>Convertir el cheque generado a un PDF

Como se describe en el tema [Generar formularios FTI imprimibles](er-generate-printable-fti-forms.md#finland), puede usar una fuente especial para producir códigos de barras en un documento generado. En este caso, las transformaciones adicionales del documento generado pueden depender de la disponibilidad de esa fuente en el entorno de transformación. Por ejemplo, si intenta convertir un documento a formato PDF u obtener una vista previa del mismo en un entorno donde falta la fuente, los códigos de barras no se representarán correctamente.

Sin embargo, cuando usa origen de datos **Código de barras** para producir códigos de barras, la representación de esos códigos de barras no depende de ninguna fuente. Por lo tanto, puede convertir fácilmente documentos que contienen los códigos de barras a formato PDF. La siguiente ilustración muestra la vista previa de un cheque de pago generado que ha sido [convertido](electronic-reporting-destinations.md#OutputConversionToPDF) a un PDF, basado en la configuración del [destino](electronic-reporting-destinations.md) de ER configurado.

![Vista previa del PDF de un cheque de pago](./media/er-barcode-data-source-cheque4.png)

## <a name="limitations"></a>Limitaciones

> [!NOTE]
> Algunos tipos de códigos de barras que se generan tienen una relación de aspecto fija. Este comportamiento tiene sentido si ha activado la característica **Habilitar el uso de la biblioteca EPPlus en el marco de informes electrónicos** para trabajar con documentos de Excel en ER. En ese caso, se incorpora una imagen en un marcador de posición que tiene una relación de aspecto bloqueada. Por lo tanto, cuando las dimensiones de un marcador de posición en una plantilla corresponden a la proporción de una imagen que se incorpora, se puede cambiar el tamaño de una imagen real en un documento generado para mantener la proporción requerida. Para evitar el cambio de tamaño de la imagen, use un marcador de posición que tenga una relación de aspecto esperada.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Destinos de informes electrónicos](electronic-reporting-destinations.md)
- [Idioma de fórmulas en los informes electrónicos](er-formula-language.md)
- [Función NUMBERFORMAT](er-functions-text-numberformat.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
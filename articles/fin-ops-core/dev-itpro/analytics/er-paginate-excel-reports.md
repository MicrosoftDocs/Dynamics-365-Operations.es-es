---
title: Diseñar un formato ER para paginar documentos generados en Excel
description: Este artículo explica cómo diseñar un formato de informes electrónicos (ER) que pagina un documento generado en Microsoft Excel.
author: kfend
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: Version 10.0.22
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.form: EROperationDesigner
ms.openlocfilehash: e4a34dffda9e9b95f5d6c7ee382723663817ec6b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285013"
---
# <a name="design-an-er-format-to-paginate-generated-documents-in-excel"></a>Diseñar un formato ER para paginar documentos generados en Excel

[!include [banner](../includes/banner.md)]

Este artículo explica cómo un usuario con el rol de administrador del sistema o Consultor funcional de Informes electrónicos puede configurar un formato de [Informes electrónicos (ER)](general-electronic-reporting.md) para generar documentos salientes en Microsoft Excel y gestionar la paginación de documentos.

En este ejemplo, modificará el formato ER proporcionado por Microsoft que se utiliza para imprimir el informe de control al [generar](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md) la declaración Intrastat. Este informe le permite observar las transacciones de Intrastat informadas. Sus modificaciones te permitirán gestionar la paginación de los informes de control que se generen.

Los procedimientos de este artículo se pueden completar en la empresa **DEMF**. No se requiere codificación. Antes de comenzar, debe descargar y guardar los archivos siguientes.

| Descripción       | Nombre de archivo |
|-------------------|-----------| 
| Plantilla de informe 1 | [ERIntrastatReportDemo1.xlsx](https://download.microsoft.com/download/7/2/a/72ae292a-8bb2-4b9d-8397-9764218f6fa8/ERIntrastatReportDemo1%20.xlsx) |
| Plantilla de informe 2 | [ERIntrastatReportDemo2.xlsx](https://download.microsoft.com/download/7/d/1/7d15858d-6260-4afa-9dda-d8b955e59b1a/ERIntrastatReportDemo2.xlsx) |

## <a name="configure-the-er-framework"></a>Configurar el marco ER

Siga los pasos de [Configurar el marco de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar el conjunto mínimo de parámetros de ER. Debe completar esta configuración antes de comenzar a utilizar el marco ER para diseñar una versión personalizada de un formato ER estándar.

## <a name="import-the-standard-er-format-configuration"></a>Importar configuraciones del formato estándar de ER

Siga los pasos de [Importar la configuración de formato estándar de ER](er-quick-start2-customize-report.md#ImportERSolution1) para agregar las configuraciones estńdar de ER a su instancia actual de Dynamics 365 Finance. Importar la versión **1,9** de la configuración de formato de **Informe intrastat**. La Versión básica 1 de la configuración **Modelo intrastat** básica se importa automáticamente desde el repositorio.

## <a name="customize-the-standard-er-format"></a>Personalizar el formato ER estándar

### <a name="create-the-custom-er-format"></a>Crear el formato ER personalizado

En este escenario, usted es el representante de Litware, Inc., que actualmente está seleccionado como el proveedor de configuración de ER activo. Debe crear una nueva configuración de formato ER utilizando la configuración **Informe intrastat** como base.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo Intrastat** y seleccione **Informe Intrastat**. Litware, Inc. utilizará la versión 1.9 de esta configuración de formato ER como base para la versión personalizada.
3. Seleccione **Crear configuración** para abrir el cuadro de diálogo desplegable. Puede usar este cuadro de diálogo para crear una nueva configuración para un formato de pago personalizado.
4. En el grupo de campos **Nuevo**, seleccione **Derivar del nombre: Infrastat, Microsoft**.
5. En el campo **Nombre**, especifique **Informe Intrastat Litware**.
6. Seleccione **Crear configuración** para crear el nuevo formato.

Se creará la versión 1.9.1 del formato de configuración de ER **Informe de Intrastat Litware**. Esta versión tiene un estado de **Borrador** y puede editarse. El contenido actual de su formato ER personalizado coincide con el contenido del formato proporcionado por Microsoft.

### <a name="make-the-custom-format-runnable"></a>Hacer ejecutable el formato personalizado

Ahora que se ha creado la primera versión de su formato personalizado y tiene un estado de **Borrador**, puede ejecutar el formato con fines de prueba. Para ejecutar el informe, procese un pago de proveedor utilizando el método de pago que se refiere a su formato ER personalizado. De forma predeterminada, cuando llama a un formato de ER desde la aplicación, las únicas versiones que tienen un estado de **Completado** o **Compartido** son las que se consideran. Este comportamiento ayuda a evitar el uso de formatos ER que tienen diseños inacabados. Sin embargo, para sus ejecuciones de prueba, puede obligar a la aplicación a usar la versión de su formato ER que tenga un estado de **Borrador**. De esta manera, puede ajustar la versión del formato actual si se requieren modificaciones. Para obtener más información, consulte [Aplicabilidad](electronic-reporting-destinations.md#applicability).

Para utilizar la versión borrador de un formato ER, debe marcar de forma explícita el formato ER.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. En el cuadro de diálogo **Parámetros de usuario**, establezca la opción **Ejecutar configuración** en **Sí** y luego seleccione **Aceptar**.
4. Seleccione **Editar** para hacer que la página actual sea editable, según sea necesario.
5. En el árbol de configuración del panel izquierdo, seleccione **Informe Intrastat Litware**.
6. Seleccione la opción **Ejecutar borrador** en **Sí** y luego seleccione **Guardar**.

    ![Opción Ejecutar borrador en la página Configuraciones.](./media/er-paginate-excel-reports-derived-format-configuration.png)

## <a name="set-up-foreign-trade-parameters-to-use-the-custom-er-format"></a>Configure los parámetros de comercio exterior para utilizar el formato ER personalizado

Siga estos pasos para configurar los parámetros de comercio exterior para que pueda utilizar el formato personalizado.

1. Vaya a **Impuestos** \> **Configuración** \> **Comercio exterior** \> **Parámetros de comercio exterior**.
2. En la página **Parámetros de comercio exterior**, en la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **Informe Intrastat Litware**.
3. En el campo **Asignación de formato de informe**, seleccione **Informe Intrastat Litware**.
4. Seleccione **Guardar**.

## <a name="configure-the-custom-format-to-use-the-downloaded-report-template"></a>Configurar el formato personalizado para usar la plantilla de informe descargada

### <a name="review-the-first-downloaded-excel-template"></a>Revisar la primera plantilla de Excel descargada

1. En la aplicación de escritorio de Excel, abra el archivo de plantilla **ERIntrastatReportDemo1.xlsx** que descargó anteriormente.
2. Verifique que la plantilla contenga rangos con nombre para crear el encabezado del informe, los detalles del informe y las secciones de pie de página del informe en los documentos generados.

    ![Diseño de la plantilla 1 de Excel en la aplicación de escritorio.](./media/er-paginate-excel-reports-template1.gif)

### <a name="replace-the-current-excel-template-in-the-custom-er-format"></a><a id="replace-template"></a>Reemplazar la plantilla actual de Excel en el formato ER personalizado

Debe agregar una nueva plantilla de Excel al formato ER personalizado.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo Intrastat** \> **Informe Intrastat** y seleccione la configuración **Informe Intrastat Litware**.
3. Seleccione **Diseñador**.
4. En la página **Diseñador de formato**, en el panel de acciones seleccione **Mostrar detalles**.
5. Asegúrese de que el se selecciona el componente de formato raíz **Intrastat: Excel** y, a continuación, en el panel de acciones, en la pestaña **Importar**, en el grupo **Importar**, seleccione **Actualizar desde Excel**.
6. En el **Actualizar desde Excel**, seleccione **Actualizar plantilla**.
7. En el cuadro de diálogo **Abrir**, explore y seleccione el archivo **ERIntrastatReportDemo1.xlsx** que descargó anteriormente y luego seleccione **Abrir**.
8. Seleccione **Aceptar**.
9. Seleccione **Guardar**.

![Estructura de formato en el diseñador de formato ER después de agregar la nueva plantilla de Excel.](./media/er-paginate-excel-reports-format1.png)

## <a name="change-the-data-binding-to-show-the-item-description-on-a-generated-report"></a>Cambiar el enlace de datos para mostrar la descripción del artículo en un informe generado

1. En la página **Diseñador de formato**, seleccione la pestaña **Asignación** .
2. Expanda **Intrastat** \> **Líneas de informe** y seleccione el componente **Código de mercancía**.
3. Seleccione **Editar fórmula**.
4. Cambie la fórmula vinculante de `@.CommodityCode` a `CONCATENATE(@.CommodityCode, " ", @.ProductName)`.
5. Seleccione **Guardar**.

![Enlace configurado para mostrar la descripción del elemento en el diseñador de formato ER.](./media/er-paginate-excel-reports-format1a.png)

## <a name="generate-an-intrastat-declaration-control-report"></a><a id="generate-intrastat-control-report"></a>Generar un informe de control de declaración Intrastat

Primero, asegúrese de tener transacciones Intrastat de las que informar en la página **Intrastat**.

![Transacciones en la página Intrastat.](./media/er-paginate-excel-reports-transactions1.gif)

Luego use el formato ER personalizado para generar el informe de control de la declaración Intrastat.

1. Vaya a **Impuestos** \> **Declaraciones** \> **Comercio exterior** \> **Intrastat**.
2. En la página **Intrastat**, en el panel de acciones, seleccione **Salida** \> **Impresión**.
3. En el cuadro de diálogo **Informe Intrastat**, siga estos pasos para ejecutar el informe:

    1. Seleccione los campos **Fecha de inicio** y **Fecha de final** para incluir transacciones específicas de Intrastat en el informe.
    2. Establezca la opción **Generar archivo** en **No**.
    3. Establezca la opción **Generar informe** en **Sí**.
    4. Seleccione **Aceptar**.

4. Descargue y guarde el documento que se genera.
5. Abra el documento en Excel y revíselo.

    ![Documento Excel generado en la aplicación de escritorio.](./media/er-paginate-excel-reports-document1.png)

## <a name="configure-the-custom-format-to-paginate-generated-documents"></a>Configurar el formato personalizado para paginar documentos generados

### <a name="review-the-second-downloaded-excel-template"></a>Revisar la segunda plantilla de Excel descargada

1. En Excel, abra el archivo de plantilla **ERIntrastatReportDemo2.xlsx** que descargó anteriormente.
2. Compare esta plantilla con la plantilla **ERIntrastatReportDemo1.xlsx** y verifique que contiene varios nombres nuevos de Excel para crear y completar secciones específicas de la página en los documentos generados:

    - El rango **ReportPageHeader** se agrega para crear encabezados de página.
    - El rango **ReportPageFooter** se agrega para crear pies de página.
    - La celda **ReportPageFooter\_PageLines** está configurada para mostrar el número de transacciones por página.
    - La celda **ReportPageFooter\_PageAmount** está configurada para mostrar la cantidad total de transacciones por página.
    - La celda **ReportPageFooter\_PageWeight** está configurada para mostrar el peso total de transacciones por página.
    - La celda **ReportPageFooter\_RunningCounterLines** está configurada para mostrar el contador en ejecución de transacciones desde el comienzo del informe hasta la página actual.
    - La celda **ReportPageFooter\_RunningTotalAmount** está configurada para mostrar la cantidad total de ejecuciones para todas las transacciones desde el comienzo del informe hasta la página actual.
    - La celda **ReportPageFooter\_RunningTotalWeight** está configurada para mostrar el peso total de ejecuciones para todas las transacciones desde el comienzo del informe hasta la página actual.

    ![Diseño de la plantilla 2 de Excel en la aplicación de escritorio.](./media/er-paginate-excel-reports-template2a.gif)

    La celda **CommodityCode** de esta plantilla está configurada para ajustar el texto de la celda. Debido a que la fila de detalles de la transacción está configurada para que se ajuste automáticamente a la altura de una fila, la altura de toda la fila debe cambiar automáticamente cuando el texto de la celda **CommodityCode** la celda está ajustado.

    ![Celda CommodityCode configurada para ajustar el texto de la celda.](./media/er-paginate-excel-reports-template2b.gif)

### <a name="repeat-the-replacement-of-the-current-excel-template-in-the-custom-er-format"></a>Repetir la sustitución de la plantilla actual de Excel en el formato ER personalizado

1. Siga los pasos de la sección [Reemplazar la plantilla actual de Excel en el formato ER personalizado](#replace-template) de este artículo. Sin embargo, en el paso 7, seleccione el archivo **ERIntrastatReportDemo2.xlsx**.
2. En la página **Diseñador de formato**, expanda **Intrastat**.
3. Nombre los componentes de formato de [Rango](er-fillable-excel.md#range-component) que se han agregado al formato ER editable para sincronizar la estructura con la estructura de la plantilla de Excel aplicada:

    1. Selecciona el componente **Distancia** que está asociado con el nombre de Excel **ReportPageHeader**.
    2. En la pestaña **Formato**, en el campo **Nombre**, introduzca **Encabezado de la página del informe**.
    3. Seleccione el componente **Rango** que está asociado con el nombre de Excel **ReportPageFooter**.
    4. En la pestaña **Formato**, en el campo **Nombre**, introduzca **Pie de página del informe**.

4. Seleccione **Guardar**.

![Estructura de formato en el diseñador de formato ER después de sustituir la nueva plantilla de Excel.](./media/er-paginate-excel-reports-format2.png)

### <a name="change-the-format-structure-to-implement-document-pagination"></a>Cambiar la estructura del formato para implementar la paginación del documento

1. En la página **Diseñador de formatos**, en el árbol de formato del panel izquierdo, seleccione la componente raíz **Intrastat**.
2. Seleccione **Agregar**.
3. En el cuadro de diálogo **Agregar**, seleccione el componente [Página](er-fillable-excel.md#page-component) en el grupo de componentes **Excel**.
4. En el cuadro de diálogo **Propiedades de componente**, en el campo **Nombre**, escriba **Página de informe**. A continuación seleccione **Aceptar**.
5. Para usar el componente **Encabezado de la página del informe** como encabezado de página en cada página generada, siga estos pasos:

    1. Seleccione el componente **Encabezado de la página del informe** y luego seleccione **Cortar**.
    2. Seleccione el componente **Página del informe** y luego seleccione **Pegar**.
    3. Expanda **Página de informe**.
    4. Para forzar que el componente **Página** [considere](er-fillable-excel.md#page-component-structure) este rango un encabezado de página, seleccione **Encabezado de la página del informe** y luego, en la pestaña **Formato**, en el campo **Dirección de replicación**, seleccione **Sin replicación**.

6. Para paginar un documento generado de modo que se considere el contenido de las líneas del informe, siga estos pasos:

    1. Seleccione el componente **Líneas del informe** y luego seleccione **Cortar**.
    2. Seleccione el componente **Página del informe** y luego seleccione **Pegar**.

7. Para incluir el pie de página del informe después de las líneas del informe pero antes del pie de página final, siga estos pasos:

    1. Seleccione el componente **Pie del informe** y luego seleccione **Cortar**.
    2. Seleccione el componente **Página del informe** y luego seleccione **Pegar**.

8. Para usar el componente **Pie de la página del informe** como pie de página en cada página generada, siga estos pasos:

    1. Seleccione el componente **Pie de página del informe** y luego seleccione **Cortar**.
    2. Seleccione el componente **Página del informe** y luego seleccione **Pegar**.
    3. Para forzar que el componente **Página** [considere](er-fillable-excel.md#page-component-structure) este rango un pie de página, seleccione **Pie de la página del informe** y luego, en la pestaña **Formato**, en el campo **Dirección de replicación**, seleccione **Sin replicación**.

![Estructura de formato en el diseñador de formato ER después de implementar la paginación del documento.](./media/er-paginate-excel-reports-format3.png)

### <a name="add-data-sources-to-calculate-page-footer-totals"></a>Agregar orígenes de datos para calcular los totales de pie de página

Debe configurar nuevos orígenes de datos para calcular el total de páginas, el contador en ejecución y los valores totales en ejecución, y mostrarlos en la sección de pie de página. Le recomendamos que utilice orígenes de datos de [Recopilación de datos](er-data-collection-data-sources.md) para este fin.

1. En la página **Diseñador de formato**, seleccione la pestaña **Asignación** .
2. Seleccione **Agregar raíz** y, a continuación, siga estos pasos:

    1. En el cuadro de diálogo **Agregar orígenes de datos**, en la sección **General**, seleccione **Contenedor vacío**.
    2. En el cuadro de diálogo **Propiedades del origen de datos 'Contenedor vacío'**, en el campo **Nombre**, introduzca **Total**.
    3. Seleccione **Aceptar**.

3. Seleccione el origen de datos **Total**, seleccione **Agregar** y luego siga estos pasos:

    1. En el cuadro de diálogo **Agregar orígenes de datos**, en la sección **General**, seleccione **Contenedor vacío**.
    2. En el cuadro de diálogo **Propiedades del origen de datos 'Contenedor vacío'**, en el campo **Nombre**, introduzca **Página**.
    3. Seleccione **Aceptar**.

4. Seleccione de nuevo **Agregar** y, a continuación, siga estos pasos:

    1. En el cuadro de diálogo **Agregar orígenes de datos**, en la sección **General**, seleccione **Contenedor vacío**.
    2. En el cuadro de diálogo **Propiedades del origen de datos 'Contenedor vacío'**, en el campo **Nombre**, introduzca **Ejecución**.
    3. Seleccione **Aceptar**.

5. Seleccione el origen de datos **Total.Page**, seleccione **Agregar** y luego siga estos pasos:

    1. En el cuadro de diálogo **Agregar orígenes de datos**, en la sección **Funciones**, seleccione **Recopilación de datos**.
    2. En el cuadro de diálogo **Propiedades del origen de datos 'Recopilación de datos'**, en el campo **Nombre**, introduzca **Cantidad**.
    3. En el campo **Tipo de artículo**, seleccione **Real**.
    4. Establezca la opción **Recopilar todos los valores** en **Sí**.
    5. Seleccione **Aceptar**.

6. Seleccione de nuevo **Agregar** y, a continuación, siga estos pasos:

    1. En el cuadro de diálogo **Agregar orígenes de datos**, en la sección **Funciones**, seleccione **Recopilación de datos**.
    2. En el cuadro de diálogo **Propiedades del origen de datos 'Recopilación de datos'**, en el campo **Nombre**, introduzca **Peso**.
    3. En el campo **Tipo de artículo**, seleccione **Real**.
    4. Establezca la opción **Recopilar todos los valores** en **Sí**.
    5. Seleccione **Aceptar**.

7. Seleccione el origen de datos **Total.Running**, seleccione **Agregar** y luego siga estos pasos:

    1. En el cuadro de diálogo **Agregar orígenes de datos**, en la sección **Funciones**, seleccione **Recopilación de datos**.
    2. En el cuadro de diálogo **Propiedades del origen de datos 'Recopilación de datos'**, en el campo **Nombre**, introduzca **Cantidad**.
    3. En el campo **Tipo de artículo**, seleccione **Real**.
    4. Establezca el campo **Recopilar todos los valores** en **Sí**.
    5. Seleccione **Aceptar**.

8. Seleccione de nuevo **Agregar** y, a continuación, siga estos pasos:

    1. En el cuadro de diálogo **Agregar orígenes de datos**, en la sección **Funciones**, seleccione **Recopilación de datos**.
    2. En el cuadro de diálogo **Propiedades del origen de datos 'Recopilación de datos'**, en el campo **Nombre**, introduzca **Peso**.
    3. En el campo **Tipo de artículo**, seleccione **Real**.
    4. Establezca el campo **Recopilar todos los valores** en **Sí**.
    5. Seleccione **Aceptar**.

9. Seleccione de nuevo **Agregar** y, a continuación, siga estos pasos:

    1. En el cuadro de diálogo **Agregar orígenes de datos**, en la sección **Funciones**, seleccione **Recopilación de datos**.
    2. En el cuadro de diálogo **Propiedades del origen de datos 'Recopilación de datos'**, en el campo **Nombre**, introduzca **Líneas**.
    3. En el campo **Tipo de artículo**, seleccione **Entero**.
    4. Establezca el campo **Recopilar todos los valores** en **Sí**.
    5. Seleccione **Aceptar**.

10. Seleccione **Guardar**.

### <a name="add-data-sources-to-control-page-footer-visibility"></a>Agregar orígenes de datos para controlar la visibilidad del pie de página

Si planea controlar la visibilidad del pie de página y no planea incluir el pie de página en la página final si contiene transacciones, configure un nuevo origen de datos para calcular el contador de ejecuciones.

1. En la página **Diseñador de formato**, seleccione la pestaña **Asignación** .
2. Seleccione el origen de datos **Total.Running** y elija **Agregar**.
3. En el cuadro de diálogo **Agregar orígenes de datos**, en la sección **Funciones**, seleccione **Recopilación de datos**.
4. En el cuadro de diálogo **Propiedades del origen de datos 'Recopilación de datos'**, en el campo **Nombre**, introduzca **Lines2**.
5. En el campo **Tipo de artículo**, seleccione **Entero**.
6. Establezca la opción **Recopilar todos los valores** en **Sí**.
7. Seleccione **Aceptar**.
8. Seleccione **Guardar**.

![Se agregaron fuentes de datos en el diseñador de formato ER.](./media/er-paginate-excel-reports-format4.png)

### <a name="configure-bindings-to-collect-total-values"></a>Configurar enlaces para recopilar valores totales

1. En la página **Diseñador de formatos**, en el árbol de formato, expanda el componente **Líneas de informe**, y seleccione el componente **Valor de la factura**.
2. Seleccione **Editar fórmula**.
3. Cambie la fórmula vinculante de `NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", "")` a `Total.Page.Amount.Collect(NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", ""))`.

    > [!NOTE]
    > Además de poner el valor de la cantidad en una celda de Excel para cada transacción iterada, este enlace recopila el valor en el origen de datos de recopilación de datos **Total.Page.Amount**.

4. Seleccione el componente anidado **Peso**.
5. Seleccione **Editar fórmula**.
6. Cambie la fórmula vinculante de `@.'$RoundedWeight'` a `Total.Page.Weight.Collect(@.'$RoundedWeight')`.

    > [!NOTE]
    > Además de poner el valor del peso en una celda de Excel para cada transacción iterada, este enlace recopila el valor en el origen de datos **Total.Page.Weight**.

![Enlaces configurados para recopilar valores totales en el diseñador de formato ER.](./media/er-paginate-excel-reports-format5.png)

### <a name="configure-bindings-to-fill-in-page-footer-totals"></a>Configurar enlaces para completar los totales de pie de página

1. En la página **Diseñador de formatos**, en el árbol de formatos, expanda el componente **Pie de página del informe**, seleccione el anidado **Rango** que se refiere a la celda de Excel **ReportPageFooter\_PageAmount** y luego siga estos pasos:

    1. En el árbol de orígenes de datos en el panel derecho, seleccione el artículo **Total.Page.Amount.Sum()**.
    2. Seleccione **Enlazar**.
    3. Seleccione **Editar fórmula**.
    4. Actualice la fórmula a `Total.Page.Amount.Sum(false)`.

    > [!NOTE]
    > Debe especificar el argumento de esta función como **False** para mantener los datos recopilados para la página actual, porque estos datos son necesarios para calcular la cantidad total acumulada, el número total de líneas por página y el contador de ejecución de líneas.

2. En el árbol de formatos, seleccione el componente anidado **Rango** que se refiere a la celda de Excel **ReportPageFooter\_PageWeight** y luego siga estos pasos:

    1. En el árbol de orígenes de datos del panel derecho, seleccione el artículo **Total.Page.Weight.Sum()**.
    2. Seleccione **Enlazar**.
    3. Seleccione **Editar fórmula**.
    4. Actualice la fórmula a `Total.Page.Weight.Sum(false)`.

### <a name="configure-bindings-to-fill-in-page-running-totals"></a>Configurar enlaces para completar los totales de ejecuciones de página

1. En la página **Diseñador de formatos**, en el árbol de formatos, expanda el componente **Pie de página del informe**, seleccione el anidado **Rango** que se refiere a la celda de Excel **ReportPageFooter\_RunningTotalAmount** y luego siga estos pasos:

    1. En el árbol de orígenes de datos en el panel derecho, seleccione el artículo **Total.Running.Amount.Collect()**.
    2. Seleccione **Enlazar**.
    3. Seleccione **Editar fórmula**.
    4. Actualice la fórmula a `Total.Running.Amount.Sum(false)+Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))`.

    > [!NOTE]
    > El operando `Total.Running.Amount.Sum(false)` devuelve la cantidad total acumulada previamente. El operando `Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))` devuelve la cantidad total de la página actual. Debe especificar el argumento de la función anidada del segundo operando como **True** para restablecer la recopilación de datos `Total.Page.Amount` tan pronto como este valor se ponga en la recopilación de total de ejecuciones `Total.Running.Amount`. El argumento especificado debe comenzar a recopilar el total de la página siguiente a partir de un valor 0 (cero).
    >
    > Se llama a la función `Total.Running.Amount.Sum(false)` para introducir la cantidad total acumulada en la celda de Excel **ReportPageFooter\_RunningTotalAmount** de la página actual.

2. En el árbol de formatos, seleccione el componente anidado **Rango** que se refiere a la celda de Excel **ReportPageFooter\_RunningTotalWeight** y luego siga estos pasos:

    1. En el árbol de orígenes de datos del panel derecho, seleccione el artículo **Total.Running.Weight.Collect()**.
    2. Seleccione **Enlazar**.
    3. Seleccione **Editar fórmula**.
    4. Actualice la fórmula a `Total.Running.Weight.Sum(false)+Total.Running.Weight.Collect(Total.Page.Weight.Sum(true))`.

### <a name="configure-bindings-to-fill-in-the-page-running-counter"></a>Configurar enlaces para completar el contador de ejecuciones de página

1. En la página **Diseñador de formatos**, en el árbol de formatos, expanda el componente **Pie de página del informe**, seleccione el anidado **Rango** que se refiere a la celda de Excel **ReportPageFooter\_RunningCounterLines** y luego siga estos pasos:
2. Seleccione **Editar fórmula**.
3. Agregue la fórmula `Total.Running.Lines.Collect(COUNT(Total.Page.Amount.Result))`.

    > [!NOTE]
    > Esta fórmula devuelve el número de valores de cantidad recopilados para todo el informe. Este número es igual al número de transacciones que se han iterado en el momento actual. Al mismo tiempo, la fórmula recopila el valor devuelto en la recopilación **Total.Running.Líneas**.

### <a name="configure-bindings-to-fill-in-the-page-footer-counter"></a>Configurar enlaces para completar el contador de pie de página

1. En la página **Diseñador de formatos**, en el árbol de formatos, expanda el componente **Pie de página del informe**, seleccione el anidado **Rango** que se refiere a la celda de Excel **ReportPageFooter\_PageLines** y luego siga estos pasos:
2. Seleccione **Editar fórmula**.
3. Agregue la fórmula `COUNT(Total.Page.Amount.Result)-Total.Running.Lines.Sum(false)`.

    > [!NOTE]
    > Esta fórmula calcula el número de transacciones en la página actual como la diferencia entre el número de transacciones que se recopilaron en **Total.Page.Amount.Result** para el informe completo y el número de transacciones que se han almacenado en esta etapa en **Total.Running.Lines.Sum**. Debido a que el número de transacciones de la página actual se almacena en **Total.Running.Lines** en el enlace del componente **Rango** que se refiere a la celda de Excel **ReportPageFooter\_RunningCounterLines**, el número de transacciones en la página actual aún no está incluido. Por lo tanto, esta diferencia es igual al número de transacciones en la página actual.

![Enlaces configurados para rellenar el contador de pie de página en el diseñador de formato ER.](./media/er-paginate-excel-reports-format6.png)

### <a name="configure-component-visibility"></a>Configurar la visibilidad de componentes

Puede cambiar la visibilidad del encabezado y pie de página de una página específica de un documento generado para ocultar los siguientes elementos:

- El encabezado de la página en la primera página, porque el encabezado del informe ya contiene títulos de columna
- El encabezado de la página en cualquier página que no tenga transacciones que puedan ocurrir para la última página
- El pie de página en cualquier página que no tenga transacciones que puedan ocurrir para la última página

Para cambiar la visibilidad, actualice la propiedad **Activado** de los componentes **Encabezado de la página del informe** y **Pie de página del informe**.

1. En la página **Diseñador de formatos**, en el árbol de formatos, expanda el componente **Página de informe**, seleccione el componente **Encabezado de página de informe** y luego siga estos pasos:

    1. Seleccione **Editar** para el campo **Habilitado**.
    2. En la página **Diseñador de fórmulas**, en el campo **Fórmula**, introduzca la expresión siguiente:

        `AND(`<br>
        `COUNT(Total.Page.Amount.Result)<>0,`<br>
        `COUNT(Total.Page.Amount.Result)<>COUNT(model.CommodityRecord)`<br>
        `)`

2. En el árbol de formatos, seleccione el componente anidado **Pie de página del informe** y luego siga estos pasos:

    1. Seleccione **Editar** para el campo **Habilitado**.
    2. En la página **Diseñador de fórmulas**, en el campo **Fórmula**, introduzca la expresión siguiente:

        `(`<br>
        `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)+`<br>
        `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result))`<br>
        `)<>0`

    > [!NOTE]
    > La construcción `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)` se utiliza para calcular el número de transacciones en la página actual. La construcción `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result)` se usa para agregar el número de transacciones en la página actual a la colección, para manejar correctamente la visibilidad del pie de página siguiente.
    >
    > La colección `Total.Running.Lines` no se puede reutilizar aquí, porque la propiedad **Habilitado** de un componente base se procesa **después** de los enlaces de componentes anidados. Cuando se procesa la propiedad **Habilitado** , la colección `Total.Running.Lines` ya se ha incrementado en el número de transacciones en la página actual.

3. Seleccione **Guardar**.

## <a name="generate-an-intrastat-declaration-control-report-updated"></a>Generar un informe de control de declaración Intrastat (actualizado)

1. Asegúrese de tener 24 transacciones Intrastat en la página **Intrastat**. Repita los pasos de la sección [Generar un informe de control de declaración Intrastat](#generate-intrastat-control-report) de este artículo para generar y revisar el informe de control.

    Todas las transacciones se presentan en la primera página. Los totales y contadores de la página son iguales a los totales y contadores del informe. El rango del encabezado de la página se oculta en la primera página, porque el encabezado del informe ya contiene títulos de columna. El encabezado y el pie de página están ocultos en la segunda página porque esa página no contiene transacciones.

    ![Documento Excel generado en la aplicación de escritorio.](./media/er-paginate-excel-reports-document2.gif)

2. Actualice dos transacciones en la página **Intrastat** cambiando el código **Número de artículo** de **D00006** a **L0010**. Observe que el nombre del producto del nuevo artículo, **Par de altavoces estéreo activos**, es más largo que el nombre del producto del artículo original, **Altavoz estándar**. Esta situación fuerza el ajuste del texto en la celda correspondiente del documento generado. La paginación de documentos y la suma y el recuento relacionados con la página ahora deben actualizarse. Repita los pasos de la sección [Generar un informe de control de declaración Intrastat](#generate-intrastat-control-report) para generar y revisar el informe de control.

    Actualmente, las transacciones se presentan en dos páginas y los totales y contadores de las páginas se calculan correctamente. El rango del encabezado de la página está correctamente oculto en la primera página y es visible en la segunda página. El pie de página es visible en ambas páginas porque contienen transacciones.

    ![Documento Excel generado y actualizado en la aplicación de escritorio.](./media/er-paginate-excel-reports-document3.gif)

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="is-there-any-way-to-recognize-when-the-final-page-is-processed-by-the-page-format-component"></a>¿Hay alguna forma de reconocer cuándo el componente de formato de página procesa la página final?

El componente **Página** [no expone](er-fillable-excel.md#page-component-limitations) información sobre el número de la página procesada y el número total de páginas en un documento generado. Sin embargo, puede configurar [fórmulas](er-formula-language.md) ER para reconocer la página final. Este es un ejemplo:

- Calcule el número total de transacciones que ya se han procesado utilizando el componente **Página de informe**. Puede hacer este cálculo utilizando la fórmula `COUNT(Total.Page.Amount.Result)`. 
- Calcule el número total de transacciones que deben procesarse en el enlace `model.CommodityRecord` que está configurado para el componente **Líneas de informe**. Puede hacer este cálculo utilizando la fórmula `COUNT(model.CommodityRecord)`.
- Compare dos números para reconocer la página final. Cuando ambos valores son iguales, se genera la página final.

> [!NOTE]
> Recomendamos que utilice este enfoque solo cuando la propiedad **Activado** del componente **Líneas de informe** no contiene ninguna fórmula que pueda devolver [False](er-formula-supported-data-types-primitive.md#boolean) en tiempo de ejecución para algunos de los [registros](er-formula-supported-data-types-composite.md#record) iterados de la [Lista de registros](er-formula-supported-data-types-composite.md#record-list) limitada.

## <a name="additional-resources"></a>Recursos adicionales

- [Diseñar una configuración para generar documentos en formato de Excel](er-fillable-excel.md)
- [Utilizar orígenes de datos de RECOPILACIÓN DE DATOS en formatos de informes electrónicos (ER)](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

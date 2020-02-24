---
title: Aplazar la ejecución de elementos XML en formatos ER
description: Este tema explica cómo diferir la ejecución de un elemento XML en un formato de informe electrónico (ER).
author: NickSelin
manager: kfend
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: e9f6161186d04b690ee560dac7ee12974d070506
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015380"
---
# <a name="defer-the-execution-of-xml-elements-in-er-formats"></a>Aplazar la ejecución de elementos XML en formatos ER

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="overview"></a>Visión general

Puede usar el diseñador de operaciones del marco de [informes electrónicos (ER)](general-electronic-reporting.md) para [configurar](./tasks/er-format-configuration-2016-11.md) el [componente de formato](general-electronic-reporting.md#FormatComponentOutbound) de una solución ER que se utiliza para generar documentos salientes en formato XML. La estructura jerárquica del componente de formato configurado consta de elementos de formato de varios tipos. Estos elementos de formato se utilizan para completar los documentos generados con la información requerida en tiempo de ejecución. De forma predeterminada, cuando ejecuta un formato ER, los elementos de formato se ejecutan en el mismo orden en que se presentan en la jerarquía de formato: uno por uno, de arriba a abajo. Sin embargo, en tiempo de diseño, puede cambiar el orden de ejecución de cualquier elemento XML del componente de formato configurado.

Al activar la opción <a name="DeferredXmlElementExecution"></a>**Ejecución aplazada** para un elemento XML en el formato configurado, puede diferir (posponer) la ejecución de ese elemento. En este caso, el elemento no se ejecuta hasta que se hayan ejecutado todos los demás elementos de su elemento primario.

Para obtener más información acerca de esta característica, complete el ejemplo de este tema.

## <a name="limitations"></a>Limitaciones

La opción **Ejecución aplazada** solo se admite para elementos XML configurados para un formato ER que se utiliza para generar documentos **salientes** en formato XML.

La opción **Ejecución diferida** solo se admite para elementos XML que residen en otro elemento XML. Por lo tanto, no es aplicable a elementos XML que residen en otros tipos de elementos de formato (por ejemplo, en un elemento **Secuencia XML**).

La opción **Ejecución aplazada** no es compatible con elementos XML que residen en el elemento de formato **Common\\File** cuando el la opción **Archivo dividido** está establecida en **Sí**. Para más información acerca de cómo dividir archivos XML, consulte [Dividir los archivos XML generados según su tamaño y la cantidad de contenido](er-split-files.md).

## <a name="Example"></a>Ejemplo: aplazar la ejecución de un elemento XML en formato ER

Los siguientes pasos explican cómo un usuario con el [rol](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/assign-users-security-roles) de administrador del sistema o consultor funcional de informes electrónicos puede configurar un formato ER que contiene un elemento XML donde el orden de ejecución difiere del orden de la jerarquía de formatos.

Estos pasos se pueden llevar a cabo en la empresa **USMF** de Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Requisitos previos

Para este ejemplo, debe tener acceso a la empresa **USMF** de Finance para uno de los roles siguientes:

- Consultor funcional de informes electrónicos
- Administrador del sistema

Si aún no ha completado el ejemplo del tema [Aplazar la ejecución de elementos de secuencia en formatos ER](er-defer-sequence-element.md#Example), descargue las siguientes [configuraciones](general-electronic-reporting.md#Configuration) de la solución ER de ejemplo.

| Descripción del contenido            | Nombre de archivo |
|--------------------------------|-----------|
| Configuración del modelo datos de ER    | [Model to learn deferred elements.version.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Configuración de la asignación del modelo ER | [Mapping to learn deferred elements.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Antes de comenzar, también debe descargar y guardar la siguiente configuración de la solución ER de ejemplo en su equipo local.

| Descripción del contenido     | Nombre de archivo |
|-------------------------|-----------|
| Configuración del formato de ER | [Format to learn deferred XML elements.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="import-the-sample-er-configurations"></a>Importar las configuraciones de ER de ejemplo

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. Seleccione **Configuraciones de informes**.
3. En la página **Configuraciones**, si la configuración **Modelo para aprender elementos aplazados** no está disponible en el árbol de configuración, impórtela del modelo de datos ER:

    1. Seleccione **Intercambiar** y luego seleccione **Cargar desde archivo XML**.
    2. Seleccione **Examinar**, encuentre y seleccione el archivo **Model to learn deferred elements.1.xml** y luego seleccione **Aceptar**.

4. Si la configuración **Asignación para aprender elementos aplazados** no está disponible en el árbol de configuración, impórtela del modelo de datos ER:

    1. Seleccione **Intercambiar** y luego seleccione **Cargar desde archivo XML**.
    2. Seleccione **Examinar**, encuentre y seleccione el archivo **Mapping to learn deferred elements.1.1.xml** y luego seleccione **Aceptar**.

5. Importar la configuración de formato ER:

    1. Seleccione **Intercambiar** y luego seleccione **Cargar desde archivo XML**.
    2. Seleccione **Examinar**, encuentre y seleccione el archivo **Format to learn deferred XML elements.1.1.xml** y luego seleccione **Aceptar**.

6. En el árbol de configuración, expanda **Modelo para aprender elementos aplazados**.
7. Revise la lista de configuraciones de ER importadas en el árbol de configuración.

    ![Configuraciones de ER importadas en la página Configuraciones](./media/ER-DeferredXml-Configurations.png)

### <a name="activate-a-configuration-provider"></a>Activar un proveedor de configuración

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, compruebe que aparece el [proveedor de la configuración](general-electronic-reporting.md#Provider) para la empresa de ejemplo Litware, Inc. (`http://www.litware.com`) y que se ha marcado como activo. Si este proveedor de configuración no aparece en la lista o si no está marcado como activo, siga los pasos de [Crear un proveedor de configuración y marcarlo como activo](./tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Empresa de ejemplo Litware, Inc. en la página Configuraciones de localización](./media/ER-DeferredXml-ElectronicReportingWorkspace.png)

### <a name="review-the-imported-model-mapping"></a>Revisar la asignación de modelo importada

Revise la configuración del componente de asignación del modelo ER que está configurado para acceder a las transacciones fiscales y exponer los datos a los que se tiene acceso a petición.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. Seleccione **Configuraciones de informes**.
3. En la página **Configuraciones**, en el árbol de configuraciones, expanda **Modelo para aprender elementos aplazados**.
4. Seleccione la configuración **Asignación para aprender elementos aplazados**.
5. Seleccione **Diseñador** para abrir la lista de asignaciones.
6. Seleccione **Diseñador** para revisar los detalles de la asignación.
7. Seleccionar **Mostrar detalles**.
8. Revise los orígenes de datos que están configurados para acceder a las transacciones fiscales:

    - El origen de datos **Transacciones** del tipo *Registro de tabla* está configurado para acceder a los registros de la tabla de aplicaciones **TaxTrans**.
    - El origen de datos **Asientos** del tipo *Campo calculado* está configurado para devolver los códigos de asiento necesarios (**INV-10000349** y **INV-10000350**) como una lista de registros.
    - El origen de datos **Filtrado** del tipo *Campo calculado* está configurado para seleccionar, desde el origen de datos **Transacciones**, solo las transacciones de impuestos de los asientos requeridos.
    - El campo **\$TaxAmount** del tipo *Campo calculado* se agrega para que el origen de datos **Filtrado** exponga el valor del impuesto que tiene el signo opuesto.
    - El origen de datos **Agrupado** del tipo *Agrupar por* está configurado para agrupar transacciones de impuestos filtradas del origen de datos **Filtrado**.
    - El campo de agregación **TotalSum** del origen de datos **Agrupado** está configurado para resumir los valores del campo **\$TaxAmount** del origen de datos **Filtrado** para todas las transacciones de impuestos filtradas de ese origen de datos.

        ![Campo de agregación TotalSum en la página de parámetros Editar 'GroupBy'](./media/ER-DeferredXml-GroupByParameters.png)

9. Revise cómo los orígenes de datos configurados están vinculados al modelo de datos y cómo exponen los datos a los que se accede para que estén disponibles en un formato ER:

    - El origen de datos **Filtrado** está vinculado al campo **Lista de datos** del modelo de datos.
    - El campo **\$TaxAmount** del origen de datos **Filtrado** está vinculado al campo **Data.List.Value** del modelo de datos.
    - El campo **TotalSum** del origen de datos **Agrupado** está vinculado al campo **Data.Summary.Total** del modelo de datos.

    ![Página de diseñador de asignación de modelos](./media/ER-DeferredXml-ModelMapping.png)

10. Cierre las páginas **Diseñador de asignación de modelos** y **Asignaciones de modelos**.

### <a name="review-the-imported-format"></a>Revisar el formato importado

1. En la página **Configuraciones**, en el árbol de configuración, seleccione la configuración **Formato para aprender elementos XML aplazados**.
2. Seleccione **Diseñador** para revisar los detalles de la asignación.
3. Seleccionar **Mostrar detalles**.
4. Revise la configuración de los componentes del formato ER que están configurados para generar un documento saliente en formato XML que incluye detalles de las transacciones fiscales:

    - El elemento XML **Report\\Message** está configurado para llenar el documento saliente con un solo nodo que incluye los elementos XML anidados (**Header**, **Record** y **Summary**).
    - El elemento XML **Report\\Message\\Header** está configurado para llenar el documento saliente con un solo nodo de encabezado que muestra la fecha y la hora en que comienza el procesamiento.
    - El elemento XML **Report \\Message\\Record** está configurado para llenar el documento saliente con un solo nodo de registro que muestra los detalles de una sola transacción de impuestos.
    - El elemento XML **Report\\Message\\Summary** está configurado para llenar el documento saliente con un solo nodo de resumen que incluye la suma de los valores de impuestos de las transacciones de impuestos procesadas.

    ![Elemento XML de mensaje y elementos XML anidados en la página Diseñador de formato](./media/ER-DeferredXml-Format.png)

5. En la pestaña **Cartografía**, revise los siguientes detalles:

    - El elemento **Report\\Message\\Header** no tiene que estar vinculado a un origen para generar un solo nodo en un documento saliente.
    - El atributo **ExecutionDateTime** genera la fecha y la hora (incluidos los milisegundos) en que se agrega el nodo de encabezado.
    - El elemento **Report\\Message\\Record** está ligado a la lista **model.Data.List** para generar un solo nodo de registro para cada registro de la lista enlazada.
    - El atributo **TaxAmount** está enlazado a **model.Data.List.Value** (que se muestra como **\@.Value** en la vista de ruta relativa) para generar el valor fiscal de la transacción fiscal actual.
    - El atributo **RunningTotal** es un marcador de posición para el total acumulado de los valores impositivos. Actualmente, este atributo no tiene salida, ya que no tiene configurados un enlace ni un valor predeterminado.
    - El atributo **ExecutionDateTime** genera la fecha y la hora (incluidos los milisegundos) en que se procesa la transacción actual en este informe.
    - El elemento **Report\\Message\\Summary** no tiene que estar vinculado a un origen de datos para generar un solo nodo en un documento saliente.
    - El atributo **TotalTaxAmount** está enlazado a **model.Data.Summary.Total** para generar la suma de los valores fiscales de las transacciones fiscales procesadas.
    - El atributo **ExecutionDateTime** genera la fecha y la hora (incluidos los milisegundos) en que se agrega el nodo de resumen.

    ![Pestaña Asignación en la página Diseñador de formato](./media/ER-DeferredXml-Format2.png)

### <a name="run-the-imported-format"></a>Ejecutar el formato importado

1. En la página **Diseñador de formato**, seleccione **Ejecutar**.
2. Descargue el archivo que ofrece el navegador web y ábralo para su revisión.

    ![Archivo descargado](./media/ER-DeferredXml-Run.png)

Observe que el nodo de resumen presenta la suma de los valores de impuestos para las transacciones procesadas. Debido a que el formato está configurado para usar el enlace **model.Data.Summary.Total** para devolver esta suma, la suma se calcula llamando a la agregación **TotalSum** del origen de datos **Grouped** del tipo *GroupBy* en la asignación del modelo. Para calcular esta agregación, la asignación de modelo recorre en iteración todas las transacciones que se han seleccionado en el origen de datos **Filtered**. Al comparar los tiempos de ejecución del nodo de resumen y el último nodo de registro, puede determinar que el cálculo de la suma tomó 12 milisegundos (ms). Al comparar los tiempos de ejecución del primer y último nodo de registro, puede determinar que la generación y suma de todos los nodos de registro tardó 9 ms. Por lo tanto, se requirió un total de 21 ms.

### <a name="modify-the-format-so-that-the-calculation-is-based-on-generated-output"></a>Modificar el formato para que el cálculo se base en la salida generada

Si el volumen de transacción es mucho mayor que el volumen del ejemplo actual, el tiempo de cálculo podría aumentar y causar problemas de rendimiento. Cambiar la configuración del formato puede ayudar a prevenir estos problemas de rendimiento. Debido a que accede a los valores de impuestos para incluirlos en el informe generado, puede reutilizar esta información para calcular valores de impuestos. Para más información, vea [Configurar el formato para contar y sumar](./tasks/er-format-counting-summing-1.md).

1. En la página **Diseñador de formatos**, en la pestaña **Formato**, seleccione el elemento de archivo **Informe** en el árbol de formato.
2. Establezca la opción **Recopilar detalles de salida** en **Sí**. Ahora puede configurar este formato utilizando el contenido de un informe generado como origen de datos al que se puede acceder utilizando las funciones ER integradas en la categoría [Recopilación de datos](er-functions-category-data-collection.md).
3. En la pestaña **Asignación**, seleccione el elemento XML **Report\\Message\\Record**.
4. Configure la expresión **Nombre de clave de datos recopilados** como `WsColumn`.
5. Configure la expresión **Valor de clave de datos recopilados** como `WsRow`.

    ![Elemento XML de registro en la página Diseñador de formato](./media/ER-DeferredXml-Format3.png)

6. Seleccione el atributo **Report\\Message\\Record\\TaxAmount**.
7. Configure la expresión **Nombre de clave de datos recopilados** como `SummingAmountKey`.

    ![Atributo TaxAmount en la página Diseñador de formato](./media/ER-DeferredXml-Format4.png)

    Puede considerar esta configuración como el cumplimiento de una hoja de trabajo virtual, donde el valor de la celda A1 se agrega con el valor del importe de los impuestos de cada transacción de impuestos procesada.

8. Seleccione el atributo **Report\\Message\\Record\\RunningTotal** y luego seleccione **Editar fórmula**.
9. Configure la expresión `SUMIF(SummingAmountKey, WsColumn, WsRow)` utilizando la función ER [SUMIF](er-functions-datacollection-sumif.md) integrada y seleccione **Guardar**.

    ![Expresión SUMIF](./media/ER-DeferredXml-FormulaDesigner.png)

10. Cierre la página **Diseñador de fórmula**.
11. Seleccione **Guardar** y, a continuación, seleccione **Ejecutar**.
12. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado](./media/ER-DeferredXml-Run1.png)

    El último nodo de registro contiene el total acumulado de los valores impositivos para todas las transacciones procesadas utilizando la salida generada como origen de datos. Este origen de datos comienza desde el principio del informe y continúa hasta la última transacción fiscal. El nodo de resumen contiene la suma de los valores impositivos para todas las transacciones procesadas que se calculan en la asignación del modelo utilizando el origen de datos del tipo *GroupBy*. Tenga en cuenta que los valores son iguales. Por lo tanto, la suma basada en la salida se puede usar en lugar de **GroupBy**. Al comparar los tiempos de ejecución del primer nodo de registro y del nodo de resumen, puede determinar que la generación y suma de todos los nodos de registro tardó 11 ms. Por lo tanto, en lo que respecta a la generación de nodos de registro y la suma de los valores fiscales, el formato modificado es aproximadamente dos veces más rápido que el formato original.

13. Seleccione el atributo **Report\\Message\\Summary\\TotalTaxAmount** y luego seleccione **Editar fórmula**.
14. Introduzca la expresión `SUMIF(SummingAmountKey, WsColumn, WsRow)` en lugar de la expresión existente.
15. Seleccione **Guardar** y, a continuación, seleccione **Ejecutar**.
16. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado](./media/ER-DeferredXml-Run2.png)

    Observe que el total acumulado de los valores de impuestos del último nodo de registro ahora es igual a la suma en el nodo de resumen.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Colocar los valores de la suma basada en la salida en el encabezado del informe

Si, por ejemplo, debe presentar la suma de los valores impositivos en el encabezado del informe, puede modificar su formato.

1. En la página **Diseñador de formato**, en la pestaña **Formato**, seleccione el elemento XML **Report\\Message\\Summary**.
2. Seleccione **Subir**.
3. Seleccione **Guardar** y, a continuación, seleccione **Ejecutar**.
4. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado](./media/ER-DeferredXml-Run3.png)

    Observe que la suma de los valores impositivos del nodo de resumen ahora es igual a 0 (cero), porque esta suma ahora se calcula en función de la salida generada. Cuando se genera el primer nodo de registro, la salida generada aún no contiene nodos de registro que tienen detalles de transacción. Puede configurar este formato para aplazar la ejecución del elemento **Report\\Message\\Summary** hasta que el elemento **Report\\Message\\Record** se haya ejecutado para todas las transacciones fiscales.

### <a name="defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used"></a>Aplazar la ejecución del elemento XML de resumen para que se use el total calculado

1. En la página **Diseñador de formato**, en la pestaña **Formato**, seleccione el elemento XML **Report\\Message\\Summary**.
2. Establezca la opción **Ejecución aplazada** en **Sí**.

    ![Opción Ejecución aplazada del elemento XML Resumen en la página Diseñador de formato](./media/ER-DeferredXml-Format5.png)

3. Seleccione **Guardar** y, a continuación, seleccione **Ejecutar**.
4. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado](./media/ER-DeferredXml-Run4.png)

    El elemento **Report\\Message\\Summary** ahora se ejecuta solo después de todos los demás elementos que están anidados bajo su elemento principal, **Report\\Message**. Por lo tanto, se ejecuta después de que el elemento **Report\\Message\\Record** se haya ejecutado para todas las transacciones fiscales del origen de datos **model.Data.List**. Los tiempos de ejecución del primer y último nodo de registro, y de los nodos de encabezado y resumen, revelan este hecho.

## <a name="additional-resources"></a>Recursos adicionales

- [Configurar el formato para contar y sumar](./tasks/er-format-counting-summing-1.md)
- [Ejecución de seguimiento del formato de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md)
- [Aplazar la ejecución de elementos de secuencia en formatos ER](er-defer-sequence-element.md#Example)

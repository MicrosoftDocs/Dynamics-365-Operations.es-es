---
title: Aplazar la ejecución de elementos de secuencia en formatos ER
description: Este tema explica cómo diferir la ejecución de un elemento de secuencia en un formato de informe electrónico (ER).
author: NickSelin
manager: kfend
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-01
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 9aa019e20b218fdaad4659fa65d9df629069204b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680743"
---
# <a name="defer-the-execution-of-sequence-elements-in-er-formats"></a>Aplazar la ejecución de elementos de secuencia en formatos ER

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Visión general

Puede usar el diseñador de operaciones del marco de [informes electrónicos (ER)](general-electronic-reporting.md) para [configurar](tasks/er-format-configuration-2016-11.md) el [componente de formato](general-electronic-reporting.md#FormatComponentOutbound) de una solución ER que se utiliza para generar documentos salientes en formato de texto. La estructura jerárquica del componente de formato configurado consta de elementos de formato de varios tipos. Estos elementos de formato se utilizan para completar los documentos generados con la información requerida en tiempo de ejecución. De forma predeterminada, cuando ejecuta un formato ER, los elementos de formato se ejecutan en el mismo orden en que se presentan en la jerarquía de formato: uno por uno, de arriba a abajo. Sin embargo, en tiempo de diseño, puede cambiar el orden de ejecución de cualquier elemento de secuencia del componente de formato configurado.

Al activar la opción <a name="DeferredSequenceExecution"></a>**Ejecución aplazada** para un elemento de formato de secuencia en el formato configurado, puede diferir (posponer) la ejecución de ese elemento. En este caso, el elemento no se ejecuta hasta que se hayan ejecutado todos los demás elementos de su elemento primario.

Para obtener más información acerca de esta característica, complete el ejemplo de este tema.

## <a name="limitations"></a>Limitaciones

La opción **Ejecución aplazada** solo se admite para elementos de secuencia configurados para un formato ER que se utiliza para generar documentos **salientes** en formato de texto.

La opción **Ejecución aplazada** no es aplicable a las secuencias que se han configurado como secuencias recortadas donde la longitud máxima está limitada.

## <a name="example-defer-the-execution-of-a-sequence-element-in-an-er-format"></a><a name="Example"></a>Ejemplo: aplazar la ejecución de un elemento de secuencia en formato ER

Los siguientes pasos explican cómo un usuario con el [rol](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/assign-users-security-roles) de administrador del sistema o consultor funcional de informes electrónicos puede configurar un formato ER que contiene un elemento de secuencia donde el orden de ejecución difiere del orden de la jerarquía de formatos.

Estos pasos se pueden llevar a cabo en la empresa **USMF** de Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Requisitos previos

Para este ejemplo, debe tener acceso a la empresa **USMF** de Finance para uno de los roles siguientes:

- Consultor funcional de informes electrónicos
- Administrador del sistema

Si aún no ha completado el ejemplo del tema [Aplazar la ejecución de elementos XML en formatos ER](er-defer-xml-element.md#Example), descargue las siguientes [configuraciones](general-electronic-reporting.md#Configuration) de la solución ER de ejemplo.

| Descripción del contenido            | Nombre de archivo |
|--------------------------------|-----------|
| Configuración del modelo datos de ER    | [Model to learn deferred elements.version.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Configuración de la asignación del modelo ER | [Mapping to learn deferred elements.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Antes de comenzar, también debe descargar y guardar la siguiente configuración de la solución ER de ejemplo.

| Descripción del contenido     |Nombre de archivo |
|-------------------------|----------|
| Configuración del formato de ER | [Format to learn deferred sequences.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

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
    2. Seleccione **Examinar**, encuentre y seleccione el archivo **Format to learn deferred sequences.1.1.xml** y luego seleccione **Aceptar**.

6. En el árbol de configuración, expanda **Modelo para aprender elementos aplazados**.
7. Revise la lista de configuraciones de ER importadas en el árbol de configuración.

    ![Configuraciones de ER importadas en la página Configuraciones](./media/ER-DeferredSequence-Configurations.png)

### <a name="activate-a-configurations-provider"></a>Activar un proveedor de las configuraciones

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, compruebe que aparece el [proveedor de la configuración](general-electronic-reporting.md#Provider) para la empresa de ejemplo Litware, Inc. (`http://www.litware.com`) y que se ha marcado como activo. Si este proveedor de configuración no aparece en la lista o si no está marcado como activo, siga los pasos de [Crear un proveedor de configuración y marcarlo como activo](./tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Empresa de ejemplo Litware, Inc. en la página Configuraciones de localización](./media/ER-DeferredSequence-ElectronicReportingWorkspace.png)

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

        ![Campo de agregación TotalSum en la página de parámetros Editar 'GroupBy'](./media/ER-DeferredSequence-GroupByParameters.png)

9. Revise cómo los orígenes de datos configurados están vinculados al modelo de datos y cómo exponen los datos a los que se accede para que estén disponibles en un formato ER:

    - El origen de datos **Filtrado** está vinculado al campo **Lista de datos** del modelo de datos.
    - El campo **\$TaxAmount** del origen de datos **Filtrado** está vinculado al campo **Data.List.Value** del modelo de datos.
    - El campo **TotalSum** del origen de datos **Agrupado** está vinculado al campo **Data.Summary.Total** del modelo de datos.

    ![Página de diseñador de asignación de modelos](./media/ER-DeferredSequence-ModelMapping.png)

10. Cierre las páginas **Diseñador de asignación de modelos** y **Asignaciones de modelos**.

### <a name="review-the-imported-format"></a>Revisar el formato importado

1. En la página **Configuraciones**, en el árbol de configuración, seleccione la configuración **Formato para aprender secuencias aplazadas**.
2. Seleccione **Diseñador** para revisar los detalles de la asignación.
3. Seleccionar **Mostrar detalles**.
4. Revise la configuración de los componentes del formato ER que están configurados para generar un documento saliente en formato de texto que incluye detalles de las transacciones fiscales:

    - El elemento de formato de secuencia **Informe\\Líneas** está configurado para llenar el documento saliente con una sola línea que se genera a partir de los elementos de secuencia anidados (**Encabezamiento**, **Registro** y **Resumen**).

        ![Elemento de formato de secuencia de líneas y elementos anidados en la página del diseñador de formatos](./media/ER-DeferredSequence-Format.png)

    - El elemento de formato de secuencia **Informe\\Líneas\\Encabezamiento** está configurado para llenar el documento saliente con una sola línea de encabezado que muestra la fecha y la hora en que comienza el procesamiento.
    - El elemento de formato de secuencia **Informe\\Líneas\\Registro** está configurado para llenar el documento saliente con una sola línea que muestra los detalles de las transacciones de impuestos individuales. Estas transacciones de impuestos están separadas por un punto y coma.

        ![Elemento de formato de secuencia de registro que utiliza un punto y coma como delimitador](./media/ER-DeferredSequence-Format1.png)

    - El elemento de formato de secuencia **Informe\\Líneas\\Resumen** está configurado para llenar el documento saliente con una sola línea de resumen que incluye la suma de los valores de impuestos de las transacciones de impuestos procesadas.

4. En la pestaña **Cartografía**, revise los siguientes detalles:

    - El elemento **Informe\\Líneas\\Encabezamiento** no tiene que estar vinculado a un origen de datos para generar una sola línea en un documento saliente.
    - El elemento **Prefix1** genera símbolos **P1** para indicar que la línea que se agrega es la línea del encabezado del informe.
    - El elemento **ExecutionDateTime** genera la fecha y la hora (incluidos los milisegundos) en que se agrega la línea de encabezado.
    - El elemento **Report\\Lines\\Record** está ligado a la lista **model.Data.List** para generar una sola línea para cada registro de la lista enlazada.
    - El elemento **Prefix2** genera símbolos **P2** para indicar que la línea que se agrega es para los detalles de las transacciones fiscales.
    - El elemento **TaxAmount** está enlazado a **model.Data.List.Value** (que se muestra como **\@.Value** en la vista de ruta relativa) para generar el valor fiscal de la transacción fiscal actual.
    - El elemento **RunningTotal** es un marcador de posición para el total acumulado de los valores impositivos. Actualmente, este elemento no tiene salida, ya que no tiene configurados un enlace ni un valor predeterminado.
    - El elemento **ExecutionDateTime** genera la fecha y la hora (incluidos los milisegundos) en que se procesa la transacción actual en este informe.
    - El elemento **Report\\Lines\\Summary** no tiene que estar vinculado a un origen de datos para generar una sola línea en un documento saliente.
    - El elemento **Prefix3** genera símbolos **P3** para indicar que la línea que se agrega contiene el valor de impuestos totales.
    - El elemento **TotalTaxAmount** está enlazado a **model.Data.Summary.Total** para generar la suma de los valores fiscales de las transacciones fiscales procesadas.
    - El elemento **ExecutionDateTime** genera la fecha y la hora (incluidos los milisegundos) en que se agrega la línea de resumen.

    ![Pestaña Asignación en la página Diseñador de formato](./media/ER-DeferredSequence-Format2.png)

### <a name="run-the-imported-format"></a>Ejecutar el formato importado

1. En la página **Diseñador de formato**, seleccione **Ejecutar**.
2. Descargue el archivo que ofrece el navegador web y ábralo para su revisión.

    ![Archivo descargado](./media/ER-DeferredSequence-Run.png)

Observe que la línea de resumen 22 presenta la suma de los valores de impuestos para las transacciones procesadas. Debido a que el formato está configurado para usar el enlace **model.Data.Summary.Total** para devolver esta suma, la suma se calcula llamando a la agregación **TotalSum** del origen de datos **Grouped** del tipo *GroupBy* que usa la asignación del modelo. Para calcular esta agregación, la asignación de modelo recorre en iteración todas las transacciones que se han seleccionado en el origen de datos **Filtered**. Al comparar los tiempos de ejecución de las líneas 21 y 22, puede determinar que el cálculo de la suma tardó 10 milisegundos (ms). Al comparar los tiempos de ejecución de las líneas 2 y 21, puede determinar que la generación de todas las líneas transaccionales tardó 7 ms. Por lo tanto, se requirió un total de 17 ms.

### <a name="modify-the-format-so-that-the-summing-is-based-on-generated-output"></a>Modificar el formato para que la suma se base en la salida generada

Si el volumen de transacciones es mucho mayor que el volumen del ejemplo actual, el tiempo de suma podría aumentar y causar problemas de rendimiento. Cambiar la configuración del formato puede ayudar a prevenir estos problemas de rendimiento. Debido a que accede a los valores de impuestos para incluirlos en el informe generado, puede reutilizar esta información para sumar valores de impuestos. Para más información, vea [Configurar el formato para contar y sumar](./tasks/er-format-counting-summing-1.md).

1. En la página **Diseñador de formatos**, en la pestaña **Formato**, seleccione el elemento de archivo **Informe** en el árbol de formato.
2. Establezca la opción **Recopilar detalles de salida** en **Sí**. Ahora puede configurar este formato utilizando el contenido de un informe existente como origen de datos al que se puede acceder utilizando las funciones ER integradas en la categoría [Recopilación de datos](er-functions-category-data-collection.md).
3. En la pestaña **Asignación**, seleccione el elemento de secuencia **Report\\Lines**.
4. Configure la expresión **Nombre de clave de datos recopilados** como `WsColumn`.
5. Configure la expresión **Valor de clave de datos recopilados** como `WsRow`.

    ![Elemento de secuencia de líneas en la página del diseñador de formato](./media/ER-DeferredSequence-Format3.png)

6. Seleccione el elemento numérico **Report\\Lines\\Record\\TaxAmount**.
7. Configure la expresión **Nombre de clave de datos recopilados** como `SummingAmountKey`.

    ![Elemento numérico TaxAmount en la página del diseñador de formato](./media/ER-DeferredSequence-Format4.png)

    Puede considerar esta configuración como el cumplimiento de una hoja de trabajo virtual, donde el valor de la celda A1 se agrega con el valor del importe de los impuestos de cada transacción de impuestos procesada.

8. Seleccione el elemento numérico **Report\\Lines\\Record\\RunningTotal** y luego seleccione **Editar fórmula**.
9. Configure la expresión `SUMIF(SummingAmountKey, WsColumn, WsRow)` utilizando la función ER [SUMIF](er-functions-datacollection-sumif.md) integrada.
10. Seleccione **Guardar**.

    ![Expresión SUMIF](./media/ER-DeferredSequence-FormulaDesigner.png)

11. Cierre la página **Diseñador de fórmula**.
12. Seleccione **Guardar** y, a continuación, seleccione **Ejecutar**.
13. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado](./media/ER-DeferredSequence-Run1.png)

    La línea 21 contiene el total acumulado de los valores impositivos para todas las transacciones procesadas utilizando la salida generada como origen de datos. Este origen de datos comienza desde el principio del informe y continúa hasta la última transacción fiscal. La línea 22 contiene la suma de los valores impositivos para todas las transacciones procesadas que se calculan en la asignación del modelo utilizando el origen de datos del tipo *GroupBy*. Tenga en cuenta que los valores son iguales. Por lo tanto, la suma basada en la salida se puede usar en lugar de **GroupBy**. Al comparar los tiempos de ejecución de las líneas 2 y 21, puede determinar que la generación y suma de todas las líneas transaccionales tardó 9 ms. Por lo tanto, en lo que respecta a la generación de líneas detalladas y la suma de los valores fiscales, el formato modificado es aproximadamente dos veces más rápido que el formato original.

14. Seleccione el elemento numérico **Report\\Lines\\Summary\\TotalTaxAmount** y luego seleccione **Editar fórmula**.
15. Introduzca la expresión `SUMIF(SummingAmountKey, WsColumn, WsRow)` en lugar de la expresión existente.
16. Seleccione **Guardar** y, a continuación, seleccione **Ejecutar**.
17. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado](./media/ER-DeferredSequence-Run2.png)

    Observe que el total acumulado de los valores de impuestos de la última línea de detalles de la transacción ahora es igual a la suma en la línea de resumen.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Colocar los valores de la suma basada en la salida en el encabezado del informe

Si, por ejemplo, debe presentar la suma de los valores impositivos en el encabezado del informe, puede modificar su formato.

1. En la página **Diseñador de formato**, en la pestaña **Formato**, seleccione el elemento de secuencia **Report\\Lines\\Summary**.
2. Seleccione **Subir**.
3. Seleccione **Guardar** y, a continuación, seleccione **Ejecutar**.
4. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado](./media/ER-DeferredSequence-Run3.png)

    Observe que la suma de los valores impositivos en la línea de resumen 2 ahora es igual a 0 (cero), porque esta suma ahora se calcula en función de la salida generada. Cuando se genera la línea 2, la salida generada aún no contiene líneas que tienen detalles de transacción. Puede configurar este formato para aplazar la ejecución del elemento de secuencia **Report\\Lines\\Summary** hasta que el elemento de secuencia **Report\\Lines\\Record** se haya ejecutado para todas las transacciones fiscales.

### <a name="defer-the-execution-of-the-summary-sequence-so-that-the-calculated-total-is-used"></a>Aplazar la ejecución de la secuencia de resumen para que se use el total calculado

1. En la página **Diseñador de formato**, en la pestaña **Formato**, seleccione el elemento de secuencia **Report\\Lines\\Summary**.
2. Establezca la opción **Ejecución aplazada** en **Sí**.

    ![Opción Ejecución aplazada del elemento de secuencia Resumen en la página Diseñador de formato](./media/ER-DeferredSequence-Format5.png)

3. Seleccione **Guardar** y, a continuación, seleccione **Ejecutar**.
4. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado](./media/ER-DeferredSequence-Run4.png)

    El elemento de secuencia **Report\\Lines\\Summary** ahora se ejecuta solo después de todos los demás elementos que están anidados bajo su elemento principal, **Report\\Lines**. Por lo tanto, se ejecuta después de que el elemento de secuencia **Report\\Lines\\Record** se haya ejecutado para todas las transacciones fiscales del origen de datos **model.Data.List**. Los tiempos de ejecución de las líneas 1, 2 y 3 y de la última línea, 22, revelan este hecho.

## <a name="additional-resources"></a>Recursos adicionales

- [Configurar el formato para contar y sumar](./tasks/er-format-counting-summing-1.md)
- [Ejecución de seguimiento del formato de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md)
- [Aplazar la ejecución de elementos XML en formatos ER](er-defer-xml-element.md#Example)

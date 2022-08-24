---
title: Utilizar orígenes de datos de RECOPILACIÓN DE DATOS en formatos de informes electrónicos
description: En este artículo se explica cómo usar orígenes de datos de RECOPILACIÓN DE DATOS en formatos de informes electrónicos (ER).
author: kfend
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.16
ms.custom: 58771
ms.assetid: ''
ms.search.form: EROperationDesigner
ms.openlocfilehash: 221cefc1880cdd88a952140424daf24975a575aa
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286191"
---
# <a name="use-data-collection-data-sources-in-electronic-reporting-formats"></a>Utilizar orígenes de datos de RECOPILACIÓN DE DATOS en formatos de informes electrónicos

[!include [banner](../includes/banner.md)]

Puede usar el Diseñador de operaciones del marco de [informes electrónico (ER)](general-electronic-reporting.md) para configurar el componente de formato de una solución de ER que se utiliza para generar documentos salientes en distintos formatos. La estructura jerárquica del componente de formato configurado consta de tipos de elementos de formato. Estos elementos de formato se utilizan para completar los documentos generados con la información requerida en tiempo de ejecución. De forma predeterminada, cuando ejecuta un formato de informes electrónicos, los elementos de formato se ejecutan en el mismo orden en que se presentan en la jerarquía de formato: uno por uno, de arriba abajo.

Cuando ER ejecuta un elemento de formato que contiene un enlace, se ejecuta la fórmula de ese enlace y el elemento de formato agrega el valor a un documento generado. Por ejemplo, el enlace puede pasar el valor de un campo de modelo de datos a un elemento de formato. Puede configurar un origen de datos de RECOPILACIÓN DE DATOS para recopilar valores de los campos del modelo de datos en tiempo de ejecución, sumar valores y rellenar un documento generado con los valores recopilados. Para utilizar este enfoque, cambie el enlace inicial para que el origen de datos de RECOPILACIÓN DE DATOS configurado se utilice para pasar el valor de un campo de modelo de datos a un elemento de formato. Al pasar valores a través del origen de datos de RECOPILACIÓN DE DATOS, puede recopilar los detalles necesarios para su uso posterior.

Cuando configure un origen de datos de RECOPILACIÓN DE DATOS, especifique un tipo de valor que se administrará en el origen de datos. Actualmente se admiten los siguientes [tipos de datos](er-formula-supported-data-types-primitive.md) para recopilar valores:

- Booleano
- Fecha
- Fecha y hora
- GUID
- Int64
- Entero
- Real
- Cadena
- Time

Puede usar el método `Collect(Value)` de un origen de datos de RECOPILACIÓN DE DATOS para pasar un valor a un origen de datos para su recopilación. En este método, el argumento `Value` es una constante o la ruta válida de un campo de origen de datos del tipo de datos relevante.

Utilice la propiedad `Result` de un origen de datos de RECOPILACIÓN DE DATOS para obtener acceso a la lista de valores recopilados. Esta propiedad devuelve una [lista de registros](er-formula-supported-data-types-composite.md#record-list). Los registros de la lista de registros contienen el campo `Value`, que puede utilizar para obtener acceso a los valores recopilados.

De forma predeterminada, un origen de datos de RECOPILACIÓN DE DATOS solo recopila valores únicos.

Para recopilar todos los valores, establezca el campo **Recopilar todos los valores** del origen de datos de RECOPILACIÓN DE DATOS configurado en **Sí**. Cuando el campo **Recopilar todos los valores** está configurado en **Sí**, la propiedad parametrizada `Sum(Flag)` está disponible. Puede utilizar esta propiedad para obtener el importe total de todos los valores recopilados actualmente. En esta propiedad, el argumento `Flag` es un valor [Booleano](er-formula-supported-data-types-primitive.md#boolean) que se utiliza para indicar si se debe restablecer el valor total.

- Cuando se proporciona el valor **Falso**, se continúa la suma desde el importe recopilado previamente.
- Cuando se proporciona el valor **Verdadero**, se inicia una nueva suma.

Actualmente se admiten los siguientes tipos de datos para sumar:

- Int64
- Entero
- Real

Para obtener más información sobre esta funcionalidad, complete el siguiente ejemplo.

## <a name="example-configure-an-er-format-to-do-counting-and-summing-by-using-a-data-collection-data-source"></a>Ejemplo: configurar un formato de informes electrónicos para realizar recuentos y sumas mediante el uso de un origen de datos de RECOPILACIÓN DE DATOS

Este ejemplo muestra cómo un usuario con la función de Administrador del sistema o Consultor funcional de informes electrónicos puede configurar un formato de ER que tiene un origen de datos de RECOPILACIÓN DE DATOS que se utiliza para calcular totales acumulados y recopilar valores sumados.

Los procedimientos de este ejemplo se pueden completar en la empresa USMF en Microsoft Dynamics 365 Finance.

### <a name="upload-and-use-the-provided-er-solution"></a>Cargar y usar la solución de informes electrónicos proporcionada

1. [Importar las configuraciones de ER de ejemplo](er-defer-sequence-element.md#import-the-sample-er-configurations).
2. [Activar un proveedor de configuración](er-defer-sequence-element.md#activate-a-configurations-provider).
3. [Revisar la asignación de modelo importada](er-defer-sequence-element.md#review-the-imported-model-mapping).
4. [Revisar el formato importado](er-defer-sequence-element.md#review-the-imported-format).
5. [Ejecutar el formato importado](er-defer-sequence-element.md#run-the-imported-format).

### <a name="run-the-format-of-the-provided-er-solution"></a>Ejecutar el formato de la solución de ER proporcionada

1. En la página **Diseñador de formato**, seleccione **Ejecutar**.
2. En el cuadro de diálogo **Parámetros de informes electrónicos**, seleccione **Aceptar**.
3. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado que contiene los resultados de la ejecución del formato inicial](./media/er-data-collection-data-sources-01.png)

### <a name="modify-the-format-of-the-er-solution-to-calculate-the-running-tax-total"></a>Modificar el formato de la solución de ER para calcular el total de impuestos acumulado

Si el volumen de transacciones es mucho mayor que el volumen del ejemplo actual, el tiempo necesario para la suma podría aumentar y causar problemas de rendimiento. Cambiar la configuración del formato puede ayudar a prevenir estos problemas de rendimiento. Puesto que obtiene acceso a los valores de impuestos para incluirlos en el informe generado, puede reutilizar esa información para sumar valores de impuestos.

1. En la página **Diseñador de formato**, en la pestaña **Asignación**, seleccione **Agregar raíz**.
2. En el cuadro de diálogo **Agregar origen de datos**, seleccione **Funciones** \> **Recopilación de datos**.
3. En el cuadro de diálogo **Propiedades del origen de datos de 'Recopilación de datos'**, siga estos pasos:

    1. En el campo **Nombre**, introduzca **CollectedTaxValues**.
    2. En el campo **Tipo de artículo**, seleccione **Real**.
    3. En el campo **Recopilar todos los valores**, seleccione **Sí**.
    4. Seleccione **Aceptar**.

4. Seleccione el elemento de formato numérico **Report\\Lines\\Record\\TaxAmount**.

    > [!NOTE]
    > Actualmente, el enlace `@.Value` está configurado para este elemento. Por tanto, un documento generado se rellena con valores de impuestos procedentes del campo `model.Data.List.Value`.

5. Seleccione **Editar fórmula**.
6. En la página **Diseñador de fórmulas**, siga estos pasos:

    1. En el campo **Fórmula**, reemplace `@.Value` con `CollectedTaxValues.Collect(@.Value)`.
    2. Guarde los cambios y cierre la página.

    > [!NOTE]
    > El nuevo enlace pasará los mismos valores de impuestos a un documento generado. Sin embargo, esos valores también se recopilarán en el origen de datos **CollectedTaxValues**.

7. Seleccione el elemento de formato numérico **Report\\Lines\\Record\\RunningTotal**.
8. Seleccione **Editar fórmula**.
9. En la página **Diseñador de fórmulas**, siga estos pasos:

    1. En el campo **Fórmula**, escriba `CollectedTaxValues.Sum(false)`.
    2. Guarde los cambios y cierre la página.

    > [!NOTE]
    > El nuevo enlace pasará a un documento generado el importe total de los valores de impuestos que ya se han introducido.

    ![Elementos numéricos que tienen enlaces actualizados en la página del Diseñador de formato](./media/er-data-collection-data-sources-02.png)

10. Seleccione **Guardar** y, a continuación, seleccione **Ejecutar**.
11. En el cuadro de diálogo **Parámetros de informes electrónicos**, seleccione **Aceptar**.
12. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado que contiene los resultados de la ejecución del formato modificado](./media/er-data-collection-data-sources-03.png)

### <a name="modify-the-format-to-evaluate-the-list-of-collected-tax-values"></a>Modificar el formato para evaluar la lista de los valores de impuestos recopilados

1. En la página **Diseñador de formato**, en la pestaña **Formato**, seleccione el elemento de formato numérico **Report\\Lines\\Record\\RunningTotal** y siga estos pasos:

    1. En el campo **Tipo numérico**, cambie el valor de **Real** a **Entero**.
    2. En el campo **Formato numérico**, cambie el valor de **F2** a **F0**.

3. En la pestaña **Asignación**, seleccione **Editar fórmula**.
4. En la página **Diseñador de fórmulas**, siga estos pasos:

    1. En el campo **Fórmula**, escriba `COUNT(CollectedTaxValues.Result)`.
    2. Guarde los cambios y cierre la página.

    > [!NOTE]
    > El nuevo enlace pasará a un documento generado el número de registros de la lista donde se recopilan los valores de impuestos.

5. Seleccione **Guardar** y, a continuación, seleccione **Ejecutar**.
6. En el cuadro de diálogo **Parámetros de informes electrónicos**, seleccione **Aceptar**.
7. Descargue y revise el archivo que ofrece el navegador web.

    ![Archivo descargado que contiene los resultados de otra ejecución del formato modificado](./media/er-data-collection-data-sources-04.png)

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions"></a>Si tengo que calcular totales acumulados y recopilar datos, ¿qué diferencia hay entre usar un origen de datos de RECOPILACIÓN DE DATOS y usar las funciones integradas de RECOPILACIÓN DE DATOS?

Para la recopilación, la suma y el recuento de datos se puede utilizar tanto un origen de datos de RECOPILACIÓN DE DATOS como las funciones integradas de [RECOPILACIÓN DE DATOS](er-functions-category-data-collection.md), en función de la información que se pasa a un documento saliente generado. Sin embargo, cuando vaya a decidir qué técnica es mejor utilizar, debe tener en cuenta los siguientes puntos.

| Origen de datos | Funciones integradas |
|-------------| ------------------ |
| Solo se recopilan valores. | <p>Se recopilan valores con nombre. Por tanto, se pueden calcular totales para grupos distintos de valores.</p><p>Además, los grupos se pueden extraer como una lista.</p><p>También se pueden recopilar valores de texto.</p> |
| Los valores únicos se recopilan automáticamente. | Se requieren configuraciones adicionales para extraer una lista de valores únicos de los valores recopilados. |
| El rendimiento depende del volumen de valores recopilados. | En la práctica, el rendimiento no depende del volumen de valores recopilados. |
| Esta técnica funciona bien para todo tipo de documentos salientes. | Esta técnica solo funciona para documentos de texto y XML. |

## <a name="additional-resources"></a>Recursos adicionales

- [Configurar el formato para contar y sumar](./tasks/er-format-counting-summing-1.md)
- [Aplazar la ejecución de elementos de secuencia en formatos de informes electrónicos](er-defer-sequence-element.md#Example)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

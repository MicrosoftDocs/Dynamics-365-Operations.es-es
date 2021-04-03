---
title: Informe de almacenamiento de valor de inventario
description: Este tema explica cómo ejecutar un informe de almacenamiento de valor de inventario y hacer que la salida esté disponible digitalmente, ya sea como una página interactiva en Microsoft Dynamics 365 Supply Chain Management o como documento exportado en cualquiera de varios formatos.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 6f0c382c56ea0c576134f2871cba7a71b44e6528
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262486"
---
# <a name="inventory-value-storage-report"></a>Informe de almacenamiento de valor de inventario

Este tema explica cómo ejecutar un informe de **almacenamiento de valor de inventario** y hacer que la salida esté disponible digitalmente, ya sea como una página interactiva en Microsoft Dynamics 365 Supply Chain Management o como documento exportado en cualquiera de varios formatos.

Cuando vea el informe en su navegador, las columnas y saldos agregados se ajustarán dinámicamente dependiendo del diseño que se haya configurado. Puede ordenar los resultados, filtrarlos, explorarlos en profundidad los datos y más.

Los resultados del informe se almacenan en la entidad de datos **Valor de inventario**. Por lo tanto, puede filtrar y exportar los resultados a un formato como valores separados por comas (CSV) o Microsoft Excel.

El informe **Almacenamiento de valor de inventario** es útil cuando la salida contiene muchas líneas. Por ejemplo, tiene 50 000 artículos y se han creado 300 tiendas como almacenes. En este caso, si solicita saldos finales de inventario por artículo, sitio y almacén, la salida contendrá muchas líneas.

> [!NOTE]
> El informe no incluirá los subtotales definidos en el diseño del informe. Tampoco incluirá saldos de contabilidad general, incluso cuando se definen en el diseño del informe. La conciliación con la contabilidad general debe hacerse utilizando saldos de prueba.

## <a name="turn-on-the-inventory-value-storage-feature"></a>Activar la función de almacenamiento de valor de inventario

Antes de que pueda generar un informe de **Almacenamiento de valor de inventario**, se debe activar la función en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de características**, la característica aparece de la siguiente forma:

- **Módulo**: Gestión de costes
- **Nombre de la característica**: Almacenamiento de valor de inventario

## <a name="generate-an-inventory-value-storage-report"></a>Genear un informe de almacenamiento de valor de inventario

Siga estos pasos para generar y almacenar un informe de **Almacenamiento de valor de inventario**.

1. Vaya a **Gestión de costes \> Consultas e informes \> Informe de almacenamiento de valor de inventario**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Valor de inventario** que aparece, establezca los siguientes valores para definir qué registros se incluyen en su informe:

    - En la ficha desplegable **Parámetros**, ingrese un nombre único para el informe y use los campos de la sección **Intervalo de fecha** para definir qué registros se incluyen en el informe. Para definir el intervalo de fechas, puede seleccionar un rango preestablecido (relativo a la fecha de generación del informe) en **Código de intervalo de fecha** o seleccionar fechas específicas en los campos **Fecha desde** y **Fecha hasta**.
    - En la ficha desplegable **Registros para incluir**, configure filtros y restricciones para definir qué datos se incluyen en el informe.
    - En la ficha desplegable **Ejecutar en segundo plano**, especifique cómo, cuándo y con qué frecuencia se genera el informe.

    > [!NOTE]
    > Este informe siempre se ejecuta como parte de un trabajo por lotes.

1. Seleccione **Aceptar** para aplicar su configuración y cerrar el cuadro de diálogo.

Después de que el trabajo por lotes se complete, el informe aparecerá en la página **Almacenamiento del informe de valor de inventario**. Es posible que deba actualizar la página para ver el informe.

## <a name="explore-an-inventory-value-storage-report"></a>Explorar un informe de almacenamiento de valor de inventario

Después de generar un informe, puede verlo y explorarlo en cualquier momento mediante estos pasos.

1. Vaya a **Gestión de costes \> Consultas e informes \> Informe de almacenamiento de valor de inventario**.
1. Seleccione un informe de la lista.
1. Seleccione **Ver detalles** para mostrar el contenido del informe.
1. Explore el informe siguiendo cualquiera de estos pasos:

    - Como sucede con la mayoría de las páginas estándar de Supply Chain Management, puede seleccionar casi cualquier encabezado de columna para ordenar o filtrar la cuadrícula por los valores en esa columna.
    - Utilice el campo **Filtro** para filtrar el informe por cualquier valor en cualquiera de las distintas columnas disponibles.
    - Use el menú de vista (sobre el campo **Filtro**) para guardar y cargar sus combinaciones favoritas de opciones de clasificación y filtro.

## <a name="export-an-inventory-value-storage-report"></a>Exportar un informe de almacenamiento de valor de inventario

Cada informe que genera se almacena en la entidad de datos **Valor de inventario**. Puede usar las funciones estándar de administración de datos de Supply Chain Management para exportar datos de esta entidad a cualquier formato de datos compatible, como CSV o Excel.

El siguiente ejemplo muestra cómo exportar un **Informe de valor de inventario**.

1. Vaya a **Administración del sistema \> Áreas de trabajo \> Administración de datos**.
1. En la sección **Importación y exportación**, seleccione el icono **Exportar**. 
1. En la página **Exportar** que aparece, configurará el trabajo de exportación. Primero especifique un nombre de grupo para el trabajo.
1. En la sección **Entidades seleccionadas**, seleccione **Agregar entidad**.
1. En el cuadro de diálogo que aparece, establezca los campos siguientes:

    - **Nombre de la entidad**: seleccione **Valor de inventario**.
    - **Formato de datos objetivo**: seleccione el formato para exportar datos.

1. Seleccione **Agregar** para añadir la fila nueva y luego seleccione **Cerrar** para cerrar el cuadro de diálogo.
1. Por lo general, exportará un informe a la vez. Para exportar un solo informe, configure un filtro para la fila que acaba de agregar al cuadro de diálogo **Consulta**. De esta forma, puede definir qué informe de la entidad **Valor de inventario** se incluye en la exportación. Siga estos pasos para establecer las siguientes opciones de filtro para exportar un solo informe:

    1. En la pestaña **Rango**, seleccione **Agregar** para agregar una fila.
    2. Establezca el campo **Tabla** en **Valor de inventario**.
    3. Establezca el campo **Tabla derivada** en **Valor de inventario**.
    4. Establezca el campo **Campo** en el campo por el que desea filtrar. Por lo general, usará el campo **Nombre de ejecución** y/o el campo **Tiempo de ejecución**.
    5. Establezca el campo **Criterios** en el valor que desea buscar en el campo seleccionado. (Si seleccionó el campo **Nombre de ejecución** en el paso anterior, este valor será el nombre del informe. Si seleccionó el campo **Tiempo de ejecución**, será el momento en que se generó el informe).
    6. Agregue más filas a la pestaña **Rango** según sea necesario, hasta que haya identificado de forma exclusiva el informe que está buscando.

1. Seleccione **Aceptar** para guardar la configuración y cerrar el cuadro de diálogo.
1. Seleccione **Guardar** para guardar su configuración de exportación.
1. En la pestaña **Opciones de exportación**, seleccione **Exportar ahora** para generar el archivo de exportación.
1. En la página **Resumen de ejecución** que aparece, puede ver el estado de su trabajo de exportación y una lista de las entidades que se exportaron. En la sección **Estado de procesamiento de la entidad**, seleccione la entidad **Valor de inventario** en la lista y luego seleccione **Descargar archivo** para descargar los datos que se exportaron desde esa entidad.

Para obtener más información sobre cómo usar la administración de datos para exportar datos, vea [Resumen de trabajos de importación y exportación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Informe para Comparar precios de almacenamiento de artículos
description: Aprenda a generar un informe para Comparar precios de almacenamiento de artículos y después explorar y/o exportar el resultado.
author: JennySong-SH
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: f88dd1c23153d325709e28b056f902b555f05376
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675386"
---
# <a name="compare-item-prices-storage-report"></a>Informe para Comparar precios de almacenamiento de artículos

[!include [banner](../includes/banner.md)]

Este tema explica cómo ejecutar un informe **Comprar precios de almacenamiento de artículos** y hacer que la salida esté disponible digitalmente, ya sea como una página interactiva en Dynamics 365 Supply Chain Management, o como documento exportado en cualquiera de varios formatos.

Cuando vea el informe en su navegador, las columnas y saldos agregados se ajustarán dinámicamente dependiendo de su diseño configurado. Puede ordenar los resultados, filtrarlos, explorarlos en profundidad los datos y más.

Los resultados del informe se almacenan en la entidad de datos **Comparar precios de artículos**, que le permite filtrar y exportar los resultados a un formato como CSV o Microsoft Excel.

El informe **Comparar precios de almacenamiento de artículos** es útil en los casos en que la salida contiene muchas líneas. Por ejemplo, la salida contendrá muchas líneas si tiene más de 40.000 artículos con un precio de artículo pendiente en la versión de gestión de costes.

## <a name="enable-compare-item-prices-storage"></a>Habilitar comprar precios de almacenamiento de artículos

Antes de poder usar esta función debe habilitarla en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y habilitarla si es necesario. Aquí, la función aparece como:

- **Módulo** - Gestión de costes
- **Nombre de la función** - Comparar el precio de almacenamiento del artículo

## <a name="generate-a-compare-item-prices-storage-report"></a>Generar un informe Comprar precios de almacenamiento de artículo

Siga estos pasos para generar y almacenar un informe **Comparar precios de almacenamiento de artículos**:

1. Vaya a **Gestión de costes > Consultas e informes > Informes de costes predeterminados> Comparación de precios de almacenamiento de artículos**.

1. Seleccione **Nuevo** para abrir el panel **Comparar precios de artículos**. Establezca las siguientes opciones para definir qué precios comparar en su informe:

    - En la ficha desplegable **Parámetros**, dele un **Nombre** único al informe y use los campos en las secciones **Precios pendientes a comparar** y **Precios utilizados para comparación** para definir qué precios y fechas comparar.
    - En la ficha desplegable **Registros para incluir**, configure filtros y restricciones para definir qué datos incluir en el informe.
    - En la ficha desplegable **Ejecutar en segundo plano**, configure cómo, cuándo y la frecuencia con la que desea generar el informe.
    > [!NOTE]
    > Este informe siempre se ejecuta como parte de un trabajo por lotes.

1. Seleccione **Aceptar** para aplicar su configuración y cerrar el panel.

1. Después de completar el trabajo por lotes, aparecerá en la página **Comparar precios de almacenamiento de artículos**. Puede tener que actualizar la página para ver el informe.

## <a name="explore-the-compare-item-prices-storage-report"></a>Explorar el informe Comprar precios de almacenamiento de artículos

Después de generar un informe, puede verlo y explorarlo en cualquier momento de la siguiente manera:

1. Vaya a **Gestión de costes > Consultas e informes > Informes de costes predeterminados> Comparación de precios de almacenamiento de artículos**.

1. Seleccione un informe de la lista.

1. Realice una de las acciones siguientes:

    - Seleccione **Vista general** para obtener una vista general de los resultados de su informe.
    - Seleccione **Ver detalles** para obtener una vista más detallada de su informe

1. Después de que la vista seleccionada se abra, puede hacer lo siguiente:

    - Seleccione casi cualquier encabezado de columna para ordenar o filtrar la tabla por valores en esa columna, al igual que con la mayoría de los formularios estándar en Supply Chain Management. Tenga en cuenta que no puede ordenar o filtrar la columna **% de cambio de precio neto** porque es un campo calculado.
    - Seleccione **Visualización de la dimensión** para abrir un panel donde puede elegir qué columna de dimensión incluir en el formulario. Establezca **Guardar configuración** a **Sí** si desea guardar esta configuración para que se conserve la próxima vez que abra el informe. Seleccione **Aceptar** para aplicar su configuración y cerrar.
    - Seleccione cualquier fila en el formulario y luego seleccione **Ver detalles** para ver más información sobre el elemento seleccionado. Desde aquí podrá explorar en profundidad los datos.
    - Seleccione cualquier fila en el formulario y seleccione **Ver tabla comparativa** para ver una representación gráfica interactiva de sus resultados en relación con su elemento seleccionado. Puede explorar estos resultados seleccionando varios elementos gráficos en el gráfico y la leyenda del gráfico.
    - Seleccione cualquier fila en el formulario y luego seleccione **Ver detalles del cálculo** para ver más información sobre los cálculos relacionados con el elemento seleccionado. Desde aquí podrá explorar en profundidad los datos.

## <a name="export-the-compare-item-prices-storage-report"></a>Exportar el informe Comprar precios de almacenamiento de artículos

Cada informe que genera se almacena en la entidad **Comparar precios de artículos**. Puede usar las funciones estándar de administración de datos de Supply Chain Management para exportar datos de esta entidad a cualquier formato de datos compatible, incluidos CSV o Microsoft Excel.

El siguiente es un ejemplo de cómo exportar un informe **Comparar precios de almacenamiento de artículos**:

1. Vaya a **Administración del sistema > Áreas de trabajo > Administración de datos**.

1. Selecciona el botón **Exportar** en la sección **Gestión de datos**.

1. Se abrirá la página **Exportar**, que usará para configurar su trabajo de exportación. Comience por darle a tu trabajo un **Nombre del grupo**.

1. En la sección **Entidades seleccionadas**, seleccione **Agregar entidad** para abrir un cuadro de diálogo donde puede configurar las siguientes opciones:

    - **Nombre de la entidad** - Seleccione **Comparar precios de artículos**.
    - **Formato de datos objetivo** - Elija el formato al que desea exportar.

1. Seleccione **Agregar** para añadir la fila nueva y luego seleccione **Cerrar** para cerrar el cuadro de diálogo.

1. Por lo general, exportará un informe a la vez. Para hacer esto, configure un **Filtro** para la fila que acaba de agregar al panel **Consulta**. Esto le permitirá definir qué informes de la entidad **Comparar precios de artículos** desea incluir en su exportación. Configure las siguientes opciones de filtro para exportar un solo informe:

    - En la pestaña **Rango**, seleccione **Agregar** para agregar una nueva fila.
    - Establezca **Tabla** en **Comparar precios de artículos**.
    - Establezca **Tabla derivada** en **Comparar precios de artículos**.
    - Establezca el campo **Campo** al campo por el que desea filtrar. Usualmente usará **Nombre de ejecución** o **Tiempo de ejecución**.
    - Establezca **Criterios** al valor del campo seleccionado que desea buscar (ya sea el nombre del informe o la hora en que se generó el informe).
    - Si es necesario, agregue más filas a la tabla **Rango** hasta que haya identificado de forma exclusiva el informe que está buscando.

1. Seleccione **Aceptar** para guardar su configuración y cerrar.

1. Seleccione **Guardar** para guardar su configuración de exportación.

1. Abra la pestaña **Opciones de exportación** y seleccione **Exportar ahora** para generar el archivo de exportación.

1. Se abrirá la página **Resumen de ejecución**, donde puede ver el estado de su trabajo de exportación y una lista de entidades que se exportaron. Seleccione la entidad **Comparar precios de artículos** enumerada en el área **Estado de procesamiento de la entidad** y luego seleccione **Descargar archivo** para descargar los datos exportados desde esa entidad.

Para obtener más información sobre cómo usar la administración de datos para exportar datos, vea [Resumen de trabajos de importación y exportación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
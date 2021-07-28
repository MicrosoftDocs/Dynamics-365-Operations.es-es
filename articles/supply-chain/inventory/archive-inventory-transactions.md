---
title: Archivar transacciones del inventario
description: Este tema describe cómo archivar datos de transacciones de inventario para ayudar a mejorar el rendimiento del sistema.
author: sherry-zheng
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 23da08f982639c9ba0ef847990979f73b96cac22
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345533"
---
# <a name="archive-inventory-transactions"></a>Archivar transacciones del inventario

[!include [banner](../../includes/banner.md)]

Con el tiempo, la tabla de transacciones de inventario (`InventTrans`) seguirá creciendo y consumiendo más espacio en la base de datos. Por lo tanto, las consultas que se realicen en la tabla se volverán gradualmente más lentas. Este tema describe cómo puede utilizar la función *Archivo de transacciones de inventario* función para archivar datos sobre transacciones de inventario para ayudar a mejorar el rendimiento del sistema.

> [!NOTE]
> Solo las transacciones de inventario actualizadas financieramente se pueden archivar en un período de libro mayor cerrado seleccionado. Para ser archivadas, las transacciones de inventario saliente actualizadas financieramente deben tener un estado de emisión de *Vendido*, y las transacciones de inventario de entrada deben tener un estado de recepción de *Comprado*.

Cuando archiva transacciones de inventario, todas las transacciones relacionadas se mueven a la tabla `InventTransArchive`. Las transacciones de emisión de inventario y las transacciones de recepción de inventario se archivan por separado, según la combinación del ID de artículo (`itemId`) e ID de dimensión de inventario (`inventDimId`) y se incluyen en las transacciones de emisión resumida y recibo resumido.

Si una combinación `itemId` e `inventDimId` contiene solo un recibo o transacción de emisión, la transacción no se archivará.

## <a name="turn-on-the-feature-in-your-system"></a>Activar la función en el sistema

Si su sistema aún no incluye las funciones descritas en este tema, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la característica *Archivo de transacciones de inventario*. Tenga en cuenta que esta función no se puede desactivar una vez que se ha activado.

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a>Cosas a considerar antes de archivar transacciones de inventario

Antes de archivar las transacciones de inventario, debe considerar los siguientes escenarios comerciales, ya que se verán afectados por la operación:

- Cuando audita transacciones de inventario de documentos relacionados, como líneas de órdenes de compra, se mostrarán como archivadas. Para revisar las transacciones archivadas, debe ir a **Gestión del inventario \> Tareas periódicas \> Limpieza \> Archivo de transacciones de inventario**.
- El cierre de inventario no se puede cancelar por períodos archivados. Antes de que pueda cancelar un cierre de inventario, debe revertir el archivo de transacciones de inventario para el período relevante.
- La conversión de costo estándar no se puede realizar para períodos archivados. Antes de que pueda realizar una conversión de coste estándar, debe revertir el archivo de transacciones de inventario para el período relevante.
- Los informes de inventario que se obtienen de las transacciones de inventario se verán afectados cuando archive las transacciones de inventario. Estos informes incluyen el informe de antigüedad del inventario y los informes de valor del inventario.
- Los pronósticos de inventario pueden verse afectados si se ejecutan durante el horizonte temporal de los períodos archivados.

## <a name="prerequisites"></a>Requisitos previos

Las transacciones de inventario se pueden archivar solo durante los períodos en los que se cumplen las siguientes condiciones:

- El período del libro mayor debe estar cerrado.
- El cierre de inventario debe realizarse en o después de la fecha del archivo hasta el período.
- El período debe ser al menos un año antes de la fecha de inicio del período del archivo.
- No debe haber ningún recálculo de inventario existente.

## <a name="archive-inventory-transactions"></a>Archivar transacciones del inventario

Para archivar transacciones de inventario, siga estos pasos.

1. Ir **Gestión del inventario** \> **Tareas periódicas** \> **Limpiar** \> **Archivo de transacciones de inventario**.

    La página **Archivo de transacciones de inventario** aparece y muestra una lista de registros de procesos archivados.

    ![Página Archivar transacciones de inventario.](media/archive-inventory-empty.png "Página Archivar transacciones de inventario")

1. En el panel de acciones, seleccione **Archivo de transacciones de inventario** para crear un archivo de transacciones de inventario.
1. En el cuadro de diálogo **Archivo de transacciones de inventario**, en la ficha desplegable **Parámetros**, establezca los siguientes campos:

    - **Desde la fecha en el período del libro mayor cerrado** - Seleccione la fecha de transacción más temprana para incluir en el archivo.
    - **Hasta la fecha en el período del libro mayor cerrado** - Seleccione la fecha de transacción más tardía para incluir en el archivo.

    ![Cuadro de diálogo Archivar transacciones de inventario.](media/archive-inventory-dates.png "Cuadro de diálogo Archivar transacciones de inventario")

    > [!NOTE]
    > Sólo períodos que cumplen con los [prerrequisitos](#prerequisites) estarán disponible para su selección.

1. Sobre la ficha desplegable **Ejecutar en segundo plano**, configure los detalles del procesamiento por lotes según sus necesidades. Siga los pasos habituales para trabajos por lotes en Microsoft Dynamics 365 Supply Chain Management.
1. Seleccione **Aceptar**.
1. Recibe un mensaje que le pide que confirme que desea continuar. Lea el mensaje con atención y luego seleccione **Sí** Si desea continuar.

    Recibe un mensaje que indica que su trabajo de archivo de transacciones de inventario se ha agregado a la cola de lotes. El trabajo ahora comenzará a archivar las transacciones de inventario del período seleccionado.

## <a name="view-archived-inventory-transactions"></a>Ver transacciones de inventario archivadas

La página **Archivo de transacciones de inventario** muestra su historial de archivo completo. Cada fila de la cuadrícula muestra información como la fecha en la que se creó el archivo, el usuario que lo creó y su estado.

![Historial de archivo en la página Archivo de transacciones de inventario.](media/archive-inventory-full.png "Historial de archivo en la página Archivo de transacciones de inventario")

En la lista desplegable en la parte superior de la página, seleccione uno de los siguientes valores para filtrar los archivos que se muestran en la cuadrícula:

- **Activo** - Mostrar solo archivos activos, no archivos revertidos.
- **Todos** - Mostrar todos los archivos, tanto activos como revertidos.

Para cada archivo de la cuadrícula, se proporciona la siguiente información:

- **Activo** - Una marca de verificación indica que el archivo está activo.
- **Partir de la fecha** - La fecha de la transacción más antigua que se puede incluir en el archivo.
- **Hasta la fecha** - La fecha de la transacción más reciente que se puede incluir en el archivo.
- **Programado por** - La cuenta de usuario que creó el archivo.
- **Ejecutado** - La fecha de creación del archivo.
- **Marcha atrás** - Una marca de verificación indica que el archivo se ha invertido.
- **Detener la actualización actual** - Una marca de verificación indica que el archivo está en curso, pero se ha detenido.
- **Expresar** - El estado de procesamiento del archivo. Los valores posibles son *Espera*, *En progreso* y *Finalizado*.

La barra de herramientas sobre la cuadrícula proporciona los siguientes botones que puede usar para trabajar con un archivo seleccionado:

- **Transacciones archivadas** - Ver los detalles completos del archivo seleccionado. La página **Transacciones archivadas** que aparece muestra todas las transacciones en el archivo.

    ![Página Transacciones archivadas.](media/archive-inventory-transactions.png "Página Transacciones archivadas")

    Para ver más información sobre una transacción específica en la página **Transacciones archivadas**, selecciónela en la cuadrícula y, a continuación, en el Panel de acciones, seleccione **Detalles de transacción archivados**. La página **Detalles de transacción archivados** que aparece muestra información como la contabilización del libro mayor, las referencias del libro mayor auxiliar relacionadas y las dimensiones financieras.

- **Pausar el archivo** - Pausar un archivo seleccionado que se está procesando actualmente. La pausa tiene efecto solo después de que se haya generado la tarea de archivo. Por lo tanto, puede haber una pequeña demora antes de que la pausa surta efecto. Si un archivo se ha detenido, aparece una marca de verificación en el campo **Detener la actualización actual**.
- **Reanudar el archivo** - Reanudar el procesamiento de un archivo seleccionado que se está pausado actualmente.
- **Marcha atrás** - Revertir el archivo seleccionado. Puede revertir un archivo solo si su campo **Estado** está configurado en *Finalizado*. Si un archivo se ha invertido, aparece una marca de verificación en el campo **Invertir**.

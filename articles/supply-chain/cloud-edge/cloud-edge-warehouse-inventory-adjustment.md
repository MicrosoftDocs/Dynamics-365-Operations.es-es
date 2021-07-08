---
title: Ajuste de inventario de almacén
description: Este tema proporciona información sobre el procesamiento y el diario de ajuste de inventario del almacén cuando utiliza unidades de escalado.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1bf147ce430d84980516d8d4824081ee2a9321a2
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271241"
---
# <a name="warehouse-inventory-adjustment"></a>Ajuste de inventario de almacén

[!include [banner](../includes/banner.md)]

La función de ajuste de inventario del almacén se utiliza cuando se ejecutan unidades de escalado de borde y en la nube para [cargas de trabajo de fabricación](cloud-edge-workload-manufacturing.md) y [cargas de trabajo de gestión de almacenes](cloud-edge-workload-warehousing.md).

Cuando un trabajador hace un ajuste de inventario usando la aplicación de almacén contra una carga de trabajo de administración de almacén de unidad de escalado, la actualización física disponible debe procesarla el trabajo por lotes **Diario de ajuste de inventario de almacén**, que puede ejecutar y programar yendo a **Gestión de almacenes > Tareas periódicas > Diario de ajuste de inventario de almacén**.

Los siguientes procesos de trabajo de la aplicación de almacén utilizan actualmente el **Diario de ajuste de inventario de almacén** en las cargas de trabajo de unidad de escalado:

- Entrada/salida de ajuste
- Recuento cíclico
- Carga de matrícula de entidad de almacén

Varias transacciones de inventario se crean como parte de cada proceso de ajuste de inventario porque las implementaciones de unidades de escala y centro de conectividad comparten los registros de inventario.

## <a name="inventory-adjustment-example"></a>Ejemplo de ajuste de inventario

En este ejemplo, un trabajador del almacén ha utilizado la aplicación del almacén para registrar la adición de inventario disponible.

Primero, la carga de trabajo de la unidad de escalado crea una transacción de ajuste de inventario de almacén para el ajuste físico positivo, que luego se sincroniza con el centro de conectividad y da como resultado un aumento del inventario disponible en el centro de conectividad.

| Tipo                                    | Unidad de escalado | Dirección | Concentrador |
|-----------------------------------------|------------|-----------|-----|
| Ajuste de inventario de almacén          | +1         | ->        | +1  |

A continuación, el concentrador procesa un registro del diario de recuento, que se recibe a través de [mensajes del procesador de mensajes](cloud-edge-message-processor-messages.md). Esto actualiza el inventario adicional disponible. Para evitar el doble inventario disponible, el centro crea una transacción de compensación como parte de este proceso y elimina el inventario disponible registrado anteriormente que está relacionado con el ajuste de inventario del almacén.

| Tipo                                    | Unidad de escalado | Dirección | Concentrador |
|-----------------------------------------|------------|-----------|-----|
| Recuento                                | +1         | <-        | +1  |
| Ajuste de inventario de almacén (compensación) | -1         | <-        | -1  |

Una vez que una unidad de escalado ha creado un **Diario de ajuste de inventario de almacén** en el centro de conectividad, puede revisar el **Diario de recuento** y el **Diario de compensación**, que los crea el centro de conectividad como parte del proceso de ajuste.

Puede revisar cada uno de estos asientos de diario y la transacción en Supply Chain Management, realizando los siguientes pasos:

1. Inicie sesión en la unidad de escalado.
1. Vaya a **Gestión de almacenes \> Tareas periódicas \> Diario de ajuste de inventario de almacén**.
1. En la página **Diario de ajuste de inventario de almacén**, busque y abra el diario que registró el cambio de inventario disponible. La sección **Líneas de diario** muestra cada ajuste registrado por este diario.
1. Inicie sesión en el centro de conectividad.
1. Vaya a **Gestión de almacenes \> Tareas periódicas \> Diario de ajuste de inventario de almacén**.
1. En la página **Diario de ajuste de inventario de almacén**, debería ver el mismo diario enumerado si el centro de conectividad y la unidad de escalado se han sincronizado.
1. Abra el diario. Si los [mensajes del procesador de mensajes](cloud-edge-message-processor-messages.md) se han procesado, verá enlaces al **Diario de recuento** y el **Diario de compensación** en el encabezado.
    - El **Diario de recuento** debe mostrar los mismos valores de dimensión que las líneas del diario.
    - El **Diario de compensación** debe mostrar la compensación, que elimina el doble ajuste de inventario.
    > [!NOTE]
    > Cuando se completa toda la sincronización y el procesamiento, el **Diario de recuento** y el **Diario de compensación** se vueven a sincronizar con la unidad de escalado. Estos también se pueden ver en la página **Diario de ajuste de inventario de almacén** correspondiente.

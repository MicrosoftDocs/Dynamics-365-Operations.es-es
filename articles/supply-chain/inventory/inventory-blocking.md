---
title: Bloqueo del inventario
description: "En este artículo se proporciona una visión general del bloqueo del inventario, que forma parte del proceso de inspección de calidad en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Puede usar el bloqueo del inventario para evitar que los artículos se procesen o se consuman."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: a59a382f90cb34c9479d64931790137f00040c6b
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="inventory-blocking"></a>Bloqueo del inventario

[!include[banner](../includes/banner.md)]


En este artículo se proporciona una visión general del bloqueo del inventario, que forma parte del proceso de inspección de calidad en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Puede usar el bloqueo del inventario para evitar que los artículos se procesen o se consuman.

Puede bloquear artículos de inventario de las siguientes formas:
-   Manualmente
-   Mediante la creación de un pedido de calidad
-   Mediante el uso de un proceso que genera un pedido de calidad
-   Mediante el bloqueo del estado de inventario

## <a name="blocking-items-manually"></a>Bloqueo manual de artículos
Puede bloquear una cantidad de un artículo creando una transacción en la página **Bloqueo del inventario**. Solo se pueden bloquear manualmente artículos disponibles en el inventario. Para las cantidades bloqueadas manualmente, debe decidir si las actividades de planificación incluyen recepciones previstas como una cantidad disponible. Las recepciones previstas son artículos bloqueados que se espera que estén disponibles en el inventario tras completar la inspección. Puede mantener la fecha prevista. De forma predeterminada, la opción **Recepciones previstas** está seleccionada para artículos bloqueados mediante un pedido de calidad. Puede cancelar un bloqueo manual en una cantidad eliminando la transacción en la página **Bloqueo del inventario**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Bloqueo de artículos creando un pedido de calidad
Puede especificar los artículos que se deben inspeccionar creando un pedido de calidad en la página **Pedidos de calidad**. Cuando crea el pedido de calidad, la cantidad de un artículo especificada se bloquea. El plan de muestreo asociado al pedido de calidad controla solo la cantidad de artículos que se debe inspeccionar, no la cantidad que se bloquea. La cantidad especificada en el pedido de calidad es la cantidad que se bloquea, independientemente de la cantidad que el plan de muestreo especifique como que se deben enviar a inspección.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Bloqueo de artículos mediante un proceso que genera un pedido de calidad
Si un proceso de calidad especifica que se debe inspeccionar un artículo, se bloquea automáticamente una cantidad del artículo. Por tanto, cuando un pedido de calidad se genera automáticamente, el plan de muestreo del artículo asociado al pedido de calidad controla tanto la cantidad de artículos que se bloquea como la cantidad que debe inspeccionarse. Si la opción **Bloqueo completo** en la página **Muestreo de artículos** está seleccionada, la cantidad completa de, por ejemplo, una línea de pedido de compra, se bloquea durante la inspección, independientemente de la cantidad de muestreo del artículo.
### <a name="example"></a>Ejemplo

En el siguiente ejemplo, se generará un pedido de calidad al registrar un albarán de pedido de compra. En la página **Asociaciones de calidad** especificó que el registro de un albarán de pedido de compra es el proceso que activa un pedido de calidad.

|Instalación                                                                     |Acción del usuario                 |Resultado             |
|--------------------------------------------------------------------------|----------------------------|-------------------|
| Una asociación de calidad especifica que debe generarse un pedido de calidad cuando se registre un albarán de pedido de compra. La configuración de muestreo del artículo del pedido de calidad especifica que se debe realizar una inspección del 10 por ciento de la cantidad en la línea del pedido de compra. Además, dado que la opción **Bloqueo completo** está seleccionada en la configuración de muestreo del artículo, la cantidad completa de la línea de pedido de compra debe bloquearse durante la inspección independientemente de la cantidad enviada para inspección. | Se imprimirá y registrará el albarán. | Se generará un pedido de calidad. Un diez por ciento de la cantidad del pedido de compra para el artículo se enviará para inspección. La cantidad completa de la línea del pedido de compra se bloqueará. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Bloqueo de artículos mediante bloqueo del estado de inventario
Puede especificar qué estados de inventario son estados de bloqueo mediante el parámetro **Bloqueo de inventario** en la página **Estados de inventario**.  No puede usar los estados de inventario como estados de bloqueo para los pedidos de producción, los pedidos de ventas, los pedidos de transferencia, las transacciones de salida ni las integraciones de proyectos. Para el trabajo de salida, use artículos que tengan un estado de inventario de disponible. Si tiene artículos con estado **Roto** y la planificación maestra se ejecuta en estos artículos, se considera que faltan los artículos y el inventario se reabastece automáticamente.



<a name="see-also"></a>Consulte también
--------

[Crear y mantener un bloqueo de inventario (Guía de tareas)](tasks/create-maintain-inventory-blocking.md)

[Procesos de gestión de calidad](quality-management-processes.md)

[Inspeccionar la calidad de las mercancías (Guía de tareas)](tasks/inspect-quality-goods.md)


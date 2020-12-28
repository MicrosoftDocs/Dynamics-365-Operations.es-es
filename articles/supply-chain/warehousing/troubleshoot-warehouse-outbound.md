---
title: Solucionar problemas de operaciones de almacén de salida
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de salida en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 56bd91d8a6fe895317021d806e180df3a2db302b
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645462"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a>Solucionar problemas de operaciones de almacén de salida

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de salida en Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a>Recibo el siguiente mensaje de error: "No se pudo liberar el pedido de venta".

### <a name="issue-description"></a>Descripción del problema

Este problema puede ocurrir por varias razones. Por ejemplo, el pedido está en espera de gestión de crédito y no se pueden crear envíos hasta que se ingrese una dirección postal válida para todas las líneas de ventas asociadas con un pedido de ventas. Alternativamente, existe una retención de pedido que debe abordarse antes de que el pedido pueda enviarse al almacén. Esta retención puede ser específica de un pedido o puede estar en la cuenta del cliente.

### <a name="issue-resolution"></a>Solución del problema

Agregue o actualice la dirección en la orden de venta y las líneas de orden y luego libere la orden en el almacén. Los pedidos se pueden enviar al almacén solo si tienen una dirección de entrega válida (según la configuración del formato de dirección en el módulo **Administración de la organización**).

Investigue la orden retenida y resuelva los problemas. Luego elimine la retención del pedido o del cliente y libere el pedido al almacén.

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a>Recibo el siguiente mensaje: "El envío de carga 1% ha sido confirmado". Sin embargo, no se publican líneas.

### <a name="issue-description"></a>Descripción del problema

Se confirmó un envío en una carga, pero no se realizaron más envíos.

### <a name="issue-resolution"></a>Solución del problema

La confirmación del envío no afecta la publicación. Solo actualiza el estado del envío y la carga. La publicación debe ocurrir en un proceso separado.

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a>Recibo el siguiente mensaje de error: "La entrega directa no se puede procesar para el 1% del almacén porque tiene habilitada la gestión del almacén. Especifique otro almacén que no esté habilitado para la gestión de almacenes ".

### <a name="issue-description"></a>Descripción del problema

Se agrega un artículo a una línea de ventas para entrega directa desde un almacén que está habilitado para la gestión de almacenes (WMS). Recibe este mensaje de error cuando se actualiza la línea de ventas. 

### <a name="issue-resolution"></a>Solución del problema

Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones. Actualmente, WMS no admite la entrega directa. Por lo tanto, para utilizar la entrega directa, debe seleccionar un artículo y un almacén que no sea WMS.

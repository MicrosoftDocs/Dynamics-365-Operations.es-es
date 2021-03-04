---
title: Solucionar problemas de planificación de carga y envíos
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con creación de cargas y envíos en Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 2933bcfd2cc526e39a4e1343cd472334a5b95607
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645341"
---
# <a name="troubleshoot-load-building-and-shipments"></a>Solucionar problemas de planificación de carga y envíos

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con creación de cargas y envíos en Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a>Recibo el siguiente mensaje de error: "No puede crear una línea de carga para esta línea de pedido porque contiene dimensiones de inventario que no son válidas ..."

### <a name="issue-description"></a>Descripción del problema

Recibe el siguiente mensaje de error cuando intenta enviar un pedido de devolución al almacén:

> No puede crear una línea de carga para esta línea de pedido porque contiene dimensiones de inventario que no son válidas. No puede hacer referencia a dimensiones de inventario que se encuentran debajo de la dimensión de ubicación en la jerarquía de reservas. Elimine las dimensiones no válidas de la línea de pedido.

### <a name="issue-resolution"></a>Solución del problema

Desafortunadamente, el producto no admite el procesamiento de carga para un proceso de devolución de ventas. Por lo tanto, no puede enviar el pedido de devolución al almacén.

En las transacciones de pedido de venta, no puede hacer referencia a dimensiones de inventario que se encuentran debajo de la dimensión **Ubicación** en la jerarquía de reservas. La resolución es quitar las dimensiones no válidas de la línea de pedido.

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a>Recibo el siguiente mensaje de error: "Una de las líneas ya está cargada. No se puede liberar al almacén".

### <a name="issue-description"></a>Descripción del problema

Si crea cargas manualmente, o si configura el proceso de modo que las cargas ya estén creadas antes de que se produzca la entrada de la línea de la orden de venta, se supone que la liberación posterior se realizará manualmente y que se utilizarán la ruta y la clasificación de la carga. .

En otro escenario posible, está intentando hacer una liberación automática al almacén, pero el proceso de oleada no pudo crear trabajo. Por lo tanto, se sigue creando un envío o carga abiertos. Este envío o carga abiertos bloquea los intentos posteriores de liberar automáticamente el pedido hasta que elimine el envío o la carga abiertos, o reprocese manualmente la ola.

### <a name="issue-resolution"></a>Solución del problema

Puede liberar desde la página de órdenes de venta, o la liberación automática puede realizarse desde la página de liberación de órdenes de venta, solo si no existe carga antes de la liberación al almacén. La carga se creará automáticamente después de que se procese la ola.

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a>Recibo el siguiente mensaje de error: "No se puede procesar la corrección del albarán de entrega. La nota de entrega solo contiene artículos que están sujetos a procesos de gestión de almacén, ya que estos no son compatibles con la corrección de la nota de entrega ".

### <a name="issue-description"></a>Descripción del problema

Después de publicar un albarán de entrega, no puede cancelarlo porque el botón **Cancelar** no está disponible. Tampoco puede corregir el albarán de entrega. Si lo intenta, recibirá este mensaje de error.

### <a name="issue-resolution"></a>Solución del problema

Para corregir las notas de empaque publicadas para los artículos que están habilitados para gestión avanzada de almacenes (WMS), debe hacer la publicación desde la carga, no desde el pedido.

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a>¿Cómo puedo crear trabajo a partir de cargas salientes en lugar de oleadas?

### <a name="issue-description"></a>Descripción del problema

A continuación se muestra una forma de reproducir este problema.

1. Crear una carga de salida mediante una orden de ventas o una orden de transferencia
2. Liberar la carga al almacén.
3. Observe que aún no se ha generado ningún trabajo de picking.

### <a name="issue-resolution"></a>Solución del problema

Si se debe generar trabajo inmediatamente cuando se libera la carga, debe configurar la plantilla de onda en consecuencia. En la plantilla de oleada, configure las siguientes opciones para *Sí*:

- Automatizar la creación de oleadas
- Procesar oleada para su liberación al almacén
- Liberación automática de oleada

## <a name="i-cant-re-release-a-partially-shipped-load"></a>No puedo volver a liberar una carga enviada parcialmente.

### <a name="issue-description"></a>Descripción del problema

No puede liberar una carga enviada parcialmente al almacén. Cuando realiza la liberación al almacén, aparece el mensaje "Operación completada", pero no ocurre nada y no se crea ningún trabajo para la cantidad restante. Este problema se produce cuando utiliza la función de carga de transporte y hay una reserva incompleta.

### <a name="issue-resolution"></a>Solución del problema

[Problema de KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Las cargas enviadas parcialmente se pueden volver a agitar y volver a procesar") se corrige en la [versión 10.0.15](../get-started/whats-new-scm-10-0-15.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
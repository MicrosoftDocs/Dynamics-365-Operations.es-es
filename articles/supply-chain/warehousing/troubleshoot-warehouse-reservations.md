---
title: Solución de problemas de reservas en gestión de almacenes
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reservas de almacenes en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5f3a9ab907c3cb0e6b99c414a78b6878bd5353274472c54e1f5eaf1d167f046a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773114"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a>Solución de problemas de reservas en gestión de almacenes

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reservas de almacenes en Microsoft Dynamics 365 Supply Chain Management.

Para temas relacionados con los registros de lotes y números de serie, consulte [Solucionar problemas de jerarquías de reserva en serie y por lotes del almacén](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a>Aparece el mensaje de error: "No se pueden quitar las reservas porque se ha creado un trabajo que depende de ellas".

### <a name="issue-description"></a>Descripción del problema

No se puede anular la reserva de inventario en una línea de ventas, porque hay trabajo abierto contra la línea.

### <a name="issue-resolution"></a>Solución del problema

Investigar si existe trabajo de grupo de empaque abierto para llevar el artículo de una estación de empaque a otra ubicación (como *Baydoor*). Revise los registros en las páginas **Registro del historial de creación de trabajos** y **Detalles del trabajo** para determinar qué está reservando físicamente el inventario, y luego completar o eliminar el trabajo para liberar la reserva.

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a>Recibo el siguiente mensaje de error: "Cantidad de inventario -%1 no se pudo actualizar debido a transacciones de inventario insuficientes para el artículo %2...."

### <a name="issue-description"></a>Descripción del problema

Este problema puede ocurrir si el sistema no puede actualizar una cantidad de inventario porque no hay suficientes transacciones de inventario que tengan las dimensiones especificadas. A continuación se muestra el texto completo del mensaje de error:

> Cantidad de inventario -%1 no se pudo actualizar debido a transacciones de inventario insuficientes para el artículo %2 con dimensiones Tamaño=%3, Color=%4, Adiciones=%5, Sitio=%6, Almacén=%7, Ubicación=%8, Estado de inventario=Disponible, Matrícula=%9, Número de lote=%10 para ID de referencia %11 en ID de lote %12.

### <a name="issue-resolution"></a>Solución del problema

Asegúrese de que ninguna transacción de inventario esté reservando físicamente la cantidad. Por ejemplo, estas transacciones pueden abrir pedidos de calidad, registros de bloqueo de inventario o pedidos de salida.

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a>Recibo el siguiente mensaje de error: "Físico disponible ... no se puede reservar porque solo 0.00 están disponibles en el inventario".

### <a name="issue-description"></a>Descripción del problema

Este problema puede ocurrir si el sistema no puede actualizar una cantidad de inventario porque no hay suficientes transacciones de inventario que tengan las dimensiones especificadas. A continuación se muestra el texto completo del mensaje de error:

> Sitio físico disponible=%1, Almacén=%2, Estado de inventario=Disponible, Número de lote=%3, Propietario=%4: %5 no se puede reservar porque solo 0.00 están disponibles en el inventario.

### <a name="issue-resolution"></a>Solución del problema

Este problema probablemente se deba al trabajo abierto. Completar el trabajo o recibir sin creación de trabajo. Asegúrese de que ninguna transacción de inventario esté reservando físicamente la cantidad. Por ejemplo, estas transacciones pueden ser pedidos de calidad, registros de bloqueo de inventario o pedidos de salida abiertos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

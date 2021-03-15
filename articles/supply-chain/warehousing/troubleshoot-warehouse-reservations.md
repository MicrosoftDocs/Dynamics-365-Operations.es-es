---
title: Solución de problemas de reservas en gestión de almacenes
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reservas de almacenes en Microsoft Dynamics 365 Supply Chain Management.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a1ea23059d56ebf387a95a1378e2a3cd47556d5f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993890"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a>Solución de problemas de reservas en gestión de almacenes

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reservas de almacenes en Microsoft Dynamics 365 Supply Chain Management.

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

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>Recibo el siguiente mensaje de error: "Para ser asignado a la ola, las líneas de carga deben especificar las dimensiones por encima de la ubicación. Para asignar estas dimensiones, reserve y vuelva a crear la línea de carga ".

### <a name="issue-description"></a>Descripción del problema

Cuando utiliza un artículo que tiene una jerarquía de reserva "lote por encima" (con la dimensión **Número de lote** colocada *sobre* la dimensión **Ubicación**), el comando **Liberar al almacén** en la página **Banco de trabajo de planificación de carga** para una cantidad parcial no funciona. Recibe este mensaje de error y no se crea ningún trabajo para la cantidad parcial.

Sin embargo, si utiliza un artículo que tiene una jerarquía de reserva "lote por debajo" (con la dimensión **Número de lote** colocada *bajo* la dimensión **Ubicación**), puede liberar una carga desde la página **Banco de trabajo de planificación de carga** para una cantidad parcial.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento se debe al diseño. Si pone una dimensión por encima de la dimensión **Ubicación** en la jerarquía de reservas, debe especificarse antes del lanzamiento al almacén. Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones durante las versiones al almacén desde el entorno de trabajo de planificación de carga. Las cantidades parciales no se pueden liberar si no se especifican una o más dimensiones sobre **Ubicación**.

Para obtener más información, consulte [Directiva de reserva de dimensión de nivel de almacén flexible](flexible-warehouse-level-dimension-reservation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
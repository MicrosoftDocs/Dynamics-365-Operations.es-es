---
title: Solucionar problemas de jerarquías de reserva en serie y por lotes del almacén
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con jerarquías de reservas de que usan lotes o dimensiones en serie.
author: perlynne
ms.date: 3/12/2021
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
ms.search.validFrom: 3/12/2021
ms.openlocfilehash: a1abb6f8657484d43d434076e5ee38d1c63fe2ff
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838187"
---
# <a name="troubleshoot-warehouse-batch-and-serial-reservation-hierarchies"></a>Solucionar problemas de jerarquías de reserva en serie y por lotes del almacén

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con jerarquías de reservas de que usan lotes o dimensiones en serie.

Para obtener más información, consulte [Directiva de reserva de dimensión de nivel de almacén flexible](flexible-warehouse-level-dimension-reservation.md).

La jerarquía de reserva de un artículo dicta el requisito de dimensiones de almacenamiento que deben cumplirse para asignar una ubicación a una orden de demanda. Estas dimensiones se pueden describir como *dimensiones por encima de la ubicación*, para todas las dimensiones que deben cumplirse antes de que se asigne una ubicación, y *dimensiones debajo de la ubicación*, para dimensiones que se pueden asignar después de que se haya asignado una ubicación a la orden de demanda. Estas jerarquías de reserva también se conocen como jerarquías de reserva *batch-above* y *batch-below* o *serial-above* y *serial-below*.

El inventario se puede asignar correctamente solo si no hay espacios en las dimensiones anteriores a la ubicación. Por ejemplo, en una jerarquía de reservas *batch-above*, espera las dimensiones de **Sitio,** **Almacén,** y **Número de lote** que se especificarán en la orden de demanda. Si falta alguna de estas dimensiones, el proceso de asignación fallará. Por el contrario, en una jerarquía de reserva *batch-below* o *serial-below*, se puede especificar un lote o un número de serie en la orden de demanda, pero el proceso de asignación no lo requiere.

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>Recibo el siguiente mensaje de error: "Para ser asignado a la ola, las líneas de carga deben especificar las dimensiones por encima de la ubicación. Para asignar estas dimensiones, reserve y vuelva a crear la línea de carga ".

### <a name="issue-description"></a>Descripción del problema

Cuando utiliza un artículo que tiene una jerarquía de reserva *batch-above* el comando **Liberar al almacén** en la página **Banco de trabajo de planificación de carga** no funcionará si intenta liberar una carga para una cantidad parcial. Recibe este mensaje de error y no se crea ningún trabajo para la cantidad parcial.

Sin embargo, si utiliza un artículo que tiene una jerarquía de reserva *batch-below*, puede liberar una carga para una cantidad parcial desde la página **Banco de trabajo de planificación de carga**.

### <a name="issue-cause"></a>Causa del problema

Cuando una dimensión está por encima de la dimensión **Ubicación** en la jerarquía de reservas, debe especificarse antes del lanzamiento al almacén. Las cantidades parciales no se pueden liberar si no se especifican una o más dimensiones sobre **Ubicación**.

## <a name="the-auto-reservation-prompt-for-a-batch-number-is-triggered-even-though-there-is-available-inventory"></a>La solicitud de reserva automática para un número de lote se activa aunque haya inventario disponible.

### <a name="issue-description"></a>Descripción del problema

Cuando usa un artículo que tiene una jerarquía de reservas *batch-above* en un almacén que no ha habilitado los procesos de almacén y la reserva automática está habilitada, se muestra la solicitud de reserva automática para un número de lote incluso si solo hay un lote disponible para el picking.

Sin embargo, cuando usa el mismo artículo en un almacén donde los procesos de almacén están habilitados, no se muestra el mensaje de reserva automática.

### <a name="issue-cause"></a>Causa del problema

Si una jerarquía de reserva se define como *batch-above* o *serial-above*, la dimensión referenciada (**Número de lote** o **Número de serie**) debe especificarse siempre bajo pedido. Es posible que los procesos de almacén puedan completar la información si se dispone de un solo lote o número de serie. Sin embargo, debido a que el almacén no está habilitado para los procesos de almacén, el usuario siempre debe especificar todas las dimensiones sobre **Ubicación**.

## <a name="slotting-templates-that-have-the-consider-on-hand-slot-criterion-dont-consider-current-on-hand-inventory-for-batch-enabled-items"></a>Las plantillas de posicionamiento que tienen el criterio Considerar espacio disponible no consideran el inventario disponible actual para los artículos habilitados por lotes.

Para más información, consulte [Slotting de almacén](warehouse-slotting.md).

### <a name="issue-description"></a>Descripción del problema

Las plantillas de posicionamiento que tienen el criterio *Considerar espacio disponible* no consideran el inventario disponible actual para los artículos *batch-above*. Solo lo tienen en cuenta si el número de lote se especifica en la línea de orden de venta.

Sin embargo, cuando usa artículos *batch-below*, el inventario disponible actual se considera como esperado.

### <a name="issue-cause"></a>Causa del problema

El encabezado de la plantilla de planificación se puede definir para la estrategia de demanda *Ordenada*, *Reservada*, o *Publicada*. Para la estrategia de demanda *Ordenada*, se aplican los mismos requisitos de jerarquía de reservas que se aplican a los procesos de reserva o liberación a almacén. Por lo tanto, para los artículos que tienen *batch-above* y *serial-below* como jerarquías de reserva, el lote o número de serie debe especificarse en la orden de demanda (venta o transferencia). Alternativamente, la estrategia de demanda *Reservada* se puede utilizar para seleccionar el lote o el número de serie antes de que se genere la demanda de asignación del almacén.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

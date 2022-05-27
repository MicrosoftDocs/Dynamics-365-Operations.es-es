---
title: Crear pedidos de servicio automáticamente
description: Puede crear pedidos de servicio a partir de un acuerdo de servicio para el período válido del acuerdo de servicio.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41f48e2156ea5f57e600cc5dec09a78a91992d60
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675806"
---
# <a name="automatically-create-service-orders"></a>Crear pedidos de servicio automáticamente 

[!include [banner](../includes/banner.md)]


Puede crear pedidos de servicio a partir de un acuerdo de servicio para el período válido del acuerdo de servicio.

Los pedidos de servicio que se crean a partir de un acuerdo de servicio están vinculados al acuerdo de servicio.

Los pedidos de servicio se crean automáticamente con los siguientes parámetros:

  - La configuración del intervalo del acuerdo de servicio que se especifica en las líneas del acuerdo de servicio. El intervalo del acuerdo de servicio indica la frecuencia con la que se crean las líneas del pedido de servicio. Para obtener más información, consulte [Intervalos de servicio](service-intervals.md).

  - El período que se especifica cuando se define el período de servicio en los campos **Fecha inicial** y **Fecha final** del formulario **Crear pedidos de servicio**. Para obtener más información, vea [Crear pedidos de servicio automáticamente](create-service-orders-automatically.md).

  - La opción **Combinar pedidos de servicio** en la cabecera del acuerdo de servicio. Esta opción define si las líneas del pedido de servicio generadas a partir de un acuerdo de servicio combinan pedidos de servicio en función del empleado, tarea de servicio, objeto de servicio o acuerdo de servicio. Para obtener más información, consulte [Combinar pedidos de servicio](combine-service-orders.md).

  - La opción **Ventana de tiempo** de la línea del acuerdo de servicio. La ventana de tiempo define la distancia hasta la que puede moverse la línea de pedido de servicio en relación con la fecha calculada. Para obtener más información, consulte [Ventanas de plazo](time-windows.md).


> [!NOTE]
> <P>Si el día especificado para el pedido de servicio no está abierto en el calendario seleccionado en el formulario <STRONG>Parámetros de gestión de servicio</STRONG>, recibirá un mensaje advirtiéndole que existe un conflicto de calendario. Puede ignorar el mensaje; el pedido de servicio se creará, aunque el día esté cerrado en el calendario.</P>

## <a name="example-1"></a>Ejemplo 1

El acuerdo de servicio cubre el período del 1 de enero del 2012 hasta el 31 de diciembre del 2012. Si el período de servicio especificado en el formulario **Crear pedidos de servicio** cubre el período del 1 de noviembre del 2012 al 1 de febrero del 2013, se crearán pedidos de servicio para el período del 1 de noviembre del 2012 al 31 de diciembre del 2012.

## <a name="example-2"></a>Ejemplo 2

El acuerdo de servicio cubre el período del 1 de enero del 2012 hasta el 31 de diciembre del 2012. Hay dos líneas del acuerdo de servicio vinculadas al acuerdo de servicio. La primera línea del acuerdo de servicio incluye la fecha de inicio del 2 de enero del 2012 y la fecha final del 1 de marzo del 2012. La segunda línea del acuerdo de servicio incluye la fecha de inicio del 1 de abril del 2012 y la fecha final del 31 de diciembre del 2012. En el formulario **Crear pedidos de servicio**, especifica un período que cubre del 1 de octubre del 2012 al 31 de diciembre del 2012. Por lo tanto, sólo se crearán pedidos de servicio para la segunda línea del acuerdo de servicio, ya que la fecha inicial y la fecha final de la primera línea del acuerdo de servicio es anterior al período especificado para el pedido de servicio.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
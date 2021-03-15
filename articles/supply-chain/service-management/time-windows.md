---
title: Ventanas de plazo
description: Puede usar ventanas de plazo para optimizar la programación de líneas de pedido de servicio.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f64718e6a96cacc005644cbf4286e743111c02f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996511"
---
# <a name="time-windows"></a>Ventanas de plazo  

[!include [banner](../includes/banner.md)]

Puede usar ventanas de plazo para optimizar la programación de líneas de pedido de servicio. Puede configurar el sistema de modo que cree automáticamente pedidos de servicio. De acuerdo con los criterios especificados por una ventana de plazo, puede conectar tantas líneas de pedido de servicio como sean posibles con la menor cantidad de pedidos de servicio como sea posible.

Las ventanas de plazo definen el tiempo que se puede alejar una línea de pedido de servcio de su fecha calculada. La fecha calculada es la fecha en la que debía realizarse la línea de pedido de servicio de acuerdo con la programación. La fecha se basa en la configuración del intervalo y del período de servicio que definió en la página **Crear pedidos de servicio** . Para definir una ventana de plazo mediante los valores de la tabla siguiente.

| Método | Descripción                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Semana   | La fecha a la que se puede trasladar la línea de pedido de servicio puede ser cualquier día de la misma semana que la fecha calculada inicial.                                                                                                                                                                                    |
| Mes  | La fecha a la que se puede trasladar la línea de pedido de servicio puede ser cualquier día abierto del mismo mes que la fecha calculada inicial. Por ejemplo, la fecha calculada para una línea de pedido de servicio es el 15 de febrero de 2017. La línea de pedido de servicio se puede programar para cualquier día de la semana entre el 1 de febrero y el 28 de febrero de 2017. |
| Manual | Puede definir el número máximo de días anteriores o posteriores a la fecha inicial calculada que se puede trasladar la línea de pedido de servicio.                                                                                                                                                                           |

Si no se especifica ninguna ventana de plazo para una línea de acuerdo de servicio, la línea de pedido de servicio derivada del acuerdo de servicio se debe ejecutar en la fecha exacta para la que se programó originalmente.

## <a name="related-topics"></a>Temas relacionados

[Crear ventanas de plazo](create-time-windows.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
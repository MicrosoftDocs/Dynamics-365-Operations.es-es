---
title: Ubicación de salida de producción
description: Este artículo describe la jerarquía que se usa para identificar la ubicación de salida de producción.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 130db343c4d09f2b8d31bf8acad3dcceec2be32e
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067953"
---
# <a name="production-output-location"></a>Ubicación de salida de producción

[!include [banner](../includes/banner.md)]

Este artículo describe la jerarquía que se usa para identificar la ubicación de salida de producción.

La ubicación de salida de producción es la ubicación en la que un producto terminado se almacena por primera vez después de que produzca. Normalmente, esta ubicación está cerca del proceso de producción que produce el producto terminado. La ubicación de salida de producción se usa como almacenamiento intermedio para el material antes de que se traslade al área de envío, una ubicación de almacenamiento, una ubicación de entrada de producción para un proceso de producción descendente, y así sucesivamente. 

Una ubicación de salida de producción predeterminada se establece cuando el producto terminado se notifica en un pedido de producción o un pedido de lote. La siguiente jerarquía se usa para identificar esta ubicación de salida:

1. Use la ubicación de salida que se define en el encabezado del pedido de producción o pedido de lote.
2. Si no encuentra ninguna ubicación ahí, use la ubicación de salida definida en el recurso que utiliza la última operación definida en la ruta de producción.
3. Si no encuentra ninguna ubicación ahí, use la ubicación de salida definida en el grupo de recursos que utiliza el recurso para la última operación definida en la ruta de producción.
4. Si no encuentra ninguna ubicación ahí, use la ubicación de salida definida en el almacén definido para el pedido de producción.

Una ubicación de salida de producción predeterminada se establece únicamente para productos que se configuran mediante procesos de gestión de almacenes (WMS). Cuando este tipo de artículo se notifica como finalizado, se crea el trabajo de almacén del tipo **Ubicación de bienes terminados** o **Ubicación de coproducto y producto derivado**. Este tipo de trabajo usa la ubicación de salida de producción como la ubicación de selección. La localización de ubicació viene determinada por las directivas de ubicación.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
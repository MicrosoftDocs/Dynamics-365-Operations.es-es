---
title: Los cargos reembolsables están mal calculados según la cantidad devuelta
description: Este artículo proporciona una guía para la solución de problemas que puede ayudar cuando los cajeros ven cargos reembolsables incorrectos en el punto de venta (PDV) por la cantidad de artículos devueltos.
author: gvrmohanreddy
ms.date: 03/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 7a84207f587a826b9acdfd818c64220c5327bde1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890252"
---
# <a name="refundable-charges-are-miscalculated-based-on-the-quantity-returned"></a>Los cargos reembolsables están mal calculados según la cantidad devuelta

[!include [banner](../../includes/banner.md)]

Este artículo proporciona una guía para la solución de problemas que puede ayudar cuando los cajeros ven cargos reembolsables incorrectos en el punto de venta (PDV) por la cantidad de artículos devueltos.

## <a name="description"></a>Description

Un cliente devuelve una cantidad parcial de los artículos que se compraron para un pedido de ventas que tiene cargos reembolsables en una línea. Sin embargo, en lugar de mostrar un reembolso parcial, el PDV muestra todos los cargos como reembolsables.

Por ejemplo, un cliente compra una cantidad de cinco artículos a 5 $ por artículo, con un cargo total de 25 $. El cliente luego devuelve tres de los cinco artículos. Sin embargo, al cajero se le muestra un cargo reembolsable 25 $ en el PDV, en lugar de un cargo de 15 $, como cabría esperar para los tres artículos devueltos.

## <a name="resolution"></a>Resolución

### <a name="turn-on-the-enable-refunding-charges-based-on-the-refunded-quantity-feature"></a>Activar la habilitación de cargos de devolución según la característica de cantidad devuelta

A partir dela versión 10.0.26 de Microsoft Dynamics 365 Commerce, la característica **Habilitar cargos de devolución según la cantidad devuelta** permite que los cargos reembolsables a nivel de línea se calculen en función de la cantidad de artículos devueltos.

Para habilitar la característica **Habilitar cargos de devolución según la cantidad devuelta** en la sede central de Commerce, siga estos pasos.

1. Abre el espacio de trabajo **Administración de características** (**Administrador del sistema \> Espacios de trabajo \> Administración de características**).
1. En la lista de características disponibles, busque y seleccione la característica **Habilitar cargos de devolución según la cantidad devuelta**.
1. En el panel derecho, seleccione **Habilitar ahora**.

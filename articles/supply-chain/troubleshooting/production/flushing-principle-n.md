---
title: Los ajustes de principos de vaciado en líneas L. MAT. no se respetan
description: Los ajustes de principos de vaciado en líneas de lista de materiales (L. MAT.) no se respetan.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ee40eff53efd920ebe43a7b2dd28129f01e6ebb5e75bd480a91f758529f77fc5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716965"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a>Los ajustes de principos de vaciado en líneas L. MAT. no se respetan

Número de KB: 4612725

## <a name="symptoms"></a>Síntomas

Este problema ocurre cuando el campo **Consumo automático de L. MAT** en la pestaña **Actualización automática** de la página **Parámetros de control de producción** está configurado para *Principio de vaciado*. Esta configuración indica que todas las líneas de la lista de materiales (L. MAT.) deben consumirse automáticamente cuando se recibe un pedido de compra. Si el campo **Principio de vaciado** en las líneas de L. MAT. se establece explícitamente en *Manual*, es de esperar que las líneas de L. MAT. no se consuman automáticamente. Sin embargo, cuando se produce este problema, las líneas de la L. MAT. donde el campo **Principio de vaciado** está configurado en *Manual* se consumen automáticamente de todos modos.

## <a name="resolution"></a>Resolución

Si tiene este problema, es posible que sus parámetros de control de producción estén configurados para invalidad el ajuste de **Principio de vaciado** en las líneas de L. MAT. En la página **Parámetros de control de producción**, en la pestaña **Actualización automática**, compruebe el valor del campo **Consumo automático de L. MAT**. Si está configurado para *Siempre*, el sistema ignorará el ajuste de **Principio de vaciado** en todas las líneas de la L. MAT. y siempre vaciará las líneas. Para que el sistema respete el ajuste de **Principio de vaciado** en las líneas de la L. MAT., cambie el valor del campo **Consumo automático de L. MAT** a *Principio de vaciado*.

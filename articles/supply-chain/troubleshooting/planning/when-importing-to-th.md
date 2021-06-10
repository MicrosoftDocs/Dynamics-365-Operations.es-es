---
title: Se le solicitará que guarde la configuración de cobertura del artículo aunque no haya realizado cambios
description: Se le solicitará que guarde la configuración de cobertura del artículo aunque no haya realizado cambios.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049488"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a>Se le solicitará que guarde la configuración de cobertura del artículo aunque no haya realizado cambios

Número de KB: 4615588

## <a name="symptoms"></a>Síntomas

En algunos escenarios, es posible que reciba el siguiente mensaje cuando abra la página **Cobertura de artículos** después de importar elementos a través de la entidad *Cobertura de artículo V2*:

> ¿Desea guardar los cambios antes de cerrar?

Recibe este mensaje aunque no haya realizado ningún cambio.

## <a name="resolution"></a>Resolución

La página **Cobertura de artículos** incluye una lógica predeterminada compleja que puede hacer que el mensaje se muestre después de que se hayan realizado cambios directos en la base de datos, como a través de la importación de entidades. Por ejemplo, el campo de entidad `AREGENERALSETTINGSOVERRIDDEN` está configurado en *No*, pero importa un archivo que proporciona valores nuevos o modificados para campos como `PRODUCTCOVERAGEGROUPID` y / o `VENDORACCOUNTNUMBER`. En este caso, debido a que el campo `AREGENERALSETTINGSOVERRIDDEN` está configurado en *No*, los valores se borran automáticamente de los campos cuando abre la página **Cobertura de artículos** por primera vez después de la importación. Si guarda los cambios como lo indica el cuadro de mensaje, se almacenan en la base de datos. De lo contrario, recibirá el mismo mensaje la próxima vez que abra la página.

Para evitar este comportamiento, pero también incluir valores para campos como `PRODUCTCOVERAGEGROUPID` a través de la importación de la entidad, establezca `AREGENERALSETTINGSOVERRIDDEN` a *Sí* cuando importe.

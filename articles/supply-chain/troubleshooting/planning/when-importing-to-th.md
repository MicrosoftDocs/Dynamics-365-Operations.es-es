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
ms.openlocfilehash: 29ee23164430f219ff3d0c94216a8be43f480ce309f6cdac3dac6ed5b6d030af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730091"
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

---
title: Plantillas de servicio
description: Puede definir un acuerdo de servicio como plantilla y, a continuación, copiar las líneas de la plantilla en otro acuerdo o pedido de servicio.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7c99e56751230a7b8881dc55c1d460674cc6f0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850507"
---
# <a name="service-templates"></a>Plantillas de servicio

[!include [banner](../includes/banner.md)]

Puede definir un acuerdo de servicio como plantilla y, a continuación, copiar las líneas de la plantilla en otro acuerdo o pedido de servicio.

## <a name="example"></a>ejemplo

Un cliente al que presta servicio tiene ascensores de servicio idénticos en cinco ubicaciones distintas.

Desea establecer cinco acuerdos de servicio para el cliente, uno para cada sitio.
Para limitar el trabajo repetitivo de configuración y asegurarse de que la información de configuración de los acuerdos de servicio sea idéntica, crea un acuerdo de servicio y lo especifica como plantilla para el trabajo de servicio de los ascensores.

A continuación, podrá copiar las líneas de la plantilla en los cinco acuerdos de servicio, de modo que cada uno de ellos se rellene con las líneas de la plantilla.

## <a name="create-a-template"></a>Crear una plantilla

Al crear una plantilla de servicio, crea un acuerdo de servicio y las líneas que éste requiere, y vincula el acuerdo de servicio a un grupo de plantillas de servicio.

> [!NOTE]
> Un acuerdo de servicio sólo se puede definir como plantilla si no tiene vinculado ningún pedido de servicio. Asimismo, no se pueden generar pedidos de servicio a partir de un acuerdo de servicio definido como plantilla.

## <a name="copy-template-lines"></a>Copiar líneas de plantilla

Es posible copiar las líneas de plantilla desde una plantilla de servicio a otro acuerdo de servicio o a un pedido de servicio.

Al copiar líneas de plantilla a los pedidos o acuerdos de servicio, los grupos de plantilla se muestran en una vista de árbol con cada grupo expandido. Esta visualización permite ver todas las plantillas y las líneas correspondientes.

Es más fácil determinar las líneas de plantilla de servicio que desea copiar si agrupa las plantillas en nombres que reflejen su uso.

## <a name="related-articles"></a>Artículos relacionados

[Copiar líneas de plantilla de servicio](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
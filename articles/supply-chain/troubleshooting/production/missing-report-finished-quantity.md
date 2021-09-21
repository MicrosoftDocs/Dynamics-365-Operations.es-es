---
title: Error en la actualización de Notificar como terminado con un mensaje que indica que falta cantidad
description: Si intenta finalizar una orden de producción como terminada mientras informa de la cantidad de error, pero no el tiempo o la cantidad de material, la actualización del informe como finalizado fallará.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7785549c47063727f2749749940c1a96a351e70f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477495"
---
# <a name="report-as-finished-update-fails-with-a-missing-quantity-error"></a>Error en la actualización de Notificar como terminado con un mensaje que indica que falta cantidad

## <a name="symptoms"></a>Síntomas

Intenta informar una orden de producción como terminada mientras informa la cantidad de error, pero no mientras informa la cantidad de tiempo o material. El informe como actualización finalizada falla cuando intente finalizar la orden de producción y recibe el siguiente mensaje de error:

> Falta notificación de cantidad como terminada.

## <a name="resolution"></a>Resolución

Si informa la cantidad de error en una orden de producción, también debe informar la cantidad buena.

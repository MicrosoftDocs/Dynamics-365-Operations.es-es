---
title: El límite máximo de un acuerdo de compra no es efectivo en una solicitud de compra
description: El límite máximo de un acuerdo de compra no es efectivo en una solicitud de compra
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c19d40dce65acbe80d4572bfc4e925aa87ea4f02
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477502"
---
# <a name="the-purchase-agreement-maximum-limit-isnt-effective-on-a-purchase-requisition"></a>El límite máximo de un acuerdo de compra no es efectivo en una solicitud de compra

## <a name="symptoms"></a>Síntomas

Cuando una solicitud de compra está vinculada a un acuerdo de compra, el límite máximo del acuerdo de compra no es efectivo en la solicitud de compra. La información de precio predeterminada se especificó correctamente, pero en la solicitud de compra se puede pedir más del límite máximo del acuerdo de compra.

## <a name="resolution"></a>Resolución

Este comportamiento es esperado. Debido a que las solicitudes no siempre se aprueban, no se debe reservar una cantidad o un importe en el acuerdo de compra. Por lo tanto, no se alcanzará el límite máximo del acuerdo de compra.

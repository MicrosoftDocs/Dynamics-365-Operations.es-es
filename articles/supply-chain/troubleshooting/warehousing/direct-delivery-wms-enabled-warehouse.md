---
title: No se puede procesar la entrega directa para el almacén habilitado para WMS
description: Si el almacén tiene WMS habilitado, no admite la entrega directa. Para utilizar la entrega directa, debe seleccionar un artículo y un almacén que no sea WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 090e17091e9fb92c2065679bb9b04637214e2eea
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477576"
---
# <a name="direct-delivery-not-able-to-process-for-wms-enabled-warehouse"></a>No se puede procesar la entrega directa para el almacén habilitado para WMS

## <a name="symptoms"></a>Síntomas

Si se agrega un artículo a una línea de ventas para la entrega directa desde un almacén que está habilitado para la gestión de almacenes (WMS), recibirá el siguiente mensaje de error cuando se actualice la línea de ventas:

> La entrega directa no se puede procesar para el 1% del almacén porque tiene habilitada la gestión del almacén. Especifique otro almacén que no esté habilitado para la gestión de almacenes.

## <a name="resolution"></a>Resolución

Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones. Actualmente, WMS no admite la entrega directa. Por lo tanto, para utilizar la entrega directa, debe seleccionar un artículo y un almacén que no sea WMS.

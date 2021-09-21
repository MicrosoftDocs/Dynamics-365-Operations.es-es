---
title: Error de cálculo de costes de toma retroactiva durante el cierre de inventario
description: En versiones anteriores, es posible que haya recibido un error de cálculo de costos Backflush durante el cierre del inventario. El problema ha sido resuelto.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ae92b7121998d6b1ba2f08ea5736c55637867fbf
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477509"
---
# <a name="backflush-costing-calculation-error-during-inventory-closing"></a>Error de cálculo de costes de toma retroactiva durante el cierre de inventario

## <a name="symptoms"></a>Síntomas

En versiones anteriores a la versión 10.0.13, si no está utilizando el flujo de cálculo de costos de producción ajustada, recibirá el siguiente mensaje de advertencia erróneo durante el cierre del inventario:

> Está a punto de ejecutar un cierre de inventario con fecha %1. No se ha registrado ningún cálculo de contabilización previa de los costes con fecha %1 coincidente con el final del período. Recuerde ejecutar un cálculo de contabilización previa de los costes con fecha %1 coincidente con el final del período. La valoración de los inventarios, el costo de los bienes vendidos y las variaciones podrían no ser correctas en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado.

## <a name="resolution"></a>Resolución

Este problema se ha solucionado en la versión 10.0.13 y posteriores. Para obtener más información, consulte [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).

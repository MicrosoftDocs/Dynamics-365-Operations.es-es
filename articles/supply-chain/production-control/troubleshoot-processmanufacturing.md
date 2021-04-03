---
title: Solucionar problemas de fabricación en procesos
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con fabricación de procesos.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 71ff5eeb2065a67281393777937d50237ab78d5e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259731"
---
# <a name="troubleshoot-process-manufacturing"></a>Solucionar problemas de fabricación en procesos

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con fabricación de procesos.

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a>Cuando utilizo el dispositivo de tarjeta de trabajo para informar una cantidad parcial en el último trabajo de una orden de producción, todos los trabajos anteriores de ese pedido que tienen el estado En curso se finalizan automáticamente.

Este comportamiento se debe al diseño. Sobre la página **Valores predeterminados de órdenes de fabricación**, en la pestaña **Informar como terminado**, hay una opción que se llama **Ruta de la marca final**. Si este tema se establece en *Sí*, se publica un diario de la tarjeta de ruta cuando un trabajador usa el dispositivo de tarjeta de trabajo o el terminal de tarjeta de trabajo para informar la última operación. Este diario marca todas las operaciones como completadas y finaliza todos los trabajos de producción. Cuando la opción **Ruta de la marca final** está configurada en *Sí*, el sistema no tiene en cuenta el estado del trabajo que el trabajador seleccionó cuando informó la última operación. El sistema tampoco considera si el trabajador informa una cantidad total o parcial.

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a>Cuando intento un cierre de existencias, recibo el siguiente mensaje de advertencia: "No se ha ejecutado el cálculo de costos de Backflush con una fecha %1 Se ha registrado el final del período coincidente ".

En versiones anteriores a la versión 10.0.13, si no está utilizando el flujo de cálculo de costos de producción ajustada, recibirá el siguiente mensaje de advertencia erróneo durante el cierre del inventario:

> Está a punto de ejecutar un cierre de inventario con fecha %1. No se ha registrado ningún cálculo de contabilización previa de los costes con fecha %1 coincidente con el final del período. Recuerde ejecutar un cálculo de contabilización previa de los costes con fecha %1 coincidente con el final del período. La valoración de los inventarios, el costo de los bienes vendidos y las variaciones podrían no ser correctas en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado.

Este problema se ha solucionado en la versión 10.0.13 y posteriores. Para obtener más información, consulte [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
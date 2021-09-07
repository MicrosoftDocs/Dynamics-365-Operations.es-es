---
title: Solucionar problemas de informes analíticos
description: En este tema se explica cómo solucionar y diagnosticar problemas si los cambios en los datos de un cliente no se muestran en los espacios de trabajo de un cliente.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2d085c041c1d12eef1271fd3f78262be19fd0629
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413444"
---
# <a name="troubleshoot-analytic-reports"></a>Solucionar problemas de informes analíticos

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Emisión**

Los cambios de los datos de un cliente no aparecen en las pestañas **Análisis** de las áreas de trabajo de un cliente.

**Causa**

De forma predeterminada, los informes de Microsoft Power BI se actualizan cada cuatro horas, de acuerdo con la programación del trabajo por lotes de medida de implementación.

**Resolución**

Este problema podría ser simplemente una cuestión de control de tiempo. Siga estos pasos para iniciar el trabajo por lotes y actualizar las áreas de trabajo de análisis.

1. Abre la página **Trabajos por lotes** en **Administración del sistema \> Vínculos \> Trabajos por lotes \> Trabajos por lotes**. De manera alternativa, use Búsqueda y escriba **Trabajos por lotes**.
1. Encuentre el trabajo **Implementación de medida** en la lista.
1. Seleccione **Editar** en la parte superior de la página, y establezca la fecha /hora inicial programada a un valor que actualice el análisis más cercano a la hora actual.

![Trabajos por lotes.](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

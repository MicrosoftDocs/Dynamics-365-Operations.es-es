---
title: Solucionar problemas de informes analíticos
description: Este artículo explica qué hacer si los cambios en los datos de un cliente no se muestran en los espacios de trabajo de un cliente.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 99d9eb3a16e6470820a2eb0a19c1d50e89bd3d36
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420447"
---
# <a name="troubleshoot-analytic-reports"></a>Solucionar problemas de informes analíticos

**Emisión**

Los cambios de los datos de un cliente no aparecen en las pestañas **Análisis** de las áreas de trabajo de un cliente.

**Causa**

De forma predeterminada, los informes de Microsoft Power BI se actualizan cada cuatro horas, de acuerdo con la programación del trabajo por lotes de medida de implementación.

**Resolución**

Este problema podría ser simplemente una cuestión de control de tiempo. Siga estos pasos para iniciar el trabajo por lotes y actualizar las áreas de trabajo de análisis.

1. Abre la página **Trabajos por lotes** en **Administración del sistema \> Vínculos \> Trabajos por lotes \> Trabajos por lotes**. De manera alternativa, use Búsqueda y escriba **Trabajos por lotes**.
1. Encuentre el trabajo **Implementación de medida** en la lista.
1. Seleccione **Editar** en la parte superior de la página, y establezca la fecha /hora inicial programada a un valor que actualice el análisis más cercano a la hora actual.

![Trabajos por lotes](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
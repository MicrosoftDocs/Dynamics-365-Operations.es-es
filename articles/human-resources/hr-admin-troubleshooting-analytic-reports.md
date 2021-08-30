---
title: Solucionar problemas de informes analíticos
description: Este artículo explica qué hacer si los cambios en los datos de un cliente no se muestran en los espacios de trabajo de un cliente.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d4e76f3b6231b6f307173fa176360daf775c8a7950bc4ab2f2162c768102c369
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717423"
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
---
title: Metodología de la convención de depreciación semestral
description: Este tema describe el método que utilizan los activos fijos para calcular la depreciación mediante la convención semestral, que calcula seis meses de depreciación durante el primer y último año de servicio de un activo.
author: moaamer
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 5e71beb316494d05a3d8ce6066f2a4c72e32a2ad3d75a4ba3560cb0aebfe4cc8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746449"
---
# <a name="half-year-depreciation-convention-methodology"></a>Metodología de la convención de depreciación semestral

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema describe el método que se usa en activos fijos para calcular la depreciación usando la convención semestral. La convención semestral calcula seis meses de depreciación durante el primer y último año de servicio de un activo. Para obtener más información sobre las convenciones de depreciación, consulte [Convenciones y métodos de depreciación](Fixed-asset-depreciation-conventions.md). 

Cuando usa la convención de depreciación semestral, el sistema usa el año de adquisición o el año en que el activo se puso en servicio, luego calcula cinco años de depreciación de ese año y luego agrega seis meses. Para ilustrar este proceso, considere un activo que se adquirió por el precio de 50 000 y se puso en servicio en abril de 2020. Suponga también que el activo tiene una vida útil de cinco años.

El primer año de servicio concluirá en diciembre de 2020, lo que significa que el final de la vida útil de cinco años del activo será diciembre de 2024. La convención de depreciación semestral agregará seis meses a la vida útil del activo, lo que significa que su vida útil finalizará en junio de 2025. 

> Depreciación anual 50 000/5 = 10 000 depreciación mensual 10 000/12 = 833,33 <br>
> Depreciación del primer año 10 000/2 = 5000 y la depreciación mensual subsiguiente 5000/9 = 555,56

   [![Programa de depreciación para la convención de depreciación semestral.](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)

Los períodos de depreciación extendidos que se agregan por la convención semestral proporcionan una asignación más precisa de la depreciación. La convención de seis meses representa los gastos de depreciación de manera más equitativa, lo que es útil para informar sobre el estado de pérdidas y ganancias.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
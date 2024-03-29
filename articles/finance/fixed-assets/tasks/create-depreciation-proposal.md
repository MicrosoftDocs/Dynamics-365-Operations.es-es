---
title: Crear una propuesta de depreciación
description: En este artículo se describe cómo funcionan las propuestas de lote de depreciación y se explica cómo proponer la depreciación para los activos fijos.
author: abruer
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1f39a1412c6f96fe0a8261602a88a6a3c3cd6b8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858507"
---
# <a name="create-a-depreciation-proposal"></a>Crear una propuesta de depreciación

[!include [banner](../../includes/banner.md)]

En este artículo se describe cómo funcionan las propuestas de lote de depreciación y se explica cómo proponer la depreciación para los activos fijos. Esta tarea usa la empresa de prueba USMF y el rol de contable.


## <a name="create-a-depreciation-proposal"></a>Crear una propuesta de depreciación
1. En el Panel de exploración, vaya a **Activos fijos > Entradas del diario > Crear propuesta de depreciación**.
2. En el campo **Nombre del diario**, seleccione una opción en el menú desplegable.
3. En el campo **Fecha final**, especifique una fecha.

    - Active la opción **Resumir depreciación** para resumir las depreciaciones mensuales en una línea de diario.  
    - Por ejemplo, si el valor de fecha es el 31 de marzo de 2015, se genera la siguiente descripción: “Depreciación desde el 31 de enero de 2015”. El campo **Fecha** de las líneas de diario propuestas se establece entonces en 31 de marzo de 2015.  
    - La propuesta de depreciación se puede filtrar por activo, grupo de activos u otros criterios mediante la opción **Filtro**.  
    - Cuando usa el formulario **Crear propuestas de adquisición o depreciación para activos fijos**, puede proponer la depreciación en lotes. Esto se recomienda para propuestas más grandes que usarán más recursos del sistema. Si selecciona la opción de lote, puede completar otras tareas durante ese tiempo. Cuando se propone la depreciación de esta manera, la depreciación se calcula para los modelos de valor de activos fijos.  

4. Seleccione **Crear diario**.

## <a name="review-depreciation-entries"></a>Revisar los movimientos de amortización
1. En el panel de navegación, vaya a **Módulos > Activos fijos > Movimientos del diario > Diario de activos fijos**.
2. En la lista, busque y seleccione el registro deseado.
3. Seleccionar **Líneas**.
4. Seleccione **Registrar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

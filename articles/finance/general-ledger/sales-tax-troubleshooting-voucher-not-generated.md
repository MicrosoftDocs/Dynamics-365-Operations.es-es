---
title: El asiento no se genera
description: Este tema proporciona información sobre resolución de problemas que puede ayudar cuando debería generarse un asiento pero no ocurre así.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: eafc9110ec58be5083569188d59b67a62e86c85d
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947706"
---
# <a name="voucher-isnt-generated"></a>El asiento no se genera

[!include [banner](../includes/banner.md)]

Si se debe generar un asiento, pero la página **Transacciones de asientos** no muestra ningún asiento, siga los pasos de las siguientes secciones ,según sea necesario para solucionar este problema.

[![Página de transacciones de asientos que no tiene asientos](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>Compruebe la aplicabilidad de impuestos

1. Vaya a **Impuesto** \> **Tareas periódicas** \> **Entradas del diario del libro mayor auxiliar aún no transferidas**.
2. Si hay un registro de diario, selecciónelo y luego seleccione **Transferir ahora**.

    [![Botón Transferir ahora en la página Entradas de diario del libro mayor auxiliar aún no transferidas](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. Abra de nuevo la página **Transacciones de asientos** para ver si se generó el asiento.

## <a name="determine-whether-customization-exists"></a>Determinar si existe personalización

Si ha completado los pasos de la sección anterior pero no ha encontrado problemas, determine si existe personalización. Si no existe personalización, cree una solicitud de servicio de Microsoft para obtener más soporte.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

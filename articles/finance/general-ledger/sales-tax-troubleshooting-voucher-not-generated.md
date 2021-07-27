---
title: El asiento no se genera
description: Este tema proporciona información sobre resolución de problemas que puede ayudar cuando debería generarse un asiento pero no ocurre así.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 82357b7fe00b93715f44eb024ac78d7cc1adca84
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356110"
---
# <a name="voucher-isnt-generated"></a>El asiento no se genera

[!include [banner](../includes/banner.md)]

Si se debe generar un asiento, pero la página **Transacciones de asientos** no muestra ningún asiento, siga los pasos de las siguientes secciones ,según sea necesario para solucionar este problema.

[![Página de transacciones de asientos que no tiene asientos.](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>Compruebe la aplicabilidad de impuestos

1. Vaya a **Impuesto** \> **Tareas periódicas** \> **Entradas del diario del libro mayor auxiliar aún no transferidas**.
2. Si hay un registro de diario, selecciónelo y luego seleccione **Transferir ahora**.

    [![Botón Transferir ahora en la página Entradas de diario del libro mayor auxiliar aún no transferidas.](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. Abra de nuevo la página **Transacciones de asientos** para ver si se generó el asiento.

## <a name="determine-whether-customization-exists"></a>Determinar si existe personalización

Si ha completado los pasos de la sección anterior pero no ha encontrado problemas, determine si existe personalización. Si no existe personalización, cree una solicitud de servicio de Microsoft para obtener más soporte.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

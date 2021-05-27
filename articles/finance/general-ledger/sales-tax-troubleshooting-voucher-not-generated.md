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
ms.openlocfilehash: ba23b597b1d7d283b99638fb7d5d91da00afb09c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018766"
---
# <a name="voucher-isnt-generated"></a><span data-ttu-id="5153e-103">El asiento no se genera</span><span class="sxs-lookup"><span data-stu-id="5153e-103">Voucher isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5153e-104">Si se debe generar un asiento, pero la página **Transacciones de asientos** no muestra ningún asiento, siga los pasos de las siguientes secciones ,según sea necesario para solucionar este problema.</span><span class="sxs-lookup"><span data-stu-id="5153e-104">If a voucher should be generated, but the **Voucher transactions** page doesn't show any vouchers, follow the steps in the following sections as required to troubleshoot this issue.</span></span>

<span data-ttu-id="5153e-105">[![Página de transacciones de asientos que no tiene asientos](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="5153e-105">[![Voucher transactions page that has no vouchers](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span></span>

## <a name="check-the-tax-applicability"></a><span data-ttu-id="5153e-106">Compruebe la aplicabilidad de impuestos</span><span class="sxs-lookup"><span data-stu-id="5153e-106">Check the tax applicability</span></span>

1. <span data-ttu-id="5153e-107">Vaya a **Impuesto** \> **Tareas periódicas** \> **Entradas del diario del libro mayor auxiliar aún no transferidas**.</span><span class="sxs-lookup"><span data-stu-id="5153e-107">Go to **Tax** \> **Periodic tasks** \> **Subledger journal entries not yet transferred**.</span></span>
2. <span data-ttu-id="5153e-108">Si hay un registro de diario, selecciónelo y luego seleccione **Transferir ahora**.</span><span class="sxs-lookup"><span data-stu-id="5153e-108">If there is a journal record, select it, and then select **Transfer now**.</span></span>

    <span data-ttu-id="5153e-109">[![Botón Transferir ahora en la página Entradas de diario del libro mayor auxiliar aún no transferidas](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="5153e-109">[![Transfer now button on the Subledger journal entries not yet transferred page](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span></span>

3. <span data-ttu-id="5153e-110">Abra de nuevo la página **Transacciones de asientos** para ver si se generó el asiento.</span><span class="sxs-lookup"><span data-stu-id="5153e-110">Open the **Voucher transactions** page again to see whether the voucher was generated.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="5153e-111">Determinar si existe personalización</span><span class="sxs-lookup"><span data-stu-id="5153e-111">Determine whether customization exists</span></span>

<span data-ttu-id="5153e-112">Si ha completado los pasos de la sección anterior pero no ha encontrado problemas, determine si existe personalización.</span><span class="sxs-lookup"><span data-stu-id="5153e-112">If you've completed the steps in the previous section but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="5153e-113">Si no existe personalización, cree una solicitud de servicio de Microsoft para obtener más soporte.</span><span class="sxs-lookup"><span data-stu-id="5153e-113">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

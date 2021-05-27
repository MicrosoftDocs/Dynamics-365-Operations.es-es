---
title: Configurar los multivencimientos con la asignación de TDS
description: Este tema explica cómo configurar multivencimientos con la asignación de impuestos deducidos en el origen (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 47551f52f35fec5ae49d696e3f4027b7d2eb2e19
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023576"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a><span data-ttu-id="f48b2-103">Configurar los multivencimientos con la asignación de TDS</span><span class="sxs-lookup"><span data-stu-id="f48b2-103">Set up payment schedules with TDS allocation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f48b2-104">Este tema explica cómo configurar multivencimientos con la asignación de impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="f48b2-104">This topic explains how to set up payment schedules with Tax Deducted at Source (TDS) allocation.</span></span>

1. <span data-ttu-id="f48b2-105">Vaya a **Proveedores \> Configuración de pagos \> Multivencimientos**.</span><span class="sxs-lookup"><span data-stu-id="f48b2-105">Go to **Accounts payable \> Payment setup \> Payment schedules**.</span></span>

    <span data-ttu-id="f48b2-106">[![Página de multivencimientos](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span><span class="sxs-lookup"><span data-stu-id="f48b2-106">[![Payment schedules page](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span></span>

2. <span data-ttu-id="f48b2-107">En el panel de acciones, seleccione **Nuevo** para crear un multivencimiento e introduzca los detalles requeridos.</span><span class="sxs-lookup"><span data-stu-id="f48b2-107">On the Action Pane, select **New** to create a payment schedule, and enter the required details.</span></span>
3. <span data-ttu-id="f48b2-108">En el campo **Asignación**, seleccione el método que se utilizará para asignar el pago para el multivencimiento:</span><span class="sxs-lookup"><span data-stu-id="f48b2-108">In the **Allocation** field, select the method to use to allocate the payment for the payment schedule:</span></span>

    - <span data-ttu-id="f48b2-109">Total</span><span class="sxs-lookup"><span data-stu-id="f48b2-109">Total</span></span>
    - <span data-ttu-id="f48b2-110">Importe fijo</span><span class="sxs-lookup"><span data-stu-id="f48b2-110">Fixed amount</span></span>
    - <span data-ttu-id="f48b2-111">Cantidad fija</span><span class="sxs-lookup"><span data-stu-id="f48b2-111">Fixed quantity</span></span>
    - <span data-ttu-id="f48b2-112">Especificado</span><span class="sxs-lookup"><span data-stu-id="f48b2-112">Specified</span></span>

    <span data-ttu-id="f48b2-113">El campo **Asignación de retención de impuestos** muestra el método de asignación de TDS para el multivencimiento.</span><span class="sxs-lookup"><span data-stu-id="f48b2-113">The **Withholding tax allocation** field shows the TDS allocation method for the payment schedule.</span></span> <span data-ttu-id="f48b2-114">Si selecciona **Total** en el campo **Asignación**, el campo **Asignación de retención de impuestos** se establece automáticamente en **Total**.</span><span class="sxs-lookup"><span data-stu-id="f48b2-114">If you select **Total** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Total**.</span></span> <span data-ttu-id="f48b2-115">Si selecciona **Importe fijo**, **Cantidad fija** o **Especificado** en el campo **Asignación**, el campo **Asignación de retención de impuestos** se establece automáticamente en **Proporcionalmente**.</span><span class="sxs-lookup"><span data-stu-id="f48b2-115">If you select **Fixed amount**, **Fixed quantity**, or **Specified** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Proportionally**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f48b2-116">Si el campo **Asignación de retención de impuestos** está configurado en **Total**, los plazos de pago se calculan en base al importe bruto, que incluye el importe de TDS.</span><span class="sxs-lookup"><span data-stu-id="f48b2-116">If the **Withholding tax allocation** field is set to **Total**, the payment installments are calculated based on the gross amount, which includes the TDS amount.</span></span> <span data-ttu-id="f48b2-117">Si el campo **Asignación de retención de impuestos** está configurado en **Proporcionalmente**, los plazos de pago se calculan en base al importe neto de la factura tras deducir el importe de TDS.</span><span class="sxs-lookup"><span data-stu-id="f48b2-117">If the **Withholding tax allocation** field is set to **Proportionally**, the payment installments are calculated based on the net invoice amount after the TDS amount is deducted.</span></span>

4. <span data-ttu-id="f48b2-118">Especifique los demás detalles necesarios y cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f48b2-118">Enter the other required details, and then close the page.</span></span>

---
title: Configurar períodos de liquidación de retención de impuestos para el tipo de impuesto de TDS
description: Este tema explica cómo configurar períodos de liquidación para períodos de liquidación de impuestos deducidos en el origen (TDS).
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
ms.openlocfilehash: 9430bc1386f127d02b598d6cad1b53f66e0cf2ba
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023555"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a><span data-ttu-id="bdbd8-103">Configurar períodos de liquidación de retención de impuestos para el tipo de impuesto de TDS</span><span class="sxs-lookup"><span data-stu-id="bdbd8-103">Set up withholding tax settlement periods for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bdbd8-104">Este tema explica cómo configurar períodos de liquidación para períodos de liquidación de impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="bdbd8-104">This topic explains how to set up settlement periods for Tax Deducted at Source (TDS) settlement periods.</span></span>

1. <span data-ttu-id="bdbd8-105">Vaya a **Impuestos \> Impuestos indirectos \> Retención de impuestos \> Períodos de liquidación de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax settlement periods**.</span></span>

    <span data-ttu-id="bdbd8-106">[![Página Períodos de liquidación de retención de impuestos](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span><span class="sxs-lookup"><span data-stu-id="bdbd8-106">[![Withholding tax settlement periods page](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span></span>

2. <span data-ttu-id="bdbd8-107">En el campo **Tipo de impuesto**, seleccione **TDS** para configurar períodos de liquidación de retención de impuestos para el tipo de impuesto TDS.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-107">In the **Tax type** field, select **TDS** to set up withholding tax settlement periods for the TDS tax type.</span></span>
3. <span data-ttu-id="bdbd8-108">Seleccione **Nuevo** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-108">Select **New** to create a line.</span></span>
4. <span data-ttu-id="bdbd8-109">En el campo **Período de liquidación**, especifique un nombre para el período de liquidación de TDS.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-109">In the **Settlement period** field, enter a name for the TDS settlement period.</span></span>
5. <span data-ttu-id="bdbd8-110">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="bdbd8-111">En el campo **Autoridad de retención de impuestos**, seleccione la autoridad de TDS para la que está definiendo el período de liquidación de TDS.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-111">In the **Withholding tax authority** field, select the TDS authority that you're defining the TDS settlement period for.</span></span>
7. <span data-ttu-id="bdbd8-112">En la ficha desplegable **General**, en el campo **Intervalo de período**, seleccione el tipo de intervalo de período para el período de liquidación de TDS.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-112">On the **General** FastTab, in the **Period interval** field, select the type of period interval for the TDS settlement period.</span></span>
8. <span data-ttu-id="bdbd8-113">En el campo **Número de unidades**, especifique el número de unidades para el tipo de intervalo de período.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-113">In the **Number of units** field, specify the number of units for the period interval type.</span></span>
9. <span data-ttu-id="bdbd8-114">En la ficha desplegable **Períodos**, en el campo **Fecha inicial**, seleccione la fecha inicial del período de liquidación de TDS.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-114">On the **Periods** FastTab, in the **From date** field, select the start date for the TDS settlement period.</span></span> <span data-ttu-id="bdbd8-115">En el campo **Fecha final**, seleccione la fecha final.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-115">In the **To date** field, select the end date.</span></span>
10. <span data-ttu-id="bdbd8-116">Para crear un período de liquidación de TDS posterior para un período existente basado en el intervalo de período y las unidades de período, seleccione **Nuevo período**.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-116">To create a subsequent TDS settlement period for an existing period, based on the period interval and period units, select **New period**.</span></span>
11. <span data-ttu-id="bdbd8-117">Para ver los detalles de la liquidación periódica de TDS que se ejecuta para un período de liquidación específico, seleccione **Pagos de retención de impuestos** para abrir la página **Pago de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-117">To view the details of the periodic TDS settlement that is run for a specific settlement period, select **Withholding tax payments** to open the **Withholding tax payment** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bdbd8-118">Para ejecutar el proceso de liquidación periódica de TDS, vaya a **Contabilidad general \> Periódica \> Retención de impuestos \> Pago de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-118">To run the periodic TDS settlement process, go to **General ledger \> Periodic \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="bdbd8-119">[![Página Pago de retención de impuestos](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span><span class="sxs-lookup"><span data-stu-id="bdbd8-119">[![Withholding tax payment page](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span></span>

12. <span data-ttu-id="bdbd8-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bdbd8-120">Close the page.</span></span>

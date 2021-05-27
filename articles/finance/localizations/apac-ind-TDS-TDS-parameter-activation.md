---
title: Configurar los parámetros de TDS
description: Este tema explica cómo configurar parámetros para activar la característica de impuestos deducidos en el origen (TDS) en transacciones específicas. Este es un paso necesario para utilizar la característica de impuestos deducidos en el origen (TDS).
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
ms.openlocfilehash: dda276b7d634317aae26728f7d9f51af9ccfb896
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023566"
---
# <a name="set-the-tds-parameters"></a><span data-ttu-id="ae070-104">Configurar los parámetros de TDS</span><span class="sxs-lookup"><span data-stu-id="ae070-104">Set the TDS parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ae070-105">Este tema explica cómo configurar parámetros para activar la característica de impuestos deducidos en el origen (TDS) en transacciones específicas.</span><span class="sxs-lookup"><span data-stu-id="ae070-105">This topic explains how to set parameters to activate Tax Deducted at Source (TDS) functionality in specified transactions.</span></span> <span data-ttu-id="ae070-106">Este es un paso necesario para utilizar la característica de impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="ae070-106">This is a necessary step to use the Tax Deducted at Source TDS feature.</span></span>

1. <span data-ttu-id="ae070-107">Vaya a **Contabilidad general \> Configuración de contabilidad \> Parámetros de Contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="ae070-107">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="ae070-108">En la pestaña **Impuestos directos**, en la sección **Impuesto deducido en el origen**, establezca la opción **Activar TDS** a **Sí** para activar la característica de TDS y las páginas y campos que se utilizan para ello.</span><span class="sxs-lookup"><span data-stu-id="ae070-108">On the **Direct taxes** tab, in the **Tax Deducted at Source** section, set the **Activate TDS** option to **Yes** to activate the TDS functionality, and the pages and fields that are used for it.</span></span>
3. <span data-ttu-id="ae070-109">Establezca la opción **Factura** a **Sí** para activar los campos que se utilizan para calcular y deducir el TDS a nivel de factura.</span><span class="sxs-lookup"><span data-stu-id="ae070-109">Set the **Invoice** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the invoice level.</span></span>
4. <span data-ttu-id="ae070-110">Establezca la opción **Pago** a **Sí** para activar los campos que se utilizan para calcular y deducir el TDS a nivel de pagos.</span><span class="sxs-lookup"><span data-stu-id="ae070-110">Set the **Payment** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the payment level.</span></span>

    <span data-ttu-id="ae070-111">[![Pestaña de impuestos directos](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span><span class="sxs-lookup"><span data-stu-id="ae070-111">[![Direct taxes tab](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span></span>

5. <span data-ttu-id="ae070-112">En la pestaña **Secuencias numéricas**, busque la fila donde el campo **Referencia** está configurado en **Pago de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="ae070-112">On the **Number sequences** tab, find the row where the **Reference** field is set to **Withholding tax payment**.</span></span> <span data-ttu-id="ae070-113">En el campo **Código de secuencia numérica** para la fila, seleccione el código de secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="ae070-113">In the **Number sequence code** field for the row, select the number sequence code.</span></span> <span data-ttu-id="ae070-114">El código de secuencia numérica se utiliza para generar números de asiento para el proceso de liquidación periódica de TDS.</span><span class="sxs-lookup"><span data-stu-id="ae070-114">The number sequence code is used to generate voucher numbers for the periodic TDS settlement process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ae070-115">Para ejecutar el proceso de liquidación periódica de TDS, vaya a **Impuesto \> Declaraciones \> Retención de impuestos \> Pago de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="ae070-115">To run the periodic TDS settlement process, go to **Tax \> Declarations \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="ae070-116">[![Ficha Secuencias numéricas](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span><span class="sxs-lookup"><span data-stu-id="ae070-116">[![Number sequences tab](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span></span>

6. <span data-ttu-id="ae070-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ae070-117">Close the page.</span></span>

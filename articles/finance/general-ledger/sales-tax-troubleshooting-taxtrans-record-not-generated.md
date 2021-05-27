---
title: El registro TaxTrans no se genera
description: Este tema proporciona información sobre resolución de problemas que puede ayudar cuando no se genera un registro TaxTrans.
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
ms.openlocfilehash: 74987506699834d86703702106e5abf87bfa45da
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018790"
---
# <a name="taxtrans-record-isnt-generated"></a><span data-ttu-id="448e8-103">El registro TaxTrans no se genera</span><span class="sxs-lookup"><span data-stu-id="448e8-103">TaxTrans record isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="448e8-104">Si selecciona **Impuesto registrado** para una transacción, pero la página **Impuesto registrado** no muestra ninguna línea de impuestos o le falta una línea de impuestos, el registro **TaxTrans** podría no haberse generado.</span><span class="sxs-lookup"><span data-stu-id="448e8-104">If you select **Posted sales tax** for a transaction, but the **Posted sales tax** page either shows no tax lines or is missing a tax line, the **TaxTrans** record might not have been generated.</span></span>

<span data-ttu-id="448e8-105">[![Página de impuestos que no tiene artículos de línea](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="448e8-105">[![Posted sales tax page that has no line items](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span></span>

<span data-ttu-id="448e8-106">Para solucionar este problema, siga los pasos de las siguientes secciones según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="448e8-106">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a><span data-ttu-id="448e8-107">Comprobar el impuesto antes de registrar la transacción</span><span class="sxs-lookup"><span data-stu-id="448e8-107">Check the sales tax before you post the transaction</span></span>

1. <span data-ttu-id="448e8-108">Antes de registrar la transacción, en la página **Registro de factura**, seleccione **Impuesto** para comprobar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="448e8-108">Before you post the transaction, on the **Posting invoice** page, select **Sales tax** to check the calculation.</span></span>

    <span data-ttu-id="448e8-109">[![Botón de impuesto en la página Registro de factura](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="448e8-109">[![Sales tax button on the Posting invoice page](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span></span>

2. <span data-ttu-id="448e8-110">En la página **Transacciones de impuestos temporales**, revise el resultado del cálculo.</span><span class="sxs-lookup"><span data-stu-id="448e8-110">On the **Temporary sales tax transactions** page, review the result of the calculation.</span></span> <span data-ttu-id="448e8-111">Si no se calcula ningún impuesto, consulte [El impuesto no se calcula o el importe del impuesto es cero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span><span class="sxs-lookup"><span data-stu-id="448e8-111">If no tax is calculated, see [Tax isn't calculated or the tax amount is zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span></span>

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a><span data-ttu-id="448e8-112">Busque el registro TaxTrans en todos los impuestos registrados</span><span class="sxs-lookup"><span data-stu-id="448e8-112">Find the TaxTrans record in all posted sales tax</span></span>

1. <span data-ttu-id="448e8-113">Vaya a **Impuestos** \> **Consultas e informes** \> **Consultas de impuestos** > **Impuestos registrados**.</span><span class="sxs-lookup"><span data-stu-id="448e8-113">Go to **Tax** \> **Inquiries and reports** \> **Sales tax inquiries** > **Posted sales tax**.</span></span>
2. <span data-ttu-id="448e8-114">En el encabezado de la columna **Asiento**, seleccione el símbolo de filtro para encontrar el registro **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="448e8-114">In the **Voucher** column heading, select the filter symbol to find the **TaxTrans** record.</span></span>
3. <span data-ttu-id="448e8-115">Si encuentra los registros de impuestos que está buscando, compruebe la fecha.</span><span class="sxs-lookup"><span data-stu-id="448e8-115">If you find the sales tax records that you're looking for, check the date.</span></span> <span data-ttu-id="448e8-116">Si la fecha difiere de la fecha del encabezado del diario, cree una solicitud de servicio de Microsoft para obtener soporte adicional.</span><span class="sxs-lookup"><span data-stu-id="448e8-116">If the date differs from the date of the journal header, create a Microsoft service request for additional support.</span></span>

    <span data-ttu-id="448e8-117">[![Página de impuestos registrados](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="448e8-117">[![Posted sales tax page](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span></span>

## <a name="debug-to-check-details"></a><span data-ttu-id="448e8-118">Depurar para comprobar detalles</span><span class="sxs-lookup"><span data-stu-id="448e8-118">Debug to check details</span></span>

1. <span data-ttu-id="448e8-119">Para obtener información sobre cómo depurar y determinar si **TmpTaxWorkTrans** y **TaxUncommitted** se generan correctamente, consulte [El valor del campo en TaxTrans es incorrecto](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span><span class="sxs-lookup"><span data-stu-id="448e8-119">For information about how to debug and determine whether **TmpTaxWorkTrans** and **TaxUncommitted** are correctly generated, see [Field value in TaxTrans is incorrect](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span></span>
2. <span data-ttu-id="448e8-120">Si **TaxTmpWorkTrans** o **TaxUncommitted** se generan correctamente, agregue un punto de interrupción en **TaxPost::SaveAndPost ()** e **Impuesto::SaveAndPost** para depurar la razón por la que **TaxTrans** no está insertado.</span><span class="sxs-lookup"><span data-stu-id="448e8-120">If **TaxTmpWorkTrans** or **TaxUncommitted** is correctly generated, add a breakpoint at **TaxPost::SaveAndPost()** and **Tax::SaveAndPost** to debug the reason why **TaxTrans** isn't inserted.</span></span>

    <span data-ttu-id="448e8-121">[![Puntos de interrupción agregados en el código](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="448e8-121">[![Breakpoints added in code](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span></span>

    <span data-ttu-id="448e8-122">[![Resultados de los puntos de interrupción agregados](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="448e8-122">[![Results of added breakpoints](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="448e8-123">Determinar si existe personalización</span><span class="sxs-lookup"><span data-stu-id="448e8-123">Determine whether customization exists</span></span>

<span data-ttu-id="448e8-124">Si ha completado los pasos de las secciones anteriores pero no ha encontrado problemas, determine si existe personalización.</span><span class="sxs-lookup"><span data-stu-id="448e8-124">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="448e8-125">Si no existe personalización, cree una solicitud de servicio de Microsoft para obtener más soporte.</span><span class="sxs-lookup"><span data-stu-id="448e8-125">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: Cálculo de TDS en facturas desde la página de facturas de servicios
description: Este tema explica cómo calcular los impuestos deducidos en el origen (TDS) en facturas mediante la página de facturas de servicios.
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
ms.openlocfilehash: 7d551a8ba6ba9ca282fd9de3fa7d7c7303e394ed
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023574"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a><span data-ttu-id="60ea0-103">Cálculo de TDS en facturas desde la página de facturas de servicios</span><span class="sxs-lookup"><span data-stu-id="60ea0-103">TDS calculation on invoices from the Free text invoice page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60ea0-104">Este tema explica cómo calcular los impuestos deducidos en el origen (TDS) en facturas mediante la página de **Facturas de servicios**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-104">This topic explains how to calculate Tax Deducted at Source (TDS) on invoices by using the **Free text invoice** page.</span></span>

1. <span data-ttu-id="60ea0-105">Vaya a **Clientes \> Facturas \> Todas las facturas de servicios**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-105">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>

    <span data-ttu-id="60ea0-106">[![Página de facturas de servicios](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span><span class="sxs-lookup"><span data-stu-id="60ea0-106">[![Free text invoice page](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span></span>

2. <span data-ttu-id="60ea0-107">Seleccione **Nuevo** para crear una factura de servicios y especificar los detalles necesarios.</span><span class="sxs-lookup"><span data-stu-id="60ea0-107">Select **New** to create a free text invoice, and enter the required details.</span></span>
3. <span data-ttu-id="60ea0-108">Seleccione la pestaña **Factura**. En la sección **Grupo de retención de impuestos**, el campo **Naturaleza del evaluado** muestra la categoría de naturaleza del evaluado del cliente.</span><span class="sxs-lookup"><span data-stu-id="60ea0-108">Select the **Invoice** tab. In the **Withholding tax group** section, the **Nature of assessee** field shows the nature of assessee category of the customer.</span></span>
4. <span data-ttu-id="60ea0-109">En el campo **Grupo TDS**, revise o cambie el grupo TDS predeterminado definido para el cliente.</span><span class="sxs-lookup"><span data-stu-id="60ea0-109">In the **TDS group** field, review or change the default TDS group that is defined for the customer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="60ea0-110">Cuando selecciona un valor en el campo **Grupo TDS**, el campo **Grupo TDS** deja de estar disponible.</span><span class="sxs-lookup"><span data-stu-id="60ea0-110">When you select a value in the **TDS group** field, the **TCS group** field becomes unavailable.</span></span> <span data-ttu-id="60ea0-111">TDS se calcula solo si se ha establecido la opción **Calcular retención de impuestos** en **Sí** para el cliente en la página **Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-111">TDS is calculated only if the **Calculate withholding tax** option is set to **Yes** for the customer on the **All customers** page.</span></span>

5. <span data-ttu-id="60ea0-112">En la pestaña **Información de impuestos**, en la sección **Información de la empresa**, en el campo **Nombre**, seleccione el nombre de la empresa para una dirección alternativa que se ha configurado para la empresa.</span><span class="sxs-lookup"><span data-stu-id="60ea0-112">On the **Tax information** tab, in the **Company information** section, in the **Name** field, select the company name for an alternate address that has been set up for the company.</span></span>

    <span data-ttu-id="60ea0-113">En la sección **Retención de impuestos**, el campo **Número de cuenta de impuestos (TAN)** muestra el número de cuenta de impuestos (TAN) de la empresa seleccionada.</span><span class="sxs-lookup"><span data-stu-id="60ea0-113">In the **Withholding tax** section, the **Tax Account Number (TAN)** field shows the tax account number (TAN) for the selected company.</span></span>

6. <span data-ttu-id="60ea0-114">En la pestaña **Líneas de factura**, cree líneas de factura e introduzca los detalles necesarios.</span><span class="sxs-lookup"><span data-stu-id="60ea0-114">On the **Invoice lines** tab, create invoice lines, and enter the required details.</span></span>

    <span data-ttu-id="60ea0-115">En la sección **Grupo de retención de impuestos**, el campo **Número de cuenta de impuestos (TAN)** muestra el TAN y el campo **Grupo TDS** muestra el grupo TDS.</span><span class="sxs-lookup"><span data-stu-id="60ea0-115">In the **Withholding tax group** section, the **Tax Account Number (TAN)** field shows the TAN, and the **TDS group** field shows the TDS group.</span></span>

7. <span data-ttu-id="60ea0-116">Seleccione **Retención de impuestos** para abrir la página **Transacciones de retención temporal de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-116">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="60ea0-117">La parte superior de esta página tiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="60ea0-117">The upper part of this page has the following fields:</span></span>

    - <span data-ttu-id="60ea0-118">**Retención de importe total de impuestos**: el total de TDS calculado para la transacción para el grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="60ea0-118">**Withholding tax amount in total** – The total TDS that was calculated for the transaction for the TDS group.</span></span>
    - <span data-ttu-id="60ea0-119">**Valor**: el porcentaje total utilizado para calcular TDS para la transacción.</span><span class="sxs-lookup"><span data-stu-id="60ea0-119">**Value** – The total percentage that was used to calculate TDS for the transaction.</span></span> <span data-ttu-id="60ea0-120">El porcentaje total se basa en la fórmula que se define para los códigos de impuestos TDS y que se adjunta al grupo TDS.</span><span class="sxs-lookup"><span data-stu-id="60ea0-120">The total percentage is based on the formula that is defined for the TDS tax codes and attached to the TDS group.</span></span>
    - <span data-ttu-id="60ea0-121">**Importe total de la retención de impuestos ajustada**: el importe total de TDS ajustado para todos los códigos de impuestos en el grupo TDS.</span><span class="sxs-lookup"><span data-stu-id="60ea0-121">**Adjusted withholding tax amount in total** – The total adjusted TDS amount for all tax codes in the TDS group.</span></span>
    - <span data-ttu-id="60ea0-122">**TDS**: una casilla seleccionada indica que un grupo de TDS está adjunto a la transacción.</span><span class="sxs-lookup"><span data-stu-id="60ea0-122">**TDS** – A selected checkbox indicates that a TDS group is attached to the transaction.</span></span>

    <span data-ttu-id="60ea0-123">Los campos en las pestañas **Información general**, **General** e **Ajuste** muestran el importe de TDS calculado y los detalles del importe de TDS ajustado para cada código de impuestos de TDS adjunto al grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="60ea0-123">The fields on the **Overview**, **General**, and **Adjustment** tabs show the calculated TDS amount and details of the adjusted TDS amount for each TDS tax code that is attached to the TDS group.</span></span>

8. <span data-ttu-id="60ea0-124">Seleccione **Umbral** para abrir la página **Umbral**, donde puede revisar el límite de umbral que se define para el componente de impuestos de TDS que está adjunto a un código de impuestos de TDS específico.</span><span class="sxs-lookup"><span data-stu-id="60ea0-124">Select **Threshold** to open the **Threshold** page, where you can review the threshold limit that is defined for the TDS tax component that is attached to a specific TDS tax code.</span></span>
9. <span data-ttu-id="60ea0-125">Seleccione **Diseñador de fórmulas** para abrir la página **Diseñador de fórmulas**, donde puede revisar la fórmula que se define para un código de impuestos de TDS específico.</span><span class="sxs-lookup"><span data-stu-id="60ea0-125">Select **Formula designer** to open the **Formula designer** page, where you can review the formula that is defined for a specific TDS tax code.</span></span>
10. <span data-ttu-id="60ea0-126">Registre la factura de servicio.</span><span class="sxs-lookup"><span data-stu-id="60ea0-126">Post the free text invoice.</span></span> <span data-ttu-id="60ea0-127">El importe de TDS que se calcula para la factura de servicios se registra en la cuenta de cliente que se define para cada código de impuestos de TDS en el grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="60ea0-127">The TDS amount that is calculated for the free text invoice is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="60ea0-128">Las cuentas de clientes para los códigos de impuestos TDS se definen en la página **Códigos de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-128">The receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>
11. <span data-ttu-id="60ea0-129">Seleccione **Retención de impuestos registrados** para abrir la página **Transacciones de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-129">Select **Posted withholding tax** to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="60ea0-130">El campo **Valor** muestra el porcentaje total utilizado para calcular TDS para la transacción.</span><span class="sxs-lookup"><span data-stu-id="60ea0-130">The **Value** field shows the total percentage that was used to calculate TDS for the transaction.</span></span>

    <span data-ttu-id="60ea0-131">Los campos de las pestañas **Información general**, **General** e **Importe** muestran los importes de TDS que se calcularon en las líneas de factura.</span><span class="sxs-lookup"><span data-stu-id="60ea0-131">The fields on the **Overview**, **General**, and **Amount** tabs show the TDS amounts that were calculated on the invoice lines.</span></span>

12. <span data-ttu-id="60ea0-132">Revise la información de cálculo de TDS para cada código de impuestos de TDS adjunto al grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="60ea0-132">Review the TDS calculation information for each TDS tax code that is attached to the TDS group.</span></span>

---
title: Configurar componentes de impuestos para el tipo de impuestos TDS
description: Este tema explica cómo configurar componentes de retención de impuestos para el tipo de impuesto de impuesto deducido en el origen (TDS). También explica cómo definir el límite de umbral que se utiliza para calcular TDS para cada componente de TDS.
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
ms.openlocfilehash: 6e0a6a05fcb4afb8c8965e25c3089bc1b3d98431
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023563"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a><span data-ttu-id="879b5-104">Configurar componentes de impuestos para el tipo de impuestos TDS</span><span class="sxs-lookup"><span data-stu-id="879b5-104">Set up tax components for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="879b5-105">Este tema explica cómo configurar componentes de retención de impuestos para el tipo de impuesto de impuesto deducido en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="879b5-105">This topic explains how to set up withholding tax components for the Tax Deducted at Source (TDS) tax type.</span></span> <span data-ttu-id="879b5-106">Los componentes de TDS son TDS, suplementos, PE-Cess y SHE Cess.</span><span class="sxs-lookup"><span data-stu-id="879b5-106">The TDS components are TDS, surcharge, PE-Cess, and SHE Cess.</span></span> <span data-ttu-id="879b5-107">Este tema también explica cómo definir el umbral que se utiliza para calcular TDS para cada componente de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-107">This topic also explains how to define the threshold that is used to calculate TDS for each TDS component.</span></span> <span data-ttu-id="879b5-108">Además, puede definir un umbral de excepción que se utiliza para calcular TDS para cada componente de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-108">Additionally, you can define an exception threshold that is used to calculate TDS for each TDS component.</span></span>

<span data-ttu-id="879b5-109">Siga estos pasos para configurar los componentes de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-109">Follow these steps to set up TDS components.</span></span>

1. <span data-ttu-id="879b5-110">Vaya a **Impuesto \> Configuración \> Retención de impuestos \> Componentes de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="879b5-110">Go to **Tax \> Setup \> Withholding tax \> Withholding tax components**.</span></span>

    <span data-ttu-id="879b5-111">[![Página de componentes de retenciones de impuestos](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span><span class="sxs-lookup"><span data-stu-id="879b5-111">[![Withholding tax components page](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)</span></span>

2. <span data-ttu-id="879b5-112">En campo **Tipo de impuesto**, seleccione **TDS** para configurar componentes de retención de impuestos para el tipo de impuesto TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-112">In the **Tax type** field, select **TDS** to set up withholding tax components for the TDS tax type.</span></span>
3. <span data-ttu-id="879b5-113">En el panel de acciones, haga clic en **Nuevo** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="879b5-113">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="879b5-114">En el campo **Componente de retención de impuestos**, introduzca un nombre para el componente de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-114">In the **Withholding tax component** field, enter a name for the TDS component.</span></span>
5. <span data-ttu-id="879b5-115">En el campo **Grupo de componentes de retención de impuestos**, seleccione el grupo de componentes de retención de impuestos de TDS al que adjuntar el componente de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-115">In the **Withholding tax component group** field, select the TDS withholding tax component group to attach the TDS component to.</span></span>
6. <span data-ttu-id="879b5-116">En la ficha desplegable **General**, en el campo **Descripción**, escriba una descripción del componente de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-116">On the **General** FastTab, in the **Description** field, enter a description of  the TDS component.</span></span>
7. <span data-ttu-id="879b5-117">En el panel de acciones, seleccione **Umbral** para abrir la página **Umbral** para que pueda definir el umbral que se utiliza para calcular los TDS para el componente de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-117">On the Action Pane, select **Threshold** to open **Threshold** page, so that you can define the threshold that is used to calculate TDS for the TDS component.</span></span>
8. <span data-ttu-id="879b5-118">Use los campos **Fecha inicial** y **Fecha final** para definir el periodo al que se aplica el umbral.</span><span class="sxs-lookup"><span data-stu-id="879b5-118">Use the **From date** and **To date** fields to define the period that the threshold is applicable to.</span></span>
9. <span data-ttu-id="879b5-119">En la ficha desplegable **General**, en el campo **Umbral**, introduzca la cantidad de umbral que se utiliza para calcular los TDS para el componente de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-119">On the **General** FastTab, in the **Threshold** field, enter the threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="879b5-120">El impuesto se deducirá en el origen solo cuando el importe acumulado de la factura supere el umbral.</span><span class="sxs-lookup"><span data-stu-id="879b5-120">The tax will be deducted at the source only when the cumulative invoice amount crosses the threshold.</span></span>

    <span data-ttu-id="879b5-121">Por ejemplo, si el importe del umbral es 10 000, los TDS se calculan después de que el importe acumulado de la factura exceda 10 000 (en otras palabras, cuando es 10 001 o más).</span><span class="sxs-lookup"><span data-stu-id="879b5-121">For example, if the threshold amount is 10,000, TDS is calculated after the cumulative invoice amount exceeds 10,000 (in other words, when it's 10,001 or more).</span></span>

10. <span data-ttu-id="879b5-122">En el campo **Umbral de excepción**, introduzca el importe de umbral de excepción que se utiliza para calcular los TDS para el componente de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-122">In the **Exception threshold** field, enter the exception threshold amount that is used to calculate TDS for the TDS component.</span></span> <span data-ttu-id="879b5-123">El impuesto de una línea de factura se deducirá en el origen solo cuando el importe supere el umbral de excepción.</span><span class="sxs-lookup"><span data-stu-id="879b5-123">The tax on an invoice line will be deducted at the source only when the amount crosses the exception threshold.</span></span>

    <span data-ttu-id="879b5-124">Por ejemplo, si el importe del umbral de excepción es 5000, los TDS se calculan en una línea de factura específica si el importe de la línea de factura excede 5000 (en otras palabras, si es 5001 o más).</span><span class="sxs-lookup"><span data-stu-id="879b5-124">For example, if the exception threshold amount is 5,000, TDS is calculated on a specific invoice line if the invoice line amount exceeds 5,000 (in other words, if it's 5,001 or more).</span></span>

    <span data-ttu-id="879b5-125">[![Página de umbral](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span><span class="sxs-lookup"><span data-stu-id="879b5-125">[![Threshold page](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="879b5-126">El importe del umbral de excepción debe ser menor o igual al importe del umbral.</span><span class="sxs-lookup"><span data-stu-id="879b5-126">The exception threshold amount must be less than or equal to the threshold amount.</span></span>
    >
    > <span data-ttu-id="879b5-127">El impuesto se deduce de una transacción si el importe de la transacción cruza el umbral de excepción, incluso si el importe de la factura acumulada no cruza el umbral que se especifica en el campo **Umbral**.</span><span class="sxs-lookup"><span data-stu-id="879b5-127">The tax is deducted for a transaction if the transaction amount crosses the exception threshold, even if the cumulative invoice amount doesn't cross the threshold that is specified in the **Threshold** field.</span></span>

11. <span data-ttu-id="879b5-128">Cierre la página **Umbral** para volver a la página **Componentes de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="879b5-128">Close the **Threshold** page to return to the **Withholding tax components** page.</span></span>
12. <span data-ttu-id="879b5-129">En el panel de acciones, seleccione **Copiar** para abrir el cuadro de diálogo **Copiar componentes de retención de impuestos**, así podrá copiar los componentes de TDS que se configuraron para un grupo de componentes de TDS a otro grupo de componentes de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-129">On the Action Pane, select **Copy** to open the **Copy withholding tax components** dialog box, so that you can copy the TDS components that were set up for one TDS component group to another TDS component group.</span></span>
13. <span data-ttu-id="879b5-130">En el campo **Desde**, seleccione el grupo de componentes de TDS desde el que copiar los componentes de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-130">In the **From** field, select the TDS component group to copy the TDS components from.</span></span> <span data-ttu-id="879b5-131">En el campo **Hasata**, seleccione el grupo de componentes de retención de impuestos al que copiar los componentes de TDS.</span><span class="sxs-lookup"><span data-stu-id="879b5-131">In the **To** field, select the withholding tax component group to copy the TDS components to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="879b5-132">Los componentes de TDS comunes que se adjuntan a ambos grupos de componentes de TDS no se copian.</span><span class="sxs-lookup"><span data-stu-id="879b5-132">Common TDS components that are attached to both TDS component groups aren't copied.</span></span>

14. <span data-ttu-id="879b5-133">Seleccione **Aceptar** para copiar y crear componentes de TDS para el otro grupo de componentes de TDS en la página **Componentes de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="879b5-133">Select **OK** to copy and create TDS components for the other TDS component group on the **Withholding tax components** page.</span></span>

    <span data-ttu-id="879b5-134">[![Cuadro de diálogo Copiar componentes de retención de impuestos](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span><span class="sxs-lookup"><span data-stu-id="879b5-134">[![Copy withholding tax components dialog box](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)</span></span>

15. <span data-ttu-id="879b5-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="879b5-135">Close the page.</span></span>

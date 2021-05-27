---
title: Adjuntar códigos de impuestos de TDS a grupos de impuestos de TDS y definir la fórmula para calcular TDS
description: Este tema explica cómo configurar grupos de impuestos con impuestos deducidos en el origen (TDS) y adjuntar códigos de impuestos TDS a grupos de impuestos TDS. Para calcular TDS para un grupo de impuestos TDS, debe definir la fórmula para los códigos de impuestos TDS que se le adjuntan.
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
ms.openlocfilehash: ec0d683153bd5ab731035159d32881fbdb352d70
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023577"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a><span data-ttu-id="eec41-104">Adjuntar códigos de impuestos de TDS a grupos de impuestos de TDS y definir la fórmula para calcular TDS</span><span class="sxs-lookup"><span data-stu-id="eec41-104">Attach TDS tax codes to TDS tax groups and define the formula for calculating TDS</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eec41-105">Este tema explica cómo configurar grupos de impuestos con impuestos deducidos en el origen (TDS) y adjuntar códigos de impuestos TDS a grupos de impuestos TDS.</span><span class="sxs-lookup"><span data-stu-id="eec41-105">This topic explains how to set up Tax Deducted at Source (TDS) tax groups and attach TDS tax codes to TDS tax groups.</span></span> <span data-ttu-id="eec41-106">Para calcular TDS para un grupo de impuestos TDS, debe definir la fórmula para los códigos de impuestos TDS que se le adjuntan.</span><span class="sxs-lookup"><span data-stu-id="eec41-106">To calculate TDS for a TDS tax group, you must define the formula for TDS tax codes that are attached to it.</span></span>

<span data-ttu-id="eec41-107">Siga estos pasos para configurar un grupo de impuestos TDS, adjuntarle códigos de impuestos TDS y definir la fórmula para calcular TDS.</span><span class="sxs-lookup"><span data-stu-id="eec41-107">Follow these steps to set up a TDS tax group, attach TDS tax codes to it, and define the formula for calculating TDS.</span></span>

1. <span data-ttu-id="eec41-108">Vaya a **Impuestos \> Impuestos indirectos \> Retención de impuestos \> Grupos de retenciones de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="eec41-108">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax groups**.</span></span>

    <span data-ttu-id="eec41-109">[![Página de grupos de retenciones de impuestos](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span><span class="sxs-lookup"><span data-stu-id="eec41-109">[![Withholding tax groups page](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)</span></span>

2. <span data-ttu-id="eec41-110">En el panel de acciones, seleccione **Nuevo** para crear un grupo de retención de impuestos para TDS e introduzca los detalles requeridos.</span><span class="sxs-lookup"><span data-stu-id="eec41-110">On the Action Pane, select **New** to create a withholding tax group for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="eec41-111">En el campo **Tipo de impuesto**, seleccione **TDS**.</span><span class="sxs-lookup"><span data-stu-id="eec41-111">In the **Tax type** field, select **TDS**.</span></span>
4. <span data-ttu-id="eec41-112">En la ficha desplegable **Configuración**, seleccione **Agregar** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="eec41-112">On the **Setup** FastTab, select **Add** to create a line.</span></span>
5. <span data-ttu-id="eec41-113">En el campo **Código de retención de impuestos**, seleccione el código de impuestos de TDS para el grupo de impuestos de TDS.</span><span class="sxs-lookup"><span data-stu-id="eec41-113">In the **Withholding tax code** field, select the TDS tax code for the TDS tax group.</span></span> <span data-ttu-id="eec41-114">El campo de **Nombre de retención de impuestos** muestra el nombre del código de impuestos TDS y el campo **Valor** muestra el valor.</span><span class="sxs-lookup"><span data-stu-id="eec41-114">The **Withholding tax name** field shows the name of the TDS tax code, and the **Value** field shows the value.</span></span>
6. <span data-ttu-id="eec41-115">Para ignorar el límite de umbral y el límite de umbral de excepción que se definen para el componente de impuestos de TDS que se adjunta al código de impuestos de TDS en las transacciones de TDS, seleccione la casilla **Omitir el umbral**.</span><span class="sxs-lookup"><span data-stu-id="eec41-115">To ignore the threshold limit and exception threshold limit that are defined for the TDS tax component that is attached to the TDS tax code in TDS transactions, select the **Overlook threshold** check box.</span></span>
7. <span data-ttu-id="eec41-116">Para evitar que el grupo de impuestos se calcule en las transacciones, seleccione la casilla **Exento**.</span><span class="sxs-lookup"><span data-stu-id="eec41-116">To prevent the tax group from being calculated in transactions, select the **Exempt** check box.</span></span>
8. <span data-ttu-id="eec41-117">En el panel de acciones, seleccione **Diseñador** para abrir el diseñador de fórmulas, de modo que pueda definir la fórmula para calcular TDS para el grupo de impuestos TDS.</span><span class="sxs-lookup"><span data-stu-id="eec41-117">On the Action Pane, select **Designer** to open the formula designer, so that you can define the formula for calculating TDS for the TDS tax group.</span></span> <span data-ttu-id="eec41-118">En la página **Diseñador**, la pestaña **Impuestos** muestra los códigos de impuestos de TDS que se han seleccionado para el grupo de impuestos de TDS.</span><span class="sxs-lookup"><span data-stu-id="eec41-118">On the **Designer** page, the **Taxes** tab shows the TDS tax codes that have been selected for the TDS tax group.</span></span>

    <span data-ttu-id="eec41-119">[![Página de diseñador](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span><span class="sxs-lookup"><span data-stu-id="eec41-119">[![Designer page](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)</span></span>

9. <span data-ttu-id="eec41-120">En la pestaña **Cálculo**, seleccione **Alt + N** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="eec41-120">On the **Calculation** tab, select **Alt+N** to create a line.</span></span> <span data-ttu-id="eec41-121">El campo **Id.** muestra el Id. de prioridad generado automáticamente para el cálculo de TDS.</span><span class="sxs-lookup"><span data-stu-id="eec41-121">The **ID** field shows the automatically generated priority ID for TDS calculation.</span></span>
10. <span data-ttu-id="eec41-122">En el campo **Código de impuestos**, seleccione el código de impuestos de TDS para el que quiere definir la fórmula.</span><span class="sxs-lookup"><span data-stu-id="eec41-122">In the **Tax code** field, select the TDS tax code to define the formula for.</span></span> <span data-ttu-id="eec41-123">Todos los códigos de impuestos de TDS que se han seleccionado para el grupo de impuestos de TDS están disponibles para su selección en este campo.</span><span class="sxs-lookup"><span data-stu-id="eec41-123">All the TDS tax codes that have been selected for the TDS tax group are available for selection in this field.</span></span>
11. <span data-ttu-id="eec41-124">En el campo **Base imponible**, seleccione la base para calcular TDS:</span><span class="sxs-lookup"><span data-stu-id="eec41-124">In the **Taxable basis** field, select the basis for calculating TDS:</span></span>

    - <span data-ttu-id="eec41-125">**Importe bruto**: calcule el TDS en función del importe bruto de la transacción (es decir, el importe de la factura) mediante la expresión de cálculo que se define para el código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="eec41-125">**Gross amount** – Calculate TDS based on the gross transaction amount (that is, the invoice amount) by using the calculation expression that is defined for the tax code.</span></span>
    - <span data-ttu-id="eec41-126">**Importe bruto excluido**: calcule TDS en función de la expresión de cálculo que se define para el código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="eec41-126">**Excl Gross amount** – Calculate TDS based on the calculation expression that is defined for the tax code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eec41-127">El campo **Base imponible** no se puede establecer en **Importe bruto excluido** para el código de impuestos TDS que tiene un Id. de prioridad de **1**.</span><span class="sxs-lookup"><span data-stu-id="eec41-127">The **Taxable basis** field can't be set to **Excl Gross amount** for the TDS tax code that has a priority ID of **1**.</span></span>

12. <span data-ttu-id="eec41-128">El cálculo de TDS se basa en la fórmula que se define en el campo **Expresión de cálculo** para cada código de impuestos que se adjunta al grupo de impuestos TDS.</span><span class="sxs-lookup"><span data-stu-id="eec41-128">The TDS calculation is based on the formula that is defined in the **Calculation expression** field for each tax code that is attached to the TDS tax group.</span></span> <span data-ttu-id="eec41-129">Seleccione el signo más (**+**), signo menos (**-**), signo de multiplicación (**\**_) o el signo de división (_*/**) para introducir la expresión de cálculo para el código de impuestos TDS seleccionado en el campo **Expresión de cálculo**.</span><span class="sxs-lookup"><span data-stu-id="eec41-129">Select the plus sign (**+**), minus sign (**-**), multiplication sign (**\**_), or division sign (_*/**) button to enter the calculation expression for the selected TDS tax code in the **Calculation expression** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eec41-130">No se puede definir ninguna expresión de cálculo para el código de impuestos TDS que tiene un Id. de prioridad de **1**.</span><span class="sxs-lookup"><span data-stu-id="eec41-130">No calculation expression can be defined for the TDS tax code that has a priority ID of **1**.</span></span>

13. <span data-ttu-id="eec41-131">Para definir la expresión de cálculo para el código de impuestos TDS en el campo **Expresión de cálculo**, agregue los códigos de impuestos TDS que están disponibles en la pestaña **Impuestos**. Para agregar códigos de impuestos TDS en el campo **Expresión de cálculo**, puede utilizar cualquiera de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="eec41-131">To define the calculation expression for the TDS tax code in the **Calculation expression** field, add TDS tax codes that are available on the **Taxes** tab. To add TDS tax codes in the **Calculation expression** field, you can use any of the following methods:</span></span>

    - <span data-ttu-id="eec41-132">Arrastre el código de impuestos requerido de la pestaña **Impuestos** al campo **Expresión de cálculo**.</span><span class="sxs-lookup"><span data-stu-id="eec41-132">Drag the required tax code from the **Taxes** tab to the **Calculation expression** field.</span></span>
    - <span data-ttu-id="eec41-133">Toque dos veces (o haga doble clic) en el código de impuestos requerido en la pestaña **Impuestos**.</span><span class="sxs-lookup"><span data-stu-id="eec41-133">Double-tap (or double-click) the required tax code on the **Taxes** tab.</span></span>
    - <span data-ttu-id="eec41-134">Seleccione y mantenga presionado (o haga clic con el botón derecho) el código de impuestos requerido en la pestaña **Impuestos** y luego seleccione **Agregar código de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="eec41-134">Select and hold (or right-click) the required tax code on the **Taxes** tab, and then select **Add tax code**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eec41-135">Inserte una expresión de cálculo antes de cada código de impuestos TDS.</span><span class="sxs-lookup"><span data-stu-id="eec41-135">Insert a calculation expression before each TDS tax code.</span></span> <span data-ttu-id="eec41-136">Los códigos de impuestos TDS que se han agregado a la expresión de cálculo aparecen entre paréntesis (\[...\]).</span><span class="sxs-lookup"><span data-stu-id="eec41-136">The TDS tax codes that have been added to the calculation expression appear in brackets (\[...\]).</span></span>

14. <span data-ttu-id="eec41-137">Para borrar la expresión de cálculo definida para un código de impuestos en el campo **Expresión de cálculo**, seleccione el botón **C**.</span><span class="sxs-lookup"><span data-stu-id="eec41-137">To clear the calculation expression that is defined for a tax code in the **Calculation expression** field, select the **C** button.</span></span>
15. <span data-ttu-id="eec41-138">Para eliminar un registro en la pestaña **Cálculo**, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="eec41-138">To delete a record on the **Calculation** tab, select **Delete**.</span></span>
16. <span data-ttu-id="eec41-139">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="eec41-139">Close the page.</span></span>

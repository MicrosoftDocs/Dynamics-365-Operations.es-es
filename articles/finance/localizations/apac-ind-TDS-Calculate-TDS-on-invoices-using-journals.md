---
title: Calcular TDS en facturas usando diarios
description: Este tema enumera los pasos para calcular los impuestos deducidos en el origen (TDS) en diarios.
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
ms.openlocfilehash: d68e1b3a4dc31823ec56a525149f16bdc23c0883
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023582"
---
# <a name="calculate-tds-on-invoices-using-journals"></a><span data-ttu-id="0b69c-103">Calcular TDS en facturas usando diarios</span><span class="sxs-lookup"><span data-stu-id="0b69c-103">Calculate TDS on invoices using journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b69c-104">Este tema enumera los pasos para calcular los impuestos deducidos en el origen (TDS) en diarios.</span><span class="sxs-lookup"><span data-stu-id="0b69c-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on journals.</span></span>

<span data-ttu-id="0b69c-105">Empiece por abrir la página **Diarios generales** (**Contabilidad general > Entradas del diario > Diarios generales**).</span><span class="sxs-lookup"><span data-stu-id="0b69c-105">Begin by opening the **General journals** page (**General ledger > Journal entries > General journals**).</span></span>

<span data-ttu-id="0b69c-106">[![Diarios generales](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span><span class="sxs-lookup"><span data-stu-id="0b69c-106">[![General journals](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span></span>

1. <span data-ttu-id="0b69c-107">Cree líneas de diario utilizando los formularios de diario que se enumeran en la tabla.</span><span class="sxs-lookup"><span data-stu-id="0b69c-107">Create journal lines using the journal forms that are listed in the table.</span></span> <span data-ttu-id="0b69c-108">Seleccione el tipo de cuenta y el tipo de cuenta de contrapartida e introduzca el importe de la transacción.</span><span class="sxs-lookup"><span data-stu-id="0b69c-108">Select the account type and offset account type and enter the amount for the transaction.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="0b69c-109">En la página **Diario de aprobación de facturas**, seleccione **Encontrar asientos** y seleccione facturas para calcular TDS.</span><span class="sxs-lookup"><span data-stu-id="0b69c-109">On the **Invoice approval journal** page, select **Find vouchers** and select invoices to calculate TDS on.</span></span> <span data-ttu-id="0b69c-110">Consulte las facturas creadas en la página **Registro de facturas** o en la página **Econtrar asientos**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-110">View the invoices created in the **Invoice register** page or the **Find vouchers** page.</span></span>  

2. <span data-ttu-id="0b69c-111">En la pestaña **General** de la página **Asiento del diario**, consulte o modifique el grupo TDS predeterminado definido para el proveedor o cliente en el campo **Grupo TDS**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-111">On the **General** tab of the **Journal voucher** page, view or modify the default TDS group defined for the vendor or customer, in the **TDS group** field.</span></span> <span data-ttu-id="0b69c-112">El importe de TDS que se calcula en las líneas de diario se basa en la fórmula definida para los códigos de impuestos de TDS que se enumeran en el campo **Grupo TDS**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-112">The TDS amount that's calculated on journal lines is based on the formula defined for the TDS tax codes listed in the **TDS group** field.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="0b69c-113">El campo **Grupo de retención de impuestos** y el campo **Grupo TCS** no están disponibles cuando selecciona un grupo TDS en el campo **Grupo TDS**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-113">The **Withholding tax group**  field and the **TCS group** field become unavailable when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="0b69c-114">El campo **Grupo de retención de impuestos** está disponible solo en la página **Diario general**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-114">The **Withholding tax group** field is available only on the **General journal** page.</span></span> <span data-ttu-id="0b69c-115">Los TDS se calculan solo si se ha seleccionado la casilla **Calcular retención de impuestos** para el proveedor o cliente en las páginas **Todos los proveedores** o **Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-115">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** pages.</span></span>   

3. <span data-ttu-id="0b69c-116">Seleccione la pestaña **Información de impuestos**. Seleccione direcciones alternativas de una empresa que estén configuradas para la empresa en este campo si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="0b69c-116">Select the **Tax information** tab. Select the alternate addresses of a company that's set up for the company in this field, if required.</span></span> <span data-ttu-id="0b69c-117">Puede ver el nombre de la empresa en el campo **Nombre**, que está en el grupo de campo **Información de la empresa**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-117">You can view the company name in the **Name** field, which is under the **Company information** field group.</span></span> 

4. <span data-ttu-id="0b69c-118">Consulte la naturaleza de la categoría del evaluado del proveedor o cliente en el campo **Naturaleza del evaluado**, que está en el grupo de campo **Retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-118">View the nature of assessee category of the vendor or customer in the **Nature of assessee** field, which is under the **Withholding tax** field group.</span></span> <span data-ttu-id="0b69c-119">En el campo **Número de cuenta de impuestos** (**TAN**), consulte el TAN del nombre de la empresa seleccionada que se muestra.</span><span class="sxs-lookup"><span data-stu-id="0b69c-119">In the **Tax Account Number** (**TAN**) field, view the TAN of the selected company name that's displayed.</span></span>  

5. <span data-ttu-id="0b69c-120">Seleccione **Retención de impuestos** en el menú **Retención de impuestos** para abrir la página **Transacciones de retención temporal de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-120">Select **Withholding tax** in **Withholding tax** menu to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="0b69c-121">Se muestran los siguientes campos en el panel superior de la página **Transacciones de retención temporal de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-121">The following fields are displayed on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="0b69c-122">**Retención de importe total de impuestos**: el total de TDS calculado para la transacción para el grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="0b69c-122">**Withholding tax amount in total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="0b69c-123">**Valor**: el porcentaje total utilizado para calcular TDS para la transacción.</span><span class="sxs-lookup"><span data-stu-id="0b69c-123">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="0b69c-124">El porcentaje total se basa en la fórmula que se define para los códigos de impuestos TDS adjuntos al grupo TDS.</span><span class="sxs-lookup"><span data-stu-id="0b69c-124">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="0b69c-125">**Importe total de la retención de impuestos ajustada**: el importe total de TDS ajustado para todos los códigos de impuestos en el grupo TDS.</span><span class="sxs-lookup"><span data-stu-id="0b69c-125">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="0b69c-126">**TDS**: si se selecciona, se adjunta un grupo de TDS a la transacción.</span><span class="sxs-lookup"><span data-stu-id="0b69c-126">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

  <span data-ttu-id="0b69c-127">Los campos en las pestañas **Información general**, **General** y **Ajuste** en la página **Transacciones de retención temporal de impuestos** muestra la cantidad de TDS calculada y los detalles de la cantidad de TDS ajustada para cada código de impuestos de TDS adjunto al grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="0b69c-127">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

6. <span data-ttu-id="0b69c-128">Seleccione **Umbral** para abrir la página **Umbral**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-128">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="0b69c-129">Consulte el límite de umbral y el límite de umbral de excepción definidos para el componente de impuestos de TDS adjunto a un código de impuestos de TDS específico en esta página.</span><span class="sxs-lookup"><span data-stu-id="0b69c-129">View the threshold limit and exception threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

   <span data-ttu-id="0b69c-130">Seleccione **Diseñador de fórmulas** para abrir el formulario **Diseñador de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-130">Select **Formula designer** to open the **Formula designer** form.</span></span> <span data-ttu-id="0b69c-131">Consulte la fórmula definida para un código de impuestos TDS específico en esta página.</span><span class="sxs-lookup"><span data-stu-id="0b69c-131">View the formula defined for a specific TDS tax code in this page.</span></span> <span data-ttu-id="0b69c-132">Cierre las páginas **Diseñador de fórmulas** y **Transacciones de retención temporal de impuestos** para volver a la página **Asiento del diario**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-132">Close the **Formula designer** and **Temporary withholding tax transactions** pages to return to the **Journal voucher** page.</span></span>

8. <span data-ttu-id="0b69c-133">Especifique los otros detalles.</span><span class="sxs-lookup"><span data-stu-id="0b69c-133">Enter the other required details.</span></span> <span data-ttu-id="0b69c-134">Valide y registre el diario.</span><span class="sxs-lookup"><span data-stu-id="0b69c-134">Validate and post the journal.</span></span> <span data-ttu-id="0b69c-135">La cantidad de TDS que se calcula en las facturas de compra se registra en la cuenta de proveedor.</span><span class="sxs-lookup"><span data-stu-id="0b69c-135">The TDS amount that's calculated on purchase invoices is posted to the payable account.</span></span> <span data-ttu-id="0b69c-136">El importe de TDS que se calcula en las facturas de ventas se registra en la cuenta de cliente que se define para cada código de impuestos de TDS en el grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="0b69c-136">The TDS amount that's calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="0b69c-137">Las cuentas de proveedores o de clientes para los códigos de impuestos TDS se definen en la página **Códigos de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-137">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

9. <span data-ttu-id="0b69c-138">Seleccione **Retención de impuestos registrados** para abrir la página **Transacciones** **de retención** **de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-138">Select **Posted withholding tax** to open the **Withholding** **tax** **transactions** page.</span></span> <span data-ttu-id="0b69c-139">Puede ver el porcentaje total utilizado para calcular TDS para la transacción en el campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="0b69c-139">In the **Value** field, the total percentage used to calculate TDS for the transaction is displayed.</span></span>

   <span data-ttu-id="0b69c-140">Los campos en las pestañas **Información general**, **General** e **Importe** en la página Transacciones de retención de impuestos muestran la cantidad de TDS calculada y los detalles de la cantidad de TDS ajustada para cada código de impuestos de TDS adjunto al grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="0b69c-140">The fields on the **Overview**, **General**, and **Amount** tabs in the Withholding tax transactions page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

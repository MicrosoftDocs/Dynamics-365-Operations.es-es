---
title: Retirar un activo fijo como desechado
description: El tema describe el proceso de eliminar transacciones para un activo fijo que se ha desechado como residuo.
author: moaamer
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 371cc2efa64916698da8e4230825c3c949920698
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975253"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a><span data-ttu-id="db769-103">Retirar un activo fijo como desechado</span><span class="sxs-lookup"><span data-stu-id="db769-103">Dispose of a fixed asset as scrap</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db769-104">El tema describe el proceso de eliminar transacciones para un activo fijo que se ha desechado como residuo.</span><span class="sxs-lookup"><span data-stu-id="db769-104">The topic describes the process of eliminating transactions for a fixed asset that was disposed of as scrap.</span></span> <span data-ttu-id="db769-105">Los tipos de transacción que se pueden eliminar incluyen la adquisición de un activo y las transacciones de depreciación acumuladas y otras transacciones de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="db769-105">The transaction types that can be eliminated include an asset's acquisition and accumulated depreciation transactions and other fixed asset transactions.</span></span> <span data-ttu-id="db769-106">La eliminación de estas transacciones afecta a las cuentas de balance de situación, como el ajuste de adquisición, el ajuste de depreciación, la revalorización, y las cuentas de revalorización y de devaluación.</span><span class="sxs-lookup"><span data-stu-id="db769-106">Elimination of these transactions affects balance sheet accounts, such as acquisition adjustment, depreciation adjustment, revaluation, write-up, and write-down accounts.</span></span>

| <span data-ttu-id="db769-107">Transacción</span><span class="sxs-lookup"><span data-stu-id="db769-107">Transaction</span></span>                                         | <span data-ttu-id="db769-108">Débito (Dr.)</span><span class="sxs-lookup"><span data-stu-id="db769-108">Debit (Dr.)</span></span> | <span data-ttu-id="db769-109">Crédito (Cr.)</span><span class="sxs-lookup"><span data-stu-id="db769-109">Credit (Cr.)</span></span> |
|-----------------------------------------------------|-------------|--------------|
| <span data-ttu-id="db769-110">Depreciación acumulada Dr.</span><span class="sxs-lookup"><span data-stu-id="db769-110">Dr. Accumulated depreciation</span></span>                        | <span data-ttu-id="db769-111">X</span><span class="sxs-lookup"><span data-stu-id="db769-111">X</span></span>           |              |
| <span data-ttu-id="db769-112">Ganancia/pérdida de activos fijos cr.</span><span class="sxs-lookup"><span data-stu-id="db769-112">Cr. Fixed assets gain/loss</span></span>                          |             | <span data-ttu-id="db769-113">X</span><span class="sxs-lookup"><span data-stu-id="db769-113">X</span></span>            |
| <span data-ttu-id="db769-114">Ganancia/pérdida de activos fijos dr.</span><span class="sxs-lookup"><span data-stu-id="db769-114">Dr. Fixed assets gain/loss</span></span>                          | <span data-ttu-id="db769-115">X</span><span class="sxs-lookup"><span data-stu-id="db769-115">X</span></span>           |              |
| <span data-ttu-id="db769-116">Cuenta de adquisición de activos fijos cr.</span><span class="sxs-lookup"><span data-stu-id="db769-116">Cr. Fixed asset acquisition account</span></span>                 |             | <span data-ttu-id="db769-117">X</span><span class="sxs-lookup"><span data-stu-id="db769-117">X</span></span>            |
| <span data-ttu-id="db769-118">Ganancia/Pérdida de activos fijos dr. (valor neto en los libros \[NBV\])</span><span class="sxs-lookup"><span data-stu-id="db769-118">Dr. Fixed assets gain/loss (net book value \[NBV\])</span></span> | <span data-ttu-id="db769-119">X</span><span class="sxs-lookup"><span data-stu-id="db769-119">X</span></span>           |              |
| <span data-ttu-id="db769-120">Ganancia/pérdida de activos fijos cr. (NBV)</span><span class="sxs-lookup"><span data-stu-id="db769-120">Cr. Fixed assets gain/loss (NBV)</span></span>                    |             | <span data-ttu-id="db769-121">X</span><span class="sxs-lookup"><span data-stu-id="db769-121">X</span></span>            |

> [!NOTE]
> <span data-ttu-id="db769-122">Recomendamos que trabaje estrechamente con el director financiero (CFO) de su empresa o controlador para identificar las cuentas correctas que se deben usar para cada tipo de transacción, y para comprobarlas que el proceso de desecho y las transacciones que genera actualiza dichas cuentas correctamente.</span><span class="sxs-lookup"><span data-stu-id="db769-122">We recommend that you work closely with your company's chief financial officer (CFO) or controller to identify the correct accounts that should be used for each transaction type, and also to verify that the disposal process and the transactions that it generates update those accounts correctly.</span></span>

<span data-ttu-id="db769-123">Antes de desechar un activo fijo como residuo, debe crear cuentas contables asociadas al valor de adquisición del activo, la depreciación durante del año actual, la depreciación de los años anteriores, y el NBV del activo.</span><span class="sxs-lookup"><span data-stu-id="db769-123">Before you dispose of a fixed asset as scrap, you must create ledger accounts that are associated with the asset's acquisition value, depreciation for the current year, depreciation for previous years, and the asset's NBV.</span></span> <span data-ttu-id="db769-124">Los tipos de transacción de activos fijos figuran en la página **Perfil de contabilización de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="db769-124">The fixed asset transaction types are listed on the **Fixed assets posting profile** page.</span></span> <span data-ttu-id="db769-125">Vaya a **Activos fijos \> Configuración \> Perfiles de contabilización de activos fijos** y, en la ficha desplegable **Cancelación**, seleccione **Residuo** en el campo que está encima de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="db769-125">Go to **Fixed assets \> Setup \> Fixed asset posting profiles**, and then, on the **Disposal** FastTab, select **Scrap** in the field above the grid.</span></span> <span data-ttu-id="db769-126">La ilustración siguiente muestra la lista de tipos de transacciones de activos fijos en la página **Perfiles de contabilización de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="db769-126">The following illustration shows the list of fixed asset transaction types on the **Fixed asset posting profiles** page.</span></span>


<span data-ttu-id="db769-127">[![Desechar un activo como residuo, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span><span class="sxs-lookup"><span data-stu-id="db769-127">[![Disposing of an asset as scap, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span></span>

<span data-ttu-id="db769-128">Para el siguiente ejemplo, un activo fijo se adquirió el 1 de enero de 2018, y se dará de baja el 31 de marzo de 2019.</span><span class="sxs-lookup"><span data-stu-id="db769-128">For the following example, a fixed asset was acquired on January 1, 2018, and it will be scrapped on March 31, 2019.</span></span>

- <span data-ttu-id="db769-129">**Precio de adquisición:** 24.000,00 Dólares estadounidenses (USD)</span><span class="sxs-lookup"><span data-stu-id="db769-129">**Acquisition price:** 24,000.00 US dollars (USD)</span></span>
- <span data-ttu-id="db769-130">**Tiempo de vida:** dos años</span><span class="sxs-lookup"><span data-stu-id="db769-130">**Service life:** Two years</span></span>
- <span data-ttu-id="db769-131">**método de depreciación**: vida de servicio de depreciación lineal</span><span class="sxs-lookup"><span data-stu-id="db769-131">**Depreciation method:** Straight line service life</span></span>
- <span data-ttu-id="db769-132">**Importe de depreciación:** 1000,00 USD por mes</span><span class="sxs-lookup"><span data-stu-id="db769-132">**Depreciation amount:** 1,000.00 USD per month</span></span>

<span data-ttu-id="db769-133">El NBV de un activo fijo se calcula mediante la fórmula siguiente:</span><span class="sxs-lookup"><span data-stu-id="db769-133">The NBV of a fixed asset is calculated by using the following formula:</span></span>

<span data-ttu-id="db769-134">Valor neto en los libros = Precio de adquisición – depreciación</span><span class="sxs-lookup"><span data-stu-id="db769-134">Net book value = Acquisition price – Depreciation</span></span>

<span data-ttu-id="db769-135">En este ejemplo, se adquirió el activo fijo y se depreció durante 15 meses, de enero de 2018 a marzo de 2019.</span><span class="sxs-lookup"><span data-stu-id="db769-135">In this example, the fixed asset was acquired and was depreciated for 15 months, from January 2018 through March 2019.</span></span> <span data-ttu-id="db769-136">Por lo tanto, el NBV del activo es 9000,00 USD (24.000,00 USD – 15.000,00 USD).</span><span class="sxs-lookup"><span data-stu-id="db769-136">Therefore, the asset's NBV is 9,000.00 USD (24,000.00 USD – 15,000.00 USD).</span></span>

<span data-ttu-id="db769-137">[![Ejemplo de depreciación para activos fijos](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span><span class="sxs-lookup"><span data-stu-id="db769-137">[![Fixed asset depreciation example](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span></span>


<span data-ttu-id="db769-138">Para crear un diario de cancelación, vaya a **Activos fijos \> Entradas de diario \> Diario de activos fijos**y, a continuación, en el panel de acciones, seleccione **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="db769-138">To create a disposal journal, go to **Fixed assets \> Journal entries \> Fixed assets journal**, and then, on the Action Pane, select **Lines**.</span></span> <span data-ttu-id="db769-139">Seleccione **Cancelación – residuos**, y a continuación, seleccione un identificador de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="db769-139">Select **Disposal – scrap**, and then select a fixed asset ID.</span></span> <span data-ttu-id="db769-140">Para cancelar completamente el activo, no inserte un valor en el campo **Débito** o el campo **Crédito** .</span><span class="sxs-lookup"><span data-stu-id="db769-140">To fully dispose of the asset, don't enter a value in either the **Debit** field or the **Credit** field.</span></span>

<span data-ttu-id="db769-141">[![Diario de activos fijos](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span><span class="sxs-lookup"><span data-stu-id="db769-141">[![Fixed assets journal](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span></span>

<span data-ttu-id="db769-142">La transacción de cancelación de activos fijos cambia los valores de campo del libro de activos fijos de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="db769-142">The fixed asset disposal scrap transaction changes the field values for the fixed asset book in the following ways:</span></span>

- <span data-ttu-id="db769-143">En la sección **Saldo** , el campo **Estado** se actualizará **Desechado**.</span><span class="sxs-lookup"><span data-stu-id="db769-143">In the **Balance** section, the **Status** field is updated to **Scrapped**.</span></span>
- <span data-ttu-id="db769-144">En la sección **Emisión** , el campo **Fecha de cancelación** se establece en la fecha en la que el activo se dio de baja.</span><span class="sxs-lookup"><span data-stu-id="db769-144">In the **Issue** section, the **Disposal date** field is set to the date when the asset was scrapped.</span></span>

<span data-ttu-id="db769-145">[![Detalle del diario de activos fijos](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span><span class="sxs-lookup"><span data-stu-id="db769-145">[![Fixed assets journal detail](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span></span>

<span data-ttu-id="db769-146">La ilustración siguiente muestra el saldo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="db769-146">The following illustration shows the fixed asset balance.</span></span>

<span data-ttu-id="db769-147">[![Saldo de activos fijos](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span><span class="sxs-lookup"><span data-stu-id="db769-147">[![Fixed asset balance](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span></span>

<span data-ttu-id="db769-148">La ilustración siguiente muestra el asiento que se registra.</span><span class="sxs-lookup"><span data-stu-id="db769-148">The following illustration shows the voucher that is posted.</span></span>

<span data-ttu-id="db769-149">[![Valor neto en los libros](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span><span class="sxs-lookup"><span data-stu-id="db769-149">[![Net book value](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span></span>

---
title: Establecer tipos de interés para un código de interés
description: Los códigos de interés contienen la configuración que determina si se carga el interés y cómo se calcula en las cuentas vencidas.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: roschlom
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d9ff856e34eb894c5d0ab5fe17c8e95f62fff57
ms.sourcegitcommit: 88babb2fffe97e93bbde543633fc492120f2a4fc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "5555374"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="7e46c-103">Establecer tipos de interés para un código de interés</span><span class="sxs-lookup"><span data-stu-id="7e46c-103">Set up interest rates for an interest code</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7e46c-104">Los códigos de interés contienen la configuración que determina si se carga el interés y cómo se calcula en las cuentas vencidas.</span><span class="sxs-lookup"><span data-stu-id="7e46c-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="7e46c-105">Puede configurar un único código de interés y aplicarlo a varios perfiles de registro de cliente, códigos de facturación o líneas de factura concretas.</span><span class="sxs-lookup"><span data-stu-id="7e46c-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="7e46c-106">Cuando se cambian los detalles del código de interés, todas las funciones que usan el código implementarán automáticamente los cambios en las nuevas transacciones.</span><span class="sxs-lookup"><span data-stu-id="7e46c-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="7e46c-107">Puede configurar dos tipos de índices para cada código de interés:</span><span class="sxs-lookup"><span data-stu-id="7e46c-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="7e46c-108">Índices para las ganancias por intereses: representan los ingresos obtenidos por cargar un interés en las facturas o notas de interés.</span><span class="sxs-lookup"><span data-stu-id="7e46c-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="7e46c-109">Índices para los pagos de interés: representan el coste pagado por el interés de las notas de abono.</span><span class="sxs-lookup"><span data-stu-id="7e46c-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="7e46c-110">Ambos tipos de índices pueden existir al mismo tiempo y en el mismo código de interés.</span><span class="sxs-lookup"><span data-stu-id="7e46c-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="7e46c-111">Los tipos de interés pueden basarse en tres tipos de cálculo:</span><span class="sxs-lookup"><span data-stu-id="7e46c-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="7e46c-112">Interés por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="7e46c-112">Interest by percentage.</span></span>
-   <span data-ttu-id="7e46c-113">Interés por importe.</span><span class="sxs-lookup"><span data-stu-id="7e46c-113">Interest by amount.</span></span>
-   <span data-ttu-id="7e46c-114">Interés por intervalo, lo que genera un único porcentaje o importe.</span><span class="sxs-lookup"><span data-stu-id="7e46c-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="7e46c-115">Si utiliza un código de interés para calcular el interés, se creará una nota de interés independiente para cada tipo de interés vigente durante el tiempo que el pago ha superado la fecha de vencimiento de la transacción.</span><span class="sxs-lookup"><span data-stu-id="7e46c-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="7e46c-116">Se usa la ficha **Ganancias** de la página **Código de Interés** para configurar los tipos de interés para la ganancia que se obtiene al cargar el interés.</span><span class="sxs-lookup"><span data-stu-id="7e46c-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="7e46c-117">Use la ficha **Pagos** para configurar los tipos de interés para el interés que usted paga.</span><span class="sxs-lookup"><span data-stu-id="7e46c-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="7e46c-118">Tipos de interés basados en porcentajes</span><span class="sxs-lookup"><span data-stu-id="7e46c-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="7e46c-119">Puede configurar los tipos de interés que calculan un porcentaje concreto.</span><span class="sxs-lookup"><span data-stu-id="7e46c-119">You can set up interest rates that calculate a specified percentage.</span></span>

- <span data-ttu-id="7e46c-120">El importe del interés se aplica a todas las divisas.</span><span class="sxs-lookup"><span data-stu-id="7e46c-120">Interest amount applies to all currencies.</span></span>
- <span data-ttu-id="7e46c-121">Se pueden especificar límites de interés opcionales.</span><span class="sxs-lookup"><span data-stu-id="7e46c-121">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="7e46c-122">**Porcentaje** se selecciona en el campo **Calcular el interés en función de**, en la página **Configurar códigos de interés**.</span><span class="sxs-lookup"><span data-stu-id="7e46c-122">**Percentage** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="7e46c-123">Por ejemplo, para configurar un código de interés que evalúe el 5 por ciento de interés por cada dos meses que el pago de la factura supere la fecha de vencimiento de la transacción, escriba 2 en el campo **Calcular interés cada** y seleccione **Mes**.</span><span class="sxs-lookup"><span data-stu-id="7e46c-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

> [!NOTE] 
> <span data-ttu-id="7e46c-124">El nuevo algoritmo para el cálculo de notas de interés se agrega mediante Administración de funciones.</span><span class="sxs-lookup"><span data-stu-id="7e46c-124">The new algorithm for interest note calculation is added using Feature management.</span></span> <span data-ttu-id="7e46c-125">Para utilizar este algoritmo, habilite la característica **(GBL) Permitir calcular el interés por día como porcentaje anual dividido por 365**.</span><span class="sxs-lookup"><span data-stu-id="7e46c-125">To use this algorithm, enable the **(GBL) Allow to calculate interest per day as yearly percent divided by 365** feature.</span></span> <span data-ttu-id="7e46c-126">Para obtener más información acerca de cómo habilitar la característica, consulte [Visión general de la administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7e46c-126">For information about how to enable the feature, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
> 
> <span data-ttu-id="7e46c-127">La fórmula para el cálculo del importe de la nota de interés es:</span><span class="sxs-lookup"><span data-stu-id="7e46c-127">The formula for the calculation for the interest note amount is:</span></span> 
>  
> <span data-ttu-id="7e46c-128">Importe de la nota de interés = Importe adeudado \* % de interés anual/365 \* Número de días de atraso</span><span class="sxs-lookup"><span data-stu-id="7e46c-128">Interest note amount = Amount owed \* Yearly interest % / 365 \* Number of days late</span></span>
>  
> <span data-ttu-id="7e46c-129">Esta característica está disponible en versión 10.0.18 o posterior.</span><span class="sxs-lookup"><span data-stu-id="7e46c-129">This feature is available in version 10.0.18 or later.</span></span>    
 
## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="7e46c-130">Tipos de interés basados en importes</span><span class="sxs-lookup"><span data-stu-id="7e46c-130">Interest rates based on amounts</span></span>
<span data-ttu-id="7e46c-131">Puede configurar los tipos de interés que calculan un importe concreto por divisa.</span><span class="sxs-lookup"><span data-stu-id="7e46c-131">You can set up interest rates that calculate a specified amount per currency.</span></span>
- <span data-ttu-id="7e46c-132">Se especifica un importe de interés para cada divisa en el código de interés.</span><span class="sxs-lookup"><span data-stu-id="7e46c-132">An interest amount is specified for each currency in the interest code.</span></span>
- <span data-ttu-id="7e46c-133">Se pueden especificar límites de interés opcionales.</span><span class="sxs-lookup"><span data-stu-id="7e46c-133">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="7e46c-134">**Porcentaje** se selecciona en el campo **Calcular el interés en función de** en la página **Configurar códigos de interés**.</span><span class="sxs-lookup"><span data-stu-id="7e46c-134">**Amount** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="7e46c-135">Por ejemplo, para configurar un código de interés que evalúe el interés de 25,00 por cada 20 días que el pago de la factura supere la fecha de vencimiento de la transacción, escriba 20 en el campo **Calcular interés cada** y seleccione **Día**.</span><span class="sxs-lookup"><span data-stu-id="7e46c-135">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="7e46c-136">Tipos de interés basados en intervalos</span><span class="sxs-lookup"><span data-stu-id="7e46c-136">Interest rates based on ranges</span></span>
<span data-ttu-id="7e46c-137">Puede configurar los tipos de interés que varían en función del importe vencido o el número de días o de meses que se retrasa el importe.</span><span class="sxs-lookup"><span data-stu-id="7e46c-137">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="7e46c-138">Puede usar la ficha **Ganancias por divisa** para definir los parámetros específicos del interés para cada divisa.</span><span class="sxs-lookup"><span data-stu-id="7e46c-138">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="7e46c-139">Aquí es también donde se define el intervalo.</span><span class="sxs-lookup"><span data-stu-id="7e46c-139">This is also where you will define the range.</span></span>
-   <span data-ttu-id="7e46c-140">Use el botón **Intervalos** para agregar las líneas que representan los intervalos que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="7e46c-140">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="7e46c-141">El valor **De** representa el principio del intervalo y el número **Valor de interés** representa un porcentaje o un importe, en función de la selección en el campo **Calcular el interés en función de** de la página **Configurar códigos de interés** .</span><span class="sxs-lookup"><span data-stu-id="7e46c-141">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="7e46c-142">Ejemplo 1: interés por intervalo = importe</span><span class="sxs-lookup"><span data-stu-id="7e46c-142">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="7e46c-143">Establezca el código de interés que evalúa el interés una vez por cada tres meses que el pago de la factura supere la fecha de vencimiento de la transacción.</span><span class="sxs-lookup"><span data-stu-id="7e46c-143">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="7e46c-144">Deberá basar el cálculo en un valor de interés de porcentaje, de acuerdo con los intervalos del importe escalonado.</span><span class="sxs-lookup"><span data-stu-id="7e46c-144">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="7e46c-145">El valor de interés será del 1 por ciento para los importes de factura de hasta 1.000,00, del 2 por ciento para los importes entre 1.001,00 y 5.000,00, y del 3 por ciento para los importes superiores a 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="7e46c-145">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="7e46c-146">Configure los valores del campo del código de interés de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7e46c-146">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="7e46c-147">**Nombre del campo**</span><span class="sxs-lookup"><span data-stu-id="7e46c-147">**Field name**</span></span>                  | <span data-ttu-id="7e46c-148">**Valor de campo**</span><span class="sxs-lookup"><span data-stu-id="7e46c-148">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="7e46c-149">**Código del interés**</span><span class="sxs-lookup"><span data-stu-id="7e46c-149">**Interest code**</span></span>               | <span data-ttu-id="7e46c-150">3M%PorCant</span><span class="sxs-lookup"><span data-stu-id="7e46c-150">3M%ByAmt</span></span>        |
| <span data-ttu-id="7e46c-151">**Calcular interés cada**</span><span class="sxs-lookup"><span data-stu-id="7e46c-151">**Calculate interest every**</span></span>    | <span data-ttu-id="7e46c-152">3/Mes</span><span class="sxs-lookup"><span data-stu-id="7e46c-152">3/Month</span></span>         |
| <span data-ttu-id="7e46c-153">**Interés por intervalo**</span><span class="sxs-lookup"><span data-stu-id="7e46c-153">**Interest by range**</span></span>           | <span data-ttu-id="7e46c-154">Importe</span><span class="sxs-lookup"><span data-stu-id="7e46c-154">Amount</span></span>          |
| <span data-ttu-id="7e46c-155">**Calcular el interés en función de**</span><span class="sxs-lookup"><span data-stu-id="7e46c-155">**Calculate interest based on**</span></span> | <span data-ttu-id="7e46c-156">Porcentaje</span><span class="sxs-lookup"><span data-stu-id="7e46c-156">Percentage</span></span>      |

<span data-ttu-id="7e46c-157">Configure la información del intervalo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7e46c-157">You set up the range information as follows.</span></span>

| <span data-ttu-id="7e46c-158">**Valor inicial**</span><span class="sxs-lookup"><span data-stu-id="7e46c-158">**From value**</span></span> | <span data-ttu-id="7e46c-159">**Valor del interés**</span><span class="sxs-lookup"><span data-stu-id="7e46c-159">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="7e46c-160">0</span><span class="sxs-lookup"><span data-stu-id="7e46c-160">0</span></span>              | <span data-ttu-id="7e46c-161">1</span><span class="sxs-lookup"><span data-stu-id="7e46c-161">1</span></span>                  |
| <span data-ttu-id="7e46c-162">1,001</span><span class="sxs-lookup"><span data-stu-id="7e46c-162">1,001</span></span>          | <span data-ttu-id="7e46c-163">2</span><span class="sxs-lookup"><span data-stu-id="7e46c-163">2</span></span>                  |
| <span data-ttu-id="7e46c-164">5,001</span><span class="sxs-lookup"><span data-stu-id="7e46c-164">5,001</span></span>          | <span data-ttu-id="7e46c-165">3</span><span class="sxs-lookup"><span data-stu-id="7e46c-165">3</span></span>                  |


## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="7e46c-166">Ejemplo 2: interés por intervalo = días</span><span class="sxs-lookup"><span data-stu-id="7e46c-166">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="7e46c-167">Establezca el código de interés que evalúa el interés una vez por cada 15 días que el pago de la factura supere la fecha de vencimiento de la transacción.</span><span class="sxs-lookup"><span data-stu-id="7e46c-167">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="7e46c-168">Deberá basar el cálculo en un valor de interés del importe, de acuerdo con los intervalos escalonados del día.</span><span class="sxs-lookup"><span data-stu-id="7e46c-168">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="7e46c-169">El valor del interés será de 10,00 por 15 días durante los primeros 60 días, de 15,00 por 15 días durante los días 61 a 90, y de 20,00 por 15 días a partir del día 91.</span><span class="sxs-lookup"><span data-stu-id="7e46c-169">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="7e46c-170">Configure los valores del campo del código de interés de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7e46c-170">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="7e46c-171">**Nombre del campo**</span><span class="sxs-lookup"><span data-stu-id="7e46c-171">**Field name**</span></span>                  | <span data-ttu-id="7e46c-172">**Valor de campo**</span><span class="sxs-lookup"><span data-stu-id="7e46c-172">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="7e46c-173">**Código del interés**</span><span class="sxs-lookup"><span data-stu-id="7e46c-173">**Interest code**</span></span>               | <span data-ttu-id="7e46c-174">15DCantXDía</span><span class="sxs-lookup"><span data-stu-id="7e46c-174">15DAmtXDay</span></span>      |
| <span data-ttu-id="7e46c-175">**Calcular interés cada**</span><span class="sxs-lookup"><span data-stu-id="7e46c-175">**Calculate interest every**</span></span>    | <span data-ttu-id="7e46c-176">15/Día</span><span class="sxs-lookup"><span data-stu-id="7e46c-176">15/Day</span></span>          |
| <span data-ttu-id="7e46c-177">**Interés por intervalo**</span><span class="sxs-lookup"><span data-stu-id="7e46c-177">**Interest by range**</span></span>           | <span data-ttu-id="7e46c-178">Días</span><span class="sxs-lookup"><span data-stu-id="7e46c-178">Days</span></span>            |
| <span data-ttu-id="7e46c-179">**Calcular el interés en función de**</span><span class="sxs-lookup"><span data-stu-id="7e46c-179">**Calculate interest based on**</span></span> | <span data-ttu-id="7e46c-180">Importe</span><span class="sxs-lookup"><span data-stu-id="7e46c-180">Amount</span></span>          |

<span data-ttu-id="7e46c-181">Configure la información del intervalo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7e46c-181">You set up the range information as follows.</span></span>

| <span data-ttu-id="7e46c-182">**Valor inicial**</span><span class="sxs-lookup"><span data-stu-id="7e46c-182">**From value**</span></span> | <span data-ttu-id="7e46c-183">**Valor del interés**</span><span class="sxs-lookup"><span data-stu-id="7e46c-183">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="7e46c-184">0</span><span class="sxs-lookup"><span data-stu-id="7e46c-184">0</span></span>              | <span data-ttu-id="7e46c-185">10</span><span class="sxs-lookup"><span data-stu-id="7e46c-185">10</span></span>                 |
| <span data-ttu-id="7e46c-186">61</span><span class="sxs-lookup"><span data-stu-id="7e46c-186">61</span></span>             | <span data-ttu-id="7e46c-187">15</span><span class="sxs-lookup"><span data-stu-id="7e46c-187">15</span></span>                 |
| <span data-ttu-id="7e46c-188">91</span><span class="sxs-lookup"><span data-stu-id="7e46c-188">91</span></span>             | <span data-ttu-id="7e46c-189">20</span><span class="sxs-lookup"><span data-stu-id="7e46c-189">20</span></span>                 |


## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="7e46c-190">Ejemplo 3: interés por intervalo = meses</span><span class="sxs-lookup"><span data-stu-id="7e46c-190">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="7e46c-191">Establezca el código de interés que evalúa el interés una vez por cada mes que el pago de la factura supere la fecha de vencimiento de la transacción.</span><span class="sxs-lookup"><span data-stu-id="7e46c-191">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="7e46c-192">Deberá basar el cálculo en un valor de interés de porcentaje, de acuerdo con los intervalos escalonados del mes.</span><span class="sxs-lookup"><span data-stu-id="7e46c-192">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="7e46c-193">El valor del interés será del 1,5 por ciento por mes para los primeros tres meses vencidos, del 2,0 por ciento por mes para los segundos tres meses y del 2,5 por ciento por mes para cada mes pasados los primeros seis meses.</span><span class="sxs-lookup"><span data-stu-id="7e46c-193">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="7e46c-194">Configure los valores del campo del código de interés de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7e46c-194">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="7e46c-195">**Nombre del campo**</span><span class="sxs-lookup"><span data-stu-id="7e46c-195">**Field name**</span></span>                  | <span data-ttu-id="7e46c-196">**Valor de campo**</span><span class="sxs-lookup"><span data-stu-id="7e46c-196">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="7e46c-197">**Código del interés**</span><span class="sxs-lookup"><span data-stu-id="7e46c-197">**Interest code**</span></span>               | <span data-ttu-id="7e46c-198">1M%PorMes</span><span class="sxs-lookup"><span data-stu-id="7e46c-198">1M%ByMth</span></span>        |
| <span data-ttu-id="7e46c-199">**Calcular interés cada**</span><span class="sxs-lookup"><span data-stu-id="7e46c-199">**Calculate interest every**</span></span>    | <span data-ttu-id="7e46c-200">1/Mes</span><span class="sxs-lookup"><span data-stu-id="7e46c-200">1/Month</span></span>         |
| <span data-ttu-id="7e46c-201">**Interés por intervalo**</span><span class="sxs-lookup"><span data-stu-id="7e46c-201">**Interest by range**</span></span>           | <span data-ttu-id="7e46c-202">Meses</span><span class="sxs-lookup"><span data-stu-id="7e46c-202">Months</span></span>          |
| <span data-ttu-id="7e46c-203">**Calcular el interés en función de**</span><span class="sxs-lookup"><span data-stu-id="7e46c-203">**Calculate interest based on**</span></span> | <span data-ttu-id="7e46c-204">Porcentaje</span><span class="sxs-lookup"><span data-stu-id="7e46c-204">Percentage</span></span>      |

<span data-ttu-id="7e46c-205">Configure la información del intervalo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7e46c-205">You set up the range information as follows.</span></span>

| <span data-ttu-id="7e46c-206">**Valor inicial**</span><span class="sxs-lookup"><span data-stu-id="7e46c-206">**From value**</span></span> | <span data-ttu-id="7e46c-207">**Valor del interés**</span><span class="sxs-lookup"><span data-stu-id="7e46c-207">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="7e46c-208">0</span><span class="sxs-lookup"><span data-stu-id="7e46c-208">0</span></span>              | <span data-ttu-id="7e46c-209">1.5</span><span class="sxs-lookup"><span data-stu-id="7e46c-209">1.5</span></span>                |
| <span data-ttu-id="7e46c-210">4</span><span class="sxs-lookup"><span data-stu-id="7e46c-210">4</span></span>              | <span data-ttu-id="7e46c-211">2</span><span class="sxs-lookup"><span data-stu-id="7e46c-211">2</span></span>                  |
| <span data-ttu-id="7e46c-212">7</span><span class="sxs-lookup"><span data-stu-id="7e46c-212">7</span></span>              | <span data-ttu-id="7e46c-213">2,5</span><span class="sxs-lookup"><span data-stu-id="7e46c-213">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="7e46c-214">Versiones nuevas</span><span class="sxs-lookup"><span data-stu-id="7e46c-214">New versions</span></span>
<span data-ttu-id="7e46c-215">Los códigos de interés tienen fecha de vigencia.</span><span class="sxs-lookup"><span data-stu-id="7e46c-215">Interest codes are date effective.</span></span> <span data-ttu-id="7e46c-216">Si desea modificar el tipo de interés, puede crear una **nueva versión** que estará vigente a partir de una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="7e46c-216">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="7e46c-217">Para ver diferentes versiones, puede usar la opción de menú **Desde fecha** para seleccionar la fecha final.</span><span class="sxs-lookup"><span data-stu-id="7e46c-217">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="7e46c-218">También puede seleccionar **Mostrar todos los registros** para ver todos los códigos de interés en la página.</span><span class="sxs-lookup"><span data-stu-id="7e46c-218">You can also select the **Display all records** to view all interest codes in the page.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]

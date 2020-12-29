---
title: Establecer tipos de interés para un código de interés
description: Los códigos de interés contienen la configuración que determina si se carga el interés y cómo se calcula en las cuentas vencidas.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a3ca43503ecbe8e814958576e46ced10bfe9ad49
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447504"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="00717-103">Establecer tipos de interés para un código de interés</span><span class="sxs-lookup"><span data-stu-id="00717-103">Set up interest rates for an interest code</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="00717-104">Los códigos de interés contienen la configuración que determina si se carga el interés y cómo se calcula en las cuentas vencidas.</span><span class="sxs-lookup"><span data-stu-id="00717-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="00717-105">Puede configurar un único código de interés y aplicarlo a varios perfiles de registro de cliente, códigos de facturación o líneas de factura concretas.</span><span class="sxs-lookup"><span data-stu-id="00717-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="00717-106">Cuando se cambian los detalles del código de interés, todas las funciones que usan el código implementarán automáticamente los cambios en las nuevas transacciones.</span><span class="sxs-lookup"><span data-stu-id="00717-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="00717-107">Puede configurar dos tipos de índices para cada código de interés:</span><span class="sxs-lookup"><span data-stu-id="00717-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="00717-108">Índices para las ganancias por intereses: representan los ingresos obtenidos por cargar un interés en las facturas o notas de interés.</span><span class="sxs-lookup"><span data-stu-id="00717-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="00717-109">Índices para los pagos de interés: representan el coste pagado por el interés de las notas de abono.</span><span class="sxs-lookup"><span data-stu-id="00717-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="00717-110">Ambos tipos de índices pueden existir al mismo tiempo y en el mismo código de interés.</span><span class="sxs-lookup"><span data-stu-id="00717-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="00717-111">Los tipos de interés pueden basarse en tres tipos de cálculo:</span><span class="sxs-lookup"><span data-stu-id="00717-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="00717-112">Interés por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="00717-112">Interest by percentage.</span></span>
-   <span data-ttu-id="00717-113">Interés por importe.</span><span class="sxs-lookup"><span data-stu-id="00717-113">Interest by amount.</span></span>
-   <span data-ttu-id="00717-114">Interés por intervalo, lo que genera un único porcentaje o importe.</span><span class="sxs-lookup"><span data-stu-id="00717-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="00717-115">Si utiliza un código de interés para calcular el interés, se creará una nota de interés independiente para cada tipo de interés vigente durante el tiempo que el pago ha superado la fecha de vencimiento de la transacción.</span><span class="sxs-lookup"><span data-stu-id="00717-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="00717-116">Se usa la ficha **Ganancias** de la página **Código de Interés** para configurar los tipos de interés para la ganancia que se obtiene al cargar el interés.</span><span class="sxs-lookup"><span data-stu-id="00717-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="00717-117">Use la ficha **Pagos** para configurar los tipos de interés para el interés que usted paga.</span><span class="sxs-lookup"><span data-stu-id="00717-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="00717-118">Tipos de interés basados en porcentajes</span><span class="sxs-lookup"><span data-stu-id="00717-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="00717-119">Puede configurar los tipos de interés que calculan un porcentaje concreto.</span><span class="sxs-lookup"><span data-stu-id="00717-119">You can set up interest rates that calculate a specified percentage.</span></span>

- <span data-ttu-id="00717-120">El importe del interés se aplica a todas las divisas.</span><span class="sxs-lookup"><span data-stu-id="00717-120">Interest amount applies to all currencies.</span></span>
- <span data-ttu-id="00717-121">Se pueden especificar límites de interés opcionales.</span><span class="sxs-lookup"><span data-stu-id="00717-121">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="00717-122"><strong>Porcentaje</strong> se selecciona** en el campo <strong>**Calcular el interés en función de</strong> en la página <strong>Configurar códigos de interés</strong>.</span><span class="sxs-lookup"><span data-stu-id="00717-122"><strong>Percentage</strong> is selected\*\* <strong>in the \*\*Calculate interest based on</strong> field on the <strong>Set up Interest codes</strong> page.</span></span>

<span data-ttu-id="00717-123">Por ejemplo, para configurar un código de interés que evalúe el 5 por ciento de interés por cada dos meses que el pago de la factura supere la fecha de vencimiento de la transacción, escriba 2 en el campo **Calcular interés cada** y seleccione **Mes**.</span><span class="sxs-lookup"><span data-stu-id="00717-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="00717-124">Tipos de interés basados en importes</span><span class="sxs-lookup"><span data-stu-id="00717-124">Interest rates based on amounts</span></span>
<span data-ttu-id="00717-125">Puede configurar los tipos de interés que calculan un importe concreto por divisa.</span><span class="sxs-lookup"><span data-stu-id="00717-125">You can set up interest rates that calculate a specified amount per currency.</span></span>
- <span data-ttu-id="00717-126">Se especifica un importe de interés para cada divisa en el código de interés.</span><span class="sxs-lookup"><span data-stu-id="00717-126">An interest amount is specified for each currency in the interest code.</span></span>
- <span data-ttu-id="00717-127">Se pueden especificar límites de interés opcionales.</span><span class="sxs-lookup"><span data-stu-id="00717-127">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="00717-128">**Porcentaje** se selecciona en el campo **Calcular el interés en función de** en la página **Configurar códigos de interés**.</span><span class="sxs-lookup"><span data-stu-id="00717-128">**Amount** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="00717-129">Por ejemplo, para configurar un código de interés que evalúe el interés de 25,00 por cada 20 días que el pago de la factura supere la fecha de vencimiento de la transacción, escriba 20 en el campo **Calcular interés cada** y seleccione **Día**.</span><span class="sxs-lookup"><span data-stu-id="00717-129">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="00717-130">Tipos de interés basados en intervalos</span><span class="sxs-lookup"><span data-stu-id="00717-130">Interest rates based on ranges</span></span>
<span data-ttu-id="00717-131">Puede configurar los tipos de interés que varían en función del importe vencido o el número de días o de meses que se retrasa el importe.</span><span class="sxs-lookup"><span data-stu-id="00717-131">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="00717-132">Puede usar la ficha **Ganancias por divisa** para definir los parámetros específicos del interés para cada divisa.</span><span class="sxs-lookup"><span data-stu-id="00717-132">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="00717-133">Aquí es también donde se define el intervalo.</span><span class="sxs-lookup"><span data-stu-id="00717-133">This is also where you will define the range.</span></span>
-   <span data-ttu-id="00717-134">Use el botón **Intervalos** para agregar las líneas que representan los intervalos que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="00717-134">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="00717-135">El valor **De** representa el principio del intervalo y el número **Valor de interés** representa un porcentaje o un importe, en función de la selección en el campo **Calcular el interés en función de** de la página **Configurar códigos de interés** .</span><span class="sxs-lookup"><span data-stu-id="00717-135">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="00717-136">Ejemplo 1: interés por intervalo = importe</span><span class="sxs-lookup"><span data-stu-id="00717-136">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="00717-137">Establezca el código de interés que evalúa el interés una vez por cada tres meses que el pago de la factura supere la fecha de vencimiento de la transacción.</span><span class="sxs-lookup"><span data-stu-id="00717-137">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="00717-138">Deberá basar el cálculo en un valor de interés de porcentaje, de acuerdo con los intervalos del importe escalonado.</span><span class="sxs-lookup"><span data-stu-id="00717-138">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="00717-139">El valor de interés será del 1 por ciento para los importes de factura de hasta 1.000,00, del 2 por ciento para los importes entre 1.001,00 y 5.000,00, y del 3 por ciento para los importes superiores a 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="00717-139">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="00717-140">Configure los valores del campo del código de interés de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="00717-140">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="00717-141">**Nombre del campo**</span><span class="sxs-lookup"><span data-stu-id="00717-141">**Field name**</span></span>                  | <span data-ttu-id="00717-142">**Valor de campo**</span><span class="sxs-lookup"><span data-stu-id="00717-142">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="00717-143">**Código del interés**</span><span class="sxs-lookup"><span data-stu-id="00717-143">**Interest code**</span></span>               | <span data-ttu-id="00717-144">3M%PorCant</span><span class="sxs-lookup"><span data-stu-id="00717-144">3M%ByAmt</span></span>        |
| <span data-ttu-id="00717-145">**Calcular interés cada**</span><span class="sxs-lookup"><span data-stu-id="00717-145">**Calculate interest every**</span></span>    | <span data-ttu-id="00717-146">3/Mes</span><span class="sxs-lookup"><span data-stu-id="00717-146">3/Month</span></span>         |
| <span data-ttu-id="00717-147">**Interés por intervalo**</span><span class="sxs-lookup"><span data-stu-id="00717-147">**Interest by range**</span></span>           | <span data-ttu-id="00717-148">Importe</span><span class="sxs-lookup"><span data-stu-id="00717-148">Amount</span></span>          |
| <span data-ttu-id="00717-149">**Calcular el interés en función de**</span><span class="sxs-lookup"><span data-stu-id="00717-149">**Calculate interest based on**</span></span> | <span data-ttu-id="00717-150">Porcentaje</span><span class="sxs-lookup"><span data-stu-id="00717-150">Percentage</span></span>      |

<span data-ttu-id="00717-151">Configure la información del intervalo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="00717-151">You set up the range information as follows.</span></span>

| <span data-ttu-id="00717-152">**Valor inicial**</span><span class="sxs-lookup"><span data-stu-id="00717-152">**From value**</span></span> | <span data-ttu-id="00717-153">**Valor del interés**</span><span class="sxs-lookup"><span data-stu-id="00717-153">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="00717-154">0</span><span class="sxs-lookup"><span data-stu-id="00717-154">0</span></span>              | <span data-ttu-id="00717-155">1</span><span class="sxs-lookup"><span data-stu-id="00717-155">1</span></span>                  |
| <span data-ttu-id="00717-156">1,001</span><span class="sxs-lookup"><span data-stu-id="00717-156">1,001</span></span>          | <span data-ttu-id="00717-157">2</span><span class="sxs-lookup"><span data-stu-id="00717-157">2</span></span>                  |
| <span data-ttu-id="00717-158">5,001</span><span class="sxs-lookup"><span data-stu-id="00717-158">5,001</span></span>          | <span data-ttu-id="00717-159">3</span><span class="sxs-lookup"><span data-stu-id="00717-159">3</span></span>                  |


## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="00717-160">Ejemplo 2: interés por intervalo = días</span><span class="sxs-lookup"><span data-stu-id="00717-160">Example 2: Interest by range = Days</span></span>
--------------------------------------------------

<span data-ttu-id="00717-161">Establezca el código de interés que evalúa el interés una vez por cada 15 días que el pago de la factura supere la fecha de vencimiento de la transacción.</span><span class="sxs-lookup"><span data-stu-id="00717-161">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="00717-162">Deberá basar el cálculo en un valor de interés del importe, de acuerdo con los intervalos escalonados del día.</span><span class="sxs-lookup"><span data-stu-id="00717-162">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="00717-163">El valor del interés será de 10,00 por 15 días durante los primeros 60 días, de 15,00 por 15 días durante los días 61 a 90, y de 20,00 por 15 días a partir del día 91.</span><span class="sxs-lookup"><span data-stu-id="00717-163">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="00717-164">Configure los valores del campo del código de interés de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="00717-164">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="00717-165">**Nombre del campo**</span><span class="sxs-lookup"><span data-stu-id="00717-165">**Field name**</span></span>                  | <span data-ttu-id="00717-166">**Valor de campo**</span><span class="sxs-lookup"><span data-stu-id="00717-166">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="00717-167">**Código del interés**</span><span class="sxs-lookup"><span data-stu-id="00717-167">**Interest code**</span></span>               | <span data-ttu-id="00717-168">15DCantXDía</span><span class="sxs-lookup"><span data-stu-id="00717-168">15DAmtXDay</span></span>      |
| <span data-ttu-id="00717-169">**Calcular interés cada**</span><span class="sxs-lookup"><span data-stu-id="00717-169">**Calculate interest every**</span></span>    | <span data-ttu-id="00717-170">15/Día</span><span class="sxs-lookup"><span data-stu-id="00717-170">15/Day</span></span>          |
| <span data-ttu-id="00717-171">**Interés por intervalo**</span><span class="sxs-lookup"><span data-stu-id="00717-171">**Interest by range**</span></span>           | <span data-ttu-id="00717-172">Días</span><span class="sxs-lookup"><span data-stu-id="00717-172">Days</span></span>            |
| <span data-ttu-id="00717-173">**Calcular el interés en función de**</span><span class="sxs-lookup"><span data-stu-id="00717-173">**Calculate interest based on**</span></span> | <span data-ttu-id="00717-174">Importe</span><span class="sxs-lookup"><span data-stu-id="00717-174">Amount</span></span>          |

<span data-ttu-id="00717-175">Configure la información del intervalo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="00717-175">You set up the range information as follows.</span></span>

| <span data-ttu-id="00717-176">**Valor inicial**</span><span class="sxs-lookup"><span data-stu-id="00717-176">**From value**</span></span> | <span data-ttu-id="00717-177">**Valor del interés**</span><span class="sxs-lookup"><span data-stu-id="00717-177">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="00717-178">0</span><span class="sxs-lookup"><span data-stu-id="00717-178">0</span></span>              | <span data-ttu-id="00717-179">10</span><span class="sxs-lookup"><span data-stu-id="00717-179">10</span></span>                 |
| <span data-ttu-id="00717-180">61</span><span class="sxs-lookup"><span data-stu-id="00717-180">61</span></span>             | <span data-ttu-id="00717-181">15</span><span class="sxs-lookup"><span data-stu-id="00717-181">15</span></span>                 |
| <span data-ttu-id="00717-182">91</span><span class="sxs-lookup"><span data-stu-id="00717-182">91</span></span>             | <span data-ttu-id="00717-183">20</span><span class="sxs-lookup"><span data-stu-id="00717-183">20</span></span>                 |


## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="00717-184">Ejemplo 3: interés por intervalo = meses</span><span class="sxs-lookup"><span data-stu-id="00717-184">Example 3: Interest by range = Months</span></span>
----------------------------------------------------

<span data-ttu-id="00717-185">Establezca el código de interés que evalúa el interés una vez por cada mes que el pago de la factura supere la fecha de vencimiento de la transacción.</span><span class="sxs-lookup"><span data-stu-id="00717-185">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="00717-186">Deberá basar el cálculo en un valor de interés de porcentaje, de acuerdo con los intervalos escalonados del mes.</span><span class="sxs-lookup"><span data-stu-id="00717-186">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="00717-187">El valor del interés será del 1,5 por ciento por mes para los primeros tres meses vencidos, del 2,0 por ciento por mes para los segundos tres meses y del 2,5 por ciento por mes para cada mes pasados los primeros seis meses.</span><span class="sxs-lookup"><span data-stu-id="00717-187">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="00717-188">Configure los valores del campo del código de interés de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="00717-188">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="00717-189">**Nombre del campo**</span><span class="sxs-lookup"><span data-stu-id="00717-189">**Field name**</span></span>                  | <span data-ttu-id="00717-190">**Valor de campo**</span><span class="sxs-lookup"><span data-stu-id="00717-190">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="00717-191">**Código del interés**</span><span class="sxs-lookup"><span data-stu-id="00717-191">**Interest code**</span></span>               | <span data-ttu-id="00717-192">1M%PorMes</span><span class="sxs-lookup"><span data-stu-id="00717-192">1M%ByMth</span></span>        |
| <span data-ttu-id="00717-193">**Calcular interés cada**</span><span class="sxs-lookup"><span data-stu-id="00717-193">**Calculate interest every**</span></span>    | <span data-ttu-id="00717-194">1/Mes</span><span class="sxs-lookup"><span data-stu-id="00717-194">1/Month</span></span>         |
| <span data-ttu-id="00717-195">**Interés por intervalo**</span><span class="sxs-lookup"><span data-stu-id="00717-195">**Interest by range**</span></span>           | <span data-ttu-id="00717-196">Meses</span><span class="sxs-lookup"><span data-stu-id="00717-196">Months</span></span>          |
| <span data-ttu-id="00717-197">**Calcular el interés en función de**</span><span class="sxs-lookup"><span data-stu-id="00717-197">**Calculate interest based on**</span></span> | <span data-ttu-id="00717-198">Porcentaje</span><span class="sxs-lookup"><span data-stu-id="00717-198">Percentage</span></span>      |

<span data-ttu-id="00717-199">Configure la información del intervalo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="00717-199">You set up the range information as follows.</span></span>

| <span data-ttu-id="00717-200">**Valor inicial**</span><span class="sxs-lookup"><span data-stu-id="00717-200">**From value**</span></span> | <span data-ttu-id="00717-201">**Valor del interés**</span><span class="sxs-lookup"><span data-stu-id="00717-201">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="00717-202">0</span><span class="sxs-lookup"><span data-stu-id="00717-202">0</span></span>              | <span data-ttu-id="00717-203">1.5</span><span class="sxs-lookup"><span data-stu-id="00717-203">1.5</span></span>                |
| <span data-ttu-id="00717-204">4</span><span class="sxs-lookup"><span data-stu-id="00717-204">4</span></span>              | <span data-ttu-id="00717-205">2</span><span class="sxs-lookup"><span data-stu-id="00717-205">2</span></span>                  |
| <span data-ttu-id="00717-206">7</span><span class="sxs-lookup"><span data-stu-id="00717-206">7</span></span>              | <span data-ttu-id="00717-207">2,5</span><span class="sxs-lookup"><span data-stu-id="00717-207">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="00717-208">Versiones nuevas</span><span class="sxs-lookup"><span data-stu-id="00717-208">New versions</span></span>
<span data-ttu-id="00717-209">Los códigos de interés tienen fecha de vigencia.</span><span class="sxs-lookup"><span data-stu-id="00717-209">Interest codes are date effective.</span></span> <span data-ttu-id="00717-210">Si desea modificar el tipo de interés, puede crear una **nueva versión** que estará vigente a partir de una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="00717-210">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="00717-211">Para ver diferentes versiones, puede usar la opción de menú **Desde fecha** para seleccionar la fecha final.</span><span class="sxs-lookup"><span data-stu-id="00717-211">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="00717-212">También puede seleccionar **Mostrar todos los registros** para ver todos los códigos de interés en la página.</span><span class="sxs-lookup"><span data-stu-id="00717-212">You can also select the **Display all records** to view all interest codes in the page.</span></span>




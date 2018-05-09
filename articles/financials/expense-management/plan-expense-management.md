---
title: "Configurar la gestión de gastos"
description: "En este artículo se describen las consideraciones y las decisiones que debe realizar durante el proceso de planificación, antes de configurar Gestión de gastos en Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e213c4436452ddf1d0e22d791c7ee2cee803edc7
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="configure-expense-management"></a><span data-ttu-id="84d03-103">Configurar la gestión de gastos</span><span class="sxs-lookup"><span data-stu-id="84d03-103">Configure expense management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84d03-104">En este tema se describen las consideraciones y las decisiones que debe realizar durante el proceso de planificación, antes de configurar Gestión de gastos en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="84d03-104">This topic describes the considerations and the decisions that you must make during the planning process before you configure Expense management in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="84d03-105">En el área Gestión de gastos, puede almacenar información sobre los métodos de pago, los pedidos de viaje, los informes de gastos y las directivas, entre otros elementos.</span><span class="sxs-lookup"><span data-stu-id="84d03-105">In Expense management, you can store information about payment methods, travel requisitions, expense reports, policies, and so on.</span></span>

<span data-ttu-id="84d03-106">Dado que muchas de las decisiones que realiza al planificar su configuración para la gestión de gastos se basan en la jerarquía y la estructura financiera de su organización, debe hacer referencia a los documentos de planificación para esas áreas.</span><span class="sxs-lookup"><span data-stu-id="84d03-106">Because many of the decisions that you make when you plan your configuration for Expense management are based on your organization’s hierarchy and financial structure, you must refer to the planning documents for those areas.</span></span>

## <a name="intercompany-expenses"></a><span data-ttu-id="84d03-107">Gastos de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="84d03-107">Intercompany expenses</span></span>

<span data-ttu-id="84d03-108">Al habilitar los gastos de empresas vinculadas, permite a las entidades jurídicas y a los empleados incurrir en gastos en nombre de otra entidad jurídica, y realizar el cobro a la entidad jurídica de empleo dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="84d03-108">When you enable intercompany expenses, you allow legal entities and employees to incur expenses on behalf of another legal entity, and collect payment from the legal entity of employment within your organization.</span></span> <span data-ttu-id="84d03-109">Por ejemplo, un empleado de una entidad jurídica A completa un proyecto para la entidad jurídica B, y el proyecto incurre en gastos relacionados con un viaje.</span><span class="sxs-lookup"><span data-stu-id="84d03-109">For example, an employee in legal entity A completes a project for legal entity B, and the project incurs travel related expenses.</span></span> <span data-ttu-id="84d03-110">Si se habilitan los gastos de empresas vinculadas, el empleado puede entonces archivar un informe de gastos que se enviará a la entidad jurídica B; esos gastos debe pagarlos la entidad jurídica A. Si su organización no tiene varias entidades jurídicas, no necesitará habilitar los gastos de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="84d03-110">If intercompany expenses are enabled, the employee can then file an expense report that will post the expense to legal entity B, and the expense must then be paid by legal entity A. If your organization doesn’t have multiple legal entities, you don’t have to enable intercompany expenses.</span></span>

<span data-ttu-id="84d03-111">**Decisión:** ¿Desea habilitar gastos de empresas vinculadas?</span><span class="sxs-lookup"><span data-stu-id="84d03-111">**Decision:** Do you want to enable intercompany expenses?</span></span>

## <a name="financial-management"></a><span data-ttu-id="84d03-112">Administración financiera</span><span class="sxs-lookup"><span data-stu-id="84d03-112">Financial management</span></span>

<span data-ttu-id="84d03-113">La gestión de gastos se integra totalmente con la administración financiera de la organización.</span><span class="sxs-lookup"><span data-stu-id="84d03-113">Expense management is tightly integrated with the financial management of your organization.</span></span> <span data-ttu-id="84d03-114">Gran parte de la configuración de la gestión de gastos se basará en las decisiones que haya realizado sobre las finanzas de su organización.</span><span class="sxs-lookup"><span data-stu-id="84d03-114">Lots of your configuration for Expense management will be based on the decisions that you’ve made about your organization’s finances.</span></span> <span data-ttu-id="84d03-115">Las siguientes secciones describen varias áreas que requieren planificación y decisiones basadas en la orientación y las decisiones financieras de su organización del equipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="84d03-115">The following sections describe the various areas that require planning and decisions, based on your organization’s financial decisions and guidance from your leadership team.</span></span>

### <a name="per-diems"></a><span data-ttu-id="84d03-116">Dietas</span><span class="sxs-lookup"><span data-stu-id="84d03-116">Per diems</span></span>

<span data-ttu-id="84d03-117">Debe definir las dietas de empleado que ofrece su organización.</span><span class="sxs-lookup"><span data-stu-id="84d03-117">You must define the employee per diems that your organization provides.</span></span> <span data-ttu-id="84d03-118">Dado que las dietas se suelen usar para satisfacer gastos como comidas, alojamiento y otros gastos incidentales, puede crear reglas para las retribuciones de dietas para que ofrece su organización.</span><span class="sxs-lookup"><span data-stu-id="84d03-118">Because per diems are typically used to cover expenses such as meals, lodging, and other incidental expenses, you can create rules for the per diem allowances that your organization offers.</span></span> <span data-ttu-id="84d03-119">Las tarifas de dietas se pueden basar en la época del año, el destino del viaje o ambos.</span><span class="sxs-lookup"><span data-stu-id="84d03-119">per diem rates can be based on the time of year, the travel location, or both.</span></span> <span data-ttu-id="84d03-120">Al definir una regla de dietas, puede especificar la retención de un porcentaje de la tarifa de dietas si el trabajador recibe comidas o servicios complementarios.</span><span class="sxs-lookup"><span data-stu-id="84d03-120">When you define a per diem rule, you can specify that a percentage of the per diem rate will be withheld if a worker receives complimentary meals or services.</span></span> <span data-ttu-id="84d03-121">También puede definir niveles de tabla de dietas para establecer el mínimo o máximo de horas durante las que se puede aplicar la tarifa de dietas al viaje del trabajador.</span><span class="sxs-lookup"><span data-stu-id="84d03-121">You can also define per diem rate tiers to set the minimum and maximum number of hours that the per diem rate can be applied to a worker’s travel.</span></span>

<span data-ttu-id="84d03-122">**Decisiones:**</span><span class="sxs-lookup"><span data-stu-id="84d03-122">**Decisions:**</span></span>

- <span data-ttu-id="84d03-123">Reglas de dietas predeterminadas para el primer y el último día:</span><span class="sxs-lookup"><span data-stu-id="84d03-123">Default per diem rules for the first and last days:</span></span>

    - <span data-ttu-id="84d03-124">¿Cuál es el número mínimo de horas que un empleado puede reclamar para un día y recibir aún dietas?</span><span class="sxs-lookup"><span data-stu-id="84d03-124">What is the minimum number of hours that an employee can claim for a day and still receive a per diem?</span></span>
    - <span data-ttu-id="84d03-125">¿Hay una reducción del importe que se ofrece para comidas el primer y el último día?</span><span class="sxs-lookup"><span data-stu-id="84d03-125">Is there a reduction in the amount that is offered for meals for the first day and last day?</span></span> <span data-ttu-id="84d03-126">Si existe una reducción, ¿cuál es el porcentaje de la misma?</span><span class="sxs-lookup"><span data-stu-id="84d03-126">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="84d03-127">¿Hay una reducción del importe que se ofrece para un hotel el primer y el último día?</span><span class="sxs-lookup"><span data-stu-id="84d03-127">Is there a reduction in the amount that is offered for a hotel for the first day and last day?</span></span> <span data-ttu-id="84d03-128">Si existe una reducción, ¿cuál es el porcentaje de la misma?</span><span class="sxs-lookup"><span data-stu-id="84d03-128">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="84d03-129">¿Hay una reducción del importe que se ofrece para otros gastos generados el primer y el último día?</span><span class="sxs-lookup"><span data-stu-id="84d03-129">Is there a reduction in the amount that is offered for other expenses that are incurred on the first day and last day?</span></span> <span data-ttu-id="84d03-130">Si existe una reducción, ¿cuál es el porcentaje de la misma?</span><span class="sxs-lookup"><span data-stu-id="84d03-130">If there is a reduction, what is the percentage of the reduction?</span></span>

- <span data-ttu-id="84d03-131">Reglas de dietas predeterminadas:</span><span class="sxs-lookup"><span data-stu-id="84d03-131">Default per diem rules:</span></span>

    - <span data-ttu-id="84d03-132">¿Hay una reducción del porcentaje en el permiso de dietas para cada comida si, por ejemplo, la comida es gratuita?</span><span class="sxs-lookup"><span data-stu-id="84d03-132">Is there a percentage reduction in the per diem allowance for each meal if, for example, the meal is complimentary?</span></span> <span data-ttu-id="84d03-133">Si existe una reducción, ¿cuál es el porcentaje de reducción de cada comida?</span><span class="sxs-lookup"><span data-stu-id="84d03-133">If there is a reduction, what is the reduction percentage for each meal?</span></span>
    - <span data-ttu-id="84d03-134">¿La reducción de la comida se calcula por día, por viaje o por el número de comidas al día?</span><span class="sxs-lookup"><span data-stu-id="84d03-134">Is the meal reduction calculated per day, per trip, or by the number of meals per day?</span></span>
    - <span data-ttu-id="84d03-135">¿Es necesario redondear los importes de las dietas de forma normal o deben redondearse hacia arriba?</span><span class="sxs-lookup"><span data-stu-id="84d03-135">Should per diem amounts be rounded in the regular manner or rounded up?</span></span>
    - <span data-ttu-id="84d03-136">¿Las dietas se calculan en un período de 24 horas o en un día de calendario?</span><span class="sxs-lookup"><span data-stu-id="84d03-136">Are per diems calculated on a 24-hour period or on a calendar day?</span></span>

- <span data-ttu-id="84d03-137">Reglas de dietas basadas en la ubicación:</span><span class="sxs-lookup"><span data-stu-id="84d03-137">Per diem rules that are based on location:</span></span>

    - <span data-ttu-id="84d03-138">¿Las tarifas de dietas cambian según la ubicación?</span><span class="sxs-lookup"><span data-stu-id="84d03-138">Do per diem rates vary according to location?</span></span> <span data-ttu-id="84d03-139">¿Qué ubicaciones están incluidas?</span><span class="sxs-lookup"><span data-stu-id="84d03-139">What locations are included?</span></span>
    - <span data-ttu-id="84d03-140">Si las tarifas de dietas varían según la ubicación, teniendo en cuenta cada ubicación, ¿qué porcentaje del importe se proporciona según los siguientes tipos de gastos?:</span><span class="sxs-lookup"><span data-stu-id="84d03-140">If per diem rates vary according to location, for each location, what percentage amount is provided for the following types of expenses:</span></span>

        - <span data-ttu-id="84d03-141">Comidas</span><span class="sxs-lookup"><span data-stu-id="84d03-141">Meals</span></span>
        - <span data-ttu-id="84d03-142">Hotel</span><span class="sxs-lookup"><span data-stu-id="84d03-142">Hotel</span></span>
        - <span data-ttu-id="84d03-143">Otros gastos</span><span class="sxs-lookup"><span data-stu-id="84d03-143">Other expenses</span></span>

### <a name="expense-management-journals-and-accounts"></a><span data-ttu-id="84d03-144">Cuentas y diarios de gestión de gastos</span><span class="sxs-lookup"><span data-stu-id="84d03-144">Expense management journals and accounts</span></span>

<span data-ttu-id="84d03-145">La gestión de gastos requiere que use varios diarios y cuentas.</span><span class="sxs-lookup"><span data-stu-id="84d03-145">Expense management requires that you use multiple journals and accounts.</span></span> <span data-ttu-id="84d03-146">Debe decidir, por ejemplo, si se usa la misma cuenta para anticipos y conflictos de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="84d03-146">You must decide, for example, whether the same account is used for cash advances and credit card disputes.</span></span>

<span data-ttu-id="84d03-147">**Decisiones:**</span><span class="sxs-lookup"><span data-stu-id="84d03-147">**Decisions:**</span></span>

- <span data-ttu-id="84d03-148">¿En qué diario contable se registran los informes de gastos aprobados?</span><span class="sxs-lookup"><span data-stu-id="84d03-148">Which ledger journal are approved expense reports posted to?</span></span>
- <span data-ttu-id="84d03-149">¿Qué cuenta se usa para anticipos?</span><span class="sxs-lookup"><span data-stu-id="84d03-149">Which account is used for cash advances?</span></span>
- <span data-ttu-id="84d03-150">¿Se deben registrar los anticipos inmediatamente?</span><span class="sxs-lookup"><span data-stu-id="84d03-150">Should cash advances be posted immediately?</span></span>

### <a name="payment-methods"></a><span data-ttu-id="84d03-151">Métodos de pago</span><span class="sxs-lookup"><span data-stu-id="84d03-151">Payment methods</span></span>

<span data-ttu-id="84d03-152">Cuando permite a los empleados incurrir en gastos en nombre de su negocio, debe definir los métodos de pago que se permiten usar a los empleados.</span><span class="sxs-lookup"><span data-stu-id="84d03-152">When you allow employees to incur expenses on behalf of your business, you must define the payment methods that employees are allowed to use.</span></span> <span data-ttu-id="84d03-153">Por ejemplo, puede que permitir a los empleados usar efectivo o una tarjeta de crédito corporativa.</span><span class="sxs-lookup"><span data-stu-id="84d03-153">For example, you might allow employees to use cash or a corporate credit card.</span></span> <span data-ttu-id="84d03-154">También puede permitir a los empleados usar tarjetas de crédito personales y después reembolsar a los empleados.</span><span class="sxs-lookup"><span data-stu-id="84d03-154">You might also allow employees to use personal credit cards, and then reimburse the employees.</span></span> <span data-ttu-id="84d03-155">Debe tomar las siguientes decisiones para cada método de pago que habilite.</span><span class="sxs-lookup"><span data-stu-id="84d03-155">You must make the following decisions for each payment method that you allow.</span></span>

<span data-ttu-id="84d03-156">**Decisiones:**</span><span class="sxs-lookup"><span data-stu-id="84d03-156">**Decisions:**</span></span>

- <span data-ttu-id="84d03-157">¿Qué métodos de pago se permiten?</span><span class="sxs-lookup"><span data-stu-id="84d03-157">What payment methods are allowed?</span></span>
- <span data-ttu-id="84d03-158">¿Quién posee los gastos del método de pago?</span><span class="sxs-lookup"><span data-stu-id="84d03-158">Who owns the payment method expenses?</span></span>
- <span data-ttu-id="84d03-159">¿Hay un tipo de cuenta de contrapartida?</span><span class="sxs-lookup"><span data-stu-id="84d03-159">Is there an offset account type?</span></span> <span data-ttu-id="84d03-160">Si hay un tipo de cuenta de contrapartida, ¿cuál es?</span><span class="sxs-lookup"><span data-stu-id="84d03-160">If there is an offset account type, what is it?</span></span>
- <span data-ttu-id="84d03-161">Si hay una cuenta de contrapartida, ¿cuál es la cuenta?</span><span class="sxs-lookup"><span data-stu-id="84d03-161">If there is an offset account, what is the account?</span></span>
- <span data-ttu-id="84d03-162">Si el método de pago es una tarjeta de crédito, ¿debe usarse el método de pago solo con transacciones importadas?</span><span class="sxs-lookup"><span data-stu-id="84d03-162">If the payment method is a credit card, should the payment method be used only with imported transactions?</span></span>

### <a name="expense-categories-and-shared-categories"></a><span data-ttu-id="84d03-163">Categorías de gastos y categorías compartidas</span><span class="sxs-lookup"><span data-stu-id="84d03-163">Expense categories and shared categories</span></span>

<span data-ttu-id="84d03-164">Cuando los empleados crean un informe de gastos, cada gasto que registran se debe asociar a una categoría de gastos.</span><span class="sxs-lookup"><span data-stu-id="84d03-164">When employees create an expense report, each expense that they record must be associated with an expense category.</span></span> <span data-ttu-id="84d03-165">Las categorías de gastos se derivan de las categorías compartidas que se pueden compartir en las entidades jurídicas de la organización.</span><span class="sxs-lookup"><span data-stu-id="84d03-165">Expense categories are derived from shared categories that can be shared across the legal entities in your organization.</span></span> <span data-ttu-id="84d03-166">Estas categorías también se pueden compartir en la gestión de proyectos y la contabilidad, en función de cómo se define la organización.</span><span class="sxs-lookup"><span data-stu-id="84d03-166">These categories can also be shared in Project management and accounting, depending on the way that your organization is defined.</span></span> <span data-ttu-id="84d03-167">En función de la definición de su organización y la orientación del equipo de implementación, determine si las categorías que se utilizan en la gestión de gastos deberán usarse solo en administrar gastos o si se deben compartir entre la administración del proyecto, la contabilidad y la administración de gastos.</span><span class="sxs-lookup"><span data-stu-id="84d03-167">Based on the definition of your organization and guidance from the implementation team, determine whether the categories that are used in Expense management will be used only in Expense management, or whether they should be shared between Project management and accounting and Expense management.</span></span> <span data-ttu-id="84d03-168">Tenga en cuenta que estas categorías se pueden compartir entre el proyecto y los gastos o el proyecto y la producción, pero no entre el gasto y la producción.</span><span class="sxs-lookup"><span data-stu-id="84d03-168">Note that these categories can be shared between Project and Expense or Project and Production, but not between Expense and Production.</span></span> <span data-ttu-id="84d03-169">Debe tomar las siguientes decisiones para cada categoría de gastos.</span><span class="sxs-lookup"><span data-stu-id="84d03-169">You must make the following decisions for each expense category.</span></span>

<span data-ttu-id="84d03-170">**Decisiones:**</span><span class="sxs-lookup"><span data-stu-id="84d03-170">**Decisions:**</span></span>

- <span data-ttu-id="84d03-171">¿Cuál es la categoría de gasto?</span><span class="sxs-lookup"><span data-stu-id="84d03-171">What is the expense category?</span></span> <span data-ttu-id="84d03-172">Estos ejemplos incluyen categorías de vuelos, hoteles o kilometraje.</span><span class="sxs-lookup"><span data-stu-id="84d03-172">Examples include categories for flights, hotel, or mileage.</span></span>
- <span data-ttu-id="84d03-173">¿Se puede usar también esta categoría de gastos en la gestión del proyecto y la contabilidad?</span><span class="sxs-lookup"><span data-stu-id="84d03-173">Can the expense category also be used in Project management and accounting?</span></span>
- <span data-ttu-id="84d03-174">¿Cuál es el tipo de gasto?</span><span class="sxs-lookup"><span data-stu-id="84d03-174">What is the expense type?</span></span>
- <span data-ttu-id="84d03-175">¿Cuál es el método de pago predeterminado para la categoría de gastos?</span><span class="sxs-lookup"><span data-stu-id="84d03-175">What is the default payment method for the expense category?</span></span>
- <span data-ttu-id="84d03-176">¿Los gastos de la categoría de gastos deben estar detallados?</span><span class="sxs-lookup"><span data-stu-id="84d03-176">Do expenses in the expense category have to be itemized?</span></span>
- <span data-ttu-id="84d03-177">¿Cuál es la principal cuenta predeterminada para la categoría de gastos?</span><span class="sxs-lookup"><span data-stu-id="84d03-177">What is the main default account for the expense category?</span></span>
- <span data-ttu-id="84d03-178">¿Qué es el grupo de impuestos de artículos predeterminado para la categoría de gastos?</span><span class="sxs-lookup"><span data-stu-id="84d03-178">What is the default item sales tax group for the expense category?</span></span>
- <span data-ttu-id="84d03-179">¿Se permiten métodos de pago adicionales para la categoría de gastos?</span><span class="sxs-lookup"><span data-stu-id="84d03-179">Are additional payment methods allowed for the expense category?</span></span> <span data-ttu-id="84d03-180">Si se permiten los métodos de pago adicionales, ¿cuáles pueden ser?</span><span class="sxs-lookup"><span data-stu-id="84d03-180">If additional payment methods are allowed, what are they?</span></span>
- <span data-ttu-id="84d03-181">¿Hay subcategorías en esta categoría de gastos?</span><span class="sxs-lookup"><span data-stu-id="84d03-181">Are there subcategories in this expense category?</span></span> <span data-ttu-id="84d03-182">Si hay subcategorías, también debe tomar las decisiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="84d03-182">If there are subcategories, you must also make the following decisions:</span></span>

    - <span data-ttu-id="84d03-183">¿Se excluye cualquiera de las subcategorías de la devolución de impuestos?</span><span class="sxs-lookup"><span data-stu-id="84d03-183">Are any of the subcategories excluded from tax recovery?</span></span>
    - <span data-ttu-id="84d03-184">¿Cuál es el grupo de impuestos de artículos de las subcategorías?</span><span class="sxs-lookup"><span data-stu-id="84d03-184">What is the item sales tax group of the subcategories?</span></span>

<span data-ttu-id="84d03-185">Si esta categoría de gastos también se usa en la gestión de proyectos y la contabilidad, responda las preguntas restantes.</span><span class="sxs-lookup"><span data-stu-id="84d03-185">If the expense category is also used in Project management and accounting, answer the remaining questions.</span></span> <span data-ttu-id="84d03-186">Si no, vaya a la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="84d03-186">Otherwise, move on to the next section.</span></span>

- <span data-ttu-id="84d03-187">¿Qué cuentas de costes se usarán para lo siguientes gastos?</span><span class="sxs-lookup"><span data-stu-id="84d03-187">Which cost accounts will be used for the following expenses?</span></span>

    - <span data-ttu-id="84d03-188">Coste</span><span class="sxs-lookup"><span data-stu-id="84d03-188">Cost</span></span>
    - <span data-ttu-id="84d03-189">Asignación de nóminas</span><span class="sxs-lookup"><span data-stu-id="84d03-189">Payroll allocation</span></span>
    - <span data-ttu-id="84d03-190">Trabajo en proceso - Valor de coste</span><span class="sxs-lookup"><span data-stu-id="84d03-190">WIP-cost value</span></span>
    - <span data-ttu-id="84d03-191">Coste-artículo</span><span class="sxs-lookup"><span data-stu-id="84d03-191">Cost-item</span></span>
    - <span data-ttu-id="84d03-192">Trabajo en proceso - Valor de coste - Artículo</span><span class="sxs-lookup"><span data-stu-id="84d03-192">WIP-cost value-item</span></span>
    - <span data-ttu-id="84d03-193">Pérdida acumulada</span><span class="sxs-lookup"><span data-stu-id="84d03-193">Accrued loss</span></span>
    - <span data-ttu-id="84d03-194">Trabajo en proceso - Pérdida acumulada</span><span class="sxs-lookup"><span data-stu-id="84d03-194">WIP-accrued loss</span></span>

- <span data-ttu-id="84d03-195">¿Qué cuentas de ingresos se usarán para lo siguiente?</span><span class="sxs-lookup"><span data-stu-id="84d03-195">Which revenue accounts will be used for the following?</span></span>

    - <span data-ttu-id="84d03-196">Ingresos facturados</span><span class="sxs-lookup"><span data-stu-id="84d03-196">Invoiced revenue</span></span>
    - <span data-ttu-id="84d03-197">Ingresos acumulados-valor de ventas</span><span class="sxs-lookup"><span data-stu-id="84d03-197">Accrued revenue-sales value</span></span>
    - <span data-ttu-id="84d03-198">Trabajo en proceso-valor de ventas</span><span class="sxs-lookup"><span data-stu-id="84d03-198">WIP-sales value</span></span>
    - <span data-ttu-id="84d03-199">Ingresos acumulados-producción</span><span class="sxs-lookup"><span data-stu-id="84d03-199">Accrued revenue-production</span></span>
    - <span data-ttu-id="84d03-200">Trabajo en proceso-producción</span><span class="sxs-lookup"><span data-stu-id="84d03-200">WIP-production</span></span>
    - <span data-ttu-id="84d03-201">Ingresos acumulados-ganancias</span><span class="sxs-lookup"><span data-stu-id="84d03-201">Accrued revenue-profit</span></span>
    - <span data-ttu-id="84d03-202">Trabajo en proceso - ganancias</span><span class="sxs-lookup"><span data-stu-id="84d03-202">WIP-profit</span></span>
    - <span data-ttu-id="84d03-203">Ingresos acumulados-suscripción</span><span class="sxs-lookup"><span data-stu-id="84d03-203">Accrued revenue-subscription</span></span>
    - <span data-ttu-id="84d03-204">Trabajo en proceso - suscripción</span><span class="sxs-lookup"><span data-stu-id="84d03-204">WIP-subscription</span></span>

### <a name="taxes"></a><span data-ttu-id="84d03-205">Impuestos</span><span class="sxs-lookup"><span data-stu-id="84d03-205">Taxes</span></span>

<span data-ttu-id="84d03-206">Para los impuestos relacionados con gastos, debe determinar qué se incluye o se permite en los informes de gastos.</span><span class="sxs-lookup"><span data-stu-id="84d03-206">For expense-related taxes, you must determine what is included or enabled on expense reports.</span></span>

<span data-ttu-id="84d03-207">**Decisiones:**</span><span class="sxs-lookup"><span data-stu-id="84d03-207">**Decisions:**</span></span>

- <span data-ttu-id="84d03-208">¿Los impuestos se incluyen en los importes de gastos?</span><span class="sxs-lookup"><span data-stu-id="84d03-208">Is sales tax included in the expense amounts?</span></span>
- <span data-ttu-id="84d03-209">¿Se debe habilitar la devolución de impuestos en los gastos?</span><span class="sxs-lookup"><span data-stu-id="84d03-209">Should tax recovery be enabled on expenses?</span></span>

    > [!NOTE]
    > <span data-ttu-id="84d03-210">Si al planificar el libro de contabilidad general decidió aplicar los impuestos de los Estados Unidos y las reglas del IVA de importación, no puede habilitar la opción de devolución de impuestos en los gastos.</span><span class="sxs-lookup"><span data-stu-id="84d03-210">When you were planning the general ledger, if you decided to apply U.S. sales tax and use tax rules, you can’t enable tax recovery on expenses.</span></span> <span data-ttu-id="84d03-211">(Para aplicar los impuestos de los Estados Unidos y las reglas del IVA de importación, establezca la opción **Aplicar reglas de tributación de impuestos** en **Sí**).</span><span class="sxs-lookup"><span data-stu-id="84d03-211">(To apply U.S. sales tax and use tax rules, set the **Apply sales tax taxations rules** option to **Yes**.)</span></span>

## <a name="policies"></a><span data-ttu-id="84d03-212">Directivas</span><span class="sxs-lookup"><span data-stu-id="84d03-212">Policies</span></span>

<span data-ttu-id="84d03-213">Al crear directivas de informes de gastos, su organización ahorrará tiempo y dinero cuando los empleados generen gastos en su nombre.</span><span class="sxs-lookup"><span data-stu-id="84d03-213">By creating expense report policies, you can help your organization save time and money when employees incur expenses on its behalf.</span></span> <span data-ttu-id="84d03-214">Las directivas le garantizan que los empleados se ajustan al presupuesto, proporcionan toda la información necesaria y gastan dinero solo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="84d03-214">Policies help guarantee that employees stay in budget, provide all required information, and spend money only as they require it.</span></span> <span data-ttu-id="84d03-215">Debe tomar las siguientes decisiones para cada directiva de informe de gastos y cada directiva de aprobación de informe de gastos que cree.</span><span class="sxs-lookup"><span data-stu-id="84d03-215">You must make the following decisions for each expense report policy and each expense report approval policy that you create.</span></span>

<span data-ttu-id="84d03-216">**Decisiones:**</span><span class="sxs-lookup"><span data-stu-id="84d03-216">**Decisions:**</span></span>

- <span data-ttu-id="84d03-217">¿Cuál es el nombre de la directiva?</span><span class="sxs-lookup"><span data-stu-id="84d03-217">What is the name of the policy?</span></span>
- <span data-ttu-id="84d03-218">¿Para qué es la directiva de gastos?</span><span class="sxs-lookup"><span data-stu-id="84d03-218">What is the expense policy for?</span></span>
- <span data-ttu-id="84d03-219">Si decidió anteriormente habilitar los gastos de empresas vinculadas, ¿a qué empresas de su organización se aplicará esta directiva?</span><span class="sxs-lookup"><span data-stu-id="84d03-219">If you previously decided to enable intercompany expenses, which companies in your organization will this policy apply to?</span></span>
- <span data-ttu-id="84d03-220">¿Cuándo entrará en vigor la directiva?</span><span class="sxs-lookup"><span data-stu-id="84d03-220">When does the policy become effective?</span></span>
- <span data-ttu-id="84d03-221">¿Cuándo expira la directiva?</span><span class="sxs-lookup"><span data-stu-id="84d03-221">When does the policy expire?</span></span>
- <span data-ttu-id="84d03-222">¿Cuál es la regla de directivas?</span><span class="sxs-lookup"><span data-stu-id="84d03-222">What is the policy rule?</span></span>
- <span data-ttu-id="84d03-223">¿Cuál es el resultado de la regla de directivas?</span><span class="sxs-lookup"><span data-stu-id="84d03-223">What is the outcome of the policy rule?</span></span>


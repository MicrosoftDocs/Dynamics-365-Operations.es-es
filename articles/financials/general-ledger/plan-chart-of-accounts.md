---
title: Planificar su plan de cuentas
description: "Este tema proporciona información que le ayudará a planificar el plan de cuentas para su organización."
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 3f8d97fc42cde9053b0552fc1dfe8e6de0f5e03b
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="7f5ab-103">Planificar su plan de cuentas</span><span class="sxs-lookup"><span data-stu-id="7f5ab-103">Plan your chart of accounts</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="7f5ab-104">Este tema proporciona información que le ayudará a planificar el plan de cuentas para su organización.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-104">This topic provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="7f5ab-105">Puede configurar un plan de cuentas para hacer un seguimiento de la información financiera de una organización y mantenerla.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="7f5ab-106">El plan de cuentas es un conjunto de cuentas que definen un marco financiero.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="7f5ab-107">Para realizar un seguimiento más exhaustivo de las transacciones de estas cuentas, puede agregar segmentos.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-107">To further track the transactions in these accounts, you can add segments.</span></span> <span data-ttu-id="7f5ab-108">Estos segmentos se conocen como dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-108">These segments are known as financial dimensions.</span></span> <span data-ttu-id="7f5ab-109">Por ejemplo, una cuenta de gastos puede incluir dimensiones financieras denominadas Departamento, Centro de coste y Propósito.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-109">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="7f5ab-110">Las reglas que define el usuario determinan la forma de vincular las dimensiones financieras a las cuentas principales y a otras dimensiones financieras, así como la forma de introducir transacciones.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-110">User-defined rules determine how financial dimensions are attached to the main accounts and to other financial dimensions, and also how transactions are entered.</span></span> <span data-ttu-id="7f5ab-111">Estas reglas definidas por el usuario se conocen como estructuras contables y reglas avanzadas.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-111">These user-defined rules are known as account structures and advanced rules.</span></span>

<span data-ttu-id="7f5ab-112">El plan contable es una lista estructurada de las cuentas de contabilidad general de una entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-112">The chart of accounts is a structured list of a legal entity's general ledger accounts.</span></span> <span data-ttu-id="7f5ab-113">Esta lista se utiliza para preparar informes financieros para autoridades y propietarios.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-113">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="7f5ab-114">Las cuentas se agrupan primero en tipos de cuentas y despuñes se agregan en categorías más grandes.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-114">The accounts are first grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="7f5ab-115">En el nivel más general, las cuentas se agrupan en ingresos y costes (cuentas operativas) y activos y pasivos (cuentas de saldo).</span><span class="sxs-lookup"><span data-stu-id="7f5ab-115">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span>

<span data-ttu-id="7f5ab-116">Cualquier entidad jurídica de una organización puede usar y compartir un plan contable.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-116">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="7f5ab-117">El plan contable utilizado por una entidad jurídica se define en la página **Libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-117">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span>

<span data-ttu-id="7f5ab-118">Estos son algunos de los factores que se deben tener en cuenta la hora de planificar la estructura del plan de cuentas en la organización:</span><span class="sxs-lookup"><span data-stu-id="7f5ab-118">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

- <span data-ttu-id="7f5ab-119">Los requisitos de informes del país o región en que está situada la organización</span><span class="sxs-lookup"><span data-stu-id="7f5ab-119">The reporting requirements of the country or region where your organization is based</span></span>
- <span data-ttu-id="7f5ab-120">Los requisitos de informes de la entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="7f5ab-120">The reporting requirements of your legal entity</span></span>
- <span data-ttu-id="7f5ab-121">El grado de especificación necesario, para las organizaciones externas y para la propia.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-121">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="7f5ab-122">Cree el plan de cuentas en la página **Plan de cuentas**.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-122">You create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="7f5ab-123">Puede crear las cuentas principales desde la página **Plan de cuentas** o la página **Cuentas principales**.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-123">You can create main accounts from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="7f5ab-124">Sus cuentas principales no deben usar ninguno de los caracteres especiales que se usan como delimitadores en los planes de cuentas.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-124">Your main accounts shouldn't use any special characters that are used as delimiters for chart of accounts.</span></span> <span data-ttu-id="7f5ab-125">De lo contrario, es posible que experimente inestabilidad o puede que tenga que utilizar siempre las búsquedas o el cuadro de diálogo al especificar combinaciones de cuentas y dimensiones.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-125">Otherwise, you might experience instability, or you might always have to use lookups or the dialog box when you enter combinations of accounts and dimensions.</span></span> <span data-ttu-id="7f5ab-126">Para obtener más información, consulte [Crear una cuenta principal](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="7f5ab-126">For more information, see [Create a main account](tasks/create-main-account.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7f5ab-127">En Microsoft Dynamics for Finance and Operations versión 8.0 (abril de 2018), puede modificar el delimitador del plan de cuentas desde la página **Parámetros de contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-127">In Microsoft Dynamics for Finance and Operations version 8.0 (April 2018), you can modify the chart of accounts delimiter from the **General ledger parameters** page.</span></span>

<span data-ttu-id="7f5ab-128">Conviene vincular cuentas principales a categorías de cuenta principal, de modo que pueda aprovecharse la ventaja de usar los informes financieros predeterminados sin tener que realizar ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-128">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="7f5ab-129">Por lo tanto, puede diseñar y mantener más rápida y fácilmente los informes.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-129">Therefore, you can more quickly and easily design and maintain reports.</span></span>

<span data-ttu-id="7f5ab-130">Cree una estructura contable en la página **Configurar estructuras contables**.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-130">You create account structures on the **Configure account structures** page.</span></span> <span data-ttu-id="7f5ab-131">Las estructuras contables definen combinaciones válidas.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-131">Account structures define valid combinations.</span></span> <span data-ttu-id="7f5ab-132">Estas combinaciones, junto con las cuentas principales, forman el plan contable.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-132">These combinations, together with main accounts, form a chart of accounts.</span></span> <span data-ttu-id="7f5ab-133">Para obtener más información, consulte [Crear una estructura contable](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="7f5ab-133">For more information, see [Create account structures](tasks/create-account-structures.md).</span></span>

<span data-ttu-id="7f5ab-134">**Anulaciones de entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="7f5ab-134">**Legal entity overrides**</span></span>

<span data-ttu-id="7f5ab-135">No todas las cuentas principales son válidas para todas las entidades jurídicas y algunas cuentas principales solo pueden ser relevantes para un período específico.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-135">Not all main accounts are valid for all legal entities, and some main account might be relevant only for a specific period.</span></span> <span data-ttu-id="7f5ab-136">En estos casos, puede usar la sección **Anulaciones de entidad jurídica** para identificar las empresas para las que se debe suspender la cuenta principal, el propietario y el período de tiempo que la dimensión está activa.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-136">In this scenario, you can use the **Legal entity overrides** section to identify the companies that the main account should be suspended for, the owner, and the period when the dimension is active.</span></span> <span data-ttu-id="7f5ab-137">Las anulaciones en el nivel compartido no pueden ser más restrictivas que las anulaciones en el nivel de entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="7f5ab-137">The overrides at the shared level can't be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="7f5ab-138">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="7f5ab-138">For more information, see the following topics:</span></span>

- [<span data-ttu-id="7f5ab-139">Dimensiones financieras</span><span class="sxs-lookup"><span data-stu-id="7f5ab-139">Financial dimensions</span></span>](financial-dimensions.md)
- [<span data-ttu-id="7f5ab-140">Crear y asignar estructuras de reglas avanzadas</span><span class="sxs-lookup"><span data-stu-id="7f5ab-140">Create and assign advanced rule structures</span></span>](tasks/create-assign-advanced-rule-structures.md)


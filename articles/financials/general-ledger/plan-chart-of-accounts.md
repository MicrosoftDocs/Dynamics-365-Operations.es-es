---
title: Planificar su plan de cuentas
description: "Este artículo proporciona información que le ayudará a planificar el plan de cuenta para su organización."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 848da7ec8f4a7915f3b78945b808b564f4510434
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="2d7be-103">Planificar su plan de cuentas</span><span class="sxs-lookup"><span data-stu-id="2d7be-103">Plan your chart of accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2d7be-104">Este artículo proporciona información que le ayudará a planificar el plan de cuenta para su organización.</span><span class="sxs-lookup"><span data-stu-id="2d7be-104">This article provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="2d7be-105">Puede configurar un plan de cuentas para hacer un seguimiento de la información financiera de una organización y mantenerla.</span><span class="sxs-lookup"><span data-stu-id="2d7be-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="2d7be-106">El plan de cuentas es un conjunto de cuentas que definen un marco financiero.</span><span class="sxs-lookup"><span data-stu-id="2d7be-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="2d7be-107">Para realizar un seguimiento más exhaustivo de las transacciones de estas cuentas, puede agregar segmentos denominados "dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="2d7be-107">To further track the transactions in these accounts, you can add segments, which are known as financial dimensions.</span></span> <span data-ttu-id="2d7be-108">Por ejemplo, una cuenta de gastos puede incluir dimensiones financieras denominadas Departamento, Centro de coste y Propósito.</span><span class="sxs-lookup"><span data-stu-id="2d7be-108">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="2d7be-109">Las reglas que define el usuario, también denominadas "estructuras contables" y "reglas avanzadas", determinan la forma de vincular las dimensiones financieras a las cuentas principales y a otras dimensiones financieras, así como la forma de introducir transacciones financieras.</span><span class="sxs-lookup"><span data-stu-id="2d7be-109">User-defined rules, which are known as account structures and advanced rules, determine how financial dimensions are attached to the main accounts and other financial dimensions, and also how transactions are entered.</span></span> 

<span data-ttu-id="2d7be-110">El plan contable es una lista estructurada de las cuentas de contabilidad general de una entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="2d7be-110">The chart of accounts is a structured list of a legal entity’s general ledger accounts.</span></span> <span data-ttu-id="2d7be-111">Esta lista se utiliza para preparar informes financieros para autoridades y propietarios.</span><span class="sxs-lookup"><span data-stu-id="2d7be-111">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="2d7be-112">Las cuentas se agrupan en tipos de cuentas que se agregan después en categorías más grandes.</span><span class="sxs-lookup"><span data-stu-id="2d7be-112">The accounts are grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="2d7be-113">En el nivel más general, las cuentas se agrupan en ingresos y costes (cuentas operativas) y activos y pasivos (cuentas de saldo).</span><span class="sxs-lookup"><span data-stu-id="2d7be-113">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span> 

<span data-ttu-id="2d7be-114">Cualquier entidad jurídica de una organización puede usar y compartir un plan contable.</span><span class="sxs-lookup"><span data-stu-id="2d7be-114">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="2d7be-115">El plan contable utilizado por una entidad jurídica se define en la página **Libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="2d7be-115">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span> 

<span data-ttu-id="2d7be-116">Estos son algunos de los factores que se deben tener en cuenta la hora de planificar la estructura del plan de cuentas en la organización:</span><span class="sxs-lookup"><span data-stu-id="2d7be-116">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

-   <span data-ttu-id="2d7be-117">Los requisitos de informes del país o región en que está situada la organización</span><span class="sxs-lookup"><span data-stu-id="2d7be-117">The reporting requirements of the country/region where your organization is based</span></span>
-   <span data-ttu-id="2d7be-118">Los requisitos de informes de la entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="2d7be-118">The reporting requirements of your legal entity</span></span>
-   <span data-ttu-id="2d7be-119">El grado de especificación necesario, para las organizaciones externas y para la propia.</span><span class="sxs-lookup"><span data-stu-id="2d7be-119">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="2d7be-120">Cree el plan de cuentas en la página **Plan de cuentas**.</span><span class="sxs-lookup"><span data-stu-id="2d7be-120">Create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="2d7be-121">Las cuentas principales se pueden crear desde la página **Plan de cuentas** o la página **Cuentas principales**.</span><span class="sxs-lookup"><span data-stu-id="2d7be-121">Main accounts can be created from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="2d7be-122">Sus cuentas principales no deben usar ninguno de los caracteres especiales que se usan como delimitadores en los planes de cuentas.</span><span class="sxs-lookup"><span data-stu-id="2d7be-122">Your main accounts shouldn't use any special characters that are used as chart of accounts delimiters.</span></span> <span data-ttu-id="2d7be-123">Si hay un carácter especial igual al delimitador del plan de cuentas, puede haber inestabilidad o puede ser necesario usar siempre búsquedas o elementos emergentes al especificar las combinaciones de las combinaciones y las cuentas.</span><span class="sxs-lookup"><span data-stu-id="2d7be-123">If you do have a special character that is the same as your chart of accounts delimiter, you may experience instability, or the need to always use lookups or the flyout when entering account and dimension combinations.</span></span> <span data-ttu-id="2d7be-124">Para obtener más información, consulte [Crear una cuenta principal](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="2d7be-124">For more information, see [Create a main account](tasks/create-account-structures.md).</span></span>


<span data-ttu-id="2d7be-125">Conviene vincular cuentas principales a categorías de cuenta principal, de modo que pueda aprovecharse la ventaja de usar los informes financieros predeterminados sin tener que realizar ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="2d7be-125">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="2d7be-126">Por lo tanto, puede diseñar y mantener más rápida y fácilmente los informes.</span><span class="sxs-lookup"><span data-stu-id="2d7be-126">Therefore, you can more quickly and easily design and maintain reports.</span></span> 

<span data-ttu-id="2d7be-127">Use la página **Configurar estructuras contables** para crear estructuras contables.</span><span class="sxs-lookup"><span data-stu-id="2d7be-127">Use the **Configure account structures** page to create account structures.</span></span> <span data-ttu-id="2d7be-128">Las estructuras contables definen combinaciones válidas.</span><span class="sxs-lookup"><span data-stu-id="2d7be-128">Account structures define valid combinations.</span></span> <span data-ttu-id="2d7be-129">Las combinaciones, junto con las cuentas principales, forman el plan contable.</span><span class="sxs-lookup"><span data-stu-id="2d7be-129">The combinations, together with main accounts, form a chart of accounts.</span></span>  <span data-ttu-id="2d7be-130">Para obtener más información, consulte [Crear una estructura contable](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="2d7be-130">For more information, see [Create account structures](tasks/create-main-account.md).</span></span>

<span data-ttu-id="2d7be-131">**Anulaciones de entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="2d7be-131">**Legal entity overrides**</span></span> 

<span data-ttu-id="2d7be-132">No todas las cuentas principales son válidas para todas las entidades jurídicas, y algunas solo pueden ser relevantes para un período de tiempo específico.</span><span class="sxs-lookup"><span data-stu-id="2d7be-132">Not all main accounts are valid for all legal entities and some may only be relevant for a specific time period.</span></span> <span data-ttu-id="2d7be-133">En esta situación, puede usarse la sección Anulaciones de entidad jurídica para identificar para qué empresas se debe suspender la cuenta principal, quién es el propietario y el período de tiempo que la dimensión está activa.</span><span class="sxs-lookup"><span data-stu-id="2d7be-133">In this scenario the Legal entity overrides section can be used to identify which companies the main account should be suspended for, who the owner is and the time period the dimension is active.</span></span> <span data-ttu-id="2d7be-134">Las anulaciones en el nivel compartido no pueden ser más restrictivas que las anulaciones en el nivel de entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="2d7be-134">The overrides at the shared level cannot be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="2d7be-135">Para obtener más información, consulte los siguientes temas: [Dimensiones financieras](financial-dimensions.md)
[Crear y asignar las estructuras de regla avanzada](tasks/create-assign-advanced-rule-structures.md)</span><span class="sxs-lookup"><span data-stu-id="2d7be-135">For more information, see the following topics: [Financial dimensions](financial-dimensions.md)
[Create and assign advanced rule structures](tasks/create-assign-advanced-rule-structures.md)</span></span>





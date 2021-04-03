---
title: Visión general de la contabilidad general y los informes financieros
description: Use Contabilidad general para definir y gestionar los registros financieros de la entidad jurídica.
author: ShylaThompson
manager: AnnBe
ms.date: 08/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3fc00cc29e37c853d7cabfa928d8e069c40a581
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249200"
---
# <a name="general-ledger-home-page"></a><span data-ttu-id="f5119-103">Página principal de contabilidad general</span><span class="sxs-lookup"><span data-stu-id="f5119-103">General ledger home page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5119-104">Use Contabilidad general para definir y gestionar los registros financieros de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="f5119-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="f5119-105">La contabilidad general es un registro de entradas de débito y de crédito.</span><span class="sxs-lookup"><span data-stu-id="f5119-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="f5119-106">Estas entradas se clasifican usando las cuentas indicadas en un gráfico de cuentas.</span><span class="sxs-lookup"><span data-stu-id="f5119-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="f5119-107">Planificar su plan de cuentas</span><span class="sxs-lookup"><span data-stu-id="f5119-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="f5119-108">Tipos de cuentas principales</span><span class="sxs-lookup"><span data-stu-id="f5119-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="f5119-109">Puede asignar, o distribuir, importes monetarios a una o varias cuentas o combinaciones de cuenta y dimensión según reglas de asignación.</span><span class="sxs-lookup"><span data-stu-id="f5119-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="f5119-110">Existen dos tipos de asignaciones: fija y variable.</span><span class="sxs-lookup"><span data-stu-id="f5119-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="f5119-111">También puede liquidar transacciones entre cuentas contables y revalorizar importes de divisa.</span><span class="sxs-lookup"><span data-stu-id="f5119-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="f5119-112">Al final de un ejercicio, se deben generar las transacciones de cierre y preparar las cuentas para el ejercicio siguiente.</span><span class="sxs-lookup"><span data-stu-id="f5119-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="f5119-113">Puede usar la funcionalidad de consolidación para combinar los resultados financieros para varias entidades jurídicas filiales en resultados para una organización única y consolidada.</span><span class="sxs-lookup"><span data-stu-id="f5119-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="f5119-114">Las filiales pueden estar en la misma base de datos o en bases de datos independientes.</span><span class="sxs-lookup"><span data-stu-id="f5119-114">The subsidiaries can be in the same database or in separate databases.</span></span>

- [<span data-ttu-id="f5119-115">Visión general de consolidación y eliminación</span><span class="sxs-lookup"><span data-stu-id="f5119-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="f5119-116">Saldos de cuentas de contabilidad</span><span class="sxs-lookup"><span data-stu-id="f5119-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="f5119-117">Dimensiones financieras</span><span class="sxs-lookup"><span data-stu-id="f5119-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="f5119-118">[![Proceso empresarial](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="f5119-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="f5119-119">Impuestos</span><span class="sxs-lookup"><span data-stu-id="f5119-119">Sales tax</span></span>
<span data-ttu-id="f5119-120">Las empresas cobran y pagan impuestos a diversas autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="f5119-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="f5119-121">Las reglas y los porcentajes varían en función del país o región, la comunidad autónoma, la provincia y la ciudad.</span><span class="sxs-lookup"><span data-stu-id="f5119-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="f5119-122">Además, las reglas se deben actualizar periódicamente cuando las autoridades fiscales cambien sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="f5119-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="f5119-123">Los códigos de impuestos contienen información básica acerca de cuánto cobra y paga a las autoridades.</span><span class="sxs-lookup"><span data-stu-id="f5119-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="f5119-124">Al configurar códigos de impuestos, define los importes o porcentajes que se deben cobrar.</span><span class="sxs-lookup"><span data-stu-id="f5119-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="f5119-125">También define los distintos métodos que permiten aplicar dichos importes o porcentajes a los importes de la transacción.</span><span class="sxs-lookup"><span data-stu-id="f5119-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="f5119-126">En los temas de esta sección se proporciona información sobre la configuración de códigos de impuestos para los métodos y los porcentajes que requieren las autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="f5119-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="f5119-127">Visión general de impuestos</span><span class="sxs-lookup"><span data-stu-id="f5119-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="f5119-128">Índices de impuestos en función de la base marginal y los métodos de cálculo</span><span class="sxs-lookup"><span data-stu-id="f5119-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="f5119-129">Pagos de impuestos y reglas de redondeo</span><span class="sxs-lookup"><span data-stu-id="f5119-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="f5119-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f5119-130">Additional resources</span></span>

#### <a name="whats-new-and-in-development"></a><span data-ttu-id="f5119-131">Novedades y características en desarrollo</span><span class="sxs-lookup"><span data-stu-id="f5119-131">What's new and in development</span></span>

<span data-ttu-id="f5119-132">Vaya a las [Planes de la versión de Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158) para ver las nuevas características que se han planificado.</span><span class="sxs-lookup"><span data-stu-id="f5119-132">Go to the [Microsoft Dynamics 365 release plans](https://go.microsoft.com/fwlink/?linkid=2010158) to see what new features have been planned.</span></span> 

#### <a name="financial-reporting"></a><span data-ttu-id="f5119-133">Informes financieros</span><span class="sxs-lookup"><span data-stu-id="f5119-133">Financial reporting</span></span>
<span data-ttu-id="f5119-134">Vaya al tema [Visión general de Financial Reporting](../../fin-ops-core/dev-itpro/analytics/financial-reporting-intro.md) para obtener información sobre los informes financieros.</span><span class="sxs-lookup"><span data-stu-id="f5119-134">Go to the [Financial reporting overview](../../fin-ops-core/dev-itpro/analytics/financial-reporting-intro.md) topic for information about financial reports.</span></span>

#### <a name="blogs"></a><span data-ttu-id="f5119-135">Blogs</span><span class="sxs-lookup"><span data-stu-id="f5119-135">Blogs</span></span>

<span data-ttu-id="f5119-136">Puede encontrar opiniones, noticias y otra información en el [blog de Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) y el [blog de Microsoft Dynamics 365 Finance and Operations - Financials](https://community.dynamics.com/365/financeandoperations/b/financials).</span><span class="sxs-lookup"><span data-stu-id="f5119-136">You can find opinions, news, and other information on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) and the [Microsoft Dynamics 365 Finance and Operations - Financials blog](https://community.dynamics.com/365/financeandoperations/b/financials).</span></span>

<span data-ttu-id="f5119-137">El [blog de la comunidad Microsoft Dynamics Operations Partner](https://community.dynamics.com/partner/b/operationspartnercommunityblog) proporciona a los socios de Microsoft Dynamics un único recurso desde el que obtener información sobre las novedades y tendencias de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f5119-137">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in Dynamics 365.</span></span>

### <a name="videos"></a><span data-ttu-id="f5119-138">Vídeos</span><span class="sxs-lookup"><span data-stu-id="f5119-138">Videos</span></span>

<span data-ttu-id="f5119-139">Consulte los vídeos de procedimientos que se encuentran ahora disponibles en el [canal de YouTube de Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span><span class="sxs-lookup"><span data-stu-id="f5119-139">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="f5119-140">Blogs de la comunidad</span><span class="sxs-lookup"><span data-stu-id="f5119-140">Community blogs</span></span>

- [<span data-ttu-id="f5119-141">Qué debería saber sobre libro mayor en Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f5119-141">What you should know about ledger in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
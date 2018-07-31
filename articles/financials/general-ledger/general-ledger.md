---
title: "Página de inicio de Contabilidad general e Informes financieros"
description: "Use Contabilidad general para definir y gestionar los registros financieros de la entidad jurídica."
author: twheeloc
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 03bab1d03be71c0e23a6ea93f542d6a52a212a1f
ms.openlocfilehash: 9ee3f73cd11b38ed2237ea3fe08db18000e55f07
ms.contentlocale: es-es
ms.lasthandoff: 06/25/2018

---

# <a name="general-ledger"></a><span data-ttu-id="7c8d8-103">Contabilidad general</span><span class="sxs-lookup"><span data-stu-id="7c8d8-103">General ledger</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c8d8-104">Use Contabilidad general para definir y gestionar los registros financieros de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="7c8d8-105">La contabilidad general es un registro de entradas de débito y de crédito.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="7c8d8-106">Estas entradas se clasifican usando las cuentas indicadas en un gráfico de cuentas.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="7c8d8-107">Planificar su plan de cuentas</span><span class="sxs-lookup"><span data-stu-id="7c8d8-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="7c8d8-108">Tipos de cuentas principales</span><span class="sxs-lookup"><span data-stu-id="7c8d8-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="7c8d8-109">Puede asignar, o distribuir, importes monetarios a una o varias cuentas o combinaciones de cuenta y dimensión según reglas de asignación.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="7c8d8-110">Existen dos tipos de asignaciones: fija y variable.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="7c8d8-111">También puede liquidar transacciones entre cuentas contables y revalorizar importes de divisa.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="7c8d8-112">Al final de un ejercicio, se deben generar las transacciones de cierre y preparar las cuentas para el ejercicio siguiente.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="7c8d8-113">Puede usar la funcionalidad de consolidación para combinar los resultados financieros para varias entidades jurídicas filiales en resultados para una organización única y consolidada.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="7c8d8-114">Las filiales pueden estar en la misma base de datos de Microsoft Dynamics 365 for Finance and Operations o en bases de datos independientes.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

- [<span data-ttu-id="7c8d8-115">Visión general de consolidación y eliminación</span><span class="sxs-lookup"><span data-stu-id="7c8d8-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="7c8d8-116">Saldos de cuentas de contabilidad</span><span class="sxs-lookup"><span data-stu-id="7c8d8-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="7c8d8-117">Dimensiones financieras</span><span class="sxs-lookup"><span data-stu-id="7c8d8-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="7c8d8-118">[![Proceso empresarial](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="7c8d8-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="7c8d8-119">Impuestos</span><span class="sxs-lookup"><span data-stu-id="7c8d8-119">Sales tax</span></span>
<span data-ttu-id="7c8d8-120">Las empresas cobran y pagan impuestos a diversas autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="7c8d8-121">Las reglas y los porcentajes varían en función del país o región, la comunidad autónoma, la provincia y la ciudad.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="7c8d8-122">Además, las reglas se deben actualizar periódicamente cuando las autoridades fiscales cambien sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="7c8d8-123">Los códigos de impuestos contienen información básica acerca de cuánto cobra y paga a las autoridades.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="7c8d8-124">Al configurar códigos de impuestos, define los importes o porcentajes que se deben cobrar.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="7c8d8-125">También define los distintos métodos que permiten aplicar dichos importes o porcentajes a los importes de la transacción.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="7c8d8-126">En los temas de esta sección se proporciona información sobre la configuración de códigos de impuestos para los métodos y los porcentajes que requieren las autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="7c8d8-127">Visión general de impuestos</span><span class="sxs-lookup"><span data-stu-id="7c8d8-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="7c8d8-128">Índices de impuestos en función de la base marginal y los métodos de cálculo</span><span class="sxs-lookup"><span data-stu-id="7c8d8-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="7c8d8-129">Pagos de impuestos y reglas de redondeo</span><span class="sxs-lookup"><span data-stu-id="7c8d8-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="7c8d8-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7c8d8-130">Additional resources</span></span>

### <a name="whats-new"></a><span data-ttu-id="7c8d8-131">Novedades</span><span class="sxs-lookup"><span data-stu-id="7c8d8-131">What's new</span></span>

<span data-ttu-id="7c8d8-132">Vaya a las [Notas de la versión](https://docs.microsoft.com/en-us/business-applications-release-notes/) para ver las nuevas funciones que se han liberado.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-132">Go to the [Release notes](https://docs.microsoft.com/en-us/business-applications-release-notes/) to see what new features have been released.</span></span> 

### <a name="videos"></a><span data-ttu-id="7c8d8-133">Vídeos</span><span class="sxs-lookup"><span data-stu-id="7c8d8-133">Videos</span></span>

<span data-ttu-id="7c8d8-134">Consulte los vídeos de procedimientos que se encuentran ahora disponibles en el [canal de YouTube de Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span><span class="sxs-lookup"><span data-stu-id="7c8d8-134">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

### <a name="blogs"></a><span data-ttu-id="7c8d8-135">Blogs</span><span class="sxs-lookup"><span data-stu-id="7c8d8-135">Blogs</span></span>

<span data-ttu-id="7c8d8-136">Puede encontrar opiniones, noticias y otra información sobre Proveedores y otras soluciones en el [blog Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).</span><span class="sxs-lookup"><span data-stu-id="7c8d8-136">You can find opinions, news, and other information about Accounts payable and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).</span></span>

<span data-ttu-id="7c8d8-137">Hay muchas publicaciones sobre el libro de contabilidad general en el [blog del equipo del producto Microsoft Dynamics AX](https://blogs.msdn.microsoft.com/dax/).</span><span class="sxs-lookup"><span data-stu-id="7c8d8-137">There are many posts about General ledger on the [Microsoft Dynamics AX product team blog](https://blogs.msdn.microsoft.com/dax/).</span></span> <span data-ttu-id="7c8d8-138">Aunque la mayoría de ellos se escribieron para la versión anterior de del libro de contabilidad general, aún se aplican los mismos conceptos y, en la versión actual, los procedimientos son también similares.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-138">Although some of these posts were written for the previous version of General ledger, the same concepts still apply, and the procedures are also similar in the current version.</span></span>

<span data-ttu-id="7c8d8-139">El [blog de la comunidad Microsoft Dynamics Operations Partner](https://community.dynamics.com/partner/b/operationspartnercommunityblog) proporciona a los socios de Microsoft Dynamics un único recurso desde el que obtener información sobre las novedades y tendencias de MBS Operations.</span><span class="sxs-lookup"><span data-stu-id="7c8d8-139">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="7c8d8-140">Blogs de la comunidad</span><span class="sxs-lookup"><span data-stu-id="7c8d8-140">Community blogs</span></span>

- [<span data-ttu-id="7c8d8-141">Lo que debe saber sobre el libro mayor en Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7c8d8-141">What you should know about ledger in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)



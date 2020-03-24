---
title: Libro mayor integrado
description: Este tema describe la integración de datos del libro mayor entre Finance and Operations y otras aplicaciones de Dynamics 365 mediante Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: d9bcec1d4bb0207a2c3e0d46f7661b666fea3736
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112223"
---
# <a name="integrated-ledger"></a><span data-ttu-id="a3147-103">Libro mayor integrado</span><span class="sxs-lookup"><span data-stu-id="a3147-103">Integrated ledger</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="a3147-104">En una aplicación empresarial, los datos de contabilidad definen la configuración básica acerca de cómo una empresa hace negocios.</span><span class="sxs-lookup"><span data-stu-id="a3147-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="a3147-105">Por ejemplo, los datos de contabilidad describen el ejercicio que la empresa sigue, las divisas con las que hace transacciones y las cuentas que utiliza.</span><span class="sxs-lookup"><span data-stu-id="a3147-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="a3147-106">Este tema describe la integración de estos datos financieros básicos.</span><span class="sxs-lookup"><span data-stu-id="a3147-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="a3147-107">Plantillas</span><span class="sxs-lookup"><span data-stu-id="a3147-107">Templates</span></span>

<span data-ttu-id="a3147-108">Los datos de contabilidad incluyen una colección de mapas de entidad financiera básicos que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a3147-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="a3147-109">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a3147-109">Finance and Operations apps</span></span>      | <span data-ttu-id="a3147-110">Aplicación basadas en modelos en Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a3147-110">Model-driven app in Dynamics 365</span></span> | <span data-ttu-id="a3147-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3147-111">Description</span></span>
---------------------------------|----------------------------------|------------
<span data-ttu-id="a3147-112">Divisas</span><span class="sxs-lookup"><span data-stu-id="a3147-112">Currencies</span></span>                       | <span data-ttu-id="a3147-113">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="a3147-113">transactioncurrencies</span></span>            |
<span data-ttu-id="a3147-114">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="a3147-114">FiscalCalendar</span></span>                   | <span data-ttu-id="a3147-115">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="a3147-115">msdyn\_fiscalcalendars</span></span>        |
<span data-ttu-id="a3147-116">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="a3147-116">FiscalCalendarYear</span></span>               | <span data-ttu-id="a3147-117">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="a3147-117">msdyn\_fiscalcalendaryears</span></span>        |
<span data-ttu-id="a3147-118">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="a3147-118">ExchRateType</span></span>                     | <span data-ttu-id="a3147-119">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="a3147-119">msdyn\_exchangeratetypes</span></span>        |
<span data-ttu-id="a3147-120">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="a3147-120">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="a3147-121">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="a3147-121">msdyn\_currencyexchangeratepairs</span></span>        |
<span data-ttu-id="a3147-122">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="a3147-122">FiscalPeriodEntity</span></span>               | <span data-ttu-id="a3147-123">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="a3147-123">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="a3147-124">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="a3147-124">MainAccountCategory</span></span>              | <span data-ttu-id="a3147-125">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="a3147-125">msdyn\_mainaccountcategory</span></span>        |
<span data-ttu-id="a3147-126">MainAccount</span><span class="sxs-lookup"><span data-stu-id="a3147-126">MainAccount</span></span>                      | <span data-ttu-id="a3147-127">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="a3147-127">msdyn\_mainaccounts</span></span>        |
<span data-ttu-id="a3147-128">Contabilidad</span><span class="sxs-lookup"><span data-stu-id="a3147-128">Ledger</span></span>                           | <span data-ttu-id="a3147-129">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="a3147-129">msdyn\_ledgers</span></span>        |
<span data-ttu-id="a3147-130">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="a3147-130">ExchangeRates</span></span>                    | <span data-ttu-id="a3147-131">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="a3147-131">msdyn\_currencyexchangerates</span></span>        |
<span data-ttu-id="a3147-132">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="a3147-132">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="a3147-133">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="a3147-133">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="a3147-134">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="a3147-134">DimensionAttributeEntity</span></span>         | <span data-ttu-id="a3147-135">msdyn\_dimensionattributes</span><span class="sxs-lookup"><span data-stu-id="a3147-135">msdyn\_dimensionattributes</span></span>        |
<span data-ttu-id="a3147-136">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="a3147-136">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="a3147-137">msdyn\_financialdimensionformats</span><span class="sxs-lookup"><span data-stu-id="a3147-137">msdyn\_financialdimensionformats</span></span>        |
<span data-ttu-id="a3147-138">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="a3147-138">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="a3147-139">msdyn\_chartofaccounts</span><span class="sxs-lookup"><span data-stu-id="a3147-139">msdyn\_chartofaccounts</span></span>        |


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](includes/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](includes/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](includes/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](includes/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Ledger fiscal periods](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Main account category](includes/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](includes/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](includes/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](includes/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](includes/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](includes/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](includes/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]





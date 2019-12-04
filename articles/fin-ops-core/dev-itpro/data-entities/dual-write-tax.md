---
title: Impuestos integrados
description: Este tema describe la integración de datos de impuestos entre Finance and Operations y Common Data Service.
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
ms.openlocfilehash: b6be53e9a2065373ca37c2791568a8161823803f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772419"
---
## <a name="integrated-tax"></a><span data-ttu-id="5639d-103">Impuestos integrados</span><span class="sxs-lookup"><span data-stu-id="5639d-103">Integrated tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5639d-104">Los datos de configuración de impuestos definen la configuración para los impuestos indirectos (IVA, impuestos, GST) y la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="5639d-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="5639d-105">Describe la regla de cálculo del impuesto, el índice de impuestos, la contabilidad del impuesto, su liquidación y otros conceptos.</span><span class="sxs-lookup"><span data-stu-id="5639d-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="5639d-106">Plantillas</span><span class="sxs-lookup"><span data-stu-id="5639d-106">Templates</span></span>

<span data-ttu-id="5639d-107">Los datos de los impuestos incluyen una colección de mapas de entidad que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5639d-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="5639d-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5639d-108">Finance and Operations</span></span>   | <span data-ttu-id="5639d-109">Aplicación Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="5639d-109">Customer Engagement application</span></span>
-------------------------|---------------------------------
<span data-ttu-id="5639d-110">Códigos de impuestos</span><span class="sxs-lookup"><span data-stu-id="5639d-110">Tax codes</span></span>                  | <span data-ttu-id="5639d-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="5639d-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="5639d-112">Grupos de impuestos</span><span class="sxs-lookup"><span data-stu-id="5639d-112">Tax groups</span></span>               | <span data-ttu-id="5639d-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="5639d-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="5639d-114">Grupos de artículos con impuestos</span><span class="sxs-lookup"><span data-stu-id="5639d-114">Tax item groups</span></span>          | <span data-ttu-id="5639d-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="5639d-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="5639d-116">Exenciones fiscales</span><span class="sxs-lookup"><span data-stu-id="5639d-116">Tax Exemptions</span></span>           | <span data-ttu-id="5639d-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="5639d-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="5639d-118">Autoridades fiscales</span><span class="sxs-lookup"><span data-stu-id="5639d-118">Tax Authorities</span></span>          | <span data-ttu-id="5639d-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="5639d-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="5639d-120">Códigos de retenciones de impuestos</span><span class="sxs-lookup"><span data-stu-id="5639d-120">Withholding tax codes</span></span>      | <span data-ttu-id="5639d-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="5639d-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="5639d-122">Grupos de retenciones de impuestos</span><span class="sxs-lookup"><span data-stu-id="5639d-122">Withholding tax groups</span></span>   | <span data-ttu-id="5639d-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="5639d-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="5639d-124">Grupo de cuentas contables de impuestos</span><span class="sxs-lookup"><span data-stu-id="5639d-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="5639d-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="5639d-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]


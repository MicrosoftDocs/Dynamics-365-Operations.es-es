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
ms.openlocfilehash: a4da37d45698290b40f6c72148f1500bef72127a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173094"
---
# <a name="integrated-tax"></a><span data-ttu-id="158cc-103">Impuestos integrados</span><span class="sxs-lookup"><span data-stu-id="158cc-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="158cc-104">Los datos de configuración de impuestos definen la configuración para los impuestos indirectos (IVA, impuestos, GST) y la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="158cc-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="158cc-105">Describe la regla de cálculo del impuesto, el índice de impuestos, la contabilidad del impuesto, su liquidación y otros conceptos.</span><span class="sxs-lookup"><span data-stu-id="158cc-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="158cc-106">Plantillas</span><span class="sxs-lookup"><span data-stu-id="158cc-106">Templates</span></span>

<span data-ttu-id="158cc-107">Los datos de los impuestos incluyen una colección de mapas de entidad que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="158cc-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="158cc-108">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="158cc-108">Finance and Operations apps</span></span> | <span data-ttu-id="158cc-109">Aplicaciones basadas en modelos en Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="158cc-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="158cc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="158cc-110">Description</span></span> |
-------------------------|---------------------------------
<span data-ttu-id="158cc-111">Códigos de impuestos</span><span class="sxs-lookup"><span data-stu-id="158cc-111">Tax codes</span></span>                   | <span data-ttu-id="158cc-112">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="158cc-112">msdyn\_taxcodes.md</span></span> | 
<span data-ttu-id="158cc-113">Grupos de impuestos</span><span class="sxs-lookup"><span data-stu-id="158cc-113">Tax groups</span></span>                 | <span data-ttu-id="158cc-114">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="158cc-114">msdyn\_taxgroups.md</span></span> | 
<span data-ttu-id="158cc-115">Grupos de artículos con impuestos</span><span class="sxs-lookup"><span data-stu-id="158cc-115">Tax item groups</span></span>             | <span data-ttu-id="158cc-116">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="158cc-116">msdyn\_taxitemgroups.md</span></span> | 
<span data-ttu-id="158cc-117">Exenciones fiscales</span><span class="sxs-lookup"><span data-stu-id="158cc-117">Tax Exemptions</span></span>             | <span data-ttu-id="158cc-118">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="158cc-118">msdyn\_taxexemptcodes.md</span></span> | 
<span data-ttu-id="158cc-119">Autoridades fiscales</span><span class="sxs-lookup"><span data-stu-id="158cc-119">Tax Authorities</span></span>             | <span data-ttu-id="158cc-120">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="158cc-120">msdyn\_taxauthorities.md</span></span> | 
<span data-ttu-id="158cc-121">Códigos de retenciones de impuestos</span><span class="sxs-lookup"><span data-stu-id="158cc-121">Withholding tax codes</span></span>       | <span data-ttu-id="158cc-122">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="158cc-122">msdyn\_withholdingtaxcodes.md</span></span> | 
<span data-ttu-id="158cc-123">Grupos de retenciones de impuestos</span><span class="sxs-lookup"><span data-stu-id="158cc-123">Withholding tax groups</span></span>     | <span data-ttu-id="158cc-124">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="158cc-124">msdyn\_withholdingtaxgroups.md</span></span> | 
<span data-ttu-id="158cc-125">Grupo de cuentas contables de impuestos</span><span class="sxs-lookup"><span data-stu-id="158cc-125">Tax Ledger Account Group</span></span> | <span data-ttu-id="158cc-126">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="158cc-126">msdyn\_taxpostinggroups</span></span>     | 

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]


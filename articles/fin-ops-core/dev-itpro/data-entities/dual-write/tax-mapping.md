---
title: Impuestos integrados
description: Este tema describe la integración de datos de impuestos entre Finance and Operations y Dataverse.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 7501ef21492a96c81b971e1d9077beaba9be897b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560346"
---
# <a name="integrated-tax"></a><span data-ttu-id="e5bf0-103">Impuestos integrados</span><span class="sxs-lookup"><span data-stu-id="e5bf0-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="e5bf0-104">Los datos de configuración de impuestos definen la configuración para los impuestos indirectos (IVA, impuestos, GST) y la retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="e5bf0-105">Describe la regla de cálculo del impuesto, el índice de impuestos, la contabilidad del impuesto, su liquidación y otros conceptos.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="e5bf0-106">Plantillas</span><span class="sxs-lookup"><span data-stu-id="e5bf0-106">Templates</span></span>

<span data-ttu-id="e5bf0-107">Los datos de los impuestos incluyen una colección de mapas de tabla que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-107">Tax data includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="e5bf0-108">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e5bf0-108">Finance and Operations apps</span></span> | <span data-ttu-id="e5bf0-109">Aplicaciones basadas en modelos en Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e5bf0-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="e5bf0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5bf0-110">Description</span></span> |
-------------------------|---------------------------------|----|
<span data-ttu-id="e5bf0-111">Grupo de impuestos de artículos</span><span class="sxs-lookup"><span data-stu-id="e5bf0-111">Item sales tax group</span></span> | <span data-ttu-id="e5bf0-112">msdyn_taxitemgroups</span><span class="sxs-lookup"><span data-stu-id="e5bf0-112">msdyn_taxitemgroups</span></span> |
<span data-ttu-id="e5bf0-113">Autoridades fiscales</span><span class="sxs-lookup"><span data-stu-id="e5bf0-113">Sales tax authorities</span></span> | <span data-ttu-id="e5bf0-114">msdyn_taxauthorities</span><span class="sxs-lookup"><span data-stu-id="e5bf0-114">msdyn_taxauthorities</span></span> |
<span data-ttu-id="e5bf0-115">Entidad de código de exención de impuestos para CDS</span><span class="sxs-lookup"><span data-stu-id="e5bf0-115">Sales tax exempt code entity CDS</span></span> | <span data-ttu-id="e5bf0-116">msdyn_taxexemptcodes</span><span class="sxs-lookup"><span data-stu-id="e5bf0-116">msdyn_taxexemptcodes</span></span> |
<span data-ttu-id="e5bf0-117">Grupos de impuestos</span><span class="sxs-lookup"><span data-stu-id="e5bf0-117">Sales tax groups</span></span> | <span data-ttu-id="e5bf0-118">msdyn_taxgroups</span><span class="sxs-lookup"><span data-stu-id="e5bf0-118">msdyn_taxgroups</span></span> |
<span data-ttu-id="e5bf0-119">Grupos de registro contable de impuestos de ventas V2</span><span class="sxs-lookup"><span data-stu-id="e5bf0-119">Sales tax ledger posting groups V2</span></span> | <span data-ttu-id="e5bf0-120">msdyn_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="e5bf0-120">msdyn_taxpostinggroups</span></span> |
<span data-ttu-id="e5bf0-121">Códigos de retenciones de impuestos</span><span class="sxs-lookup"><span data-stu-id="e5bf0-121">Withholding tax codes</span></span> | <span data-ttu-id="e5bf0-122">msdyn_withholdingtaxcodes</span><span class="sxs-lookup"><span data-stu-id="e5bf0-122">msdyn_withholdingtaxcodes</span></span> |
<span data-ttu-id="e5bf0-123">Grupos de retenciones de impuestos</span><span class="sxs-lookup"><span data-stu-id="e5bf0-123">Withholding tax groups</span></span> | <span data-ttu-id="e5bf0-124">msdyn_withholdingtaxgroups</span><span class="sxs-lookup"><span data-stu-id="e5bf0-124">msdyn_withholdingtaxgroups</span></span> | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
---
title: Directivas de idoneidad para beneficio
description: Este artículo proporciona información acerca de las directivas de idoneidad de prestación, que le ayudan a definir quién es apto para las prestaciones específicas.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 87a080c47e34a3265afea6494ff1733dac5bc384
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053114"
---
# <a name="benefit-eligibility-policies"></a><span data-ttu-id="e7757-103">Directivas de idoneidad para prestaciones</span><span class="sxs-lookup"><span data-stu-id="e7757-103">Benefit eligibility policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e7757-104">Este artículo proporciona información acerca de las directivas de idoneidad de prestación, que le ayudan a definir quién es apto para las prestaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="e7757-104">This article provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="e7757-105">Cuando crea prestaciones, decide qué beneficios estarán disponibles para qué empleados.</span><span class="sxs-lookup"><span data-stu-id="e7757-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="e7757-106">En la tabla siguiente se muestran ejemplos de las prestaciones que puede poner a disposición de empleados específicos.</span><span class="sxs-lookup"><span data-stu-id="e7757-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="e7757-107">Prestación</span><span class="sxs-lookup"><span data-stu-id="e7757-107">Benefit</span></span>          | <span data-ttu-id="e7757-108">Para quién está disponible la prestación</span><span class="sxs-lookup"><span data-stu-id="e7757-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="e7757-109">Seguro médico</span><span class="sxs-lookup"><span data-stu-id="e7757-109">Health insurance</span></span> | <span data-ttu-id="e7757-110">Todos los empleados</span><span class="sxs-lookup"><span data-stu-id="e7757-110">All employees</span></span>                   |
| <span data-ttu-id="e7757-111">Teléfono móvil</span><span class="sxs-lookup"><span data-stu-id="e7757-111">Mobile phone</span></span>     | <span data-ttu-id="e7757-112">Personal de ventas, ejecutivos</span><span class="sxs-lookup"><span data-stu-id="e7757-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="e7757-113">Pases para aparcamiento</span><span class="sxs-lookup"><span data-stu-id="e7757-113">Parking passes</span></span>   | <span data-ttu-id="e7757-114">Ejecutivos</span><span class="sxs-lookup"><span data-stu-id="e7757-114">Executives</span></span>                      |

<span data-ttu-id="e7757-115">Se usan los siguientes componentes para crear directivas de idoneidad:</span><span class="sxs-lookup"><span data-stu-id="e7757-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="e7757-116">Tipos de reglas de directivas</span><span class="sxs-lookup"><span data-stu-id="e7757-116">Policy rule types</span></span>
-   <span data-ttu-id="e7757-117">Directivas de idoneidad para prestación</span><span class="sxs-lookup"><span data-stu-id="e7757-117">Benefit eligibility policies</span></span>

<span data-ttu-id="e7757-118">Los tipos de reglas de directivas definen los parámetros de consulta que se usan al desarrollar reglas de directivas específicas.</span><span class="sxs-lookup"><span data-stu-id="e7757-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="e7757-119">Tras crear tipos de reglas de directivas, puede crear directivas de idoneidad de prestación.</span><span class="sxs-lookup"><span data-stu-id="e7757-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="e7757-120">Las directivas le permiten crear una colección de reglas que se aplican a una o más entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="e7757-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="e7757-121">Dentro de cada directiva, puede ver cualquiera de los tipos de reglas de directivas de idoneidad de prestación que haya creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e7757-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="e7757-122">Define el ámbito de la regla dentro de la directiva.</span><span class="sxs-lookup"><span data-stu-id="e7757-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="e7757-123">Por ejemplo, si crea un tipo de regla de directivas de idoneidad de prestación que se llama **Ejecutivo**, puede especificar cuáles es la regla dentro de dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="e7757-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="e7757-124">En este ejemplo, la regla podría indicar que se debe incluir en la regla cualquier título de trabajo que contenga la palabra "ejecutivo".</span><span class="sxs-lookup"><span data-stu-id="e7757-124">In this example, the rule might state that any job title that contains the word "executive" should be included in the rule.</span></span> <span data-ttu-id="e7757-125">Una vez que haya definido los parámetros de la regla o las reglas que se incluyen en la directiva, puede asignar una regla específica a la prestación.</span><span class="sxs-lookup"><span data-stu-id="e7757-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>






[!INCLUDE[footer-include](../includes/footer-banner.md)]
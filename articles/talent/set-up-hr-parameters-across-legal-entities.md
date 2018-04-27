---
title: "Configurar parámetros de recursos humanos en entidades jurídicas"
description: "Debe configurar los parámetros compartidos para los registros que se comparten entre empresas, como registros de puesto. En este artículo se explica cómo configurar parámetros de recursos humanos entre entidades jurídicas."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2e73441a3f4190561d1d16db40ee1581267c8dfb
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-hr-parameters-across-legal-entities"></a><span data-ttu-id="eed0e-104">Configurar parámetros de recursos humanos en entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="eed0e-104">Set up HR parameters across legal entities</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="eed0e-105">Debe configurar los parámetros compartidos para los registros que se comparten entre empresas, como registros de puesto.</span><span class="sxs-lookup"><span data-stu-id="eed0e-105">You must set up shared parameters for records that are shared across companies, such as Position records.</span></span> <span data-ttu-id="eed0e-106">En este artículo se explica cómo configurar parámetros de recursos humanos entre entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="eed0e-106">This article explains how to set up Human resources parameters across legal entities.</span></span>

<span data-ttu-id="eed0e-107">Algunos tipos de registros, como Registros de puestos, se comparten entre las empresas.</span><span class="sxs-lookup"><span data-stu-id="eed0e-107">Some types of records, such as Position records, are shared across companies.</span></span> <span data-ttu-id="eed0e-108">Para estos registros, debe configurar los parámetros compartidos.</span><span class="sxs-lookup"><span data-stu-id="eed0e-108">For these records, you must set up shared parameters.</span></span> <span data-ttu-id="eed0e-109">Por ejemplo, puede usar la página **Parámetros compartidos de recursos humanos** para configurar los parámetros de recursos humanos entre entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="eed0e-109">For example, you use the **Human resources shared parameters** page to set up Human resources parameters across legal entities.</span></span> 

<span data-ttu-id="eed0e-110">En la página **Parámetros compartidos de recursos humanos**, los parámetros se agrupan en áreas, en función de su funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="eed0e-110">On the **Human resources shared parameters** page, parameters are grouped into areas, based on their functionality.</span></span> 

### <a name="previously-released-functionality"></a><span data-ttu-id="eed0e-111">Funcionalidad anteriormente liberada</span><span class="sxs-lookup"><span data-stu-id="eed0e-111">Previously released functionality</span></span>
<span data-ttu-id="eed0e-112">En la pestaña **Identificación**, debe seleccionar los tipos de identificación que representan los números de identificación enumerados en la página.</span><span class="sxs-lookup"><span data-stu-id="eed0e-112">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="eed0e-113">Debe configurar tipos de identificación para poder especificar la información de identificación para los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="eed0e-113">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="eed0e-114">La información sobre el número de seguridad social, el número de DNI, el número de identificación de salida y el código de identificación personal se mantiene en la página **Tipo de identificación**.</span><span class="sxs-lookup"><span data-stu-id="eed0e-114">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="eed0e-115">Para definir un nuevo tipo de identificación o revisar la lista de tipos existentes, haga clic en **Gestión del personal** &gt; **Ficha Vínculos** &gt; **Confirguración** &gt; **Tipos de identificación**.</span><span class="sxs-lookup"><span data-stu-id="eed0e-115">To define a new identification type or review the list of existing types, click **Personnel management** &gt; **Links tab** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="eed0e-116">Puede especificar una descripción y un código simples.</span><span class="sxs-lookup"><span data-stu-id="eed0e-116">You can enter a simple code and description.</span></span> 

### <a name="if-youre-using-dynamics-365-for-talent"></a><span data-ttu-id="eed0e-117">Si utiliza Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="eed0e-117">If you're using Dynamics 365 for Talent</span></span>
<span data-ttu-id="eed0e-118">En la pestaña **Identificación**, debe seleccionar los tipos de identificación que representan los números de identificación enumerados en la página.</span><span class="sxs-lookup"><span data-stu-id="eed0e-118">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="eed0e-119">Debe configurar tipos de identificación para poder especificar la información de identificación para los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="eed0e-119">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="eed0e-120">La información sobre el número de seguridad social, el número de DNI, el número de identificación de salida y el código de identificación personal se mantiene en la página **Tipo de identificación**.</span><span class="sxs-lookup"><span data-stu-id="eed0e-120">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="eed0e-121">Para definir un nuevo tipo de identificación o revisar la lista de tipos existentes, haga clic en **Recursos humanos** &gt; **Instalación** &gt; **Tipos de identificación**.</span><span class="sxs-lookup"><span data-stu-id="eed0e-121">To define a new identification type or review the list of existing types, click **Human resources** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="eed0e-122">Puede especificar una descripción y un código simples.</span><span class="sxs-lookup"><span data-stu-id="eed0e-122">You can enter a simple code and description.</span></span> 

<span data-ttu-id="eed0e-123">En la pestaña **Secuencias numéricas**, puede seleccionar las secuencias numéricas que se usan para los registros siguientes: número de personal, puesto, Id. de solicitud de usuario, documento I-9, candidato, discusión, Id. de prestación y acción de personal (si se permite a este tipo de registro).</span><span class="sxs-lookup"><span data-stu-id="eed0e-123">On the **Number sequences** tab, you can select the number sequences that are used for the following records: Personnel number, Position, User request ID, I-9 document, Applicant, Discussion, Benefit ID, and Personnel action (if this record type is enabled).</span></span> <span data-ttu-id="eed0e-124">Para mantener las referencias y los códigos de la secuencia numérica, use la página de lista **Secuencias numéricas**.</span><span class="sxs-lookup"><span data-stu-id="eed0e-124">To maintain number sequence references and codes, use the **Number sequences** list page.</span></span> <span data-ttu-id="eed0e-125">Para buscar esta página, use la fncionalidad de búsqueda de páginas.</span><span class="sxs-lookup"><span data-stu-id="eed0e-125">To find this page, use the page search feature.</span></span> 

<span data-ttu-id="eed0e-126">En la pestaña **Puestos**, indique si los nuevos puestos están disponibles para la asignación de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="eed0e-126">On the **Positions** tab, indicate whether new positions are available for assignment by default:</span></span>

-   <span data-ttu-id="eed0e-127">**Siempre:** no puede asignar trabajadores a los nuevos puestos cuando se crean los puestos.</span><span class="sxs-lookup"><span data-stu-id="eed0e-127">**Always** – You can assign workers to new positions when positions are created.</span></span> <span data-ttu-id="eed0e-128">Cuando se crean los puestos, la fecha y la hora **Disponibles para la asignación** en la pestaña **General** de la página **Puesto** se cambian automáticamente a la fecha y hora de la creación.</span><span class="sxs-lookup"><span data-stu-id="eed0e-128">When positions are created, the **Available for assignment** date and time on the **General** tab of the **Position** page are automatically set to the creation date and time.</span></span>
-   <span data-ttu-id="eed0e-129">**Nunca:** no puede asignar trabajadores a los nuevos puestos cuando se crean los puestos.</span><span class="sxs-lookup"><span data-stu-id="eed0e-129">**Never** – You can't assign workers to new positions when positions are created.</span></span> <span data-ttu-id="eed0e-130">Si selecciona esta opción, también debe abrir la página **Puesto** para cada nuevo puesto a medida que se haga disponible y luego en la pestaña **General**, especificar la fecha **Disponible para la asignación** para habilitar la asignación del trabajador.</span><span class="sxs-lookup"><span data-stu-id="eed0e-130">If you select this option, you must open the **Position** page for each new position as it becomes available, and then, on the **General** tab, enter the **Available for assignment** date to enable worker assignment.</span></span>


<a name="see-also"></a><span data-ttu-id="eed0e-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eed0e-131">See also</span></span>
--------

[<span data-ttu-id="eed0e-132">Configuración de los parámetros de recursos humanos específicos de la empresa</span><span class="sxs-lookup"><span data-stu-id="eed0e-132">Set up company specific HR parameters</span></span>](set-up-company-specific-hr-parameters.md)





---
title: "Planificación presupuestaria para documentos de justificación"
description: "Los documentos de justificación proporcionan una descripción para aquellos que solicitan un presupuesto para explicar por qué es necesario un presupuesto específico."
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c4ac839e69440c8d3f1e86007a074999189e391d
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="budget-planning-justification-documents"></a><span data-ttu-id="710eb-103">Planificación presupuestaria para documentos de justificación</span><span class="sxs-lookup"><span data-stu-id="710eb-103">Budget planning justification documents</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="710eb-104">Los documentos de justificación proporcionan una descripción para aquellos que solicitan un presupuesto para explicar por qué es necesario un presupuesto específico.</span><span class="sxs-lookup"><span data-stu-id="710eb-104">Justification documents provide a narrative for those requesting a budget to explain why a specific budget is necessary.</span></span> 

<span data-ttu-id="710eb-105">El administrador presupuestario crea una plantilla del plan presupuestario en Microsoft Word y la asigna al proceso de planificación presupuestaria actual.</span><span class="sxs-lookup"><span data-stu-id="710eb-105">A budget plan template is created by the budget manager in Microsoft Word and assigned to the current budget planning process.</span></span> <span data-ttu-id="710eb-106">A continuación, los propietarios de presupuesto pueden abrir la plantilla y tener los datos rellenados automáticamente en Word en función de su solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="710eb-106">Budget owners can then open the template and have data automatically populated in Word based on their budget request.</span></span> <span data-ttu-id="710eb-107">Posteriormente, pueden agregar texto o datos adicionales antes de guardar y adjuntar el documento de justificación personalizado a su plan presupuestario.</span><span class="sxs-lookup"><span data-stu-id="710eb-107">They can then add additional text or data prior to saving and attaching their personalized justification document to their budget plan.</span></span>

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a><span data-ttu-id="710eb-108">Configure el complemento de Microsoft Dynamics Office para Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="710eb-108">Set up Microsoft Dynamics Office Add-in for Microsoft Word</span></span>

1.  <span data-ttu-id="710eb-109">Abra un nuevo documento de Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="710eb-109">Open a new Microsoft Word document.</span></span>
2.  <span data-ttu-id="710eb-110">Haga clic en **Insertar** en la cinta de opciones y haga clic en **Tienda**.</span><span class="sxs-lookup"><span data-stu-id="710eb-110">Click **Insert** on the ribbon, and click **Store**.</span></span>
3.  <span data-ttu-id="710eb-111">Busque el complemento de Microsoft Dynamics Office y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="710eb-111">Search for Microsoft Dynamics Office Add-in and click **Add**.</span></span>
4.  <span data-ttu-id="710eb-112">En Word, en el panel derecho, haga clic en **Agregar información de servidor**.</span><span class="sxs-lookup"><span data-stu-id="710eb-112">In Word, in the right pane, click **Add server information**.</span></span>
5.  <span data-ttu-id="710eb-113">Escriba o pegue la dirección URL del servidor y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="710eb-113">Type or paste the server URL and click **OK**.</span></span>

##### <a name="define-the-justification-template-in-microsoft-word"></a><span data-ttu-id="710eb-114">Defina la plantilla de justificación en Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="710eb-114">Define the Justification template in Microsoft Word</span></span>

1.  <span data-ttu-id="710eb-115">Haga clic en **Diseño** en el complemento de Microsoft Dynamics Office una vez que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="710eb-115">Click **Design** in the Microsoft Dynamics Office Add-in after you’ve logged in.</span></span>
2.  <span data-ttu-id="710eb-116">Para obtener información del encabezado, utilice el botón **Agregar campos**.</span><span class="sxs-lookup"><span data-stu-id="710eb-116">For header information, use the **Add fields** button.</span></span>
3.  <span data-ttu-id="710eb-117">Seleccione el origen de datos de entidad de BudgetPlanJustification y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="710eb-117">Select the entity data source of BudgetPlanJustification, and click **Next**.</span></span> <span data-ttu-id="710eb-118">**Nota:** Esta entidad es necesaria para cualquier documento de justificación.</span><span class="sxs-lookup"><span data-stu-id="710eb-118">**Note:** This entity is required for any justification document.</span></span> <span data-ttu-id="710eb-119">Se pueden utilizar otras entidades, pero la nueva carga en Microsoft Dynamics 365 for Finance and Operations fallará si no se incluye esta entidad.</span><span class="sxs-lookup"><span data-stu-id="710eb-119">Other entities can be used but the upload back to Microsoft Dynamics 365 for Finance and Operations will fail if this entity isn’t included.</span></span>
4.  <span data-ttu-id="710eb-120">Agregue las etiquetas y los valores BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter y DocumentNumber en el documento de Word.</span><span class="sxs-lookup"><span data-stu-id="710eb-120">Add the BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter, and DocumentNumber labels and values in the Word document.</span></span> <span data-ttu-id="710eb-121">**Nota:** Si es necesario, puede usar sus propias etiquetas personalizadas en lugar de las etiquetas estándar.</span><span class="sxs-lookup"><span data-stu-id="710eb-121">**Note:** You can use your own custom labels, rather than the standard labels, if needed.</span></span>
5.  <span data-ttu-id="710eb-122">Haga clic en **Hecho** para completar la sección de encabezado.</span><span class="sxs-lookup"><span data-stu-id="710eb-122">Click **Done** to complete the header section.</span></span>
6.  <span data-ttu-id="710eb-123">Para el detalle de nivel de línea de los importes del plan presupuestario, haga clic en **Agregar tabla**.</span><span class="sxs-lookup"><span data-stu-id="710eb-123">For line level detail of budget plan amounts, click **Add table**.</span></span>
7.  <span data-ttu-id="710eb-124">Una vez más, seleccione el origen de datos de entidad de BudgetPlanJustification y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="710eb-124">Again, select the entity data source of BudgetPlanJustification, and click **Next**.</span></span>
8.  <span data-ttu-id="710eb-125">Agregue campos para EffectiveDate, ScenarioName, AccountDisplayValue y AccountingCurrencyExpenseAmount.</span><span class="sxs-lookup"><span data-stu-id="710eb-125">Add fields for EffectiveDate, ScenarioName, AccountDisplayValue, and AccountingCurrencyExpenseAmount.</span></span> <span data-ttu-id="710eb-126">**Nota:** Si hay comentarios disponibles para agregar dentro de las líneas individuales del plan presupuestario, estos se pueden agregar a la tabla aquí.</span><span class="sxs-lookup"><span data-stu-id="710eb-126">**Note:** If comments are available to add within individual budget plan lines, those can be added to the table here.</span></span>
9.  <span data-ttu-id="710eb-127">Agregue cualquier instrucción adicional para proporcionar al usuario final y realice cualquier formato o estilo necesario al documento.</span><span class="sxs-lookup"><span data-stu-id="710eb-127">Add any additional instructions to provide to the end user, and perform any necessary formatting or styling to the document.</span></span>
10. <span data-ttu-id="710eb-128">Guarde el documento en su equipo local y cierre el archivo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="710eb-128">Save the document to your local computer and close the file before continuing.</span></span>

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a><span data-ttu-id="710eb-129">Configure el proceso de planificación presupuestaria para usar la plantilla de justificación</span><span class="sxs-lookup"><span data-stu-id="710eb-129">Set up the Budget planning process to use the Justification template</span></span>

1.  <span data-ttu-id="710eb-130">En Finance and Operations, vaya a **Gestión presupuestaria** &gt; **Configuración** &gt; **Planificación presupuestaria** &gt; **Plantillas de documento de justificación**.</span><span class="sxs-lookup"><span data-stu-id="710eb-130">In Finance and Operations, go to **Budgeting** &gt; **Setup** &gt; **Budget planning** &gt; **Justification document templates**.</span></span>
2.  <span data-ttu-id="710eb-131">Haga clic **Nuevo** y busque su documento de Microsoft Word recién creado.</span><span class="sxs-lookup"><span data-stu-id="710eb-131">Click **New** and browse to your newly created Microsoft Word document.</span></span>
3.  <span data-ttu-id="710eb-132">Escribe un nombre y una descripción para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="710eb-132">Enter a template display name and description.</span></span> <span data-ttu-id="710eb-133">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="710eb-133">Click **OK**.</span></span>
4.  <span data-ttu-id="710eb-134">Vaya a **Gestión presupuestaria** &gt; **Configurar** &gt; **Planificación** **presupuestaria** &gt; **Proceso de planificación presupuestaria**.</span><span class="sxs-lookup"><span data-stu-id="710eb-134">Go to **Budgeting** &gt; **Setup** &gt; **Budget** **planning** &gt; **Budget planning process**.</span></span>
5.  <span data-ttu-id="710eb-135">Seleccione el proceso en el que debe utilizarse la plantilla de justificación y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="710eb-135">Select the process where the justification template should be used, and click **Edit**.</span></span>
6.  <span data-ttu-id="710eb-136">En el campo **Plantilla de documento de justificación**, seleccione la plantilla adecuada y guarde.</span><span class="sxs-lookup"><span data-stu-id="710eb-136">In the **Justification document template** field, select the appropriate template and save.</span></span>

##### <a name="edit-and-save-personalized-justification-documents"></a><span data-ttu-id="710eb-137">Edite y guarde los documentos de justificación personalizados</span><span class="sxs-lookup"><span data-stu-id="710eb-137">Edit and save personalized justification documents</span></span>

1.  <span data-ttu-id="710eb-138">En Finance and Operations, cree un nuevo plan presupuestario o abra un plan presupuestario existente.</span><span class="sxs-lookup"><span data-stu-id="710eb-138">In Finance and Operations, create a new budget plan or open an existing budget plan.</span></span>
2.  <span data-ttu-id="710eb-139">En el menú desplegable **Justificación**, seleccione **Crear nueva justificación**.</span><span class="sxs-lookup"><span data-stu-id="710eb-139">In the **Justification** drop-down menu, select **Create new justification**.</span></span>
3.  <span data-ttu-id="710eb-140">Tras completar los detalles, seleccione el documento personalizado que desea cargar desde el menú desplegable **Justificación**.</span><span class="sxs-lookup"><span data-stu-id="710eb-140">After filling in the details, select to upload the personalized document from the **Justification** drop-down menu.</span></span>






---
title: Crear una plantilla de incorporación mediante Dynamics 365 for Talent - Onboard
description: Este tema explica cómo usar la aplicación Dynamics 365 for Talent - Onboard para crear una plantilla para una guía de incorporación para los nuevos empleados contratados. Esta tarea es el primer paso esencial en la estrategia de contratación hasta la jubilación de la gestión del capital humano (HCM).
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c53c24b2913e3ca30cfc6491556b49d5d9230128
ms.sourcegitcommit: 9f762fa89c5b432667aa156c22d679a7f601952d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2019
ms.locfileid: "1731635"
---
# <a name="create-an-onboarding-template-by-using-dynamics-365-for-talent-onboard"></a><span data-ttu-id="6ca61-104">Crear una plantilla de incorporación mediante Dynamics 365 for Talent: Onboard</span><span class="sxs-lookup"><span data-stu-id="6ca61-104">Create an onboarding template by using Dynamics 365 for Talent: Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6ca61-105">Microsoft Dynamics 365 for Talent: Onboard proporciona varias plantillas que le ayudan a crear una guía de incorporación lo más rápidamente posible.</span><span class="sxs-lookup"><span data-stu-id="6ca61-105">Microsoft Dynamics 365 for Talent: Onboard provides various templates that can help you create an onboarding guide as quickly as possible.</span></span> <span data-ttu-id="6ca61-106">Puede usar una o más de estas plantillas, o bien crear sus propias plantillas.</span><span class="sxs-lookup"><span data-stu-id="6ca61-106">You can use one or more of these templates, or you can create your own templates.</span></span> <span data-ttu-id="6ca61-107">Onboard proporciona el texto de muestra que puede usar al crear sus propias plantillas.</span><span class="sxs-lookup"><span data-stu-id="6ca61-107">Onboard provides sample text that you can use when you create your own templates.</span></span> <span data-ttu-id="6ca61-108">Por lo tanto, el proceso es fácil incluso si empieza a partir de cero.</span><span class="sxs-lookup"><span data-stu-id="6ca61-108">Therefore, the process is easy even if you start from scratch.</span></span>

## <a name="create-an-onboarding-template-from-an-existing-template"></a><span data-ttu-id="6ca61-109">Crear una plantilla de incorporación a partir de una plantilla existente</span><span class="sxs-lookup"><span data-stu-id="6ca61-109">Create an onboarding template from an existing template</span></span>

1. <span data-ttu-id="6ca61-110">En el menú izquierdo, seleccione **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="6ca61-110">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="6ca61-111">En **Plantillas populares de la galería** o **Mis plantillas**, seleccione una plantilla.</span><span class="sxs-lookup"><span data-stu-id="6ca61-111">Under **Popular templates from the gallery** or **My templates**, select a template.</span></span> <span data-ttu-id="6ca61-112">Para ver más plantillas, seleccione **Más en la galería de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="6ca61-112">To view more templates, select **More in template gallery**.</span></span>
3. <span data-ttu-id="6ca61-113">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6ca61-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="6ca61-114">Si la plantilla es de la galería, seleccione **Guardar como mi plantilla**, especifique un nuevo nombre para la plantilla, y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6ca61-114">If the template is from the gallery, select **Save as my template**, enter a new name for the template, and select **Save**.</span></span>
    - <span data-ttu-id="6ca61-115">Si la plantilla es de **Mis plantillas**, seleccione **Guardar como plantilla**, especifique un nuevo nombre para la plantilla, y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6ca61-115">If the template is from **My templates**, select **Save as template**, enter a new name for the template, and select **Save**.</span></span>

    <span data-ttu-id="6ca61-116">[![Creación de una plantilla a partir de una plantilla existente](./media/onboard-save-template.png)](./media/onboard-save-template.png)</span><span class="sxs-lookup"><span data-stu-id="6ca61-116">[![Creating a template from an existing template](./media/onboard-save-template.png)](./media/onboard-save-template.png)</span></span>

## <a name="create-a-new-onboarding-template"></a><span data-ttu-id="6ca61-117">Crear una plantilla de incorporación nueva</span><span class="sxs-lookup"><span data-stu-id="6ca61-117">Create a new onboarding template</span></span>

1. <span data-ttu-id="6ca61-118">En el menú izquierdo, seleccione **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="6ca61-118">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="6ca61-119">En **Mis plantillas**, seleccione el icono **Agregar** (signo más \[**+**\]).</span><span class="sxs-lookup"><span data-stu-id="6ca61-119">Under **My templates**, select the **Add** (plus sign \[**+**\]) tile.</span></span>

    <span data-ttu-id="6ca61-120">[![Crear una nueva plantilla](./media/onboard-create-new-template.png)](./media/onboard-create-new-template.png)</span><span class="sxs-lookup"><span data-stu-id="6ca61-120">[![Creating a new template](./media/onboard-create-new-template.png)](./media/onboard-create-new-template.png)</span></span>

3. <span data-ttu-id="6ca61-121">En el cuadro de diálogo **Crear una plantilla de guía**, escriba un nombre para la plantilla y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6ca61-121">In the **Create a guide template** dialog box, enter a name for the template, and then select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ca61-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6ca61-122">Next steps</span></span>

- [<span data-ttu-id="6ca61-123">Editar guías y plantillas de incorporación</span><span class="sxs-lookup"><span data-stu-id="6ca61-123">Edit onboarding guides and templates</span></span>](./onboard-edit-guides-templates.md)
- [<span data-ttu-id="6ca61-124">Compartir contenido con otros trabajadores</span><span class="sxs-lookup"><span data-stu-id="6ca61-124">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="6ca61-125">Ver el estado de las tareas y los empleados que se incorporan</span><span class="sxs-lookup"><span data-stu-id="6ca61-125">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="6ca61-126">Crear equipos de contratación en Onboard</span><span class="sxs-lookup"><span data-stu-id="6ca61-126">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="6ca61-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ca61-127">See also</span></span>

- [<span data-ttu-id="6ca61-128">Probar o comprar la aplicación Onboard</span><span class="sxs-lookup"><span data-stu-id="6ca61-128">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="6ca61-129">Novedades</span><span class="sxs-lookup"><span data-stu-id="6ca61-129">What's new</span></span>](./whats-new.md)
- [<span data-ttu-id="6ca61-130">Notas de la versión</span><span class="sxs-lookup"><span data-stu-id="6ca61-130">Release notes</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="6ca61-131">Obtener soporte</span><span class="sxs-lookup"><span data-stu-id="6ca61-131">Get support</span></span>](./talent-support.md)

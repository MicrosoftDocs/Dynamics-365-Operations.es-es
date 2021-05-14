---
title: Trabajadores sin empleo
description: Los trabajadores sin empleo futuro, activo ni histórico con su organización aparecen en el formulario Trabajadores sin empleo.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1a137de25924f4c4ec6f6b1fe70f9d21af591c0
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924580"
---
# <a name="workers-without-employment"></a><span data-ttu-id="2fba9-103">Trabajadores sin empleo</span><span class="sxs-lookup"><span data-stu-id="2fba9-103">Workers without employment</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2fba9-104">Los trabajadores sin empleo futuro, activo ni histórico con su organización aparecen en el formulario **Trabajadores sin formulario de empleo**.</span><span class="sxs-lookup"><span data-stu-id="2fba9-104">Workers with no future, active, or historical employment with your organization appear in the **Workers without employment** form.</span></span> <span data-ttu-id="2fba9-105">Los trabajadores con este estado pueden aparecer cuando importa trabajadores sin un registro de empleo o cuando elimina el empleo de un trabajador a través de **Trabajadores > Historial de empleo**.</span><span class="sxs-lookup"><span data-stu-id="2fba9-105">Workers with this status can appear when you import workers without an employment record, or when you delete a worker's employment via **Workers > Employment history**.</span></span>

<span data-ttu-id="2fba9-106">De forma predeterminada, el formulario **Trabajadores sin empleo** está disponible para los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="2fba9-106">By default, the **Workers without employment** form is available to the following roles:</span></span>

- <span data-ttu-id="2fba9-107">Ayudante de Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="2fba9-107">Human Resources Assistant</span></span>
- <span data-ttu-id="2fba9-108">Director de Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="2fba9-108">Human Resources Manager</span></span>
- <span data-ttu-id="2fba9-109">Contratante</span><span class="sxs-lookup"><span data-stu-id="2fba9-109">Recruiter</span></span>
- <span data-ttu-id="2fba9-110">Director de compensaciones y prestaciones</span><span class="sxs-lookup"><span data-stu-id="2fba9-110">Comp and Benefits Manager</span></span>
- <span data-ttu-id="2fba9-111">Administrador de nóminas</span><span class="sxs-lookup"><span data-stu-id="2fba9-111">Payroll Administrator</span></span>
- <span data-ttu-id="2fba9-112">Administrador de nóminas</span><span class="sxs-lookup"><span data-stu-id="2fba9-112">Payroll Manager</span></span>
- <span data-ttu-id="2fba9-113">Director de cursos</span><span class="sxs-lookup"><span data-stu-id="2fba9-113">Training Manager</span></span>

<span data-ttu-id="2fba9-114">En la lista **Trabajadores sin empleo**, puede eliminar las personas enumeradas.</span><span class="sxs-lookup"><span data-stu-id="2fba9-114">In the **Workers without employment** list, you can delete the individuals listed.</span></span> <span data-ttu-id="2fba9-115">De forma predeterminada, este privilegio se otorga al rol de Asistente de Recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="2fba9-115">By default, this privilege is given to the Human Resources Assistant role.</span></span> <span data-ttu-id="2fba9-116">Puede otorgar este privilegio a otros roles con los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="2fba9-116">You can give this privilege to other roles with the following steps:</span></span>

1. <span data-ttu-id="2fba9-117">Seleccione **Administración del sistema** y luego **Configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="2fba9-117">Select **System administration**, and then select **Security configuration**.</span></span>

2. <span data-ttu-id="2fba9-118">En la pestaña **Privilegios**, filtre la lista **Privilegios** para **Mantener trabajadores**.</span><span class="sxs-lookup"><span data-stu-id="2fba9-118">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>

   <span data-ttu-id="2fba9-119">[![Filtrar lista de privilegios](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span><span class="sxs-lookup"><span data-stu-id="2fba9-119">[![Filter Privileges list](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span></span>

3. <span data-ttu-id="2fba9-120">En la columna **Referencias**, seleccione **Elementos del menú de visualización**.</span><span class="sxs-lookup"><span data-stu-id="2fba9-120">In the **References** column, select **Display menu items**.</span></span>

4. <span data-ttu-id="2fba9-121">En **Elementos del menú de visualización**, seleccione **HcmWorkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="2fba9-121">In **Display menu items**, select **HcmWorkersWithoutEmployment**.</span></span>

   <span data-ttu-id="2fba9-122">[![Seleccionar formulario](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span><span class="sxs-lookup"><span data-stu-id="2fba9-122">[![Select form](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span></span>

5. <span data-ttu-id="2fba9-123">Seleccione el permiso **Eliminar** para **Conceder**.</span><span class="sxs-lookup"><span data-stu-id="2fba9-123">Set the **Delete** permission to **Grant**.</span></span>

6. <span data-ttu-id="2fba9-124">Seleccione la pestaña **Objetos sin publicar**.</span><span class="sxs-lookup"><span data-stu-id="2fba9-124">Select the **Unpublished objects** tab.</span></span>

7. <span data-ttu-id="2fba9-125">Seleccione **Publicar todo**.</span><span class="sxs-lookup"><span data-stu-id="2fba9-125">Select **Publish all**.</span></span>

   <span data-ttu-id="2fba9-126">[![Publicar cambios](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span><span class="sxs-lookup"><span data-stu-id="2fba9-126">[![Publish changes](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
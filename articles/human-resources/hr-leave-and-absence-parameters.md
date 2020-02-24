---
title: Configurar parámetros de bajas y ausencias
description: Defina parámetros de recursos humanos para bajas y ausencias en Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2acb8502ebcab122a0a1ff21e9f5e23931026327
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010449"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="6be03-103">Configurar parámetros de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="6be03-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="6be03-104">Antes de configurar planes de bajas y ausencias en Dynamics 365 Human Resources, es una buena idea comprobar la configuración de todos los parámetros de recursos humanos relacionados, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6be03-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="6be03-105">Secuencia numérica para solicitudes de licencia</span><span class="sxs-lookup"><span data-stu-id="6be03-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="6be03-106">Configuración de Ley de Ausencia Familiar y Médica</span><span class="sxs-lookup"><span data-stu-id="6be03-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="6be03-107">Configuración de autoservicio de empleados para solicitudes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="6be03-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="6be03-108">Parámetros de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="6be03-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="6be03-109">Ver y cambiar parámetros de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="6be03-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="6be03-110">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="6be03-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="6be03-111">En **Configuración**, seleccione **Parámetros de Recursos Humanos**.</span><span class="sxs-lookup"><span data-stu-id="6be03-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="6be03-112">En la pestaña **Secuencias numéricas**, compruebe el **Código de secuencia numérica** para el **Id. de solicitud de baja** y cambie según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6be03-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="6be03-113">Esta configuración determina la secuencia que se usa para asignar id. automáticamente a solicitudes de bajas.</span><span class="sxs-lookup"><span data-stu-id="6be03-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="6be03-114">En la pestaña **FMLA**, compruebe la configuración de FMLA y cambie según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6be03-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="6be03-115">En la pestaña **Autoservicio para empleados**, indique si los responsables pueden introducir solicitudes de bajas y ausencias en nombre de sus empleados.</span><span class="sxs-lookup"><span data-stu-id="6be03-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="6be03-116">En la pestaña **Bajas y ausencias**, compruebe la configuración de y cambie según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6be03-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="6be03-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6be03-117">Select **Save**.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="6be03-118">Configurar parámetros de calendario</span><span class="sxs-lookup"><span data-stu-id="6be03-118">Configure calendar parameters</span></span>

<span data-ttu-id="6be03-119">Si ha habilitado la característica de vista previa del calendario de bajas y ausencias, debe configurar parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="6be03-119">If you have enabled the Leave and absence calendar preview feature, you need to configure additional parameters.</span></span> 

[!include [banner](includes/preview-feature-leave-absence.md)]

> [!NOTE]
> <span data-ttu-id="6be03-120">Para la versión de vista previa del 3 de febrero de 2020, solo la opción **Solicitudes de licencias pendientes** está habilitada.</span><span class="sxs-lookup"><span data-stu-id="6be03-120">For the preview release on February 3, 2020, only **Pending leave requests** are enabled.</span></span>

1. <span data-ttu-id="6be03-121">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="6be03-121">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="6be03-122">En **Configuración**, seleccione **Parámetros de Recursos Humanos**.</span><span class="sxs-lookup"><span data-stu-id="6be03-122">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="6be03-123">En la pestaña **Calendario**, compruebe la configuración del calendario según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6be03-123">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="6be03-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6be03-124">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6be03-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6be03-125">See also</span></span>

- [<span data-ttu-id="6be03-126">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="6be03-126">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)

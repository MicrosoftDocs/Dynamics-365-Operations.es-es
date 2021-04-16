---
title: Configurar un trabajador mediante el dispositivo móvil de trabajo
description: Este tema explica cómo asignar los roles correctos a la cuenta de usuario de un trabajador y, a continuación, habilitar al trabajador para que realice registros de planta.
author: ShylaThompson
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3fe4e195763f5329ee7732a2f087094acbad595a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810951"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="451bf-103">Configurar un trabajador mediante el dispositivo móvil de trabajo</span><span class="sxs-lookup"><span data-stu-id="451bf-103">Configure a worker using the mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="451bf-104">Este tema explica cómo asignar los roles correctos a la cuenta de usuario de un trabajador y, a continuación, habilitar al trabajador para que realice registros de planta.</span><span class="sxs-lookup"><span data-stu-id="451bf-104">This topic explains how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a><span data-ttu-id="451bf-105">Comprobar que el trabajador está asignado a un rol</span><span class="sxs-lookup"><span data-stu-id="451bf-105">Verify that a worker is assigned a certain role</span></span>

<span data-ttu-id="451bf-106">Para este ejemplo, compruebe que se asigna al usuario "SHANNON" el rol de operadora de maquinaria antes de configurar la cuenta de la trabajadora.</span><span class="sxs-lookup"><span data-stu-id="451bf-106">For this example, verify that user "SHANNON" is assigned the machine operator role before you configure the worker account.</span></span>

1. <span data-ttu-id="451bf-107">Vaya a **Panel de navegación > Módulos > Administración del sistema > Usuarios > Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="451bf-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="451bf-108">Busque un usuario en el filtro rápido.</span><span class="sxs-lookup"><span data-stu-id="451bf-108">Search for a user in the quick filter.</span></span> <span data-ttu-id="451bf-109">Para este ejemplo, escriba `shannon`.</span><span class="sxs-lookup"><span data-stu-id="451bf-109">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="451bf-110">Seleccione el vínculo en la columna **Id. de usuario** de la cuenta de usuario que aparece.</span><span class="sxs-lookup"><span data-stu-id="451bf-110">Select the link in the **User ID** column of the user account that appears.</span></span>
4. <span data-ttu-id="451bf-111">En el árbol **Roles de usuario**, seleccione **Roles > Operador de maquinaria**.</span><span class="sxs-lookup"><span data-stu-id="451bf-111">In the **User's roles** tree, select **Roles > Machine operator**.</span></span>
5. <span data-ttu-id="451bf-112">Cierre las páginas **detalles de usuario** y **usuarios** para volver a la página principal.</span><span class="sxs-lookup"><span data-stu-id="451bf-112">Close the **user details** and **users** pages to return to the home page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="451bf-113">Configurar la cuenta de trabajador</span><span class="sxs-lookup"><span data-stu-id="451bf-113">Configure worker account</span></span>
1. <span data-ttu-id="451bf-114">Vaya a **Panel de exploración > Módulos > Recursos humanos > Trabajadores > Trabajadores**.</span><span class="sxs-lookup"><span data-stu-id="451bf-114">Go to **Navigation pane > Modules > Human resources > Workers > Workers**.</span></span>
2. <span data-ttu-id="451bf-115">Busque un usuario en el filtro rápido.</span><span class="sxs-lookup"><span data-stu-id="451bf-115">Search for a user in the quick filter.</span></span> <span data-ttu-id="451bf-116">Para este ejemplo, escriba `shannon`.</span><span class="sxs-lookup"><span data-stu-id="451bf-116">For this example, enter `shannon`.</span></span>
3. <span data-ttu-id="451bf-117">Seleccione el vínculo en la columna **Nombre** de la cuenta de usuario que aparece.</span><span class="sxs-lookup"><span data-stu-id="451bf-117">Select the link in the **Name** column of the user account that appears.</span></span>
4. <span data-ttu-id="451bf-118">Seleccione la pestaña **Registro de horas**.</span><span class="sxs-lookup"><span data-stu-id="451bf-118">Select the **Time registration** tab.</span></span>
5. <span data-ttu-id="451bf-119">Seleccione **Activar en terminales de registro**.</span><span class="sxs-lookup"><span data-stu-id="451bf-119">Select **Activate on registration terminals**.</span></span>
6. <span data-ttu-id="451bf-120">Especifique o seleccione los valores de los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="451bf-120">Enter or select values in the following fields:</span></span>  

    - <span data-ttu-id="451bf-121">**Grupo de cálculo**</span><span class="sxs-lookup"><span data-stu-id="451bf-121">**Calculation group**</span></span>  
    - <span data-ttu-id="451bf-122">**Grupo de cálculo predeterminado**</span><span class="sxs-lookup"><span data-stu-id="451bf-122">**Default calculation group**</span></span>  
    - <span data-ttu-id="451bf-123">**Grupo de aprobación**</span><span class="sxs-lookup"><span data-stu-id="451bf-123">**Approval group**</span></span>  
    - <span data-ttu-id="451bf-124">**Perfil estándar**</span><span class="sxs-lookup"><span data-stu-id="451bf-124">**Standard profile**</span></span>  
    - <span data-ttu-id="451bf-125">**Grupo de perfiles**</span><span class="sxs-lookup"><span data-stu-id="451bf-125">**Profile group**</span></span>  

7. <span data-ttu-id="451bf-126">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="451bf-126">Select **OK**.</span></span>
8. <span data-ttu-id="451bf-127">Seleccione **Editar** para especificar un número de tarjeta para el nuevo trabajador con registro de horas.</span><span class="sxs-lookup"><span data-stu-id="451bf-127">Select **Edit** to enter a badge number for the new time registration worker.</span></span> <span data-ttu-id="451bf-128">En el campo **Id. de tarjeta**, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="451bf-128">Enter a value in the **Badge ID** field.</span></span>
9. <span data-ttu-id="451bf-129">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="451bf-129">Select **Save**.</span></span>
10. <span data-ttu-id="451bf-130">Cierre **Detalles del trabajador** y **Trabajadores**.</span><span class="sxs-lookup"><span data-stu-id="451bf-130">Close the **Worker details** and **Workers** pages.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="451bf-131">Asignar un trabajador a un grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="451bf-131">Assign worker to device group</span></span>
1. <span data-ttu-id="451bf-132">Vaya a **Control de producción > Configuración > Ejecución de fabricación > Configurar tarjeta de trabajo para dispositivos**:</span><span class="sxs-lookup"><span data-stu-id="451bf-132">Go to **Production control > Setup > Manufacturing execution > Configure job card for devices**.</span></span>
2. <span data-ttu-id="451bf-133">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="451bf-133">Select **Add**.</span></span>
3. <span data-ttu-id="451bf-134">En la lista, seleccione el trabajador que desee.</span><span class="sxs-lookup"><span data-stu-id="451bf-134">In the list, select the desired worker.</span></span> <span data-ttu-id="451bf-135">Para este ejemplo, seleccione **SHANNON**.</span><span class="sxs-lookup"><span data-stu-id="451bf-135">For this example, select **SHANNON**.</span></span>
4. <span data-ttu-id="451bf-136">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="451bf-136">Select **OK**.</span></span>
5. <span data-ttu-id="451bf-137">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="451bf-137">Select **Edit**.</span></span>
6. <span data-ttu-id="451bf-138">En el campo **Unidad de producción**, puede establecer el filtro predeterminado para el trabajador.</span><span class="sxs-lookup"><span data-stu-id="451bf-138">In the **Production unit** field, you can set the default filter for the worker.</span></span> <span data-ttu-id="451bf-139">Esto asegurará que solo se muestran los trabajos de producción para la unidad de producción seleccionada cuando el trabajador inicia sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="451bf-139">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span> <span data-ttu-id="451bf-140">Especifique el valor que desee.</span><span class="sxs-lookup"><span data-stu-id="451bf-140">Enter the desired value.</span></span>
7. <span data-ttu-id="451bf-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="451bf-141">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
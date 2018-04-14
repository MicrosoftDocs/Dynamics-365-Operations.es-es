--- 
title: "Configurar un trabajador mediante el dispositivo móvil de trabajo"
description: "Este procedimiento le muestra cómo asignar los roles correctos a la cuenta de usuario de un trabajador y, a continuación, habilitar al trabajador para que realice registros de planta."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 449c8411b06303a470aba279f85fb904ca1ad3c2
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="configure-a-worker-using-the-mobile-job-device"></a><span data-ttu-id="c40bc-103">Configurar un trabajador mediante el dispositivo móvil de trabajo</span><span class="sxs-lookup"><span data-stu-id="c40bc-103">Configure a worker using the mobile job device</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c40bc-104">Este procedimiento le muestra cómo asignar los roles correctos a la cuenta de usuario de un trabajador y, a continuación, habilitar al trabajador para que realice registros de planta.</span><span class="sxs-lookup"><span data-stu-id="c40bc-104">This procedure shows you how to assign the correct roles to the user account of a worker, and then enable the worker to do shop floor registrations.</span></span>


## <a name="assign-roles-to-user-account"></a><span data-ttu-id="c40bc-105">Asignar roles a cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="c40bc-105">Assign roles to user account</span></span>
1. <span data-ttu-id="c40bc-106">Vaya a Administración del sistema > Usuarios > Usuarios.</span><span class="sxs-lookup"><span data-stu-id="c40bc-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="c40bc-107">Use el filtro rápido para filtrar por el nombre de un trabajador el que la cuenta de usuario está asociada al rol de operador de maquinaria.</span><span class="sxs-lookup"><span data-stu-id="c40bc-107">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="c40bc-108">En los datos de ejemplo, el nombre sería Shannon.</span><span class="sxs-lookup"><span data-stu-id="c40bc-108">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="c40bc-109">Resalte el registro de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="c40bc-109">Highlight the user account record.</span></span>
4. <span data-ttu-id="c40bc-110">En la lista, haga clic en el vínculo "Nombre" en la fila seleccionada para ver los detalles de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="c40bc-110">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="c40bc-111">En el árbol, seleccione el "Roles\Operador de máquina".</span><span class="sxs-lookup"><span data-stu-id="c40bc-111">In the tree, select 'Roles\Machine operator'.</span></span>
6. <span data-ttu-id="c40bc-112">Cierre la página de detalles de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="c40bc-112">Close the user account details page.</span></span>
7. <span data-ttu-id="c40bc-113">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c40bc-113">Close the page.</span></span>

## <a name="configure-worker-account"></a><span data-ttu-id="c40bc-114">Configurar cuenta de trabajador.</span><span class="sxs-lookup"><span data-stu-id="c40bc-114">Configure worker account.</span></span>
1. <span data-ttu-id="c40bc-115">Vaya a Recursos humanos > Trabajadores > Trabajadores.</span><span class="sxs-lookup"><span data-stu-id="c40bc-115">Go to Human resources > Workers > Workers.</span></span>
2. <span data-ttu-id="c40bc-116">Use el filtro rápido para filtrar por el nombre de un trabajador el que la cuenta de usuario está asociada al rol de operador de maquinaria.</span><span class="sxs-lookup"><span data-stu-id="c40bc-116">Use the Quick Filter to filter on the name of a worker where the user account is associated with the machine operator role.</span></span> <span data-ttu-id="c40bc-117">En los datos de ejemplo, el nombre sería Shannon.</span><span class="sxs-lookup"><span data-stu-id="c40bc-117">In the sample data, the name would be Shannon.</span></span>
3. <span data-ttu-id="c40bc-118">Resalte el registro de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="c40bc-118">Highlight the user account record.</span></span>
4. <span data-ttu-id="c40bc-119">En la lista, haga clic en el vínculo "Nombre" en la fila seleccionada para ver los detalles de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="c40bc-119">In the list, click the "Name" link in the selected row to view the details of the user account.</span></span>
5. <span data-ttu-id="c40bc-120">Haga clic en la ficha Empleo.</span><span class="sxs-lookup"><span data-stu-id="c40bc-120">Click the Employment tab.</span></span>
6. <span data-ttu-id="c40bc-121">Expanda la ficha desplegable Registro de horas y haga clic en Activar en terminales de registro.</span><span class="sxs-lookup"><span data-stu-id="c40bc-121">Expand the Time registration FastTab and click Activate on registration terminals.</span></span>
7. <span data-ttu-id="c40bc-122">Haga clic en Activar en terminales de registro.</span><span class="sxs-lookup"><span data-stu-id="c40bc-122">Click Activate on registration terminals.</span></span>
8. <span data-ttu-id="c40bc-123">En el campo Grupo de cálculo, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c40bc-123">In the Calculation group field, enter or select a value.</span></span>
9. <span data-ttu-id="c40bc-124">En el campo Grupo de cálculo predeterminado, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c40bc-124">In the Default calculation group field, enter or select a value.</span></span>
10. <span data-ttu-id="c40bc-125">En el campo Grupo de aprobación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c40bc-125">In the Approval group field, enter or select a value.</span></span>
11. <span data-ttu-id="c40bc-126">En el campo Perfil estándar, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c40bc-126">In the Standard profile field, enter or select a value.</span></span>
12. <span data-ttu-id="c40bc-127">En el campo Grupo de perfiles, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c40bc-127">In the Profile group field, enter or select a value.</span></span>
13. <span data-ttu-id="c40bc-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c40bc-128">Click OK.</span></span>
14. <span data-ttu-id="c40bc-129">Haga clic en Editar para especificar un número de tarjeta para el nuevo trabajador con registro de horas.</span><span class="sxs-lookup"><span data-stu-id="c40bc-129">Click Edit to enter a badge number for the new time registration worker.</span></span>
15. <span data-ttu-id="c40bc-130">En el campo Id. de tarjeta, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c40bc-130">In the Badge ID field, type a value.</span></span>
16. <span data-ttu-id="c40bc-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c40bc-131">Click Save.</span></span>
17. <span data-ttu-id="c40bc-132">Use el acceso directo SaveRecord.</span><span class="sxs-lookup"><span data-stu-id="c40bc-132">Use the SaveRecord shortcut.</span></span>
18. <span data-ttu-id="c40bc-133">Cierre la página de detalles del trabajador.</span><span class="sxs-lookup"><span data-stu-id="c40bc-133">Close the worker details page.</span></span>
19. <span data-ttu-id="c40bc-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c40bc-134">Close the page.</span></span>

## <a name="assign-worker-to-device-group"></a><span data-ttu-id="c40bc-135">Asignar trabajador a grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c40bc-135">Assign worker to device group.</span></span>
1. <span data-ttu-id="c40bc-136">Vaya a Control de producción > Configuración > Ejecución de fabricación > Configurar tarjeta de trabajo para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c40bc-136">Go to Production control > Setup > Manufacturing execution > Configure job card for devices.</span></span>
2. <span data-ttu-id="c40bc-137">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c40bc-137">Click Add.</span></span>
3. <span data-ttu-id="c40bc-138">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c40bc-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="c40bc-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c40bc-139">Click OK.</span></span>
5. <span data-ttu-id="c40bc-140">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="c40bc-140">Click Edit.</span></span>
6. <span data-ttu-id="c40bc-141">En el campo Unidad de producción, puede establecer el filtro predeterminado para el trabajador.</span><span class="sxs-lookup"><span data-stu-id="c40bc-141">In the Production unit field, you can set the default filter for the worker.</span></span> <span data-ttu-id="c40bc-142">Esto asegurará que solo se muestran los trabajos de producción para la unidad de producción seleccionada cuando el trabajador inicia sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c40bc-142">This will ensure that only production jobs for the selected production unit are shown when the worker logs on to the device.</span></span>
7. <span data-ttu-id="c40bc-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c40bc-143">Close the page.</span></span>


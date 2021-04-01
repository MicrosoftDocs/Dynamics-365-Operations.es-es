---
title: Crear canales del centro de llamadas y definir los atributos del canal
description: Este procedimiento le muestra cómo crear un nuevo canal y definir atributos de canal.
author: mugunthanm
manager: AnnBe
ms.date: 05/22/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5e4ef84abcfd0948c46c5312078f2a940840144
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256958"
---
# <a name="create-call-center-channels-and-define-channel-attributes"></a><span data-ttu-id="b70e4-103">Crear canales del centro de llamadas y definir los atributos del canal</span><span class="sxs-lookup"><span data-stu-id="b70e4-103">Create call center channels and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b70e4-104">Este procedimiento le muestra cómo crear un nuevo canal de Commerce y definir atributos de canal.</span><span class="sxs-lookup"><span data-stu-id="b70e4-104">This procedure walks through creating a new commerce channel and defining channel attributes.</span></span> <span data-ttu-id="b70e4-105">La empresa de datos de prueba utilizada para crear esta tarea es USRT.</span><span class="sxs-lookup"><span data-stu-id="b70e4-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="b70e4-106">Este procedimiento se va a utilizar para el rol de TI de Commerce.</span><span class="sxs-lookup"><span data-stu-id="b70e4-106">This procedure is intended for the Commerce IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="b70e4-107">Crear nueva tienda</span><span class="sxs-lookup"><span data-stu-id="b70e4-107">Create new store</span></span>
1. <span data-ttu-id="b70e4-108">Vaya a Todos los espacios de trabajo > Implementación de canales.</span><span class="sxs-lookup"><span data-stu-id="b70e4-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="b70e4-109">Haga clic en Nuevo canal.</span><span class="sxs-lookup"><span data-stu-id="b70e4-109">Click New channel.</span></span>
3. <span data-ttu-id="b70e4-110">Haga clic en Tienda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-110">Click Store.</span></span>
4. <span data-ttu-id="b70e4-111">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b70e4-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="b70e4-112">En el campo Número de tienda, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b70e4-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="b70e4-113">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="b70e4-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b70e4-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="b70e4-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="b70e4-116">En el campo Zona horaria de la tienda, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="b70e4-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="b70e4-117">En el campo Perfil de canal, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="b70e4-118">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="b70e4-119">En el campo Idioma, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="b70e4-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b70e4-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="b70e4-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="b70e4-122">En el campo Grupo de impuestos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="b70e4-123">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b70e4-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="b70e4-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="b70e4-125">En el campo Libreta de direcciones de cliente, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b70e4-126">Seleccione la libreta de direcciones utilizada para vincular clientes a esta tienda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="b70e4-127">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b70e4-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="b70e4-128">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="b70e4-129">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="b70e4-129">Click Select.</span></span>
22. <span data-ttu-id="b70e4-130">En el campo Libreta de direcciones de empleado, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b70e4-131">Seleccione la libreta de direcciones utilizada para cajeros clientes a esta canal.</span><span class="sxs-lookup"><span data-stu-id="b70e4-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="b70e4-132">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b70e4-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="b70e4-133">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="b70e4-134">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="b70e4-134">Click Select.</span></span>
26. <span data-ttu-id="b70e4-135">En el campo Cliente predeterminado, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="b70e4-136">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="b70e4-137">Expanda o contraiga la sección Diseño de pantalla.</span><span class="sxs-lookup"><span data-stu-id="b70e4-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="b70e4-138">En el campo Id. de diseño de pantalla, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b70e4-139">Seleccione el diseño de pantalla de POS predeterminado para esta tienda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="b70e4-140">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b70e4-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="b70e4-141">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="b70e4-142">En el panel de acciones, haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="b70e4-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="b70e4-143">Haga clic en Atributos del canal.</span><span class="sxs-lookup"><span data-stu-id="b70e4-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="b70e4-144">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b70e4-144">Click New.</span></span>
35. <span data-ttu-id="b70e4-145">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="b70e4-146">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b70e4-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="b70e4-147">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="b70e4-148">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b70e4-148">Click Save.</span></span>
39. <span data-ttu-id="b70e4-149">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b70e4-149">Close the page.</span></span>
40. <span data-ttu-id="b70e4-150">En el panel de acciones, haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="b70e4-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="b70e4-151">Haga clic en Métodos de pago.</span><span class="sxs-lookup"><span data-stu-id="b70e4-151">Click Payment methods.</span></span>
42. <span data-ttu-id="b70e4-152">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b70e4-152">Click New.</span></span>
43. <span data-ttu-id="b70e4-153">En el campo Método de pago, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="b70e4-154">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="b70e4-155">Expanda o contraiga la sección Registro.</span><span class="sxs-lookup"><span data-stu-id="b70e4-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="b70e4-156">En el campo Número de cuenta, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="b70e4-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="b70e4-157">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b70e4-157">Click Save.</span></span>
48. <span data-ttu-id="b70e4-158">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b70e4-158">Close the page.</span></span>
49. <span data-ttu-id="b70e4-159">En el panel de acciones, haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="b70e4-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="b70e4-160">Haga clic en Declaración de efectivo.</span><span class="sxs-lookup"><span data-stu-id="b70e4-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="b70e4-161">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b70e4-161">Click New.</span></span>
52. <span data-ttu-id="b70e4-162">En el campo Importe en divisa de la transacción, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="b70e4-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="b70e4-163">En el campo Divisa, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="b70e4-164">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b70e4-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="b70e4-165">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="b70e4-166">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b70e4-166">Click Save.</span></span>
57. <span data-ttu-id="b70e4-167">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b70e4-167">Close the page.</span></span>
58. <span data-ttu-id="b70e4-168">En el panel de acciones, haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="b70e4-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="b70e4-169">Haga clic en Asignación del grupo de localizadores de almacén.</span><span class="sxs-lookup"><span data-stu-id="b70e4-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="b70e4-170">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b70e4-170">Click New.</span></span>
61. <span data-ttu-id="b70e4-171">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="b70e4-172">En el campo Grupo de localizadores, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b70e4-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="b70e4-173">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b70e4-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="b70e4-174">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b70e4-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="b70e4-175">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b70e4-175">Click Save.</span></span>
66. <span data-ttu-id="b70e4-176">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b70e4-176">Close the page.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Configuración de perfiles de registro de activos fijos
description: Esta guía de la tarea configurará los perfiles de contabilización de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 286c8732c1f2c92d0f16582b0b9de41990280e5a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "351111"
---
# <a name="set-up-fixed-asset-posting-profiles"></a><span data-ttu-id="8bad5-103">Configuración de perfiles de registro de activos fijos</span><span class="sxs-lookup"><span data-stu-id="8bad5-103">Set up fixed asset posting profiles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8bad5-104">Esta guía de la tarea configurará los perfiles de contabilización de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="8bad5-104">This task guide will set up Fixed asset posting profiles.</span></span>  <span data-ttu-id="8bad5-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="8bad5-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>  <span data-ttu-id="8bad5-106">Los ejemplos proporcionados en esta guía de la tarea son para un perfil de contabilización básico, aunque se deben crear perfiles de contabilización para sus requisitos específicos de plan de cuentas y de informes financieros.</span><span class="sxs-lookup"><span data-stu-id="8bad5-106">Examples given in the task guide are for a basic posting profile, though posting profiles must be created for your specific chart of accounts and financial reporting requirements.</span></span>

1. <span data-ttu-id="8bad5-107">Vaya a Activos fijos > Configuración > Perfiles de contabilización de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="8bad5-107">Go to Fixed assets > Setup > Fixed asset posting profiles.</span></span>
2. <span data-ttu-id="8bad5-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8bad5-108">Click New.</span></span>
3. <span data-ttu-id="8bad5-109">En el campo Perfil de contabilización, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-109">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="8bad5-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="8bad5-111">Deberá crear un perfil de contabilización para cada tipo de transacción de activo fijo que usará al trabajar con los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="8bad5-111">You will need to create a posting profile for each fixed asset transaction type you will be using when working with fixed assets.</span></span>  <span data-ttu-id="8bad5-112">Esta guía de la tarea empezará con el tipo de transacción Adquisición.</span><span class="sxs-lookup"><span data-stu-id="8bad5-112">This task guide will start with the Acquisition transaction type.</span></span>  
5. <span data-ttu-id="8bad5-113">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-113">Click Add.</span></span>
6. <span data-ttu-id="8bad5-114">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-114">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="8bad5-115">El campo de agrupaciones permite definir el perfil de contabilización hasta el nivel de tabla (una cuenta configurada para cada activo fijo) o de grupo (una cuenta configurada para cada grupo de activos fijos).</span><span class="sxs-lookup"><span data-stu-id="8bad5-115">The Groupings field allows you to define the posting profile down to the Table (one account set up for each fixed asset) or Group (one account set up for each fixed asset group).</span></span>  <span data-ttu-id="8bad5-116">Para esta guía de tareas dejaré el valor establecido en “Todos” para aplicar a todos los activos fijos con el libro especificado.</span><span class="sxs-lookup"><span data-stu-id="8bad5-116">For this task guide I will leave the value set to “All” to apply to all fixed assets with the specified Book.</span></span>  
7. <span data-ttu-id="8bad5-117">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-117">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="8bad5-118">Para las adquisiciones, puede especificar una cuenta de contrapartida o dejar el cuadro en blanco para que se rellene con la transacción específica.</span><span class="sxs-lookup"><span data-stu-id="8bad5-118">For Acquisitions, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
8. <span data-ttu-id="8bad5-119">En el campo Tipo de transacción, seleccione “Ajuste de adquisición”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-119">In the Transaction type field, select 'Acquisition adjustment'.</span></span>
    * <span data-ttu-id="8bad5-120">Para las transacciones de ajuste de adquisición, utilizaremos las mismas cuentas que se usan para las transacciones de adquisición.</span><span class="sxs-lookup"><span data-stu-id="8bad5-120">For Acquisition adjustment transactions, we will use the same accounts as used for Acquisition transactions.</span></span>  
9. <span data-ttu-id="8bad5-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-121">Click Add.</span></span>
10. <span data-ttu-id="8bad5-122">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-122">In the Book field, enter or select a value.</span></span>
11. <span data-ttu-id="8bad5-123">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-123">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="8bad5-124">Para los ajustes de adquisiciones, puede especificar una cuenta de contrapartida o dejar el cuadro en blanco para que se rellene con la transacción específica.</span><span class="sxs-lookup"><span data-stu-id="8bad5-124">For Acquisition adjustments, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
12. <span data-ttu-id="8bad5-125">En el campo de tipo de transacción, seleccione “Depreciación”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-125">In the Transaction type field, select 'Depreciation'.</span></span>
13. <span data-ttu-id="8bad5-126">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-126">Click Add.</span></span>
14. <span data-ttu-id="8bad5-127">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-127">In the Book field, enter or select a value.</span></span>
15. <span data-ttu-id="8bad5-128">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-128">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="8bad5-129">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-129">In the Offset account field, specify the desired values.</span></span>
17. <span data-ttu-id="8bad5-130">En el campo Tipo de transacción, seleccione “Ajuste de depreciación”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-130">In the Transaction type field, select 'Depreciation adjustment'.</span></span>
    * <span data-ttu-id="8bad5-131">Para las transacciones de ajuste de depreciación, utilizaremos las mismas cuentas que se usan para las transacciones de depreciación.</span><span class="sxs-lookup"><span data-stu-id="8bad5-131">For Depreciation adjustment transactions, we will use the same accounts as used for Depreciation transactions.</span></span>  
18. <span data-ttu-id="8bad5-132">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-132">Click Add.</span></span>
19. <span data-ttu-id="8bad5-133">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-133">In the Book field, enter or select a value.</span></span>
20. <span data-ttu-id="8bad5-134">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-134">In the Main account field, specify the desired values.</span></span>
21. <span data-ttu-id="8bad5-135">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-135">In the Offset account field, specify the desired values.</span></span>
22. <span data-ttu-id="8bad5-136">En el campo de tipo de transacción, seleccione "Venta".</span><span class="sxs-lookup"><span data-stu-id="8bad5-136">In the Transaction type field, select 'Disposal - sale'.</span></span>
23. <span data-ttu-id="8bad5-137">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-137">Click Add.</span></span>
24. <span data-ttu-id="8bad5-138">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-138">In the Book field, enter or select a value.</span></span>
25. <span data-ttu-id="8bad5-139">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-139">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="8bad5-140">Para las cancelaciones, puede especificar una cuenta de contrapartida o dejar el cuadro en blanco para que se rellene con la transacción específica.</span><span class="sxs-lookup"><span data-stu-id="8bad5-140">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
26. <span data-ttu-id="8bad5-141">En el campo de tipo de transacción, seleccione "Cancelación".</span><span class="sxs-lookup"><span data-stu-id="8bad5-141">In the Transaction type field, select 'Disposal - scrap'.</span></span>
    * <span data-ttu-id="8bad5-142">Utilizaremos las mismas cuentas para venta y cancelación.</span><span class="sxs-lookup"><span data-stu-id="8bad5-142">We will use the same accounts for Disposal sale and Disposal scrap.</span></span>  
27. <span data-ttu-id="8bad5-143">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-143">Click Add.</span></span>
28. <span data-ttu-id="8bad5-144">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-144">In the Book field, enter or select a value.</span></span>
29. <span data-ttu-id="8bad5-145">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-145">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="8bad5-146">Para las cancelaciones, puede especificar una cuenta de contrapartida o dejar el cuadro en blanco para que se rellene con la transacción específica.</span><span class="sxs-lookup"><span data-stu-id="8bad5-146">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
30. <span data-ttu-id="8bad5-147">Expanda la sección Cancelación.</span><span class="sxs-lookup"><span data-stu-id="8bad5-147">Expand the Disposal section.</span></span>
    * <span data-ttu-id="8bad5-148">Debe configurar los perfiles de contabilización de cancelación para la venta y el valor residual.</span><span class="sxs-lookup"><span data-stu-id="8bad5-148">You must set up disposal posting profiles for both sale and scrap.</span></span>  <span data-ttu-id="8bad5-149">Comenzaremos con transacciones de venta.</span><span class="sxs-lookup"><span data-stu-id="8bad5-149">We will start with disposal sale transactions.</span></span>  
31. <span data-ttu-id="8bad5-150">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-150">Click Add.</span></span>
32. <span data-ttu-id="8bad5-151">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-151">In the Book field, enter or select a value.</span></span>
33. <span data-ttu-id="8bad5-152">En el campo de valor contable, seleccione “Valor de adquisición”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-152">In the Post value field, select 'Acquisition value'.</span></span>
    * <span data-ttu-id="8bad5-153">El valor de adquisición dirigirá los valores de adquisición o de ajuste de adquisición para todos los años.</span><span class="sxs-lookup"><span data-stu-id="8bad5-153">Acquisition value will address Acquisition and Acquisition adjustment values for all years.</span></span>  <span data-ttu-id="8bad5-154">También puede definir cuentas para estos tipos de transacción por separado.</span><span class="sxs-lookup"><span data-stu-id="8bad5-154">You can also define accounts for these transaction types separately.</span></span>  
    * <span data-ttu-id="8bad5-155">Puede establecer el proceso de cancelación para utilizar distintas cuentas en función de que la cancelación resulte en una pérdida o en una ganancia.</span><span class="sxs-lookup"><span data-stu-id="8bad5-155">You can set the disposal process to use different accounts depending upon if the disposal results in a gain or loss.</span></span>  <span data-ttu-id="8bad5-156">Estableceré el tipo de valor de ventas como “Todos” para usar las mismas cuentas para todos los tipos de cancelaciones.</span><span class="sxs-lookup"><span data-stu-id="8bad5-156">I will set the Sales value type to “All” to use the same accounts for all types of disposals.</span></span>  
34. <span data-ttu-id="8bad5-157">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-157">In the Main account field, specify the desired values.</span></span>
35. <span data-ttu-id="8bad5-158">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-158">In the Offset account field, specify the desired values.</span></span>
36. <span data-ttu-id="8bad5-159">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-159">Click Add.</span></span>
37. <span data-ttu-id="8bad5-160">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-160">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="8bad5-161">En el campo Valor contable, seleccione “Depreciación (años anteriores)”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-161">In the Post value field, select 'Depreciation (prior years)'.</span></span>  
38. <span data-ttu-id="8bad5-162">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-162">In the Main account field, specify the desired values.</span></span>
39. <span data-ttu-id="8bad5-163">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-163">In the Offset account field, specify the desired values.</span></span>
40. <span data-ttu-id="8bad5-164">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-164">Click Add.</span></span>
41. <span data-ttu-id="8bad5-165">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-165">In the Book field, enter or select a value.</span></span>
42. <span data-ttu-id="8bad5-166">En el campo Valor contable, seleccione “Depreciación (este año)”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-166">In the Post value field, select 'Depreciation (this year)'.</span></span>
43. <span data-ttu-id="8bad5-167">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-167">In the Main account field, specify the desired values.</span></span>
44. <span data-ttu-id="8bad5-168">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-168">In the Offset account field, specify the desired values.</span></span>
45. <span data-ttu-id="8bad5-169">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-169">Click Add.</span></span>
46. <span data-ttu-id="8bad5-170">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-170">In the Book field, enter or select a value.</span></span>
47. <span data-ttu-id="8bad5-171">En el campo Valor contable, seleccione “Ajustes de depreciación (años anteriores)”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-171">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
48. <span data-ttu-id="8bad5-172">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-172">In the Main account field, specify the desired values.</span></span>
49. <span data-ttu-id="8bad5-173">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-173">In the Offset account field, specify the desired values.</span></span>
50. <span data-ttu-id="8bad5-174">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-174">Click Add.</span></span>
51. <span data-ttu-id="8bad5-175">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-175">In the Book field, enter or select a value.</span></span>
52. <span data-ttu-id="8bad5-176">En el campo Valor contable, seleccione “Ajustes de depreciación (este año)”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-176">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
53. <span data-ttu-id="8bad5-177">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-177">In the Main account field, specify the desired values.</span></span>
54. <span data-ttu-id="8bad5-178">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-178">In the Offset account field, specify the desired values.</span></span>
55. <span data-ttu-id="8bad5-179">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-179">Click Add.</span></span>
56. <span data-ttu-id="8bad5-180">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-180">In the Book field, enter or select a value.</span></span>
57. <span data-ttu-id="8bad5-181">En el campo de valor contable, seleccione “Valor neto en los libros”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-181">In the Post value field, select 'Net book value'.</span></span>
58. <span data-ttu-id="8bad5-182">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-182">In the Main account field, specify the desired values.</span></span>
59. <span data-ttu-id="8bad5-183">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-183">In the Offset account field, specify the desired values.</span></span>
60. <span data-ttu-id="8bad5-184">En el campo Venta o residual, seleccione “Residuo”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-184">In the Sale or scrap field, select 'Scrap'.</span></span>
61. <span data-ttu-id="8bad5-185">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-185">Click Add.</span></span>
62. <span data-ttu-id="8bad5-186">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-186">In the Book field, enter or select a value.</span></span>
63. <span data-ttu-id="8bad5-187">En el campo de valor contable, seleccione “Valor de adquisición”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-187">In the Post value field, select 'Acquisition value'.</span></span>
64. <span data-ttu-id="8bad5-188">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-188">In the Main account field, specify the desired values.</span></span>
65. <span data-ttu-id="8bad5-189">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-189">In the Offset account field, specify the desired values.</span></span>
66. <span data-ttu-id="8bad5-190">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-190">Click Add.</span></span>
67. <span data-ttu-id="8bad5-191">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-191">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="8bad5-192">En el campo Valor contable, seleccione “Depreciación (años anteriores)”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-192">In Post value field, select 'Depreciation (prior years)'.</span></span>  
68. <span data-ttu-id="8bad5-193">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-193">In the Main account field, specify the desired values.</span></span>
69. <span data-ttu-id="8bad5-194">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-194">In the Offset account field, specify the desired values.</span></span>
70. <span data-ttu-id="8bad5-195">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-195">Click Add.</span></span>
71. <span data-ttu-id="8bad5-196">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-196">In the Book field, enter or select a value.</span></span>
72. <span data-ttu-id="8bad5-197">En el campo Valor contable, seleccione “Depreciación (este año)”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-197">In the Post value field, select 'Depreciation (this year)'.</span></span>
73. <span data-ttu-id="8bad5-198">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-198">In the Main account field, specify the desired values.</span></span>
74. <span data-ttu-id="8bad5-199">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-199">In the Offset account field, specify the desired values.</span></span>
75. <span data-ttu-id="8bad5-200">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-200">Click Add.</span></span>
76. <span data-ttu-id="8bad5-201">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-201">In the Book field, enter or select a value.</span></span>
77. <span data-ttu-id="8bad5-202">En el campo Valor contable, seleccione “Ajustes de depreciación (años anteriores)”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-202">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
78. <span data-ttu-id="8bad5-203">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-203">In the Main account field, specify the desired values.</span></span>
79. <span data-ttu-id="8bad5-204">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-204">In the Offset account field, specify the desired values.</span></span>
80. <span data-ttu-id="8bad5-205">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-205">Click Add.</span></span>
81. <span data-ttu-id="8bad5-206">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-206">In the Book field, enter or select a value.</span></span>
82. <span data-ttu-id="8bad5-207">En el campo Valor contable, seleccione “Ajustes de depreciación (este año)”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-207">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
83. <span data-ttu-id="8bad5-208">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-208">In the Main account field, specify the desired values.</span></span>
84. <span data-ttu-id="8bad5-209">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-209">In the Offset account field, specify the desired values.</span></span>
85. <span data-ttu-id="8bad5-210">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8bad5-210">Click Add.</span></span>
86. <span data-ttu-id="8bad5-211">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8bad5-211">In the Book field, enter or select a value.</span></span>
87. <span data-ttu-id="8bad5-212">En el campo de valor contable, seleccione “Valor neto en los libros”.</span><span class="sxs-lookup"><span data-stu-id="8bad5-212">In the Post value field, select 'Net book value'.</span></span>
88. <span data-ttu-id="8bad5-213">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-213">In the Main account field, specify the desired values.</span></span>
89. <span data-ttu-id="8bad5-214">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="8bad5-214">In the Offset account field, specify the desired values.</span></span>


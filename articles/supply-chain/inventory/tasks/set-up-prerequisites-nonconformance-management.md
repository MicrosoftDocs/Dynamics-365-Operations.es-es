---
title: "Configurar requisitos previo para la gestión"
description: "Use este procedimiento para habilitar procesos de gestión de disconformidades."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 4bb4af7cb7aff101a8b9e6162823515f63b12886
ms.openlocfilehash: 9b5b05a3c00f093066a2714964bb99146427c3bc
ms.contentlocale: es-es
ms.lasthandoff: 11/02/2017

---
# <a name="set-up-prerequisites-for-management"></a><span data-ttu-id="fc01b-103">Configurar requisitos previo para la gestión</span><span class="sxs-lookup"><span data-stu-id="fc01b-103">Set up prerequisites for management</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc01b-104">Use este procedimiento para habilitar procesos de gestión de disconformidades.</span><span class="sxs-lookup"><span data-stu-id="fc01b-104">Use this procedure to enable nonconformance management processes.</span></span> <span data-ttu-id="fc01b-105">Una no conformidad hace referencia a un procedimiento o artículo que tiene un problema de calidad, donde la información descriptiva incluye el origen y el tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="fc01b-105">A nonconformance describes a procedure or item that has a quality problem, where the descriptive information includes the source and type of problem.</span></span> <span data-ttu-id="fc01b-106">Este procedimiento usa la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="fc01b-106">This procedure uses the USMF demo data company.</span></span> <span data-ttu-id="fc01b-107">Este procedimiento lo realiza normalmente un gestor de calidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-107">This procedure is typically performed by a quality manager.</span></span>


## <a name="enable-quality-management-processes-within-the-company"></a><span data-ttu-id="fc01b-108">Habilitar los procesos de administración de calidad dentro de la empresa</span><span class="sxs-lookup"><span data-stu-id="fc01b-108">Enable quality management processes within the company</span></span>
1. <span data-ttu-id="fc01b-109">Vaya a Gestión del inventario > Configurar > Parámetros de la gestión de inventario y almacenes.</span><span class="sxs-lookup"><span data-stu-id="fc01b-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="fc01b-110">Haga clic en la ficha Administración de calidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="fc01b-111">Seleccione Sí en el campo Usar administración de calidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-111">Select Yes in the Use quality management field.</span></span>
    * <span data-ttu-id="fc01b-112">Seleccione este parámetro para habilitar los procesos de gestión de calidad para la empresa.</span><span class="sxs-lookup"><span data-stu-id="fc01b-112">Select this parameter to enable quality management processes for the company.</span></span>  
4. <span data-ttu-id="fc01b-113">En el campo Índice por hora, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="fc01b-113">In the Hourly rate field, enter a number.</span></span>
    * <span data-ttu-id="fc01b-114">Use el campo Índice por hora para especificar un índice de trabajo por hora en la divisa local.</span><span class="sxs-lookup"><span data-stu-id="fc01b-114">Use the Hourly rate field to enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="fc01b-115">El índice por hora se usa para calcular los costes de operaciones relacionadas con una disconformidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-115">The hourly rate is used for calculating costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="fc01b-116">El índice por hora y los costes calculados proporcionan información de referencia para una disconformidad, y no interactúan con otras funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="fc01b-116">The hourly rate and calculated costs provide reference information for a nonconformance, and they do not interact with other functionality.</span></span>  
5. <span data-ttu-id="fc01b-117">Haga clic en Configuración del informe.</span><span class="sxs-lookup"><span data-stu-id="fc01b-117">Click Report setup.</span></span>
    * <span data-ttu-id="fc01b-118">Esta página le permite definir los tipos de nota del informe de calidad que se usarán en diferentes tipos de informes de administración de calidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-118">This page allows you to define the quality report note types that will be used on different kinds of quality management reports.</span></span>  
6. <span data-ttu-id="fc01b-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-119">Close the page.</span></span>
7. <span data-ttu-id="fc01b-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-120">Close the page.</span></span>

## <a name="enable-user-for-nonconformance-processing"></a><span data-ttu-id="fc01b-121">Habilitar el procesamiento de disconformidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-121">Enable user for nonconformance processing</span></span>
1. <span data-ttu-id="fc01b-122">Vaya a Administración del sistema > Usuarios > Usuarios.</span><span class="sxs-lookup"><span data-stu-id="fc01b-122">Go to System administration > Users > Users.</span></span>
    * <span data-ttu-id="fc01b-123">Para procesar la aprobación de un caso de disconformidad, el usuario que aprueba o rechaza las disconformidades debe tener un valor "Nombre" asignado en la página Usuarios.</span><span class="sxs-lookup"><span data-stu-id="fc01b-123">To process the approval of a nonconformance the user who  approves or rejects nonconformances must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="fc01b-124">Para usar las notas de documento, el usuario también debe tener activada la gestión de documentos en las opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="fc01b-124">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
2. <span data-ttu-id="fc01b-125">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="fc01b-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="fc01b-126">Por ejemplo, filtrar en el campo Nombre con un valor de "Ricardo".</span><span class="sxs-lookup"><span data-stu-id="fc01b-126">For example, filter on the Name field with a value of 'Ricardo'.</span></span>
    * <span data-ttu-id="fc01b-127">Use el filtro para encontrar el usuario que aprobará o rechazará los registros disconformidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-127">Use the filter to find the user who will be approving or rejecting the nonconformance records.</span></span>  
3. <span data-ttu-id="fc01b-128">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fc01b-128">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="fc01b-129">Para procesar la aprobación de un caso de disconformidad, asegúrese de que el usuario que aprueba o rechaza las disconformidades tiene un valor "Nombre" asignado en la página Usuarios.</span><span class="sxs-lookup"><span data-stu-id="fc01b-129">To process the approval of a nonconformance, make sure the user who approves or rejects nonconformances has a “Name” value assigned on the Users page.</span></span>  
4. <span data-ttu-id="fc01b-130">Haga clic en Opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="fc01b-130">Click User options.</span></span>
5. <span data-ttu-id="fc01b-131">Haga clic en la ficha Preferencias.</span><span class="sxs-lookup"><span data-stu-id="fc01b-131">Click the Preferences tab.</span></span>
6. <span data-ttu-id="fc01b-132">Seleccione Sí en el campo Habilitar gestión de documentos.</span><span class="sxs-lookup"><span data-stu-id="fc01b-132">Select Yes in the Enable document handling field.</span></span>
    * <span data-ttu-id="fc01b-133">Para usar las notas de documento, el usuario también debe tener activada la gestión de documentos en las opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="fc01b-133">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
7. <span data-ttu-id="fc01b-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-134">Close the page.</span></span>
8. <span data-ttu-id="fc01b-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-135">Close the page.</span></span>
9. <span data-ttu-id="fc01b-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-136">Close the page.</span></span>

## <a name="define-diagnostic-types-for-nonconformance-processing"></a><span data-ttu-id="fc01b-137">Definir tipos de diagnóstico para el procesamiento de disconformidad</span><span class="sxs-lookup"><span data-stu-id="fc01b-137">Define diagnostic types for nonconformance processing</span></span>
1. <span data-ttu-id="fc01b-138">Vaya a Gestión del inventario > Configurar > Administración de calidad > Tipos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="fc01b-138">Go to Inventory management > Setup > Quality management > Diagnostic types.</span></span>
    * <span data-ttu-id="fc01b-139">Use la página Tipos de diagnóstico para definir una clasificación de acciones de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="fc01b-139">Use the Diagnostic types page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="fc01b-140">Una corrección identifica qué tipo de acción de diagnóstico se debe realizar en una disconformidad aprobada, quién debe efectuarla, y la fecha de finalización solicitada y planificada.</span><span class="sxs-lookup"><span data-stu-id="fc01b-140">A correction identifies what type of diagnostic action should be taken on an approved nonconformance, who should perform it, and the requested and planned completion date.</span></span>  
2. <span data-ttu-id="fc01b-141">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fc01b-141">Click New.</span></span>
3. <span data-ttu-id="fc01b-142">En el campo Diagnóstico, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fc01b-142">In the Diagnostic field, type a value.</span></span>
4. <span data-ttu-id="fc01b-143">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fc01b-143">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fc01b-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-144">Close the page.</span></span>

## <a name="define-quality-charges-for-nonconformance-processing"></a><span data-ttu-id="fc01b-145">Definir gastos de calidad para procesamiento de disconformidad</span><span class="sxs-lookup"><span data-stu-id="fc01b-145">Define quality charges for nonconformance processing</span></span>
1. <span data-ttu-id="fc01b-146">Vaya a Gestión del inventario > Configurar > Administración de calidad > Gastos de calidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-146">Go to Inventory management > Setup > Quality management > Quality charges.</span></span>
    * <span data-ttu-id="fc01b-147">Use la página Gastos de calidad para definir una clasificación de los gastos que se utilizarán en operaciones relacionadas con disconformidades.</span><span class="sxs-lookup"><span data-stu-id="fc01b-147">Use the Quality charges page to define a classification of charges that will used in operations related to nonconformances.</span></span>  
2. <span data-ttu-id="fc01b-148">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fc01b-148">Click New.</span></span>
3. <span data-ttu-id="fc01b-149">En el campo Código de gastos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fc01b-149">In the Charges code field, type a value.</span></span>
4. <span data-ttu-id="fc01b-150">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fc01b-150">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fc01b-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-151">Close the page.</span></span>

## <a name="define-the-operations-for-nonconformance-processing"></a><span data-ttu-id="fc01b-152">Definir las operaciones para procesamiento de disconformidad</span><span class="sxs-lookup"><span data-stu-id="fc01b-152">Define the operations for nonconformance processing</span></span>
1. <span data-ttu-id="fc01b-153">Vaya a Gestión del inventario > Configurar > Administración de calidad > Operaciones.</span><span class="sxs-lookup"><span data-stu-id="fc01b-153">Go to Inventory management > Setup > Quality management > Operations.</span></span>
    * <span data-ttu-id="fc01b-154">Use la página Operaciones para definir una clasificación del trabajo que se puede efectuar para un caso de disconformidad aprobado.</span><span class="sxs-lookup"><span data-stu-id="fc01b-154">Use the Operations page to define a classification of the work that may be performed for an approved nonconformance.</span></span> <span data-ttu-id="fc01b-155">Al relacionar una operación relacionada con una disconformidad, se puede definir información acerca del material asociado, las horas de trabajo y los gastos varios requeridos para llevar a cabo la operación.</span><span class="sxs-lookup"><span data-stu-id="fc01b-155">When you relate an operation to a nonconformance, you can define information about the associated material, labor hours, and miscellaneous charges that are required to perform the operation.</span></span> <span data-ttu-id="fc01b-156">Esta información proporciona la base para calcular un coste estimado para la ejecución de la operación.</span><span class="sxs-lookup"><span data-stu-id="fc01b-156">This information provides the basis for calculating an estimated cost for performing the operation.</span></span>  
2. <span data-ttu-id="fc01b-157">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fc01b-157">Click New.</span></span>
3. <span data-ttu-id="fc01b-158">En el campo Operación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fc01b-158">In the Operation field, type a value.</span></span>
4. <span data-ttu-id="fc01b-159">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fc01b-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fc01b-160">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-160">Close the page.</span></span>

## <a name="define-problem-types-for-nonconformance-processing"></a><span data-ttu-id="fc01b-161">Definir tipos de problema para procesamiento de disconformidad</span><span class="sxs-lookup"><span data-stu-id="fc01b-161">Define problem types for nonconformance processing</span></span>
1. <span data-ttu-id="fc01b-162">Vaya a Gestión del inventario > Configurar > Administración de calidad > Tipos de problemas.</span><span class="sxs-lookup"><span data-stu-id="fc01b-162">Go to Inventory management > Setup > Quality management > Problem types.</span></span>
    * <span data-ttu-id="fc01b-163">Use la página Tipos de problemas para definir una clasificación de problemas de calidad encontradas en los distintos tipos de disconformidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-163">Use the Problem types page to define a classification of quality problems that are encountered in the various nonconformance types.</span></span> <span data-ttu-id="fc01b-164">Entre los tipos de disconformidad se incluyen Interna, Cliente, Proveedor, Solicitud de servicio, Producción y Producción de coproductos.</span><span class="sxs-lookup"><span data-stu-id="fc01b-164">The nonconformance types include Internal, Customer, Vendor, Service request, Production, and Co-product production.</span></span> <span data-ttu-id="fc01b-165">Un tipo de problema único se puede asociar con varios tipos de disconformidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-165">A single problem type can be associated with multiple nonconformance types.</span></span>  
2. <span data-ttu-id="fc01b-166">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fc01b-166">Click New.</span></span>
3. <span data-ttu-id="fc01b-167">En el campo Tipo de problema, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fc01b-167">In the Problem type field, type a value.</span></span>
4. <span data-ttu-id="fc01b-168">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fc01b-168">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fc01b-169">Haga clic en Tipos de no conformidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-169">Click Non conformance types.</span></span>
    * <span data-ttu-id="fc01b-170">Use la página Tipos de no conformidad para autorizar el uso de un tipo de problema para uno o varios tipos de disconformidad.</span><span class="sxs-lookup"><span data-stu-id="fc01b-170">Use the Non conformance types page to authorize the use of a problem type for one or more of the nonconformance types.</span></span> <span data-ttu-id="fc01b-171">Por ejemplo, un tipo de problema relativo a un código defectuoso se podría aplicar a todos los tipos de no conformidad, mientras que un tipo de problema acerca de quejas del cliente sólo se puede aplicar a los tipos de no conformidad de cliente y solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="fc01b-171">For example, a problem type regarding a defect code could apply to all nonconformance types, whereas a problem type about customer complaints may only apply to the customer and service request nonconformance types.</span></span>  
6. <span data-ttu-id="fc01b-172">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fc01b-172">Click New.</span></span>
7. <span data-ttu-id="fc01b-173">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fc01b-173">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="fc01b-174">En el campo Tipo de no conformidad, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="fc01b-174">In the Non conformance type field, select an option.</span></span>
9. <span data-ttu-id="fc01b-175">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-175">Close the page.</span></span>
10. <span data-ttu-id="fc01b-176">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-176">Close the page.</span></span>

## <a name="define-quarantine-zones-for-nonconformance-processing"></a><span data-ttu-id="fc01b-177">Definir zonas de cuarentena para el procesamiento de disconformidad</span><span class="sxs-lookup"><span data-stu-id="fc01b-177">Define quarantine zones for nonconformance processing</span></span>
1. <span data-ttu-id="fc01b-178">Vaya a Gestión del inventario > Configurar > Administración de calidad > Zonas de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="fc01b-178">Go to Inventory management > Setup > Quality management > Quarantine zones.</span></span>
2. <span data-ttu-id="fc01b-179">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fc01b-179">Click New.</span></span>
3. <span data-ttu-id="fc01b-180">En el campo Zona de cuarentena, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fc01b-180">In the Quarantine zone field, type a value.</span></span>
4. <span data-ttu-id="fc01b-181">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fc01b-181">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fc01b-182">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fc01b-182">Close the page.</span></span>


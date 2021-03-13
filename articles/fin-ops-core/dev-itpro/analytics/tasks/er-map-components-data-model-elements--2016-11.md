---
title: ER Asignar componentes del formato creado a los elementos del modelo de datos (noviembre de 2016)
description: Este tema describe cómo asignar elementos del modelo de datos a componentes de la configuración de informes electrónicos (ER) creada.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 043c66cf3345678aa7750ef50323700384579299
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093782"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a><span data-ttu-id="43433-103">ER Asignar componentes del formato creado a los elementos del modelo de datos (noviembre de 2016)</span><span class="sxs-lookup"><span data-stu-id="43433-103">ER Map components of the created format to data model elements (November 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="43433-104">El procedimiento siguiente muestra cómo un usuario con rol de Administrador del sistema o de Desarrollador de informes electrónicos puede asignar elementos del modelo de datos a componentes de la configuración de informes electrónicos (ER) creada, lo que define un formato de documento electrónico para el dominio de pagos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="43433-104">The following procedure shows how a user in either the System administrator or Electronic reporting developer role can map data model elements to components of the created Electronic reporting (ER) configuration, which defines an electronic document format for the payments business domain.</span></span> <span data-ttu-id="43433-105">Este formato se utilizará después para generar documentos electrónicos para el procesamiento de pagos.</span><span class="sxs-lookup"><span data-stu-id="43433-105">This format will be used later to generate electronic documents for processing payments.</span></span> <span data-ttu-id="43433-106">En este ejemplo, usted creará una configuración de formato para la empresa de muestra "Litware, Inc".</span><span class="sxs-lookup"><span data-stu-id="43433-106">In this example, you will create a format configuration for the sample company, 'Litware, Inc.'.</span></span> <span data-ttu-id="43433-107">Estos pasos se pueden realizar con cualquier empresa, ya que las configuraciones de informes electrónicos se comparten en todas las empresas.</span><span class="sxs-lookup"><span data-stu-id="43433-107">These steps can be performed in any company as ER configurations are shared for all companies.</span></span> <span data-ttu-id="43433-108">Para finalizar estos pasos, primero debe completar los pasos en la guía de tareas "Creación de una configuración de formato".</span><span class="sxs-lookup"><span data-stu-id="43433-108">To complete these steps, you must first complete the steps in the "Create a format configuration" task guide.</span></span>


## <a name="select-a-format-configuration"></a><span data-ttu-id="43433-109">Seleccione una configuración de formato</span><span class="sxs-lookup"><span data-stu-id="43433-109">Select a format configuration</span></span>
1. <span data-ttu-id="43433-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="43433-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="43433-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="43433-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="43433-112">En el árbol, expanda "Pagos (modelo simplificado)".</span><span class="sxs-lookup"><span data-stu-id="43433-112">In the tree, expand 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="43433-113">En el árbol, seleccione "Pagos (modelo simplificado)\BACS (ficticio Reino Unido)".</span><span class="sxs-lookup"><span data-stu-id="43433-113">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
5. <span data-ttu-id="43433-114">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="43433-114">Click Designer.</span></span>

## <a name="map-format-components-to-data-model-elements"></a><span data-ttu-id="43433-115">Asignación de los componentes de formato a los elementos del modelo de datos</span><span class="sxs-lookup"><span data-stu-id="43433-115">Map format components to data model elements</span></span>
1. <span data-ttu-id="43433-116">Haga clic en Expandir/Contraer.</span><span class="sxs-lookup"><span data-stu-id="43433-116">Click Expand/collapse.</span></span>
2. <span data-ttu-id="43433-117">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="43433-117">Click the Mapping tab.</span></span>
3. <span data-ttu-id="43433-118">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="43433-118">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="43433-119">En el árbol, seleccione 'Xml\Mensaje\ProcessingDate\DateTime".</span><span class="sxs-lookup"><span data-stu-id="43433-119">In the tree, select 'Xml\Message\ProcessingDate\DateTime'.</span></span>
5. <span data-ttu-id="43433-120">En el árbol, seleccione "modelo\ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="43433-120">In the tree, select 'model\ProcessingDateTime'.</span></span>
6. <span data-ttu-id="43433-121">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-121">Click Bind.</span></span>
7. <span data-ttu-id="43433-122">En el árbol, seleccione "'Xml\Mensaje\MessageId\Cadena".</span><span class="sxs-lookup"><span data-stu-id="43433-122">In the tree, select 'Xml\Message\MessageId\String'.</span></span>
8. <span data-ttu-id="43433-123">En el árbol, seleccione "modelo\MessageIdentification".</span><span class="sxs-lookup"><span data-stu-id="43433-123">In the tree, select 'model\MessageIdentification'.</span></span>
9. <span data-ttu-id="43433-124">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-124">Click Bind.</span></span>
10. <span data-ttu-id="43433-125">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="43433-125">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="43433-126">En el árbol, seleccione "Xml\Mensaje\Pagos\Importe\Cadena".</span><span class="sxs-lookup"><span data-stu-id="43433-126">In the tree, select 'Xml\Message\Payments\Item\Amount\String'.</span></span>
12. <span data-ttu-id="43433-127">En el árbol, seleccione "modelo\Pagos\InstructedAmount".</span><span class="sxs-lookup"><span data-stu-id="43433-127">In the tree, select 'model\Payments\InstructedAmount'.</span></span>
13. <span data-ttu-id="43433-128">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-128">Click Bind.</span></span>
14. <span data-ttu-id="43433-129">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\TransDate\DateTime".</span><span class="sxs-lookup"><span data-stu-id="43433-129">In the tree, select 'Xml\Message\Payments\Item\TransDate\DateTime'.</span></span>
15. <span data-ttu-id="43433-130">En el árbol, seleccione "modelo\Pagos\TransactionDate".</span><span class="sxs-lookup"><span data-stu-id="43433-130">In the tree, select 'model\Payments\TransactionDate'.</span></span>
16. <span data-ttu-id="43433-131">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-131">Click Bind.</span></span>
17. <span data-ttu-id="43433-132">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Descripción\Cadena".</span><span class="sxs-lookup"><span data-stu-id="43433-132">In the tree, select 'Xml\Message\Payments\Item\Description\String'.</span></span>
18. <span data-ttu-id="43433-133">En el árbol, seleccione modelo\Pagos\Descripción.</span><span class="sxs-lookup"><span data-stu-id="43433-133">In the tree, select 'model\Payments\Description'.</span></span>
19. <span data-ttu-id="43433-134">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-134">Click Bind.</span></span>
20. <span data-ttu-id="43433-135">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Divisa\Cadena".</span><span class="sxs-lookup"><span data-stu-id="43433-135">In the tree, select 'Xml\Message\Payments\Item\Currency\String'.</span></span>
21. <span data-ttu-id="43433-136">En el árbol, seleccione "modelo\Pagos\Divisa".</span><span class="sxs-lookup"><span data-stu-id="43433-136">In the tree, select 'model\Payments\Currency'.</span></span>
22. <span data-ttu-id="43433-137">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-137">Click Bind.</span></span>
23. <span data-ttu-id="43433-138">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Id.".</span><span class="sxs-lookup"><span data-stu-id="43433-138">In the tree, select 'Xml\Message\Payments\Item\Id'.</span></span>
24. <span data-ttu-id="43433-139">En el árbol, seleccione "modelo\Pagos\End2EndID".</span><span class="sxs-lookup"><span data-stu-id="43433-139">In the tree, select 'model\Payments\End2EndID'.</span></span>
25. <span data-ttu-id="43433-140">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-140">Click Bind.</span></span>
26. <span data-ttu-id="43433-141">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="43433-141">In the tree, expand 'model\Payments\Creditor'.</span></span>
27. <span data-ttu-id="43433-142">En el árbol, expanda modelo\Pagos\Acreedor\Cuenta.</span><span class="sxs-lookup"><span data-stu-id="43433-142">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
28. <span data-ttu-id="43433-143">En el árbol, expanda modelo\Pagos\Acreedor\Agente.</span><span class="sxs-lookup"><span data-stu-id="43433-143">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
29. <span data-ttu-id="43433-144">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Cadena".</span><span class="sxs-lookup"><span data-stu-id="43433-144">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
30. <span data-ttu-id="43433-145">En el árbol, seleccione modelo\Pagos\Acreedor\Nombre.</span><span class="sxs-lookup"><span data-stu-id="43433-145">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
31. <span data-ttu-id="43433-146">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-146">Click Bind.</span></span>
32. <span data-ttu-id="43433-147">En el árbol, seleccione 'Xml\Mensaje\Pagos\Artículo\Proveedor\Banco\RoutingNumber\Cadena".</span><span class="sxs-lookup"><span data-stu-id="43433-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String'.</span></span>
33. <span data-ttu-id="43433-148">En el árbol, seleccione "modelo\Pagos\Acreedor\Agente\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="43433-148">In the tree, select 'model\Payments\Creditor\Agent\RoutingNumber'.</span></span>
34. <span data-ttu-id="43433-149">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-149">Click Bind.</span></span>
35. <span data-ttu-id="43433-150">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Banco\AccountNumber\Cadena".</span><span class="sxs-lookup"><span data-stu-id="43433-150">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String'.</span></span>
36. <span data-ttu-id="43433-151">En el árbol, seleccione modelo\Pagos\Acreedor\Cuenta\Número.</span><span class="sxs-lookup"><span data-stu-id="43433-151">In the tree, select 'model\Payments\Creditor\Account\Number'.</span></span>
37. <span data-ttu-id="43433-152">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-152">Click Bind.</span></span>
38. <span data-ttu-id="43433-153">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Pagador\Nombre\Cadena".</span><span class="sxs-lookup"><span data-stu-id="43433-153">In the tree, select 'Xml\Message\Payments\Item\Payer\Name\String'.</span></span>
39. <span data-ttu-id="43433-154">En el árbol, expanda modelo\Pagos\Deudor.</span><span class="sxs-lookup"><span data-stu-id="43433-154">In the tree, expand 'model\Payments\Debtor'.</span></span>
40. <span data-ttu-id="43433-155">En el árbol, expanda modelo\Pagos\Deudor\Cuenta.</span><span class="sxs-lookup"><span data-stu-id="43433-155">In the tree, expand 'model\Payments\Debtor\Account'.</span></span>
41. <span data-ttu-id="43433-156">En el árbol, expanda modelo\Pagos\Deudor\Agente.</span><span class="sxs-lookup"><span data-stu-id="43433-156">In the tree, expand 'model\Payments\Debtor\Agent'.</span></span>
42. <span data-ttu-id="43433-157">En el árbol, seleccione modelo\Pagos\Deudor\Nombre.</span><span class="sxs-lookup"><span data-stu-id="43433-157">In the tree, select 'model\Payments\Debtor\Name'.</span></span>
43. <span data-ttu-id="43433-158">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-158">Click Bind.</span></span>
44. <span data-ttu-id="43433-159">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Pagador\Banco\RoutingNumber\Cadena".</span><span class="sxs-lookup"><span data-stu-id="43433-159">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String'.</span></span>
45. <span data-ttu-id="43433-160">En el árbol, seleccione "modelo\Pagos\Deudor\Agente\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="43433-160">In the tree, select 'model\Payments\Debtor\Agent\RoutingNumber'.</span></span>
46. <span data-ttu-id="43433-161">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-161">Click Bind.</span></span>
47. <span data-ttu-id="43433-162">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Pagador\Banco\AccountNumber\Cadena".</span><span class="sxs-lookup"><span data-stu-id="43433-162">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String'.</span></span>
48. <span data-ttu-id="43433-163">En el árbol, seleccione modelo\Pagos\Deudor\Cuenta\Número.</span><span class="sxs-lookup"><span data-stu-id="43433-163">In the tree, select 'model\Payments\Debtor\Account\Number'.</span></span>
49. <span data-ttu-id="43433-164">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-164">Click Bind.</span></span>
50. <span data-ttu-id="43433-165">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo".</span><span class="sxs-lookup"><span data-stu-id="43433-165">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="43433-166">En el árbol, seleccione modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="43433-166">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="43433-167">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="43433-167">Click Bind.</span></span>
53. <span data-ttu-id="43433-168">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="43433-168">Click Save.</span></span>

## <a name="validate-format-mapping"></a><span data-ttu-id="43433-169">Validación de la asignación de formato</span><span class="sxs-lookup"><span data-stu-id="43433-169">Validate format mapping</span></span>
1. <span data-ttu-id="43433-170">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="43433-170">Click Validate.</span></span>
    * <span data-ttu-id="43433-171">Valide la nueva asignación para garantizar que todos los enlaces son aceptables.</span><span class="sxs-lookup"><span data-stu-id="43433-171">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="43433-172">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="43433-172">Close the page.</span></span>

## <a name="change-status-of-the-current-version-of-format-configuration"></a><span data-ttu-id="43433-173">Cambio del estado de la versión actual de la configuración del formato</span><span class="sxs-lookup"><span data-stu-id="43433-173">Change status of the current version of format configuration</span></span>
<span data-ttu-id="43433-174">En los siguientes pasos, usted cambiará el estado de la configuración del formato de Borrador a Completado para que esté disponible para la generación de documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="43433-174">In the next steps, you'll change the status of the format configuration from Draft to Completed to make it available for payment document generation.</span></span>  
1. <span data-ttu-id="43433-175">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="43433-175">Click Change status.</span></span>
2. <span data-ttu-id="43433-176">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="43433-176">Click Complete.</span></span>
3. <span data-ttu-id="43433-177">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="43433-177">In the Description field, type a value.</span></span>
    * <span data-ttu-id="43433-178">Para ver un ejemplo, "versión 1".</span><span class="sxs-lookup"><span data-stu-id="43433-178">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="43433-179">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="43433-179">Click OK.</span></span>
5. <span data-ttu-id="43433-180">Seleccione la versión completada de la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="43433-180">Select completed version of the current configuration.</span></span>
    * <span data-ttu-id="43433-181">Tenga en cuenta que la configuración se guarda como una versión 1.1 completa: versión 1 del formato basado en la versión 1 del modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="43433-181">Note that the configuration is saved as completed version 1.1: version 1 of the format based on the version 1 of the data model.</span></span>  

## <a name="define-effective-date-for-completed-version-of-format"></a><span data-ttu-id="43433-182">Definición de la fecha de vigencia para la versión finalizada del formato</span><span class="sxs-lookup"><span data-stu-id="43433-182">Define effective date for completed version of format</span></span>
<span data-ttu-id="43433-183">Cada versión del formato se puede configurar como disponible para su uso a partir de una fecha concreta.</span><span class="sxs-lookup"><span data-stu-id="43433-183">Each format version can be configured as available for usage starting from a certain date.</span></span> <span data-ttu-id="43433-184">Cuando haya más de una versión de formato activa en una fecha concreta, se seleccionará para su uso el formato más reciente (según el número de versión).</span><span class="sxs-lookup"><span data-stu-id="43433-184">When more than one format version is active on a certain date, the latest format (based on version number) will be selected for usage.</span></span> <span data-ttu-id="43433-185">El valor de fecha de sesión se usa para seleccionar la versión adecuada.</span><span class="sxs-lookup"><span data-stu-id="43433-185">The session date value is used for proper version selection.</span></span>  

## <a name="restrict-access-to-created-format-from-companies"></a><span data-ttu-id="43433-186">Restricción del acceso al formato creado desde empresas</span><span class="sxs-lookup"><span data-stu-id="43433-186">Restrict access to created format from companies</span></span>
1. <span data-ttu-id="43433-187">Expanda la sección Códigos ISO de país/región.</span><span class="sxs-lookup"><span data-stu-id="43433-187">Expand the ISO Country/region codes section.</span></span>
    * <span data-ttu-id="43433-188">Los accesos a los formatos se pueden restringir identificando países o regiones aplicables.</span><span class="sxs-lookup"><span data-stu-id="43433-188">Each format access can be restricted by identifying particular countries/regions in which a format is applicable.</span></span> <span data-ttu-id="43433-189">Si la lista de países o regiones para el formato concreto está vacía, el formato se puede usar en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="43433-189">When the list of countries/regions for particular format is empty, this format can be used in any company.</span></span> <span data-ttu-id="43433-190">Si se insertan códigos de país o región ISO en la lista de países o regiones, el formato solo se puede usar en empresas si su sede principal se encuentra ubicada en dicho país o región.</span><span class="sxs-lookup"><span data-stu-id="43433-190">When some ISO country/region codes are inserted in the list of countries/regions, the format can only be use in companies if the primary address is in the country/region.</span></span>  


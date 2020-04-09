---
title: ER Actualizar el formato adoptando una nueva versión de base de ese formato
description: En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede mantener una configuración de formato de informes electrónicos.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52bc276a4a88971a7214fa09087cb1323b91aaf5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143291"
---
# <a name="er-upgrade-your-format-by-adopting-a-new-base-version-of-that-format"></a><span data-ttu-id="51db8-103">ER Actualizar el formato adoptando una nueva versión de base de ese formato</span><span class="sxs-lookup"><span data-stu-id="51db8-103">ER Upgrade your format by adopting a new, base version of that format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="51db8-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede mantener una configuración de formato de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="51db8-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can maintain an Electronic reporting (ER) format configuration.</span></span> <span data-ttu-id="51db8-105">Este procedimiento explica el modo en que se puede crear una versión personalizada de un formato en función del formato recibido de un proveedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="51db8-105">This procedure explains how a custom version of a format can be created based on the format received from a configuration provider (CP).</span></span> <span data-ttu-id="51db8-106">También explica cómo adoptar una nueva versión base de ese formato.</span><span class="sxs-lookup"><span data-stu-id="51db8-106">It also explains how to adopt a new, base version of that format.</span></span>

<span data-ttu-id="51db8-107">Para finalizar estos pasos, debe completar primero los pasos de los procedimientos "Creación y activación de un proveedor de configuraciones" y "Usar formato creado para generar documentos electrónicos para pagos”.</span><span class="sxs-lookup"><span data-stu-id="51db8-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" and "Use created format to generate electronic documents for payments" procedures.</span></span> <span data-ttu-id="51db8-108">Estos pasos se pueden llevar a cabo en la empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="51db8-108">These steps can be performed in the GBSI company.</span></span>

## <a name="select-format-configuration-for-customization"></a><span data-ttu-id="51db8-109">Seleccionar configuración del formato para personalización</span><span class="sxs-lookup"><span data-stu-id="51db8-109">Select format configuration for customization</span></span>
1. <span data-ttu-id="51db8-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="51db8-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="51db8-111">En este ejemplo, la empresa de muestra Litware, Inc., (https://www.litware.com), actuará como proveedor de configuración que admite las configuraciones de formato para pagos electrónicos para un país concreto.</span><span class="sxs-lookup"><span data-stu-id="51db8-111">In this example, sample company Litware, Inc. (https://www.litware.com) will act as a configuration provider that supports format configurations for electronic payments for a particular country.</span></span>    <span data-ttu-id="51db8-112">La empresa de muestra Proseware, Inc (http://www.proseware.com) actuará como consumidor de la configuración del formato que Litware, Inc. proporcionó.</span><span class="sxs-lookup"><span data-stu-id="51db8-112">Sample company Proseware, Inc. (http://www.proseware.com) will act as a consumer of the format configuration that Litware, Inc. provided.</span></span> <span data-ttu-id="51db8-113">Proseware, Inc. usa formatos en determinadas regiones de ese país.</span><span class="sxs-lookup"><span data-stu-id="51db8-113">Proseware, Inc. uses formats in certain regions of that country.</span></span>  
2. <span data-ttu-id="51db8-114">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="51db8-114">Click Reporting configurations.</span></span>
3. <span data-ttu-id="51db8-115">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="51db8-115">Click Show filters.</span></span>
4. <span data-ttu-id="51db8-116">Aplique los siguientes filtros: especifique un valor de filtro de "BACS (UK ficticia)" en el campo "Nombre" mediante el operador de filtro "empieza por".</span><span class="sxs-lookup"><span data-stu-id="51db8-116">Apply the following filters: Enter a filter value of "BACS (UK fictitious)" on the "Name" field using the "begins with" filter operator.</span></span>
  
    <span data-ttu-id="51db8-117">La configuración de formato seleccionada BACS (ficticia del Reino Unido) es propiedad del proveedor Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="51db8-117">The selected format configuration BACS (UK fictitious) is owned by provider Litware, Inc.</span></span>  

5. <span data-ttu-id="51db8-118">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="51db8-118">Click Show filters.</span></span>
6. <span data-ttu-id="51db8-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="51db8-119">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="51db8-120">La versión del formato con el estado de Completado se usará por Proseware, Inc. para personalización.</span><span class="sxs-lookup"><span data-stu-id="51db8-120">The version of the format with the status of Completed will be used by Proseware, Inc. for customization.</span></span>  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a><span data-ttu-id="51db8-121">Crear una nueva configuración para su formato personalizado de documento electrónico</span><span class="sxs-lookup"><span data-stu-id="51db8-121">Create a new configuration for your custom format of electronic document</span></span>
<span data-ttu-id="51db8-122">Proseware, Inc. recibió la versión 1.1 de la configuración de BACS (ficticia del Reino Unido) que contiene el formato inicial para generar documentos de pago electrónico de Litware, Inc. de acuerdo a su servicio de suscripción.</span><span class="sxs-lookup"><span data-stu-id="51db8-122">Proseware, Inc. received version 1.1 of BACS (UK fictitious) configuration that contains the initial format to generate electronic payment documents from Litware, Inc. in accordance to their service subscription.</span></span> <span data-ttu-id="51db8-123">Proseware, Inc. desea comenzar a usar esto como estándar para su país pero se requiere alguna personalización para admitir requisitos regionales específicos.</span><span class="sxs-lookup"><span data-stu-id="51db8-123">Proseware, Inc. wants to start using this as a standard for their country but some customization is required to support specific regional requirements.</span></span> <span data-ttu-id="51db8-124">Proseware, Inc. también desea conservar la capacidad de actualizar un formato personalizado tan pronto como llegue una nueva versión (con los cambios para admitir nuevos requisitos específicos de país) de Litware, Inc. y quieren desarrollar esta actualización con el coste más bajo.</span><span class="sxs-lookup"><span data-stu-id="51db8-124">Proseware, Inc. also wants to keep the ability to upgrade a custom format as soon as a new version of it (with changes to support new country-specific requirements) comes from Litware, Inc. and they want to perform this upgrade with the lowest cost.</span></span>  

<span data-ttu-id="51db8-125">Para ello, Proseware, Inc. debe crear una configuración mediante la configuración BACS (ficticio de Reino Unido) de Litware, Inc. como base.</span><span class="sxs-lookup"><span data-stu-id="51db8-125">To do this, Proseware, Inc. needs to create a configuration using the Litware, Inc. configuration BACS (UK fictitious) as a base.</span></span>  

1. <span data-ttu-id="51db8-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="51db8-126">Close the page.</span></span>
2. <span data-ttu-id="51db8-127">seleccione Proseware, Inc. para convertirlo en un proveedor activo.</span><span class="sxs-lookup"><span data-stu-id="51db8-127">Select Proseware, Inc. to make it an active provider.</span></span>
3. <span data-ttu-id="51db8-128">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="51db8-128">Click Set active.</span></span>
4. <span data-ttu-id="51db8-129">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="51db8-129">Click Reporting configurations.</span></span>
5. <span data-ttu-id="51db8-130">En el árbol, expanda "Pagos (modelo simplificado)".</span><span class="sxs-lookup"><span data-stu-id="51db8-130">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="51db8-131">En el árbol, seleccione "Pagos (modelo simplificado\BACS (ficticio Reino Unido)".</span><span class="sxs-lookup"><span data-stu-id="51db8-131">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="51db8-132">Seleccione la configuración BACS (ficticio de Reino Unido) de Litware, Inc. Proseware, Inc. utilizará la versión 1.1 como base para la versión personalizada.</span><span class="sxs-lookup"><span data-stu-id="51db8-132">Select the BACS (UK fictitious) configuration from Litware, Inc. Proseware, Inc. will use version 1.1 as a base for the custom version.</span></span>  

7. <span data-ttu-id="51db8-133">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="51db8-133">Click Create configuration to open the drop dialog.</span></span>

    <span data-ttu-id="51db8-134">Esto le permite crear una nueva configuración para un formato de pago personalizado.</span><span class="sxs-lookup"><span data-stu-id="51db8-134">This lets you create a new configuration for a custom payment format.</span></span>  

8. <span data-ttu-id="51db8-135">En el campo Nuevo, especifique "Derivan del nombre: BACS (ficticio Reino Unido), Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="51db8-135">In the New field, enter 'Derive from Name: BACS (UK fictitious), Litware, Inc.'.</span></span>

    <span data-ttu-id="51db8-136">Seleccione la opción Derivar para confirmar el uso de BACS (ficticio Reino Unido) como la base para crear la versión personalizada.</span><span class="sxs-lookup"><span data-stu-id="51db8-136">Select the Derive option to confirm the usage of BACS (UK fictitious) as the base for creating the custom version.</span></span>  

9. <span data-ttu-id="51db8-137">En el campo Nombre, escriba "BACS (personalizado ficticio del Reino Unido)".</span><span class="sxs-lookup"><span data-stu-id="51db8-137">In the Name field, type 'BACS (UK fictitious custom)'.</span></span>
10. <span data-ttu-id="51db8-138">En el campo Descripción, escriba "Formato de pago de proveedor BACS (Reino Unido ficticio personalizado)".</span><span class="sxs-lookup"><span data-stu-id="51db8-138">In the Description field, type 'BACS vendor payment (UK fictitious custom)'.</span></span>

    <span data-ttu-id="51db8-139">El proveedor de configuraciones activo (Proseware, Inc.) se especifica automáticamente aquí.</span><span class="sxs-lookup"><span data-stu-id="51db8-139">The active configuration provider (Proseware, Inc.) is automatically entered here.</span></span> <span data-ttu-id="51db8-140">Este proveedor podrá mantener esta configuración.</span><span class="sxs-lookup"><span data-stu-id="51db8-140">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="51db8-141">Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.</span><span class="sxs-lookup"><span data-stu-id="51db8-141">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

11. <span data-ttu-id="51db8-142">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="51db8-142">Click Create configuration.</span></span>

## <a name="customize-your-format-for-the-electronic-document"></a><span data-ttu-id="51db8-143">Personalizar el formato para el documento electrónico</span><span class="sxs-lookup"><span data-stu-id="51db8-143">Customize your format for the electronic document</span></span>
1. <span data-ttu-id="51db8-144">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="51db8-144">Click Designer.</span></span>
2. <span data-ttu-id="51db8-145">Haga clic en Expandir/Contraer.</span><span class="sxs-lookup"><span data-stu-id="51db8-145">Click Expand/collapse.</span></span>
3. <span data-ttu-id="51db8-146">Haga clic en Expandir/Contraer.</span><span class="sxs-lookup"><span data-stu-id="51db8-146">Click Expand/collapse.</span></span>
4. <span data-ttu-id="51db8-147">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Banco".</span><span class="sxs-lookup"><span data-stu-id="51db8-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="51db8-148">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="51db8-148">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="51db8-149">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="51db8-149">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="51db8-150">En el campo Nombre, escriba "IBAN".</span><span class="sxs-lookup"><span data-stu-id="51db8-150">In the Name field, type 'IBAN'.</span></span>
8. <span data-ttu-id="51db8-151">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="51db8-151">Click OK.</span></span>
9. <span data-ttu-id="51db8-152">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\IBAN".</span><span class="sxs-lookup"><span data-stu-id="51db8-152">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\IBAN'.</span></span>
10. <span data-ttu-id="51db8-153">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="51db8-153">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="51db8-154">En el árbol, seleccione "Texto\Cadena".</span><span class="sxs-lookup"><span data-stu-id="51db8-154">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="51db8-155">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="51db8-155">Click OK.</span></span>
13. <span data-ttu-id="51db8-156">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Cadena".</span><span class="sxs-lookup"><span data-stu-id="51db8-156">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="51db8-157">Escriba "60" en el campo Longitud máxima.</span><span class="sxs-lookup"><span data-stu-id="51db8-157">In the Maximum length field, enter '60'.</span></span>
15. <span data-ttu-id="51db8-158">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="51db8-158">Click the Mapping tab.</span></span>
16. <span data-ttu-id="51db8-159">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="51db8-159">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="51db8-160">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="51db8-160">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="51db8-161">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="51db8-161">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="51db8-162">En el árbol, expanda modelo\Pagos\Acreedor\Cuenta.</span><span class="sxs-lookup"><span data-stu-id="51db8-162">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
20. <span data-ttu-id="51db8-163">En el árbol, seleccione "modelo\Pagos\Acreedor\Cuenta\IBAN".</span><span class="sxs-lookup"><span data-stu-id="51db8-163">In the tree, select 'model\Payments\Creditor\Account\IBAN'.</span></span>
21. <span data-ttu-id="51db8-164">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo =  modelo.Pagos\Proveedor\Banco\IBAN\Cadena".</span><span class="sxs-lookup"><span data-stu-id="51db8-164">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\IBAN\String'.</span></span>
22. <span data-ttu-id="51db8-165">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="51db8-165">Click Bind.</span></span>
23. <span data-ttu-id="51db8-166">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="51db8-166">Click Save.</span></span>

## <a name="validate-the-customized-format"></a><span data-ttu-id="51db8-167">Validar el formato personalizado</span><span class="sxs-lookup"><span data-stu-id="51db8-167">Validate the customized format</span></span>
1. <span data-ttu-id="51db8-168">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="51db8-168">Click Validate.</span></span>

    <span data-ttu-id="51db8-169">Valide el diseño de formato personalizado y los cambios de asignación de datos para asegurarse de que todos los enlaces son correctos.</span><span class="sxs-lookup"><span data-stu-id="51db8-169">Validate the customized format layout and data mapping changes to make sure that all bindings are okay.</span></span>  

2. <span data-ttu-id="51db8-170">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="51db8-170">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a><span data-ttu-id="51db8-171">Cambie el estado de la versión actual de la configuración del formato personalizada</span><span class="sxs-lookup"><span data-stu-id="51db8-171">Change the status of the current version of the custom format configuration</span></span>
<span data-ttu-id="51db8-172">Cambie el estado de la configuración del formato diseñado de Borrador a Completado para que esté disponible para la generación de documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="51db8-172">Change the status of the designed format configuration from Draft to Completed to make it available for payment document generation.</span></span>  

1. <span data-ttu-id="51db8-173">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="51db8-173">Click Change status.</span></span>

    <span data-ttu-id="51db8-174">Observe cómo la versión actual de la configuración seleccionada se encuentra en el estado Borrador.</span><span class="sxs-lookup"><span data-stu-id="51db8-174">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="51db8-175">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="51db8-175">Click Complete.</span></span>
3. <span data-ttu-id="51db8-176">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="51db8-176">In the Description field, type a value.</span></span>
4. <span data-ttu-id="51db8-177">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="51db8-177">Click OK.</span></span>
5. <span data-ttu-id="51db8-178">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="51db8-178">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="51db8-179">Observe cómo la configuración creada se guarda como versión completada 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="51db8-179">Note that the created configuration is saved as completed version 1.1.1.</span></span> <span data-ttu-id="51db8-180">Esto significa que es la versión 1 del formato BACS personalizado (personalizado ficticio del Reino Unido), que se basa en la versión 1 del formato BACS (personalizado ficticio del Reino Unido), que se basa en la versión 1 del modelo de datos de pagos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="51db8-180">This means it is version 1 of the custom BACS (UK fictitious custom) format, which is based on version 1 of the BACS (UK fictitious) format, which is based on version 1 of the Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-to-generate-payment-files"></a><span data-ttu-id="51db8-181">Probar el formato personalizado para generar archivos de pago</span><span class="sxs-lookup"><span data-stu-id="51db8-181">Test the customized format to generate payment files</span></span>
<span data-ttu-id="51db8-182">Complete los pasos del procedimiento “Usar formato creado para generar documentos electrónicos para pagos” en una sesión paralela de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="51db8-182">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in a parallel Finance and Operations session.</span></span> <span data-ttu-id="51db8-183">Seleccione el formato de BACS (personalizado ficticio del Reino Unido) en parámetros del método de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="51db8-183">Select the BACS (UK fictitious custom) format in electronic payment method parameters.</span></span> <span data-ttu-id="51db8-184">Asegúrese de que el archivo de pago creado contiene el nodo XML recién introducido que presenta código IBAN de acuerdo con los requisitos regionales.</span><span class="sxs-lookup"><span data-stu-id="51db8-184">Make sure that the created payment file contains the recently introduced XML node presenting IBAN code in accordance to regional requirements.</span></span>  

## <a name="update-the-existing-country-specific-configuration"></a><span data-ttu-id="51db8-185">Actualizar la configuración específica de país existente</span><span class="sxs-lookup"><span data-stu-id="51db8-185">Update the existing country-specific configuration</span></span>
<span data-ttu-id="51db8-186">Litware. Inc debe actualizar la configuración de BACS (ficticio del Reino Unido) y adoptar nuevos requisitos de país para gestionar el formato de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="51db8-186">Litware, Inc. needs to update the BACS (UK fictitious) configuration and adopt new country requirements for managing the format of the electronic document.</span></span> <span data-ttu-id="51db8-187">Más adelante, esto se incluirá en una nueva versión de esta configuración que se ofrecerá para los suscriptores de servicio, incluidos Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="51db8-187">Later, this will be enclosed in a new version of this configuration that will be offered for service subscribers, including Proseware, Inc.</span></span>  

<span data-ttu-id="51db8-188">En los procesos relacionados con las disposiciones de servicio reales, cada nueva versión de BACS (ficticio del Reino Unido) se puede importar por Proseware, Inc. desde Litware, Inc. configuraciones repositorias LCS.</span><span class="sxs-lookup"><span data-stu-id="51db8-188">In real service provision related processes, each new version of BACS (UK fictitious) can be imported by Proseware, Inc. from Litware, Inc. configurations' LCS repository.</span></span> <span data-ttu-id="51db8-189">En este procedimiento simularemos esto actualizando BACS (ficticio del Reino Unido) en nombre de un proveedor de servicio.</span><span class="sxs-lookup"><span data-stu-id="51db8-189">In this procedure we will simulate this by updating BACS (UK fictitious) on behalf of a service provider.</span></span>  

1. <span data-ttu-id="51db8-190">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="51db8-190">Close the page.</span></span>
2. <span data-ttu-id="51db8-191">Seleccione el proveedor Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="51db8-191">Select Litware, inc. provider.</span></span>
3. <span data-ttu-id="51db8-192">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="51db8-192">Click Set active.</span></span>
4. <span data-ttu-id="51db8-193">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="51db8-193">Click Reporting configurations.</span></span>
5. <span data-ttu-id="51db8-194">En el árbol, expanda "Pagos (modelo simplificado)".</span><span class="sxs-lookup"><span data-stu-id="51db8-194">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="51db8-195">En el árbol, seleccione "Pagos (modelo simplificado\BACS (ficticio Reino Unido)".</span><span class="sxs-lookup"><span data-stu-id="51db8-195">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="51db8-196">La versión provisional del provedor Litware, Inc. (ficticio del Reino Unido) se selecciona para incorporar cambios para admitir nuevos requisitos específicos de país.</span><span class="sxs-lookup"><span data-stu-id="51db8-196">The draft version owned by Litware, Inc. provider BACS (UK fictitious) is selected to bring in changes to support new country-specific requirements.</span></span>  

## <a name="localize-the-base-format-of-the-electronic-document"></a><span data-ttu-id="51db8-197">Localizar el formato base del documento electrónico</span><span class="sxs-lookup"><span data-stu-id="51db8-197">Localize the base format of the electronic document</span></span>
<span data-ttu-id="51db8-198">Supongamos que hay nuevos requisitos regionales específicos del país que admite Litware, Inc.:</span><span class="sxs-lookup"><span data-stu-id="51db8-198">Assume that there are new country-specific requirements to be supported by Litware, Inc.:</span></span>  

- <span data-ttu-id="51db8-199">Un valor para el código SWIFT del banco del acreedor en cada transacción de pago.</span><span class="sxs-lookup"><span data-stu-id="51db8-199">A value for the creditor's bank SWIFT code in each payment transaction.</span></span>
- <span data-ttu-id="51db8-200">Un límite de 100 caracteres para la longitud del texto para el nombre del proveedor en un archivo de generación.</span><span class="sxs-lookup"><span data-stu-id="51db8-200">A limit of 100 characters for the length of text for the vendor's name in a generating file.</span></span>  
- <span data-ttu-id="51db8-201">Nuevos requisitos específicos de país</span><span class="sxs-lookup"><span data-stu-id="51db8-201">New country-specific requirements</span></span>  
- <span data-ttu-id="51db8-202">Seleccione la versión de borrador de la configuración que desee para introducir los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="51db8-202">Select the draft version of the desired configuration to introduce required changes.</span></span>  


1. <span data-ttu-id="51db8-203">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="51db8-203">Click Designer.</span></span>
2. <span data-ttu-id="51db8-204">Haga clic en Expandir/Contraer.</span><span class="sxs-lookup"><span data-stu-id="51db8-204">Click Expand/collapse.</span></span>
3. <span data-ttu-id="51db8-205">Haga clic en Expandir/Contraer.</span><span class="sxs-lookup"><span data-stu-id="51db8-205">Click Expand/collapse.</span></span>
4. <span data-ttu-id="51db8-206">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Banco".</span><span class="sxs-lookup"><span data-stu-id="51db8-206">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="51db8-207">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="51db8-207">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="51db8-208">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="51db8-208">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="51db8-209">En el campo Nombre, escriba "SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="51db8-209">In the Name field, type 'SWIFT'.</span></span>
8. <span data-ttu-id="51db8-210">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="51db8-210">Click OK.</span></span>
9. <span data-ttu-id="51db8-211">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\SWIFT".</span><span class="sxs-lookup"><span data-stu-id="51db8-211">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\SWIFT'.</span></span>
10. <span data-ttu-id="51db8-212">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="51db8-212">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="51db8-213">En el árbol, seleccione "Texto\Cadena".</span><span class="sxs-lookup"><span data-stu-id="51db8-213">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="51db8-214">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="51db8-214">Click OK.</span></span>
13. <span data-ttu-id="51db8-215">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Cadena".</span><span class="sxs-lookup"><span data-stu-id="51db8-215">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="51db8-216">Escriba "100" en el campo Longitud máxima.</span><span class="sxs-lookup"><span data-stu-id="51db8-216">In the Maximum length field, enter '100'.</span></span>
15. <span data-ttu-id="51db8-217">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="51db8-217">Click the Mapping tab.</span></span>
16. <span data-ttu-id="51db8-218">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="51db8-218">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="51db8-219">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="51db8-219">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="51db8-220">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="51db8-220">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="51db8-221">En el árbol, expanda modelo\Pagos\Acreedor\Agente.</span><span class="sxs-lookup"><span data-stu-id="51db8-221">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
20. <span data-ttu-id="51db8-222">En el árbol, seleccione "modelo\Pagos\Acreedor\Agente\SWIFT".</span><span class="sxs-lookup"><span data-stu-id="51db8-222">In the tree, select 'model\Payments\Creditor\Agent\SWIFT'.</span></span>
21. <span data-ttu-id="51db8-223">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo = modelo.Pagos\Proveedor\SWIFT\Cadena".</span><span class="sxs-lookup"><span data-stu-id="51db8-223">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\SWIFT\String'.</span></span>
22. <span data-ttu-id="51db8-224">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="51db8-224">Click Bind.</span></span>
23. <span data-ttu-id="51db8-225">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="51db8-225">Click Save.</span></span>

## <a name="validate-the-localized-format"></a><span data-ttu-id="51db8-226">Valide el formato localizado</span><span class="sxs-lookup"><span data-stu-id="51db8-226">Validate the localized format</span></span>
1. <span data-ttu-id="51db8-227">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="51db8-227">Click Validate.</span></span>
2. <span data-ttu-id="51db8-228">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="51db8-228">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a><span data-ttu-id="51db8-229">Cambiar el estado de la versión actual de la configuración del formato base</span><span class="sxs-lookup"><span data-stu-id="51db8-229">Change the status of the current version of the base format configuration</span></span>
<span data-ttu-id="51db8-230">Cambie el estado de la configuración del formato base actualizada de Borrador a Completado para que esté disponible para la generación de documentos de pago y actualizaciones de configuraciones de formato derivadas de él.</span><span class="sxs-lookup"><span data-stu-id="51db8-230">Change the status of the updated base format configuration from Draft to Completed to make it available for generation of payment documents and updates of format configurations derived from it.</span></span>  

1. <span data-ttu-id="51db8-231">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="51db8-231">Click Change status.</span></span>

    <span data-ttu-id="51db8-232">Observe cómo la versión actual de la configuración seleccionada se encuentra en el estado Borrador.</span><span class="sxs-lookup"><span data-stu-id="51db8-232">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="51db8-233">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="51db8-233">Click Complete.</span></span>
3. <span data-ttu-id="51db8-234">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="51db8-234">In the Description field, type a value.</span></span>
4. <span data-ttu-id="51db8-235">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="51db8-235">Click OK.</span></span>
5. <span data-ttu-id="51db8-236">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="51db8-236">In the list, find and select the desired record.</span></span>

## <a name="change-the-base-version-for-the-custom-format-configuration"></a><span data-ttu-id="51db8-237">Cambiar la versión de base para la configuración de formato personalizada</span><span class="sxs-lookup"><span data-stu-id="51db8-237">Change the base version for the custom format configuration</span></span>

<span data-ttu-id="51db8-238">Se informa a Proseware, Inc. de que hay una nueva versión 1.2 disponible de la configuración BACS (ficticio Reino Unido) para generar documentos de pago electrónico de acuerdo con los requisitos específicos de país anunciados recientemente.</span><span class="sxs-lookup"><span data-stu-id="51db8-238">Proseware, Inc. is informed that a new version 1.2 of BACS (UK fictitious) configuration is available to generate electronic payment documents in accordance to recently announced country-specific requirements.</span></span> <span data-ttu-id="51db8-239">Proseware, Inc. desea empezar a usarla como estándar para el país.</span><span class="sxs-lookup"><span data-stu-id="51db8-239">Proseware, Inc. wants to start using it as a standard for the country.</span></span>  

<span data-ttu-id="51db8-240">Para ello, Proseware, Inc. tiene que cambiar la versión de la configuración base por la configuración personalizada BACS (personalizada ficticia del Reino Unido).</span><span class="sxs-lookup"><span data-stu-id="51db8-240">To do this, Proseware, Inc. needs to change the base configuration version for the custom configuration BACS (UK fictitious custom).</span></span> <span data-ttu-id="51db8-241">En lugar de la versión 1.1 de BACS (ficticio Reino Unido), use la nueva versión 1.2.</span><span class="sxs-lookup"><span data-stu-id="51db8-241">Instead of version 1.1 of BACS (UK fictitious) use new version 1.2.</span></span>  

1. <span data-ttu-id="51db8-242">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="51db8-242">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="51db8-243">seleccione Proseware, Inc. para marcarlo como proveedor activo.</span><span class="sxs-lookup"><span data-stu-id="51db8-243">Select the Proseware, Inc. provider to mark it as active.</span></span>
3. <span data-ttu-id="51db8-244">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="51db8-244">Click Set active.</span></span>
4. <span data-ttu-id="51db8-245">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="51db8-245">Click Reporting configurations.</span></span>
5. <span data-ttu-id="51db8-246">En el árbol, expanda "Pagos (modelo simplificado)".</span><span class="sxs-lookup"><span data-stu-id="51db8-246">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="51db8-247">En el árbol, expanda "Pagos (modelo simplificado\BACS (ficticio Reino Unido)".</span><span class="sxs-lookup"><span data-stu-id="51db8-247">In the tree, expand 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
7. <span data-ttu-id="51db8-248">En el árbol, seleccione "Pagos (modelo simplificado\BACS (ficticio Reino Unido\BACS (personalizado ficticio del Reino Unido)".</span><span class="sxs-lookup"><span data-stu-id="51db8-248">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)\BACS (UK fictitious custom)'.</span></span>

    <span data-ttu-id="51db8-249">Seleccione la configuración BACS (personalizada ficticia del Reino Unido), que es propiedad de Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="51db8-249">Select the BACS (UK fictitious custom) configuration, which is owned by Proseware, Inc.</span></span>  

    <span data-ttu-id="51db8-250">Use la versión de borrador de la configuración seleccionada para introducir los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="51db8-250">Use the draft version of the selected configuration to introduce required changes.</span></span>  

8. <span data-ttu-id="51db8-251">Haga clic en Reorganizar.</span><span class="sxs-lookup"><span data-stu-id="51db8-251">Click Rebase.</span></span>

    <span data-ttu-id="51db8-252">Seleccione la nueva versión 1.2 de la configuración base que se aplicará como nueva base para actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="51db8-252">Select the new version 1.2 of the base configuration to be applied as a new base for updating the configuration.</span></span>  

9. <span data-ttu-id="51db8-253">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="51db8-253">Click OK.</span></span>

    <span data-ttu-id="51db8-254">Tenga en cuenta que se han detectado algunos conflictos entre la combinación de la versión personalizada y una nueva versión base que representa algunos cambios de formato que no se pueden combinar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="51db8-254">Note that some conflicts have been discovered between merging the custom version and a new base version representing some format changes that can't be merged automatically.</span></span>  

## <a name="resolve-rebase-conflicts"></a><span data-ttu-id="51db8-255">Resolver conflictos de reorganización</span><span class="sxs-lookup"><span data-stu-id="51db8-255">Resolve rebase conflicts</span></span>
1. <span data-ttu-id="51db8-256">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="51db8-256">Click Designer.</span></span>
    
    <span data-ttu-id="51db8-257">Observe que los cambios al límite de la longitud del texto del nombre del proveedor no se podrían resolver automáticamente.</span><span class="sxs-lookup"><span data-stu-id="51db8-257">Note that changes to the vendor's name text length limit couldn't be resolved automatically.</span></span> <span data-ttu-id="51db8-258">Por tanto, esto se presenta en una lista de conflictos.</span><span class="sxs-lookup"><span data-stu-id="51db8-258">Therefore, this is presented in a conflicts list.</span></span> <span data-ttu-id="51db8-259">Para cada conflicto del tipo Actualización, están disponibles las siguientes opciones: - Aplicar valor de base anterior (botón de la parte superior de la cuadrícula) para incorporar el valor de la versión base anterior (0 en nuestro caso).</span><span class="sxs-lookup"><span data-stu-id="51db8-259">For each conflict of type Update, the following options are available:  - Apply a prior base value (button on top of the grid) to bring in the previous base version value (0 in our case).</span></span>  <span data-ttu-id="51db8-260">- Aplicar un valor de base (botón encima de la cuadrícula) para incorporar el nuevo valor de la versión base (100 en nuestro caso).</span><span class="sxs-lookup"><span data-stu-id="51db8-260">- Apply a base value (button on top of the grid) to bring in the new base version value (100 in our case).</span></span>  <span data-ttu-id="51db8-261">- Mantenga su propio el valor (personalizado) (60 en nuestro caso).</span><span class="sxs-lookup"><span data-stu-id="51db8-261">- Keep your own (custom) value (60 in our case).</span></span>  <span data-ttu-id="51db8-262">Haga clic en Aplicar valor de base para aplicar un límite específico por país de 100 caracteres para la longitud del texto del nombre del proveedor.</span><span class="sxs-lookup"><span data-stu-id="51db8-262">Click Apply base value to apply a country-specific limit of 100 characters for vendor's name text length.</span></span>  

    <span data-ttu-id="51db8-263">Tenga en cuenta que Proseware, Inc y Litware, Inc tienen versiones personalizadas y locales de este formato con los códigos IBAN y SWIFT con componentes relacionados que se combinan automáticamente en el formato de gestión.</span><span class="sxs-lookup"><span data-stu-id="51db8-263">Note that Proseware, Inc. and Litware, Inc. have custom and local versions of this format using IBAN and SWIFT codes with related components that are automatically merged in the managing format.</span></span>  

2. <span data-ttu-id="51db8-264">Haga clic en Aplicar valor de base.</span><span class="sxs-lookup"><span data-stu-id="51db8-264">Click Apply base value.</span></span>

    <span data-ttu-id="51db8-265">Haga clic en Aplicar valor de base para aplicar el límite específico por país de 100 caracteres para nombres de proveedor.</span><span class="sxs-lookup"><span data-stu-id="51db8-265">Click Apply base value to apply the country-specific limit of 100 characters for vendor names.</span></span>  

3. <span data-ttu-id="51db8-266">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="51db8-266">Click Save.</span></span>

    <span data-ttu-id="51db8-267">Al guardar el formato se eliminarán conflictos resueltos de la lista de conflictos.</span><span class="sxs-lookup"><span data-stu-id="51db8-267">Saving the format will remove resolved conflicts from the conflicts list.</span></span>  

4. <span data-ttu-id="51db8-268">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="51db8-268">Close the page.</span></span>

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a><span data-ttu-id="51db8-269">Cambiar el estado de la nueva versión de la configuración del formato personalizada</span><span class="sxs-lookup"><span data-stu-id="51db8-269">Change the status of the new version of the custom format configuration</span></span>
1. <span data-ttu-id="51db8-270">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="51db8-270">Click Change status.</span></span>

    <span data-ttu-id="51db8-271">Cambie el estado de la configuración de formato personalizada y actualizada de Borrador a Completado.</span><span class="sxs-lookup"><span data-stu-id="51db8-271">Change the status of the updated, custom format configuration from Draft to Completed.</span></span> <span data-ttu-id="51db8-272">Esto hará que la configuración del formato esté disponible para generar documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="51db8-272">This will make the format configuration available for generating payment documents.</span></span> <span data-ttu-id="51db8-273">Observe cómo la versión actual de la configuración seleccionada se encuentra en el estado Borrador.</span><span class="sxs-lookup"><span data-stu-id="51db8-273">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="51db8-274">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="51db8-274">Click Complete.</span></span>
3. <span data-ttu-id="51db8-275">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="51db8-275">In the Description field, type a value.</span></span>
4. <span data-ttu-id="51db8-276">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="51db8-276">Click OK.</span></span>

    <span data-ttu-id="51db8-277">Tenga en cuenta que la configuración creada se guarda como la versión 1.2.2 completada: versión 2 del formato BACS base (personalizado ficticia del Reino Unido), que se basa en la versión 2 del formato BACS base (ficticio Reino Unido), que se basa en la versión 1 del modelo de datos de pagos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="51db8-277">Note that the created configuration is saved as completed version 1.2.2: version 2 of base BACS (UK fictitious custom) format, which is based on version 2 of base BACS (UK fictitious) format, which is based on version 1 of Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-for-payment-files-generation"></a><span data-ttu-id="51db8-278">Probar el formato personalizado para generación de archivos de pago</span><span class="sxs-lookup"><span data-stu-id="51db8-278">Test the customized format for payment files generation</span></span>
<span data-ttu-id="51db8-279">Complete los pasos del procedimiento “Usar formato creado para generar documentos electrónicos para pagos” en una sesión paralela de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="51db8-279">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in parallel Finance and Operations session.</span></span> <span data-ttu-id="51db8-280">Seleccione el formato "BACS (personalizado ficticio del Reino Unido)" en parámetros del método de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="51db8-280">Select the created 'BACS (UK fictitious custom)' format in electronic payment method parameters.</span></span> <span data-ttu-id="51db8-281">Asegúrese de que el archivo de pago creado contiene el nodo XML recién introducido por Proseware, Inc. que presenta código de cuenta IBAN de acuerdo con los requisitos regionales.</span><span class="sxs-lookup"><span data-stu-id="51db8-281">Make sure that the created payment file contains recently introduced by Proseware, Inc. XML node presenting IBAN account code in accordance to regional requirements.</span></span> <span data-ttu-id="51db8-282">El archivo también debe contener el nodo XML recientemente introducido por Litware, Inc. que muestra el código bancario SWIFT de acuerdo con los requisitos de país.</span><span class="sxs-lookup"><span data-stu-id="51db8-282">The file also should contain the recently introduced by Litware, Inc. XML node presenting SWIFT bank code in accordance to country requirements.</span></span>  


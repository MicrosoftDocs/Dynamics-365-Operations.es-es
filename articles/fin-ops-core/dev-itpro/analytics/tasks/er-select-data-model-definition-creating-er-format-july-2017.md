---
title: Seleccionar definiciones de modelo de datos al crear formatos
description: 'Para completar los pasos de este procedimiento, primero debe completar los pasos del procedimiento, ER: Creación y activación de un proveedor de configuraciones.'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66b9636f6d9da06f0ea65ab311dd9308ff6ae020
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184724"
---
# <a name="select-data-model-definitions-when-you-create-formats"></a><span data-ttu-id="31ff7-103">Seleccionar definiciones de modelo de datos al crear formatos</span><span class="sxs-lookup"><span data-stu-id="31ff7-103">Select data model definitions when you create formats</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="31ff7-104">Para completar los pasos de este procedimiento, primero debe completar los pasos del procedimiento, ER: Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="31ff7-104">To complete the steps in this procedure, you must first complete the procedure, ER Create a configuration provider and mark it as active.</span></span> 

<span data-ttu-id="31ff7-105">Este procedimiento muestra cómo el elemento raíz de un modelo se puede seleccionar como definición del modelo de datos para insertar una configuración de formato de informe electrónico (ER) que se designa para generar documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="31ff7-105">This procedure shows how a model’s root item can be selected as a data model definition for inserting an Electronic reporting (ER) format configuration that is designed to generate electronic documents.</span></span> <span data-ttu-id="31ff7-106">En este procedimiento, usted agregará una configuración de formato de ER para la empresa de ejemplo Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="31ff7-106">In this procedure, you will add a new ER format configuration for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="31ff7-107">Este procedimiento se ha creado para los usuarios con los roles de Administrador del sistema o Desarrollador de informes electrónicos asignados.</span><span class="sxs-lookup"><span data-stu-id="31ff7-107">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="31ff7-108">Los pasos se pueden completar mediante cualquier conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="31ff7-108">The steps can be completed by using any dataset.</span></span>

1. <span data-ttu-id="31ff7-109">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="31ff7-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="31ff7-110">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como Activo.</span><span class="sxs-lookup"><span data-stu-id="31ff7-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="31ff7-111">Si no ve a este proveedor de configuración, complete los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".</span><span class="sxs-lookup"><span data-stu-id="31ff7-111">If you don’t see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  
2. <span data-ttu-id="31ff7-112">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="31ff7-112">Click Reporting configurations.</span></span>

## <a name="add-a-new-er-data-model-configuration"></a><span data-ttu-id="31ff7-113">Agregue una nueva configuración para los datos de ER</span><span class="sxs-lookup"><span data-stu-id="31ff7-113">Add a new ER data model configuration</span></span>
1. <span data-ttu-id="31ff7-114">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="31ff7-114">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="31ff7-115">Agregamos una nueva configuración del modelo de ER que contiene un modelo de datos que se designa para usarlo como origen de datos para generar informes ER.</span><span class="sxs-lookup"><span data-stu-id="31ff7-115">We add a new ER model configuration containing a data model that is designed to be used as data source for generation ER reports.</span></span>  
2. <span data-ttu-id="31ff7-116">En el campo Nombre, escriba "Modelo de pagos (ficticio)".</span><span class="sxs-lookup"><span data-stu-id="31ff7-116">In the Name field, type 'Payment model (fictitious)'.</span></span>
    * <span data-ttu-id="31ff7-117">Modelo de pago (ficticio)</span><span class="sxs-lookup"><span data-stu-id="31ff7-117">Payment model (fictitious)</span></span>  
3. <span data-ttu-id="31ff7-118">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="31ff7-118">Click Create configuration.</span></span>
4. <span data-ttu-id="31ff7-119">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="31ff7-119">Click Designer.</span></span>
    * <span data-ttu-id="31ff7-120">Abra el diseñador de ER para especificar la estructura del modelo de datos de esta configuración.</span><span class="sxs-lookup"><span data-stu-id="31ff7-120">Open the ER designer to specify the structure of data model of this configuration.</span></span>  
    * <span data-ttu-id="31ff7-121">Supongamos que diseñamos el modelo de datos para que el dominio de pagos de la empresa admita 2 métodos de pago: transferencia de crédito y transferencia bancaria.</span><span class="sxs-lookup"><span data-stu-id="31ff7-121">Assume that we design the data model for payments business domain to support 2 payment methods – credit transfer and direct debit ones.</span></span>  
5. <span data-ttu-id="31ff7-122">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="31ff7-122">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="31ff7-123">En el campo Nombre, escriba "Pagos: transferencia de crédito".</span><span class="sxs-lookup"><span data-stu-id="31ff7-123">In the Name field, type 'Payments – credit transfer'.</span></span>
    * <span data-ttu-id="31ff7-124">Pagos: transferencia de crédito</span><span class="sxs-lookup"><span data-stu-id="31ff7-124">Payments – credit transfer</span></span>  
7. <span data-ttu-id="31ff7-125">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="31ff7-125">Click Add.</span></span>
8. <span data-ttu-id="31ff7-126">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="31ff7-126">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="31ff7-127">En el campo "Nuevo nodo como", escriba "Raíz del modelo".</span><span class="sxs-lookup"><span data-stu-id="31ff7-127">In the New node as a field, enter 'Model root'.</span></span>
10. <span data-ttu-id="31ff7-128">En el campo Nombre, escriba "Pagos: transferencia bancaria".</span><span class="sxs-lookup"><span data-stu-id="31ff7-128">In the Name field, type 'Payments – direct debit'.</span></span>
    * <span data-ttu-id="31ff7-129">Pagos: domiciliación bancaria</span><span class="sxs-lookup"><span data-stu-id="31ff7-129">Payments – direct debit</span></span>  
11. <span data-ttu-id="31ff7-130">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="31ff7-130">Click Add.</span></span>
12. <span data-ttu-id="31ff7-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="31ff7-131">Click Save.</span></span>
13. <span data-ttu-id="31ff7-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="31ff7-132">Close the page.</span></span>
14. <span data-ttu-id="31ff7-133">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="31ff7-133">Click Change status.</span></span>
    * <span data-ttu-id="31ff7-134">Complete la versión de borrador del modelo para que esté disponible en las asignaciones y los formatos del modelo nuevo.</span><span class="sxs-lookup"><span data-stu-id="31ff7-134">Complete the draft version of the model to make it available in new model mappings and formats.</span></span>  
15. <span data-ttu-id="31ff7-135">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="31ff7-135">Click Complete.</span></span>
16. <span data-ttu-id="31ff7-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="31ff7-136">Click OK.</span></span>

## <a name="start-to-enter-a-new-er-format-configuration"></a><span data-ttu-id="31ff7-137">Empezar a especificar una nueva configuración del formato de ER</span><span class="sxs-lookup"><span data-stu-id="31ff7-137">Start to enter a new ER format configuration</span></span>
1. <span data-ttu-id="31ff7-138">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="31ff7-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="31ff7-139">En el campo Nuevo, especifique "Formato basado en el modelo de datos del Modelo de pagos (ficticio)".</span><span class="sxs-lookup"><span data-stu-id="31ff7-139">In the New field, enter 'Format based on data model Payment model (fictitious)'.</span></span>
3. <span data-ttu-id="31ff7-140">En el campo definición del modelo de Datos, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="31ff7-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="31ff7-141">Tenga en cuenta que todos los elementos raíz del modelo de datos seleccionados están actualmente disponibles para su selección como definición del modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="31ff7-141">Note that all root items of the selected data model are currently available for selection as a data model definition.</span></span> <span data-ttu-id="31ff7-142">Puede continuar diseñando el formato mediante cualquiera de los elementos raíz necesarios del modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="31ff7-142">You can continue to design your format by using any of the required root items of the data model.</span></span> <span data-ttu-id="31ff7-143">Si falta una asignación de modelo para el elemento raíz seleccionado no impide que continúe.</span><span class="sxs-lookup"><span data-stu-id="31ff7-143">A missing model mapping for the selected root item doesn't prevent you from continuing.</span></span>  
4. <span data-ttu-id="31ff7-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="31ff7-144">Close the page.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="31ff7-145">Agregar una nueva configuración de asignación al modelo de ER</span><span class="sxs-lookup"><span data-stu-id="31ff7-145">Add a new ER model mapping configuration</span></span>
1. <span data-ttu-id="31ff7-146">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="31ff7-146">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="31ff7-147">En el campo Nuevo, especifique "Asignación de modelo basado en el modelo de datos del Modelo de pagos (ficticio)".</span><span class="sxs-lookup"><span data-stu-id="31ff7-147">In the New field, enter 'Model Mapping based on data model Payment model (fictitious)'.</span></span>
3. <span data-ttu-id="31ff7-148">En el campo Nombre, escriba "Asignaciones de Modelo de pagos (ficticio)".</span><span class="sxs-lookup"><span data-stu-id="31ff7-148">In the Name field, type 'Payment model mappings (fictitious)'.</span></span>
    * <span data-ttu-id="31ff7-149">Asignaciones del modelo de pago (ficticio)</span><span class="sxs-lookup"><span data-stu-id="31ff7-149">Payment model mappings (fictitious)</span></span>  
4. <span data-ttu-id="31ff7-150">En el campo definición del modelo de Datos, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="31ff7-150">In the Data model definition field, enter or select a value.</span></span>
5. <span data-ttu-id="31ff7-151">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="31ff7-151">Click Create configuration.</span></span>

## <a name="design-er-model-mappings"></a><span data-ttu-id="31ff7-152">Diseñar asignaciones de modelo de ER</span><span class="sxs-lookup"><span data-stu-id="31ff7-152">Design ER model mappings</span></span>
1. <span data-ttu-id="31ff7-153">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="31ff7-153">Click Designer.</span></span>
    * <span data-ttu-id="31ff7-154">Use el diseñador de ER para especificar las asignaciones de modelo para los elementos raíz necesarios.</span><span class="sxs-lookup"><span data-stu-id="31ff7-154">Use the ER designer to specify the model mappings for the required root items.</span></span>  
2. <span data-ttu-id="31ff7-155">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="31ff7-155">Click Designer.</span></span>
    * <span data-ttu-id="31ff7-156">Simule el valor de la asignación del modelo seleccionado para el elemento raíz del modelo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="31ff7-156">Simulate setting of selected model mapping for the selected model’s root item.</span></span>  
3. <span data-ttu-id="31ff7-157">En el árbol, seleccione "Dynamics 365 for Operations\Registros de tabla".</span><span class="sxs-lookup"><span data-stu-id="31ff7-157">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
4. <span data-ttu-id="31ff7-158">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="31ff7-158">Click Add root.</span></span>
5. <span data-ttu-id="31ff7-159">En el campo Nombre escriba "Libro mayor".</span><span class="sxs-lookup"><span data-stu-id="31ff7-159">In the Name field, type 'Ledger'.</span></span>
6. <span data-ttu-id="31ff7-160">En el campo Tabla, escriba "LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="31ff7-160">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="31ff7-161">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="31ff7-161">LedgerJournalTrans</span></span>  
7. <span data-ttu-id="31ff7-162">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="31ff7-162">Click OK.</span></span>
8. <span data-ttu-id="31ff7-163">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="31ff7-163">Click Save.</span></span>
9. <span data-ttu-id="31ff7-164">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="31ff7-164">Close the page.</span></span>
10. <span data-ttu-id="31ff7-165">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="31ff7-165">Close the page.</span></span>

## <a name="start-to-enter-another-new-er-format-configuration"></a><span data-ttu-id="31ff7-166">Empezar a especificar otra configuración de formato de ER nueva</span><span class="sxs-lookup"><span data-stu-id="31ff7-166">Start to enter another new ER format configuration</span></span>
1. <span data-ttu-id="31ff7-167">En el árbol, seleccione "Modelo de pagos (ficticio)".</span><span class="sxs-lookup"><span data-stu-id="31ff7-167">In the tree, select 'Payment model (fictitious)'.</span></span>
2. <span data-ttu-id="31ff7-168">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="31ff7-168">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="31ff7-169">En el campo Nuevo, especifique "Formato basado en el modelo de datos del Modelo de pagos (ficticio)".</span><span class="sxs-lookup"><span data-stu-id="31ff7-169">In the New field, enter 'Format based on data model Payment model (fictitious)'.</span></span>
4. <span data-ttu-id="31ff7-170">En el campo definición del modelo de Datos, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="31ff7-170">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="31ff7-171">Tenga en cuenta que solo un elemento raíz está disponible ahora asignar a los orígenes de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="31ff7-171">Note that now only one root item is available to map to the application data sources.</span></span> <span data-ttu-id="31ff7-172">Cuando se introduce al menos una asignación de modelo, solo los artículos raíz del modelo se asignan a los orígenes de datos de la aplicación se pueden seleccionar como definición de modelo cuando se agrega el formato de ER.</span><span class="sxs-lookup"><span data-stu-id="31ff7-172">When at least one model mapping is introduced, only the model’s root items that are mapped to application data sources can be selected as a model definition while the ER format is added.</span></span>   
5. <span data-ttu-id="31ff7-173">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="31ff7-173">Close the page.</span></span>

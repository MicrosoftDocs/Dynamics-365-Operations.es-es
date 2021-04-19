---
title: CE Diseñar el modelo de datos específico de dominio
description: Este tema describe cómo crear una nueva configuración de informes electrónicos (ER) que contiene un modelo de datos para documentos de pago electrónicos.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 351c5a6624f7ee912c507a9f74324f4c8f61166b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755043"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="78835-103">CE Diseñar el modelo de datos específico de dominio</span><span class="sxs-lookup"><span data-stu-id="78835-103">ER Design domain specific data model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="78835-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga un modelo de datos para los documentos de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="78835-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="78835-105">Este modelo de datos se usará posteriormente como origen de datos al crear el formato de los documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="78835-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="78835-106">En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que las configuraciones de ER se comparten entre las empresas.</span><span class="sxs-lookup"><span data-stu-id="78835-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="78835-107">Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="78835-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

1. <span data-ttu-id="78835-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="78835-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="78835-109">Seleccione el proveedor de configuración de la empresa de ejemplo, "Litware, Inc".</span><span class="sxs-lookup"><span data-stu-id="78835-109">Select the configuration provider for sample company, 'Litware, Inc.'</span></span> <span data-ttu-id="78835-110">Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".</span><span class="sxs-lookup"><span data-stu-id="78835-110">If you don't see this configuration provider, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>  
    
2. <span data-ttu-id="78835-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="78835-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="78835-112">Creará una configuración que contenga un modelo de datos para los documentos de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="78835-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="78835-113">Este modelo de datos se usará posteriormente como origen de datos cuando cree el formato para los documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="78835-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="78835-114">Creación de un nuevo modelo de configuración de datos</span><span class="sxs-lookup"><span data-stu-id="78835-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="78835-115">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="78835-116">En el campo Nombre, escriba Pagos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="78835-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="78835-117">En el campo Descripción, escriba Configuración del modelo de pago.</span><span class="sxs-lookup"><span data-stu-id="78835-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="78835-118">El proveedor de configuraciones activo se especifica automáticamente aquí.</span><span class="sxs-lookup"><span data-stu-id="78835-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="78835-119">Este proveedor podrá mantener esta configuración.</span><span class="sxs-lookup"><span data-stu-id="78835-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="78835-120">Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.</span><span class="sxs-lookup"><span data-stu-id="78835-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="78835-121">Haga clic en el botón "Crear configuración" para completar la tarea de creación de la configuración</span><span class="sxs-lookup"><span data-stu-id="78835-121">Click 'Create configuration' button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="78835-122">Creación de un modelo de datos</span><span class="sxs-lookup"><span data-stu-id="78835-122">Create a data model</span></span>
<span data-ttu-id="78835-123">Usted está creando un nuevo modelo de datos para la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="78835-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="78835-124">Esta versión de la configuración tendrá un estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="78835-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="78835-125">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="78835-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="78835-126">Definición de la estructura de una parte que participa en un proceso de pago</span><span class="sxs-lookup"><span data-stu-id="78835-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="78835-127">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="78835-128">Escriba "Parte" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="78835-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="78835-129">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-129">Click Add.</span></span>
4. <span data-ttu-id="78835-130">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="78835-131">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="78835-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="78835-132">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="78835-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="78835-133">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-133">Click Add.</span></span>
8. <span data-ttu-id="78835-134">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="78835-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="78835-135">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="78835-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="78835-136">Definición de la estructura bancaria para este modelo</span><span class="sxs-lookup"><span data-stu-id="78835-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="78835-137">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="78835-138">En el campo Nombre, escriba "Agente".</span><span class="sxs-lookup"><span data-stu-id="78835-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="78835-139">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="78835-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="78835-140">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-140">Click Add.</span></span>
5. <span data-ttu-id="78835-141">En el campo Descripción, escriba "Entidad financiera (por ejemplo, un banco) que proporciona una cuenta a una de las partes (deudor/acreedeor).</span><span class="sxs-lookup"><span data-stu-id="78835-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="78835-142">Entidad financiera (por ejemplo, un banco) que proporciona una cuenta a una de las partes (deudor/acreedor).</span><span class="sxs-lookup"><span data-stu-id="78835-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="78835-143">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="78835-144">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="78835-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="78835-145">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="78835-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="78835-146">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-146">Click Add.</span></span>
10. <span data-ttu-id="78835-147">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="78835-148">En el campo Nombre, escriba "SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="78835-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="78835-149">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-149">Click Add.</span></span>
13. <span data-ttu-id="78835-150">En el campo Descripción, escriba un "código de identificación del Banco".</span><span class="sxs-lookup"><span data-stu-id="78835-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="78835-151">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="78835-152">En el campo Nombre, especifique "RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="78835-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="78835-153">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-153">Click Add.</span></span>
17. <span data-ttu-id="78835-154">En el campo Descripción, especifique un "Número de ruta".</span><span class="sxs-lookup"><span data-stu-id="78835-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="78835-155">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="78835-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="78835-156">Definición de la cuenta bancaria para este modelo</span><span class="sxs-lookup"><span data-stu-id="78835-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="78835-157">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="78835-158">En el campo Nombre, escriba "Cuenta".</span><span class="sxs-lookup"><span data-stu-id="78835-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="78835-159">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="78835-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="78835-160">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-160">Click Add.</span></span>
5. <span data-ttu-id="78835-161">En el campo Descripción, escriba "Identificación de una cuenta de una parte en una entidad financiera (por ejemplo, un banco)".</span><span class="sxs-lookup"><span data-stu-id="78835-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="78835-162">Identificación de una cuenta de una parte en una entidad financiera (por ejemplo, un banco).</span><span class="sxs-lookup"><span data-stu-id="78835-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="78835-163">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="78835-164">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="78835-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="78835-165">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="78835-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="78835-166">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-166">Click Add.</span></span>
10. <span data-ttu-id="78835-167">En el campo Descripción, especifique un "Código de moneda".</span><span class="sxs-lookup"><span data-stu-id="78835-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="78835-168">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="78835-169">En el campo Nombre, escriba "Número".</span><span class="sxs-lookup"><span data-stu-id="78835-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="78835-170">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-170">Click Add.</span></span>
14. <span data-ttu-id="78835-171">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="78835-172">En el campo Nombre, escriba "IBAN".</span><span class="sxs-lookup"><span data-stu-id="78835-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="78835-173">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-173">Click Add.</span></span>
17. <span data-ttu-id="78835-174">En el campo descripción, escriba "Número de cuenta bancaria internacional".</span><span class="sxs-lookup"><span data-stu-id="78835-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="78835-175">Definición de la estructura del mensaje de pago para el tipo de pago de transferencia de crédito.</span><span class="sxs-lookup"><span data-stu-id="78835-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="78835-176">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="78835-177">En el campo "Nuevo nodo como", escriba "Raíz del modelo".</span><span class="sxs-lookup"><span data-stu-id="78835-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="78835-178">En el campo Nombre, escriba "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="78835-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="78835-179">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-179">Click Add.</span></span>
5. <span data-ttu-id="78835-180">En el campo Buscar, escriba "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="78835-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="78835-181">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="78835-181">Click Find previous.</span></span>
7. <span data-ttu-id="78835-182">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="78835-183">En el campo Nombre, escriba "MessageIdentification".</span><span class="sxs-lookup"><span data-stu-id="78835-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="78835-184">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-184">Click Add.</span></span>
10. <span data-ttu-id="78835-185">En el campo Descripción, escriba "La referencia punto a punto asignada por la parte ordenante (y enviada a la siguiente parte) para identificar un mensaje".</span><span class="sxs-lookup"><span data-stu-id="78835-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="78835-186">La referencia punto a punto asignada por la parte ordenante (y que se envía a la siguiente parte) para identificar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="78835-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="78835-187">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="78835-188">En el campo Nombre, escriba "ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="78835-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="78835-189">En el campo Tipo de artículo, seleccione DateTime.</span><span class="sxs-lookup"><span data-stu-id="78835-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="78835-190">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-190">Click Add.</span></span>
15. <span data-ttu-id="78835-191">En el campo Descripción, escriba "Fecha y hora de creación del mensaje de pago".</span><span class="sxs-lookup"><span data-stu-id="78835-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="78835-192">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="78835-193">Definición de la estructura de transacción de pago para este modelo.</span><span class="sxs-lookup"><span data-stu-id="78835-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="78835-194">En el campo Nombre, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="78835-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="78835-195">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="78835-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="78835-196">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-196">Click Add.</span></span>
20. <span data-ttu-id="78835-197">En el campo Descripción, especifique Líneas de pago del mensaje actual.</span><span class="sxs-lookup"><span data-stu-id="78835-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="78835-198">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="78835-199">En el campo Nombre, escriba "Acreedor".</span><span class="sxs-lookup"><span data-stu-id="78835-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="78835-200">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="78835-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="78835-201">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-201">Click Add.</span></span>
25. <span data-ttu-id="78835-202">En el campo Descripción, escriba "Parte a la que se debe una suma de dinero".</span><span class="sxs-lookup"><span data-stu-id="78835-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="78835-203">Haga clic en Cambiar referencia del artículo.</span><span class="sxs-lookup"><span data-stu-id="78835-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="78835-204">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="78835-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="78835-205">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="78835-205">Click Find next.</span></span>
29. <span data-ttu-id="78835-206">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="78835-206">Click OK.</span></span>
30. <span data-ttu-id="78835-207">En el campo Buscar, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="78835-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="78835-208">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="78835-208">Click Find next.</span></span>
32. <span data-ttu-id="78835-209">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="78835-210">En el campo Nombre, escriba "Deudor".</span><span class="sxs-lookup"><span data-stu-id="78835-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="78835-211">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-211">Click Add.</span></span>
35. <span data-ttu-id="78835-212">En el campo Descripción, escriba "Parte que adeuda una suma de dinero al (último) acreedor".</span><span class="sxs-lookup"><span data-stu-id="78835-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="78835-213">Haga clic en Cambiar referencia del artículo.</span><span class="sxs-lookup"><span data-stu-id="78835-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="78835-214">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="78835-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="78835-215">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="78835-215">Click Find next.</span></span>
39. <span data-ttu-id="78835-216">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="78835-216">Click OK.</span></span>
40. <span data-ttu-id="78835-217">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="78835-217">Click Find next.</span></span>
41. <span data-ttu-id="78835-218">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="78835-219">En el campo Nombre, escriba "Descripción".</span><span class="sxs-lookup"><span data-stu-id="78835-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="78835-220">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="78835-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="78835-221">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-221">Click Add.</span></span>
45. <span data-ttu-id="78835-222">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="78835-223">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="78835-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="78835-224">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-224">Click Add.</span></span>
48. <span data-ttu-id="78835-225">En el campo Descripción, especifique un "Código de moneda".</span><span class="sxs-lookup"><span data-stu-id="78835-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="78835-226">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="78835-227">En el campo Nombre, escriba "TransactionDate".</span><span class="sxs-lookup"><span data-stu-id="78835-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="78835-228">En el campo Tipo de artículo, seleccione Fecha.</span><span class="sxs-lookup"><span data-stu-id="78835-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="78835-229">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-229">Click Add.</span></span>
53. <span data-ttu-id="78835-230">En el campo Descripción, escriba una "Fecha de transacción".</span><span class="sxs-lookup"><span data-stu-id="78835-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="78835-231">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="78835-232">En el campo Nombre, escriba "InstructedAmount".</span><span class="sxs-lookup"><span data-stu-id="78835-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="78835-233">En el campo Tipo de artículo, seleccione Real.</span><span class="sxs-lookup"><span data-stu-id="78835-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="78835-234">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-234">Click Add.</span></span>
58. <span data-ttu-id="78835-235">En el campo Descripción, escriba "La suma de dinero que se transferirá entre el deudor y el acreedor, antes de la deducción de cargos".</span><span class="sxs-lookup"><span data-stu-id="78835-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="78835-236">El importe se debe expresar en la divisa solicitada por la parte iniciadora."</span><span class="sxs-lookup"><span data-stu-id="78835-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="78835-237">La suma de dinero que se transferirá entre el deudor y el acreedor, antes de la deducción de cargos.</span><span class="sxs-lookup"><span data-stu-id="78835-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="78835-238">El importe se debe expresar en la divisa solicitada por la parte iniciadora.</span><span class="sxs-lookup"><span data-stu-id="78835-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="78835-239">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78835-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="78835-240">En el campo Nombre, escriba "End2EndID".</span><span class="sxs-lookup"><span data-stu-id="78835-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="78835-241">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="78835-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="78835-242">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78835-242">Click Add.</span></span>
63. <span data-ttu-id="78835-243">En el campo Descripción, escriba "La identificación única asignada por la parte iniciadora".</span><span class="sxs-lookup"><span data-stu-id="78835-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="78835-244">Esta identificación se pasa, sin cambios, por la cadena completa, de extremo a extremo".</span><span class="sxs-lookup"><span data-stu-id="78835-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="78835-245">En el campo Nombre, especifique "PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="78835-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="78835-246">El nombre del modelo de pago se alinea con las interfaces predefinidas de los formularios de pago.</span><span class="sxs-lookup"><span data-stu-id="78835-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="78835-247">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="78835-247">Click Save.</span></span>
66. <span data-ttu-id="78835-248">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78835-248">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
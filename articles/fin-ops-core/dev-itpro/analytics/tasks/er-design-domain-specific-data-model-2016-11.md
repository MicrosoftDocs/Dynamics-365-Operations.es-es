---
title: CE Diseñar el modelo de datos específico de dominio
description: En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga un modelo de datos para los documentos de pago electrónico.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d66cc69da08478ceb931fab594da51bafcacc38
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185092"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="c6d1a-103">CE Diseñar el modelo de datos específico de dominio</span><span class="sxs-lookup"><span data-stu-id="c6d1a-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c6d1a-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga un modelo de datos para los documentos de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="c6d1a-105">Este modelo de datos se usará posteriormente como origen de datos al crear el formato de los documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="c6d1a-106">En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que las configuraciones de ER se comparten entre las empresas.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="c6d1a-107">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="c6d1a-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="c6d1a-109">Seleccione el proveedor de configuración de la empresa de ejemplo, "Litware, Inc".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="c6d1a-110">Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="c6d1a-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="c6d1a-112">Creará una configuración que contenga un modelo de datos para los documentos de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="c6d1a-113">Este modelo de datos se usará posteriormente como origen de datos cuando cree el formato para los documentos de pago.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="c6d1a-114">Creación de un nuevo modelo de configuración de datos</span><span class="sxs-lookup"><span data-stu-id="c6d1a-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="c6d1a-115">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="c6d1a-116">En el campo Nombre, escriba Pagos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="c6d1a-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="c6d1a-117">Pagos (modelo simplificado)</span><span class="sxs-lookup"><span data-stu-id="c6d1a-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="c6d1a-118">En el campo Descripción, escriba Configuración del modelo de pago.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="c6d1a-119">Configuración del modelo de pago</span><span class="sxs-lookup"><span data-stu-id="c6d1a-119">Payment model configuration</span></span>  
    * <span data-ttu-id="c6d1a-120">El proveedor de configuraciones activo se especifica automáticamente aquí.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="c6d1a-121">Este proveedor podrá mantener esta configuración.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="c6d1a-122">Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="c6d1a-123">Haga clic en el botón Crear configuración para completar la tarea de creación de la configuración.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="c6d1a-124">Creación de un modelo de datos</span><span class="sxs-lookup"><span data-stu-id="c6d1a-124">Create a data model</span></span>
    * <span data-ttu-id="c6d1a-125">Usted está creando un nuevo modelo de datos para la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="c6d1a-126">Esta versión de la configuración tendrá un estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="c6d1a-127">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="c6d1a-128">Definición de la estructura de una parte que participa en un proceso de pago</span><span class="sxs-lookup"><span data-stu-id="c6d1a-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="c6d1a-129">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="c6d1a-130">Escriba "Parte" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="c6d1a-131">Parte</span><span class="sxs-lookup"><span data-stu-id="c6d1a-131">Party</span></span>  
3. <span data-ttu-id="c6d1a-132">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-132">Click Add.</span></span>
4. <span data-ttu-id="c6d1a-133">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="c6d1a-134">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="c6d1a-135">Nombre</span><span class="sxs-lookup"><span data-stu-id="c6d1a-135">Name</span></span>  
6. <span data-ttu-id="c6d1a-136">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="c6d1a-137">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-137">Click Add.</span></span>
8. <span data-ttu-id="c6d1a-138">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="c6d1a-139">Parte</span><span class="sxs-lookup"><span data-stu-id="c6d1a-139">Party</span></span>  
9. <span data-ttu-id="c6d1a-140">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="c6d1a-141">Definición de la estructura bancaria para este modelo</span><span class="sxs-lookup"><span data-stu-id="c6d1a-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="c6d1a-142">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="c6d1a-143">En el campo Nombre, escriba "Agente".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="c6d1a-144">Agente</span><span class="sxs-lookup"><span data-stu-id="c6d1a-144">Agent</span></span>  
3. <span data-ttu-id="c6d1a-145">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="c6d1a-146">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-146">Click Add.</span></span>
5. <span data-ttu-id="c6d1a-147">En el campo Descripción, escriba "Entidad financiera (por ejemplo, un banco) que proporciona una cuenta a una de las partes (deudor/acreedeor).</span><span class="sxs-lookup"><span data-stu-id="c6d1a-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="c6d1a-148">Entidad financiera (por ejemplo, un banco) que proporciona una cuenta a una de las partes (deudor/acreedor).</span><span class="sxs-lookup"><span data-stu-id="c6d1a-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="c6d1a-149">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="c6d1a-150">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="c6d1a-151">Nombre</span><span class="sxs-lookup"><span data-stu-id="c6d1a-151">Name</span></span>  
8. <span data-ttu-id="c6d1a-152">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="c6d1a-153">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-153">Click Add.</span></span>
10. <span data-ttu-id="c6d1a-154">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="c6d1a-155">En el campo Nombre, escriba "SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="c6d1a-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="c6d1a-156">SWIFT</span></span>  
12. <span data-ttu-id="c6d1a-157">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-157">Click Add.</span></span>
13. <span data-ttu-id="c6d1a-158">En el campo Descripción, escriba un "código de identificación del Banco".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="c6d1a-159">Código de identificación del banco</span><span class="sxs-lookup"><span data-stu-id="c6d1a-159">Bank identification code</span></span>  
14. <span data-ttu-id="c6d1a-160">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="c6d1a-161">En el campo Nombre, especifique "RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="c6d1a-162">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="c6d1a-162">RoutingNumber</span></span>  
16. <span data-ttu-id="c6d1a-163">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-163">Click Add.</span></span>
17. <span data-ttu-id="c6d1a-164">En el campo Descripción, especifique un "Número de ruta".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="c6d1a-165">Número de ruta</span><span class="sxs-lookup"><span data-stu-id="c6d1a-165">Routing number</span></span>  
18. <span data-ttu-id="c6d1a-166">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="c6d1a-167">Definición de la cuenta bancaria para este modelo</span><span class="sxs-lookup"><span data-stu-id="c6d1a-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="c6d1a-168">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="c6d1a-169">En el campo Nombre, escriba "Cuenta".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="c6d1a-170">Cuenta</span><span class="sxs-lookup"><span data-stu-id="c6d1a-170">Account</span></span>  
3. <span data-ttu-id="c6d1a-171">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="c6d1a-172">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-172">Click Add.</span></span>
5. <span data-ttu-id="c6d1a-173">En el campo Descripción, escriba "Identificación de una cuenta de una parte en una entidad financiera (por ejemplo, un banco)".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="c6d1a-174">Identificación de una cuenta de una parte en una entidad financiera (por ejemplo, un banco).</span><span class="sxs-lookup"><span data-stu-id="c6d1a-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="c6d1a-175">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="c6d1a-176">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="c6d1a-177">Divisa</span><span class="sxs-lookup"><span data-stu-id="c6d1a-177">Currency</span></span>  
8. <span data-ttu-id="c6d1a-178">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="c6d1a-179">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-179">Click Add.</span></span>
10. <span data-ttu-id="c6d1a-180">En el campo Descripción, especifique un "Código de moneda".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="c6d1a-181">Código de divisa</span><span class="sxs-lookup"><span data-stu-id="c6d1a-181">Currency code</span></span>  
11. <span data-ttu-id="c6d1a-182">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="c6d1a-183">En el campo Nombre, escriba "Número".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="c6d1a-184">Número</span><span class="sxs-lookup"><span data-stu-id="c6d1a-184">Number</span></span>  
13. <span data-ttu-id="c6d1a-185">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-185">Click Add.</span></span>
14. <span data-ttu-id="c6d1a-186">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="c6d1a-187">En el campo Nombre, escriba "IBAN".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="c6d1a-188">IBAN</span><span class="sxs-lookup"><span data-stu-id="c6d1a-188">IBAN</span></span>  
16. <span data-ttu-id="c6d1a-189">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-189">Click Add.</span></span>
17. <span data-ttu-id="c6d1a-190">En el campo descripción, escriba "Número de cuenta bancaria internacional".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="c6d1a-191">Número internacional de cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="c6d1a-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="c6d1a-192">Definición de la estructura del mensaje de pago para el tipo de pago de transferencia de crédito.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="c6d1a-193">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="c6d1a-194">En el campo "Nuevo nodo como", escriba "Raíz del modelo".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="c6d1a-195">En el campo Nombre, escriba "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="c6d1a-196">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="c6d1a-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="c6d1a-197">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-197">Click Add.</span></span>
5. <span data-ttu-id="c6d1a-198">En el campo Buscar, escriba "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="c6d1a-199">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="c6d1a-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="c6d1a-200">Haga clic en Buscar anterior.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-200">Click Find previous.</span></span>
7. <span data-ttu-id="c6d1a-201">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="c6d1a-202">En el campo Nombre, escriba "MessageIdentification".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="c6d1a-203">MessageIdentification</span><span class="sxs-lookup"><span data-stu-id="c6d1a-203">MessageIdentification</span></span>  
9. <span data-ttu-id="c6d1a-204">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-204">Click Add.</span></span>
10. <span data-ttu-id="c6d1a-205">En el campo Descripción, escriba "La referencia punto a punto asignada por la parte ordenante (y enviada a la siguiente parte) para identificar un mensaje".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="c6d1a-206">La referencia punto a punto asignada por la parte ordenante (y que se envía a la siguiente parte) para identificar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="c6d1a-207">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="c6d1a-208">En el campo Nombre, escriba "ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="c6d1a-209">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="c6d1a-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="c6d1a-210">En el campo Tipo de artículo, seleccione DateTime.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="c6d1a-211">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-211">Click Add.</span></span>
15. <span data-ttu-id="c6d1a-212">En el campo Descripción, escriba "Fecha y hora de creación del mensaje de pago".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="c6d1a-213">Fecha y hora de creación del mensaje de pago.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="c6d1a-214">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="c6d1a-215">Definición de la estructura de transacción de pago para este modelo.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="c6d1a-216">En el campo Nombre, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="c6d1a-217">Pagos</span><span class="sxs-lookup"><span data-stu-id="c6d1a-217">Payments</span></span>  
18. <span data-ttu-id="c6d1a-218">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="c6d1a-219">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-219">Click Add.</span></span>
20. <span data-ttu-id="c6d1a-220">En el campo Descripción, especifique Líneas de pago del mensaje actual.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="c6d1a-221">Líneas de pago del mensaje actual</span><span class="sxs-lookup"><span data-stu-id="c6d1a-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="c6d1a-222">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="c6d1a-223">En el campo Nombre, escriba "Acreedor".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="c6d1a-224">Acreedor</span><span class="sxs-lookup"><span data-stu-id="c6d1a-224">Creditor</span></span>  
23. <span data-ttu-id="c6d1a-225">En el campo Tipo de artículo, seleccione Registro.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="c6d1a-226">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-226">Click Add.</span></span>
25. <span data-ttu-id="c6d1a-227">En el campo Descripción, escriba "Parte a la que se debe una suma de dinero".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="c6d1a-228">Parte a la que se debe una suma de dinero.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="c6d1a-229">Haga clic en Cambiar referencia del artículo.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="c6d1a-230">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="c6d1a-231">Parte</span><span class="sxs-lookup"><span data-stu-id="c6d1a-231">Party</span></span>  
28. <span data-ttu-id="c6d1a-232">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-232">Click Find next.</span></span>
29. <span data-ttu-id="c6d1a-233">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c6d1a-233">Click OK.</span></span>
30. <span data-ttu-id="c6d1a-234">En el campo Buscar, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="c6d1a-235">Pagos</span><span class="sxs-lookup"><span data-stu-id="c6d1a-235">Payments</span></span>  
31. <span data-ttu-id="c6d1a-236">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-236">Click Find next.</span></span>
32. <span data-ttu-id="c6d1a-237">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="c6d1a-238">En el campo Nombre, escriba "Deudor".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="c6d1a-239">Deudor</span><span class="sxs-lookup"><span data-stu-id="c6d1a-239">Debtor</span></span>  
34. <span data-ttu-id="c6d1a-240">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-240">Click Add.</span></span>
35. <span data-ttu-id="c6d1a-241">En el campo Descripción, escriba "Parte que adeuda una suma de dinero al (último) acreedor".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="c6d1a-242">Parte que adeuda una suma de dinero al (último) acreedor.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="c6d1a-243">Haga clic en Cambiar referencia del artículo.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="c6d1a-244">Escriba "Parte" en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="c6d1a-245">Parte</span><span class="sxs-lookup"><span data-stu-id="c6d1a-245">Party</span></span>  
38. <span data-ttu-id="c6d1a-246">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-246">Click Find next.</span></span>
39. <span data-ttu-id="c6d1a-247">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c6d1a-247">Click OK.</span></span>
40. <span data-ttu-id="c6d1a-248">Haga clic en Buscar siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-248">Click Find next.</span></span>
41. <span data-ttu-id="c6d1a-249">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="c6d1a-250">En el campo Nombre, escriba "Descripción".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="c6d1a-251">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6d1a-251">Description</span></span>  
43. <span data-ttu-id="c6d1a-252">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="c6d1a-253">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-253">Click Add.</span></span>
45. <span data-ttu-id="c6d1a-254">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="c6d1a-255">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="c6d1a-256">Divisa</span><span class="sxs-lookup"><span data-stu-id="c6d1a-256">Currency</span></span>  
47. <span data-ttu-id="c6d1a-257">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-257">Click Add.</span></span>
48. <span data-ttu-id="c6d1a-258">En el campo Descripción, especifique un "Código de moneda".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="c6d1a-259">Código de divisa</span><span class="sxs-lookup"><span data-stu-id="c6d1a-259">Currency code</span></span>  
49. <span data-ttu-id="c6d1a-260">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="c6d1a-261">En el campo Nombre, escriba "TransactionDate".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="c6d1a-262">TransactionDate</span><span class="sxs-lookup"><span data-stu-id="c6d1a-262">TransactionDate</span></span>  
51. <span data-ttu-id="c6d1a-263">En el campo Tipo de artículo, seleccione Fecha.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="c6d1a-264">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-264">Click Add.</span></span>
53. <span data-ttu-id="c6d1a-265">En el campo Descripción, escriba una "Fecha de transacción".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="c6d1a-266">Fecha de la transacción</span><span class="sxs-lookup"><span data-stu-id="c6d1a-266">Transaction date</span></span>  
54. <span data-ttu-id="c6d1a-267">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="c6d1a-268">En el campo Nombre, escriba "InstructedAmount".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="c6d1a-269">InstructedAmount</span><span class="sxs-lookup"><span data-stu-id="c6d1a-269">InstructedAmount</span></span>  
56. <span data-ttu-id="c6d1a-270">En el campo Tipo de artículo, seleccione Real.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="c6d1a-271">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-271">Click Add.</span></span>
58. <span data-ttu-id="c6d1a-272">En el campo Descripción, escriba "La suma de dinero que se transferirá entre el deudor y el acreedor, antes de la deducción de cargos".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="c6d1a-273">El importe se debe expresar en la divisa solicitada por la parte iniciadora."</span><span class="sxs-lookup"><span data-stu-id="c6d1a-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="c6d1a-274">La suma de dinero que se transferirá entre el deudor y el acreedor, antes de la deducción de cargos.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="c6d1a-275">El importe se debe expresar en la divisa solicitada por la parte iniciadora.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="c6d1a-276">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="c6d1a-277">En el campo Nombre, escriba "End2EndID".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="c6d1a-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="c6d1a-278">End2EndID</span></span>  
61. <span data-ttu-id="c6d1a-279">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="c6d1a-280">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-280">Click Add.</span></span>
63. <span data-ttu-id="c6d1a-281">En el campo Descripción, escriba "La identificación única asignada por la parte iniciadora".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="c6d1a-282">Esta identificación se pasa, sin cambios, por la cadena completa, de extremo a extremo".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="c6d1a-283">La identificación única asignada por la parte iniciadora.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="c6d1a-284">Esta identificación se pasa, sin cambios, por la cadena completa, de extremo a extremo.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="c6d1a-285">En el campo Nombre, especifique "PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="c6d1a-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="c6d1a-286">El nombre del modelo de pago se alinea con las interfaces predefinidas de los formularios de pago.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="c6d1a-287">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-287">Click Save.</span></span>
66. <span data-ttu-id="c6d1a-288">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c6d1a-288">Close the page.</span></span>


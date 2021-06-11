---
title: Configurar códigos de motivos
description: Dynamics 365 Human Resources usa códigos de motivo para explicar por qué los beneficios de un empleado están cambiando.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6fc641233a1bd217de5b9eb6e06560b989f91c7b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056357"
---
# <a name="set-up-reason-codes"></a><span data-ttu-id="7e113-103">Configurar códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="7e113-103">Set up reason codes</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7e113-104">Dynamics 365 Human Resources usa códigos de motivo para explicar por qué los beneficios de un empleado están cambiando.</span><span class="sxs-lookup"><span data-stu-id="7e113-104">Dynamics 365 Human Resources uses reason codes to explain why an employee’s benefits are changing.</span></span>

> [!NOTE]
> <span data-ttu-id="7e113-105">A partir de enero de 2021, los códigos de motivo se migrarán al espacio de trabajo **Administración de personal** en lugar de al espacio de trabajo **Administración de prestaciones**.</span><span class="sxs-lookup"><span data-stu-id="7e113-105">As of January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="7e113-106">Para obtener más información, consulte [Migrar manualmente los códigos de motivo a la Administración de personal](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span><span class="sxs-lookup"><span data-stu-id="7e113-106">For more information, see [Manually migrate reason codes to Personnel management](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span></span>

## <a name="create-reason-codes"></a><span data-ttu-id="7e113-107">Crear códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="7e113-107">Create reason codes</span></span>

1. <span data-ttu-id="7e113-108">En el espacio de trabajo **Administración de personal** (o el espacio de trabajo **Administración de prestaciones** si aún no se han migrado los códigos de motivo), seleccione **Vínculos** y, a continuación, seleccione **Códigos de motivo**.</span><span class="sxs-lookup"><span data-stu-id="7e113-108">In the **Personnel management** workspace (or **Benefits management** workspace if your reason codes haven't yet migrated), select **Links**, and then select **Reason codes**.</span></span>

2. <span data-ttu-id="7e113-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7e113-109">Select **New**.</span></span>

3. <span data-ttu-id="7e113-110">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="7e113-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="7e113-111">Campo</span><span class="sxs-lookup"><span data-stu-id="7e113-111">Field</span></span> | <span data-ttu-id="7e113-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e113-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="7e113-113">**Código de motivo**</span><span class="sxs-lookup"><span data-stu-id="7e113-113">**Reason code**</span></span> | <span data-ttu-id="7e113-114">Un nombre único para identificar la razón por la cual un empleado cambiaría una inscripción al plan de beneficios.</span><span class="sxs-lookup"><span data-stu-id="7e113-114">A unique name to identify the reason an employee would change a benefit plan enrollment.</span></span> |
   | <span data-ttu-id="7e113-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7e113-115">**Description**</span></span> | <span data-ttu-id="7e113-116">Una descripción del código de motivo.</span><span class="sxs-lookup"><span data-stu-id="7e113-116">A description of the reason code.</span></span> |

4. <span data-ttu-id="7e113-117">En **Escenarios aplicables**, establezca **Administración de prestaciones** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7e113-117">Under **Applicable scenarios**, set **Benefits management** to **Yes**.</span></span> <span data-ttu-id="7e113-118">(No es aplicable si los códigos de motivo aún no se han migrado al espacio de trabajo **Administración de personal**).</span><span class="sxs-lookup"><span data-stu-id="7e113-118">(Not applicable if your reason codes haven't yet migrated to the **Personnel management** workspace.)</span></span>

5. <span data-ttu-id="7e113-119">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7e113-119">Select **Save**.</span></span>

## <a name="manually-migrate-reason-codes-to-personnel-management"></a><span data-ttu-id="7e113-120">Migrar manualmente los códigos de motivo a la Administración de personal</span><span class="sxs-lookup"><span data-stu-id="7e113-120">Manually migrate reason codes to Personnel management</span></span>

<span data-ttu-id="7e113-121">En enero de 2021, los códigos de motivo se migrarán al espacio de trabajo **Administración de personal** en lugar de al espacio de trabajo **Administración de prestaciones**.</span><span class="sxs-lookup"><span data-stu-id="7e113-121">In January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="7e113-122">La mayoría de los datos de códigos de motivo se migrarán automáticamente en su entorno.</span><span class="sxs-lookup"><span data-stu-id="7e113-122">Most reason code data will automatically migrate in your environment.</span></span> <span data-ttu-id="7e113-123">Es posible que algunos datos de códigos de motivo no se migren.</span><span class="sxs-lookup"><span data-stu-id="7e113-123">Some reason code data might not migrate.</span></span> <span data-ttu-id="7e113-124">Por ejemplo, ahora los códigos de motivo tienen 15 caracteres como máximo, por lo que cualquier código de motivo de más de 15 caracteres no se migrará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7e113-124">For example, reason codes now have a 15-character maximum, so any reason codes longer than 15 characters won't migrate automatically.</span></span>

<span data-ttu-id="7e113-125">Verá un banner en la página **Vínculos** del espacio de trabajo **Administración de prestaciones** que le informará de la migración y de si no se han migrado algunos códigos de motivo.</span><span class="sxs-lookup"><span data-stu-id="7e113-125">You'll see a banner on the **Links** page of the **Benefits management** workspace informing you about the migration and whether any reason codes didn't migrate.</span></span>

1. <span data-ttu-id="7e113-126">Seleccione **Códigos de motivo** para obtener detalles sobre el estado de la migración.</span><span class="sxs-lookup"><span data-stu-id="7e113-126">Select **Reason codes** for details about migration status.</span></span>

   <span data-ttu-id="7e113-127">[![Códigos de motivos](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span><span class="sxs-lookup"><span data-stu-id="7e113-127">[![Reason codes](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span></span>

2. <span data-ttu-id="7e113-128">Seleccione un código de motivo que no haya podido migrar.</span><span class="sxs-lookup"><span data-stu-id="7e113-128">Select a reason code that failed to migrate.</span></span>

   <span data-ttu-id="7e113-129">[![Estado de la migración de los códigos de motivo](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span><span class="sxs-lookup"><span data-stu-id="7e113-129">[![Reason code migration status](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span></span>

3. <span data-ttu-id="7e113-130">Seleccione **Migrar código de motivo**.</span><span class="sxs-lookup"><span data-stu-id="7e113-130">Select **Migrate reason code**.</span></span>

   <span data-ttu-id="7e113-131">[![Migrar código de motivo](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span><span class="sxs-lookup"><span data-stu-id="7e113-131">[![Migrate reason code](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span></span>

4. <span data-ttu-id="7e113-132">En el panel **Migración de código de motivo de prestación** tiene dos opciones para asignar a un código de motivo de Administración de personal:</span><span class="sxs-lookup"><span data-stu-id="7e113-132">In the **Benefit reason code migration** pane, you have two options for mapping to a Personnel management reason code:</span></span>

   - <span data-ttu-id="7e113-133">Para utilizar un código de motivo existente en Administración de personal, elija uno de los cuadros desplegables **Usar código de motivo existente**.</span><span class="sxs-lookup"><span data-stu-id="7e113-133">To use an existing reason code in Personnel management, choose one from the **Use existing reason code** dropdown.</span></span>
     > [!NOTE]
     > <span data-ttu-id="7e113-134">Solo puede utilizar un código de motivo existente en Administración de personal si aún no se ha migrado otro código de motivo de Administración de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="7e113-134">You can only use an existing reason code in Personnel management if another Benefits management reason code hasn't already migrated to it.</span></span>
   - <span data-ttu-id="7e113-135">Para crear un nuevo código de motivo en Administración de personal, introduzca uno nuevo en **Nuevo código de motivo** y, a continuación, escriba una descripción en **Nueva descripción**.</span><span class="sxs-lookup"><span data-stu-id="7e113-135">To create a new reason code in Personnel management, enter a new one in **New reason code**, and then enter a description in **New description**.</span></span>

   <span data-ttu-id="7e113-136">[![Asignar a un código de motivo de Administración de personal](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span><span class="sxs-lookup"><span data-stu-id="7e113-136">[![Map to a Personnel management reason code](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span></span>

<span data-ttu-id="7e113-137">Una vez que se hayan migrado los códigos de motivo a Administración de personal, la opción de usarlos en Administración de prestaciones se establece automáticamente en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7e113-137">After reason codes migrate to Personnel management, the option for using them in Benefits management is automatically set to **Yes**.</span></span>

<span data-ttu-id="7e113-138">[![Usar código de motivo en la Administración de prestaciones](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span><span class="sxs-lookup"><span data-stu-id="7e113-138">[![Use reason code in Benefits management](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
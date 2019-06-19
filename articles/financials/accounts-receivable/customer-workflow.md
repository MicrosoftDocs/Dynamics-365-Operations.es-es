---
title: Flujo de trabajo de cliente
description: Este tema proporciona información sobre el flujo de trabajo de cliente. Cambia campos específicos para un cliente y, a continuación, envía esos cambios para su aprobación mediante el flujo de trabajo antes de que se añadan al cliente.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 1b0e1621b256e6bbb42f97134b87dd65fa146193
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554883"
---
# <a name="customer-workflow"></a><span data-ttu-id="22114-104">Flujo de trabajo de cliente</span><span class="sxs-lookup"><span data-stu-id="22114-104">Customer workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="22114-105">El flujo de trabajo del cliente se ha agregado a la versión 8.0.4. de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22114-105">The customer workflow has been added to Microsoft Dynamics 365 for Finance and Operations version 8.0.4.</span></span> <span data-ttu-id="22114-106">Puede cambiar campos específicos para un cliente y, a continuación, envía esos cambios para su aprobación mediante el flujo de trabajo antes de que se añadan al cliente.</span><span class="sxs-lookup"><span data-stu-id="22114-106">You can change specific fields for a customer and then send those changes for approval by using the workflow before they are added to the customer.</span></span>

## <a name="set-up-the-customer-workflow"></a><span data-ttu-id="22114-107">Configurar el flujo de trabajo de cliente</span><span class="sxs-lookup"><span data-stu-id="22114-107">Set up the customer workflow</span></span>

<span data-ttu-id="22114-108">Antes de poder usar la función de flujo de trabajo de cliente, debe habilitarla.</span><span class="sxs-lookup"><span data-stu-id="22114-108">Before you can use the customer workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="22114-109">Vaya a **Clientes \> Configuración \> Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="22114-109">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="22114-110">En la pestaña **General**, en la ficha desplegable **Aprobación del cliente**, establezca la opción **Habilitar aprobaciones de cliente** en **Sí** para habilitar la función.</span><span class="sxs-lookup"><span data-stu-id="22114-110">On the **General** tab, on the **Customer approval** FastTab, set the **Enable customer approvals** option to **Yes** to enable the feature.</span></span>
3. <span data-ttu-id="22114-111">En el campo **Comportamiento de entidad de datos**, seleccione el comportamiento que las entidades de datos deben usar cuando se importan los datos:</span><span class="sxs-lookup"><span data-stu-id="22114-111">In the **Data entity behavior** field, select the behavior that the data entities should use when data is imported:</span></span>

    - <span data-ttu-id="22114-112">**Permitir cambios sin aprobación** – Una entidad puede actualizar el registro del cliente sin procesarlo mediante el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22114-112">**Allow changes without approval** – An entity can update the customer record without processing it through the workflow.</span></span>
    - <span data-ttu-id="22114-113">**Rechazar cambios** – No se pueden hacer cambios en el registro del cliente.</span><span class="sxs-lookup"><span data-stu-id="22114-113">**Reject changes** – Changes can't be made to the customer record.</span></span> <span data-ttu-id="22114-114">La importación no se realizará correctamente para los campos que están habilitados para el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22114-114">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="22114-115">**Crear propuestas de cambio** – Se cambiarán todos los campos excepto los que están habilitados para el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22114-115">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="22114-116">Los nuevos valores para esos campos se añadirán al cliente como cambios propuestos, y el flujo de trabajo comenzará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="22114-116">The new values for those fields will be added to the customer as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="22114-117">En la lista de campos del cliente, seleccione la casilla **Habilitar** para cada campo que debe aprobarse antes de que se puedan hacer los cambios.</span><span class="sxs-lookup"><span data-stu-id="22114-117">In the list of customer fields, select then **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="22114-118">Vaya a **Clientes \> Configuración \> Flujos de trabajo de clientes**.</span><span class="sxs-lookup"><span data-stu-id="22114-118">Go to **Accounts receivable \> Setup \> Accounts receivable workflows**.</span></span>
6. <span data-ttu-id="22114-119">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="22114-119">Select **New**.</span></span>
7. <span data-ttu-id="22114-120">Seleccione **Flujo de trabajo de cambio de cliente propuesto**.</span><span class="sxs-lookup"><span data-stu-id="22114-120">Select **Proposed customer change workflow**.</span></span> 
8. <span data-ttu-id="22114-121">Configurar el flujo de trabajo para que coincida con su proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="22114-121">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="22114-122">El elemento de aprobación del flujo de trabajo **Aprobación de flujo de trabajo para el cambio de cliente propuesto** aplicará los cambios al cliente.</span><span class="sxs-lookup"><span data-stu-id="22114-122">The **Workflow approval for proposed customer change** workflow approval element will apply the changes to the customer.</span></span>

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="22114-123">Cambiar la información del cliente y enviar los cambios al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="22114-123">Change customer information and submit the changes to the workflow</span></span>

<span data-ttu-id="22114-124">Cuando cambie un campo que está habilitado para el flujo de trabajo, aparece la página **Cambios propuestos**.</span><span class="sxs-lookup"><span data-stu-id="22114-124">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="22114-125">Esta página muestra el valor original del campo y el nuevo valor que introdujo.</span><span class="sxs-lookup"><span data-stu-id="22114-125">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="22114-126">El campo que cambió se revierte a su valor original.</span><span class="sxs-lookup"><span data-stu-id="22114-126">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="22114-127">Un mensaje de estado en la página le informa de que sus cambios no se han enviado.</span><span class="sxs-lookup"><span data-stu-id="22114-127">A status message on the page informs you that your changes haven't been submitted.</span></span>

<span data-ttu-id="22114-128">Cada vez que cambie un campo que está habilitado para el flujo de trabajo, ese campo se añade a la lista de cambios propuestos.</span><span class="sxs-lookup"><span data-stu-id="22114-128">Every time that you change a field that is enabled for the workflow, that field is added to the list of proposed changes.</span></span> <span data-ttu-id="22114-129">Para descartar el valor propuesto para un campo, use el botón **Descartar** al lado del campo en la lista.</span><span class="sxs-lookup"><span data-stu-id="22114-129">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="22114-130">Para descartar todos los cambios, use el botón **Descartar todos los cambios** en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="22114-130">To discard all changes, use the **Discard all change** button at the bottom of the page.</span></span> <span data-ttu-id="22114-131">Seleccione **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="22114-131">Select **OK** to close the page.</span></span>

<span data-ttu-id="22114-132">Una vez que tenga al menos un cambio propuesto, aparecen dos menús adicionales en el panel de acción: **Cambios propuestos** y **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="22114-132">After you have at least one proposed change, two additional menus appear on the Action Pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="22114-133">Seleccione **Cambios propuestos** para abrir la página **Cambios propuestos** y revise sus cambios.</span><span class="sxs-lookup"><span data-stu-id="22114-133">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="22114-134">Seleccione **Flujo de trabajo \> Enviar** para enviar los cambios en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22114-134">Select **Workflow \> Submit** to submit the changes to the workflow.</span></span>

    <span data-ttu-id="22114-135">El estado en la página se cambia a **Cambios pendientes de aprobación**.</span><span class="sxs-lookup"><span data-stu-id="22114-135">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="22114-136">El flujo de trabajo sigue el proceso de flujo de trabajo estándar en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22114-136">The workflow follows the standard workflow process in Finance and Operations.</span></span> <span data-ttu-id="22114-137">El aprobador es dirigido a la página **Cliente**, donde puede revisar los cambios en la página **Cambios propuestos** y, a continuación, seleccione **Flujo de trabajo \> Aprobar** para aprobar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22114-137">The approver is directed to the **Customer** page, where he or she can review the changes on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="22114-138">Una vez que se completan todas las aprobaciones, los campos se actualizan con los valores que propuso.</span><span class="sxs-lookup"><span data-stu-id="22114-138">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>

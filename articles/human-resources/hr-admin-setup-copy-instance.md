---
title: Copiar una instancia
description: Puede utilizar los servicios Microsoft Dynamics Lifecycle Services (LCS) para copiar una base de datos de Microsoft Dynamics 365 Human Resources en un entorno de espacio retirado.
author: andreabichsel
manager: AnnBe
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6b52b696d323df6bafead2418ae322d1a9cdf64a
ms.sourcegitcommit: ec4df354602c20f48f8581bfe5be0c04c66d2927
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "3706237"
---
# <a name="copy-an-instance"></a><span data-ttu-id="aedc1-103">Copiar una instancia</span><span class="sxs-lookup"><span data-stu-id="aedc1-103">Copy an instance</span></span>

<span data-ttu-id="aedc1-104">Puede utilizar los servicios Microsoft Dynamics Lifecycle Services (LCS) para copiar una base de datos de Microsoft Dynamics 365 Human Resources en un entorno de espacio retirado.</span><span class="sxs-lookup"><span data-stu-id="aedc1-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="aedc1-105">Si tiene otro entorno de espacio retirado, también puede copiar la base de datos del entorno a un entorno de espacio aislado destinado.</span><span class="sxs-lookup"><span data-stu-id="aedc1-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="aedc1-106">Para copiar una instancia, tenga en cuenta los siguientes consejos:</span><span class="sxs-lookup"><span data-stu-id="aedc1-106">To copy an instance, keep the following tips in mind:</span></span>

- <span data-ttu-id="aedc1-107">La instancia de Human Resources que desea sobrescribir debe ser un entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="aedc1-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="aedc1-108">Los entornos desde los que está copiando y a los que copia deben estar en la misma región.</span><span class="sxs-lookup"><span data-stu-id="aedc1-108">The environments you're copying from and to must be in the same region.</span></span> <span data-ttu-id="aedc1-109">No puede copiar entre regiones.</span><span class="sxs-lookup"><span data-stu-id="aedc1-109">You can't copy across regions.</span></span>

- <span data-ttu-id="aedc1-110">Debe ser un administrador en el entorno de destino para poder iniciar sesión después de copiar la instancia.</span><span class="sxs-lookup"><span data-stu-id="aedc1-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="aedc1-111">Cuando copia la base de datos de Human Resources, no copia los elementos (aplicaciones o datos) contenidos en un entorno de Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="aedc1-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft Power Apps environment.</span></span> <span data-ttu-id="aedc1-112">Para obtener información sobre cómo copiar elementos en un entorno de Power Apps, vea [Copiar un entorno](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="aedc1-112">For information about how to copy elements in a Power Apps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="aedc1-113">El entorno de Power Apps que desea sobrescribir debe ser un entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="aedc1-113">The Power Apps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="aedc1-114">Debe ser un administrador global de inquilinos para cambiar un entorno de producción de Power Apps a un entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="aedc1-114">You must be a global tenant admin to change a Power Apps production environment to a sandbox environment.</span></span> <span data-ttu-id="aedc1-115">Para obtener más información sobre cómo cambiar un entorno de Power Apps, vea [Cambiar una instancia](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="aedc1-115">For more information about changing a Power Apps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

- <span data-ttu-id="aedc1-116">Si copia una instancia en su entorno de espacio aislado y desea integrar su entorno de espacio aislado con Common Data Service, debe volver a aplicar campos personalizados a entidades Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="aedc1-116">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Common Data Service, you must reapply custom fields to Common Data Service entities.</span></span> <span data-ttu-id="aedc1-117">Consulte [Aplicar campos personalizados a Common Data Service](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span><span class="sxs-lookup"><span data-stu-id="aedc1-117">See [Apply custom fields to Common Data Service](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="aedc1-118">Efectos de copiar una base de datos de Human Resources</span><span class="sxs-lookup"><span data-stu-id="aedc1-118">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="aedc1-119">Los siguientes eventos ocurren cuando copia una base de datos de Human Resources:</span><span class="sxs-lookup"><span data-stu-id="aedc1-119">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="aedc1-120">El proceso de copia borra la base de datos existente en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="aedc1-120">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="aedc1-121">Una vez que se completa el proceso de copia, no puede recuperar la base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="aedc1-121">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="aedc1-122">El entorno de destino no estará disponible hasta que se complete el proceso de copia.</span><span class="sxs-lookup"><span data-stu-id="aedc1-122">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="aedc1-123">Los documentos de almacenamiento en blobs de Microsoft Azure no se copian de un entorno a otro.</span><span class="sxs-lookup"><span data-stu-id="aedc1-123">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="aedc1-124">Como resultado, los documentos y plantillas que se adjunten no se copiarán y permanecerán en el entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="aedc1-124">As a result, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="aedc1-125">Se deshabilitarán todos los usuarios, excepto el usuario Admin, y otras cuentas de usuario de servicio interno no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="aedc1-125">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="aedc1-126">El usuario administrador puede eliminar u ofuscar datos antes de permitir que otros usuarios vuelvan al sistema.</span><span class="sxs-lookup"><span data-stu-id="aedc1-126">The Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="aedc1-127">El usuario administrador debe realizar los cambios de configuración necesarios, como volver a conectar los puntos finales de integración a servicios o URL específicos.</span><span class="sxs-lookup"><span data-stu-id="aedc1-127">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="aedc1-128">Copiar la base de datos de Human Resources</span><span class="sxs-lookup"><span data-stu-id="aedc1-128">Copy the Human Resources database</span></span>

<span data-ttu-id="aedc1-129">Para completar esta tarea, primero copie una instancia y luego inicie sesión en el Centro de administración de Microsoft Power Platform para copiar su entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="aedc1-129">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your Power Apps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="aedc1-130">Cuando copia una instancia, la base de datos se borra en la instancia de destino.</span><span class="sxs-lookup"><span data-stu-id="aedc1-130">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="aedc1-131">La instancia de destino no está disponible durante este proceso.</span><span class="sxs-lookup"><span data-stu-id="aedc1-131">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="aedc1-132">Inicie sesión en LCS y seleccione el proyecto LCS que contiene la instancia que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="aedc1-132">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="aedc1-133">En su proyecto de LCS seleccione el mosaico **Gestión de la app Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-133">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="aedc1-134">Seleccione la instancia que se debe copiar y, a continuación, seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-134">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="aedc1-135">En el panel de tareas **Copiar una instancia**, seleccione la instancia para sobrescribir y luego seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-135">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="aedc1-136">Espere a que el valor del campo **Estado de copia** se actualice a **Terminado**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-136">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="aedc1-137">Seleccionar la instancia para sobrescribir</span><span class="sxs-lookup"><span data-stu-id="aedc1-137">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="aedc1-138">Seleccione **Power Platform** e inicie sesión en el Centro de administración de Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="aedc1-138">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="aedc1-139">Seleccionar Power Platform</span><span class="sxs-lookup"><span data-stu-id="aedc1-139">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="aedc1-140">Seleccione el entorno de Power Apps para copiar y luego seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-140">Select the Power Apps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="aedc1-141">Cuando se complete el proceso de copia, inicie sesión en la instancia de destino y habilite la integración con Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="aedc1-141">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="aedc1-142">Para obtener más información e instrucciones, consulte [Configurar la integración de Common Data Service](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="aedc1-142">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="aedc1-143">Elementos de datos y estados</span><span class="sxs-lookup"><span data-stu-id="aedc1-143">Data elements and statuses</span></span>

<span data-ttu-id="aedc1-144">Los siguientes elementos de datos no se copian cuando copia una instancia de Human Resources:</span><span class="sxs-lookup"><span data-stu-id="aedc1-144">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="aedc1-145">Direcciones de correo electrónico en la tabla **LogisticsElectronicAddress**</span><span class="sxs-lookup"><span data-stu-id="aedc1-145">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="aedc1-146">Historial de trabajos por lotes en las tablas **BatchJobHistory**, **BatchHistory** y **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="aedc1-146">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="aedc1-147">Contraseña del Protocolo simple de transferencia de correo (SMTP) en la tabla **SysEmailSMTPPassword**</span><span class="sxs-lookup"><span data-stu-id="aedc1-147">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="aedc1-148">El servidor de retransmisión SMTP en la tabla **SysEmailParameters**</span><span class="sxs-lookup"><span data-stu-id="aedc1-148">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="aedc1-149">Configuración de gestión de impresión en las tablas **PrintMgmtSettings** y **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="aedc1-149">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="aedc1-150">Registros específicos del entorno en las tablas **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** y **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="aedc1-150">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="aedc1-151">Documentos adjuntos en la tabla DocuValue</span><span class="sxs-lookup"><span data-stu-id="aedc1-151">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="aedc1-152">Estos archivos adjuntos incluyen cualquier plantilla de Microsoft Office que se sobrescribió en el entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="aedc1-152">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="aedc1-153">La cadena de conexión en la tabla **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="aedc1-153">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="aedc1-154">Algunos de estos elementos no se copian porque son específicos del entorno.</span><span class="sxs-lookup"><span data-stu-id="aedc1-154">Some of these elements aren't copied because they're environment-specific.</span></span> <span data-ttu-id="aedc1-155">Algunos ejemplos son los registros **BatchServerConfig** y **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-155">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="aedc1-156">Otros elementos no se copian debido al volumen de incidencias de soporte.</span><span class="sxs-lookup"><span data-stu-id="aedc1-156">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="aedc1-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aedc1-157">For example:</span></span>

- <span data-ttu-id="aedc1-158">Es posible que se envíen correos electrónicos duplicados porque SMTP todavía está habilitado en el entorno de prueba de aceptación del usuario (espacio aislado).</span><span class="sxs-lookup"><span data-stu-id="aedc1-158">Duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment.</span></span>

- <span data-ttu-id="aedc1-159">Es posible que se envíen mensajes de integración no válidos porque los trabajos por lotes aún están habilitados.</span><span class="sxs-lookup"><span data-stu-id="aedc1-159">Invalid integration messages might be sent because batch jobs are still enabled.</span></span>

- <span data-ttu-id="aedc1-160">Los usuarios pueden estar habilitados antes de que los administradores puedan realizar acciones de limpieza posteriores a la actualización.</span><span class="sxs-lookup"><span data-stu-id="aedc1-160">Users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="aedc1-161">Por otra parte, los siguientes estados cambian cuando copia una instancia:</span><span class="sxs-lookup"><span data-stu-id="aedc1-161">Also, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="aedc1-162">Todos los usuarios, excepto el administrador, están establecidos en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-162">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="aedc1-163">Todos los trabajos por lotes, excepto algunos trabajos del sistema, están configurados como **Retener**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-163">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="aedc1-164">Administración del entorno</span><span class="sxs-lookup"><span data-stu-id="aedc1-164">Environment admin</span></span>

<span data-ttu-id="aedc1-165">Todos los usuarios del entorno de espacio aislado de destino, incluidos los administradores, son reemplazados por los usuarios del entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="aedc1-165">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="aedc1-166">Antes de copiar una instancia, asegúrese de ser administrador en el entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="aedc1-166">Before you copy an instance, be sure that you're an Administrator in the source environment.</span></span> <span data-ttu-id="aedc1-167">Si no lo está, no puede iniciar sesión en el entorno de espacio aislado de destino una vez que se haya completado la copia.</span><span class="sxs-lookup"><span data-stu-id="aedc1-167">If you aren't, you can't sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="aedc1-168">Todos los usuarios que no son administradores en el entorno de espacio aislado de destino están deshabilitados para evitar inicios de sesión no deseados en el entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="aedc1-168">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="aedc1-169">Los administradores pueden volver a habilitar a los usuarios si es necesario.</span><span class="sxs-lookup"><span data-stu-id="aedc1-169">Administrators can reenable users if needed.</span></span>

## <a name="apply-custom-fields-to-common-data-service"></a><span data-ttu-id="aedc1-170">Aplicar campos personalizados a Common Data Service</span><span class="sxs-lookup"><span data-stu-id="aedc1-170">Apply custom fields to Common Data Service</span></span>

<span data-ttu-id="aedc1-171">Si copia una instancia en su entorno de espacio aislado y desea integrar su entorno de espacio aislado con Common Data Service, debe volver a aplicar campos personalizados a entidades Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="aedc1-171">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Common Data Service, you must reapply custom fields to Common Data Service entities.</span></span>

<span data-ttu-id="aedc1-172">Para cada campo personalizado que se expone en entidades Common Data Service, siga los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="aedc1-172">For each custom field that's exposed on Common Data Service entities, do the following steps:</span></span>

1. <span data-ttu-id="aedc1-173">Vaya al campo personalizado y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-173">Go to the custom field and select **Edit**.</span></span>

2. <span data-ttu-id="aedc1-174">Deseleccione el campo **Habilitar** para cada entidad cdm_\* en la que está habilitado el campo personalizado.</span><span class="sxs-lookup"><span data-stu-id="aedc1-174">Unselect the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

3. <span data-ttu-id="aedc1-175">Seleccione **Aplicar cambios**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-175">Select **Apply Changes**.</span></span>

4. <span data-ttu-id="aedc1-176">Seleccione de nuevo **Editar**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-176">Select **Edit** again.</span></span>

5. <span data-ttu-id="aedc1-177">Seleccione el campo **Habilitar** para cada entidad cdm_\* en la que está habilitado el campo personalizado.</span><span class="sxs-lookup"><span data-stu-id="aedc1-177">Select the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

6. <span data-ttu-id="aedc1-178">Seleccione otra vez **Aplicar cambios**.</span><span class="sxs-lookup"><span data-stu-id="aedc1-178">Select **Apply Changes** again.</span></span>

<span data-ttu-id="aedc1-179">El proceso de deseleccionar, aplicar cambios, volver a seleccionar y volver a aplicar cambios hace que el esquema se actualice en Common Data Service para incluir los campos personalizados.</span><span class="sxs-lookup"><span data-stu-id="aedc1-179">The process of unselecting, applying changes, reselecting, and reapplying changes prompts the schema to update in Common Data Service to include the custom fields.</span></span>

<span data-ttu-id="aedc1-180">Para obtener más información sobre los campos personalizados, consulte [Crear y trabajar con campos personalizados](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields).</span><span class="sxs-lookup"><span data-stu-id="aedc1-180">For more information about custom fields, see [Create and work with custom fields](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields).</span></span>

## <a name="see-also"></a><span data-ttu-id="aedc1-181">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aedc1-181">See also</span></span>

[<span data-ttu-id="aedc1-182">Aprovisionar Human Resources</span><span class="sxs-lookup"><span data-stu-id="aedc1-182">Provision Human Resources</span></span>](hr-admin-setup-provision.md)</br>
[<span data-ttu-id="aedc1-183">Quitar una instancia</span><span class="sxs-lookup"><span data-stu-id="aedc1-183">Remove an instance</span></span>](hr-admin-setup-remove-instance.md)</br>
[<span data-ttu-id="aedc1-184">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="aedc1-184">Update process</span></span>](hr-admin-setup-update-process.md)


---
title: Copiar una instancia
description: Puede utilizar los servicios Microsoft Dynamics Lifecycle Services (LCS) para copiar una base de datos de Microsoft Dynamics 365 Human Resources en un entorno de espacio retirado.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: b14baf49517f5d606038af20366944788b22eba2
ms.sourcegitcommit: 1ec931f8fe86bde27f6def36ea214a2a05fb22f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "3554334"
---
# <a name="copy-an-instance"></a><span data-ttu-id="0cfc6-103">Copiar una instancia</span><span class="sxs-lookup"><span data-stu-id="0cfc6-103">Copy an instance</span></span>

<span data-ttu-id="0cfc6-104">Puede utilizar los servicios Microsoft Dynamics Lifecycle Services (LCS) para copiar una base de datos de Microsoft Dynamics 365 Human Resources en un entorno de espacio retirado.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="0cfc6-105">Si tiene otro entorno de espacio retirado, también puede copiar la base de datos del entorno a un entorno de espacio aislado destinado.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="0cfc6-106">Para copiar una instancia, debe asegurarse de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cfc6-106">To copy an instance, you need to ensure the following:</span></span>

- <span data-ttu-id="0cfc6-107">La instancia de Human Resources que desea sobrescribir debe ser un entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="0cfc6-108">Los entornos desde los que está copiando deben estar en la misma región.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-108">The environments you are copying from and to must be in the same region.</span></span> <span data-ttu-id="0cfc6-109">No puede copiar entre regiones.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-109">You can't copy across regions.</span></span>

- <span data-ttu-id="0cfc6-110">Debe ser un administrador en el entorno de destino para poder iniciar sesión después de copiar la instancia.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="0cfc6-111">Cuando copia la base de datos de Human Resources, no copia los elementos (aplicaciones o datos) contenidos en un entorno de Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft PowerApps environment.</span></span> <span data-ttu-id="0cfc6-112">Para obtener información sobre cómo copiar elementos en un entorno de PowerApps, vea [Copiar un entorno](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="0cfc6-112">For information about how to copy elements in a PowerApps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="0cfc6-113">El entorno de PowerApps que desea sobrescribir debe ser un entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-113">The PowerApps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="0cfc6-114">Debe ser un administrador global de inquilinos para cambiar un entorno de producción de PowerApps a un entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-114">You must be a global tenant admin to change a PowerApps production environment to a sandbox environment.</span></span> <span data-ttu-id="0cfc6-115">Para obtener más información sobre cómo cambiar un entorno de PowerApps, vea [Cambiar una instancia](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="0cfc6-115">For more information about changing a PowerApps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="0cfc6-116">Efectos de copiar una base de datos de Human Resources</span><span class="sxs-lookup"><span data-stu-id="0cfc6-116">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="0cfc6-117">Los siguientes eventos ocurren cuando copia una base de datos de Human Resources:</span><span class="sxs-lookup"><span data-stu-id="0cfc6-117">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="0cfc6-118">El proceso de copia borra la base de datos existente en el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-118">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="0cfc6-119">Una vez que se completa el proceso de copia, no puede recuperar la base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-119">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="0cfc6-120">El entorno de destino no estará disponible hasta que se complete el proceso de copia.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-120">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="0cfc6-121">Los documentos de almacenamiento en blobs de Microsoft Azure no se copian de un entorno a otro.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-121">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="0cfc6-122">Por lo tanto, los documentos y plantillas que se adjunten no se copiarán y permanecerán en el entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-122">Therefore, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="0cfc6-123">Se deshabilitarán todos los usuarios, excepto el usuario Admin, y otras cuentas de usuario de servicio interno no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-123">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="0cfc6-124">Por lo tanto, el usuario administrador puede eliminar u ofuscar datos antes de permitir que otros usuarios vuelvan al sistema.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-124">Therefore, the Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="0cfc6-125">El usuario administrador debe realizar los cambios de configuración necesarios, como volver a conectar los puntos finales de integración a servicios o URL específicos.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-125">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="0cfc6-126">Copiar la base de datos de Human Resources</span><span class="sxs-lookup"><span data-stu-id="0cfc6-126">Copy the Human Resources database</span></span>

<span data-ttu-id="0cfc6-127">Para completar esta tarea, primero copie una instancia y luego inicie sesión en el Centro de administración de Microsoft Power Platform para copiar su entorno de PowerApps.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-127">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your PowerApps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="0cfc6-128">Cuando copia una instancia, la base de datos se borra en la instancia de destino.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-128">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="0cfc6-129">La instancia de destino no está disponible durante este proceso.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-129">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="0cfc6-130">Inicie sesión en LCS y seleccione el proyecto LCS que contiene la instancia que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-130">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="0cfc6-131">En su proyecto de LCS seleccione el mosaico **Gestión de la app Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-131">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="0cfc6-132">Seleccione la instancia que se debe copiar y, a continuación, seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-132">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="0cfc6-133">En el panel de tareas **Copiar una instancia**, seleccione la instancia para sobrescribir y luego seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-133">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="0cfc6-134">Espere a que el valor del campo **Estado de copia** se actualice a **Terminado**.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-134">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="0cfc6-135">Seleccionar la instancia para sobrescribir</span><span class="sxs-lookup"><span data-stu-id="0cfc6-135">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="0cfc6-136">Seleccione **Power Platform** e inicie sesión en el Centro de administración de Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-136">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="0cfc6-137">Seleccionar Power Platform</span><span class="sxs-lookup"><span data-stu-id="0cfc6-137">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="0cfc6-138">Seleccione el entorno de PowerApps para copiar y luego seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-138">Select the PowerApps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="0cfc6-139">Cuando se complete el proceso de copia, inicie sesión en la instancia de destino y habilite la integración con Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-139">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="0cfc6-140">Para obtener más información e instrucciones, consulte [Configurar la integración de Common Data Service](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="0cfc6-140">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="0cfc6-141">Elementos de datos y estados</span><span class="sxs-lookup"><span data-stu-id="0cfc6-141">Data elements and statuses</span></span>

<span data-ttu-id="0cfc6-142">Los siguientes elementos de datos no se copian cuando copia una instancia de Human Resources:</span><span class="sxs-lookup"><span data-stu-id="0cfc6-142">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="0cfc6-143">Direcciones de correo electrónico en la tabla **LogisticsElectronicAddress**</span><span class="sxs-lookup"><span data-stu-id="0cfc6-143">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="0cfc6-144">Historial de trabajos por lotes en las tablas **BatchJobHistory**, **BatchHistory** y **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="0cfc6-144">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="0cfc6-145">Contraseña del Protocolo simple de transferencia de correo (SMTP) en la tabla **SysEmailSMTPPassword**</span><span class="sxs-lookup"><span data-stu-id="0cfc6-145">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="0cfc6-146">El servidor de retransmisión SMTP en la tabla **SysEmailParameters**</span><span class="sxs-lookup"><span data-stu-id="0cfc6-146">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="0cfc6-147">Configuración de gestión de impresión en las tablas **PrintMgmtSettings** y **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="0cfc6-147">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="0cfc6-148">Registros específicos del entorno en las tablas **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** y **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="0cfc6-148">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="0cfc6-149">Documentos adjuntos en la tabla DocuValue</span><span class="sxs-lookup"><span data-stu-id="0cfc6-149">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="0cfc6-150">Estos archivos adjuntos incluyen cualquier plantilla de Microsoft Office que se sobrescribió en el entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-150">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="0cfc6-151">La cadena de conexión en la tabla **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="0cfc6-151">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="0cfc6-152">Algunos de estos elementos no se copian porque son específicos del entorno.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-152">Some of these elements aren't copied because they are environment-specific.</span></span> <span data-ttu-id="0cfc6-153">Algunos ejemplos son los registros **BatchServerConfig** y **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-153">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="0cfc6-154">Otros elementos no se copian debido al volumen de incidencias de soporte.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-154">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="0cfc6-155">Por ejemplo, se pueden enviar correos electrónicos duplicados porque SMTP todavía está habilitado en el entorno de pruebas de aceptación del usuario (sandbox), se pueden enviar mensajes de integración no válidos porque los trabajos por lotes aún están habilitados y los usuarios pueden habilitarse antes de que los administradores puedan realizar acciones de limpieza posteriores a la actualización.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-155">For example, duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment, invalid integration messages might be sent because batch jobs are still enabled, and users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="0cfc6-156">Además, los siguientes estados cambian cuando copia una instancia:</span><span class="sxs-lookup"><span data-stu-id="0cfc6-156">In addition, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="0cfc6-157">Todos los usuarios, excepto el administrador, están establecidos en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-157">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="0cfc6-158">Todos los trabajos por lotes, excepto algunos trabajos del sistema, están configurados como **Retener**.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-158">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="0cfc6-159">Administración del entorno</span><span class="sxs-lookup"><span data-stu-id="0cfc6-159">Environment admin</span></span>

<span data-ttu-id="0cfc6-160">Todos los usuarios del entorno de espacio aislado de destino, incluidos los administradores, son reemplazados por los usuarios del entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-160">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="0cfc6-161">Antes de copiar una instancia, asegúrese de ser administrador en el entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-161">Before you copy an instance, be sure that you're an Administrator in the source environment.</span></span> <span data-ttu-id="0cfc6-162">Si no lo está, no podrá iniciar sesión en el entorno de espacio aislado de destino una vez que se haya completado la copia.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-162">If you aren't, you won't be able to sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="0cfc6-163">Todos los usuarios que no son administradores en el entorno de espacio aislado de destino están deshabilitados para evitar inicios de sesión no deseados en el entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-163">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="0cfc6-164">Los administradores pueden volver a habilitar a los usuarios si es necesario.</span><span class="sxs-lookup"><span data-stu-id="0cfc6-164">Administrators can reenable users if needed.</span></span>

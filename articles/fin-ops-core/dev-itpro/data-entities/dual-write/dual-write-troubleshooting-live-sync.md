---
title: Solucionar problemas de sincronización en vivo
description: Este tema proporciona información para la solución de problemas que puede ayudarlo a solucionar problemas con la sincronización en vivo.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 60839bbd1b3ae642cdd419c7df2388292776a461
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172746"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="3e1bc-103">Solucionar problemas de sincronización en vivo</span><span class="sxs-lookup"><span data-stu-id="3e1bc-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="3e1bc-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="3e1bc-105">Proporciona información específica que puede ayudarlo a solucionar problemas con la sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e1bc-106">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="3e1bc-107">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="3e1bc-108">La sincronización en vivo arroja un error prohibido 403 cuando crea un registro en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3e1bc-108">Live synchronization throws a 403 Forbidden error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="3e1bc-109">Es posible que reciba el siguiente mensaje de error cuando crea un registro en una aplicación Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="3e1bc-109">You might receive the following error message when you create a record in a Finance and Operations app:</span></span>

<span data-ttu-id="3e1bc-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"El usuario no es miembro de la organización.\\"}}\], El servidor remoto devolvió un error: (403) Prohibido."}}".*</span><span class="sxs-lookup"><span data-stu-id="3e1bc-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="3e1bc-111">Para solucionar el problema, siga los pasos en [Requisitos del sistema y requisitos previos](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="3e1bc-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="3e1bc-112">Para completar esos pasos, los usuarios de la aplicación de doble escritura que se crea en Common Data Service deben tener el rol de administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-112">To complete those steps, the dual-write application users who are created in Common Data Service must have the system admin role.</span></span> <span data-ttu-id="3e1bc-113">El equipo propietario predeterminado también debe tener el rol de administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="3e1bc-114">La sincronización en vivo para cualquier entidad genera de forma regular un error similar cuando crea un registro en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3e1bc-114">Live synchronization for any entity consistently throws a similar error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="3e1bc-115">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="3e1bc-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="3e1bc-116">Es posible que reciba un mensaje de error como el siguiente cada vez que intente guardar datos de entidad en una aplicación Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="3e1bc-116">You might receive an error message like the following every time that you try to save entity data in a Finance and Operations app:</span></span>

<span data-ttu-id="3e1bc-117">*No se pueden guardar los cambios en la base de datos. La unidad de trabajo no puede confirmar la transacción. No se pueden escribir datos en la entidad uoms. Las escrituras en UnitOfMeasureEntity fallaron con el mensaje de error No se puede sincronizar con las entidades uoms.*</span><span class="sxs-lookup"><span data-stu-id="3e1bc-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="3e1bc-118">Para solucionar el problema, debe asegurarse de que los datos de referencia de requisitos previos existan en la aplicación Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Common Data Service.</span></span> <span data-ttu-id="3e1bc-119">Por ejemplo, si el cliente en el que está en la aplicación Finance and Operations pertenece a un grupo de clientes específico, asegúrese de que el grupo de clientes exista en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Common Data Service.</span></span>

<span data-ttu-id="3e1bc-120">Si existen datos en ambos lados y ha confirmado que el problema no está relacionado con los datos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="3e1bc-121">Detener la entidad relacionada.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-121">Stop the related entity.</span></span>
2. <span data-ttu-id="3e1bc-122">Inicie sesión en la aplicación de Finance and Operations y asegúrese de que existan registros para la entidad que falla en las tablas DualWriteProjectConfiguration y DualWriteProjectFieldConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-122">Sign in to the Finance and Operations app, and make sure that records for the failing entity exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="3e1bc-123">Por ejemplo, así es como se ve la consulta si la entidad **Clientes** está fallando.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-123">For example, here is what the query looks like if the **Customers** entity is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="3e1bc-124">Si hay registros para la entidad anómala incluso después de detener la asignación de la entidad, elimine los registros relacionados con la entidad anómala.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-124">If there are records for the failing entity even after you stop the entity mapping, delete the records that are related to the failing entity.</span></span> <span data-ttu-id="3e1bc-125">Tome nota de la columna **projectname** en la tabla DualWriteProjectConfiguration y obtenga el registro en la tabla DualWriteProjectFieldConfiguration utilizando el nombre del proyecto para eliminar el registro.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the record in the DualWriteProjectFieldConfiguration table by using the project name to delete the record.</span></span>
4. <span data-ttu-id="3e1bc-126">Inicie la asignación de la entidad.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-126">Start the entity mapping.</span></span> <span data-ttu-id="3e1bc-127">Valide si los datos se sincronizan sin ningún problema.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="3e1bc-128">Gestionar errores de privilegio de lectura o escritura cuando crea datos en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3e1bc-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="3e1bc-129">Es posible que reciba un mensaje de error "Solicitud incorrecta" similar al siguiente ejemplo cuando crea datos en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3e1bc-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Ejemplo del mensaje de error de solicitud incorrecta](media/error_record_id_source.png)

<span data-ttu-id="3e1bc-131">Para solucionar el problema, debe asignar la función de seguridad correcta al equipo de la unidad de negocio asignada a Dynamics 365 Sales o Dynamics 365 Customer Service para habilitar el privilegio faltante.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="3e1bc-132">En la aplicación Finance and Operations, busque la unidad de negocio que está asignada en el conjunto de conexión de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Asignación de la organización](media/mapped_business_unit.png)

2. <span data-ttu-id="3e1bc-134">Inicie sesión en el entorno en la aplicación basada en modelos en Dynamics 365, vaya a **Configuración \> Seguridad** y encuentre el equipo de la unidad de negocio asignada.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Equipo de la unidad de negocio asignada](media/setting_security_page.png)

3. <span data-ttu-id="3e1bc-136">Abra la página para que el equipo la edite y luego seleccione **Administrar roles** para abrir la ventana de diálogo **Administrar roles de equipo**.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Botón de administrar roles](media/manage_team_roles.png)

4. <span data-ttu-id="3e1bc-138">Asigne el rol que tiene el privilegio de lectura / escritura para las entidades relevantes y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-138">Assign the role that has the read/write privilege for the relevant entities, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a><span data-ttu-id="3e1bc-139">Solucione problemas de sincronización en un entorno que ha cambiado recientemente el entorno Common Data Service</span><span class="sxs-lookup"><span data-stu-id="3e1bc-139">Fix synchronization issues in an environment that has a recently changed Common Data Service environment</span></span>

<span data-ttu-id="3e1bc-140">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="3e1bc-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="3e1bc-141">Es posible que reciba el siguiente mensaje de error cuando crea datos en una aplicación Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="3e1bc-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="3e1bc-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**No se puede generar la carga útil para la entidad CustCustomerV3Entity**","logDateTime":" 2019-08-27T18:51:52.5843124Z","verboseError":"Error en la creación de la carga útil con error URI no válido: el URI está vacío".}\], isErrorCountUpdated":true}*</span><span class="sxs-lookup"><span data-stu-id="3e1bc-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="3e1bc-143">Este es el aspecto del error en la aplicación basada en modelos en Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="3e1bc-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="3e1bc-144">*Se produjo un error inesperado del código ISV. (ErrorType = ClientError) Excepción inesperada del complemento (Execute): Microsoft.Dynamics.Integrator.CrmPlugins.Plugin: System.Exception: no se pudo procesar la cuenta de la entidad - (Un intento de conexión falló porque la parte conectada no respondió correctamente después de un período de tiempo, o la conexión establecida falló porque el anfitrión conectado no pudo responder*</span><span class="sxs-lookup"><span data-stu-id="3e1bc-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.CrmPlugins.Plugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="3e1bc-145">Este error ocurre cuando el entorno Common Data Service se restablece incorrectamente al mismo tiempo que intenta crear datos en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-145">This error occurs when the Common Data Service environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="3e1bc-146">Para arreglar el problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="3e1bc-147">Inicie sesión en la máquina virtual (VM) Finance and Operations, abra SQL Server Management Studio (SSMS) y busque registros en la tabla DUALWRITEPROJECTCONFIGURATIONENTITY donde **internalentityname** es igual a **Clientes V3** y **externalentityname** es igual a **cuentas**.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for records in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="3e1bc-148">Así es como se ve la consulta.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="3e1bc-149">Use el nombre del proyecto de los resultados de la consulta anterior para ejecutar la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="3e1bc-150">Asegúrese de que la columna **externalenvironmentURL** tiene el Common Data Service o URL de la aplicación correctos.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-150">Make sure that the **externalenvironmentURL** column has the correct Common Data Service or app URL.</span></span> <span data-ttu-id="3e1bc-151">Elimine cualquier registro duplicado que apunte al error Common Data Service URL.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-151">Delete any duplicate records that point to the wrong Common Data Service URL.</span></span> <span data-ttu-id="3e1bc-152">Elimine los registros correspondientes en las tablas DUALWRITEPROJECTFIELDCONFIGURATION y DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="3e1bc-152">Delete the corresponding records in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="3e1bc-153">Detenga la asignación de entidad y luego reiníciela</span><span class="sxs-lookup"><span data-stu-id="3e1bc-153">Stop the entity mapping, and then restart it</span></span>

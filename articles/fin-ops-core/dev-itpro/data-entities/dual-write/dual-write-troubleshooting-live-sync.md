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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 59c8bd80b167cdfaa7a65e469f4dc7ebf8f50844
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744622"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="8f1f7-103">Solucionar problemas de sincronización en vivo</span><span class="sxs-lookup"><span data-stu-id="8f1f7-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="8f1f7-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="8f1f7-105">Proporciona información específica que puede ayudarlo a solucionar problemas con la sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f1f7-106">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="8f1f7-107">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="8f1f7-108">La sincronización en vivo arroja un error prohibido 403 cuando crea una fila en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f1f7-108">Live synchronization throws a 403 Forbidden error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="8f1f7-109">Es posible que reciba el siguiente mensaje de error cuando crea una fila en una aplicación Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="8f1f7-109">You might receive the following error message when you create a row in a Finance and Operations app:</span></span>

<span data-ttu-id="8f1f7-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"El usuario no es miembro de la organización.\\"}}\], El servidor remoto devolvió un error: (403) Prohibido."}}".*</span><span class="sxs-lookup"><span data-stu-id="8f1f7-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="8f1f7-111">Para solucionar el problema, siga los pasos en [Requisitos del sistema y requisitos previos](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="8f1f7-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="8f1f7-112">Para completar esos pasos, los usuarios de la aplicación de doble escritura que se crea en Dataverse deben tener el rol de administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-112">To complete those steps, the dual-write application users who are created in Dataverse must have the system admin role.</span></span> <span data-ttu-id="8f1f7-113">El equipo propietario predeterminado también debe tener el rol de administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-table-consistently-throws-a-similar-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="8f1f7-114">La sincronización en vivo para cualquier tabla genera de forma regular un error similar cuando crea una fila en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f1f7-114">Live synchronization for any table consistently throws a similar error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="8f1f7-115">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="8f1f7-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="8f1f7-116">Es posible que reciba un mensaje de error como el siguiente cada vez que intente guardar datos de tabla en una aplicación Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="8f1f7-116">You might receive an error message like the following every time that you try to save table data in a Finance and Operations app:</span></span>

<span data-ttu-id="8f1f7-117">*No se pueden guardar los cambios en la base de datos. La unidad de trabajo no puede confirmar la transacción. No se pueden escribir datos en la entidad uoms. Las escrituras en UnitOfMeasureEntity fallaron con el mensaje de error No se puede sincronizar con las entidades uoms.*</span><span class="sxs-lookup"><span data-stu-id="8f1f7-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="8f1f7-118">Para solucionar el problema, debe asegurarse de que los datos de referencia de requisitos previos existan en la aplicación Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Dataverse.</span></span> <span data-ttu-id="8f1f7-119">Por ejemplo, si el cliente en el que está en la aplicación Finance and Operations pertenece a un grupo de clientes específico, asegúrese de que el grupo de clientes exista en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Dataverse.</span></span>

<span data-ttu-id="8f1f7-120">Si existen datos en ambos lados y ha confirmado que el problema no está relacionado con los datos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="8f1f7-121">Detener la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-121">Stop the related table.</span></span>
2. <span data-ttu-id="8f1f7-122">Inicie sesión en la aplicación de Finance and Operations y asegúrese de que existan filas para la tabla que falla en las tablas DualWriteProjectConfiguration y DualWriteProjectFieldConfiguration.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-122">Sign in to the Finance and Operations app, and make sure that rows for the failing table exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="8f1f7-123">Por ejemplo, así es como se ve la consulta si la tabla **Clientes** está fallando.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-123">For example, here is what the query looks like if the **Customers** table is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="8f1f7-124">Si hay filas para la tabla anómala incluso después de detener la asignación de la tabla, elimine las filas relacionadas con la tabla anómala.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-124">If there are rows for the failing table even after you stop the table mapping, delete the rows that are related to the failing table.</span></span> <span data-ttu-id="8f1f7-125">Tome nota de la columna **projectname** en la tabla DualWriteProjectConfiguration y obtenga la fila en la tabla DualWriteProjectFieldConfiguration utilizando el nombre del proyecto para eliminar la fila.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the row in the DualWriteProjectFieldConfiguration table by using the project name to delete the row.</span></span>
4. <span data-ttu-id="8f1f7-126">Inicie la asignación de la tabla.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-126">Start the table mapping.</span></span> <span data-ttu-id="8f1f7-127">Valide si los datos se sincronizan sin ningún problema.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="8f1f7-128">Gestionar errores de privilegio de lectura o escritura cuando crea datos en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f1f7-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="8f1f7-129">Es posible que reciba un mensaje de error "Solicitud incorrecta" similar al siguiente ejemplo cuando crea datos en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f1f7-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Ejemplo del mensaje de error de solicitud incorrecta](media/error_record_id_source.png)

<span data-ttu-id="8f1f7-131">Para solucionar el problema, debe asignar la función de seguridad correcta al equipo de la unidad de negocio asignada a Dynamics 365 Sales o Dynamics 365 Customer Service para habilitar el privilegio faltante.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="8f1f7-132">En la aplicación Finance and Operations, busque la unidad de negocio que está asignada en el conjunto de conexión de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Asignación de la organización](media/mapped_business_unit.png)

2. <span data-ttu-id="8f1f7-134">Inicie sesión en el entorno en la aplicación basada en modelos en Dynamics 365, vaya a **Configuración \> Seguridad** y encuentre el equipo de la unidad de negocio asignada.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Equipo de la unidad de negocio asignada](media/setting_security_page.png)

3. <span data-ttu-id="8f1f7-136">Abra la página para que el equipo la edite y luego seleccione **Administrar roles** para abrir la ventana de diálogo **Administrar roles de equipo**.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Botón de administrar roles](media/manage_team_roles.png)

4. <span data-ttu-id="8f1f7-138">Asigne el rol que tiene el privilegio de lectura / escritura para las tablas relevantes y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-138">Assign the role that has the read/write privilege for the relevant tables, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a><span data-ttu-id="8f1f7-139">Solucione problemas de sincronización en un entorno que ha cambiado recientemente el entorno Dataverse</span><span class="sxs-lookup"><span data-stu-id="8f1f7-139">Fix synchronization issues in an environment that has a recently changed Dataverse environment</span></span>

<span data-ttu-id="8f1f7-140">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="8f1f7-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="8f1f7-141">Es posible que reciba el siguiente mensaje de error cuando crea datos en una aplicación Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="8f1f7-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="8f1f7-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**No se puede generar la carga útil para la entidad CustCustomerV3Entity**","logDateTime":" 2019-08-27T18:51:52.5843124Z","verboseError":"Error en la creación de la carga útil con error URI no válido: el URI está vacío".}\], isErrorCountUpdated":true}*</span><span class="sxs-lookup"><span data-stu-id="8f1f7-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="8f1f7-143">Este es el aspecto del error en la aplicación basada en modelos en Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="8f1f7-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="8f1f7-144">*Se produjo un error inesperado del código ISV. (ErrorType = ClientError) Excepción inesperada del complemento (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: no se pudo procesar la cuenta de la entidad - (Un intento de conexión falló porque la parte conectada no respondió correctamente después de un período de tiempo, o la conexión establecida falló porque el anfitrión conectado no pudo responder).*</span><span class="sxs-lookup"><span data-stu-id="8f1f7-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="8f1f7-145">Este error ocurre cuando el entorno Dataverse se restablece incorrectamente al mismo tiempo que intenta crear datos en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-145">This error occurs when the Dataverse environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="8f1f7-146">Para arreglar el problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="8f1f7-147">Inicie sesión en la máquina virtual (VM) Finance and Operations, abra SQL Server Management Studio (SSMS) y busque filas en la tabla DUALWRITEPROJECTCONFIGURATIONENTITY donde **internalentityname** es igual a **Clientes V3** y **externalentityname** es igual a **cuentas**.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for rows in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="8f1f7-148">Así es como se ve la consulta.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="8f1f7-149">Use el nombre del proyecto de los resultados de la consulta anterior para ejecutar la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="8f1f7-150">Asegúrese de que la columna **externalenvironmentURL** tiene el Dataverse o URL de la aplicación correctos.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-150">Make sure that the **externalenvironmentURL** column has the correct Dataverse or app URL.</span></span> <span data-ttu-id="8f1f7-151">Elimine cualquier fila duplicada que apunte al error Dataverse URL.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-151">Delete any duplicate rows that point to the wrong Dataverse URL.</span></span> <span data-ttu-id="8f1f7-152">Elimine las filas correspondientes en las tablas DUALWRITEPROJECTFIELDCONFIGURATION y DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="8f1f7-152">Delete the corresponding rows in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="8f1f7-153">Detenga la asignación de tabla y luego reiníciela</span><span class="sxs-lookup"><span data-stu-id="8f1f7-153">Stop the table mapping, and then restart it</span></span>

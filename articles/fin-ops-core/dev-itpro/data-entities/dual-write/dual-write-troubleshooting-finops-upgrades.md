---
title: Solucionar problemas relacionados con actualizaciones de aplicaciones Finance and Operations
description: Este tema proporciona información de solución de problemas que puede ayudarlo a solucionar problemas relacionados con las actualizaciones de aplicaciones Finance and Operations.
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
ms.openlocfilehash: 53df00de82b101aa02160d865a9c3bbebcfcae15
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275473"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a><span data-ttu-id="d1804-103">Solucionar problemas relacionados con actualizaciones de aplicaciones Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d1804-103">Troubleshoot issues related to upgrades of Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d1804-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d1804-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="d1804-105">Especificamente proporciona información que puede ayudarlo a solucionar problemas relacionados con las actualizaciones de aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1804-105">Specifically, it provides information that can help you fix issues that are related to upgrades of Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1804-106">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d1804-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="d1804-107">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="d1804-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="database-synchronization-errors"></a><span data-ttu-id="d1804-108">Errores de sincronización de la base de datos</span><span class="sxs-lookup"><span data-stu-id="d1804-108">Database synchronization errors</span></span>

<span data-ttu-id="d1804-109">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="d1804-109">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="d1804-110">Es posible que reciba un mensaje de error similar al siguiente ejemplo cuando intenta utilizar la entidad **DualWriteProjectConfiguration** para actualizar una aplicación Finance and Operations a la Platform update 30.</span><span class="sxs-lookup"><span data-stu-id="d1804-110">You might receive an error message that resembles the following example when you try to use the **DualWriteProjectConfiguration** entity to update a Finance and Operations app to Platform update 30.</span></span>

```console
Infolog diagnostic message: 'Cannot select a record in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

<span data-ttu-id="d1804-111">Para arreglar el problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d1804-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="d1804-112">Inicie sesión en la máquina virtual (VM) para la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1804-112">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="d1804-113">Abra Visual Studio como administrador y abra el Árbol de objetos de aplicación (AOT).</span><span class="sxs-lookup"><span data-stu-id="d1804-113">Open Visual Studio as an admin, and open the Application Object Tree (AOT).</span></span>
3. <span data-ttu-id="d1804-114">Buscar **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d1804-114">Search for **DualWriteProjectConfiguration**.</span></span>
4. <span data-ttu-id="d1804-115">En el AOT, haga clic derecho en **DualWriteProjectConfiguration** y seleccione **Agregar al nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d1804-115">In the AOT, right-click **DualWriteProjectConfiguration**, and select **Add to new project**.</span></span> <span data-ttu-id="d1804-116">Seleccione **Aceptar** para crear el nuevo proyecto que usa opciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="d1804-116">Select **OK** to create the new project that uses default options.</span></span>
5. <span data-ttu-id="d1804-117">En el Explorador de soluciones, haga clic con el botón derecho en **Propiedades del proyecto** y establezca **Sincronizar base de datos en la compilación** a **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="d1804-117">In Solution Explorer, right-click **Project properties**, and set **Synchronize Database on Build** to **True**.</span></span>
6. <span data-ttu-id="d1804-118">Compile el proyecto y confirme que la compilación es exitosa.</span><span class="sxs-lookup"><span data-stu-id="d1804-118">Build the project, and confirm that the build is successful.</span></span>
7. <span data-ttu-id="d1804-119">En el menú **Dynamics 365**, seleccione **Sincronizar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="d1804-119">On the **Dynamics 365** menu, select **Synchronize database**.</span></span>
8. <span data-ttu-id="d1804-120">Seleccione **Sincronizar** para hacer una sincronización completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1804-120">Select **Synchronize** to do a full database synchronization.</span></span>
9. <span data-ttu-id="d1804-121">Después de que la sincronización completa de la base de datos sea exitosa, vuelva a ejecutar el paso de sincronización de la base de datos en Microsoft Dynamics Lifecycle Services (LCS) y use los scripts de actualización manual según corresponda, para que pueda continuar con la actualización.</span><span class="sxs-lookup"><span data-stu-id="d1804-121">After the full database synchronization is successful, rerun the database synchronization step in Microsoft Dynamics Lifecycle Services (LCS) and use the manual upgrade scripts as applicable, so that you can proceed with the update.</span></span>

## <a name="missing-entity-fields-issue-on-maps"></a><span data-ttu-id="d1804-122">Problema de campos de entidad faltantes en mapas</span><span class="sxs-lookup"><span data-stu-id="d1804-122">Missing entity fields issue on maps</span></span>

<span data-ttu-id="d1804-123">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="d1804-123">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="d1804-124">En la página **Doble escritura**, puede recibir un mensaje de error similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d1804-124">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="d1804-125">*Falta el campo fuente \<nombre del campo\> en el esquema.*</span><span class="sxs-lookup"><span data-stu-id="d1804-125">*Missing source field \<field name\> in the schema.*</span></span>

![Ejemplo del mensaje de error del campo fuente faltante](media/error_missing_field.png)

<span data-ttu-id="d1804-127">Para solucionar el problema, primero siga estos pasos para asegurarse de que los campos estén en la entidad.</span><span class="sxs-lookup"><span data-stu-id="d1804-127">To fix the issue, first follow these steps to make sure that the fields are in the entity.</span></span>

1. <span data-ttu-id="d1804-128">Inicie sesión en la máquina virtual para la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1804-128">Sign in to the VM for the Finance and Operations app.</span></span>
2. <span data-ttu-id="d1804-129">Vaya a **Espacios de trabajo \> Gestión de datos**, seleccione el mosaico **Parámetros de marco**, y luego, en la pestaña **Configuración de entidad**, seleccione **Actualizar lista de entidades** para actualizar las entidades.</span><span class="sxs-lookup"><span data-stu-id="d1804-129">Go to **Workspaces \> Data management**, select the **Framework parameters** tile, and then, on the **Entity settings** tab, select **Refresh entity list** to refresh the entities.</span></span>
3. <span data-ttu-id="d1804-130">Vaya a **Espacios de trabajo \> Gestión de datos**, seleccione la pestaña **Entidades de datos** y asegúrese de que la entidad esté en la lista.</span><span class="sxs-lookup"><span data-stu-id="d1804-130">Go to **Workspaces \> Data management**, select the **Data entities** tab, and make sure that the entity is listed.</span></span> <span data-ttu-id="d1804-131">Si la entidad no aparece en la lista, inicie sesión en la máquina virtual para la aplicación Finance and Operations y asegúrese de que la entidad esté disponible.</span><span class="sxs-lookup"><span data-stu-id="d1804-131">If the entity isn't listed, sign in to the VM for the Finance and Operations app, and make sure the entity is available.</span></span>
4. <span data-ttu-id="d1804-132">Abra la página **Asignación de entidades** de la página **Doble escritura** en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1804-132">Open the **Entity mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="d1804-133">Seleccione **Actualizar lista de entidades** para completar automáticamente los campos en las asignaciones de entidades.</span><span class="sxs-lookup"><span data-stu-id="d1804-133">Select **Refresh entity list** to automatically fill the fields in the entity mappings.</span></span>

<span data-ttu-id="d1804-134">Si el problema aún no se soluciona, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d1804-134">If the issue still isn't fixed, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1804-135">Estos pasos lo guían a través del proceso de eliminar una entidad y luego agregarla nuevamente.</span><span class="sxs-lookup"><span data-stu-id="d1804-135">These steps guide you through the process of deleting an entity and then adding it again.</span></span> <span data-ttu-id="d1804-136">Para evitar problemas, asegúrese de seguir los pasos exactamente.</span><span class="sxs-lookup"><span data-stu-id="d1804-136">To avoid issues, be sure to follow the steps exactly.</span></span>

1. <span data-ttu-id="d1804-137">En la aplicación Finance and Operations, vaya a **Espacios de trabajo \> Gestión de datos** y seleccione el mosaico **Entidades de datos**.</span><span class="sxs-lookup"><span data-stu-id="d1804-137">In the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Data entities** tile.</span></span>
2. <span data-ttu-id="d1804-138">Encuentre la entidad a la que le falta el atributo.</span><span class="sxs-lookup"><span data-stu-id="d1804-138">Find the entity that is missing the attribute.</span></span> <span data-ttu-id="d1804-139">Haga clic en **Modificar asignación de destino** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="d1804-139">Click **Modify target mapping** in the toolbar.</span></span>
3. <span data-ttu-id="d1804-140">En el panel **Asignar ubicación provisional a destino**, haga clic en **Generar asignación**.</span><span class="sxs-lookup"><span data-stu-id="d1804-140">On the **Map staging to target** pane, click **Generate mapping**.</span></span>
4. <span data-ttu-id="d1804-141">Abra la página **Asignación de entidades** de la página **Doble escritura** en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1804-141">Open the **Entity mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="d1804-142">Si el atributo no se rellena automáticamente en la asignación, agréguelo manualmente haciendo clic en el botón **Agregar atributo** y luego haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d1804-142">If the attribute is not auto-populated on the map, add it manually by clicking **Add attribute** button and then clicking **Save**.</span></span> 
6. <span data-ttu-id="d1804-143">Seleccione la asignación y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d1804-143">Select the map and click **Run**.</span></span>

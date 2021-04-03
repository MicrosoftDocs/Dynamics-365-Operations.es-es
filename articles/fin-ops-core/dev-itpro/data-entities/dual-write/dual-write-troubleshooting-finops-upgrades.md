---
title: Solucionar problemas con actualizaciones de aplicaciones de Finance and Operations
description: Este tema proporciona información de solución de problemas que puede ayudarlo a solucionar problemas relacionados con las actualizaciones de aplicaciones Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ae54ffc9f7a97793dfaddc29f5aae66e5b06c931
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561211"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a><span data-ttu-id="dc3e5-103">Solucionar problemas con actualizaciones de aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="dc3e5-103">Troubleshoot issues from upgrades of Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="dc3e5-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="dc3e5-105">Especificamente proporciona información que puede ayudarlo a solucionar problemas relacionados con las actualizaciones de aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-105">Specifically, it provides information that can help you fix issues that are related to upgrades of Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc3e5-106">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="dc3e5-107">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="database-synchronization-errors"></a><span data-ttu-id="dc3e5-108">Errores de sincronización de la base de datos</span><span class="sxs-lookup"><span data-stu-id="dc3e5-108">Database synchronization errors</span></span>

<span data-ttu-id="dc3e5-109">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="dc3e5-109">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="dc3e5-110">Es posible que reciba un mensaje de error similar al siguiente ejemplo cuando intenta utilizar la tabla **DualWriteProjectConfiguration** para actualizar una aplicación Finance and Operations a la Platform update 30.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-110">You might receive an error message that resembles the following example when you try to use the **DualWriteProjectConfiguration** table to update a Finance and Operations app to Platform update 30.</span></span>

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

<span data-ttu-id="dc3e5-111">Para arreglar el problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="dc3e5-112">Inicie sesión en la máquina virtual (VM) para la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-112">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="dc3e5-113">Abra Visual Studio como administrador y abra el Árbol de objetos de aplicación (AOT).</span><span class="sxs-lookup"><span data-stu-id="dc3e5-113">Open Visual Studio as an admin, and open the Application Object Tree (AOT).</span></span>
3. <span data-ttu-id="dc3e5-114">Buscar **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-114">Search for **DualWriteProjectConfiguration**.</span></span>
4. <span data-ttu-id="dc3e5-115">En el AOT, haga clic derecho en **DualWriteProjectConfiguration** y seleccione **Agregar al nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-115">In the AOT, right-click **DualWriteProjectConfiguration**, and select **Add to new project**.</span></span> <span data-ttu-id="dc3e5-116">Seleccione **Aceptar** para crear el nuevo proyecto que usa opciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-116">Select **OK** to create the new project that uses default options.</span></span>
5. <span data-ttu-id="dc3e5-117">En el Explorador de soluciones, haga clic con el botón derecho en **Propiedades del proyecto** y establezca **Sincronizar base de datos en la compilación** a **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-117">In Solution Explorer, right-click **Project properties**, and set **Synchronize Database on Build** to **True**.</span></span>
6. <span data-ttu-id="dc3e5-118">Compile el proyecto y confirme que la compilación es exitosa.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-118">Build the project, and confirm that the build is successful.</span></span>
7. <span data-ttu-id="dc3e5-119">En el menú **Dynamics 365**, seleccione **Sincronizar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-119">On the **Dynamics 365** menu, select **Synchronize database**.</span></span>
8. <span data-ttu-id="dc3e5-120">Seleccione **Sincronizar** para hacer una sincronización completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-120">Select **Synchronize** to do a full database synchronization.</span></span>
9. <span data-ttu-id="dc3e5-121">Después de que la sincronización completa de la base de datos sea exitosa, vuelva a ejecutar el paso de sincronización de la base de datos en Microsoft Dynamics Lifecycle Services (LCS) y use los scripts de actualización manual según corresponda, para que pueda continuar con la actualización.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-121">After the full database synchronization is successful, rerun the database synchronization step in Microsoft Dynamics Lifecycle Services (LCS) and use the manual upgrade scripts as applicable, so that you can proceed with the update.</span></span>

## <a name="missing-table-columns-issue-on-maps"></a><span data-ttu-id="dc3e5-122">Problema de columnas de tabla faltantes en asignaciones</span><span class="sxs-lookup"><span data-stu-id="dc3e5-122">Missing table columns issue on maps</span></span>

<span data-ttu-id="dc3e5-123">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="dc3e5-123">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="dc3e5-124">En la página **Doble escritura**, puede recibir un mensaje de error similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dc3e5-124">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="dc3e5-125">*Falta el campo de origen \<field name\> en el esquema*.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-125">*Missing source field \<field name\> in the schema.*</span></span>

![Ejemplo del mensaje de error de la columna fuente faltante](media/error_missing_field.png)

<span data-ttu-id="dc3e5-127">Para solucionar el problema, primero siga estos pasos para asegurarse de que las columnas estén en la tabla.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-127">To fix the issue, first follow these steps to make sure that the columns are in the table.</span></span>

1. <span data-ttu-id="dc3e5-128">Inicie sesión en la máquina virtual para la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-128">Sign in to the VM for the Finance and Operations app.</span></span>
2. <span data-ttu-id="dc3e5-129">Vaya a **Espacios de trabajo \> Administración de datos**, seleccione el mosaico **Parámetros de marco**, y luego, en la pestaña **Configuración de tabla**, seleccione **Actualizar lista de tablas** para actualizar las tablas.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-129">Go to **Workspaces \> Data management**, select the **Framework parameters** tile, and then, on the **Table settings** tab, select **Refresh table list** to refresh the tables.</span></span>
3. <span data-ttu-id="dc3e5-130">Vaya a **Espacios de trabajo \> Administración de datos**, seleccione la pestaña **Tablas de datos** y asegúrese de que la tabla esté en la lista.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-130">Go to **Workspaces \> Data management**, select the **Data tables** tab, and make sure that the table is listed.</span></span> <span data-ttu-id="dc3e5-131">Si la tabla no aparece en la lista, inicie sesión en la máquina virtual para la aplicación Finance and Operations y asegúrese de que la tabla esté disponible.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-131">If the table isn't listed, sign in to the VM for the Finance and Operations app, and make sure the table is available.</span></span>
4. <span data-ttu-id="dc3e5-132">Abra la página **Asignación de tablas** de la página **Doble escritura** en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-132">Open the **Table mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="dc3e5-133">Seleccione **Actualizar lista de tablas** para completar automáticamente las columnas en las asignaciones de tablas.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-133">Select **Refresh table list** to automatically fill the columns in the table mappings.</span></span>

<span data-ttu-id="dc3e5-134">Si el problema aún no se soluciona, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-134">If the issue still isn't fixed, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc3e5-135">Estos pasos lo guían a través del proceso de eliminar una tabla y luego agregarla nuevamente.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-135">These steps guide you through the process of deleting a table and then adding it again.</span></span> <span data-ttu-id="dc3e5-136">Para evitar problemas, asegúrese de seguir los pasos exactamente.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-136">To avoid issues, be sure to follow the steps exactly.</span></span>

1. <span data-ttu-id="dc3e5-137">En la aplicación Finance and Operations, vaya a **Espacios de trabajo \> Gestión de datos** y seleccione el mosaico **Tablas de datos**.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-137">In the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Data tables** tile.</span></span>
2. <span data-ttu-id="dc3e5-138">Encuentre la tabla a la que le falta el atributo.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-138">Find the table that is missing the attribute.</span></span> <span data-ttu-id="dc3e5-139">Haga clic en **Modificar asignación de destino** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-139">Click **Modify target mapping** in the toolbar.</span></span>
3. <span data-ttu-id="dc3e5-140">En el panel **Asignar ubicación provisional a destino**, haga clic en **Generar asignación**.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-140">On the **Map staging to target** pane, click **Generate mapping**.</span></span>
4. <span data-ttu-id="dc3e5-141">Abra la página **Asignación de tablas** de la página **Doble escritura** en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-141">Open the **Table mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="dc3e5-142">Si el atributo no se rellena automáticamente en la asignación, agréguelo manualmente haciendo clic en el botón **Agregar atributo** y luego haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-142">If the attribute is not auto-populated on the map, add it manually by clicking **Add attribute** button and then clicking **Save**.</span></span> 
6. <span data-ttu-id="dc3e5-143">Seleccione la asignación y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="dc3e5-143">Select the map and click **Run**.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
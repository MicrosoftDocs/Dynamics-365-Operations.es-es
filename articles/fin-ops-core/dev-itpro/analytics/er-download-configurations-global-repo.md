---
title: Descargue las configuraciones de ER del repositorio global del servicio de configuración
description: Este tema explica cómo descargar configuraciones de informes electrónicos (ER) desde el repositorio global del servicio de configuración.
author: NickSelin
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ed31cdee74c9db26ba76ed263b5e0578cd04bc3d
ms.sourcegitcommit: 7816902b59aa61d9183d54b50a86e282661e3971
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "3421711"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a><span data-ttu-id="71b87-103">Descargue las configuraciones de ER del repositorio global del servicio de configuración</span><span class="sxs-lookup"><span data-stu-id="71b87-103">Download ER configurations from the Global repository of Configuration service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71b87-104">Este tema explica cómo descargar [configuraciones de informes electrónicos (ER)](general-electronic-reporting.md#Configuration) desde el repositorio global del servicio de configuración.</span><span class="sxs-lookup"><span data-stu-id="71b87-104">This topic explains how to download [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the Global repository of configuration service.</span></span> <span data-ttu-id="71b87-105">Para más información, consulte [Microsoft Dynamics 365 for Finance and Operations: Regulatory services, servicio de configuración](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="71b87-105">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="open-configurations-repository"></a><span data-ttu-id="71b87-106">Abrir el repositorio de configuraciones</span><span class="sxs-lookup"><span data-stu-id="71b87-106">Open configurations repository</span></span>

1. <span data-ttu-id="71b87-107">Inicie sesión en la aplicación Dynamics 365 Finance mediante uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="71b87-107">Sign in to the Dynamics 365 Finance application using one of the following roles:</span></span>

    - <span data-ttu-id="71b87-108">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="71b87-108">Electronic reporting developer</span></span>
    - <span data-ttu-id="71b87-109">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="71b87-109">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="71b87-110">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="71b87-110">System administrator</span></span>

2. <span data-ttu-id="71b87-111">Vaya a **Administración de la organización > Espacios de trabajo > Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="71b87-111">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="71b87-112">En la sección **Proveedores de configuración**, seleccione el icono de **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="71b87-112">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
3. <span data-ttu-id="71b87-113">En el icono **Microsoft**, seleccione **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="71b87-113">On the **Microsoft** tile, select **Repositories**.</span></span>

    ![Espacio de trabajo de los informes electrónicos](./media/er-download-configurations-global-repo-er-workspace.png)

4. <span data-ttu-id="71b87-115">En la página **Repositorios de configuración**, en la cuadrícula, seleccione el repositorio existente del tipo **Global**.</span><span class="sxs-lookup"><span data-stu-id="71b87-115">On the **Configuration repositories** page, in the grid, select the existing repository of the **Global** type.</span></span> <span data-ttu-id="71b87-116">Si este repositorio no aparece en la cuadrícula, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="71b87-116">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="71b87-117">Seleccione **Agregar** para agregar un repositorio nuevo.</span><span class="sxs-lookup"><span data-stu-id="71b87-117">Select **Add** to add a new repository.</span></span>
    2. <span data-ttu-id="71b87-118">Seleccione **Global** como tipo de repositorio y luego seleccione **Crear repositorio**.</span><span class="sxs-lookup"><span data-stu-id="71b87-118">Select **Global** as the repository type, and then select **Create repository**.</span></span>
    3. <span data-ttu-id="71b87-119">Si se le solicite, siga las instrucciones de autorización.</span><span class="sxs-lookup"><span data-stu-id="71b87-119">If prompted, follow the authorization instructions.</span></span>
    4. <span data-ttu-id="71b87-120">introduzca un nombre y una descripción para el repositorio y luego seleccione **Aceptar** para confirmar la nueva entrada del repositorio.</span><span class="sxs-lookup"><span data-stu-id="71b87-120">Enter a name and description for the repository and then select **OK** to confirm the new repository entry.</span></span>
    5. <span data-ttu-id="71b87-121">En la cuadrícula, seleccione el nuevo repositorio del tipo **Global**.</span><span class="sxs-lookup"><span data-stu-id="71b87-121">In the grid, select the new repository of the **Global** type.</span></span>

5. <span data-ttu-id="71b87-122">Seleccione **Abrir** para ver la lista de configuraciones de ER para el repositorio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="71b87-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    ![Página de repositorios de configuración](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a><span data-ttu-id="71b87-124">Importar una única configuración</span><span class="sxs-lookup"><span data-stu-id="71b87-124">Import a single configuration</span></span>

1. <span data-ttu-id="71b87-125">En la página **Repositorios de configuración**, en el árbol de configuraciones, seleccione la configuración de ER que desee.</span><span class="sxs-lookup"><span data-stu-id="71b87-125">On the **Configuration repositories** page, in the configurations tree, select the ER configuration that you want.</span></span>
2. <span data-ttu-id="71b87-126">En la ficha desplegable **Versiones**, seleccione la versión necesaria de la configuración de ER seleccionada.</span><span class="sxs-lookup"><span data-stu-id="71b87-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
3. <span data-ttu-id="71b87-127">Seleccione **Importar** para descargar la versión seleccionada del repositorio Global a a la instancia actual de Finance.</span><span class="sxs-lookup"><span data-stu-id="71b87-127">Select **Import** to download the selected version from Global repository to the current Finance instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71b87-128">El botón **Importar** no está disponible para las versiones de configuración de ER que ya están presentes en la instancia de Finance actual.</span><span class="sxs-lookup"><span data-stu-id="71b87-128">The **Import** button is unavailable for ER configuration versions that are already present in the current Finance instance.</span></span>

    ![Página de configuración del repositorio](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a><span data-ttu-id="71b87-130">Importar configuraciones filtradas</span><span class="sxs-lookup"><span data-stu-id="71b87-130">Import filtered configurations</span></span>

1. <span data-ttu-id="71b87-131">En la página **Repositorios de configuración**, en el árbol de configuraciones, expanda la ficha desplegable **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="71b87-131">On the **Configuration repositories** page, in the configurations tree, expand the **Filter** FastTab.</span></span>
2. <span data-ttu-id="71b87-132">En la cuadrícula **Etiquetas**, agregue las etiquetas que sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="71b87-132">In the **Tags** grid, add any tags that are needed.</span></span>
3. <span data-ttu-id="71b87-133">En el campo **Aplicabilidad por país/región**, seleccione los códigos de país/región apropiados y luego seleccione **Aplicar filtro**.</span><span class="sxs-lookup"><span data-stu-id="71b87-133">In the **Country/region applicability** field, select the appropriate country/region codes, and then select  **Apply filter**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71b87-134">La ficha desplegable **Configuraciones** muestra todas las configuraciones que satisfacen las condiciones de selección especificadas.</span><span class="sxs-lookup"><span data-stu-id="71b87-134">The **Configurations** FastTab shows all the configurations that satisfy the specified selection conditions.</span></span>

4. <span data-ttu-id="71b87-135">En la ficha desplegable **Configuraciones**, seleccione **Importar** para descargar las configuraciones filtradas del repositorio Global a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="71b87-135">On the **Configurations** FastTab, select **Import** to download the filtered configurations from the Global repository to the current instance.</span></span>
5. <span data-ttu-id="71b87-136">En la ficha desplegable **Configuraciones**, seleccione **Restablecer filtro** para limpiar las condiciones de selección especificadas.</span><span class="sxs-lookup"><span data-stu-id="71b87-136">On the **Configurations** FastTab, select **Reset filter** to clean up the specified selection conditions.</span></span>

    ![Página de configuración del repositorio](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> <span data-ttu-id="71b87-138">En característica de la configuración de ER, se validan las configuraciones después de haberlas importado.</span><span class="sxs-lookup"><span data-stu-id="71b87-138">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="71b87-139">Es posible que se le notifique acerca de los problemas de incoherencias que se detecten.</span><span class="sxs-lookup"><span data-stu-id="71b87-139">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="71b87-140">Debe resolver los problemas para poder usar la versión de configuración importada.</span><span class="sxs-lookup"><span data-stu-id="71b87-140">Before you can use the imported configuration version, you must resolve the issues.</span></span> <span data-ttu-id="71b87-141">Para obtener más información, consulte la lista de recursos relacionados para este tema.</span><span class="sxs-lookup"><span data-stu-id="71b87-141">For more information, see the list of related resources for this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="71b87-142">Las configuraciones de ER se pueden configurar como dependientes de otras configuraciones.</span><span class="sxs-lookup"><span data-stu-id="71b87-142">ER configurations can be configured as being dependent on other configurations.</span></span> <span data-ttu-id="71b87-143">Por lo tanto, junto con una configuración seleccionada, pueden importarse automáticamente otras configuraciones.</span><span class="sxs-lookup"><span data-stu-id="71b87-143">Therefore, along with a selected configuration, other configurations might be automatically imported.</span></span> <span data-ttu-id="71b87-144">Para obtener más información sobre las dependencias de configuración, consulte [Definir la dependencia de las configuraciones de ER en otros componentes](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span><span class="sxs-lookup"><span data-stu-id="71b87-144">For more about configuration dependencies, see [Define the dependency of ER configurations on other components](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71b87-145">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="71b87-145">Additional resources</span></span>

[<span data-ttu-id="71b87-146">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="71b87-146">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

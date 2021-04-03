---
title: Descargar configuraciones de informes electrónicos de Lifecycle Services
description: En este tema se explica cómo descargar las configuraciones de Informes electrónicos (ER) de Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8aaa3be426c0321da7e72d6acc18918d8b0ecee2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570379"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="c3cbd-103">Descargar configuraciones de informes electrónicos de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="c3cbd-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3cbd-104">Este tema explica cómo descargar la versión más reciente de [Configuraciones de informes electrónicos (ER)](general-electronic-reporting.md#Configuration) desde la [Biblioteca de activos compartidos](../lifecycle-services/asset-library.md) en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c3cbd-104">This topic explains how to download the newest version of [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the [Shared asset library](../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="c3cbd-105">Inicie sesión a la aplicación mediante uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3cbd-105">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="c3cbd-106">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="c3cbd-106">Electronic reporting developer</span></span>
    - <span data-ttu-id="c3cbd-107">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="c3cbd-107">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="c3cbd-108">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="c3cbd-108">System administrator</span></span>

2. <span data-ttu-id="c3cbd-109">Vaya a **Administración de la organización** &gt; **Espacios de trabajo** &gt; **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-109">Go to **Organization administration** &gt; **Workspaces** &gt; **Electronic reporting**.</span></span>
3. <span data-ttu-id="c3cbd-110">En la sección **Proveedores de configuración**, seleccione el icono de **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-110">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4. <span data-ttu-id="c3cbd-111">En el icono **Microsoft**, seleccione **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-111">On the **Microsoft** tile, select **Repositories**.</span></span>

    <span data-ttu-id="c3cbd-112">[![Icono de Microsoft en la página de configuraciones de localización](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="c3cbd-112">[![Microsoft tile on the Localization configurations page](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>

5. <span data-ttu-id="c3cbd-113">En la página **Repositorios de configuración**, en la cuadrícula, seleccione el repositorio existente del tipo **LCS**.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-113">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="c3cbd-114">Si este repositorio no aparece en la cuadrícula, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c3cbd-114">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="c3cbd-115">Seleccione **Agregar** para agregar un repositorio.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-115">Select **Add** to add a repository.</span></span>
    2. <span data-ttu-id="c3cbd-116">Seleccione **LCS** como el tipo de repositorio.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-116">Select **LCS** as the repository type.</span></span>
    3. <span data-ttu-id="c3cbd-117">Seleccione **Crear repositorio**.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-117">Select **Create repository**.</span></span>
    4. <span data-ttu-id="c3cbd-118">Si se le solicita la autorización, siga las instrucciones en pantalla.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-118">If you're prompted about authorization, follow the on-screen instructions.</span></span>
    5. <span data-ttu-id="c3cbd-119">Especifique un nombre y una descripción para el repositorio.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-119">Enter a name and description for the repository.</span></span>
    6. <span data-ttu-id="c3cbd-120">Seleccione **Aceptar** para confirmar la nueva entrada de repositorio.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-120">Select **OK** to confirm the new repository entry.</span></span>
    7. <span data-ttu-id="c3cbd-121">En la cuadrícula, seleccione el nuevo repositorio del tipo **LCS**.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-121">In the grid, select the new repository of the **LCS** type.</span></span>

6. <span data-ttu-id="c3cbd-122">Seleccione **Abrir** para ver la lista de configuraciones de ER para el repositorio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    <span data-ttu-id="c3cbd-123">[![Página de repositorios de configuración](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="c3cbd-123">[![Configuration repositories page](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>

    > [!TIP]
    > <span data-ttu-id="c3cbd-124">Si tiene problemas para acceder al repositorio LCS para descargar configuraciones de la biblioteca de activos compartidos en LCS, puede descargar configuraciones desde el [Repositorio global](er-download-configurations-global-repo.md) en lugar.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-124">If you have trouble accessing the LCS repository to download configurations from the Shared asset library in LCS, you can download configurations from the [Global repository](er-download-configurations-global-repo.md) instead.</span></span>

7. <span data-ttu-id="c3cbd-125">En el árbol de configuración del panel izquierdo, seleccione la configuración de ER que necesita.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-125">In the configurations tree in the left pane, select the required ER configuration.</span></span>
8. <span data-ttu-id="c3cbd-126">En la ficha desplegable **Versiones**, seleccione la versión necesaria de la configuración de ER seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9. <span data-ttu-id="c3cbd-127">Seleccione **Importar** para descargar la versión seleccionada de LCS en la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-127">Select **Import** to download the selected version from LCS to the current instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3cbd-128">El botón **Importar** no está disponible para las versiones de configuración de ER que ya están presentes en la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-128">The **Import** button is unavailable for ER configuration versions that are already present in the current instance.</span></span>

    <span data-ttu-id="c3cbd-129">[![Página de configuración del repositorio](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="c3cbd-129">[![Configuration repository page](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

> [!NOTE]
> <span data-ttu-id="c3cbd-130">En característica de la configuración de ER, se validan las configuraciones después de haberlas importado.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-130">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="c3cbd-131">Es posible que se le notifique acerca de los problemas de incoherencias que se detecten.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-131">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="c3cbd-132">Debe resolver esos problemas antes de poder usar la versión de configuración importada.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-132">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="c3cbd-133">Para obtener más información, consulte la lista de temas relacionados para este tema.</span><span class="sxs-lookup"><span data-stu-id="c3cbd-133">For more information, see the list of related topics for this topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c3cbd-134">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c3cbd-134">Additional resources</span></span>

[<span data-ttu-id="c3cbd-135">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="c3cbd-135">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="c3cbd-136">Descargue las configuraciones de ER del repositorio global del servicio de configuración</span><span class="sxs-lookup"><span data-stu-id="c3cbd-136">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
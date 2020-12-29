---
title: Importar versiones actualizadas de configuraciones ER
description: Este tema explica cómo importar versiones actualizadas de informes electrónicos (ER) desde el repositorio global del servicio de configuración.
author: NickSelin
manager: AnnBe
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 897663998c6c95ff6d7172de2abc4d4dd6ec5f12
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679519"
---
# <a name="import-updated-versions-of-er-configurations"></a><span data-ttu-id="cd55f-103">Importar versiones actualizadas de configuraciones ER</span><span class="sxs-lookup"><span data-stu-id="cd55f-103">Import updated versions of ER configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cd55f-104">Los [repositorios](general-electronic-reporting.md#Repository) de informes electrónicos (ER) se usan para compartir [configuraciones ER](general-electronic-reporting.md#Configuration).</span><span class="sxs-lookup"><span data-stu-id="cd55f-104">Electronic reporting (ER) [repositories](general-electronic-reporting.md#Repository) are used to share [ER configurations](general-electronic-reporting.md#Configuration).</span></span> <span data-ttu-id="cd55f-105">Puede [importar](download-electronic-reporting-configuration-lcs.md) configuraciones de ER desde diferentes repositorios en su instancia de Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="cd55f-105">You can [import](download-electronic-reporting-configuration-lcs.md) ER configurations from different repositories into your instance of Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="cd55f-106">Cuando importa configuraciones de ER, los [proveedores de configuración](general-electronic-reporting.md#Provider) puede publicar [versiones](general-electronic-reporting.md#component-versioning) nuevas de repositorios para que puedan ser compartidos.</span><span class="sxs-lookup"><span data-stu-id="cd55f-106">When you import ER configurations, [configuration providers](general-electronic-reporting.md#Provider) can publish new [versions](general-electronic-reporting.md#component-versioning) repositories so that they can be shared.</span></span>

<span data-ttu-id="cd55f-107">Este tema explica cómo importar versiones actualizadas de ER desde el repositorio global del servicio de configuración.</span><span class="sxs-lookup"><span data-stu-id="cd55f-107">This topic explains how to import updated versions of ER configurations from the Global repository of the Configuration service.</span></span> <span data-ttu-id="cd55f-108">Para más información, consulte [Microsoft Dynamics 365 for Finance and Operations: Regulatory services, servicio de configuración](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="cd55f-108">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="review-the-available-updated-versions"></a><span data-ttu-id="cd55f-109">Revise las versiones actualizadas disponibles</span><span class="sxs-lookup"><span data-stu-id="cd55f-109">Review the available updated versions</span></span>

1. <span data-ttu-id="cd55f-110">Inicie sesión en Finance mediante con uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd55f-110">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="cd55f-111">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="cd55f-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="cd55f-112">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="cd55f-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="cd55f-113">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="cd55f-113">System administrator</span></span>

2. <span data-ttu-id="cd55f-114">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="cd55f-114">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="cd55f-115">En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Importar versiones actualizadas de configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="cd55f-115">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>

    ![Página de ubicación de configuraciones](./media/er-download-updated-versions-global-repo1.png)

4. <span data-ttu-id="cd55f-117">En el cuadro de diálogo **Importar actualizaciones de versiones de configuraciones de informes electrónicos**, en el campo **Modo de ejecución**, seleccione **Mostrar solo las actualizaciones disponibles**.</span><span class="sxs-lookup"><span data-stu-id="cd55f-117">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Only show available updates**.</span></span> <span data-ttu-id="cd55f-118">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd55f-118">Then select **OK**.</span></span> 

    ![El campo Modo de ejecución está configurado para mostrar solo las actualizaciones disponibles](./media/er-download-updated-versions-global-repo2.png)

5. <span data-ttu-id="cd55f-120">Revise los mensajes que recibe.</span><span class="sxs-lookup"><span data-stu-id="cd55f-120">Review the messages that you receive.</span></span> <span data-ttu-id="cd55f-121">Estos mensajes proporcionan la siguiente información sobre las configuraciones de ER en la instancia actual de Finance y cómo se comparan con el contenido del repositorio global:</span><span class="sxs-lookup"><span data-stu-id="cd55f-121">These messages provide the following information about the ER configurations in the current Finance instance and how they compare to the content of the Global repository:</span></span>

    - <span data-ttu-id="cd55f-122">El número total de configuraciones de ER</span><span class="sxs-lookup"><span data-stu-id="cd55f-122">The total number of ER configurations</span></span>
    - <span data-ttu-id="cd55f-123">Configuraciones de ER que no están presentes en el repositorio global</span><span class="sxs-lookup"><span data-stu-id="cd55f-123">ER configurations that aren't present in the Global repository</span></span>
    - <span data-ttu-id="cd55f-124">Configuraciones de ER para las cuales la última versión ya está disponible en la instancia actual de Finance (para ver la lista completa de estas configuraciones de ER, seleccione el enlace **Detalles del mensaje**).</span><span class="sxs-lookup"><span data-stu-id="cd55f-124">ER configurations for which the latest version is already available in the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![Mensaje y detalles del mensaje "Las últimas versiones de las siguientes configuraciones ya están importadas"](./media/er-download-updated-versions-global-repo3.png)

    - <span data-ttu-id="cd55f-126">Configuraciones de ER para las cuales la última versión está disponible en el repositorio global y pueden importarse en la instancia actual de Finance (para ver la lista completa de estas configuraciones de ER, seleccione el enlace **Detalles del mensaje**).</span><span class="sxs-lookup"><span data-stu-id="cd55f-126">ER configurations for which the latest version is available in the Global repository and can be imported into the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![Mensaje "Actualizaciones disponibles" y detalles del mensaje](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a><span data-ttu-id="cd55f-128">Importar versiones actualizadas disponibles</span><span class="sxs-lookup"><span data-stu-id="cd55f-128">Import available updated versions</span></span>

1. <span data-ttu-id="cd55f-129">Inicie sesión en Finance mediante con uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd55f-129">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="cd55f-130">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="cd55f-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="cd55f-131">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="cd55f-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="cd55f-132">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="cd55f-132">System administrator</span></span>

2. <span data-ttu-id="cd55f-133">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="cd55f-133">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="cd55f-134">En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Importar versiones actualizadas de configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="cd55f-134">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>
4. <span data-ttu-id="cd55f-135">En el cuadro de diálogo **Importar actualizaciones de versiones de configuraciones de informes electrónicos**, en el campo **Modo de ejecución**, seleccione **Importar las últimas actualizaciones** para importar las últimas versiones de configuraciones ER desde el repositorio global a la instancia actual de Finance.</span><span class="sxs-lookup"><span data-stu-id="cd55f-135">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Import latest updates** to import the latest versions of ER configurations from the Global repository into the current Finance instance.</span></span>
5. <span data-ttu-id="cd55f-136">Para programar un trabajo por lotes para la importación, en la ficha desplegable **Correr en segundo plano**, configure la opción **Procesamiento por lotes** **Sí**.</span><span class="sxs-lookup"><span data-stu-id="cd55f-136">To schedule a batch job for the import, on the **Run in the background** FastTab, set the **Batch processing** option to **Yes**.</span></span> <span data-ttu-id="cd55f-137">Si desea repetir la importación periódicamente, configure la recurrencia requerida.</span><span class="sxs-lookup"><span data-stu-id="cd55f-137">If you want to repeat the import periodically, configure the required recurrence.</span></span>

    ![Campo de modo de ejecución configurado para importar las últimas actualizaciones](./media/er-download-updated-versions-global-repo5.png)

6. <span data-ttu-id="cd55f-139">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cd55f-139">Select **OK**.</span></span>
7. <span data-ttu-id="cd55f-140">Para saber qué versiones de configuración se han importado, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cd55f-140">To learn what configuration versions have been imported, follow one of these steps:</span></span>

    - <span data-ttu-id="cd55f-141">Si ejecuta la importación de forma interactiva en lugar de utilizar un trabajo por lotes, revise los mensajes que recibe.</span><span class="sxs-lookup"><span data-stu-id="cd55f-141">If you run the import interactively instead of using a batch job, review the messages that you receive.</span></span>

        ![Mensajes recibidos durante una ejecución de importación interactiva](./media/er-download-updated-versions-global-repo6.png)

    - <span data-ttu-id="cd55f-143">Si ejecuta la importación en modo por lotes, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cd55f-143">If you run the import in batch mode, follow these steps:</span></span>

        1. <span data-ttu-id="cd55f-144">Vaya **Común** \> **Consultas** \> **Trabajos por lotes** \> **Mis trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="cd55f-144">Go to **Common** \> **Inquiries** \> **Batch jobs** \> **My batch jobs**.</span></span>
        2. <span data-ttu-id="cd55f-145">Encuentre y seleccione el trabajo **Importar actualizaciones de versiones de configuraciones de informes electrónicos** y luego, en el Panel de acciones, en la pestaña **Trabajo por lotes**, seleccione **Historial de trabajo por lotes** para ver el historial de trabajos.</span><span class="sxs-lookup"><span data-stu-id="cd55f-145">Find and select the **Import electronic reporting configurations versions updates** job, and then, on the Action Pane, on the **Batch job** tab, select **Batch job history** to view the job history.</span></span>
        3. <span data-ttu-id="cd55f-146">En la página **Historial de trabajo por lotes**, seleccione **Registro**.</span><span class="sxs-lookup"><span data-stu-id="cd55f-146">On the **Batch job history** page, select **Log**.</span></span> <span data-ttu-id="cd55f-147">Luego, en el mensaje que recibe, seleccione el vínculo **Detalles del mensaje** para ver el registro de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cd55f-147">Then, in the message that you receive, select the **Message details** link to view the job log.</span></span>

        ![Registro de trabajo](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> <span data-ttu-id="cd55f-149">No recomendamos que programe un trabajo por lotes recurrente para importar versiones actualizadas de configuraciones de ER directamente desde el repositorio global a un entorno de producción, porque las versiones importadas estarán disponibles de inmediato para su uso.</span><span class="sxs-lookup"><span data-stu-id="cd55f-149">We don't recommend that you schedule a recurring batch job to import updated versions of ER configurations directly from the Global repository into a production environment, because the imported versions will immediately be available for use.</span></span> <span data-ttu-id="cd55f-150">En su lugar, utilice este enfoque para implementar versiones de configuraciones de ER en un entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="cd55f-150">Instead, use this approach to deploy versions of ER configurations to a sandbox environment.</span></span> <span data-ttu-id="cd55f-151">Luego pueden evaluarse en el entorno de espacio aislado antes de implementarse en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="cd55f-151">They can then be evaluated in the sandbox environment before they are deployed to a production environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cd55f-152">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cd55f-152">Additional resources</span></span>

- [<span data-ttu-id="cd55f-153">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="cd55f-153">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="cd55f-154">Descargue las configuraciones de ER del repositorio global del servicio de configuración</span><span class="sxs-lookup"><span data-stu-id="cd55f-154">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)

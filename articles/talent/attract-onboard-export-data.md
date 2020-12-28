---
title: Exportar datos desde Attract y Onboard
description: 'Exporte datos desde Dynamics 365 Talent: Attract y Onboard.'
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462416"
---
# <a name="export-data-from-attract-and-onboard"></a><span data-ttu-id="0c03e-103">Exportar datos desde Attract y Onboard</span><span class="sxs-lookup"><span data-stu-id="0c03e-103">Export data from Attract and Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0c03e-104">Como se anunció en [Retirada de las aplicaciones Dynamics 365 Talent: Attract y Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), vamos a retirar Dynamics 365 Talent: Attract y Dynamics 365 Talent: Onboard el 1 de febrero de 2022.</span><span class="sxs-lookup"><span data-stu-id="0c03e-104">As announced in [Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), we're retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard on February 1, 2022.</span></span> <span data-ttu-id="0c03e-105">Para ayudarle a migrar a otro producto, ahora ofrecen ambas aplicaciones funciones de exportación de datos.</span><span class="sxs-lookup"><span data-stu-id="0c03e-105">To help with your migration to another product, both apps now provide data export capabilities.</span></span>

## <a name="export-data-from-attract"></a><span data-ttu-id="0c03e-106">Exportar datos desde Attract</span><span class="sxs-lookup"><span data-stu-id="0c03e-106">Export data from Attract</span></span>

<span data-ttu-id="0c03e-107">Puede exportar los datos sin limitar el acceso a su entorno.</span><span class="sxs-lookup"><span data-stu-id="0c03e-107">You can export your data without restricting access to your environment.</span></span> <span data-ttu-id="0c03e-108">Es posible que desee hacer esto con fines de prueba o para comprender nuestra estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="0c03e-108">You might want to do this for testing purposes or to understand our data structure.</span></span> <span data-ttu-id="0c03e-109">Cuando esté listo para migrar, limite el acceso a su entorno de Attract mediante las instrucciones que se indican después de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0c03e-109">When you're ready to migrate, restrict access to your Attract environment using the instructions after this procedure.</span></span> <span data-ttu-id="0c03e-110">Asegúrese de exportar los datos nuevamente.</span><span class="sxs-lookup"><span data-stu-id="0c03e-110">Be sure to export your data again.</span></span> 

1. <span data-ttu-id="0c03e-111">Ir a [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="0c03e-111">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="0c03e-112">En **Exportación de datos**, seleccione **Solicitar una exportación de datos**.</span><span class="sxs-lookup"><span data-stu-id="0c03e-112">Under **Data export**, select **Request a data export**.</span></span>

   ![[<span data-ttu-id="0c03e-113">Solicitar una exportación de datos desde Attract</span><span class="sxs-lookup"><span data-stu-id="0c03e-113">Request a data export from Attract</span></span>](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. <span data-ttu-id="0c03e-114">Cuando se abra el cuadro de mensaje **Su petición se está procesando**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0c03e-114">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="0c03e-115">La exportación de datos puede tardar hasta 20 minutos, en función de su tamaño.</span><span class="sxs-lookup"><span data-stu-id="0c03e-115">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="0c03e-116">Cuando finalice su exportación, haga clic en el botón **Descargar** situado junto a ella.</span><span class="sxs-lookup"><span data-stu-id="0c03e-116">When your export completes, select the **Download** button next to it.</span></span> 

   >[!NOTE]
   ><span data-ttu-id="0c03e-117">Todas las exportaciones de datos están disponibles durante siete días. Después, el vínculo **Descargar** expira.</span><span class="sxs-lookup"><span data-stu-id="0c03e-117">All data exports are available for seven days, at which point the **Download** link expires.</span></span></br>
   
<span data-ttu-id="0c03e-118">La descarga contiene un archivo .zip con sus datos de Attract, incluidas las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="0c03e-118">The download contains a .zip file with your Attract data, including the following folders:</span></span>

| <span data-ttu-id="0c03e-119">Nombre de carpeta</span><span class="sxs-lookup"><span data-stu-id="0c03e-119">Folder name</span></span> | <span data-ttu-id="0c03e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c03e-120">Description</span></span> |
| --- | --- |
| <span data-ttu-id="0c03e-121">Configuración de administrador</span><span class="sxs-lookup"><span data-stu-id="0c03e-121">Admin settings</span></span> | <span data-ttu-id="0c03e-122">Configuraciones del Centro de administración de Attract.</span><span class="sxs-lookup"><span data-stu-id="0c03e-122">Attract admin center configurations.</span></span> |
| <span data-ttu-id="0c03e-123">Candidatos</span><span class="sxs-lookup"><span data-stu-id="0c03e-123">Candidates</span></span> | <span data-ttu-id="0c03e-124">Todos los candidatos que se agregaron a trabajos o grupos de talentos.</span><span class="sxs-lookup"><span data-stu-id="0c03e-124">All candidates that were added to jobs or talent pools.</span></span> |
| <span data-ttu-id="0c03e-125">Plantillas de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="0c03e-125">Email templates</span></span> | <span data-ttu-id="0c03e-126">Todas las plantillas de correo electrónico que se configuraron para el entorno.</span><span class="sxs-lookup"><span data-stu-id="0c03e-126">All email templates that were configured for the environment.</span></span> |
| <span data-ttu-id="0c03e-127">Plantillas de paquetes de oferta de trabajo</span><span class="sxs-lookup"><span data-stu-id="0c03e-127">Job offer package templates</span></span> | <span data-ttu-id="0c03e-128">Todas las plantillas de paquetes de ofertas de trabajo que se crearon, con sus configuraciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="0c03e-128">All job offer package templates that were created, plus their associated configurations.</span></span> |
| <span data-ttu-id="0c03e-129">Conjunto de reglas de oferta de trabajo</span><span class="sxs-lookup"><span data-stu-id="0c03e-129">Job offer rule sets</span></span> |  <span data-ttu-id="0c03e-130">Todos los archivos de conjunto de reglas que se cargaron para la administración de ofertas.</span><span class="sxs-lookup"><span data-stu-id="0c03e-130">All rule set files that were uploaded for offer management.</span></span> |
| <span data-ttu-id="0c03e-131">Plantillas de oferta de trabajo</span><span class="sxs-lookup"><span data-stu-id="0c03e-131">Job offer templates</span></span> | <span data-ttu-id="0c03e-132">Todas las plantillas de documentos de ofertas de trabajo creadas para el entorno.</span><span class="sxs-lookup"><span data-stu-id="0c03e-132">All job offer document templates created for the environment.</span></span> |
| <span data-ttu-id="0c03e-133">Vacantes</span><span class="sxs-lookup"><span data-stu-id="0c03e-133">Job openings</span></span> | <span data-ttu-id="0c03e-134">Todos los empleos creados.</span><span class="sxs-lookup"><span data-stu-id="0c03e-134">All created jobs.</span></span> <span data-ttu-id="0c03e-135">Los trabajos eliminados no se exportan.</span><span class="sxs-lookup"><span data-stu-id="0c03e-135">Deleted jobs aren't exported.</span></span> <span data-ttu-id="0c03e-136">Las subcarpetas contienen solicitudes de candidatos, con subcarpetas para los archivos adjuntos de las solicitudes de candidatos y paquetes de ofertas, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="0c03e-136">The sub-folders contain candidate applications, with sub-folders for candidate application attachments and offer packages, where applicable.</span></span> |
| <span data-ttu-id="0c03e-137">Plantillas de vacantes</span><span class="sxs-lookup"><span data-stu-id="0c03e-137">Job opening templates</span></span> | <span data-ttu-id="0c03e-138">Plantillas de proceso de trabajo que se configuraron en el entorno.</span><span class="sxs-lookup"><span data-stu-id="0c03e-138">Job process templates that were configured in the environment.</span></span> |
| <span data-ttu-id="0c03e-139">Grupos de talentos</span><span class="sxs-lookup"><span data-stu-id="0c03e-139">Talent pools</span></span> | <span data-ttu-id="0c03e-140">Todos los grupos de talentos creados, sus listas de colaboradores y las listas de candidatos para los grupos de talentos.</span><span class="sxs-lookup"><span data-stu-id="0c03e-140">All created talent pools, their contributors lists, and the candidates lists for the talent pools.</span></span> |
| <span data-ttu-id="0c03e-141">Trabajadores</span><span class="sxs-lookup"><span data-stu-id="0c03e-141">Workers</span></span> | <span data-ttu-id="0c03e-142">Lista de todos los trabajadores que están presentes en el entorno, y sus roles.</span><span class="sxs-lookup"><span data-stu-id="0c03e-142">List of all the workers who are present in the environment, plus their roles.</span></span> |
| <span data-ttu-id="0c03e-143">(carpeta raíz)</span><span class="sxs-lookup"><span data-stu-id="0c03e-143">(root folder)</span></span> | <span data-ttu-id="0c03e-144">Un archivo de esquema JSON que describe los campos de la estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="0c03e-144">A JSON schema file that describes the data structure fields.</span></span> |

### <a name="restrict-access-to-attract"></a><span data-ttu-id="0c03e-145">Restringir el acceso a Attract</span><span class="sxs-lookup"><span data-stu-id="0c03e-145">Restrict access to Attract</span></span>

<span data-ttu-id="0c03e-146">Cuando esté preparado para realizar la migración, limite el acceso de los no administradores a su entorno de Attract y exporte los datos.</span><span class="sxs-lookup"><span data-stu-id="0c03e-146">When you're ready to migrate, restrict non-admins from accessing your Attract environment and export your data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="0c03e-147">Restringir el acceso a su entorno de Attract es una acción irreversible.</span><span class="sxs-lookup"><span data-stu-id="0c03e-147">Restricting access to your Attract environment is permanent and can't be undone.</span></span> <span data-ttu-id="0c03e-148">Si desea que los usuarios que no son administradores sigan accediendo a su entorno, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="0c03e-148">If you want non-admin users to continue accessing your environment, skip this step.</span></span>

1. <span data-ttu-id="0c03e-149">Ir a [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="0c03e-149">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="0c03e-150">Para restringir el acceso de los no administradores a su entorno de Attract, en **Restringe el acceso a esta aplicación** seleccione **Restringir el acceso ahora**.</span><span class="sxs-lookup"><span data-stu-id="0c03e-150">To restrict non-admins from accessing your Attract environment, under **Restrict access to this app**, select **Restrict access now**.</span></span> <span data-ttu-id="0c03e-151">Restringir el acceso también elimina los puestos de trabajo activos que se hayan publicado.</span><span class="sxs-lookup"><span data-stu-id="0c03e-151">Restricting access also unposts any active jobs that have been posted.</span></span>

   ![[<span data-ttu-id="0c03e-152">Restringir el acceso de no administradores a Attract</span><span class="sxs-lookup"><span data-stu-id="0c03e-152">Restrict non-admin access to Attract</span></span>](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. <span data-ttu-id="0c03e-153">Cuando vea la advertencia **Este cambio es irreversible**, seleccione **Acceso restringido** para restringir de forma permanente el acceso de los usuarios que no son administradores a este entorno.</span><span class="sxs-lookup"><span data-stu-id="0c03e-153">When you see the warning **This is a permanent change**, select **Restrict access** to permanently restrict non-admin users from this environment.</span></span> <span data-ttu-id="0c03e-154">Si no está preparado para completar este paso, seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="0c03e-154">If you're not ready to complete this step, select **Cancel**.</span></span>

   ![[<span data-ttu-id="0c03e-155">Advertencia de que restringir el acceso es un cambio irreversible</span><span class="sxs-lookup"><span data-stu-id="0c03e-155">Warning that restricting access is a permanent change</span></span>](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   ><span data-ttu-id="0c03e-156">Después de que se restrinja el acceso al entorno de Attract, los administradores podrán seguir accediendo a las páginas de exportación de datos e informes de personas.</span><span class="sxs-lookup"><span data-stu-id="0c03e-156">Admins can continue to access the data export and person report pages after you restrict access to the Attract environment.</span></span>

## <a name="export-data-from-onboard"></a><span data-ttu-id="0c03e-157">Exportar datos de Onboard</span><span class="sxs-lookup"><span data-stu-id="0c03e-157">Export data from Onboard</span></span>

<span data-ttu-id="0c03e-158">Cuando esté preparado podrá descargar plantillas, guías y datos de candidatos desde Onboard.</span><span class="sxs-lookup"><span data-stu-id="0c03e-158">When you're ready, you can download templates, guides, and candidate data from Onboard.</span></span>

1. <span data-ttu-id="0c03e-159">Ir a [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span><span class="sxs-lookup"><span data-stu-id="0c03e-159">Go to [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span></span>

2. <span data-ttu-id="0c03e-160">En **Exportación de datos**, seleccione **Solicitar una exportación de datos**.</span><span class="sxs-lookup"><span data-stu-id="0c03e-160">Under **Data export**, select **Request a data export**.</span></span> 

   ![[<span data-ttu-id="0c03e-161">Solicitar una exportación de datos desde Onboard</span><span class="sxs-lookup"><span data-stu-id="0c03e-161">Request a data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. <span data-ttu-id="0c03e-162">Cuando se abra el cuadro de mensaje **Su petición se está procesando**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0c03e-162">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="0c03e-163">La exportación de datos puede tardar hasta 20 minutos, en función de su tamaño.</span><span class="sxs-lookup"><span data-stu-id="0c03e-163">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="0c03e-164">Cuando finalice su exportación, haga clic en el botón **Descargar** situado junto a ella.</span><span class="sxs-lookup"><span data-stu-id="0c03e-164">When your export completes, select the **Download** button next to it.</span></span> 

   ![[<span data-ttu-id="0c03e-165">Descargar una exportación de datos desde Onboard</span><span class="sxs-lookup"><span data-stu-id="0c03e-165">Download data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   ><span data-ttu-id="0c03e-166">Su exportación de datos estará disponible durante siete días.</span><span class="sxs-lookup"><span data-stu-id="0c03e-166">Your data export is available for seven days.</span></span> <span data-ttu-id="0c03e-167">Al cabo de los siete días, el vínculo **Descargar** expira y tendrá que solicitar una nueva exportación si tiene que volver a descargar los datos.</span><span class="sxs-lookup"><span data-stu-id="0c03e-167">After seven days, the **Download** link expires, and you must request a new export if you need to download your data again.</span></span> <span data-ttu-id="0c03e-168">Al iniciar una nueva exportación de datos, las descargas existentes expirarán cuando se haya completado la nueva exportación.</span><span class="sxs-lookup"><span data-stu-id="0c03e-168">When you start a new data export, any existing downloads will expire after the new export succeeds.</span></span>

<span data-ttu-id="0c03e-169">La descarga es un archivo .zip que contiene:</span><span class="sxs-lookup"><span data-stu-id="0c03e-169">The download is a .zip file that contains:</span></span>

- <span data-ttu-id="0c03e-170">Una carpeta **Plantillas** que contiene sus plantillas de Onboard en formato de documento de Word.</span><span class="sxs-lookup"><span data-stu-id="0c03e-170">A **Templates** folder that contains your Onboard templates in Word document format.</span></span>

- <span data-ttu-id="0c03e-171">Una carpeta **Guías** que contiene sus guías de Onboard en formato de documento de Word.</span><span class="sxs-lookup"><span data-stu-id="0c03e-171">A **Guides** folder that contains your Onboard guides in Word document format.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c03e-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c03e-172">See also</span></span>

[<span data-ttu-id="0c03e-173">Retirada de las aplicaciones Dynamics 365 Talent: Attract y Dynamics 365 Talent: Onboard</span><span class="sxs-lookup"><span data-stu-id="0c03e-173">Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
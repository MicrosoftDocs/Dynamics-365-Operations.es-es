---
title: (ER) Importar configuraciones desde RCS
description: En este tema se proporciona información acerca de cómo un usuario puede importar una nueva versión de una configuración de ER desde RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32c9c17d8b63e4c0806559c2dcc2e11ae9825a53
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184632"
---
# <a name="er-import-configurations-from-rcs"></a><span data-ttu-id="a76c7-103">(ER) Importar configuraciones desde RCS</span><span class="sxs-lookup"><span data-stu-id="a76c7-103">(ER) Import configurations from RCS</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a76c7-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede importar una nueva versión de una configuración de informe electrónico desde Microsoft Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="a76c7-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Regulatory Configuration Services (RCS).</span></span> <span data-ttu-id="a76c7-105">En este ejemplo, seleccionará la versión de la configuración de ER que se ha configurado en una instancia de RCS y la importará en la instancia actual para la empresa de ejemplo, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa ya que las configuraciones de ER se comparten entre empresas.</span><span class="sxs-lookup"><span data-stu-id="a76c7-105">In this example, you will select the version of the ER configuration that has been configured in an RCS instance and import it into the current instance for sample company, Litware, Inc. These steps can be performed in any company because ER configurations are shared among companies.</span></span> <span data-ttu-id="a76c7-106">Para completar estos pasos, primero debe completar los pasos del tema [Creación de un proveedor de configuraciones y marcarlo como activo](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="a76c7-106">To complete these steps, you must first complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="a76c7-107">Para completar estos pasos, también debe tener acceso a una instancia de RCS que contenga al menos una configuración de ER en estado **Completado** o **Compartido**.</span><span class="sxs-lookup"><span data-stu-id="a76c7-107">To complete these steps, you must also have access to an RCS instance containing at least one ER configuration in either **Completed** or **Shared** status.</span></span>

1. <span data-ttu-id="a76c7-108">Vaya a **Administración de la organización** > **Espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="a76c7-108">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="a76c7-109">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="a76c7-109">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="a76c7-110">Si no ve a este proveedor de configuración, complete los pasos en el tema [Creación de un proveedor de configuración y marcarlo como activo](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="a76c7-110">If you don’t see this configuration provider, complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3. <span data-ttu-id="a76c7-111">Si no tiene ningún entorno de RCS aprovisionado en su empresa, haga clic en el vínculo externo **Regulatory services – Configuration** y siga las instrucciones para aprovisionar un entorno de RCS.</span><span class="sxs-lookup"><span data-stu-id="a76c7-111">If you have no RCS environment provisioned to your company, click **Regulatory services – Configuration** external link and follow the instructions to provision an RCS environment.</span></span> 
4. <span data-ttu-id="a76c7-112">Haga clic en **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="a76c7-112">Click **Electronic reporting parameters**.</span></span> 
5. <span data-ttu-id="a76c7-113">Haga clic en la pestaña **RCS**.</span><span class="sxs-lookup"><span data-stu-id="a76c7-113">Click the **RCS** tab.</span></span> 
6. <span data-ttu-id="a76c7-114">Si ya se ha aprovisionado un entorno de RCS a su empresa, utilice las direcciones URL presentadas en la página para obtener acceso.</span><span class="sxs-lookup"><span data-stu-id="a76c7-114">If RCS environment has been already provisioned to your company, use presented on the page URLs to access it.</span></span> 
7. <span data-ttu-id="a76c7-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a76c7-115">Close the page.</span></span> 

## <a name="register-a-new-er-repository"></a><span data-ttu-id="a76c7-116">Registrar un nuevo repositorio de ER.</span><span class="sxs-lookup"><span data-stu-id="a76c7-116">Register a new ER repository.</span></span> 
1. <span data-ttu-id="a76c7-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a76c7-117">In the list, mark the selected row.</span></span> 
2. <span data-ttu-id="a76c7-118">Seleccione el proveedor Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="a76c7-118">Select Litware, Inc. provider.</span></span> 
3. <span data-ttu-id="a76c7-119">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="a76c7-119">Click Repositories.</span></span> 
4. <span data-ttu-id="a76c7-120">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="a76c7-120">Click Add to open the drop dialog.</span></span> 
5. <span data-ttu-id="a76c7-121">En el campo Repositorio de configuración, escriba "RCS".</span><span class="sxs-lookup"><span data-stu-id="a76c7-121">In the Configuration repository type field, enter 'RCS'.</span></span> 
6. <span data-ttu-id="a76c7-122">Haga clic en Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="a76c7-122">Click Create repository.</span></span> 
7. <span data-ttu-id="a76c7-123">En el campo Nombre de visualización del entorno de RCS, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a76c7-123">In the RCS environment display name field, enter or select a value.</span></span> 
8. <span data-ttu-id="a76c7-124">Seleccione la instancia de RCS que desee.</span><span class="sxs-lookup"><span data-stu-id="a76c7-124">Select the desired RCS instance.</span></span> <span data-ttu-id="a76c7-125">Tenga en cuenta que puede tener varias.</span><span class="sxs-lookup"><span data-stu-id="a76c7-125">Note that you can have several of them.</span></span> 
9. <span data-ttu-id="a76c7-126">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="a76c7-126">Click OK.</span></span> 

## <a name="import-er-configurations-from-rcs-based-repository"></a><span data-ttu-id="a76c7-127">Importe las configuraciones de ER desde el repositorio basado en RCS</span><span class="sxs-lookup"><span data-stu-id="a76c7-127">Import ER configurations from RCS based repository</span></span>
1. <span data-ttu-id="a76c7-128">Haga clic en **Mostrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="a76c7-128">Click **Show filters**.</span></span> 
2. <span data-ttu-id="a76c7-129">Introduzca un valor de filtro de "RCS" en el campo **Nombre** mediante el operador de filtro **empieza por**.</span><span class="sxs-lookup"><span data-stu-id="a76c7-129">Enter a filter value of "RCS" on the **Name** field using the **begins with** filter operator.</span></span> 
3. <span data-ttu-id="a76c7-130">Cuando abra el repositorio seleccionado, en la página **Conectarse a Regulatory Configuration Services** , haga clic en el vínculo **Haga clic aquí para conectarse a Regulatory Configuration Services**.</span><span class="sxs-lookup"><span data-stu-id="a76c7-130">When you open the selected repository, on the **Connect to Regulatory Configuration Services** page, click **Click here to connect to Regulatory Configuration Services** link.</span></span> 
4. <span data-ttu-id="a76c7-131">Haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a76c7-131">Click **Open**.</span></span> 
5. <span data-ttu-id="a76c7-132">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a76c7-132">Click **Close**.</span></span> 
6. <span data-ttu-id="a76c7-133">Seleccione la versión deseada de la configuración de ER y haga clic en **Importar** para traerla a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="a76c7-133">Select the desired version of ER configuration and click **Import** to bring it in the current instance.</span></span>


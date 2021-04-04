---
title: (ER) Importar configuraciones desde RCS
description: En este tema se proporciona información acerca de cómo un usuario puede importar una nueva versión de una configuración de ER desde RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 799abeafe5f0929e6dd2f8a5f437f3c10b3b06d9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570545"
---
# <a name="er-import-configurations-from-rcs"></a><span data-ttu-id="9ff01-103">(ER) Importar configuraciones desde RCS</span><span class="sxs-lookup"><span data-stu-id="9ff01-103">(ER) Import configurations from RCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9ff01-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede importar una nueva versión de una configuración de informe electrónico desde Microsoft Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="9ff01-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Regulatory Configuration Services (RCS).</span></span> <span data-ttu-id="9ff01-105">En este ejemplo, seleccionará la versión de la configuración de ER que se ha configurado en una instancia de RCS y la importará en la instancia actual para la empresa de ejemplo, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa ya que las configuraciones de ER se comparten entre empresas.</span><span class="sxs-lookup"><span data-stu-id="9ff01-105">In this example, you will select the version of the ER configuration that has been configured in an RCS instance and import it into the current instance for sample company, Litware, Inc. These steps can be performed in any company because ER configurations are shared among companies.</span></span> <span data-ttu-id="9ff01-106">Para completar estos pasos, primero debe completar los pasos del tema [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="9ff01-106">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="9ff01-107">Para completar estos pasos, también debe tener acceso a una instancia de RCS que contenga al menos una configuración de ER en estado **Completado** o **Compartido**.</span><span class="sxs-lookup"><span data-stu-id="9ff01-107">To complete these steps, you must also have access to an RCS instance containing at least one ER configuration in either **Completed** or **Shared** status.</span></span>

1. <span data-ttu-id="9ff01-108">Vaya a **Administración de la organización** > **Espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9ff01-108">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="9ff01-109">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="9ff01-109">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="9ff01-110">Si no ve a este proveedor de configuración, complete los pasos del tema [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="9ff01-110">If you don't see this configuration provider, complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3. <span data-ttu-id="9ff01-111">Si no tiene ningún entorno de RCS aprovisionado en su empresa, seleccione el vínculo externo **Regulatory services – Configuration** y siga las instrucciones para aprovisionar un entorno de RCS.</span><span class="sxs-lookup"><span data-stu-id="9ff01-111">If you have no RCS environment provisioned to your company, select **Regulatory services – Configuration** external link and follow the instructions to provision an RCS environment.</span></span> 
4. <span data-ttu-id="9ff01-112">Seleccione **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="9ff01-112">Select **Electronic reporting parameters**.</span></span> 
5. <span data-ttu-id="9ff01-113">Seleccione la pestaña **RCS**.</span><span class="sxs-lookup"><span data-stu-id="9ff01-113">Select the **RCS** tab.</span></span> 
6. <span data-ttu-id="9ff01-114">Si ya se ha aprovisionado un entorno de RCS a su empresa, utilice las direcciones URL presentadas en la página para obtener acceso.</span><span class="sxs-lookup"><span data-stu-id="9ff01-114">If RCS environment has been already provisioned to your company, use presented on the page URLs to access it.</span></span> 
7. <span data-ttu-id="9ff01-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9ff01-115">Close the page.</span></span> 

## <a name="register-a-new-er-repository"></a><span data-ttu-id="9ff01-116">Registrar un nuevo repositorio de ER.</span><span class="sxs-lookup"><span data-stu-id="9ff01-116">Register a new ER repository.</span></span> 
1. <span data-ttu-id="9ff01-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9ff01-117">In the list, mark the selected row.</span></span> 
2. <span data-ttu-id="9ff01-118">Seleccione el proveedor Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="9ff01-118">Select Litware, Inc. provider.</span></span> 
3. <span data-ttu-id="9ff01-119">Seleccione Repositorios.</span><span class="sxs-lookup"><span data-stu-id="9ff01-119">Select Repositories.</span></span> 
4. <span data-ttu-id="9ff01-120">Seleccione Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="9ff01-120">Select Add to open the drop dialog.</span></span> 
5. <span data-ttu-id="9ff01-121">En el campo Repositorio de configuración, escriba "RCS".</span><span class="sxs-lookup"><span data-stu-id="9ff01-121">In the Configuration repository type field, enter 'RCS'.</span></span> 
6. <span data-ttu-id="9ff01-122">Seleccione Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="9ff01-122">Select Create repository.</span></span> 
7. <span data-ttu-id="9ff01-123">En el campo Nombre de visualización del entorno de RCS, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="9ff01-123">In the RCS environment display name field, enter or select a value.</span></span> 
8. <span data-ttu-id="9ff01-124">Seleccione la instancia de RCS que desee.</span><span class="sxs-lookup"><span data-stu-id="9ff01-124">Select the desired RCS instance.</span></span> <span data-ttu-id="9ff01-125">Puede tener varias.</span><span class="sxs-lookup"><span data-stu-id="9ff01-125">You can have several of them.</span></span> 
9. <span data-ttu-id="9ff01-126">Seleccione Aceptar.</span><span class="sxs-lookup"><span data-stu-id="9ff01-126">Select OK.</span></span> 

## <a name="import-er-configurations-from-rcs-based-repository"></a><span data-ttu-id="9ff01-127">Importe las configuraciones de ER desde el repositorio basado en RCS</span><span class="sxs-lookup"><span data-stu-id="9ff01-127">Import ER configurations from RCS-based repository</span></span>
1. <span data-ttu-id="9ff01-128">Seleccione **Mostrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="9ff01-128">Select **Show filters**.</span></span> 
2. <span data-ttu-id="9ff01-129">Introduzca un valor de filtro de "RCS" en el campo **Nombre** mediante el operador de filtro **empieza por**.</span><span class="sxs-lookup"><span data-stu-id="9ff01-129">Enter a filter value of "RCS" on the **Name** field using the **begins with** filter operator.</span></span> 
3. <span data-ttu-id="9ff01-130">Cuando abra el repositorio seleccionado, en la página **Conectarse a Regulatory Configuration Services** , seleccione el vínculo **Seleccione aquí para conectarse a Regulatory Configuration Services**.</span><span class="sxs-lookup"><span data-stu-id="9ff01-130">When you open the selected repository, on the **Connect to Regulatory Configuration Services** page, select **Select here to connect to Regulatory Configuration Services** link.</span></span> 
4. <span data-ttu-id="9ff01-131">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="9ff01-131">Select **Open**.</span></span> 
5. <span data-ttu-id="9ff01-132">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9ff01-132">Select **Close**.</span></span> 
6. <span data-ttu-id="9ff01-133">Seleccione la versión deseada de la configuración de ER y seleccione en **Importar** para traerla a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="9ff01-133">Select the desired version of ER configuration and select **Import** to bring it in the current instance.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
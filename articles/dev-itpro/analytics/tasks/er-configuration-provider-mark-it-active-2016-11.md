--- 
title: "Crear un proveedor de configuración y marcarlo como activo para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario administrador del sistema o con rol de desarrollador de informes electrónicos puede crear un proveedor de configuraciones para realizar informes electrónicos (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 809a1466b0f4674f503bc654175d8f94b37a6508
ms.openlocfilehash: 2dfa04f280249884af2a237807fb283059444a6c
ms.contentlocale: es-es
ms.lasthandoff: 11/02/2017

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="e6476-103">Crear un proveedor de configuración y marcarlo como activo para informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="e6476-103">Create a configuration provider and mark it as active for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e6476-104">En los pasos siguientes se explica cómo un usuario administrador del sistema o con rol de desarrollador de informes electrónicos puede crear un proveedor de configuraciones para realizar informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="e6476-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="e6476-105">Cada configuración de informes electrónicos hará referencia al proveedor como autor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="e6476-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="e6476-106">En este ejemplo, creará un proveedor de configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que los proveedores de configuración de ER se comparten entre todas las empresas.</span><span class="sxs-lookup"><span data-stu-id="e6476-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="e6476-107">Creación de un proveedor</span><span class="sxs-lookup"><span data-stu-id="e6476-107">Create a provider</span></span>
1. <span data-ttu-id="e6476-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="e6476-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="e6476-109">Haga clic en Proveedores de configuración.</span><span class="sxs-lookup"><span data-stu-id="e6476-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="e6476-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="e6476-110">Click New.</span></span>
    * <span data-ttu-id="e6476-111">Cada registro de proveedor tiene un nombre y dirección URL únicos.</span><span class="sxs-lookup"><span data-stu-id="e6476-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="e6476-112">Revise el contenido de esta página y omita este procedimiento si ya existe un registro para Litware, Inc. (http://www.litware.com).</span><span class="sxs-lookup"><span data-stu-id="e6476-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="e6476-113">En el campo Nombre, especifique "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="e6476-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="e6476-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="e6476-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="e6476-115">En el campo Dirección de Internet, especifique "http://www.litware.com".</span><span class="sxs-lookup"><span data-stu-id="e6476-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * <span data-ttu-id="e6476-116">http://www.litware.com</span><span class="sxs-lookup"><span data-stu-id="e6476-116">http://www.litware.com</span></span>  
6. <span data-ttu-id="e6476-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e6476-117">Click Save.</span></span>
7. <span data-ttu-id="e6476-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e6476-118">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="e6476-119">Selección como proveedor activo</span><span class="sxs-lookup"><span data-stu-id="e6476-119">Select as an active provider</span></span>
1. <span data-ttu-id="e6476-120">Seleccione el proveedor Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="e6476-120">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="e6476-121">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="e6476-121">Click Set active.</span></span>



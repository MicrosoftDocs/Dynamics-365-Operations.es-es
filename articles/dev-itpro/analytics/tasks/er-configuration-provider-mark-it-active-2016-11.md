---
title: Crear proveedores de configuración y marcarlos como activos
description: En los pasos siguientes se explica cómo un usuario administrador del sistema o con rol de desarrollador de informes electrónicos puede crear un proveedor de configuraciones para realizar informes electrónicos (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13a27c2fec2a2b226e9ae8d5b8f9a61e8b79ceb0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544918"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="7150b-103">Crear proveedores de configuración y marcarlos como activos</span><span class="sxs-lookup"><span data-stu-id="7150b-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7150b-104">En los pasos siguientes se explica cómo un usuario administrador del sistema o con rol de desarrollador de informes electrónicos puede crear un proveedor de configuraciones para realizar informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="7150b-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="7150b-105">Cada configuración de informes electrónicos hará referencia al proveedor como autor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="7150b-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="7150b-106">En este ejemplo, creará un proveedor de configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que los proveedores de configuración de ER se comparten entre todas las empresas.</span><span class="sxs-lookup"><span data-stu-id="7150b-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="7150b-107">Creación de un proveedor</span><span class="sxs-lookup"><span data-stu-id="7150b-107">Create a provider</span></span>
1. <span data-ttu-id="7150b-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="7150b-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="7150b-109">Haga clic en Proveedores de configuración.</span><span class="sxs-lookup"><span data-stu-id="7150b-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="7150b-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7150b-110">Click New.</span></span>
    * <span data-ttu-id="7150b-111">Cada registro de proveedor tiene un nombre y dirección URL únicos.</span><span class="sxs-lookup"><span data-stu-id="7150b-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="7150b-112">Revise el contenido de esta página y omita este procedimiento si ya existe un registro para Litware, Inc. (http://www.litware.com).</span><span class="sxs-lookup"><span data-stu-id="7150b-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="7150b-113">En el campo Nombre, especifique "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="7150b-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="7150b-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7150b-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="7150b-115">En el campo Dirección de Internet, escriba "http://www.litware.com".</span><span class="sxs-lookup"><span data-stu-id="7150b-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * http://www.litware.com  
6. <span data-ttu-id="7150b-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7150b-116">Click Save.</span></span>
7. <span data-ttu-id="7150b-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7150b-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="7150b-118">Selección como proveedor activo</span><span class="sxs-lookup"><span data-stu-id="7150b-118">Select as an active provider</span></span>
1. <span data-ttu-id="7150b-119">Seleccione el proveedor Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7150b-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="7150b-120">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="7150b-120">Click Set active.</span></span>


---
title: Crear proveedores de configuración y marcarlos como activos
description: En este tema se explica cómo un usuario administrador del sistema o con rol de desarrollador de informes electrónicos puede crear un proveedor de configuraciones.
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11ff1d531b0467cf75ec98b092fe6010f4fa95c0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569796"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="bbc1b-103">Crear proveedores de configuración y marcarlos como activos</span><span class="sxs-lookup"><span data-stu-id="bbc1b-103">Create configuration providers and mark them as active</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bbc1b-104">En este tema se explica cómo un usuario administrador del sistema o con rol de desarrollador de informes electrónicos puede crear un proveedor de configuraciones para realizar informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="bbc1b-104">This topic explains how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="bbc1b-105">Cada configuración de informes electrónicos hará referencia al proveedor como autor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="bbc1b-106">En este ejemplo, creará un proveedor de configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que los proveedores de configuración de ER se comparten entre todas las empresas.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>

## <a name="create-a-provider"></a><span data-ttu-id="bbc1b-107">Creación de un proveedor</span><span class="sxs-lookup"><span data-stu-id="bbc1b-107">Create a provider</span></span>
1. <span data-ttu-id="bbc1b-108">Vaya al **panel de navegación** en la esquina superior izquierda y seleccione **Administración de la organización**.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-108">Go to the **navigation pane** in the upper left corner and select **Organization administration**.</span></span>
2. <span data-ttu-id="bbc1b-109">Vaya a **Espacios de trabajo > Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-109">Go to **Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="bbc1b-110">Vaya a **Vínculos relacionados > Proveedores de configuración**.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-110">Go to **Related links > Configuration providers**.</span></span>
4. <span data-ttu-id="bbc1b-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-111">Select **New**.</span></span>
    - <span data-ttu-id="bbc1b-112">Cada registro de proveedor tiene un nombre y dirección URL únicos.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-112">A provider record has a unique name and URL.</span></span> <span data-ttu-id="bbc1b-113">Revise el contenido de esta página y omita este procedimiento si ya existe un registro para Litware, Inc. (https://www.litware.com).</span><span class="sxs-lookup"><span data-stu-id="bbc1b-113">Review the content of this page and skip this procedure if a record for Litware, Inc. (https://www.litware.com) already exists.</span></span>  
5. <span data-ttu-id="bbc1b-114">En el campo Nombre, escriba `Litware, Inc.`.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-114">In the Name field, type `Litware, Inc.`.</span></span>
6. <span data-ttu-id="bbc1b-115">En el campo Dirección de Internet, escriba `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-115">In the Internet address field, type `https://www.litware.com`.</span></span>
7. <span data-ttu-id="bbc1b-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-116">Select **Save**.</span></span>
8. <span data-ttu-id="bbc1b-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="bbc1b-118">Selección como proveedor activo</span><span class="sxs-lookup"><span data-stu-id="bbc1b-118">Select as an active provider</span></span>
1. <span data-ttu-id="bbc1b-119">Seleccione el proveedor Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="bbc1b-120">Seleccione **Definir como activo**.</span><span class="sxs-lookup"><span data-stu-id="bbc1b-120">Select **Set active**.</span></span>

![Página del espacio de trabajo de los informes electrónicos](../media/GER-Task-ActiveProvider-1.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
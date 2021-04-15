---
title: Importar usuarios de Azure Active Directory
description: Este procedimiento se puede utilizar por administradores del sistema para importar manualmente usuarios seleccionados o para importar a un gran número de usuarios desde Azure Active Directory.
author: peakerbl
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9f03ae7197790c1aac6ebf3cb94ff7963b1291e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745798"
---
# <a name="import-users-from-azure-active-directory"></a><span data-ttu-id="7909e-103">Importar usuarios de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7909e-103">Import users from Azure Active Directory</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a><span data-ttu-id="7909e-104">Importar usuarios seleccionados</span><span class="sxs-lookup"><span data-stu-id="7909e-104">Import select users</span></span>

<span data-ttu-id="7909e-105">Este procedimiento se puede utilizar por administradores del sistema para importar usuarios seleccionados desde Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7909e-105">This procedure can be used by system administrators to import select users from Azure Active Directory (Azure AD).</span></span>

1. <span data-ttu-id="7909e-106">El usuario se importará con la empresa de la sesión actual como empresa predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7909e-106">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="7909e-107">Cambie la compañía actual si corresponde antes de importar usuarios.</span><span class="sxs-lookup"><span data-stu-id="7909e-107">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="7909e-108">Vaya a **Administración del sistema > Usuarios > Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="7909e-108">Go to **System administration > Users > User** s.</span></span>
3. <span data-ttu-id="7909e-109">Haga clic en **Importar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="7909e-109">Click **Import users**.</span></span>
4. <span data-ttu-id="7909e-110">Seleccione los usuarios que se deben importar y seleccione **Importar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="7909e-110">Select the users that should be imported and select **Import users**.</span></span>

<span data-ttu-id="7909e-111">Una vez completada la importación, será necesario asignar roles a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7909e-111">After import is completed it will be required to assign roles to users.</span></span>

## <a name="import-users-in-bulk"></a><span data-ttu-id="7909e-112">Importar usuarios en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="7909e-112">Import users in bulk</span></span>

<span data-ttu-id="7909e-113">Este procedimiento se puede utilizar por administradores del sistema para importar a un gran número de usuarios desde Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7909e-113">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>
<span data-ttu-id="7909e-114">Tenga en cuenta que no es posible seleccionar usuarios cuando se utiliza la opción de importación por lotes.</span><span class="sxs-lookup"><span data-stu-id="7909e-114">Note that it is not possible to select users when using the Batch import option.</span></span>

## <a name="run-the-import-as-a-batch-job"></a><span data-ttu-id="7909e-115">Ejecute la importación como un trabajo por lotes</span><span class="sxs-lookup"><span data-stu-id="7909e-115">Run the import as a batch job</span></span>
1. <span data-ttu-id="7909e-116">El usuario se importará con la empresa de la sesión actual como empresa predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7909e-116">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="7909e-117">Cambie la compañía actual si corresponde antes de importar usuarios.</span><span class="sxs-lookup"><span data-stu-id="7909e-117">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="7909e-118">Vaya a **Administración del sistema > Usuarios > Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="7909e-118">Go to **System administration > Users > Users**.</span></span>
3. <span data-ttu-id="7909e-119">Haga clic en **Importación por lotes**.</span><span class="sxs-lookup"><span data-stu-id="7909e-119">Click **Batch import**.</span></span>
4. <span data-ttu-id="7909e-120">Expanda la sección **Ejecutar en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="7909e-120">Expand the **Run in the background** section.</span></span>
4. <span data-ttu-id="7909e-121">Seleccione **Sí** en el campo **Procesamiento por lotes**.</span><span class="sxs-lookup"><span data-stu-id="7909e-121">Select **Yes** in the **Batch processing** field.</span></span>
6. <span data-ttu-id="7909e-122">En el campo **Grupo de lotes**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7909e-122">In the **Batch group** field, enter or select a value.</span></span> <span data-ttu-id="7909e-123">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="7909e-123">This is an optional step.</span></span>  
7. <span data-ttu-id="7909e-124">Seleccione **Sí** en el campo **Privado**.</span><span class="sxs-lookup"><span data-stu-id="7909e-124">Select **Yes** in the **Private** field.</span></span> <span data-ttu-id="7909e-125">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="7909e-125">This is an optional step.</span></span>  
8. <span data-ttu-id="7909e-126">Seleccione **Sí** en el campo **Trabajo crítico**.</span><span class="sxs-lookup"><span data-stu-id="7909e-126">Select **Yes** in the **Critical job** field.</span></span> <span data-ttu-id="7909e-127">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="7909e-127">This is an optional step.</span></span>  
9. <span data-ttu-id="7909e-128">En el campo **Categoría de supervisión**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="7909e-128">In the **Monitoring category** field, select an option.</span></span>
10. <span data-ttu-id="7909e-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7909e-129">Click **OK**.</span></span>

<span data-ttu-id="7909e-130">Una vez completada la importación, será necesario asignar roles a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7909e-130">After import is completed, it will be required to assign roles to users.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="7909e-131">Ejecutar un entorno de espacio aislado</span><span class="sxs-lookup"><span data-stu-id="7909e-131">Run in a sandbox environment</span></span>
1. <span data-ttu-id="7909e-132">Seleccione **Importación por lotes**.</span><span class="sxs-lookup"><span data-stu-id="7909e-132">Select **Batch import**.</span></span>
2. <span data-ttu-id="7909e-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7909e-133">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
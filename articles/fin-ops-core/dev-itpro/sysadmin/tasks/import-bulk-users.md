---
title: Importar usuarios de Azure Active Directory
description: Este procedimiento se puede utilizar por administradores del sistema para importar manualmente usuarios seleccionados o para importar a un gran número de usuarios desde Azure Active Directory.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b6666310309817ff30ccb3902721880b829ee0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679823"
---
# <a name="import-users-from-azure-active-directory"></a><span data-ttu-id="13b6d-103">Importar usuarios de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="13b6d-103">Import users from Azure Active Directory</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a><span data-ttu-id="13b6d-104">Importar usuarios seleccionados</span><span class="sxs-lookup"><span data-stu-id="13b6d-104">Import select users</span></span>

<span data-ttu-id="13b6d-105">Este procedimiento se puede utilizar por administradores del sistema para importar usuarios seleccionados desde Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="13b6d-105">This procedure can be used by system administrators to import select users from Azure Active Directory (Azure AD).</span></span>

1. <span data-ttu-id="13b6d-106">El usuario se importará con la empresa de la sesión actual como empresa predeterminada.</span><span class="sxs-lookup"><span data-stu-id="13b6d-106">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="13b6d-107">Cambie la compañía actual si corresponde antes de importar usuarios.</span><span class="sxs-lookup"><span data-stu-id="13b6d-107">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="13b6d-108">Vaya a **Administración del sistema > Usuarios > Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-108">Go to **System administration > Users > User** s.</span></span>
3. <span data-ttu-id="13b6d-109">Haga clic en **Importar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-109">Click **Import users**.</span></span>
4. <span data-ttu-id="13b6d-110">Seleccione los usuarios que se deben importar y seleccione **Importar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-110">Select the users that should be imported and select **Import users**.</span></span>

<span data-ttu-id="13b6d-111">Una vez completada la importación, será necesario asignar roles a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="13b6d-111">After import is completed it will be required to assign roles to users.</span></span>

## <a name="import-users-in-bulk"></a><span data-ttu-id="13b6d-112">Importar usuarios en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="13b6d-112">Import users in bulk</span></span>

<span data-ttu-id="13b6d-113">Este procedimiento se puede utilizar por administradores del sistema para importar a un gran número de usuarios desde Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="13b6d-113">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>
<span data-ttu-id="13b6d-114">Tenga en cuenta que no es posible seleccionar usuarios cuando se utiliza la opción de importación por lotes.</span><span class="sxs-lookup"><span data-stu-id="13b6d-114">Note that it is not possible to select users when using the Batch import option.</span></span>

## <a name="run-the-import-as-a-batch-job"></a><span data-ttu-id="13b6d-115">Ejecute la importación como un trabajo por lotes</span><span class="sxs-lookup"><span data-stu-id="13b6d-115">Run the import as a batch job</span></span>
1. <span data-ttu-id="13b6d-116">El usuario se importará con la empresa de la sesión actual como empresa predeterminada.</span><span class="sxs-lookup"><span data-stu-id="13b6d-116">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="13b6d-117">Cambie la compañía actual si corresponde antes de importar usuarios.</span><span class="sxs-lookup"><span data-stu-id="13b6d-117">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="13b6d-118">Vaya a **Administración del sistema > Usuarios > Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-118">Go to **System administration > Users > Users**.</span></span>
3. <span data-ttu-id="13b6d-119">Haga clic en **Importación por lotes**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-119">Click **Batch import**.</span></span>
4. <span data-ttu-id="13b6d-120">Expanda la sección **Ejecutar en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-120">Expand the **Run in the background** section.</span></span>
4. <span data-ttu-id="13b6d-121">Seleccione \*\*Sí en el campo **Procesamiento por lotes**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-121">Select \*\*Yes in the **Batch processing** field.</span></span>
6. <span data-ttu-id="13b6d-122">En el campo **Grupo de lotes**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="13b6d-122">In the **Batch group** field, enter or select a value.</span></span> <span data-ttu-id="13b6d-123">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="13b6d-123">This is an optional step.</span></span>  
7. <span data-ttu-id="13b6d-124">Seleccione **Sí** en el campo **Privado**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-124">Select **Yes** in the **Private** field.</span></span> <span data-ttu-id="13b6d-125">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="13b6d-125">This is an optional step.</span></span>  
8. <span data-ttu-id="13b6d-126">Seleccione **Sí** en el campo **Trabajo crítico**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-126">Select **Yes** in the **Critical job** field.</span></span> <span data-ttu-id="13b6d-127">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="13b6d-127">bThis is an optional step.</span></span>  
9. <span data-ttu-id="13b6d-128">En el campo \*\*Categoría de supervisión, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="13b6d-128">In the \*\*Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="13b6d-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-129">Click **OK**.</span></span>

<span data-ttu-id="13b6d-130">Una vez completada la importación, será necesario asignar roles a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="13b6d-130">After import is completed, it will be required to assign roles to users.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="13b6d-131">Ejecutar un entorno de espacio aislado</span><span class="sxs-lookup"><span data-stu-id="13b6d-131">Run in a sandbox environment</span></span>
1. <span data-ttu-id="13b6d-132">Seleccione **Importación por lotes**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-132">Select **Batch import**.</span></span>
2. <span data-ttu-id="13b6d-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="13b6d-133">Select **OK**.</span></span>

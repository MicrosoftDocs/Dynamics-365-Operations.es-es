---
title: Configurar grupos de activos fijos
description: En ese tema se explica cómo crear un nuevo grupo de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 246502f66c0cfcd4b4ed3c4b9f2ae616e71a1c50
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186886"
---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="abb1a-103">Configurar grupos de activos fijos</span><span class="sxs-lookup"><span data-stu-id="abb1a-103">Set up fixed asset groups</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="abb1a-104">En ese tema se explica cómo crear un nuevo grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="abb1a-104">This topic explains how to create a new fixed asset group.</span></span> <span data-ttu-id="abb1a-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="abb1a-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="abb1a-106">En el panel de navegación, vaya a **Módulos > Activos fijos > Configuración > Grupos de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="abb1a-106">In the navigation pane, go to **Modules > Fixed assets > Setup > Fixed asset groups**.</span></span>
2. <span data-ttu-id="abb1a-107">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="abb1a-107">Select **New**.</span></span>
3. <span data-ttu-id="abb1a-108">En el campo **Grupo de activos fijos**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="abb1a-108">In the **Fixed asset group** field, type a value.</span></span>
4. <span data-ttu-id="abb1a-109">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="abb1a-109">In the **Name** field, type a value.</span></span> <span data-ttu-id="abb1a-110">Las opciones Enumerar automáticamente los activos fijos y Código de secuencia numérica del grupo de **Activos fijos** reemplazarán la configuración de los parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="abb1a-110">Autonumber fixed assets and Number sequence code on the **Fixed asset** group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="abb1a-111">Puede cambiarlo aquí si los activos de este grupo de activos fijos tendrán una numeración diferente a la de otros grupos.</span><span class="sxs-lookup"><span data-stu-id="abb1a-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="abb1a-112">Seleccione **Libros**.</span><span class="sxs-lookup"><span data-stu-id="abb1a-112">Select **Books**.</span></span>
6. <span data-ttu-id="abb1a-113">En el campo **Libro**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="abb1a-113">In the **Book** field, enter or select a value.</span></span> <span data-ttu-id="abb1a-114">El campo **Calcular depreciación** se establece en **Sí** para que el libro del activo se incluya en las propuestas de depreciación.</span><span class="sxs-lookup"><span data-stu-id="abb1a-114">The **Calculate depreciation** field is set to **Yes**, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="abb1a-115">Si **Calcular la depreciación** se establece en **No**, el activo no se depreciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="abb1a-115">If **Calculate depreciation** is set to **No**, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="abb1a-116">Establezca el tiempo de vida del activo, en años.</span><span class="sxs-lookup"><span data-stu-id="abb1a-116">Set the Service life of the asset, in years.</span></span> <span data-ttu-id="abb1a-117">Tenga en cuenta que el valor del campo **Períodos de depreciación** se calcula después de definir el tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="abb1a-117">Note that the **Depreciation periods** field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="abb1a-118">En el campo **Convención de amortizaciones**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="abb1a-118">In the **Depreciation convention** field, select an option.</span></span>
9. <span data-ttu-id="abb1a-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="abb1a-119">Close the page.</span></span>


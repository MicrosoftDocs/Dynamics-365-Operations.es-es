---
title: Configurar grupos de activos fijos
description: Este procedimiento muestra cómo crear un nuevo grupo de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: e8f52b73c07aad1047d6e6e7caf80daecc9c26e7
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839794"
---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="a4194-103">Configurar grupos de activos fijos</span><span class="sxs-lookup"><span data-stu-id="a4194-103">Set up fixed asset groups</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a4194-104">Este procedimiento muestra cómo crear un nuevo grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="a4194-104">This procedure shows how to create a new fixed asset group.</span></span> <span data-ttu-id="a4194-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="a4194-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="a4194-106">Vaya a Activos fijos > Configuración > Grupos de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="a4194-106">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="a4194-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a4194-107">Click New.</span></span>
3. <span data-ttu-id="a4194-108">En el campo Grupo de activos fijos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a4194-108">In the Fixed asset group field, type a value.</span></span>
4. <span data-ttu-id="a4194-109">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a4194-109">In the Name field, type a value.</span></span>
    * <span data-ttu-id="a4194-110">Las opciones Enumerar automáticamente los activos fijos y Código de secuencia numérica del grupo de activos fijos reemplazarán la configuración de los parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="a4194-110">Autonumber fixed assets and Number sequence code on the Fixed asset group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="a4194-111">Puede cambiarlo aquí si los activos de este grupo de activos fijos tendrán una numeración diferente a la de otros grupos.</span><span class="sxs-lookup"><span data-stu-id="a4194-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="a4194-112">Haga clic en Libros.</span><span class="sxs-lookup"><span data-stu-id="a4194-112">Click Books.</span></span>
6. <span data-ttu-id="a4194-113">En el campo Libro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a4194-113">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="a4194-114">El campo Calcular depreciación se establece en Sí para que el libro del activo se incluya en las propuestas de depreciación.</span><span class="sxs-lookup"><span data-stu-id="a4194-114">The Calculate depreciation field is set to Yes, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="a4194-115">Si Calcular la depreciación se establece en No, el activo no se depreciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a4194-115">If Calculate depreciation is set to No, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="a4194-116">Establezca el tiempo de vida del activo, en años.</span><span class="sxs-lookup"><span data-stu-id="a4194-116">Set the Service life of the asset, in years.</span></span>
    * <span data-ttu-id="a4194-117">Tenga en cuenta que el valor del campo Períodos de depreciación se calcula después de definir el tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="a4194-117">Note that the Depreciation periods field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="a4194-118">En el campo Convención de amortizaciones, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="a4194-118">In the Depreciation convention field, select an option.</span></span>
9. <span data-ttu-id="a4194-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a4194-119">Close the page.</span></span>


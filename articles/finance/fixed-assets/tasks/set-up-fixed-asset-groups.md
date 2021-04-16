---
title: Configurar grupos de activos fijos
description: En ese tema se explica cómo crear un nuevo grupo de activos fijos.
author: saraschi2
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c1b97193f09cfbb943522ca7af6bace9a14d9cf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819563"
---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="b6988-103">Configurar grupos de activos fijos</span><span class="sxs-lookup"><span data-stu-id="b6988-103">Set up fixed asset groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b6988-104">En ese tema se explica cómo crear un nuevo grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="b6988-104">This topic explains how to create a new fixed asset group.</span></span> <span data-ttu-id="b6988-105">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="b6988-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="b6988-106">En el panel de navegación, vaya a **Módulos > Activos fijos > Configuración > Grupos de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="b6988-106">In the navigation pane, go to **Modules > Fixed assets > Setup > Fixed asset groups**.</span></span>
2. <span data-ttu-id="b6988-107">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b6988-107">Select **New**.</span></span>
3. <span data-ttu-id="b6988-108">En el campo **Grupo de activos fijos**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b6988-108">In the **Fixed asset group** field, type a value.</span></span>
4. <span data-ttu-id="b6988-109">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b6988-109">In the **Name** field, type a value.</span></span> <span data-ttu-id="b6988-110">Las opciones Enumerar automáticamente los activos fijos y Código de secuencia numérica del grupo de **Activos fijos** reemplazarán la configuración de los parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="b6988-110">Autonumber fixed assets and Number sequence code on the **Fixed asset** group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="b6988-111">Puede cambiarlo aquí si los activos de este grupo de activos fijos tendrán una numeración diferente a la de otros grupos.</span><span class="sxs-lookup"><span data-stu-id="b6988-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="b6988-112">Seleccione **Libros**.</span><span class="sxs-lookup"><span data-stu-id="b6988-112">Select **Books**.</span></span>
6. <span data-ttu-id="b6988-113">En el campo **Libro**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b6988-113">In the **Book** field, enter or select a value.</span></span> <span data-ttu-id="b6988-114">El campo **Calcular depreciación** se establece en **Sí** para que el libro del activo se incluya en las propuestas de depreciación.</span><span class="sxs-lookup"><span data-stu-id="b6988-114">The **Calculate depreciation** field is set to **Yes**, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="b6988-115">Si **Calcular la depreciación** se establece en **No**, el activo no se depreciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b6988-115">If **Calculate depreciation** is set to **No**, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="b6988-116">Establezca el tiempo de vida del activo, en años.</span><span class="sxs-lookup"><span data-stu-id="b6988-116">Set the Service life of the asset, in years.</span></span> <span data-ttu-id="b6988-117">Tenga en cuenta que el valor del campo **Períodos de depreciación** se calcula después de definir el tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="b6988-117">Note that the **Depreciation periods** field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="b6988-118">En el campo **Convención de amortizaciones**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="b6988-118">In the **Depreciation convention** field, select an option.</span></span>
9. <span data-ttu-id="b6988-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b6988-119">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
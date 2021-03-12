---
title: Configuración de las restricciones de transporte para un artículo
description: Este procedimiento configurará una restricción de transporte para evitar que un artículo seleccionado se transporte a través de un centro seleccionado.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSConstraint, InventLocationIdLookup, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 244cf7337ec856f7517a3c0c3e055a90ab65b13f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973944"
---
# <a name="set-up-transportation-constraints-for-an-item"></a><span data-ttu-id="8374a-103">Configuración de las restricciones de transporte para un artículo</span><span class="sxs-lookup"><span data-stu-id="8374a-103">Set up transportation constraints for an item</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8374a-104">Este procedimiento configurará una restricción de transporte para evitar que un artículo seleccionado se transporte a través de un centro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8374a-104">This procedure will set up a transportation constraint to prevent a selected item from being transported through a selected hub.</span></span> <span data-ttu-id="8374a-105">Esta tarea normalmente se llevaría a cabo por un coordinador de transporte.</span><span class="sxs-lookup"><span data-stu-id="8374a-105">This task would typically be carried out by a Transportation coordinator.</span></span> <span data-ttu-id="8374a-106">Puede utilizar este procedimiento en la empresa de demostración USMF o en sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="8374a-106">You can use this procedure in the USMF demo data company or on your own data.</span></span>


## <a name="create-an-item-constaint"></a><span data-ttu-id="8374a-107">Crear una restricción de artículo</span><span class="sxs-lookup"><span data-stu-id="8374a-107">Create an item constaint</span></span>
1. <span data-ttu-id="8374a-108">Vaya a Restricciones.</span><span class="sxs-lookup"><span data-stu-id="8374a-108">Go to Constraints.</span></span>
2. <span data-ttu-id="8374a-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8374a-109">Click New.</span></span>
3. <span data-ttu-id="8374a-110">En el campo Restricción de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8374a-110">In the Item constraint field, type a value.</span></span>
4. <span data-ttu-id="8374a-111">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8374a-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8374a-112">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8374a-112">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="8374a-113">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8374a-113">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="8374a-114">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8374a-114">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="8374a-115">En el campo Centro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8374a-115">In the Hub field, enter or select a value.</span></span>
9. <span data-ttu-id="8374a-116">En el campo Acción de restricción, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="8374a-116">In the Constraint action field, select an option.</span></span>
10. <span data-ttu-id="8374a-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="8374a-117">Click Save.</span></span>
11. <span data-ttu-id="8374a-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8374a-118">Close the page.</span></span>


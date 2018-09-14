--- 
title: Crear un nuevo producto
description: "Esta tarea muestra cómo crear un nuevo producto compartido."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 7a603d89749242a4c6039ab83da286ec6ab727d8
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-new-product"></a><span data-ttu-id="195de-103">Crear un nuevo producto</span><span class="sxs-lookup"><span data-stu-id="195de-103">Create a new product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="195de-104">Esta tarea muestra cómo crear un nuevo producto compartido.</span><span class="sxs-lookup"><span data-stu-id="195de-104">This task shows how to create a new shared product.</span></span> <span data-ttu-id="195de-105">Normalmente se lleva a cabo por un diseñador de producto.</span><span class="sxs-lookup"><span data-stu-id="195de-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="195de-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="195de-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="195de-107">Vaya a Gestión de información de productos > Productos > Productos.</span><span class="sxs-lookup"><span data-stu-id="195de-107">Go to Product information management > Products > Products.</span></span>

## <a name="create-a-product"></a><span data-ttu-id="195de-108">Crear un producto</span><span class="sxs-lookup"><span data-stu-id="195de-108">Create a product</span></span>
1. <span data-ttu-id="195de-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="195de-109">Click New.</span></span>
2. <span data-ttu-id="195de-110">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="195de-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="195de-111">Si no se ha configurado una secuencia numérica para el número de producto, debe especificarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="195de-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
3. <span data-ttu-id="195de-112">En el campo Nombre de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="195de-112">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="195de-113">El nombre del producto se establece de forma predeterminada como el nombre de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="195de-113">The product name defaults to the search name.</span></span> <span data-ttu-id="195de-114">Si es necesario, se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="195de-114">You can change this if needed.</span></span>  
4. <span data-ttu-id="195de-115">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="195de-115">Click OK.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="195de-116">Configurar grupos de dimensiones</span><span class="sxs-lookup"><span data-stu-id="195de-116">Set up dimension groups</span></span>
1. <span data-ttu-id="195de-117">Haga clic en Grupos de dimensiones para abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="195de-117">Click Dimension groups to open the drop dialog.</span></span>
2. <span data-ttu-id="195de-118">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="195de-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="195de-119">El grupo de dimensiones de almacenamiento determina qué dimensiones de almacenamiento debe especificar en cada transacción para el producto y cómo se realizará su seguimiento en el inventario.</span><span class="sxs-lookup"><span data-stu-id="195de-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="195de-120">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="195de-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="195de-121">El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento debe especificar para cada transacción para el producto y cómo se controlará en el inventario.</span><span class="sxs-lookup"><span data-stu-id="195de-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="195de-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="195de-122">Click OK.</span></span>



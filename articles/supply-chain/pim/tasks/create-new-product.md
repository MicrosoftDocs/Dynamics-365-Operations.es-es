---
title: Crear un nuevo producto
description: En este tema se describe cómo crear un producto compartido nuevo.
author: ShylaThompson
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6d33a13920e1881cdc69ad7c100180d3b3b441d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820043"
---
# <a name="create-a-new-product"></a><span data-ttu-id="3274d-103">Crear un nuevo producto</span><span class="sxs-lookup"><span data-stu-id="3274d-103">Create a new product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3274d-104">En este tema se describe cómo crear un producto compartido nuevo.</span><span class="sxs-lookup"><span data-stu-id="3274d-104">This topic describes how to create a new shared product.</span></span> <span data-ttu-id="3274d-105">Normalmente se lleva a cabo por un diseñador de producto.</span><span class="sxs-lookup"><span data-stu-id="3274d-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="3274d-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="3274d-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-product"></a><span data-ttu-id="3274d-107">Crear un producto</span><span class="sxs-lookup"><span data-stu-id="3274d-107">Create a product</span></span>
1. <span data-ttu-id="3274d-108">En el panel de exploración, vaya a **Módulos > Gestión de información de productos > Productos > Productos**.</span><span class="sxs-lookup"><span data-stu-id="3274d-108">In the Navigation pane, go to **Modules > Product information management > Products > Products**.</span></span>
2. <span data-ttu-id="3274d-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3274d-109">Select **New**.</span></span>
3. <span data-ttu-id="3274d-110">En el campo **Número de producto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3274d-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="3274d-111">Si no se ha configurado una secuencia numérica para el número de producto, debe especificarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="3274d-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
4. <span data-ttu-id="3274d-112">En el campo **Nombre de producto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3274d-112">In the **Product name** field, type a value.</span></span> <span data-ttu-id="3274d-113">El nombre del producto se establece de forma predeterminada como el nombre de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3274d-113">The product name defaults to the search name.</span></span> <span data-ttu-id="3274d-114">Si es necesario, se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="3274d-114">You can change this if needed.</span></span>  
5. <span data-ttu-id="3274d-115">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3274d-115">Select **OK**.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="3274d-116">Configurar grupos de dimensiones</span><span class="sxs-lookup"><span data-stu-id="3274d-116">Set up dimension groups</span></span>
1. <span data-ttu-id="3274d-117">Seleccione **Grupos de dimensiones** para abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3274d-117">Select **Dimension groups** to open the drop dialog.</span></span>
2. <span data-ttu-id="3274d-118">En el campo **Grupo de dimensiones de almacenamiento**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3274d-118">In the **Storage dimension group** field, enter or select a value.</span></span> <span data-ttu-id="3274d-119">El grupo de dimensiones de almacenamiento determina qué dimensiones de almacenamiento debe especificar en cada transacción para el producto y cómo se realizará su seguimiento en el inventario.</span><span class="sxs-lookup"><span data-stu-id="3274d-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="3274d-120">En el campo **Grupo de dimensiones de seguimiento**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3274d-120">In the **Tracking dimension group** field, enter or select a value.</span></span> <span data-ttu-id="3274d-121">El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento debe especificar para cada transacción para el producto y cómo se controlará en el inventario.</span><span class="sxs-lookup"><span data-stu-id="3274d-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="3274d-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3274d-122">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
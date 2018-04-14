---
title: "Recepción de matrícula de entidad de almacén mixta"
description: "Este tema describe cómo usar la recepción de matrícula mixta para registrar y para crear trabajo para varios artículos con un dispositivo móvil."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 47587664c0c3ed553c724920168782a64fdaf9de
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="mixed-license-plate-receiving"></a><span data-ttu-id="fa935-103">Recepción de matrícula de entidad de almacén mixta</span><span class="sxs-lookup"><span data-stu-id="fa935-103">Mixed license plate receiving</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="fa935-104">La recepción de matrículas mixtas le permite generar una matrícula que consiste en varios artículos antes de registrar y crear un trabajo de ubicación.</span><span class="sxs-lookup"><span data-stu-id="fa935-104">Mixed license plate receiving allows you to build a license plate consisting of multiple items before you register and create put-away work.</span></span> 

<span data-ttu-id="fa935-105">Una matrícula que consiste de varios artículos no tiene que dividirse en el muelle recepción para que pueda registrar cada artículo.</span><span class="sxs-lookup"><span data-stu-id="fa935-105">A license plate that consists of multiple items does not have to be split at the receiving dock for you to register each item.</span></span> 

<span data-ttu-id="fa935-106">Al usar un flujo relacionado con artículos para identificar las líneas del documento de origen, puede digitalizar códigos de barras en el control de artículos.</span><span class="sxs-lookup"><span data-stu-id="fa935-106">When using an item-related flow to identify the source document lines, you can scan bar codes on the item control.</span></span> <span data-ttu-id="fa935-107">Si el código de barras tiene una cantidad y una unidad de medida (UOM) configurada en él, el artículo y la cantidad automáticamente se agregarán a la matrícula mixta y que volverá a la pantalla para escanear otro artículo.</span><span class="sxs-lookup"><span data-stu-id="fa935-107">If the bar code has a quantity and a unit of measure (UOM) configured on it, the item and quantity will automatically be added to the mixed license plate, and you will be returned to the screen to scan another item.</span></span> <span data-ttu-id="fa935-108">Esto le permite digitalizar rápidamente todos los artículos sin tener que crear una confirmación en cada paso.</span><span class="sxs-lookup"><span data-stu-id="fa935-108">This allows you to quickly scan all the items without having to make a confirmation at each step.</span></span> 

<span data-ttu-id="fa935-109">En el flujo para la recepción de matrículas mixtas, puede mostrar la lista de artículos que ya se han digitalizado para la matrícula y a partir de ahí puede modificar o corregir la cantidad de un artículo.</span><span class="sxs-lookup"><span data-stu-id="fa935-109">In the flow for mixed license plate receiving, you can display the list of items that are already scanned to the license plate and from here you can modify or correct the quantity of an item.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="fa935-110">Dónde se aplica</span><span class="sxs-lookup"><span data-stu-id="fa935-110">Where it applies</span></span>

<span data-ttu-id="fa935-111">La recepción de matrículas es un dispositivo móvil que recibe flujo para registrar y crear trabajo para varios artículos o líneas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="fa935-111">Mixed license plate receiving is a mobile device receiving flow to register and create work for multiple lines/items at the same time.</span></span> <span data-ttu-id="fa935-112">Esto resulta útil si recibe matrículas de entrada con varios artículos.</span><span class="sxs-lookup"><span data-stu-id="fa935-112">This is useful if you receive inbound license plates with multiple items.</span></span> 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a><span data-ttu-id="fa935-113">Cómo configurar la recepción de matrículas mixtas</span><span class="sxs-lookup"><span data-stu-id="fa935-113">How to set up mixed license plate receiving</span></span>
<span data-ttu-id="fa935-114">La recepción de matrículas mixtas se establece como un elemento de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="fa935-114">Mixed license plate receiving is set up as a mobile device menu item.</span></span>

<span data-ttu-id="fa935-115">Es necesario crear un nuevo elemento de menú en modo trabajo que no utilice el trabajo existente y use los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa935-115">You need to create a new menu item with mode work that does not use existing work and use one of the following methods:</span></span>

- <span data-ttu-id="fa935-116">Recepción de matrícula de entidad de almacén mixta</span><span class="sxs-lookup"><span data-stu-id="fa935-116">Mixed license plate receiving</span></span>
- <span data-ttu-id="fa935-117">Recepción de matrícula de entidad de almacén mixta y ubicación</span><span class="sxs-lookup"><span data-stu-id="fa935-117">Mixed license plate receiving and put away</span></span>

<span data-ttu-id="fa935-118">Las opciones para identificar las líneas de documento de origen son artículos de pedidos de compra, línea de pedido de compra, pedido de devolución, artículo de pedido de transferencia y línea de pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="fa935-118">The options to identify the source document lines are purchase order item, purchase order line, return order, transfer order item, and transfer order line.</span></span> <span data-ttu-id="fa935-119">Estas opciones pueden cambiar el pedido de recepción en una sola matrícula.</span><span class="sxs-lookup"><span data-stu-id="fa935-119">These options can change the receiving order on a single license plate.</span></span> <span data-ttu-id="fa935-120">La última opción es cargar artículos.</span><span class="sxs-lookup"><span data-stu-id="fa935-120">The last option is by load item.</span></span> <span data-ttu-id="fa935-121">Puede agregar varios artículos a una matrícula, pero no puede alternar entre las varias cargas.</span><span class="sxs-lookup"><span data-stu-id="fa935-121">You can add multiple items to a license plate, but you cannot switch between multiple loads.</span></span>


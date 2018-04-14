---
title: "Confirmación de picking de pieza"
description: "Este tema describe cómo configurar y aplicar la confirmación el picking de pieza desde un dispositivo móvil."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
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
ms.openlocfilehash: 5109bc180cedfb21dfb8b2920d71d54812e7e6cf
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="piece-picking-confirmation"></a><span data-ttu-id="61fdd-103">Confirmación de picking de pieza</span><span class="sxs-lookup"><span data-stu-id="61fdd-103">Piece picking confirmation</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="61fdd-104">El picking de pieza le permite confirmar cada pieza de inventario con picking o trabajo de recuento en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="61fdd-104">Piece picking allows you to confirm each piece of inventory through picking or counting work on a mobile device.</span></span> <span data-ttu-id="61fdd-105">Para las selecciones, puede confirmar la cantidad de trabajo que se procesará hasta la cantidad especificada en el trabajo que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="61fdd-105">For picks, you can confirm the quantity of work to be processed up to the quantity that is specified on work to be picked.</span></span> <span data-ttu-id="61fdd-106">Para el trabajo de recuento, puede digitalizar el inventario que está contando y hacer un seguimiento de la cantidad total.</span><span class="sxs-lookup"><span data-stu-id="61fdd-106">For counting work, you can scan the inventory that you are counting and track the total amount.</span></span>

<span data-ttu-id="61fdd-107">Si habilita el piece picking, la confirmación del producto se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="61fdd-107">When you enable piece picking, product confirmation is automatically selected.</span></span> <span data-ttu-id="61fdd-108">Para las selecciones de tipo de trabajo, se habilita un número máximo de piezas.</span><span class="sxs-lookup"><span data-stu-id="61fdd-108">For work-type picks, a maximum number of pieces is enabled.</span></span> <span data-ttu-id="61fdd-109">Esto le permite establecer un máximo número de elementos que se deben confirmar durante el proceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="61fdd-109">This allows you to set a maximum to the number of pieces that must be confirmed during the work process.</span></span> <span data-ttu-id="61fdd-110">La cantidad máxima se basa en la unidad de trabajo actual que se está procesando.</span><span class="sxs-lookup"><span data-stu-id="61fdd-110">The maximum quantity is based on the current work unit that is being processed.</span></span> <span data-ttu-id="61fdd-111">El tipo de trabajo de recuento no permite un máximo.</span><span class="sxs-lookup"><span data-stu-id="61fdd-111">The counting work type does not allow a maximum.</span></span>

<span data-ttu-id="61fdd-112">También puede utilizar la cantidad y la unidad de medida (UdM) asociada a un código de barras digitalizado.</span><span class="sxs-lookup"><span data-stu-id="61fdd-112">You can also use the quantity and unit of measure (UOM) that is associated with a scanned bar code.</span></span> <span data-ttu-id="61fdd-113">Esto funcionará para recibir flujos de entrada con matrículas mezcladas, artículos de pedidos de compra, artículos de pedidos de transferencia y artículos de flete.</span><span class="sxs-lookup"><span data-stu-id="61fdd-113">This will work for receiving on inbound flows including mixed license plate receiving, purchase order item, transfer order item, and load item.</span></span> <span data-ttu-id="61fdd-114">También funciona para el picking de pieza cuando la digitalización del código de barras agregará la cantidad al número total de piezas confirmados que se convierten entre la UdM en el código de barras y la unidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="61fdd-114">It also works for piece picking where scanning the bar code will add the quantity to the total number of confirmed pieces converting between the UOM on the bar code and the work unit.</span></span> <span data-ttu-id="61fdd-115">Si, al realizar el recuento la UdM en el código de barras, se confirma que la cantidad está permitida para el recuento en el grupo de la secuencia, la cantidad se agregará al recuento total.</span><span class="sxs-lookup"><span data-stu-id="61fdd-115">If, when counting the UOM on the bar code, it is confirmed that the quantity is allowed for counting on the sequence group, the quantity will be added to the total count.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="61fdd-116">Dónde se aplica</span><span class="sxs-lookup"><span data-stu-id="61fdd-116">Where it applies</span></span>

<span data-ttu-id="61fdd-117">El picking de piezas funciona para todos los trabajos de recuento y para la selección inicial en cualquier tipo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="61fdd-117">Piece picking works for all counting work and for the initial pick for any type of work.</span></span> <span data-ttu-id="61fdd-118">El picking de piezas no se aplica si el artículo se controla mediante números de serie o si es una selección de producción o kanban de una ubicación de matrícula (LP) y el artículo se configura por etapas.</span><span class="sxs-lookup"><span data-stu-id="61fdd-118">Piece picking does not apply if the item is controlled by serial numbers or if it is a production or kanban pick from a license plate (LP) location and the item is set to staging.</span></span>

## <a name="set-up-piece-picking"></a><span data-ttu-id="61fdd-119">Configurar picking de piezas</span><span class="sxs-lookup"><span data-stu-id="61fdd-119">Set up piece picking</span></span>

1.  <span data-ttu-id="61fdd-120">En un elemento de menú del dispositivo móvil, abra el formulario de configuración para la confirmación del trabajo: Gestión de almacenes > **Gestión de almacenes** > **Configuración** > **Dispositivo móvil** > **Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="61fdd-120">On a mobile device menu item, open the setup form for work confirmation: Warehouse management > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span> 
2. <span data-ttu-id="61fdd-121">En el elemento de menú del dispositivo móvil, abra Configuración de la confirmación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="61fdd-121">From the mobile device menu item, open Work confirmation setup.</span></span>

<span data-ttu-id="61fdd-122">Las siguientes opciones están disponibles para la selección cuando el tipo de trabajo es selección o el recuento.</span><span class="sxs-lookup"><span data-stu-id="61fdd-122">The following options become available for selection when the work type is pick or counting.</span></span>


|           <span data-ttu-id="61fdd-123">Opción</span><span class="sxs-lookup"><span data-stu-id="61fdd-123">Option</span></span>           |                                                                            <span data-ttu-id="61fdd-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="61fdd-124">Description</span></span>                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="61fdd-125">Confirmación de picking de pieza</span><span class="sxs-lookup"><span data-stu-id="61fdd-125">Piece picking confirmation</span></span> | <span data-ttu-id="61fdd-126">Disponible para los tipos de trabajo selección y recuento.</span><span class="sxs-lookup"><span data-stu-id="61fdd-126">Available for pick and counting work types.</span></span> <span data-ttu-id="61fdd-127">La confirmación de producto se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="61fdd-127">Product confirmation is automatically selected.</span></span> <span data-ttu-id="61fdd-128">Permite confirmar cada pieza de inventario desde el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="61fdd-128">Allows you to confirm each piece of inventory from the mobile device.</span></span> |
|  <span data-ttu-id="61fdd-129">Número máximo de piezas</span><span class="sxs-lookup"><span data-stu-id="61fdd-129">Maximum number of pieces</span></span>  |                   <span data-ttu-id="61fdd-130">Disponible para el trabajo de selección si la confirmación de picking de piezas está habilitada.</span><span class="sxs-lookup"><span data-stu-id="61fdd-130">Available for pick work if piece picking confirmation is enabled.</span></span> <span data-ttu-id="61fdd-131">Establece un límite en el número de piezas que debe confirmar.</span><span class="sxs-lookup"><span data-stu-id="61fdd-131">Sets a limit to the number of pieces that you must confirm.</span></span>                   |



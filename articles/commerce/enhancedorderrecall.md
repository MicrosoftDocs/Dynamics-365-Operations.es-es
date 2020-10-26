---
title: Recuperar la operación de pedido en PDV
description: Este tema explica las capacidades de las funciones disponibles para mejorar las páginas de recuperación de pedidos en POS.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 41944fb7819b5527f6bc023a60acd9450d9e43c2
ms.sourcegitcommit: 25909c6ad3616e4f75a2fe006057dda18d7cc856
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "3974847"
---
# <a name="recall-order-operation-in-pos"></a><span data-ttu-id="01cb6-103">Recuperar la operación de pedido en PDV</span><span class="sxs-lookup"><span data-stu-id="01cb6-103">Recall order operation in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="01cb6-104">La operación de recuperación de pedidos en el punto de venta comercial (POS) proporciona funciones de filtrado y búsqueda de pedidos actualizadas e información específica del pedido.</span><span class="sxs-lookup"><span data-stu-id="01cb6-104">The Recall order operation in the Commerce point of sale (POS) provides updated order search and filtering features and order-specific information.</span></span> <span data-ttu-id="01cb6-105">Esta función está disponible en las versiones de Commerce 10.0.15 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="01cb6-105">This feature is available in Commerce versions 10.0.15 and later.</span></span>

<span data-ttu-id="01cb6-106">Para habilitar esta funcionalidad, active la función **Operación mejorada de pedido de recuperación en PDV** en el espacio de trabajo **Gestión de funciones** en Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="01cb6-106">To enable this functionality, turn the **Improved Recall order operation in POS** feature on in **Feature management** workspace in Commerce headquarters.</span></span> <span data-ttu-id="01cb6-107">Después de habilitar la función, considere actualizar sus [diseños de pantalla](pos-screen-layouts.md) en el PDV para aprovechar algunas de las capacidades cambiadas.</span><span class="sxs-lookup"><span data-stu-id="01cb6-107">After you enable the feature, consider updating your [screen layouts](pos-screen-layouts.md) in POS to take advantage of some of the changed  capabilities.</span></span>

<span data-ttu-id="01cb6-108">La configuración del botón de operación **Recuperar pedido** permite a las organizaciones implementar la operación con una pantalla predefinida.</span><span class="sxs-lookup"><span data-stu-id="01cb6-108">The configuration of the **Recall order** operation button allows organizations to deploy the operation with a pre-defined display.</span></span>

![Configuración de cuadrícula de botones](media/recallorderbuttongrid.png)

<span data-ttu-id="01cb6-110">Las opciones de visualización son las siguientes.</span><span class="sxs-lookup"><span data-stu-id="01cb6-110">The display options are as follows.</span></span>
- <span data-ttu-id="01cb6-111">**Ninguna** - Esta opción despliega la operación sin visualización específica.</span><span class="sxs-lookup"><span data-stu-id="01cb6-111">**None** – This option deploys the operation with no specific display.</span></span> <span data-ttu-id="01cb6-112">Cuando un usuario abre la operación con esta configuración, se le pedirá que busque y encuentre pedidos o elija entre un filtro de pedidos predefinido.</span><span class="sxs-lookup"><span data-stu-id="01cb6-112">When a user opens the operation with this configuration, they will be prompted to search and find orders or choose from a pre-defined order filter.</span></span>
- <span data-ttu-id="01cb6-113">**Órdenes a cumplir** - Cuando un usuario inicia la operación, se ejecutará automáticamente una consulta para buscar y mostrar una lista de pedidos que debe atender la tienda.</span><span class="sxs-lookup"><span data-stu-id="01cb6-113">**Orders to fulfill** – When a user launches the operation, a query will run automatically to search and display a list of orders that are to be fulfilled by the store.</span></span> <span data-ttu-id="01cb6-114">Estos pedidos están configurados para recogida en tienda o envío en tienda y las líneas de estos pedidos aún no se han recogido ni embalado.</span><span class="sxs-lookup"><span data-stu-id="01cb6-114">These orders are configured for in-store pickup or store shipment and the lines of these orders have not yet been picked or packed.</span></span>
- <span data-ttu-id="01cb6-115">**Órdenes a recoger** - Cuando un usuario inicia la operación, se ejecutará automáticamente una consulta para buscar y mostrar una lista de pedidos que están configurados para la recogida en la tienda actual del usuario.</span><span class="sxs-lookup"><span data-stu-id="01cb6-115">**Orders to pick up** – When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for in-store pickup at the user's current store.</span></span>
- <span data-ttu-id="01cb6-116">**Órdenes a enviar** - Cuando un usuario inicia la operación, se ejecutará automáticamente una consulta para buscar y mostrar una lista de pedidos que están configurados para el envío desde la tienda actual del usuario.</span><span class="sxs-lookup"><span data-stu-id="01cb6-116">**Orders to ship** - When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for shipment from the user's current store.</span></span>

<span data-ttu-id="01cb6-117">Al iniciar la operación **Recuperar pedido** desde el PDV, si la pantalla está configurada para **Ninguno**, un usuario podrá buscar y recuperar los pedidos de una de las siguientes formas.</span><span class="sxs-lookup"><span data-stu-id="01cb6-117">When launching the **Recall order** operation from POS, if the display is configured to **None**, a user will be able to search and retrieve orders in one of the following ways.</span></span>
- <span data-ttu-id="01cb6-118">Escanee códigos de barras de pedidos.</span><span class="sxs-lookup"><span data-stu-id="01cb6-118">Scan order barcodes.</span></span> <span data-ttu-id="01cb6-119">Esto buscará coincidencias en los campos de número de orden, referencia de canal e ID de recibo.</span><span class="sxs-lookup"><span data-stu-id="01cb6-119">This will search order number, channel reference, and receipt ID fields for matches.</span></span>
- <span data-ttu-id="01cb6-120">Seleccione **Buscar órdenes** o **Buscar y filtrar** en la barra de aplicaciones para usar el mecanismo de filtrado para localizar pedidos que cumplan con los criterios de filtrado.</span><span class="sxs-lookup"><span data-stu-id="01cb6-120">Select **Search orders** or **Search and filter** icon on the AppBar to use the filtering mechanism to locate orders that meet the filter criteria.</span></span>
- <span data-ttu-id="01cb6-121">Elija entre un filtro predefinido del menú desplegable **Mostrar pedidos** (pedidos para cumplir, pedidos para recoger o pedidos para enviar).</span><span class="sxs-lookup"><span data-stu-id="01cb6-121">Choose from a pre-defined filter from the **Show Orders** drop-down menu (orders to fulfill, orders to pick up, or orders to ship).</span></span>

![RecallOrderMainMenu](media/recallordermain.png)

<span data-ttu-id="01cb6-123">Después de aplicar los criterios de búsqueda, la aplicación mostrará una lista de pedidos de ventas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="01cb6-123">After search criteria are applied, the application will display a list of matching sales orders.</span></span>

![RecallOrderDetail](media/orderrecalldetail.png)

<span data-ttu-id="01cb6-125">Un usuario puede seleccionar un pedido de la lista para ver detalles adicionales.</span><span class="sxs-lookup"><span data-stu-id="01cb6-125">A user can select an order on the list to view additional details.</span></span> <span data-ttu-id="01cb6-126">El panel de información en el lado derecho de la pantalla muestra detalles sobre el pedido seleccionado, incluidos los detalles de la línea del pedido, los detalles de la entrega y los detalles de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="01cb6-126">The information panel on the right side of the screen displays specifics on the selected order, including order line details, delivery details, and fulfillment details.</span></span>

<span data-ttu-id="01cb6-127">Desde la barra de aplicaciones, un usuario puede seleccionar una operación.</span><span class="sxs-lookup"><span data-stu-id="01cb6-127">From the AppBar, a user can select an operation.</span></span> <span data-ttu-id="01cb6-128">Dependiendo del estado del pedido, es posible que algunas operaciones no estén habilitadas.</span><span class="sxs-lookup"><span data-stu-id="01cb6-128">Depending on the status of the order, certain operations may not be enabled.</span></span>

- <span data-ttu-id="01cb6-129">**Regreso** - Ejecuta una devolución para una o más facturas relacionadas con el pedido del cliente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="01cb6-129">**Return** – Executes a return for one or more invoices related to the selected customer order.</span></span>

- <span data-ttu-id="01cb6-130">**Cancelar** - Emitir una cancelación total de la orden de venta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="01cb6-130">**Cancel** – Issue a full cancellation of the selected sales order.</span></span>

- <span data-ttu-id="01cb6-131">**Cumplir** - Transfiere al usuario a la página de cumplimiento del pedido, que se prefiltrará para el pedido seleccionado.</span><span class="sxs-lookup"><span data-stu-id="01cb6-131">**Fulfill** – Transfers the user to the order fulfillment page, which will be pre-filtered for the selected order.</span></span> <span data-ttu-id="01cb6-132">Solo se mostrarán las líneas de pedido que estén abiertas para el cumplimiento por parte de la tienda del usuario para el pedido seleccionado.</span><span class="sxs-lookup"><span data-stu-id="01cb6-132">Only order lines that are open for fulfillment by the user's store for the selected order will be displayed.</span></span>

- <span data-ttu-id="01cb6-133">**Editar** - Permite a los usuarios realizar cambios en el pedido del cliente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="01cb6-133">**Edit** – Allows users to make changes to the selected customer order.</span></span>

- <span data-ttu-id="01cb6-134">**Recoger** - Lanza el flujo de recogida, que permite al usuario elegir los productos a recoger y crea la transacción de venta de recogida.</span><span class="sxs-lookup"><span data-stu-id="01cb6-134">**Pick up** – Launches the pickup flow, which allows the user to choose the products to be picked up and creates the pickup sales transaction.</span></span>

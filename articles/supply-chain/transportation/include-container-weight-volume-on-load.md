---
title: Incluir peso y volumen del contenedor de la carga
description: "En este tema se describe cómo configurar y aplicar una funcionalidad para incluir el peso y el volumen del contenedor en las cargas."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4190b5cb05cccc3d762d8ad153ecbd467fa0a332
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="include-container-weight-and-volume-on-load"></a><span data-ttu-id="26626-103">Incluir peso y volumen del contenedor de la carga</span><span class="sxs-lookup"><span data-stu-id="26626-103">Include container weight and volume on load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="26626-104">La funcionalidad para incluir el peso y el volumen del contenedor en una carga ofrece una representación clara del peso y volumen totales de los contenedores y los artículos que se vayan a cargar.</span><span class="sxs-lookup"><span data-stu-id="26626-104">The functionality for including the container weight and volume on a load gives a clear representation of the total weight and volume of containers and items that are going on a load.</span></span>

<span data-ttu-id="26626-105">Una carga contiene un envío único o varios envíos y estos contienen distintos artículos que pertenecen a un único pedido de ventas o a varios pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="26626-105">A load contains a single shipment or multiple shipments, and these shipments contain distinct items that belong to a single sales order or multiple sales orders.</span></span> <span data-ttu-id="26626-106">Los artículos se almacenan en un contenedor y los contenedores se cargan en una carga.</span><span class="sxs-lookup"><span data-stu-id="26626-106">The items are stored inside a container, and containers are loaded on a load.</span></span> <span data-ttu-id="26626-107">Los artículos que se encuentran fuera de un contenedor también pueden formar parte de una carga.</span><span class="sxs-lookup"><span data-stu-id="26626-107">Items that are outside a container can also be part of a load.</span></span> <span data-ttu-id="26626-108">Según estas condiciones, el sistema calculará los valores del peso y volumen en la carga considerando el peso y el volumen de los contenedores y los artículos.</span><span class="sxs-lookup"><span data-stu-id="26626-108">Based on these conditions, the system calculates values for the weight and volume on the load by considering the weight and volume of both containers and items.</span></span>

<span data-ttu-id="26626-109">Si los valores calculados no coinciden exactamente, puede ajustarlos especificando valores reales del peso y el volumen en la carga.</span><span class="sxs-lookup"><span data-stu-id="26626-109">If the calculated values aren’t precise, you can adjust them by entering the actual values for the weight and volume on the load.</span></span> <span data-ttu-id="26626-110">Los valores de peso y volumen se usan en procesos de gestión de transporte.</span><span class="sxs-lookup"><span data-stu-id="26626-110">The values for the weight and volume are used in transportation management processes.</span></span> <span data-ttu-id="26626-111">Por ejemplo, los valores se usan en el banco de trabajo de una ruta de tasa, donde se definen la tasa y la ruta de las cargas y también las formas de pago de transporte y el registro de entrada del conductor.</span><span class="sxs-lookup"><span data-stu-id="26626-111">For example, the values are used in the rate route workbench, where they help define the rate and route for loads, and they are also used for transportation tenders and driver check-in.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="26626-112">Dónde se aplica</span><span class="sxs-lookup"><span data-stu-id="26626-112">Where it applies</span></span>

<span data-ttu-id="26626-113">La funcionalidad para incluir el peso y el volumen del contenedor en una carga, se aplica a los procesos de gestión de transporte tales como el banco de trabajo de una ruta de tasa, las formas de pago de transporte y el registro de entrada del conductor</span><span class="sxs-lookup"><span data-stu-id="26626-113">The functionality for including the container weight and volume on a load applies in transportation management processes, such as the rate route workbench, transportation tenders, and driver check-in.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="26626-114">Cómo se configura</span><span class="sxs-lookup"><span data-stu-id="26626-114">How it is set up</span></span>

<span data-ttu-id="26626-115">El número de contenedores que se deben tener en cuente para una carga se calcula en función del peso y el volumen del contenedor, así como el porcentaje del contenedor que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="26626-115">The number of containers that should be considered for a load is calculated based on the weight and volume of the container, and on the percentage of the container is used.</span></span>

-   <span data-ttu-id="26626-116">Para establecer el peso y el volumen de un contenedor, haga clic en **Gestión de almacenes** \> **Configuración** \> **Contenedores** \> **Tipos de contenedor**.</span><span class="sxs-lookup"><span data-stu-id="26626-116">To set the weight and volume for a container, click **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>

-   <span data-ttu-id="26626-117">Para configurar el porcentaje de utilización del contenedor, haga clic en **Gestión de almacenes** \> **Configuración** \> **Contenedores** \> **Grupos de contenedor** y, a continuación, especifique un valor en el campo **Porcentaje de utilización del contenedor**.</span><span class="sxs-lookup"><span data-stu-id="26626-117">To set the container utilization percentage, click **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**, and then enter a value in the **Container utilization percentage** field.</span></span>


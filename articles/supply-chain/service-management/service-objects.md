---
title: Objetos de servicio
description: Los objetos de servicio son los activos y los productos de un cliente para los que puede realizar un servicio.
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0f7b63393085858c5ff4c64ebdf5d64b3c3ccdef
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="service-objects"></a><span data-ttu-id="c174d-103">Objetos de servicio</span><span class="sxs-lookup"><span data-stu-id="c174d-103">Service objects</span></span> 

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="c174d-104">Los objetos de servicio son los activos y los productos de un cliente para los que puede realizar un servicio.</span><span class="sxs-lookup"><span data-stu-id="c174d-104">Service objects are a customer’s assets and products for which you can perform a service.</span></span> <span data-ttu-id="c174d-105">En función del tipo de servicio proporcionado, los objetos pueden ser tangibles o intangibles:</span><span class="sxs-lookup"><span data-stu-id="c174d-105">Depending on the type of service you provide, objects can be tangible or intangible:</span></span>

-  <span data-ttu-id="c174d-106">Los objetos tangibles son elementos, tal como una máquina o un edificio, sobre los que puede realizar una tarea de servicio física.</span><span class="sxs-lookup"><span data-stu-id="c174d-106">Tangible objects are things, such as a machine or a building, on which you can perform a physical service task.</span></span>

    <span data-ttu-id="c174d-107">Un objeto de servicio tangible también puede ser un artículo de inventario creado en el formulario Detalles de producto emitido.</span><span class="sxs-lookup"><span data-stu-id="c174d-107">A tangible service object can also be an inventory item that you create in the Released product details form.</span></span> <span data-ttu-id="c174d-108">En función del grupo de dimensiones de inventario que vincule al elemento, puede crear un objeto de servicio en un nivel de detalle que incluya el número de serie del artículo.</span><span class="sxs-lookup"><span data-stu-id="c174d-108">Depending on the inventory dimension group that you attach to the item, you can create a service object to a level of detail that includes the item serial number.</span></span> <span data-ttu-id="c174d-109">Esto puede ser de utilidad si debe realizar un seguimiento del artículo exacto que el objeto de servicio representa.</span><span class="sxs-lookup"><span data-stu-id="c174d-109">This is useful when you must keep track of the exact item that the service object represents.</span></span>

    <span data-ttu-id="c174d-110">Un objeto de servicio tangible también puede ser un artículo que no esté relacionado directamente con la producción directa o cadena de suministro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="c174d-110">A tangible service object can also be an item that is not directly related to a company's direct production or supply chain.</span></span> <span data-ttu-id="c174d-111">Por ejemplo, un kit de herramientas que se usa para las reparaciones en un pedido de servicio puede ser un objeto de servicio que no está incluido en el inventario.</span><span class="sxs-lookup"><span data-stu-id="c174d-111">For example, a tool kit that is used for repairs in a service order can be a service object that is not included in inventory.</span></span> <span data-ttu-id="c174d-112">En este caso, no se registra como artículo de inventario.</span><span class="sxs-lookup"><span data-stu-id="c174d-112">In this case, you don’t register it as an inventory item.</span></span>

-  <span data-ttu-id="c174d-113">Los objetos intangibles son cosas inmateriales, como un conjunto de cuentas o un documento legal, sobre las que se pueden realizar tareas de servicio.</span><span class="sxs-lookup"><span data-stu-id="c174d-113">Intangible objects are nonphysical things, such as a set of accounts or a legal document, on which you can perform a service task.</span></span>

## <a name="example-of-an-intangible-service-object"></a><span data-ttu-id="c174d-114">Ejemplo de un objeto de servicio intangible</span><span class="sxs-lookup"><span data-stu-id="c174d-114">Example of an intangible service object</span></span>

<span data-ttu-id="c174d-115">La empresa A mantiene los registros financieros de varias pequeñas empresas.</span><span class="sxs-lookup"><span data-stu-id="c174d-115">Company A maintains the financial records for several small companies.</span></span> <span data-ttu-id="c174d-116">Uno de los clientes de la compañía A es el equipo de fútbol local, para el que la Empresa A realiza la contabilidad semanal y la auditoría anual de las cuentas del club.</span><span class="sxs-lookup"><span data-stu-id="c174d-116">One of Company A's clients is the local football team, for which Company A does the weekly bookkeeping and annual audit of the club's accounts.</span></span> <span data-ttu-id="c174d-117">Las cuentas del club están configuradas en el formulario Objetos de servicio y se especifican como el objeto del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c174d-117">The club's accounts are set up in the Service objects form and specified as the object in the service agreement.</span></span> <span data-ttu-id="c174d-118">Hay dos líneas de acuerdo de servicio para el objeto.</span><span class="sxs-lookup"><span data-stu-id="c174d-118">There are two service agreement lines for the object.</span></span> <span data-ttu-id="c174d-119">La línea 1 es la contabilidad semanal con un intervalo semanal asignado a la línea, y la línea 2 es la auditoría anual con un intervalo anual asignado a ella.</span><span class="sxs-lookup"><span data-stu-id="c174d-119">Line 1 is weekly bookkeeping with a weekly interval assigned to the line, and line 2 is the annual audit with a yearly interval assigned to it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c174d-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c174d-120">Related topics</span></span>

[<span data-ttu-id="c174d-121">Crear objetos del servicio</span><span class="sxs-lookup"><span data-stu-id="c174d-121">Create service objects</span></span>](create-service-objects.md)



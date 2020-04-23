---
title: Visión general de los objetos de servicio
description: Los objetos de servicio son los activos y los productos de un cliente para los que puede realizar un servicio.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ac26083609a337a8d78929dd6f736e1a7c26767
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215157"
---
# <a name="service-objects-overview"></a><span data-ttu-id="770f9-103">Visión general de los objetos de servicio</span><span class="sxs-lookup"><span data-stu-id="770f9-103">Service objects overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="770f9-104">Los objetos de servicio son los activos y los productos de un cliente para los que puede realizar un servicio.</span><span class="sxs-lookup"><span data-stu-id="770f9-104">Service objects are a customer’s assets and products for which you can perform a service.</span></span> <span data-ttu-id="770f9-105">En función del tipo de servicio proporcionado, los objetos pueden ser tangibles o intangibles:</span><span class="sxs-lookup"><span data-stu-id="770f9-105">Depending on the type of service you provide, objects can be tangible or intangible:</span></span>

-  <span data-ttu-id="770f9-106">Los objetos tangibles son elementos, tal como una máquina o un edificio, sobre los que puede realizar una tarea de servicio física.</span><span class="sxs-lookup"><span data-stu-id="770f9-106">Tangible objects are things, such as a machine or a building, on which you can perform a physical service task.</span></span>

    <span data-ttu-id="770f9-107">Un objeto de servicio tangible también puede ser un artículo de inventario creado en el formulario Detalles de producto emitido.</span><span class="sxs-lookup"><span data-stu-id="770f9-107">A tangible service object can also be an inventory item that you create in the Released product details form.</span></span> <span data-ttu-id="770f9-108">En función del grupo de dimensiones de inventario que vincule al elemento, puede crear un objeto de servicio en un nivel de detalle que incluya el número de serie del artículo.</span><span class="sxs-lookup"><span data-stu-id="770f9-108">Depending on the inventory dimension group that you attach to the item, you can create a service object to a level of detail that includes the item serial number.</span></span> <span data-ttu-id="770f9-109">Esto puede ser de utilidad si debe realizar un seguimiento del artículo exacto que el objeto de servicio representa.</span><span class="sxs-lookup"><span data-stu-id="770f9-109">This is useful when you must keep track of the exact item that the service object represents.</span></span>

    <span data-ttu-id="770f9-110">Un objeto de servicio tangible también puede ser un artículo que no esté relacionado directamente con la producción directa o cadena de suministro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="770f9-110">A tangible service object can also be an item that is not directly related to a company's direct production or supply chain.</span></span> <span data-ttu-id="770f9-111">Por ejemplo, un kit de herramientas que se usa para las reparaciones en un pedido de servicio puede ser un objeto de servicio que no está incluido en el inventario.</span><span class="sxs-lookup"><span data-stu-id="770f9-111">For example, a tool kit that is used for repairs in a service order can be a service object that is not included in inventory.</span></span> <span data-ttu-id="770f9-112">En este caso, no se registra como artículo de inventario.</span><span class="sxs-lookup"><span data-stu-id="770f9-112">In this case, you don’t register it as an inventory item.</span></span>

-  <span data-ttu-id="770f9-113">Los objetos intangibles son cosas inmateriales, como un conjunto de cuentas o un documento legal, sobre las que se pueden realizar tareas de servicio.</span><span class="sxs-lookup"><span data-stu-id="770f9-113">Intangible objects are nonphysical things, such as a set of accounts or a legal document, on which you can perform a service task.</span></span>

## <a name="example-of-an-intangible-service-object"></a><span data-ttu-id="770f9-114">Ejemplo de un objeto de servicio intangible</span><span class="sxs-lookup"><span data-stu-id="770f9-114">Example of an intangible service object</span></span>

<span data-ttu-id="770f9-115">La empresa A mantiene los registros financieros de varias pequeñas empresas.</span><span class="sxs-lookup"><span data-stu-id="770f9-115">Company A maintains the financial records for several small companies.</span></span> <span data-ttu-id="770f9-116">Uno de los clientes de la compañía A es el equipo de fútbol local, para el que la Empresa A realiza la contabilidad semanal y la auditoría anual de las cuentas del club.</span><span class="sxs-lookup"><span data-stu-id="770f9-116">One of Company A's clients is the local football team, for which Company A does the weekly bookkeeping and annual audit of the club's accounts.</span></span> <span data-ttu-id="770f9-117">Las cuentas del club están configuradas en el formulario Objetos de servicio y se especifican como el objeto del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="770f9-117">The club's accounts are set up in the Service objects form and specified as the object in the service agreement.</span></span> <span data-ttu-id="770f9-118">Hay dos líneas de acuerdo de servicio para el objeto.</span><span class="sxs-lookup"><span data-stu-id="770f9-118">There are two service agreement lines for the object.</span></span> <span data-ttu-id="770f9-119">La línea 1 es la contabilidad semanal con un intervalo semanal asignado a la línea, y la línea 2 es la auditoría anual con un intervalo anual asignado a ella.</span><span class="sxs-lookup"><span data-stu-id="770f9-119">Line 1 is weekly bookkeeping with a weekly interval assigned to the line, and line 2 is the annual audit with a yearly interval assigned to it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="770f9-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="770f9-120">Related topics</span></span>

[<span data-ttu-id="770f9-121">Crear objetos del servicio</span><span class="sxs-lookup"><span data-stu-id="770f9-121">Create service objects</span></span>](create-service-objects.md)


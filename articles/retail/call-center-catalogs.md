---
title: "Catálogos de centros de llamadas"
description: "Este artículo describe la funcionalidad específica del centro de llamadas para catálogos en Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 2a0055086c29a2ce1ddf14a008bf7ce8b82d011f
ms.contentlocale: es-es
ms.lasthandoff: 01/18/2018

---

# <a name="call-center-catalogs"></a><span data-ttu-id="687ae-103">Catálogos de centros de llamadas</span><span class="sxs-lookup"><span data-stu-id="687ae-103">Call center catalogs</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="687ae-104">Este artículo describe la funcionalidad específica del centro de llamadas para catálogos en Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="687ae-104">This article describes the call center–specific functionality for catalogs in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="687ae-105">En un centro de llamadas, puede usar los catálogos de productos comerciales para identificar los productos que desee ofrecer a los clientes.</span><span class="sxs-lookup"><span data-stu-id="687ae-105">In a call center, you can use product catalogs to identify the products that you want to offer to customers.</span></span> <span data-ttu-id="687ae-106">Los centros de llamadas usan normalmente catálogos impresos.</span><span class="sxs-lookup"><span data-stu-id="687ae-106">Call centers typically use printed catalogs.</span></span> <span data-ttu-id="687ae-107">El diseño y la producción de un catálogo impreso se gestiona fuera de Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="687ae-107">The design and production of a printed catalog is handled outside Dynamics 365 for Retail.</span></span> <span data-ttu-id="687ae-108">Sin embargo, puede crear y almacenar un formulario digital de un catálogo con las mismas páginas que usa para configurar catálogos de venta al por mayor en línea.</span><span class="sxs-lookup"><span data-stu-id="687ae-108">However, you can create and store a digital form of a catalog by using the same pages that you use to set up online retail catalogs.</span></span> <span data-ttu-id="687ae-109">Antes de poder crear un catálogo, debe configurar las selecciones de productos y asignar las selecciones a un centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="687ae-109">Before you can create a catalog, you must set up product assortments and assign the assortments to a call center.</span></span> <span data-ttu-id="687ae-110">A continuación agrega productos al catálogo seleccionando los productos de estas selecciones.</span><span class="sxs-lookup"><span data-stu-id="687ae-110">You then add products to the catalog by selecting products from these assortments.</span></span> <span data-ttu-id="687ae-111">Después de agregar los productos al catálogo y de haberlo completado, debe validar el catálogo para comprobar los datos.</span><span class="sxs-lookup"><span data-stu-id="687ae-111">After products have been added to the catalog, and the catalog is complete, you must validate the catalog to verify the data.</span></span> <span data-ttu-id="687ae-112">A continuación, debe enviar el catálogo para su revisión y aprobación.</span><span class="sxs-lookup"><span data-stu-id="687ae-112">You must then submit the catalog for review and approval.</span></span> <span data-ttu-id="687ae-113">Una vez aprobado el catálogo, es se puede publicar.</span><span class="sxs-lookup"><span data-stu-id="687ae-113">After the catalog is approved, it can be published.</span></span> <span data-ttu-id="687ae-114">Cuando se crea un catálogo de centro de llamadas, puede tomar una instantánea de los datos del catálogo en el momento en que el catálogo se publica.</span><span class="sxs-lookup"><span data-stu-id="687ae-114">When a call center catalog is created, you can take a snapshot of the catalog data at the time that the catalog is published.</span></span> <span data-ttu-id="687ae-115">Esta función de la instantánea permite el acceso a una versión concreta del catálogo incluso si el catálogo se cambia y se actualiza más adelante.</span><span class="sxs-lookup"><span data-stu-id="687ae-115">This snapshot functionality lets you access a particular version of the catalog even if the catalog is later changed and updated.</span></span> <span data-ttu-id="687ae-116">Los catálogos del centro de llamadas también se pueden configurar para incluir las características opcionales siguientes:</span><span class="sxs-lookup"><span data-stu-id="687ae-116">Call center catalogs can also be set up to include the following optional features:</span></span>

-   <span data-ttu-id="687ae-117">**Códigos fuente**: códigos fuente que se utilizan para realizar un seguimiento de la respuesta del cliente en correos de catálogos específicos.</span><span class="sxs-lookup"><span data-stu-id="687ae-117">**Source codes** – Source codes are used to track the customer response to specific catalog mailings.</span></span>
-   <span data-ttu-id="687ae-118">**Productos gratuitos**: se pueden incluir productos en el pedido de un cliente sin ningún gasto adicional.</span><span class="sxs-lookup"><span data-stu-id="687ae-118">**Free products** – Products can be included in a customer's order at no additional charge.</span></span> <span data-ttu-id="687ae-119">Estos productos se agregan a un pedido automáticamente cuando el código fuente del catálogo se especifica en el pedido.</span><span class="sxs-lookup"><span data-stu-id="687ae-119">These products are automatically added to an order when the source code for the catalog is entered into the order.</span></span>
-   <span data-ttu-id="687ae-120">**Scripts**: los scripts son textos que un trabajador del centro de llamadas lee a un cliente cuando se crea un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="687ae-120">**Scripts** – Scripts are texts that a call center worker reads to a customer when a sales order is being created.</span></span> <span data-ttu-id="687ae-121">Las secuencias de comandos pueden incluir saludos o sugerencias de compras.</span><span class="sxs-lookup"><span data-stu-id="687ae-121">Scripts can include greetings or purchase suggestions.</span></span>
-   <span data-ttu-id="687ae-122">**Diseño de página**: un diseño de página captura la posición de la página de productos del catálogo impreso.</span><span class="sxs-lookup"><span data-stu-id="687ae-122">**Page layout** – A page layout captures the page position of products in the printed catalog.</span></span> <span data-ttu-id="687ae-123">Esta información se usa para el informe de análisis del área del catálogo.</span><span class="sxs-lookup"><span data-stu-id="687ae-123">This information is used for the catalog area analysis report.</span></span>






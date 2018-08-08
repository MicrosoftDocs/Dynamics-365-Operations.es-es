---
title: "Iintegración con Microsoft Dynamics 365 for Field Service"
description: "Este tema proporciona una visión general de la integración con Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2ef7f71dc6d58108b498ed89e9175ff2ce900cda
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a><span data-ttu-id="fb345-103">Iintegración con Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="fb345-103">Integration with Microsoft Dynamics 365 for Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="fb345-104">Microsoft Dynamics 365 for Finance and Operations habilita la sincronización de los procesos empresariales entre Finance and Operations y Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="fb345-104">Microsoft Dynamics 365 for Finance and Operations enables synchronization of business processes between Finance and Operations and Microsoft Dynamics 365 for Field Service.</span></span> <span data-ttu-id="fb345-105">Los escenarios de integración se configuran utilizando las plantillas extensibles integradoras del Common Data Service (CDS) para habilitar la sincronización de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="fb345-105">The integration scenarios are configured by using extensible Data integrator templates and the Common Data Service (CDS) to enable the synchronization of business processes.</span></span>

<span data-ttu-id="fb345-106">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="fb345-106">[![Synchronization of business processes between Finance and Operations and Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span></span>

<span data-ttu-id="fb345-107">La primera fase de la integración entre Field Service y Finance and Operations se enfoca en habilitar pedidos y acuerdos de trabajo en Field Service para facturar en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fb345-107">The first phase  of the integration between Field Service and Finance and Operations is focused on enabling work orders and agreements in Field Service to be invoiced in Finance and Operations.</span></span> <span data-ttu-id="fb345-108">El flujo admitido comienza en Field Service, donde la información de pedidos de trabajo se sincroniza con Finance and Operations como pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="fb345-108">The supported flow starts in Field Service, where information from work orders is synchronized to Finance and Operations as sales orders.</span></span> <span data-ttu-id="fb345-109">En Finance and Operations, se facturan los pedidos de ventas para generar documentos de factura.</span><span class="sxs-lookup"><span data-stu-id="fb345-109">In Finance and Operations, the sales orders are invoiced to generate invoice documents.</span></span> <span data-ttu-id="fb345-110">Además, la información de las facturas de acuerdos de Field Service se sincroniza con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fb345-110">In addition, the information from Field Service agreement invoices is synchronized to Finance and Operations.</span></span> <span data-ttu-id="fb345-111">El integrador de los datos de Microsoft Dynamics 365 sincroniza datos mediante proyectos personalizables.</span><span class="sxs-lookup"><span data-stu-id="fb345-111">The Microsoft Dynamics 365 Data integrator synchronizes data by using customizable projects.</span></span> <span data-ttu-id="fb345-112">Las plantillas estándar se pueden usar para crear proyectos personalizados de integración donde la norma adicional estándar y los campos personalizados, y también las entidades, se pueden asignar para ajustar la integración y para cumplir con los requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="fb345-112">Standard templates can be used to create custom integration projects where additional standard and custom fields, and also entities, can be mapped to adjust the integration and meet specific requirements.</span></span>

<span data-ttu-id="fb345-113">La primera fase de la integración entre Field Service y Finance and Operations permite la sincronización de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fb345-113">The first phase of the integration between Field Service and Finance and Operations enables synchronization of the following items:</span></span>

- [<span data-ttu-id="fb345-114">Productos de Finance and Operations con productos de Field Service que incluyen información del tipo de producto</span><span class="sxs-lookup"><span data-stu-id="fb345-114">Products in Finance and Operations to products in Field Service that include Product Type information</span></span>](field-service-product.md)
- [<span data-ttu-id="fb345-115">Pedidos de trabajo en Field Service con pedidos de ventas en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fb345-115">Work orders in Field Service to sales orders in Finance and Operations</span></span>](field-service-work-order.md)
- [<span data-ttu-id="fb345-116">Facturas en Field Service con facturas de texto libre en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fb345-116">Invoices in Field Service to free text invoices in Finance and Operations</span></span>](field-service-invoice.md)

<span data-ttu-id="fb345-117">Para ver un ejemplo de cómo puede sincronizar un pedido de trabajo entre Field Service y Finance and Operations, observe el breve vídeo de YouTube [Sincronizar un pedido de trabajo entre Dynamics 365 for Field Service and Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).</span><span class="sxs-lookup"><span data-stu-id="fb345-117">To see an example of how you can synchronize a work order between Field Service and Finance and Operations, watch the short YouTube video [Synchronize a work order between Dynamics 365 for Field Service and Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).</span></span>

[![](https://img.youtube.com/vi/hAB4TDVMjxU/0.jpg)](https://www.youtube.com/watch?v=hAB4TDVMjxU)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="fb345-118">Requisitos del sistema para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fb345-118">System requirements for Finance and Operations</span></span>
<span data-ttu-id="fb345-119">La integración Field Service admite las siguientes versiones:</span><span class="sxs-lookup"><span data-stu-id="fb345-119">Field Service integration supports the following versions:</span></span>

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a><span data-ttu-id="fb345-120">Dynamics 365 for Finance and Operations vesión 8.0 (abril 2018) o posterior</span><span class="sxs-lookup"><span data-stu-id="fb345-120">Dynamics 365 for Finance and Operations version 8.0 (April 2018) or later</span></span>

- <span data-ttu-id="fb345-121">Dynamics 365 for Finance and Operations versión 8.0 (abril de 2018) fue emitido en abril de 2018 y tiene un número de compilacion de la aplicación 8.0.30.8020 con la plataforma actualiza 15 (7.0.4841.35234).</span><span class="sxs-lookup"><span data-stu-id="fb345-121">Dynamics 365 for Finance and Operations version 8.0 (April 2018) was released in April 2018 and has an application build number 8.0.30.8020 with Platform Update 15 (7.0.4841.35234).</span></span> 

## <a name="system-requirements-for-field-service"></a><span data-ttu-id="fb345-122">Requisitos del sistema para Field Service</span><span class="sxs-lookup"><span data-stu-id="fb345-122">System requirements for Field Service</span></span>
<span data-ttu-id="fb345-123">Para usar la solución de integración de Field Service, debe instalar los componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="fb345-123">To use the Field Service integration solution, you must install the following components:</span></span>

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a><span data-ttu-id="fb345-124">Microsoft Dynamics 365 for Field Service 9.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="fb345-124">Microsoft Dynamics 365 for Field Service 9.0 or later</span></span>

- <span data-ttu-id="fb345-125">Dynamics 365 for Field Service versión 1612 (9.0.1.733) (DB 9.0.1.733) en línea o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="fb345-125">Dynamics 365 for Field Service version 1612 (9.0.1.733) (DB 9.0.1.733) online or a later version.</span></span>
- <span data-ttu-id="fb345-126">Solución Prospect to Cash (P2C) para Dynamics 365, versión 1.15.0.1 o versión posterior.</span><span class="sxs-lookup"><span data-stu-id="fb345-126">Prospect to Cash (P2C) solution for Dynamics 365, version 1.15.0.1 or a later version.</span></span> <span data-ttu-id="fb345-127">La solución está disponible para descarga desde [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span><span class="sxs-lookup"><span data-stu-id="fb345-127">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
- <span data-ttu-id="fb345-128">Solución de integración de Field Service para Dynamics 365, versión 1.0.0.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="fb345-128">Field Service integration solution for Dynamics 365, version 1.0.0.0 or a later version.</span></span> <span data-ttu-id="fb345-129">La solución está disponible para descarga desde [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span><span class="sxs-lookup"><span data-stu-id="fb345-129">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span></span>


---
title: "Iintegración con Microsoft Dynamics 365 for Field Service"
description: "Este tema proporciona una visión general de la integración con Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: d32a4e376770fc73c79b94924d5ae062d201d84a
ms.openlocfilehash: a224962152e80293f6cf3425dea74d73a283e31a
ms.contentlocale: es-es
ms.lasthandoff: 04/12/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a><span data-ttu-id="a8788-103">Iintegración con Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="a8788-103">Integration with Microsoft Dynamics 365 for Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a8788-104">Microsoft Dynamics 365 for Finance and Operations habilita la sincronización de los procesos empresariales entre Finance and Operations y Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="a8788-104">Microsoft Dynamics 365 for Finance and Operations enables synchronization of business processes between Finance and Operations and Microsoft Dynamics 365 for Field Service.</span></span> <span data-ttu-id="a8788-105">Los escenarios de integración se configuran utilizando las plantillas extensibles integradoras del Common Data Service (CDS) para habilitar la sincronización de procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="a8788-105">The integration scenarios are configured by using extensible Data integrator templates and the Common Data Service (CDS) to enable the synchronization of business processes.</span></span>

<span data-ttu-id="a8788-106">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="a8788-106">[![Synchronization of business processes between Finance and Operations and Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span></span>

<span data-ttu-id="a8788-107">La primera fase de la integración entre Field Service y Finance and Operations se enfoca en habilitar pedidos y acuerdos de trabajo en Field Service para facturar en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a8788-107">The first phase  of the integration between Field Service and Finance and Operations is focused on enabling work orders and agreements in Field Service to be invoiced in Finance and Operations.</span></span> <span data-ttu-id="a8788-108">El flujo admitido comienza en Field Service, donde la información de pedidos de trabajo se sincroniza con Finance and Operations como pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="a8788-108">The supported flow starts in Field Service, where information from work orders is synchronized to Finance and Operations as sales orders.</span></span> <span data-ttu-id="a8788-109">En Finance and Operations, se facturan los pedidos de ventas para generar documentos de factura.</span><span class="sxs-lookup"><span data-stu-id="a8788-109">In Finance and Operations, the sales orders are invoiced to generate invoice documents.</span></span> <span data-ttu-id="a8788-110">Además, la información de las facturas de acuerdos de Field Service se sincroniza con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a8788-110">In addition, the information from Field Service agreement invoices is synchronized to Finance and Operations.</span></span> <span data-ttu-id="a8788-111">El integrador de los datos de Microsoft Dynamics 365 sincroniza datos mediante proyectos personalizables.</span><span class="sxs-lookup"><span data-stu-id="a8788-111">The Microsoft Dynamics 365 Data integrator synchronizes data by using customizable projects.</span></span> <span data-ttu-id="a8788-112">Las plantillas estándar se pueden usar para crear proyectos personalizados de integración donde la norma adicional estándar y los campos personalizados, y también las entidades, se pueden asignar para ajustar la integración y para cumplir con los requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="a8788-112">Standard templates can be used to create custom integration projects where additional standard and custom fields, and also entities, can be mapped to adjust the integration and meet specific requirements.</span></span>

<span data-ttu-id="a8788-113">La primera fase de la integración entre Field Service y Finance and Operations permite la sincronización de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8788-113">The first phase of the integration between Field Service and Finance and Operations enables synchronization of the following items:</span></span>

- [<span data-ttu-id="a8788-114">Productos de Finance and Operations con productos de Field Service que incluyen información del tipo de producto</span><span class="sxs-lookup"><span data-stu-id="a8788-114">Products in Finance and Operations to products in Field Service that include Product Type information</span></span>](field-service-product.md)
- [<span data-ttu-id="a8788-115">Pedidos de trabajo en Field Service con pedidos de ventas en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a8788-115">Work orders in Field Service to sales orders in Finance and Operations</span></span>](field-service-work-order.md)
- [<span data-ttu-id="a8788-116">Facturas en Field Service con facturas de texto libre en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a8788-116">Invoices in Field Service to free text invoices in Finance and Operations</span></span>](field-service-invoice.md)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="a8788-117">Requisitos del sistema para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a8788-117">System requirements for Finance and Operations</span></span>
<span data-ttu-id="a8788-118">La integración Field Service admite las siguientes versiones:</span><span class="sxs-lookup"><span data-stu-id="a8788-118">Field Service integration supports the following versions:</span></span>

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a><span data-ttu-id="a8788-119">Dynamics 365 for Finance and Operations vesión 8.0 (abril 2018) o posterior</span><span class="sxs-lookup"><span data-stu-id="a8788-119">Dynamics 365 for Finance and Operations version 8.0 (April 2018) or later</span></span>

- <span data-ttu-id="a8788-120">Dynamics 365 for Finance and Operations versión 8.0 (abril de 2018) fue emitido en abril de 2018 y tiene un número de compilacion de la aplicación 8.0.30.8020 con la plataforma actualiza 15 (7.0.4841.35234).</span><span class="sxs-lookup"><span data-stu-id="a8788-120">Dynamics 365 for Finance and Operations version 8.0 (April 2018) was released in April 2018 and has an application build number 8.0.30.8020 with Platform Update 15 (7.0.4841.35234).</span></span> 

## <a name="system-requirements-for-field-service"></a><span data-ttu-id="a8788-121">Requisitos del sistema para Field Service</span><span class="sxs-lookup"><span data-stu-id="a8788-121">System requirements for Field Service</span></span>
<span data-ttu-id="a8788-122">Para usar la solución de integración de Field Service, debe instalar los componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8788-122">To use the Field Service integration solution, you must install the following components:</span></span>

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a><span data-ttu-id="a8788-123">Microsoft Dynamics 365 for Field Service 9.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="a8788-123">Microsoft Dynamics 365 for Field Service 9.0 or later</span></span>

- <span data-ttu-id="a8788-124">Dynamics 365 for Field Service versión 1612 (9.0.1.733) (DB 9.0.1.733) en línea o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="a8788-124">Dynamics 365 for Field Service version 1612 (9.0.1.733) (DB 9.0.1.733) online or a later version.</span></span>
- <span data-ttu-id="a8788-125">Solución Prospect to Cash (P2C) para Dynamics 365, versión 1.15.0.1 o versión posterior.</span><span class="sxs-lookup"><span data-stu-id="a8788-125">Prospect to Cash (P2C) solution for Dynamics 365, version 1.15.0.1 or a later version.</span></span> <span data-ttu-id="a8788-126">La solución está disponible para descarga desde [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span><span class="sxs-lookup"><span data-stu-id="a8788-126">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
- <span data-ttu-id="a8788-127">Solución de integración de Field Service para Dynamics 365, versión 1.0.0.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="a8788-127">Field Service integration solution for Dynamics 365, version 1.0.0.0 or a later version.</span></span> <span data-ttu-id="a8788-128">La solución está disponible para descarga desde AppSource.</span><span class="sxs-lookup"><span data-stu-id="a8788-128">The solution is available for download from AppSource.</span></span> <span data-ttu-id="a8788-129">**(LIBERACIÓN PENDIENTE)**</span><span class="sxs-lookup"><span data-stu-id="a8788-129">**(PENDING RELEASE)**</span></span>


---
title: Servicios de globalización de Dynamics 365
description: Este tema proporciona información general de los servicios de globalización de Microsoft Dynamics 365.
author: JaneA07
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2ef942f7f6dac2c321a51800ade0bf25f2162304
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018816"
---
# <a name="dynamics-365-globalization-services"></a><span data-ttu-id="76350-103">Servicios de globalización de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="76350-103">Dynamics 365 globalization services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="76350-104">Los siguientes servicios de globalización se pueden configurar para ampliar las capacidades que existen en algunos servicios de Microsoft Dynamics 365 Online:</span><span class="sxs-lookup"><span data-stu-id="76350-104">The following globalization services can be configured to extend the capabilities that exist in some Microsoft Dynamics 365 online services:</span></span>

- <span data-ttu-id="76350-105">**Regulatory Configuration Service (RCS)** admite la configuración de diferentes tipos de documentos e informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="76350-105">**Regulatory Configuration Service (RCS)** supports the configuration of different types of electronic documents and reports.</span></span> <span data-ttu-id="76350-106">RCS proporciona una versión mejorada del diseñador de informes electrónicos (ER) donde el depósito de configuración es un servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="76350-106">RCS provides an enhanced version of the Electronic reporting (ER) designer where the configuration repository is a standalone service.</span></span> <span data-ttu-id="76350-107">Para más información, consulte : [Regulatory Configuration Service](rcs-overview.md).</span><span class="sxs-lookup"><span data-stu-id="76350-107">For more information, see [Regulatory Configuration Service](rcs-overview.md).</span></span>
- <span data-ttu-id="76350-108">**Facturacion electronica** reúne formatos configurables para transformaciones, firmas digitales e integraciones configurables para conectividad con servicios web externos, incluida la certificación y el manejo de respuestas.</span><span class="sxs-lookup"><span data-stu-id="76350-108">**Electronic Invoicing** brings together configurable formats for transformations, digital signatures, and configurable integrations for connectivity with external web services, including certification and response handling.</span></span> <span data-ttu-id="76350-109">Para más información, vea [Facturación electrónica](e-invoicing-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="76350-109">For more information, see [Electronic Invoicing](e-invoicing-service-overview.md).</span></span>
- <span data-ttu-id="76350-110">**Cálculo de impuestos** proporciona una mayor flexibilidad al admitir múltiples ID de impuestos, determinación de códigos de impuestos, el diseñador de cálculo de impuestos y un motor de tiempo de ejecución para cumplir con las complejas regulaciones fiscales en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="76350-110">**Tax Calculation** provides enhanced flexibility by supporting multiple tax IDs, tax code determination, the tax calculation designer, and a runtime engine to comply with complex tax regulations worldwide.</span></span> <span data-ttu-id="76350-111">Para obtener más información, consulte [Cálculo de impuestos](global-tax-calcuation-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="76350-111">For more information, see [Tax Calculation](global-tax-calcuation-service-overview.md).</span></span>

<span data-ttu-id="76350-112">Estos servicios de globalización brindan integración inmediata con los siguientes servicios en línea de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="76350-112">These globalization services provide out-of-box integration with the following Dynamics 365 online services.</span></span>

| <span data-ttu-id="76350-113">Servicio en línea</span><span class="sxs-lookup"><span data-stu-id="76350-113">Online service</span></span> | <span data-ttu-id="76350-114">RCS</span><span class="sxs-lookup"><span data-stu-id="76350-114">RCS</span></span> | <span data-ttu-id="76350-115">Facturación electrónica</span><span class="sxs-lookup"><span data-stu-id="76350-115">Electronic Invoicing</span></span> | <span data-ttu-id="76350-116">Cálculo de impuestos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="76350-116">Tax Calculation (Preview)</span></span> |
|----------------|-----|----------------------|---------------------------|
| <span data-ttu-id="76350-117">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="76350-117">Dynamics 365 Finance</span></span> | <span data-ttu-id="76350-118">Sí</span><span class="sxs-lookup"><span data-stu-id="76350-118">Yes</span></span> | <span data-ttu-id="76350-119">Sí</span><span class="sxs-lookup"><span data-stu-id="76350-119">Yes</span></span> | <span data-ttu-id="76350-120">Sí</span><span class="sxs-lookup"><span data-stu-id="76350-120">Yes</span></span> | 
| <span data-ttu-id="76350-121">Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="76350-121">Dynamics 365 Supply Chain Management</span></span> | <span data-ttu-id="76350-122">Sí</span><span class="sxs-lookup"><span data-stu-id="76350-122">Yes</span></span> | <span data-ttu-id="76350-123">Sí</span><span class="sxs-lookup"><span data-stu-id="76350-123">Yes</span></span> | <span data-ttu-id="76350-124">Sí</span><span class="sxs-lookup"><span data-stu-id="76350-124">Yes</span></span> | 
| <span data-ttu-id="76350-125">Dynamics 365 Project Operations</span><span class="sxs-lookup"><span data-stu-id="76350-125">Dynamics 365 Project Operations</span></span> | <span data-ttu-id="76350-126">Sí</span><span class="sxs-lookup"><span data-stu-id="76350-126">Yes</span></span> | <span data-ttu-id="76350-127">Sí</span><span class="sxs-lookup"><span data-stu-id="76350-127">Yes</span></span> | <span data-ttu-id="76350-128">No aplicable</span><span class="sxs-lookup"><span data-stu-id="76350-128">Not applicable</span></span> | 
| <span data-ttu-id="76350-129">Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="76350-129">Dynamics 365 Commerce</span></span> | <span data-ttu-id="76350-130">Sí</span><span class="sxs-lookup"><span data-stu-id="76350-130">Yes</span></span> | <span data-ttu-id="76350-131">No aplicable</span><span class="sxs-lookup"><span data-stu-id="76350-131">Not applicable</span></span> | <span data-ttu-id="76350-132">No aplicable</span><span class="sxs-lookup"><span data-stu-id="76350-132">Not applicable</span></span> | 

> [!NOTE]
> <span data-ttu-id="76350-133">Debido a las diferencias en la disponibilidad de las ubicaciones geográficas de Azure (geos) para RCS, la configuración de este servicio puede hacer que los datos del cliente se transfieran fuera de la ubicación geográfica seleccionada para el servicio en línea de Dynamics 365 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="76350-133">Because of differences in the availability of Azure geographic locations (geos) for RCS, configuration of this service might cause customer data to be transferred outside the geo that is selected for the applicable Dynamics 365 online service.</span></span> <span data-ttu-id="76350-134">Para obtener más información, consulte [Dynamics 365 y Power Platform: Disponibilidad, ubicación de los datos, idioma y localización](https://aka.ms/rcs/D365Productavailabilityguide).</span><span class="sxs-lookup"><span data-stu-id="76350-134">For more information, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/rcs/D365Productavailabilityguide).</span></span>
---
title: Materiales peligrosos
description: Este tema proporciona información sobre documentos de materiales peligrosos e información almacenada en su entorno.
author: lachlancashMS
manager: AnnBe
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76dd6539e39bb77c546e613b290fc5decba9457f
ms.sourcegitcommit: 4c60f5dccdf0b94ed110a657ef331546adc5424a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2020
ms.locfileid: "2982317"
---
# <a name="hazardous-materials"></a><span data-ttu-id="74a27-103">Materiales peligrosos</span><span class="sxs-lookup"><span data-stu-id="74a27-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74a27-104">La información sobre materiales peligrosos se configura en la gestión de información del producto.</span><span class="sxs-lookup"><span data-stu-id="74a27-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="74a27-105">Este módulo también proporciona documentos que se pueden imprimir a través de la gestión del almacén.</span><span class="sxs-lookup"><span data-stu-id="74a27-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="74a27-106">Cuando envía materiales clasificados como mercancías peligrosas, debe incluir documentación adicional con los envíos.</span><span class="sxs-lookup"><span data-stu-id="74a27-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="74a27-107">La funcionalidad de materiales peligrosos permite que los clientes almacenen información de clasificación y la relacionen para liberar artículos.</span><span class="sxs-lookup"><span data-stu-id="74a27-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="74a27-108">Esta información se puede utilizar para ayudar a preparar la documentación de envío.</span><span class="sxs-lookup"><span data-stu-id="74a27-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74a27-109">Para ayudar a administrar los envíos de mercancías peligrosas, Microsoft Dynamics 365 Supply Chain Management permite configurar información de referencia adicional relacionada con productos.</span><span class="sxs-lookup"><span data-stu-id="74a27-109">To help manage shipments of dangerous goods, Microsoft Dynamics 365 Supply Chain Management lets you set up additional reference information that is related to products.</span></span> <span data-ttu-id="74a27-110">También puede configurar documentos de envío adicionales.</span><span class="sxs-lookup"><span data-stu-id="74a27-110">You can also set up additional shipment documents.</span></span> <span data-ttu-id="74a27-111">Sin embargo, el sistema no cumple automáticamente con las regulaciones de su país o región.</span><span class="sxs-lookup"><span data-stu-id="74a27-111">However, the system isn't automatically compliant with your country's or region's regulations.</span></span> <span data-ttu-id="74a27-112">En cambio, es una herramienta que puede ayudar a su programa general.</span><span class="sxs-lookup"><span data-stu-id="74a27-112">Instead, it's a tool that can help your overall program.</span></span>

<span data-ttu-id="74a27-113">Antes de poder usar esta funcionalidad, se requiere la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a27-113">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="74a27-114">**Gestión de la información del producto:** configure códigos que se pueden aplicar a productos lanzados.</span><span class="sxs-lookup"><span data-stu-id="74a27-114">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="74a27-115">**Gestión de almacenes:** use documentos de envío adicionales para imprimir la información de envío.</span><span class="sxs-lookup"><span data-stu-id="74a27-115">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="74a27-116">Gestión de información de productos</span><span class="sxs-lookup"><span data-stu-id="74a27-116">Product information management</span></span>

<span data-ttu-id="74a27-117">En la gestión de la información del producto, hay una variedad de tablas de configuración donde puede agregar la información de referencia que se proporciona en las listas de mercancías peligrosas para el transporte por carretera, aéreo y marítimo.</span><span class="sxs-lookup"><span data-stu-id="74a27-117">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="74a27-118">Estas son algunas de las regulaciones a las que se suele hacer referencia:</span><span class="sxs-lookup"><span data-stu-id="74a27-118">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="74a27-119">**ADR** - Regulaciones relacionadas con el transporte internacional de mercancías peligrosas por carretera.</span><span class="sxs-lookup"><span data-stu-id="74a27-119">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="74a27-120">**CFR 49** - Regulaciones en los Estados Unidos para el transporte de mercancías peligrosas</span><span class="sxs-lookup"><span data-stu-id="74a27-120">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="74a27-121">**IMDG** - El código internacional de mercancías peligrosas marinas (IMDG)</span><span class="sxs-lookup"><span data-stu-id="74a27-121">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="74a27-122">**IATA** - Las regulaciones de mercancías peligrosas de la Asociación Internacional de Transporte Aéreo (IATA)</span><span class="sxs-lookup"><span data-stu-id="74a27-122">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="74a27-123">Cada una de estas regulaciones tiene una lista de productos peligrosos que incluye códigos de referencia.</span><span class="sxs-lookup"><span data-stu-id="74a27-123">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="74a27-124">Las listas para cada tipo de transporte se combinan en clasificaciones internacionales compartidas.</span><span class="sxs-lookup"><span data-stu-id="74a27-124">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="74a27-125">Supply Chain Management proporciona una tabla de referencia para los códigos compartidos en esas listas.</span><span class="sxs-lookup"><span data-stu-id="74a27-125">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="74a27-126">Cada lista también tiene algunos códigos únicos que se pueden definir.</span><span class="sxs-lookup"><span data-stu-id="74a27-126">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="74a27-127">Para comenzar a configurar esta información, cree una regulación que pueda usar para configurar los parámetros iniciales.</span><span class="sxs-lookup"><span data-stu-id="74a27-127">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="74a27-128">Gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="74a27-128">Warehouse management</span></span>

<span data-ttu-id="74a27-129">Cuando se prepara un envío, se pueden imprimir varios informes nuevos.</span><span class="sxs-lookup"><span data-stu-id="74a27-129">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="74a27-130">Estos informes utilizan la información que configuró en la gestión de información del producto.</span><span class="sxs-lookup"><span data-stu-id="74a27-130">These reports use the information that you set up in Product information management.</span></span>

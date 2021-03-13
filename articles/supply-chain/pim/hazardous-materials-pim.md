---
title: Materiales peligrosos
description: Este tema proporciona información sobre documentos de materiales peligrosos e información almacenada en su entorno.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 156cd4ec3a1d1a08ba43832a93fde0d4f22ac2ed
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007650"
---
# <a name="hazardous-materials"></a><span data-ttu-id="6df9b-103">Materiales peligrosos</span><span class="sxs-lookup"><span data-stu-id="6df9b-103">Hazardous materials</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="6df9b-104">La información sobre materiales peligrosos se configura en la gestión de información del producto.</span><span class="sxs-lookup"><span data-stu-id="6df9b-104">Information about hazardous materials is set up in Product information management.</span></span> <span data-ttu-id="6df9b-105">Este módulo también proporciona documentos que se pueden imprimir a través de la gestión del almacén.</span><span class="sxs-lookup"><span data-stu-id="6df9b-105">This module also provides documents that can be printed through warehouse management.</span></span>

<span data-ttu-id="6df9b-106">Cuando envía materiales clasificados como mercancías peligrosas, debe incluir documentación adicional con los envíos.</span><span class="sxs-lookup"><span data-stu-id="6df9b-106">When you ship materials that are classified as dangerous goods, additional paperwork must be included with the shipments.</span></span> <span data-ttu-id="6df9b-107">La funcionalidad de materiales peligrosos permite que los clientes almacenen información de clasificación y la relacionen para despachar artículos.</span><span class="sxs-lookup"><span data-stu-id="6df9b-107">The hazardous materials functionality lets customers store classification information and relate it to release items.</span></span> <span data-ttu-id="6df9b-108">Esta información se puede utilizar para ayudar a preparar la documentación de envío.</span><span class="sxs-lookup"><span data-stu-id="6df9b-108">This information can then be used to help prepare shipping documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6df9b-109">Las características de materiales peligrosos en Microsoft Dynamics 365 Supply Chain Management proporcionan una colección de campos de información de productos útiles y funciones relacionadas que pueden ayudarle a registrar y hacer referencia a información relacionada con sus productos peligrosos.</span><span class="sxs-lookup"><span data-stu-id="6df9b-109">The hazardous materials features in Microsoft Dynamics 365 Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="6df9b-110">Estas características también pueden ayudarle a diseñar e imprimir documentos de envío que incluyan parte de la misma información sobre cualquier material peligroso que esté enviando.</span><span class="sxs-lookup"><span data-stu-id="6df9b-110">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="6df9b-111">Sin embargo, el sistema no hará que cumpla automáticamente todas las regulaciones de su país o región.</span><span class="sxs-lookup"><span data-stu-id="6df9b-111">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="6df9b-112">Si bien estas herramientas están destinadas a ayudarla a cumplir con las regulaciones comunes, no son suficientes por sí mismas ni se garantiza que lo sean.</span><span class="sxs-lookup"><span data-stu-id="6df9b-112">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="6df9b-113">Su organización es responsable de conocer todas las regulaciones aplicables y de tomar todas las medidas necesarias para cumplirlas.</span><span class="sxs-lookup"><span data-stu-id="6df9b-113">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

<span data-ttu-id="6df9b-114">Antes de poder usar esta funcionalidad, se requiere la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="6df9b-114">Before you can use this functionality, the following setup is required:</span></span>

- <span data-ttu-id="6df9b-115">**Gestión de la información del producto:** configure códigos que se pueden aplicar a productos despachados.</span><span class="sxs-lookup"><span data-stu-id="6df9b-115">**Product information management:** Set up codes that can be applied to released products.</span></span>
- <span data-ttu-id="6df9b-116">**Gestión de almacenes:** use documentos de envío adicionales para imprimir la información de envío.</span><span class="sxs-lookup"><span data-stu-id="6df9b-116">**Warehouse management:** Use additional shipping documents to print shipment information.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="6df9b-117">Gestión de información de productos</span><span class="sxs-lookup"><span data-stu-id="6df9b-117">Product information management</span></span>

<span data-ttu-id="6df9b-118">En la gestión de la información del producto, hay una variedad de tablas de configuración donde puede agregar la información de referencia que se proporciona en las listas de mercancías peligrosas para el transporte por carretera, aéreo y marítimo.</span><span class="sxs-lookup"><span data-stu-id="6df9b-118">In Product information management, there is a range of setup tables where you can add the reference information that is provided in the dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="6df9b-119">Estas son algunas de las regulaciones a las que se suele hacer referencia:</span><span class="sxs-lookup"><span data-stu-id="6df9b-119">Here are some of the regulations that are often referenced:</span></span>

- <span data-ttu-id="6df9b-120">**ADR** - Regulaciones relacionadas con el transporte internacional de mercancías peligrosas por carretera.</span><span class="sxs-lookup"><span data-stu-id="6df9b-120">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="6df9b-121">**CFR 49** - Regulaciones en los Estados Unidos para el transporte de mercancías peligrosas</span><span class="sxs-lookup"><span data-stu-id="6df9b-121">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="6df9b-122">**IMDG** - El código internacional de mercancías peligrosas marinas (IMDG)</span><span class="sxs-lookup"><span data-stu-id="6df9b-122">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="6df9b-123">**IATA** - Las regulaciones de mercancías peligrosas de la Asociación Internacional de Transporte Aéreo (IATA)</span><span class="sxs-lookup"><span data-stu-id="6df9b-123">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="6df9b-124">Cada una de estas regulaciones tiene una lista de productos peligrosos que incluye códigos de referencia.</span><span class="sxs-lookup"><span data-stu-id="6df9b-124">Each of these regulations has a dangerous goods list that includes reference codes.</span></span> <span data-ttu-id="6df9b-125">Las listas para cada tipo de transporte se combinan en clasificaciones internacionales compartidas.</span><span class="sxs-lookup"><span data-stu-id="6df9b-125">The lists for each type of transport are combined on shared international classifications.</span></span> <span data-ttu-id="6df9b-126">Supply Chain Management proporciona una tabla de referencia para los códigos compartidos en esas listas.</span><span class="sxs-lookup"><span data-stu-id="6df9b-126">Supply Chain Management provides a reference table for the shared codes in those lists.</span></span> <span data-ttu-id="6df9b-127">Cada lista también tiene algunos códigos únicos que se pueden definir.</span><span class="sxs-lookup"><span data-stu-id="6df9b-127">Each list also has some unique codes that can be defined.</span></span>

<span data-ttu-id="6df9b-128">Para comenzar a configurar esta información, cree una regulación que pueda usar para configurar los parámetros iniciales.</span><span class="sxs-lookup"><span data-stu-id="6df9b-128">To start to configure this information, create a regulation that you can use to configure the initial parameters.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="6df9b-129">Gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="6df9b-129">Warehouse management</span></span>

<span data-ttu-id="6df9b-130">Cuando se prepara un envío, se pueden imprimir varios informes nuevos.</span><span class="sxs-lookup"><span data-stu-id="6df9b-130">When a shipment is prepared, several new reports can be printed.</span></span> <span data-ttu-id="6df9b-131">Estos informes utilizan la información que configuró en la gestión de información del producto.</span><span class="sxs-lookup"><span data-stu-id="6df9b-131">These reports use the information that you set up in Product information management.</span></span>

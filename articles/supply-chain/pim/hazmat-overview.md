---
title: Resumen de materiales peligrosos
description: Este tema proporciona una descripción general de las características relacionadas con la manipulación y documentación de materiales peligrosos durante la gestión de información de productos y de almacén.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: ff285e7e8bcdd2a3197f0ccae569ac880b796028
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007600"
---
# <a name="hazardous-materials-overview"></a><span data-ttu-id="b893c-103">Resumen de materiales peligrosos</span><span class="sxs-lookup"><span data-stu-id="b893c-103">Hazardous materials overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="b893c-104">Para seguir cumpliendo con las regulaciones de envío y transporte, las organizaciones que envían materiales clasificados como mercancías peligrosas deben incluir documentación adicional con sus envíos.</span><span class="sxs-lookup"><span data-stu-id="b893c-104">To remain compliant with shipping and transport regulations, organizations that ship materials that are classified as dangerous goods must include additional paperwork with their shipments.</span></span> <span data-ttu-id="b893c-105">La función de materiales peligrosos permite a los clientes almacenar información relacionada con los artículos despachados.</span><span class="sxs-lookup"><span data-stu-id="b893c-105">The hazardous materials feature lets customers store information that is related to released items.</span></span> <span data-ttu-id="b893c-106">Esta información se puede utilizar para ayudar a preparar la documentación de envío.</span><span class="sxs-lookup"><span data-stu-id="b893c-106">This information can then be used to help prepare shipping documentation.</span></span> <span data-ttu-id="b893c-107">Una organización que envía mercancías peligrosas debe tener sus propios procesos y procedimientos para gestionar el proceso de envío.</span><span class="sxs-lookup"><span data-stu-id="b893c-107">An organization that ships dangerous goods must have its own processes and procedures for managing the shipping process.</span></span> <span data-ttu-id="b893c-108">Microsoft Dynamics 365 Supply Chain Management es solo una herramienta que puede ayudar a generar los documentos requeridos.</span><span class="sxs-lookup"><span data-stu-id="b893c-108">Microsoft Dynamics 365 Supply Chain Management is just a tool that can help generate the required documents.</span></span>

<span data-ttu-id="b893c-109">El siguiente diagrama ilustra los pasos necesarios para configurar y utilizar la función de materiales peligrosos.</span><span class="sxs-lookup"><span data-stu-id="b893c-109">The following diagram illustrates the steps needed to set up and use the hazardous materials feature.</span></span>

<span data-ttu-id="b893c-110">![Configuración y uso de la función de materiales peligrosos](media/hazmat-overview.png "Configuración y uso de la función de materiales peligrosos")</span><span class="sxs-lookup"><span data-stu-id="b893c-110">![Setup and use of the hazardous materials feature](media/hazmat-overview.png "Setup and use of the hazardous materials feature")</span></span>

<span data-ttu-id="b893c-111">La función de materiales peligrosos se configura en la gestión de información de productos y proporciona documentos que se pueden imprimir a través de la gestión del almacén.</span><span class="sxs-lookup"><span data-stu-id="b893c-111">The hazardous materials feature is set up in Product information management and provides documents that can be printed through Warehouse management.</span></span> <span data-ttu-id="b893c-112">Por lo tanto, en términos generales, esas áreas son las dos áreas principales en las que revisará, configurará y utilizará la funcionalidad de esta función:</span><span class="sxs-lookup"><span data-stu-id="b893c-112">Therefore, broadly speaking, those areas are the two main areas where you will review, set up, and use this feature's functionality:</span></span>

- <span data-ttu-id="b893c-113">**Gestión de la información del producto**: configure los códigos que se aplicarán a los productos despachados.</span><span class="sxs-lookup"><span data-stu-id="b893c-113">**Product information management** – Set up the codes that will be applied to a released product.</span></span>
- <span data-ttu-id="b893c-114">**Gestión de almacenes**: trabajar con documentos de envío adicionales que se imprimirán para los envíos.</span><span class="sxs-lookup"><span data-stu-id="b893c-114">**Warehouse management** – Work with additional shipping documents that will be printed for shipments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b893c-115">Las características de materiales peligrosos en Supply Chain Management proporcionan una colección de campos de información de productos útiles y funcionalidades relacionadas que pueden ayudarle a registrar y hacer referencia a información relacionada con sus productos peligrosos.</span><span class="sxs-lookup"><span data-stu-id="b893c-115">The hazardous materials features in Supply Chain Management provide a collection of useful product information fields and related functionality that can help you record and reference information that is related to your hazardous products.</span></span> <span data-ttu-id="b893c-116">Estas características también pueden ayudarle a diseñar e imprimir documentos de envío que incluyan parte de la misma información sobre cualquier material peligroso que esté enviando.</span><span class="sxs-lookup"><span data-stu-id="b893c-116">These features can also help you design and print shipment documents that include some of the same information about any hazardous materials that you're shipping.</span></span> <span data-ttu-id="b893c-117">Sin embargo, el sistema no hará que cumpla automáticamente todas las regulaciones de su país o región.</span><span class="sxs-lookup"><span data-stu-id="b893c-117">However, the system won't automatically make you compliant with all applicable regulations in your country or region.</span></span> <span data-ttu-id="b893c-118">Si bien estas herramientas están destinadas a ayudarla a cumplir con las regulaciones comunes, no son suficientes por sí mismas ni se garantiza que lo sean.</span><span class="sxs-lookup"><span data-stu-id="b893c-118">Although these tools are intended to help you comply with common regulations, they are neither sufficient in themselves nor guaranteed to be so.</span></span> <span data-ttu-id="b893c-119">Su organización es responsable de conocer todas las regulaciones aplicables y de tomar todas las medidas necesarias para cumplirlas.</span><span class="sxs-lookup"><span data-stu-id="b893c-119">Your organization is responsible for being aware of all applicable regulations and for taking all necessary steps to comply with them.</span></span>

## <a name="product-information-management"></a><span data-ttu-id="b893c-120">Gestión de información de productos</span><span class="sxs-lookup"><span data-stu-id="b893c-120">Product information management</span></span>

<span data-ttu-id="b893c-121">La gestión de información de productos ofrece diversas tablas de configuración donde puede introducir la información de referencia para las listas de mercancías peligrosas para el transporte por carretera, aéreo y marítimo.</span><span class="sxs-lookup"><span data-stu-id="b893c-121">Product information management provides a range of setup tables where you can enter reference information for the various dangerous goods lists for road, air, and sea freight.</span></span>

<span data-ttu-id="b893c-122">Se hizo referencia a las siguientes regulaciones comunes cuando se desarrolló esta funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="b893c-122">The following common regulations were referenced when this functionality was developed:</span></span>

- <span data-ttu-id="b893c-123">**ADR** - Regulaciones relacionadas con el transporte internacional de mercancías peligrosas por carretera.</span><span class="sxs-lookup"><span data-stu-id="b893c-123">**ADR** – Regulations that are related to the international carriage of dangerous goods by road</span></span>
- <span data-ttu-id="b893c-124">**CFR 49** - Regulaciones en los Estados Unidos para el transporte de mercancías peligrosas</span><span class="sxs-lookup"><span data-stu-id="b893c-124">**CFR 49** – Regulations in the United Sates for the carriage of dangerous goods</span></span>
- <span data-ttu-id="b893c-125">**IMDG** - El código internacional de mercancías peligrosas marinas (IMDG)</span><span class="sxs-lookup"><span data-stu-id="b893c-125">**IMDG** – The International Marine Dangerous Goods (IMDG) code</span></span>
- <span data-ttu-id="b893c-126">**IATA** - Las regulaciones de mercancías peligrosas de la Asociación Internacional de Transporte Aéreo (IATA)</span><span class="sxs-lookup"><span data-stu-id="b893c-126">**IATA** – The International Air Transport Association (IATA) dangerous goods regulations</span></span>

<span data-ttu-id="b893c-127">Cada conjunto de reglamentaciones proporciona listas estandarizadas de mercancías peligrosas y códigos de referencia.</span><span class="sxs-lookup"><span data-stu-id="b893c-127">Each set of regulations provides standardized lists of dangerous goods and reference codes.</span></span> <span data-ttu-id="b893c-128">Por tanto, Supply Chain Management proporciona una tabla de referencia para los códigos comunes de esas listas.</span><span class="sxs-lookup"><span data-stu-id="b893c-128">Therefore, Supply Chain Management provides a reference table for the common codes on those lists.</span></span> <span data-ttu-id="b893c-129">Cada lista también tiene algunos códigos únicos que puede definir.</span><span class="sxs-lookup"><span data-stu-id="b893c-129">Each list also has some unique codes that you can define.</span></span>

<span data-ttu-id="b893c-130">Para obtener más información sobre cómo configurar regulaciones y valores para materiales peligrosos, y cómo asignar los valores a productos relevantes, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="b893c-130">For more information about how to set up regulations and values for hazardous materials, and how to assign the values to relevant products, see the following topics:</span></span>

- [<span data-ttu-id="b893c-131">Configurar materiales peligrosos</span><span class="sxs-lookup"><span data-stu-id="b893c-131">Set up hazardous materials</span></span>](hazmat-setup.md)
- [<span data-ttu-id="b893c-132">Materiales peligrosos en productos, pedidos, envíos y cargas</span><span class="sxs-lookup"><span data-stu-id="b893c-132">Hazardous materials in products, orders, shipments, and loads</span></span>](hazmat-items.md)

## <a name="warehouse-management"></a><span data-ttu-id="b893c-133">Gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="b893c-133">Warehouse management</span></span>

<span data-ttu-id="b893c-134">Cuando prepare un envío en Gestión de almacenes, podrá imprimir varios informes nuevos que utilizan la información que configuró en Gestión de información de productos.</span><span class="sxs-lookup"><span data-stu-id="b893c-134">When you prepare a shipment in Warehouse management, you will be able to print several new reports that use the information that you set up in Product information management.</span></span> <span data-ttu-id="b893c-135">Para obtener más información sobre los informes disponibles y cómo utilizarlos, consulte [Consultas e informes sobre materiales peligrosos](hazmat-reports.md).</span><span class="sxs-lookup"><span data-stu-id="b893c-135">For more information about the available reports and how to use them, see [Hazardous materials inquiries and reports](hazmat-reports.md).</span></span>

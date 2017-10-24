---
title: "Periféricos de hardware de PDV"
description: "El punto de venta (POS) moderno al por menor y el PDV en la Nube pueden usar una gran variedad de hardware periférico del PDV, con múltiples interfaces y opciones de implementación para alcanzar los distintos escenarios empresariales de un distribuidor."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 215234
ms.assetid: 1893d4b3-e1b7-4b66-be58-0102addd5b36
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 17738e794f18fddc7320b1b40ef55376fba0de24
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="pos-hardware-peripherals"></a><span data-ttu-id="bb1f6-103">Periféricos de hardware de PDV</span><span class="sxs-lookup"><span data-stu-id="bb1f6-103">POS hardware peripherals</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="bb1f6-104">El punto de venta (POS) moderno al por menor y el PDV en la Nube pueden usar una gran variedad de hardware periférico del PDV, con múltiples interfaces y opciones de implementación para alcanzar los distintos escenarios empresariales de un distribuidor.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-104">Retail Modern point of sale (POS) and Cloud POS can utilize a wide range of POS hardware peripherals, with multiple interfaces and deployment options to achieve a retailer’s various business scenarios.</span></span> 

<span data-ttu-id="bb1f6-105">Para admitir la selección más amplia de dispositivos de distintos fabricantes y modelos, el PDV usa interfaces estándar tales como OLE para PDV al por menor (OPOS), controladores de dispositivo de Windows y las interfaces del programa de aplicación del punto de servicio de Windows (API).</span><span class="sxs-lookup"><span data-stu-id="bb1f6-105">To support the widest selection of devices across manufactures and models, POS utilizes standard interfaces such as OLE for Retail POS (OPOS), Windows device drivers, and Windows point of service application program interfaces (APIs).</span></span> <span data-ttu-id="bb1f6-106">Normalmente, el PDV funcionará en estos dispositivos siempre que se proporcione el controlador adecuado.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-106">Generally, POS will work on these devices provided that the appropriate driver is supplied.</span></span> <span data-ttu-id="bb1f6-107">Sin embargo, dado que la implementación de los estándares de cada fabricante y del programador de software puede variar, a menudo hay diferencias en cuanto a las habilidades o comportamientos admitidos.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-107">However, because each manufacturer and software developer’s implementation of these standards can vary, there are often differences in supported capabilities or behaviors.</span></span>

<span data-ttu-id="bb1f6-108">La siguiente lista incluye los modelos de dispositivo de cada clase que se han sido probados internamente por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb1f6-108">The following list includes device models, in each class, that have been tested internally by Microsoft.</span></span>

<span data-ttu-id="bb1f6-109">**Dispositivos OPDV**</span><span class="sxs-lookup"><span data-stu-id="bb1f6-109">**OPOS devices**</span></span>

-   <span data-ttu-id="bb1f6-110">Código de barras – Motorola DS9208</span><span class="sxs-lookup"><span data-stu-id="bb1f6-110">Barcode – Motorola DS9208</span></span>
-   <span data-ttu-id="bb1f6-111">MSR – HP IDRA-334133, Magtek PN - 21073062</span><span class="sxs-lookup"><span data-stu-id="bb1f6-111">MSR – HP IDRA-334133, Magtek PN - 21073062</span></span>
-   <span data-ttu-id="bb1f6-112">LineDisplay – Epson M58DC</span><span class="sxs-lookup"><span data-stu-id="bb1f6-112">LineDisplay – Epson M58DC</span></span>
-   <span data-ttu-id="bb1f6-113">Pinpad – Verifone 1000SE</span><span class="sxs-lookup"><span data-stu-id="bb1f6-113">Pinpad – Verifone 1000SE</span></span>
-   <span data-ttu-id="bb1f6-114">Tableta de firmas – Scriptel ST1550</span><span class="sxs-lookup"><span data-stu-id="bb1f6-114">Signature pad – Scriptel ST1550</span></span>
-   <span data-ttu-id="bb1f6-115">Impresora – EPSON TM-T88IV, TMT88V</span><span class="sxs-lookup"><span data-stu-id="bb1f6-115">Printer – EPSON TM-T88IV, TMT88V</span></span>
-   <span data-ttu-id="bb1f6-116">Cajas registradora – Star SMD2-1317BK44</span><span class="sxs-lookup"><span data-stu-id="bb1f6-116">Cash drawer – Star SMD2-1317BK44</span></span>
-   <span data-ttu-id="bb1f6-117">Báscula – Datalogic Magellan 8400</span><span class="sxs-lookup"><span data-stu-id="bb1f6-117">Scale – Datalogic Magellan 8400</span></span>

<span data-ttu-id="bb1f6-118">**Teclado con lector MSR**</span><span class="sxs-lookup"><span data-stu-id="bb1f6-118">**Keyboard wedge MSR**</span></span>

-   <span data-ttu-id="bb1f6-119">Magtek USB</span><span class="sxs-lookup"><span data-stu-id="bb1f6-119">Magtek USB</span></span>

<span data-ttu-id="bb1f6-120">**Terminal de pago**</span><span class="sxs-lookup"><span data-stu-id="bb1f6-120">**Payment terminal**</span></span>

-   <span data-ttu-id="bb1f6-121">Equinox L3500</span><span class="sxs-lookup"><span data-stu-id="bb1f6-121">Equinox L3500</span></span>
-   <span data-ttu-id="bb1f6-122">Verifone MX925</span><span class="sxs-lookup"><span data-stu-id="bb1f6-122">Verifone MX925</span></span>

<span data-ttu-id="bb1f6-123">**Dispositivos de red**</span><span class="sxs-lookup"><span data-stu-id="bb1f6-123">**Network devices**</span></span>

-   <span data-ttu-id="bb1f6-124">Impresora – Star TSP650II</span><span class="sxs-lookup"><span data-stu-id="bb1f6-124">Printer – Star TSP650II</span></span>
-   <span data-ttu-id="bb1f6-125">Cajas registradoras – APG Atwood</span><span class="sxs-lookup"><span data-stu-id="bb1f6-125">Cash drawer – APG Atwood</span></span>
-   <span data-ttu-id="bb1f6-126">Terminal de pago – MX915, MX925</span><span class="sxs-lookup"><span data-stu-id="bb1f6-126">Payment terminal – MX915, MX925</span></span>

<span data-ttu-id="bb1f6-127">**PDV modernos de IPC directo solo**</span><span class="sxs-lookup"><span data-stu-id="bb1f6-127">**MPOS direct IPC only**</span></span>

-   <span data-ttu-id="bb1f6-128">Código de barras – Honeywell 1900, HP LS2208</span><span class="sxs-lookup"><span data-stu-id="bb1f6-128">Barcode – Honeywell 1900, HP LS2208</span></span>
-   <span data-ttu-id="bb1f6-129">MSR – Magtek PN - 21073075</span><span class="sxs-lookup"><span data-stu-id="bb1f6-129">MSR – Magtek PN - 21073075</span></span>






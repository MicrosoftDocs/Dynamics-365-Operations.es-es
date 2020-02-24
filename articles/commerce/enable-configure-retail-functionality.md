---
title: Inicializar datos semilla en nuevos entornos de Retail
description: En este artículo se describen los datos que se crean como parte del proceso de inicialización para Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e2833c32d557ec3d2dc80808222d1d47860ce6ea
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023978"
---
# <a name="initialize-seed-data-in-new-retail-environments"></a><span data-ttu-id="29ea5-103">Inicializar datos semilla en nuevos entornos de Retail</span><span class="sxs-lookup"><span data-stu-id="29ea5-103">Initialize seed data in new Retail environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="29ea5-104">En este artículo se describen los datos que se crean como parte del proceso de inicialización para Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="29ea5-104">This article describes the data that's created as part of the initialization process for Dynamics 365 Commerce.</span></span>

<span data-ttu-id="29ea5-105">Después de que la solución Commerce se haya desplegado con Microsoft Dynamics Lifecycle Services (LCS) , debe inicializar la configuración de Commerce para crear los datos de configuración básicos.</span><span class="sxs-lookup"><span data-stu-id="29ea5-105">After the Commerce solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the Commerce configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29ea5-106">Antes de inicializar la configuración de Commerce, asegúrese de que haya especificado un idioma y una dirección postal para cada entidad jurídica en la que va a configurar tiendas.</span><span class="sxs-lookup"><span data-stu-id="29ea5-106">Before you initialize the commerce configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up stores.</span></span> <span data-ttu-id="29ea5-107">Este paso se debe completar para cada entidad jurídica que se use para Commerce.</span><span class="sxs-lookup"><span data-stu-id="29ea5-107">This step must be completed for each legal entity that you use for commerce.</span></span>

<span data-ttu-id="29ea5-108">Para inicializar la configuración, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="29ea5-108">To initialize the configuration, follow these steps.</span></span>

1. <span data-ttu-id="29ea5-109">Iniciar el cliente de Commerce.</span><span class="sxs-lookup"><span data-stu-id="29ea5-109">Start the Commerce client.</span></span>
2. <span data-ttu-id="29ea5-110">Haga clic en **Retail y Commerce** &gt; **Configuración de sede** &gt; **Parámetros** &gt; **Parámetros de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="29ea5-110">Click **Retail and Commerce** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Commerce parameters**.</span></span>
3. <span data-ttu-id="29ea5-111">Haga clic en **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="29ea5-111">Click **Initialize**.</span></span>

<span data-ttu-id="29ea5-112">Inicialización crea los datos de configuración siguientes predeterminados:</span><span class="sxs-lookup"><span data-stu-id="29ea5-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="29ea5-113">Trabajos y subtrabajos del programador de Commerce</span><span class="sxs-lookup"><span data-stu-id="29ea5-113">Commerce scheduler jobs and subjobs</span></span>
- <span data-ttu-id="29ea5-114">Esquema de canal de comercio</span><span class="sxs-lookup"><span data-stu-id="29ea5-114">Commerce channel schema</span></span>
- <span data-ttu-id="29ea5-115">Programaciones de distribución de Commerce</span><span class="sxs-lookup"><span data-stu-id="29ea5-115">Commerce distribution schedules</span></span>
- <span data-ttu-id="29ea5-116">Diseños de pantalla predeterminados, que incluyen bloqueos, imágenes y temas</span><span class="sxs-lookup"><span data-stu-id="29ea5-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="29ea5-117">Información de zona horaria</span><span class="sxs-lookup"><span data-stu-id="29ea5-117">Time zone information</span></span>
- <span data-ttu-id="29ea5-118">Operaciones de punto de venta (PDV)</span><span class="sxs-lookup"><span data-stu-id="29ea5-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="29ea5-119">Permisos de PDV</span><span class="sxs-lookup"><span data-stu-id="29ea5-119">POS permissions</span></span>
- <span data-ttu-id="29ea5-120">Informes de canales</span><span class="sxs-lookup"><span data-stu-id="29ea5-120">Channel reports</span></span>
- <span data-ttu-id="29ea5-121">Metadatos de atributos</span><span class="sxs-lookup"><span data-stu-id="29ea5-121">Attribute metadata</span></span>
- <span data-ttu-id="29ea5-122">Plantillas de validación de entidad</span><span class="sxs-lookup"><span data-stu-id="29ea5-122">Entity validation templates</span></span>
- <span data-ttu-id="29ea5-123">Trabajo por lotes para depurar el historial de la sesión Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="29ea5-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="29ea5-124">Además, el registro relacionado con la industria de la tarjeta de pago se habilita para la base de datos de Commerce.</span><span class="sxs-lookup"><span data-stu-id="29ea5-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Commerce database.</span></span>

> [!NOTE]
> <span data-ttu-id="29ea5-125">Hay una opción para configurar por separado el programador de Commerce.</span><span class="sxs-lookup"><span data-stu-id="29ea5-125">There is an option to separately configure the Commerce scheduler.</span></span> <span data-ttu-id="29ea5-126">Esta opción permite restablecer la configuración del programador de Commerce a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="29ea5-126">This option lets you reset the Commerce scheduler configuration to its default settings.</span></span>

<span data-ttu-id="29ea5-127">Después de que la inicialización esté completada, debe configurar los datos adicionales de Commerce.</span><span class="sxs-lookup"><span data-stu-id="29ea5-127">After initialization is completed, you must configure additional commerce data.</span></span> <span data-ttu-id="29ea5-128">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="29ea5-128">Here are some examples:</span></span>

- <span data-ttu-id="29ea5-129">Parámetros de comercio</span><span class="sxs-lookup"><span data-stu-id="29ea5-129">Commerce parameters</span></span>
- <span data-ttu-id="29ea5-130">Parámetros del programador de comercio</span><span class="sxs-lookup"><span data-stu-id="29ea5-130">Commerce scheduler parameters</span></span>
- <span data-ttu-id="29ea5-131">Canales de Commerce</span><span class="sxs-lookup"><span data-stu-id="29ea5-131">Commerce channels</span></span>
- <span data-ttu-id="29ea5-132">Cajas registradoras y dispositivos</span><span class="sxs-lookup"><span data-stu-id="29ea5-132">Registers and devices</span></span>
- <span data-ttu-id="29ea5-133">Varios</span><span class="sxs-lookup"><span data-stu-id="29ea5-133">Assortments</span></span>

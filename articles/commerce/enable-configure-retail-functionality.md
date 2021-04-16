---
title: Inicializar datos semilla en nuevos entornos de Commerce
description: En este artículo se describen los datos que se crean como parte del proceso de inicialización para Dynamics 365 Commerce.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9f534410b21fd97554f4e038bb14eebd5f887130
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792592"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a><span data-ttu-id="95fe7-103">Inicializar datos semilla en nuevos entornos de Commerce</span><span class="sxs-lookup"><span data-stu-id="95fe7-103">Initialize seed data in new Commerce environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="95fe7-104">En este artículo se describen los datos que se crean como parte del proceso de inicialización para Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="95fe7-104">This article describes the data that's created as part of the initialization process for Dynamics 365 Commerce.</span></span>

<span data-ttu-id="95fe7-105">Después de que la solución Commerce se haya desplegado con Microsoft Dynamics Lifecycle Services (LCS) , debe inicializar la configuración de Commerce para crear los datos de configuración básicos.</span><span class="sxs-lookup"><span data-stu-id="95fe7-105">After the Commerce solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the Commerce configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95fe7-106">Antes de inicializar la configuración de Commerce, asegúrese de que haya especificado un idioma y una dirección postal para cada entidad jurídica en la que va a configurar tiendas.</span><span class="sxs-lookup"><span data-stu-id="95fe7-106">Before you initialize the commerce configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up stores.</span></span> <span data-ttu-id="95fe7-107">Este paso se debe completar para cada entidad jurídica que se use para Commerce.</span><span class="sxs-lookup"><span data-stu-id="95fe7-107">This step must be completed for each legal entity that you use for commerce.</span></span>

<span data-ttu-id="95fe7-108">Para inicializar la configuración, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="95fe7-108">To initialize the configuration, follow these steps.</span></span>

1. <span data-ttu-id="95fe7-109">Iniciar el cliente de Commerce.</span><span class="sxs-lookup"><span data-stu-id="95fe7-109">Start the Commerce client.</span></span>
2. <span data-ttu-id="95fe7-110">Haga clic en **Retail y Commerce** &gt; **Configuración de sede** &gt; **Parámetros** &gt; **Parámetros de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="95fe7-110">Click **Retail and Commerce** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Commerce parameters**.</span></span>
3. <span data-ttu-id="95fe7-111">Haga clic en **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="95fe7-111">Click **Initialize**.</span></span>

<span data-ttu-id="95fe7-112">Inicialización crea los datos de configuración siguientes predeterminados:</span><span class="sxs-lookup"><span data-stu-id="95fe7-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="95fe7-113">Trabajos y subtrabajos del programador de Commerce</span><span class="sxs-lookup"><span data-stu-id="95fe7-113">Commerce scheduler jobs and subjobs</span></span>
- <span data-ttu-id="95fe7-114">Esquema de canal de comercio</span><span class="sxs-lookup"><span data-stu-id="95fe7-114">Commerce channel schema</span></span>
- <span data-ttu-id="95fe7-115">Programaciones de distribución de Commerce</span><span class="sxs-lookup"><span data-stu-id="95fe7-115">Commerce distribution schedules</span></span>
- <span data-ttu-id="95fe7-116">Diseños de pantalla predeterminados, que incluyen bloqueos, imágenes y temas</span><span class="sxs-lookup"><span data-stu-id="95fe7-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="95fe7-117">Información de zona horaria</span><span class="sxs-lookup"><span data-stu-id="95fe7-117">Time zone information</span></span>
- <span data-ttu-id="95fe7-118">Operaciones de punto de venta (PDV)</span><span class="sxs-lookup"><span data-stu-id="95fe7-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="95fe7-119">Permisos de PDV</span><span class="sxs-lookup"><span data-stu-id="95fe7-119">POS permissions</span></span>
- <span data-ttu-id="95fe7-120">Informes de canales</span><span class="sxs-lookup"><span data-stu-id="95fe7-120">Channel reports</span></span>
- <span data-ttu-id="95fe7-121">Metadatos de atributos</span><span class="sxs-lookup"><span data-stu-id="95fe7-121">Attribute metadata</span></span>
- <span data-ttu-id="95fe7-122">Plantillas de validación de entidad</span><span class="sxs-lookup"><span data-stu-id="95fe7-122">Entity validation templates</span></span>
- <span data-ttu-id="95fe7-123">Trabajo por lotes para depurar el historial de la sesión Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="95fe7-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="95fe7-124">Además, el registro relacionado con la industria de la tarjeta de pago se habilita para la base de datos de Commerce.</span><span class="sxs-lookup"><span data-stu-id="95fe7-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Commerce database.</span></span>

> [!NOTE]
> <span data-ttu-id="95fe7-125">Hay una opción para configurar por separado el programador de Commerce.</span><span class="sxs-lookup"><span data-stu-id="95fe7-125">There is an option to separately configure the Commerce scheduler.</span></span> <span data-ttu-id="95fe7-126">Esta opción permite restablecer la configuración del programador de Commerce a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="95fe7-126">This option lets you reset the Commerce scheduler configuration to its default settings.</span></span>

<span data-ttu-id="95fe7-127">Después de que la inicialización esté completada, debe configurar los datos adicionales de Commerce.</span><span class="sxs-lookup"><span data-stu-id="95fe7-127">After initialization is completed, you must configure additional commerce data.</span></span> <span data-ttu-id="95fe7-128">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="95fe7-128">Here are some examples:</span></span>

- <span data-ttu-id="95fe7-129">Parámetros de comercio</span><span class="sxs-lookup"><span data-stu-id="95fe7-129">Commerce parameters</span></span>
- <span data-ttu-id="95fe7-130">Parámetros del programador de comercio</span><span class="sxs-lookup"><span data-stu-id="95fe7-130">Commerce scheduler parameters</span></span>
- <span data-ttu-id="95fe7-131">Canales de Commerce</span><span class="sxs-lookup"><span data-stu-id="95fe7-131">Commerce channels</span></span>
- <span data-ttu-id="95fe7-132">Cajas registradoras y dispositivos</span><span class="sxs-lookup"><span data-stu-id="95fe7-132">Registers and devices</span></span>
- <span data-ttu-id="95fe7-133">Varios</span><span class="sxs-lookup"><span data-stu-id="95fe7-133">Assortments</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
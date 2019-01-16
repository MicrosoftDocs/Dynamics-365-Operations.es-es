---
title: Inicializar datos semilla en nuevos entornos de Retail
description: "En este artículo se describen los datos que se crean como parte del proceso de inicialización para Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 52f0c52748958f0bebb6c40df01cfac10c0ed427
ms.contentlocale: es-es
ms.lasthandoff: 01/04/2019

---

# <a name="initialize-seed-data-in-new-retail-environments"></a><span data-ttu-id="77db8-103">Inicializar datos semilla en nuevos entornos de Retail</span><span class="sxs-lookup"><span data-stu-id="77db8-103">Initialize seed data in new Retail environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="77db8-104">En este artículo se describen los datos que se crean como parte del proceso de inicialización para Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="77db8-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="77db8-105">Después de que la solución de venta minorista se haya desplegado con los servicios de ciclo de vida de Microsoft Dynamics, debe inicializar la configuración de venta minorista para crear los datos de configuración básicos.</span><span class="sxs-lookup"><span data-stu-id="77db8-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77db8-106">Antes de inicializar la configuración de venta minorista, asegúrese de que haya especificado un idioma y una dirección postal para cada entidad jurídica en la que va a configurar tiendas de venta minorista.</span><span class="sxs-lookup"><span data-stu-id="77db8-106">Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="77db8-107">Este paso se debe completar para cada entidad jurídica que se use para la venta minorista.</span><span class="sxs-lookup"><span data-stu-id="77db8-107">This step must be completed for each legal entity that you use for retail.</span></span>

<span data-ttu-id="77db8-108">Para inicializar la configuración de venta minorista, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="77db8-108">To initialize the retail configuration, follow these steps.</span></span>

1. <span data-ttu-id="77db8-109">Inicie el cliente de Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="77db8-109">Start the Dynamics 365 for Retail client.</span></span>
2. <span data-ttu-id="77db8-110">Haga clic en **Retail** &gt; **Configuración de sede central** &gt; **Parámetros** &gt; **Parámetros comerciales**.</span><span class="sxs-lookup"><span data-stu-id="77db8-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3. <span data-ttu-id="77db8-111">Haga clic en **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="77db8-111">Click **Initialize**.</span></span>

<span data-ttu-id="77db8-112">Inicialización crea los datos de configuración siguientes predeterminados:</span><span class="sxs-lookup"><span data-stu-id="77db8-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="77db8-113">Trabajos y subtrabajos del programador de ventas minoristas</span><span class="sxs-lookup"><span data-stu-id="77db8-113">Retail scheduler jobs and subjobs</span></span>
- <span data-ttu-id="77db8-114">Esquema del canal comercial</span><span class="sxs-lookup"><span data-stu-id="77db8-114">Retail channel schema</span></span>
- <span data-ttu-id="77db8-115">Programaciones de distribución de ventas minoristas</span><span class="sxs-lookup"><span data-stu-id="77db8-115">Retail distribution schedules</span></span>
- <span data-ttu-id="77db8-116">Diseños de pantalla predeterminados, que incluyen bloqueos, imágenes y temas</span><span class="sxs-lookup"><span data-stu-id="77db8-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="77db8-117">Información de zona horaria</span><span class="sxs-lookup"><span data-stu-id="77db8-117">Time zone information</span></span>
- <span data-ttu-id="77db8-118">Operaciones de punto de venta (PDV)</span><span class="sxs-lookup"><span data-stu-id="77db8-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="77db8-119">Permisos de PDV</span><span class="sxs-lookup"><span data-stu-id="77db8-119">POS permissions</span></span>
- <span data-ttu-id="77db8-120">Informes de canales</span><span class="sxs-lookup"><span data-stu-id="77db8-120">Channel reports</span></span>
- <span data-ttu-id="77db8-121">Metadatos de atributos</span><span class="sxs-lookup"><span data-stu-id="77db8-121">Attribute metadata</span></span>
- <span data-ttu-id="77db8-122">Plantillas de validación de entidad</span><span class="sxs-lookup"><span data-stu-id="77db8-122">Entity validation templates</span></span>
- <span data-ttu-id="77db8-123">Trabajo por lotes para purgar historial de la sesión de intercambio de datos comerciales</span><span class="sxs-lookup"><span data-stu-id="77db8-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="77db8-124">Además, el registro relacionado con la industria de la tarjeta de pago se habilita para la base de datos de Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="77db8-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span>

> [!NOTE]
> <span data-ttu-id="77db8-125">Hay una opción para configurar por separado el programador de venta minorista.</span><span class="sxs-lookup"><span data-stu-id="77db8-125">There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="77db8-126">Esta opción permite restablecer la configuración del programador de venta minorista a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="77db8-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span>

<span data-ttu-id="77db8-127">Después de que la inicialización esté completada, debe configurar los datos adicionales de la venta minorista.</span><span class="sxs-lookup"><span data-stu-id="77db8-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="77db8-128">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="77db8-128">Here are some examples:</span></span>

- <span data-ttu-id="77db8-129">Parámetros comerciales</span><span class="sxs-lookup"><span data-stu-id="77db8-129">Retail parameters</span></span>
- <span data-ttu-id="77db8-130">Parámetros del Programador de tareas Retail</span><span class="sxs-lookup"><span data-stu-id="77db8-130">Retail scheduler parameters</span></span>
- <span data-ttu-id="77db8-131">Canales comerciales</span><span class="sxs-lookup"><span data-stu-id="77db8-131">Retail channels</span></span>
- <span data-ttu-id="77db8-132">Cajas registradoras y dispositivos</span><span class="sxs-lookup"><span data-stu-id="77db8-132">Registers and devices</span></span>
- <span data-ttu-id="77db8-133">Varios</span><span class="sxs-lookup"><span data-stu-id="77db8-133">Assortments</span></span>


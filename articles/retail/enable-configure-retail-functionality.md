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
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 80fa443fc235496a111a8a866d2e703202721268
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="initialize-seed-data-in-new-retail-environments"></a><span data-ttu-id="844d1-103">Inicializar datos semilla en nuevos entornos de Retail</span><span class="sxs-lookup"><span data-stu-id="844d1-103">Initialize seed data in new Retail environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="844d1-104">En este artículo se describen los datos que se crean como parte del proceso de inicialización para Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="844d1-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="844d1-105">Después de que la solución de venta minorista se haya desplegado con los servicios de ciclo de vida de Microsoft Dynamics, debe inicializar la configuración de venta minorista para crear los datos de configuración básicos.</span><span class="sxs-lookup"><span data-stu-id="844d1-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span> <span data-ttu-id="844d1-106">**Importante:** antes de inicializar la configuración de venta minorista, asegúrese de que haya especificado un idioma y una dirección postal para cada entidad jurídica en la que va a configurar tiendas de venta minorista.</span><span class="sxs-lookup"><span data-stu-id="844d1-106">**Important:** Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="844d1-107">Este paso se debe completar para cada entidad jurídica que se use para la venta minorista.</span><span class="sxs-lookup"><span data-stu-id="844d1-107">This step must be completed for each legal entity that you use for retail.</span></span> <span data-ttu-id="844d1-108">Para inicializar la configuración de venta minorista, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="844d1-108">To initialize the retail configuration, follow these steps.</span></span>

1.  <span data-ttu-id="844d1-109">Inicie el cliente de Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="844d1-109">Start the Dynamics 365 for Retail client.</span></span>
2.  <span data-ttu-id="844d1-110">Haga clic en **Retail** &gt; **Configuración de sede central** &gt; **Parámetros** &gt; **Parámetros comerciales**.</span><span class="sxs-lookup"><span data-stu-id="844d1-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3.  <span data-ttu-id="844d1-111">Haga clic en **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="844d1-111">Click **Initialize**.</span></span>

<span data-ttu-id="844d1-112">Inicialización crea los datos de configuración siguientes predeterminados:</span><span class="sxs-lookup"><span data-stu-id="844d1-112">Initialization creates the following default configuration data:</span></span>

-   <span data-ttu-id="844d1-113">Trabajos y subtrabajos del programador de ventas minoristas</span><span class="sxs-lookup"><span data-stu-id="844d1-113">Retail scheduler jobs and subjobs</span></span>
-   <span data-ttu-id="844d1-114">Esquema del canal comercial</span><span class="sxs-lookup"><span data-stu-id="844d1-114">Retail channel schema</span></span>
-   <span data-ttu-id="844d1-115">Programaciones de distribución de ventas minoristas</span><span class="sxs-lookup"><span data-stu-id="844d1-115">Retail distribution schedules</span></span>
-   <span data-ttu-id="844d1-116">Diseños de pantalla predeterminados, que incluyen bloqueos, imágenes y temas</span><span class="sxs-lookup"><span data-stu-id="844d1-116">Default screen layouts, which include button grids, images, and themes</span></span>
-   <span data-ttu-id="844d1-117">Información de zona horaria</span><span class="sxs-lookup"><span data-stu-id="844d1-117">Time zone information</span></span>
-   <span data-ttu-id="844d1-118">Operaciones de punto de venta (PDV)</span><span class="sxs-lookup"><span data-stu-id="844d1-118">Point-of-sale (POS) operations</span></span>
-   <span data-ttu-id="844d1-119">Permisos de PDV</span><span class="sxs-lookup"><span data-stu-id="844d1-119">POS permissions</span></span>
-   <span data-ttu-id="844d1-120">Informes de canales</span><span class="sxs-lookup"><span data-stu-id="844d1-120">Channel reports</span></span>
-   <span data-ttu-id="844d1-121">Metadatos de atributos</span><span class="sxs-lookup"><span data-stu-id="844d1-121">Attribute metadata</span></span>
-   <span data-ttu-id="844d1-122">Plantillas de validación de entidad</span><span class="sxs-lookup"><span data-stu-id="844d1-122">Entity validation templates</span></span>
-   <span data-ttu-id="844d1-123">Trabajo por lotes para purgar historial de la sesión de intercambio de datos comerciales</span><span class="sxs-lookup"><span data-stu-id="844d1-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="844d1-124">Además, el registro relacionado con la industria de la tarjeta de pago se habilita para la base de datos de Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="844d1-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span> <span data-ttu-id="844d1-125">**Nota:** hay una opción para configurar por separado el programador de venta minorista.</span><span class="sxs-lookup"><span data-stu-id="844d1-125">**Note:** There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="844d1-126">Esta opción permite restablecer la configuración del programador de venta minorista a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="844d1-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span> <span data-ttu-id="844d1-127">Después de que la inicialización esté completada, debe configurar los datos adicionales de la venta minorista.</span><span class="sxs-lookup"><span data-stu-id="844d1-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="844d1-128">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="844d1-128">Here are some examples:</span></span>

-   <span data-ttu-id="844d1-129">Parámetros comerciales</span><span class="sxs-lookup"><span data-stu-id="844d1-129">Retail parameters</span></span>
-   <span data-ttu-id="844d1-130">Parámetros del Programador de tareas Retail</span><span class="sxs-lookup"><span data-stu-id="844d1-130">Retail scheduler parameters</span></span>
-   <span data-ttu-id="844d1-131">Canales comerciales</span><span class="sxs-lookup"><span data-stu-id="844d1-131">Retail channels</span></span>
-   <span data-ttu-id="844d1-132">Cajas registradoras y dispositivos</span><span class="sxs-lookup"><span data-stu-id="844d1-132">Registers and devices</span></span>
-   <span data-ttu-id="844d1-133">Varios</span><span class="sxs-lookup"><span data-stu-id="844d1-133">Assortments</span></span>






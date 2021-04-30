---
title: Regulatory Configuration Service
description: Este tema proporciona una descripción general de las capacidades de Regulatory Configuration Service (RCS) y explica cómo acceder al servicio.
author: JaneA07
manager: AnnBe
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ec7e0fe07d979b85109605949b6ba33ab6d99b51
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890809"
---
# <a name="regulatory-configuration-service"></a><span data-ttu-id="287fe-103">Regulatory Configuration Service</span><span class="sxs-lookup"><span data-stu-id="287fe-103">Regulatory Configuration Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="287fe-104">Regulatory Configuration Service (RCS) es un diseñador independiente y un servicio de gestión del ciclo de vida para la funcionalidad de globalización sin código / código bajo.</span><span class="sxs-lookup"><span data-stu-id="287fe-104">Regulatory Configuration Service (RCS) is a standalone designer and lifecycle management service for no-code/low-code globalization functionality.</span></span> <span data-ttu-id="287fe-105">RCS permite que las partes interesadas de la globalización amplíen y personalicen áreas clave de globalización de impuestos, facturación electrónica, informes regulatorios, banca y documentos comerciales sin tener que involucrar a los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="287fe-105">RCS lets globalization stakeholders extend and customize key globalization areas of tax, e-invoicing, regulatory reporting, banking, and business documents without having to involve developers.</span></span> <span data-ttu-id="287fe-106">Este enfoque de globalización sin código / bajo código hace que la globalización sea más fácil, rápida y rentable de crear o ampliar.</span><span class="sxs-lookup"><span data-stu-id="287fe-106">This no-code/low-code globalization approach makes globalization easier, faster, and more cost effective to create or extend.</span></span>

<span data-ttu-id="287fe-107">RCS proporciona las prestaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="287fe-107">RCS provides the following capabilities:</span></span>

- <span data-ttu-id="287fe-108">Soporte para todas las funciones que proporciona la generación de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="287fe-108">Support for all functionality that is provided by Electronic reporting (ER).</span></span>
- <span data-ttu-id="287fe-109">Un requisito previo para configurar nuevos microservicios de globalización.</span><span class="sxs-lookup"><span data-stu-id="287fe-109">A prerequisite to configure new globalization microservices.</span></span>
- <span data-ttu-id="287fe-110">Compatibilidad con facturación electrónica.</span><span class="sxs-lookup"><span data-stu-id="287fe-110">Support for Electronic Invoicing.</span></span> <span data-ttu-id="287fe-111">Para más información, vea [Facturación electrónica](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span><span class="sxs-lookup"><span data-stu-id="287fe-111">For more information, see [Electronic Invoicing](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span></span>
- <span data-ttu-id="287fe-112">Soportes para el cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="287fe-112">Supports for Tax Calculation.</span></span> <span data-ttu-id="287fe-113">Para obtener más información, consulte [Servicio de impuestos](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span><span class="sxs-lookup"><span data-stu-id="287fe-113">For more information, see [Tax service](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span></span>
- <span data-ttu-id="287fe-114">Compatibilidad con la nueva función de función de globalización que simplifica la gestión del ciclo de vida de funciones de varios componentes y proporciona capacidad adicional para configurar acciones y configurar parámetros de funciones.</span><span class="sxs-lookup"><span data-stu-id="287fe-114">Support for new globalization feature functionality that simplifies the lifecycle management of multi-component features and provides extra capability to configure actions and set up feature parameters.</span></span> <span data-ttu-id="287fe-115">Para más información, ver [Regulatory Configuration Service: gestión simplificada de funciones de globalización para servicios de globalización](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span><span class="sxs-lookup"><span data-stu-id="287fe-115">For more information, see [Regulatory Configuration Service – simplified globalization feature management for globalization services](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span></span>
- <span data-ttu-id="287fe-116">Soporte para publicación, almacenamiento y uso compartido centralizados de configuraciones personalizadas en el repositorio global para simplificar la administración de la configuración sin requerir el uso de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="287fe-116">Support for centralized publication, storage, and sharing of custom configurations in the Global repository to simplify configuration management without requiring the use of Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="access-rcs"></a><span data-ttu-id="287fe-117">Acceder a RCS</span><span class="sxs-lookup"><span data-stu-id="287fe-117">Access RCS</span></span>

<span data-ttu-id="287fe-118">Puede registrarse o iniciar sesión en RCS desde la [Página de Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="287fe-118">You can sign up for or sign in to RCS from the [Regulatory Configuration Service page](https://marketing.configure.global.dynamics.com/).</span></span>

![Registro e inicio de sesión en RCS](media/202103_RCS%20Marketing%20page_updated_1.jpg)

<span data-ttu-id="287fe-120">En la página **Regulatory Configuration Service**, revise y acepte los términos y condiciones suplementarios para el uso del servicio, y luego seleccione uno de los siguientes botones:</span><span class="sxs-lookup"><span data-stu-id="287fe-120">On the **Regulatory Configuration Service** page, review and accept the supplemental terms and conditions for use of the service, and then select one of the following buttons:</span></span>

- <span data-ttu-id="287fe-121">**Inscribirse** si es la primera vez que utiliza el servicio y utiliza una dirección de correo electrónico empresarial para proporcionar a su organización un entorno de servicio</span><span class="sxs-lookup"><span data-stu-id="287fe-121">**Sign up** if you're a first-time user of the service, and you're using a business email address to provision your organization a service environment</span></span>
- <span data-ttu-id="287fe-122">**Iniciar sesión** si se ha registrado anteriormente en el servicio y desea acceder al entorno de su organización</span><span class="sxs-lookup"><span data-stu-id="287fe-122">**Sign in** if you've previously signed up for the service, and you want to access your organization environment</span></span>

## <a name="regional-availability"></a><span data-ttu-id="287fe-123">Disponibilidad regional</span><span class="sxs-lookup"><span data-stu-id="287fe-123">Regional availability</span></span>

<span data-ttu-id="287fe-124">RCS generalmente está disponible en las siguientes regiones:</span><span class="sxs-lookup"><span data-stu-id="287fe-124">RCS is generally available in the following regions:</span></span>

- <span data-ttu-id="287fe-125">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="287fe-125">United States</span></span>
- <span data-ttu-id="287fe-126">India</span><span class="sxs-lookup"><span data-stu-id="287fe-126">India</span></span>
- <span data-ttu-id="287fe-127">Francia</span><span class="sxs-lookup"><span data-stu-id="287fe-127">France</span></span>
- <span data-ttu-id="287fe-128">Europa</span><span class="sxs-lookup"><span data-stu-id="287fe-128">Europe</span></span>

<span data-ttu-id="287fe-129">Para obtener una lista completa de regiones, consulte [Dynamics 365 y Power Platform: Disponibilidad, ubicación de los datos, idioma y localización](https://aka.ms/dynamics_365_international_availability_deck).</span><span class="sxs-lookup"><span data-stu-id="287fe-129">For a complete list of regions, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/dynamics_365_international_availability_deck).</span></span>

## <a name="related-rcs-documentation"></a><span data-ttu-id="287fe-130">Documentación de RCS relacionada</span><span class="sxs-lookup"><span data-stu-id="287fe-130">Related RCS documentation</span></span>

<span data-ttu-id="287fe-131">Para obtener más información acerca componentes relacionados, consulte la siguiente documentación:</span><span class="sxs-lookup"><span data-stu-id="287fe-131">For more information about related components, see the following documentation:</span></span>

- <span data-ttu-id="287fe-132">**Repositorio global:**</span><span class="sxs-lookup"><span data-stu-id="287fe-132">**Global repository:**</span></span>

    - [<span data-ttu-id="287fe-133">Cree la configuración de ER y cárguela en el repositorio global</span><span class="sxs-lookup"><span data-stu-id="287fe-133">Create ER configuration & upload to Global repo</span></span>](rcs-global-repo-upload.md)
    - [<span data-ttu-id="287fe-134">Comparta la configuración en el repositorio global</span><span class="sxs-lookup"><span data-stu-id="287fe-134">Share configuration in Global repo</span></span>](rcs-global-repo-share-configuration.md)
    - [<span data-ttu-id="287fe-135">Filtrado mejorado en el repositorio global</span><span class="sxs-lookup"><span data-stu-id="287fe-135">Enhanced filtering in Global repo</span></span>](enhanced-filtering-global-repo.md)
    - [<span data-ttu-id="287fe-136">Descargar configuraciones de informes electrónicos del repositorio global</span><span class="sxs-lookup"><span data-stu-id="287fe-136">Download ER configurations from the Global repository</span></span>](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [<span data-ttu-id="287fe-137">Suspender configuraciones en el repositorio global</span><span class="sxs-lookup"><span data-stu-id="287fe-137">Discontinuing configurations in Global repo</span></span>](discontinuing-configurations-rcs-global-repo.md)

- <span data-ttu-id="287fe-138">**Característica de globalización**</span><span class="sxs-lookup"><span data-stu-id="287fe-138">**Globalization feature:**</span></span>

    - [<span data-ttu-id="287fe-139">Regulatory Configuration Service (RCS): característica de globalización</span><span class="sxs-lookup"><span data-stu-id="287fe-139">Regulatory Configuration Service (RCS) - Globalization feature</span></span>](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)
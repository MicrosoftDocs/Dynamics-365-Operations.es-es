---
title: Descripción general de doble escritura
description: Este tema proporciona una visión general de doble escritura. La doble escritura es una infraestructura que proporciona interacción casi en tiempo real entre aplicaciones basadas en modelos de Microsoft Dynamics 365 y aplicaciones de Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c4a643d4981364cea5b549118c201ac8a9798e02
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113883"
---
# <a name="dual-write-overview"></a><span data-ttu-id="0e80d-104">Descripción general de doble escritura</span><span class="sxs-lookup"><span data-stu-id="0e80d-104">Dual-write overview</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

## <a name="what-is-dual-write"></a><span data-ttu-id="0e80d-105">¿Qué es la doble escritura?</span><span class="sxs-lookup"><span data-stu-id="0e80d-105">What is dual-write?</span></span>

<span data-ttu-id="0e80d-106">La doble escritura es una infraestructura lista para usar que proporciona interacción casi en tiempo real entre aplicaciones basadas en modelos de Microsoft Dynamics 365 y aplicaciones de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0e80d-106">Dual-write is an out-of-box infrastructure that provides near-real-time interaction between model-driven apps in Microsoft Dynamics 365 and Finance and Operations apps.</span></span> <span data-ttu-id="0e80d-107">Cuando los datos sobre clientes, productos, personas y operaciones fluyen más allá de los límites de la aplicación, todos los departamentos de una organización tienen poder.</span><span class="sxs-lookup"><span data-stu-id="0e80d-107">When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.</span></span>

<span data-ttu-id="0e80d-108">La doble escritura proporciona una integración bidireccional estrechamente acoplada entre aplicaciones Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0e80d-108">Dual-write provides tightly coupled, bidirectional integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="0e80d-109">Cualquier cambio de datos en aplicaciones Finance and Operations hace que se escriba en Common Data Service y cualquier cambio de datos en Common Data Service hace que se escriba en las aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0e80d-109">Any data change in Finance and Operations apps causes writes to Common Data Service, and any data change in Common Data Service causes writes to Finance and Operations apps.</span></span> <span data-ttu-id="0e80d-110">Este flujo de datos automatizado proporciona una experiencia de usuario integrada en todas las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0e80d-110">This automated data flow provides an integrated user experience across the apps.</span></span>

![Relación de datos entre aplicaciones](media/dual-write-overview.jpg)

<span data-ttu-id="0e80d-112">La doble escritura tiene dos aspectos: un aspecto *infraestructura* y un aspecto *solicitud*.</span><span class="sxs-lookup"><span data-stu-id="0e80d-112">Dual-write has two aspects: an *infrastructure* aspect and an *application* aspect.</span></span>

### <a name="infrastructure"></a><span data-ttu-id="0e80d-113">Infraestructura</span><span class="sxs-lookup"><span data-stu-id="0e80d-113">Infrastructure</span></span>

<span data-ttu-id="0e80d-114">La infraestructura de doble escritura es extensible y fiable, e incluye las siguientes características clave:</span><span class="sxs-lookup"><span data-stu-id="0e80d-114">The dual-write infrastructure is extensible and reliable, and includes the following key features:</span></span>

+ <span data-ttu-id="0e80d-115">Flujo de datos síncrono y bidireccional entre aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0e80d-115">Synchronous and bidirectional data flow between applications</span></span>
+ <span data-ttu-id="0e80d-116">Sincronización, junto con modos de reproducción, pausa y recuperación para admitir el sistema durante los modos en línea y fuera de línea / asíncrono.</span><span class="sxs-lookup"><span data-stu-id="0e80d-116">Synchronization, together with play, pause, and catchup modes to support the system during online and offline/asynchronous modes.</span></span>
+ <span data-ttu-id="0e80d-117">Capacidad para sincronizar datos iniciales entre las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="0e80d-117">Ability to sync initial data between the applications</span></span>
+ <span data-ttu-id="0e80d-118">Vista consolidada de actividad y registros de errores para administradores de datos</span><span class="sxs-lookup"><span data-stu-id="0e80d-118">Consolidated view of activity and error logs for data admins</span></span>
+ <span data-ttu-id="0e80d-119">Posibilidad de configurar alertas y umbrales personalizados y suscribirse a notificaciones</span><span class="sxs-lookup"><span data-stu-id="0e80d-119">Ability to configure custom alerts and thresholds, and to subscribe to notifications</span></span>
+ <span data-ttu-id="0e80d-120">Interfaz de usuario intuitiva (UI) para filtrado y transformaciones</span><span class="sxs-lookup"><span data-stu-id="0e80d-120">Intuitive user interface (UI) for filtering and transformations</span></span>
+ <span data-ttu-id="0e80d-121">Capacidad para establecer y ver las dependencias y relaciones de la entidad</span><span class="sxs-lookup"><span data-stu-id="0e80d-121">Ability to set and view entity dependencies and relationships</span></span>
+ <span data-ttu-id="0e80d-122">Extensibilidad para entidades y mapas estándar y personalizados</span><span class="sxs-lookup"><span data-stu-id="0e80d-122">Extensibility for both standard and custom entities and maps</span></span>
+ <span data-ttu-id="0e80d-123">Administración fiable del ciclo de vida de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0e80d-123">Reliable application lifecycle management</span></span>
+ <span data-ttu-id="0e80d-124">Experiencia de configuración lista para usar para nuevos clientes</span><span class="sxs-lookup"><span data-stu-id="0e80d-124">Out-of-box setup experience for new customers</span></span>

### <a name="application"></a><span data-ttu-id="0e80d-125">Solicitud</span><span class="sxs-lookup"><span data-stu-id="0e80d-125">Application</span></span>

<span data-ttu-id="0e80d-126">La doble escritura crea una asignación entre conceptos en aplicaciones de Finance and Operations aplicaciones y conceptos en aplicaciones basadas en modelos en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0e80d-126">Dual-write creates a mapping between concepts in Finance and Operations apps and concepts in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="0e80d-127">Esta integración admite los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="0e80d-127">This integration supports the following scenarios:</span></span>

+ <span data-ttu-id="0e80d-128">Maestro de clientes integrado</span><span class="sxs-lookup"><span data-stu-id="0e80d-128">Integrated customer master</span></span>
+ <span data-ttu-id="0e80d-129">Acceso a tarjetas de fidelización de clientes y puntos de recompensa</span><span class="sxs-lookup"><span data-stu-id="0e80d-129">Access to customer loyalty cards and reward points</span></span>
+ <span data-ttu-id="0e80d-130">Experiencia unificada del producto maestro</span><span class="sxs-lookup"><span data-stu-id="0e80d-130">Unified product mastering experience</span></span>
+ <span data-ttu-id="0e80d-131">Reconocimiento de jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="0e80d-131">Awareness of organization hierarchy</span></span>
+ <span data-ttu-id="0e80d-132">Maestro de proveedores integrado</span><span class="sxs-lookup"><span data-stu-id="0e80d-132">Integrated vendor master</span></span>
+ <span data-ttu-id="0e80d-133">Acceso a datos financieros y de referencia fiscal</span><span class="sxs-lookup"><span data-stu-id="0e80d-133">Access to finance and tax reference data</span></span>
+ <span data-ttu-id="0e80d-134">Experiencia de motor de precio bajo demanda</span><span class="sxs-lookup"><span data-stu-id="0e80d-134">On-demand price engine experience</span></span>
+ <span data-ttu-id="0e80d-135">Experiencia integrada de cliente potencial a efectivo</span><span class="sxs-lookup"><span data-stu-id="0e80d-135">Integrated prospect-to-cash experience</span></span>
+ <span data-ttu-id="0e80d-136">Capacidad para servir tanto los activos internos como los activos de los clientes a través de agentes de campo</span><span class="sxs-lookup"><span data-stu-id="0e80d-136">Ability to serve both in-house assets and customer assets through field agents</span></span>
+ <span data-ttu-id="0e80d-137">Experiencia integrada de adquisición a pago</span><span class="sxs-lookup"><span data-stu-id="0e80d-137">Integrated procure-to-pay experience</span></span>
+ <span data-ttu-id="0e80d-138">Actividades integradas y notas para los datos y documentos del cliente</span><span class="sxs-lookup"><span data-stu-id="0e80d-138">Integrated activities and notes for customer data and documents</span></span>
+ <span data-ttu-id="0e80d-139">Capacidad para buscar disponibilidad de inventario disponible y detalles</span><span class="sxs-lookup"><span data-stu-id="0e80d-139">Ability to look up on-hand inventory availability and details</span></span>
+ <span data-ttu-id="0e80d-140">Experiencia cliente potencial a efectivo</span><span class="sxs-lookup"><span data-stu-id="0e80d-140">Project-to-cash experience</span></span>
+ <span data-ttu-id="0e80d-141">Capacidad para manejar múltiples direcciones y roles a través del concepto de parte</span><span class="sxs-lookup"><span data-stu-id="0e80d-141">Ability to handle multiple addresses and roles through the party concept</span></span>
+ <span data-ttu-id="0e80d-142">Gestión de fuente única para usuarios</span><span class="sxs-lookup"><span data-stu-id="0e80d-142">Single source management for users</span></span>
+ <span data-ttu-id="0e80d-143">Canales integrados para venta minorista y comercialización</span><span class="sxs-lookup"><span data-stu-id="0e80d-143">Integrated channels for retailing and marketing</span></span>
+ <span data-ttu-id="0e80d-144">Visibilidad de promociones y descuentos</span><span class="sxs-lookup"><span data-stu-id="0e80d-144">Visibility into promotions and discounts</span></span>
+ <span data-ttu-id="0e80d-145">Funciones de solicitud de servicio</span><span class="sxs-lookup"><span data-stu-id="0e80d-145">Request-for-service functions</span></span>
+ <span data-ttu-id="0e80d-146">Operaciones de servicio optimizadas</span><span class="sxs-lookup"><span data-stu-id="0e80d-146">Streamlined service operations</span></span>

## <a name="top-reasons-to-use-dual-write"></a><span data-ttu-id="0e80d-147">Principales razones para usar doble escritura</span><span class="sxs-lookup"><span data-stu-id="0e80d-147">Top reasons to use dual-write</span></span>

<span data-ttu-id="0e80d-148">La doble escritura proporciona integración de datos en las aplicaciones Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0e80d-148">Dual-write provides data integration across Microsoft Dynamics 365 applications.</span></span> <span data-ttu-id="0e80d-149">Este marco robusto vincula entornos y permite que diferentes aplicaciones empresariales trabajen juntas.</span><span class="sxs-lookup"><span data-stu-id="0e80d-149">This robust framework links environments and enables different business applications to work together.</span></span> <span data-ttu-id="0e80d-150">Estas son las principales razones por las que debería usar la doble escritura:</span><span class="sxs-lookup"><span data-stu-id="0e80d-150">Here are the top reasons why you should use dual-write:</span></span>

+ <span data-ttu-id="0e80d-151">La doble escritura proporciona una integración estrechamente acoplada, casi en tiempo real y bidireccional entre aplicaciones Finance and Operations y aplicaciones basadas en modelos en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0e80d-151">Dual-write provides tightly coupled, near-real-time, and bidirectional integration between Finance and Operations apps and model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="0e80d-152">Esta integración hace de Microsoft Dynamics 365 la ventanilla única para todas sus soluciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="0e80d-152">This integration makes Microsoft Dynamics 365 the one-stop shop for all your business solutions.</span></span> <span data-ttu-id="0e80d-153">Los clientes que usan Dynamics 365 Finance y Dynamics 365 Supply Chain Management, pero que usan soluciones que no son de Microsoft para la gestión de relaciones con los clientes (CRM), se están pasando a Dynamics 365 por su soporte de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="0e80d-153">Customers who use Dynamics 365 Finance and Dynamics 365 Supply Chain Management, but who use non-Microsoft solutions for customer relationship management (CRM), are moving toward Dynamics 365 for its dual-write support.</span></span>
+ <span data-ttu-id="0e80d-154">Los datos de clientes, productos, operaciones, proyectos e Internet de las cosas (IoT) fluyen automáticamente a Common Data Service a través de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="0e80d-154">Data from customers, products, operations, projects, and the Internet of Things (IoT) automatically flows to Common Data Service through dual-write.</span></span> <span data-ttu-id="0e80d-155">Esta conexión es muy útil para las empresas que están interesadas en expansiones de Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="0e80d-155">This connection is very useful for businesses that are interested in Microsoft Power Platform expansions.</span></span>
+ <span data-ttu-id="0e80d-156">La infraestructura de doble escritura sigue el principio sin código / código bajo.</span><span class="sxs-lookup"><span data-stu-id="0e80d-156">The dual-write infrastructure follows the no-code/low-code principle.</span></span> <span data-ttu-id="0e80d-157">Se requiere un mínimo esfuerzo de ingeniería para ampliar los mapas estándar de tabla a tabla e incluir mapas personalizados.</span><span class="sxs-lookup"><span data-stu-id="0e80d-157">Minimal engineering effort is required to extend the standard table-to-table maps and to include custom maps.</span></span>
+ <span data-ttu-id="0e80d-158">La doble escritura admite tanto el modo en línea como el modo fuera de línea.</span><span class="sxs-lookup"><span data-stu-id="0e80d-158">Dual-write supports both online mode and offline mode.</span></span> <span data-ttu-id="0e80d-159">Microsoft es la única compañía que ofrece soporte para modos en línea y fuera de línea.</span><span class="sxs-lookup"><span data-stu-id="0e80d-159">Microsoft is the only company that offers support for online and offline modes.</span></span>

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a><span data-ttu-id="0e80d-160">¿Qué significa la doble escritura para los usuarios y arquitectos de productos CRM?</span><span class="sxs-lookup"><span data-stu-id="0e80d-160">What does dual-write mean for users and architects of CRM products?</span></span>

<span data-ttu-id="0e80d-161">La doble escritura automatiza el flujo de datos entre aplicaciones Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0e80d-161">Dual-write automates the data flow between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="0e80d-162">En futuras versiones, los conceptos de las aplicaciones basadas en modelos en Dynamics 365 (por ejemplo, cliente, contacto, presupuesto y pedido) se ampliarán a clientes de mercado medio y mercado medio alto.</span><span class="sxs-lookup"><span data-stu-id="0e80d-162">In future releases, concepts in model-driven apps in Dynamics 365 (for example, customer, contact, quotation, and order) will be scaled to mid-market and upper-mid-market customers.</span></span>

<span data-ttu-id="0e80d-163">En la primera versión, la mayor parte de la automatización se maneja con soluciones de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="0e80d-163">In the first release, most of the automation is handled by dual-write solutions.</span></span> <span data-ttu-id="0e80d-164">En futuras versiones, esas soluciones se convertirán en parte de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0e80d-164">In future releases, those solutions will become part of Common Data Service.</span></span> <span data-ttu-id="0e80d-165">Al comprender los próximos cambios a Common Data Service, puede ahorrar esfuerzos a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="0e80d-165">By understanding the upcoming changes to Common Data Service, you can save yourself effort in the long term.</span></span> <span data-ttu-id="0e80d-166">Estos son algunos de los cambios cruciales:</span><span class="sxs-lookup"><span data-stu-id="0e80d-166">Here are some of the crucial changes:</span></span>

+ <span data-ttu-id="0e80d-167">Common Data Service tendrá nuevos conceptos, como empresa y parte.</span><span class="sxs-lookup"><span data-stu-id="0e80d-167">Common Data Service will have new concepts, such as company and party.</span></span> <span data-ttu-id="0e80d-168">Estos conceptos afectarán a todas las aplicaciones basadas en Common Data Service, como Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service y Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="0e80d-168">These concepts will affect all apps that are built on Common Data Service, such as Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service, and Dynamics 365 Field Service.</span></span>
+ <span data-ttu-id="0e80d-169">Las actividades y notas se unifican y amplían para admitir tanto C1 (usuarios del sistema) como C2 (clientes del sistema).</span><span class="sxs-lookup"><span data-stu-id="0e80d-169">Activities and notes are unified and expanded to support both C1s (users of the system) and C2s (customers of the system).</span></span>
+ <span data-ttu-id="0e80d-170">Estos son algunos de los próximos cambios en Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="0e80d-170">Here are some of the upcoming changes in Common Data Service:</span></span>

    - <span data-ttu-id="0e80d-171">El tipo de datos decimal reemplazará el tipo de datos de dinero.</span><span class="sxs-lookup"><span data-stu-id="0e80d-171">The decimal data type will replace the money data type.</span></span>
    - <span data-ttu-id="0e80d-172">La efectividad de la fecha admitirá datos pasados, presentes y futuros en el mismo lugar.</span><span class="sxs-lookup"><span data-stu-id="0e80d-172">Date effectivity will support past, present, and future data in the same place.</span></span>
    - <span data-ttu-id="0e80d-173">Habrá más soporte para la divisa y los tipos de cambio, y la interfaz de la aplicación de programación **Tipo de cambio** (API) se revisará.</span><span class="sxs-lookup"><span data-stu-id="0e80d-173">There will be more support for currency and exchange rates, and the **Exchange Rate** application programming interface (API) will be revised.</span></span>
    - <span data-ttu-id="0e80d-174">Se admitirán conversiones de unidades.</span><span class="sxs-lookup"><span data-stu-id="0e80d-174">Unit conversions will be supported.</span></span>

<span data-ttu-id="0e80d-175">Para obtener más información sobre los próximos cambios, vea [Datos en Common Data Service - fases 1 y 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/finance-operations-crossapp-capabilities/data-common-data-service-phase-1).</span><span class="sxs-lookup"><span data-stu-id="0e80d-175">For more information about upcoming changes, see [Data in Common Data Service – phase 1 & 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/finance-operations-crossapp-capabilities/data-common-data-service-phase-1).</span></span>

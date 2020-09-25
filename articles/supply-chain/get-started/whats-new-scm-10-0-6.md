---
title: Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.6 (noviembre de 2019)
description: En este tema se describen las características nuevas o modificadas en Dynamics 365 Supply Chain Management 10.0.6.
author: josaw1
manager: tfehr
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 9ee25036488d2f7f24c1691d36239f3f34caf0cb
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802928"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a><span data-ttu-id="39f82-103">Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.6 (noviembre de 2019)</span><span class="sxs-lookup"><span data-stu-id="39f82-103">What's new or changed in Dynamics 365 Supply Chain Management 10.0.6 (November 2019)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39f82-104">En este tema se describen las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span><span class="sxs-lookup"><span data-stu-id="39f82-104">This topic describes features that are either new or changed in Microsoft Dynamics 365 Supply Chain Management 10.0.6.</span></span> <span data-ttu-id="39f82-105">El número de compilación de esta versión es 10.0.234.</span><span class="sxs-lookup"><span data-stu-id="39f82-105">This version has a build number of 10.0.234.</span></span> <span data-ttu-id="39f82-106">Aunque la fecha de disponibilidad general cae en noviembre, las nuevas características están disponibles para un lanzamiento anticipado en octubre.</span><span class="sxs-lookup"><span data-stu-id="39f82-106">While the general availability date is in November, the new features are available for early release in October.</span></span> <span data-ttu-id="39f82-107">Para obtener más información sobre la versión 10.0.6, consulte [Recursos adicionales](whats-new-scm-10-0-6.md#additional-resources).</span><span class="sxs-lookup"><span data-stu-id="39f82-107">For more information about version 10.0.6, see [Additional resources](whats-new-scm-10-0-6.md#additional-resources).</span></span>

## <a name="product-configuration-models-v2-data-entity"></a><span data-ttu-id="39f82-108">Entidad de datos "modelos de configuración de producto V2"</span><span class="sxs-lookup"><span data-stu-id="39f82-108">Product configuration models V2 data entity</span></span>

<span data-ttu-id="39f82-109">Se lanza una segunda versión de la entidad de datos "modelos de configuración de producto" (llamada "modelos de configuración de producto V2").</span><span class="sxs-lookup"><span data-stu-id="39f82-109">A second version for the "product configuration models" data entity is released (called "products configuration models V2").</span></span> <span data-ttu-id="39f82-110">La plantilla predeterminada "418-modelos de configuración de producto" también debe ser así para que use la nueva entidad de datos "modelos de configuración de producto V2" en las plantillas de marco de importación/exportación.</span><span class="sxs-lookup"><span data-stu-id="39f82-110">The default template "418-product configuration models" is also needs to be so that it uses the new "product configuration models V2" data entity in the import/export framework templates.</span></span> <span data-ttu-id="39f82-111">La plantilla no se actualizará automáticamente, por lo que tendrá que cargarla desde la predeterminada manualmente.</span><span class="sxs-lookup"><span data-stu-id="39f82-111">The template will not be auto-updated so that you will have to load the template from the default manually.</span></span> <span data-ttu-id="39f82-112">La entidad V2 exporta una fila como un archivo independiente en un archivo adjunto en lugar de en línea, solucionando así las limitaciones de tamaño de la entidad V1.</span><span class="sxs-lookup"><span data-stu-id="39f82-112">The V2 entity exports one row as separate file in an attachment instead of inline, solving the size limitations of the V1 entity.</span></span> 
 
<span data-ttu-id="39f82-113">¿Qué tengo que hacer para incorporar este cambio?</span><span class="sxs-lookup"><span data-stu-id="39f82-113">What do you need to do to take this change?</span></span>
-    <span data-ttu-id="39f82-114">Como la entidad V1 ha quedado en desuso, debe iniciar la migración de V1 a V2.</span><span class="sxs-lookup"><span data-stu-id="39f82-114">As the V1 entity has been deprecated, you should start migrating from V1 to V2.</span></span> <span data-ttu-id="39f82-115">Si utiliza la plantilla "418-modelos de configuración de producto", puede hacer clic en el botón "cargar plantillas predeterminadas" y volver a cargar la plantilla "418-modelos de configuración de producto"</span><span class="sxs-lookup"><span data-stu-id="39f82-115">If you are using the  "418-product configuration models" template, you can click on "load default templates" button and reload the template "418 – product configuration models"</span></span>
-    <span data-ttu-id="39f82-116">Si necesita mantener la compatibilidad con los sistemas existentes, puede seguir utilizando la plantilla existente y la entidad V1 (en desuso) hasta que migre sus integraciones a la nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="39f82-116">If you need to keep compatibility with existing systems, you can for now continue using the existing template and the (deprecated) V1 entity until you move your integrations to the new template.</span></span> 

## <a name="feature-management-enhancements"></a><span data-ttu-id="39f82-117">Mejoras de la administración de características</span><span class="sxs-lookup"><span data-stu-id="39f82-117">Feature management enhancements</span></span>
<span data-ttu-id="39f82-118">Ahora la administración de características le permite habilitar todas las características de manera predeterminada, solicitar confirmación para habilitar una característica y habilitar todas las características que aún no se han habilitado.</span><span class="sxs-lookup"><span data-stu-id="39f82-118">Feature management now allows you to enable all new features by default, require confirmation to enable a feature, and enable all features that have not already been enabled.</span></span> 


## <a name="purchase-agreement-responsible-party"></a><span data-ttu-id="39f82-119">Parte responsable del acuerdo de compra</span><span class="sxs-lookup"><span data-stu-id="39f82-119">Purchase agreement responsible party</span></span>
<span data-ttu-id="39f82-120">Ahora tiene la capacidad de definir las partes responsables principal y secundarias en el formulario de clasificación del acuerdo de compra y los acuerdos de compra derivados.</span><span class="sxs-lookup"><span data-stu-id="39f82-120">You now have the ability to define primary and secondary responsible parties on the Purchase agreement classification form and resulting Purchase agreements.</span></span>  <span data-ttu-id="39f82-121">Esto proporciona al usuario acceso a quién supervisa los acuerdos.</span><span class="sxs-lookup"><span data-stu-id="39f82-121">This provides the user access to who oversees the agreements.</span></span>

## <a name="rfq-link-on-the-purchase-order-line"></a><span data-ttu-id="39f82-122">Vínculo de solicitud de presupuesto en la línea de pedido de compra</span><span class="sxs-lookup"><span data-stu-id="39f82-122">RFQ link on the Purchase order line</span></span>
<span data-ttu-id="39f82-123">Puede agregar un vínculo de referencia desde las líneas de pedido de compra a las líneas de solicitud de presupuesto correspondientes de las que se originaron, lo que permite al usuario recibir fácilmente el documento de solicitud de presupuesto correspondiente.</span><span class="sxs-lookup"><span data-stu-id="39f82-123">You can add a reference link from the Purchase order lines back to the corresponding RFQ lines they originated from, allowing the user to easily be provided with the supporting request for quotation document.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39f82-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="39f82-124">Additional resources</span></span>

### <a name="bug-fixes"></a><span data-ttu-id="39f82-125">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="39f82-125">Bug fixes</span></span>
<span data-ttu-id="39f82-126">Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.6, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span><span class="sxs-lookup"><span data-stu-id="39f82-126">For information about the bug fixes included in each of the updates that are part of 10.0.6, sign in to Lifecycle Services (LCS) and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).</span></span>

### <a name="platform-update-30"></a><span data-ttu-id="39f82-127">Platform update 30</span><span class="sxs-lookup"><span data-stu-id="39f82-127">Platform update 30</span></span>
<span data-ttu-id="39f82-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 incluye la Platform update 30.</span><span class="sxs-lookup"><span data-stu-id="39f82-128">Microsoft Dynamics 365 Supply Chain Management 10.0.6 includes Platform update 30.</span></span> <span data-ttu-id="39f82-129">Para obtener más información sobre la Platform update 30, consulte [Novedades y cambios en la Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span><span class="sxs-lookup"><span data-stu-id="39f82-129">To learn more about Platform update 30, see [What's new or changed in Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).</span></span>

### <a name="dynamics-365-2019-release-wave-2-plan"></a><span data-ttu-id="39f82-130">Dynamics 365: segunda oleada de lanzamiento de versiones de 2019</span><span class="sxs-lookup"><span data-stu-id="39f82-130">Dynamics 365: 2019 release wave 2 plan</span></span>
<span data-ttu-id="39f82-131">¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?</span><span class="sxs-lookup"><span data-stu-id="39f82-131">Wondering about upcoming and recently released capabilities in any of our business apps or platform?</span></span>

<span data-ttu-id="39f82-132">Consulte [Dynamics 365: plan de la segunda oleada de lanzamiento de versiones de 2019](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span><span class="sxs-lookup"><span data-stu-id="39f82-132">Check out the [Dynamics 365: 2019 release wave 2 plan](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/).</span></span> <span data-ttu-id="39f82-133">Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.</span><span class="sxs-lookup"><span data-stu-id="39f82-133">We've captured all the details, end to end, top to bottom, in a single document that you can use for planning.</span></span>

### <a name="removed-and-deprecated-supply-chain-management-features"></a><span data-ttu-id="39f82-134">Características de Supply Chain Management quitadas o en desuso</span><span class="sxs-lookup"><span data-stu-id="39f82-134">Removed and deprecated Supply Chain Management features</span></span>

<span data-ttu-id="39f82-135">En el tema [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) se describen las características que se han quitado o cuya eliminación o puesta en desuso están programadas para Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="39f82-135">The [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic describes features that have been or are scheduled to be removed or deprecated for Supply Chain Management.</span></span>

- <span data-ttu-id="39f82-136">Una característica *quitada* dejará de estar disponible en el producto.</span><span class="sxs-lookup"><span data-stu-id="39f82-136">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="39f82-137">Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.</span><span class="sxs-lookup"><span data-stu-id="39f82-137">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="39f82-138">Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el tema [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes de su eliminación.</span><span class="sxs-lookup"><span data-stu-id="39f82-138">Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) topic 12 months prior to the removal.</span></span>

<span data-ttu-id="39f82-139">Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses.</span><span class="sxs-lookup"><span data-stu-id="39f82-139">For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months.</span></span> <span data-ttu-id="39f82-140">Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.</span><span class="sxs-lookup"><span data-stu-id="39f82-140">Typically, these are functional updates that need to be made to the compiler.</span></span>

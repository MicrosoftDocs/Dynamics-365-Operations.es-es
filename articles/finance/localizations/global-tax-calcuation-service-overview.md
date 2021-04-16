---
title: Servicio de cálculo de impuestos (versión preliminar)
description: Este tema explica el alcance general y las características del servicio de cálculo de impuestos.
author: wangchen
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818233"
---
# <a name="tax-calculation-service-preview"></a><span data-ttu-id="6371e-103">Servicio de cálculo de impuestos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="6371e-103">Tax calculation service (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="6371e-104">El servicio de cálculo de impuestos es un servicio multiinquilino hiperescalable que permite que el motor de impuestos global automatice y simplifique el proceso de determinación y cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6371e-104">The tax calculation service is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="6371e-105">El motor de impuestos es completamente configurable.</span><span class="sxs-lookup"><span data-stu-id="6371e-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="6371e-106">Los elementos que se pueden configurar incluyen, entre otros, el modelo de datos imponibles, el código impositivo, la matriz de aplicabilidad impositiva y la fórmula de cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6371e-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="6371e-107">El motor de impuestos se ejecuta en la plataforma de servicios centrales de Microsoft Azure y ofrece tecnología moderna y escalabilidad exponencial.</span><span class="sxs-lookup"><span data-stu-id="6371e-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="6371e-108">El servicio de cálculo de impuestos se integra con Dynamics 365 Finance y Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6371e-108">The tax calculation service integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="6371e-109">Posteriormente, también se integrará con Dynamics 365 Project Operations, Dynamics 365 Commerce y otras aplicaciones propias y de terceros.</span><span class="sxs-lookup"><span data-stu-id="6371e-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="6371e-110">El servicio de cálculo de impuestos es un motor de impuestos basado en Microsoft que ofrece una escalabilidad exponencial.</span><span class="sxs-lookup"><span data-stu-id="6371e-110">The tax calculation service is a Microsoft-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="6371e-111">Puede ayudarle a llevar a cabo las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="6371e-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="6371e-112">Configure el servicio de cálculo de impuestos a través del Servicio de Configuración Regulatoria (RCS).</span><span class="sxs-lookup"><span data-stu-id="6371e-112">Configure the tax calculation service through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="6371e-113">RCS es una versión mejorada del diseñador de informes electrónicos (ER) y está disponible como un servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="6371e-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="6371e-114">Configure la matriz de impuestos para determinar automáticamente los códigos y los tipos impositivos.</span><span class="sxs-lookup"><span data-stu-id="6371e-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="6371e-115">Configure la matriz de impuestos para determinar automáticamente el número de registro de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6371e-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="6371e-116">Configure el diseñador de cálculo de impuestos para definir fórmulas y condiciones.</span><span class="sxs-lookup"><span data-stu-id="6371e-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="6371e-117">Comparta la solución de determinación y cálculo de impuestos entre entidades legales.</span><span class="sxs-lookup"><span data-stu-id="6371e-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="6371e-118">Para utilizar el servicio de cálculo de impuestos, instale el complemento del servicio de cálculo de impuestos de su proyecto en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="6371e-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="6371e-119">Luego, complete la configuración en RCS y habilite el servicio de cálculo de impuestos en Finance y Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6371e-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="6371e-120">Para obtener más información, vea [Introducción al servicio de impuestos](https://go.microsoft.com/fwlink/?linkid=2138482).</span><span class="sxs-lookup"><span data-stu-id="6371e-120">For more information, see [Get started with tax service](https://go.microsoft.com/fwlink/?linkid=2138482).</span></span>

## <a name="availability"></a><span data-ttu-id="6371e-121">Disponibilidad</span><span class="sxs-lookup"><span data-stu-id="6371e-121">Availability</span></span>

<span data-ttu-id="6371e-122">El servicio de cálculo de impuestos está disponible solo en entornos de espacio aislado y para clientes seleccionados, a través de un programa en versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="6371e-122">The tax calculation service is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="6371e-123">Con el tiempo, estará disponible de manera general para todos los clientes y en entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="6371e-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="6371e-124">Se seguirán proporcionando nuevas funciones en el servicio de cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6371e-124">New features will continue to be delivered in the tax calculation service.</span></span> <span data-ttu-id="6371e-125">Por lo tanto, asegúrese de consultar la documentación más actualizada con frecuencia, para conocer la cobertura y el alcance de las características compatibles.</span><span class="sxs-lookup"><span data-stu-id="6371e-125">Therefore, be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="6371e-126">El servicio de cálculo de impuestos está implementado en las siguientes geografías de Azure.</span><span class="sxs-lookup"><span data-stu-id="6371e-126">The tax calculation service is deployed in the following Azure geographies.</span></span> <span data-ttu-id="6371e-127">También se implementará en más geografías de Azure, según las necesidades del cliente:</span><span class="sxs-lookup"><span data-stu-id="6371e-127">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="6371e-128">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="6371e-128">United States</span></span>
- <span data-ttu-id="6371e-129">Europa</span><span class="sxs-lookup"><span data-stu-id="6371e-129">Europe</span></span>
- <span data-ttu-id="6371e-130">Francia</span><span class="sxs-lookup"><span data-stu-id="6371e-130">France</span></span>
- <span data-ttu-id="6371e-131">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="6371e-131">United Kingdom</span></span>

> [!NOTE]
> <span data-ttu-id="6371e-132">El servicio de cálculo de impuestos no admite implementaciones locales de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6371e-132">The tax calculation service doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="6371e-133">Tampoco es compatible con versiones anteriores, como Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="6371e-133">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="6371e-134">Características destacadas</span><span class="sxs-lookup"><span data-stu-id="6371e-134">Feature highlights</span></span>

- <span data-ttu-id="6371e-135">Una matriz de impuestos configurable para determinar automáticamente y calcular los impuestos</span><span class="sxs-lookup"><span data-stu-id="6371e-135">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="6371e-136">Compatibilidad con múltiples números de registro del impuesto sobre el valor añadido (IVA)</span><span class="sxs-lookup"><span data-stu-id="6371e-136">Support for multiple value-added tax (VAT) registration numbers</span></span>
- <span data-ttu-id="6371e-137">Compatibilidad de órdenes de transferencia para la determinación y cálculo de impuestos</span><span class="sxs-lookup"><span data-stu-id="6371e-137">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="6371e-138">Compatibilidad de órdenes de transferencia para la determinación de múltiples números de registro de IVA</span><span class="sxs-lookup"><span data-stu-id="6371e-138">Transfer order support for determination of multiple VAT registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="6371e-139">Transacciones admitidas</span><span class="sxs-lookup"><span data-stu-id="6371e-139">Supported transactions</span></span>

<span data-ttu-id="6371e-140">El servicio de cálculo de impuestos puede habilitarse por entidad legal y transacción.</span><span class="sxs-lookup"><span data-stu-id="6371e-140">The tax calculation service can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="6371e-141">Se admiten las siguientes transacciones:</span><span class="sxs-lookup"><span data-stu-id="6371e-141">The following transactions are supported:</span></span>

- <span data-ttu-id="6371e-142">Proceso de ventas</span><span class="sxs-lookup"><span data-stu-id="6371e-142">Sales process</span></span>

    - <span data-ttu-id="6371e-143">Presupuesto de ventas</span><span class="sxs-lookup"><span data-stu-id="6371e-143">Sales quotation</span></span>
    - <span data-ttu-id="6371e-144">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="6371e-144">Sales order</span></span>
    - <span data-ttu-id="6371e-145">Confirmación</span><span class="sxs-lookup"><span data-stu-id="6371e-145">Confirmation</span></span>
    - <span data-ttu-id="6371e-146">Lista de selección</span><span class="sxs-lookup"><span data-stu-id="6371e-146">Picking list</span></span>
    - <span data-ttu-id="6371e-147">Traslado</span><span class="sxs-lookup"><span data-stu-id="6371e-147">Packing slip</span></span>
    - <span data-ttu-id="6371e-148">Factura de ventas</span><span class="sxs-lookup"><span data-stu-id="6371e-148">Sales invoice</span></span>
    - <span data-ttu-id="6371e-149">Factura rectificativa</span><span class="sxs-lookup"><span data-stu-id="6371e-149">Credit note</span></span>
    - <span data-ttu-id="6371e-150">Pedido de devolución</span><span class="sxs-lookup"><span data-stu-id="6371e-150">Return order</span></span>
    - <span data-ttu-id="6371e-151">Cargo misceláneo de encabezado</span><span class="sxs-lookup"><span data-stu-id="6371e-151">Header miscellaneous charge</span></span>
    - <span data-ttu-id="6371e-152">Cargo misceláneo de línea</span><span class="sxs-lookup"><span data-stu-id="6371e-152">Line miscellaneous charge</span></span>

- <span data-ttu-id="6371e-153">Proceso de compra</span><span class="sxs-lookup"><span data-stu-id="6371e-153">Purchase process</span></span>

    - <span data-ttu-id="6371e-154">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="6371e-154">Purchase order</span></span>
    - <span data-ttu-id="6371e-155">Confirmación</span><span class="sxs-lookup"><span data-stu-id="6371e-155">Confirmation</span></span>
    - <span data-ttu-id="6371e-156">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="6371e-156">Receipts list</span></span>
    - <span data-ttu-id="6371e-157">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="6371e-157">Product receipt</span></span>
    - <span data-ttu-id="6371e-158">Factura de compra</span><span class="sxs-lookup"><span data-stu-id="6371e-158">Purchase invoice</span></span>
    - <span data-ttu-id="6371e-159">Cargo misceláneo de encabezado</span><span class="sxs-lookup"><span data-stu-id="6371e-159">Header miscellaneous charge</span></span>
    - <span data-ttu-id="6371e-160">Cargo misceláneo de línea</span><span class="sxs-lookup"><span data-stu-id="6371e-160">Line miscellaneous charge</span></span>
    - <span data-ttu-id="6371e-161">Factura rectificativa</span><span class="sxs-lookup"><span data-stu-id="6371e-161">Credit note</span></span>
    - <span data-ttu-id="6371e-162">Pedido de devolución</span><span class="sxs-lookup"><span data-stu-id="6371e-162">Return order</span></span>
    - <span data-ttu-id="6371e-163">Solicitud de compra</span><span class="sxs-lookup"><span data-stu-id="6371e-163">Purchase requisition</span></span>
    - <span data-ttu-id="6371e-164">Cargo misceláneo de línea de solicitud de compra</span><span class="sxs-lookup"><span data-stu-id="6371e-164">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="6371e-165">Solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="6371e-165">Request for quotation</span></span>
    - <span data-ttu-id="6371e-166">Cargo misceláneo de encabezado de solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="6371e-166">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="6371e-167">Cargo misceláneo de línea de solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="6371e-167">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="6371e-168">Proceso de inventario</span><span class="sxs-lookup"><span data-stu-id="6371e-168">Inventory process</span></span>

    - <span data-ttu-id="6371e-169">Pedido de transferencia: envío</span><span class="sxs-lookup"><span data-stu-id="6371e-169">Transfer order – ship</span></span>
    - <span data-ttu-id="6371e-170">Pedido de transferencia: recepción</span><span class="sxs-lookup"><span data-stu-id="6371e-170">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="6371e-171">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="6371e-171">Related resources</span></span>

[<span data-ttu-id="6371e-172">Introducción al servicio de impuestos</span><span class="sxs-lookup"><span data-stu-id="6371e-172">Get started with tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138482)

[<span data-ttu-id="6371e-173">Número de registro de IVA múltiple</span><span class="sxs-lookup"><span data-stu-id="6371e-173">Multiple VAT registration number</span></span>](https://go.microsoft.com/fwlink/?linkid=2153387)

[<span data-ttu-id="6371e-174">Compatibilidad de la característica de impuestos para pedidos de transferencia</span><span class="sxs-lookup"><span data-stu-id="6371e-174">Tax feature support for transfer order</span></span>](https://go.microsoft.com/fwlink/?linkid=2153388)

[<span data-ttu-id="6371e-175">Cómo crear una extensión en el servicio de impuestos</span><span class="sxs-lookup"><span data-stu-id="6371e-175">How to build extension in tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138483)

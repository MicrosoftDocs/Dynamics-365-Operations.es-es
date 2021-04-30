---
title: Cálculo de impuestos (versión preliminar)
description: Este tema explica el alcance general y las características de la funcionalidad de cálculo de impuestos.
author: wangchen
ms.date: 04/12/2021
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
ms.openlocfilehash: 3df952e0632807e55f176e63dc2047be5e622ec2
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892358"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="a64ae-103">Cálculo de impuestos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="a64ae-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="a64ae-104">El cálculo de impuestos es un servicio multiinquilino hiperescalable que permite que Global Tax Engine automatice y simplifique el proceso de determinación y cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="a64ae-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="a64ae-105">El motor de impuestos es completamente configurable.</span><span class="sxs-lookup"><span data-stu-id="a64ae-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="a64ae-106">Los elementos que se pueden configurar incluyen, entre otros, el modelo de datos imponibles, el código impositivo, la matriz de aplicabilidad impositiva y la fórmula de cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="a64ae-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="a64ae-107">El motor de impuestos se ejecuta en la plataforma de servicios centrales de Microsoft Azure y ofrece tecnología moderna y escalabilidad exponencial.</span><span class="sxs-lookup"><span data-stu-id="a64ae-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="a64ae-108">El cálculo de impuestos se integra con Dynamics 365 Finance y Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a64ae-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="a64ae-109">Posteriormente, también se integrará con Dynamics 365 Project Operations, Dynamics 365 Commerce y otras aplicaciones propias y de terceros.</span><span class="sxs-lookup"><span data-stu-id="a64ae-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="a64ae-110">El cálculo de impuestos es un motor de impuestos basado en microservicio que ofrece una escalabilidad exponencial.</span><span class="sxs-lookup"><span data-stu-id="a64ae-110">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="a64ae-111">Puede ayudarle a llevar a cabo las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a64ae-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="a64ae-112">Configure el cálculo de impuestos a través del Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="a64ae-112">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="a64ae-113">RCS es una versión mejorada del diseñador de informes electrónicos (ER) y está disponible como un servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="a64ae-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="a64ae-114">Configure la matriz de impuestos para determinar automáticamente los códigos y los tipos impositivos.</span><span class="sxs-lookup"><span data-stu-id="a64ae-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="a64ae-115">Configure la matriz de impuestos para determinar automáticamente el número de registro de impuestos.</span><span class="sxs-lookup"><span data-stu-id="a64ae-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="a64ae-116">Configure el diseñador de cálculo de impuestos para definir fórmulas y condiciones.</span><span class="sxs-lookup"><span data-stu-id="a64ae-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="a64ae-117">Comparta la solución de determinación y cálculo de impuestos entre entidades legales.</span><span class="sxs-lookup"><span data-stu-id="a64ae-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="a64ae-118">Para utilizar el servicio de cálculo de impuestos, instale el complemento del servicio de cálculo de impuestos de su proyecto en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="a64ae-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="a64ae-119">Luego, complete la configuración en RCS y habilite el servicio de cálculo de impuestos en Finance y Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a64ae-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="a64ae-120">Para obtener más información, vea [Introducción al servicio de impuestos](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="a64ae-120">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="a64ae-121">Disponibilidad</span><span class="sxs-lookup"><span data-stu-id="a64ae-121">Availability</span></span>

<span data-ttu-id="a64ae-122">El cálculo de impuestos está disponible solo en entornos de espacio aislado y para clientes seleccionados, a través de un programa en versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="a64ae-122">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="a64ae-123">Con el tiempo, estará disponible de manera general para todos los clientes y en entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="a64ae-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="a64ae-124">Se seguirán entregando nuevas características, por lo que asegúrese de consultar la documentación más actualizada con frecuencia, para conocer la cobertura y el alcance de las características compatibles.</span><span class="sxs-lookup"><span data-stu-id="a64ae-124">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="a64ae-125">El cálculo de impuestos está implementado en las siguientes geografías de Azure.</span><span class="sxs-lookup"><span data-stu-id="a64ae-125">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="a64ae-126">También se implementará en más geografías de Azure, según las necesidades del cliente:</span><span class="sxs-lookup"><span data-stu-id="a64ae-126">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="a64ae-127">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="a64ae-127">United States</span></span>
- <span data-ttu-id="a64ae-128">Europa</span><span class="sxs-lookup"><span data-stu-id="a64ae-128">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="a64ae-129">El cálculo de impuestos no admite implementaciones locales de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a64ae-129">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="a64ae-130">Tampoco es compatible con versiones anteriores, como Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="a64ae-130">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="a64ae-131">Características destacadas</span><span class="sxs-lookup"><span data-stu-id="a64ae-131">Feature highlights</span></span>

- <span data-ttu-id="a64ae-132">Una matriz de impuestos configurable para determinar automáticamente y calcular los impuestos</span><span class="sxs-lookup"><span data-stu-id="a64ae-132">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="a64ae-133">Compatibilidad con múltiples números de registro del impuesto</span><span class="sxs-lookup"><span data-stu-id="a64ae-133">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="a64ae-134">Compatibilidad de órdenes de transferencia para la determinación y cálculo de impuestos</span><span class="sxs-lookup"><span data-stu-id="a64ae-134">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="a64ae-135">Compatibilidad de órdenes de transferencia para la determinación de múltiples números de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="a64ae-135">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="a64ae-136">Transacciones admitidas</span><span class="sxs-lookup"><span data-stu-id="a64ae-136">Supported transactions</span></span>

<span data-ttu-id="a64ae-137">El cálculo de impuestos puede habilitarse por entidad legal y transacción.</span><span class="sxs-lookup"><span data-stu-id="a64ae-137">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="a64ae-138">Se admiten las siguientes transacciones:</span><span class="sxs-lookup"><span data-stu-id="a64ae-138">The following transactions are supported:</span></span>

- <span data-ttu-id="a64ae-139">Proceso de ventas</span><span class="sxs-lookup"><span data-stu-id="a64ae-139">Sales process</span></span>

    - <span data-ttu-id="a64ae-140">Presupuesto de ventas</span><span class="sxs-lookup"><span data-stu-id="a64ae-140">Sales quotation</span></span>
    - <span data-ttu-id="a64ae-141">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="a64ae-141">Sales order</span></span>
    - <span data-ttu-id="a64ae-142">Confirmación</span><span class="sxs-lookup"><span data-stu-id="a64ae-142">Confirmation</span></span>
    - <span data-ttu-id="a64ae-143">Lista de selección</span><span class="sxs-lookup"><span data-stu-id="a64ae-143">Picking list</span></span>
    - <span data-ttu-id="a64ae-144">Traslado</span><span class="sxs-lookup"><span data-stu-id="a64ae-144">Packing slip</span></span>
    - <span data-ttu-id="a64ae-145">Factura de ventas</span><span class="sxs-lookup"><span data-stu-id="a64ae-145">Sales invoice</span></span>
    - <span data-ttu-id="a64ae-146">Factura rectificativa</span><span class="sxs-lookup"><span data-stu-id="a64ae-146">Credit note</span></span>
    - <span data-ttu-id="a64ae-147">Pedido de devolución</span><span class="sxs-lookup"><span data-stu-id="a64ae-147">Return order</span></span>
    - <span data-ttu-id="a64ae-148">Cargo misceláneo de encabezado</span><span class="sxs-lookup"><span data-stu-id="a64ae-148">Header miscellaneous charge</span></span>
    - <span data-ttu-id="a64ae-149">Cargo misceláneo de línea</span><span class="sxs-lookup"><span data-stu-id="a64ae-149">Line miscellaneous charge</span></span>

- <span data-ttu-id="a64ae-150">Proceso de compra</span><span class="sxs-lookup"><span data-stu-id="a64ae-150">Purchase process</span></span>

    - <span data-ttu-id="a64ae-151">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="a64ae-151">Purchase order</span></span>
    - <span data-ttu-id="a64ae-152">Confirmación</span><span class="sxs-lookup"><span data-stu-id="a64ae-152">Confirmation</span></span>
    - <span data-ttu-id="a64ae-153">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="a64ae-153">Receipts list</span></span>
    - <span data-ttu-id="a64ae-154">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="a64ae-154">Product receipt</span></span>
    - <span data-ttu-id="a64ae-155">Factura de compra</span><span class="sxs-lookup"><span data-stu-id="a64ae-155">Purchase invoice</span></span>
    - <span data-ttu-id="a64ae-156">Cargo misceláneo de encabezado</span><span class="sxs-lookup"><span data-stu-id="a64ae-156">Header miscellaneous charge</span></span>
    - <span data-ttu-id="a64ae-157">Cargo misceláneo de línea</span><span class="sxs-lookup"><span data-stu-id="a64ae-157">Line miscellaneous charge</span></span>
    - <span data-ttu-id="a64ae-158">Factura rectificativa</span><span class="sxs-lookup"><span data-stu-id="a64ae-158">Credit note</span></span>
    - <span data-ttu-id="a64ae-159">Pedido de devolución</span><span class="sxs-lookup"><span data-stu-id="a64ae-159">Return order</span></span>
    - <span data-ttu-id="a64ae-160">Solicitud de compra</span><span class="sxs-lookup"><span data-stu-id="a64ae-160">Purchase requisition</span></span>
    - <span data-ttu-id="a64ae-161">Cargo misceláneo de línea de solicitud de compra</span><span class="sxs-lookup"><span data-stu-id="a64ae-161">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="a64ae-162">Solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="a64ae-162">Request for quotation</span></span>
    - <span data-ttu-id="a64ae-163">Cargo misceláneo de encabezado de solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="a64ae-163">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="a64ae-164">Cargo misceláneo de línea de solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="a64ae-164">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="a64ae-165">Proceso de inventario</span><span class="sxs-lookup"><span data-stu-id="a64ae-165">Inventory process</span></span>

    - <span data-ttu-id="a64ae-166">Pedido de transferencia: envío</span><span class="sxs-lookup"><span data-stu-id="a64ae-166">Transfer order – ship</span></span>
    - <span data-ttu-id="a64ae-167">Pedido de transferencia: recepción</span><span class="sxs-lookup"><span data-stu-id="a64ae-167">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="a64ae-168">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="a64ae-168">Related resources</span></span>

[<span data-ttu-id="a64ae-169">Introducción al servicio de impuestos</span><span class="sxs-lookup"><span data-stu-id="a64ae-169">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="a64ae-170">Número de registro de IVA múltiple</span><span class="sxs-lookup"><span data-stu-id="a64ae-170">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="a64ae-171">Compatibilidad de la característica de impuestos para pedidos de transferencia</span><span class="sxs-lookup"><span data-stu-id="a64ae-171">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="a64ae-172">Cómo crear una extensión en el servicio de impuestos</span><span class="sxs-lookup"><span data-stu-id="a64ae-172">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)
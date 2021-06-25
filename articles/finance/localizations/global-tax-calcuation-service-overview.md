---
title: Cálculo de impuestos (versión preliminar)
description: Este tema explica el alcance general y las características de la funcionalidad de cálculo de impuestos.
author: wangchen
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9daa6e001200d03a2639974fb6de618d77ddf09d
ms.sourcegitcommit: cb282e8d2306ab71adf80a84346a6863d2d019e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184110"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="feef0-103">Cálculo de impuestos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="feef0-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="feef0-104">El cálculo de impuestos es un servicio multiinquilino hiperescalable que permite que Global Tax Engine automatice y simplifique el proceso de determinación y cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="feef0-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="feef0-105">El motor de impuestos es completamente configurable.</span><span class="sxs-lookup"><span data-stu-id="feef0-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="feef0-106">Los elementos que se pueden configurar incluyen, entre otros, el modelo de datos imponibles, el código impositivo, la matriz de aplicabilidad impositiva y la fórmula de cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="feef0-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="feef0-107">El motor de impuestos se ejecuta en la plataforma de servicios centrales de Microsoft Azure y ofrece tecnología moderna y escalabilidad exponencial.</span><span class="sxs-lookup"><span data-stu-id="feef0-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="feef0-108">El cálculo de impuestos se integra con Dynamics 365 Finance y Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="feef0-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="feef0-109">Posteriormente, también se integrará con Dynamics 365 Project Operations, Dynamics 365 Commerce y otras aplicaciones propias y de terceros.</span><span class="sxs-lookup"><span data-stu-id="feef0-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="feef0-110">Cuando habilita el servicio de cálculo de impuestos, es posible que algunas operaciones con datos relacionados se realicen en un centro de datos que no sea el centro de datos que mantiene los datos del servicio.</span><span class="sxs-lookup"><span data-stu-id="feef0-110">When you enable the Tax Calculation service, some operations on related data might be performed in a data center other than the data center that maintains your service data.</span></span> <span data-ttu-id="feef0-111">Revise los [Términos y condiciones](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) antes de habilitar el servicio de cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="feef0-111">Review the [Terms and Conditions](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) before you enable the Tax Calculation service.</span></span> <span data-ttu-id="feef0-112">Su privacidad es importante para nosotros.</span><span class="sxs-lookup"><span data-stu-id="feef0-112">Your privacy is important to us.</span></span> <span data-ttu-id="feef0-113">Para obtener más información, lea nuestra [Declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=521839).</span><span class="sxs-lookup"><span data-stu-id="feef0-113">To learn more, read our [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839).</span></span>

<span data-ttu-id="feef0-114">El cálculo de impuestos es un motor de impuestos basado en microservicio que ofrece una escalabilidad exponencial.</span><span class="sxs-lookup"><span data-stu-id="feef0-114">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="feef0-115">Puede ayudarle a llevar a cabo las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="feef0-115">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="feef0-116">Configure el cálculo de impuestos a través del Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="feef0-116">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="feef0-117">RCS es una versión mejorada del diseñador de informes electrónicos (ER) y está disponible como un servicio independiente.</span><span class="sxs-lookup"><span data-stu-id="feef0-117">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="feef0-118">Configure la matriz de impuestos para determinar automáticamente los códigos y los tipos impositivos.</span><span class="sxs-lookup"><span data-stu-id="feef0-118">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="feef0-119">Configure la matriz de impuestos para determinar automáticamente el número de registro de impuestos.</span><span class="sxs-lookup"><span data-stu-id="feef0-119">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="feef0-120">Configure el diseñador de cálculo de impuestos para definir fórmulas y condiciones.</span><span class="sxs-lookup"><span data-stu-id="feef0-120">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="feef0-121">Comparta la solución de determinación y cálculo de impuestos entre entidades legales.</span><span class="sxs-lookup"><span data-stu-id="feef0-121">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="feef0-122">Para utilizar el servicio de cálculo de impuestos, instale el complemento del servicio de cálculo de impuestos de su proyecto en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="feef0-122">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="feef0-123">Luego, complete la configuración en RCS y habilite el servicio de cálculo de impuestos en Finance y Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="feef0-123">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="feef0-124">Para obtener más información, vea [Introducción al servicio de impuestos](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="feef0-124">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="feef0-125">Disponibilidad</span><span class="sxs-lookup"><span data-stu-id="feef0-125">Availability</span></span>

<span data-ttu-id="feef0-126">El cálculo de impuestos está disponible solo en entornos de espacio aislado y para clientes seleccionados, a través de un programa en versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="feef0-126">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="feef0-127">Con el tiempo, estará disponible de manera general para todos los clientes y en entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="feef0-127">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="feef0-128">Se seguirán entregando nuevas características, por lo que asegúrese de consultar la documentación más actualizada con frecuencia, para conocer la cobertura y el alcance de las características compatibles.</span><span class="sxs-lookup"><span data-stu-id="feef0-128">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="feef0-129">El cálculo de impuestos está implementado en las siguientes geografías de Azure.</span><span class="sxs-lookup"><span data-stu-id="feef0-129">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="feef0-130">También se implementará en más geografías de Azure, según las necesidades del cliente:</span><span class="sxs-lookup"><span data-stu-id="feef0-130">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="feef0-131">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="feef0-131">United States</span></span>
- <span data-ttu-id="feef0-132">Europa</span><span class="sxs-lookup"><span data-stu-id="feef0-132">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="feef0-133">El cálculo de impuestos no admite implementaciones locales de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="feef0-133">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="feef0-134">Tampoco es compatible con versiones anteriores, como Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="feef0-134">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="feef0-135">Características destacadas</span><span class="sxs-lookup"><span data-stu-id="feef0-135">Feature highlights</span></span>

- <span data-ttu-id="feef0-136">Una matriz de impuestos configurable para determinar automáticamente y calcular los impuestos</span><span class="sxs-lookup"><span data-stu-id="feef0-136">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="feef0-137">Compatibilidad con múltiples números de registro del impuesto</span><span class="sxs-lookup"><span data-stu-id="feef0-137">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="feef0-138">Compatibilidad de órdenes de transferencia para la determinación y cálculo de impuestos</span><span class="sxs-lookup"><span data-stu-id="feef0-138">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="feef0-139">Compatibilidad de órdenes de transferencia para la determinación de múltiples números de registro de impuestos</span><span class="sxs-lookup"><span data-stu-id="feef0-139">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="feef0-140">Transacciones admitidas</span><span class="sxs-lookup"><span data-stu-id="feef0-140">Supported transactions</span></span>

<span data-ttu-id="feef0-141">El cálculo de impuestos puede habilitarse por entidad legal y transacción.</span><span class="sxs-lookup"><span data-stu-id="feef0-141">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="feef0-142">Se admiten las siguientes transacciones:</span><span class="sxs-lookup"><span data-stu-id="feef0-142">The following transactions are supported:</span></span>

- <span data-ttu-id="feef0-143">Proceso de ventas</span><span class="sxs-lookup"><span data-stu-id="feef0-143">Sales process</span></span>

    - <span data-ttu-id="feef0-144">Presupuesto de ventas</span><span class="sxs-lookup"><span data-stu-id="feef0-144">Sales quotation</span></span>
    - <span data-ttu-id="feef0-145">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="feef0-145">Sales order</span></span>
    - <span data-ttu-id="feef0-146">Confirmación</span><span class="sxs-lookup"><span data-stu-id="feef0-146">Confirmation</span></span>
    - <span data-ttu-id="feef0-147">Lista de selección</span><span class="sxs-lookup"><span data-stu-id="feef0-147">Picking list</span></span>
    - <span data-ttu-id="feef0-148">Traslado</span><span class="sxs-lookup"><span data-stu-id="feef0-148">Packing slip</span></span>
    - <span data-ttu-id="feef0-149">Factura de ventas</span><span class="sxs-lookup"><span data-stu-id="feef0-149">Sales invoice</span></span>
    - <span data-ttu-id="feef0-150">Factura rectificativa</span><span class="sxs-lookup"><span data-stu-id="feef0-150">Credit note</span></span>
    - <span data-ttu-id="feef0-151">Pedido de devolución</span><span class="sxs-lookup"><span data-stu-id="feef0-151">Return order</span></span>
    - <span data-ttu-id="feef0-152">Cargo misceláneo de encabezado</span><span class="sxs-lookup"><span data-stu-id="feef0-152">Header miscellaneous charge</span></span>
    - <span data-ttu-id="feef0-153">Cargo misceláneo de línea</span><span class="sxs-lookup"><span data-stu-id="feef0-153">Line miscellaneous charge</span></span>

- <span data-ttu-id="feef0-154">Proceso de compra</span><span class="sxs-lookup"><span data-stu-id="feef0-154">Purchase process</span></span>

    - <span data-ttu-id="feef0-155">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="feef0-155">Purchase order</span></span>
    - <span data-ttu-id="feef0-156">Confirmación</span><span class="sxs-lookup"><span data-stu-id="feef0-156">Confirmation</span></span>
    - <span data-ttu-id="feef0-157">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="feef0-157">Receipts list</span></span>
    - <span data-ttu-id="feef0-158">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="feef0-158">Product receipt</span></span>
    - <span data-ttu-id="feef0-159">Factura de compra</span><span class="sxs-lookup"><span data-stu-id="feef0-159">Purchase invoice</span></span>
    - <span data-ttu-id="feef0-160">Cargo misceláneo de encabezado</span><span class="sxs-lookup"><span data-stu-id="feef0-160">Header miscellaneous charge</span></span>
    - <span data-ttu-id="feef0-161">Cargo misceláneo de línea</span><span class="sxs-lookup"><span data-stu-id="feef0-161">Line miscellaneous charge</span></span>
    - <span data-ttu-id="feef0-162">Factura rectificativa</span><span class="sxs-lookup"><span data-stu-id="feef0-162">Credit note</span></span>
    - <span data-ttu-id="feef0-163">Pedido de devolución</span><span class="sxs-lookup"><span data-stu-id="feef0-163">Return order</span></span>
    - <span data-ttu-id="feef0-164">Solicitud de compra</span><span class="sxs-lookup"><span data-stu-id="feef0-164">Purchase requisition</span></span>
    - <span data-ttu-id="feef0-165">Cargo misceláneo de línea de solicitud de compra</span><span class="sxs-lookup"><span data-stu-id="feef0-165">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="feef0-166">Solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="feef0-166">Request for quotation</span></span>
    - <span data-ttu-id="feef0-167">Cargo misceláneo de encabezado de solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="feef0-167">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="feef0-168">Cargo misceláneo de línea de solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="feef0-168">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="feef0-169">Proceso de inventario</span><span class="sxs-lookup"><span data-stu-id="feef0-169">Inventory process</span></span>

    - <span data-ttu-id="feef0-170">Pedido de transferencia: envío</span><span class="sxs-lookup"><span data-stu-id="feef0-170">Transfer order – ship</span></span>
    - <span data-ttu-id="feef0-171">Pedido de transferencia: recepción</span><span class="sxs-lookup"><span data-stu-id="feef0-171">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="feef0-172">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="feef0-172">Related resources</span></span>

[<span data-ttu-id="feef0-173">Introducción al servicio de impuestos</span><span class="sxs-lookup"><span data-stu-id="feef0-173">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="feef0-174">Número de registro de IVA múltiple</span><span class="sxs-lookup"><span data-stu-id="feef0-174">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="feef0-175">Compatibilidad de la característica de impuestos para pedidos de transferencia</span><span class="sxs-lookup"><span data-stu-id="feef0-175">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="feef0-176">Cómo crear una extensión en el servicio de impuestos</span><span class="sxs-lookup"><span data-stu-id="feef0-176">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)

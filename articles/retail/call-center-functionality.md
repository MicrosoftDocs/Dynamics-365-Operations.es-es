---
title: Funcionalidad de ventas del centro de llamadas
description: Este tema proporciona una visión general de la funcionalidad de ventas de centro de asistencia telefónica en Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 2e44770af4a30f539e56d38b21c897cacd2707e7
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812348"
---
# <a name="call-center-sales-functionality"></a><span data-ttu-id="cc7bd-103">Funcionalidad de ventas del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="cc7bd-103">Call center sales functionality</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="cc7bd-104">En Dynamics 365 Retail, un centro de llamadas es un tipo de canal minorista que se puede definir en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc7bd-104">In Dynamics 365 Retail, a call center is a type of Retail channel that can be defined in the application.</span></span> <span data-ttu-id="cc7bd-105">La definición de un canal específico para sus entidades de centro de asistencia telefónica permite que el sistema vincule valores predeterminados específicos de datos y los valores predeterminados del procesamiento del pedido a los pedidos de ventas creados por un usuario del canal de centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="cc7bd-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="cc7bd-106">Las características del centro de asistencia telefónica incluyen precio y promociones al por menor avanzados, catálogos, tarjetas regalo, programas de fidelidad, y vales.</span><span class="sxs-lookup"><span data-stu-id="cc7bd-106">Call center features include advanced retail price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="cc7bd-107">Se saca provecho de los pedidos de centro de asistencia telefónica en función de su aplicación de punto de venta (POS) para admitir escenarios de cumplimiento de pedidos transcanales.</span><span class="sxs-lookup"><span data-stu-id="cc7bd-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="cc7bd-108">Es importante tener en cuenta que mientras que el módulo de centro de asistencia telefónica se utiliza en otras sectores que no son de ventas al por menor, la versión actual de la aplicación de centro de asistencia telefónica de Retail no se ha optimizado para su uso en escenarios interempresariales (B2B) de procesamiento de pedidos o los escenarios donde los pedidos tengan una gran cantidad de líneas de ventas.</span><span class="sxs-lookup"><span data-stu-id="cc7bd-108">It's important to note that while the call center module can be utilized by other industries outside of Retail, the current release of the Retail call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large amount of sales lines.</span></span> <span data-ttu-id="cc7bd-109">Se recomienda que los usuarios que desean utilizar el centro de asistencia telefónica para el procesamiento del pedido fuera del procesamiento de transacciones típico de directo a consumidor, tomen el tiempo adecuado para probar y validar que la habilitación de la función del centro de asistencia telefónica va a cubrir las necesidades funcionales y de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cc7bd-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="cc7bd-110">Además de admitir la creación de pedidos, el módulo de centro de asistencia telefónica también proporciona una aplicación de servicio al cliente convivial que hace más fácil que los usuarios localicen cuentas de cliente y revisen todos los datos y atributos relacionados de pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="cc7bd-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="cc7bd-111">La pantalla de servicio al cliente está diseñada para permitir que un usuario pueda obtener acceso rápidamente a los datos relacionados con el pedido que le permitirán atender la mayoría de consultas más habituales relacionadas con pedidos recibidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="cc7bd-111">The customer service screen is designed to enable a user to quickly access order related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="cc7bd-112">Esta página ofrece vínculos a la documentación pertinente relacionada con la configuración, y el uso funcional de las características del centro de asistencia telefónica de Retail.</span><span class="sxs-lookup"><span data-stu-id="cc7bd-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features in Retail.</span></span>


## <a name="configure-the-call-center"></a><span data-ttu-id="cc7bd-113">Configure el centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="cc7bd-113">Configure the call center</span></span>

[<span data-ttu-id="cc7bd-114">Configurar canales del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="cc7bd-114">Set up call center channels</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="cc7bd-115">Configurar el procesamiento de pedidos</span><span class="sxs-lookup"><span data-stu-id="cc7bd-115">Configure order processing</span></span>

[<span data-ttu-id="cc7bd-116">Configuración y trabajo con alertas de fraudes de centro de asistencia telefónica</span><span class="sxs-lookup"><span data-stu-id="cc7bd-116">Set up and work with call center fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="cc7bd-117">Configurar y trabajar con retenciones de pedidos del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="cc7bd-117">Configure and work with call center order holds</span></span>](work-with-order-holds.md)

## <a name="configure-payment-processing"></a><span data-ttu-id="cc7bd-118">Configurar procesamiento de pagos</span><span class="sxs-lookup"><span data-stu-id="cc7bd-118">Configure payment processing</span></span>

[<span data-ttu-id="cc7bd-119">Métodos de pago en centros de llamadas</span><span class="sxs-lookup"><span data-stu-id="cc7bd-119">Payment methods in call centers</span></span>](work-with-payments.md)

## <a name="configure-delivery-modes"></a><span data-ttu-id="cc7bd-120">Configurar modos de entrega</span><span class="sxs-lookup"><span data-stu-id="cc7bd-120">Configure delivery modes</span></span>

[<span data-ttu-id="cc7bd-121">Configurar modos y cargos de entrega del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="cc7bd-121">Configure call center delivery modes and charges</span></span>](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="cc7bd-122">Configurar marketing directo</span><span class="sxs-lookup"><span data-stu-id="cc7bd-122">Configure direct marketing</span></span>

[<span data-ttu-id="cc7bd-123">Catálogos del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="cc7bd-123">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="cc7bd-124">Configurar análisis de novedad, frecuencia y monetario (RFM)</span><span class="sxs-lookup"><span data-stu-id="cc7bd-124">Set up Recency, Frequency, and Monetary (RFM) analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="cc7bd-125">Configurar programas de continuidad</span><span class="sxs-lookup"><span data-stu-id="cc7bd-125">Configure continuity programs</span></span>

[<span data-ttu-id="cc7bd-126">Configurar programas de continuidad para centros de llamadas</span><span class="sxs-lookup"><span data-stu-id="cc7bd-126">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)

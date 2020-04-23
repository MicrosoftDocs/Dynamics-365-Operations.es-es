---
title: Visión general del flujo de trabajo de suscripción
description: Este tema proporciona una visión general del flujo de trabajo de suscripción.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0cb8b86ef0e2a1bd90590c8cc2a20e18e82ef9c6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206597"
---
# <a name="subscription-workflow-overview"></a><span data-ttu-id="f6a70-103">Visión general del flujo de trabajo de suscripción</span><span class="sxs-lookup"><span data-stu-id="f6a70-103">Subscription workflow overview</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f6a70-104">Usted es el administrador de suscripciones para una empresa de iluminación que ofrece suscripciones para el mantenimiento de las instalaciones de luz.</span><span class="sxs-lookup"><span data-stu-id="f6a70-104">You are the subscriptions administrator for a light company that offers subscriptions for lighting rig maintenance.</span></span> <span data-ttu-id="f6a70-105">Un cliente se pone en contacto con la empresa para adquirir una suscripción anual para el mantenimiento de las instalaciones de luz.</span><span class="sxs-lookup"><span data-stu-id="f6a70-105">A customer contacts your company to purchase a yearly subscription for lighting rig maintenance.</span></span>

## <a name="setting-up-subscriptions"></a><span data-ttu-id="f6a70-106">Configuración de suscripciones</span><span class="sxs-lookup"><span data-stu-id="f6a70-106">Setting up subscriptions</span></span>

<span data-ttu-id="f6a70-107">Para configurar una suscripción, en primer lugar debe crear un grupo de suscripciones para el nuevo acuerdo de servicio, o bien comprobar si existe un grupo de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="f6a70-107">To set up a subscription, you must first create a subscription group for the new service agreement or verify that a subscription group exists.</span></span> <span data-ttu-id="f6a70-108">Si ya existe uno, deberá configurarlo para facturar al cliente de forma anual y para acumular los ingresos de ventas todos los meses del año.</span><span class="sxs-lookup"><span data-stu-id="f6a70-108">If a subscription group exists, you must set it up to invoice the customer yearly and to accrue sales revenue every month of the year.</span></span> <span data-ttu-id="f6a70-109">Para obtener más información acerca de la configuración de suscripciones, consulte [Configurar grupos de suscripciones](set-up-subscription-groups.md).</span><span class="sxs-lookup"><span data-stu-id="f6a70-109">For more information about how to set up subscriptions, see [Set up subscription groups](set-up-subscription-groups.md).</span></span>

<span data-ttu-id="f6a70-110">Una vez creado el grupo de suscripciones, podrá crear la suscripción.</span><span class="sxs-lookup"><span data-stu-id="f6a70-110">After the subscription group is created, you can create the subscription.</span></span> <span data-ttu-id="f6a70-111">Para obtener más información sobre cómo crear suscripciones de servicio, consulte [Crear suscripciones servicio desde un grupo de suscripciones](create-service-subscriptions-from-subscription-group.md).</span><span class="sxs-lookup"><span data-stu-id="f6a70-111">For more information about how to create service subscriptions, see [Create service subscriptions from a subscription group](create-service-subscriptions-from-subscription-group.md).</span></span>

## <a name="create-and-modify-subscription-transactions"></a><span data-ttu-id="f6a70-112">Crear y modificar transacciones de suscripción</span><span class="sxs-lookup"><span data-stu-id="f6a70-112">Create and modify subscription transactions</span></span>

<span data-ttu-id="f6a70-113">Una vez configurada la suscripción, deberá crear la transacción de cuota de suscripción para el primer período de facturación, que en este caso será de un año.</span><span class="sxs-lookup"><span data-stu-id="f6a70-113">After you set up the subscription, you create the subscription fee transaction for the first invoicing period, which is one year.</span></span> <span data-ttu-id="f6a70-114">Las transacciones son del tipo **Normal**.</span><span class="sxs-lookup"><span data-stu-id="f6a70-114">The transactions are of the **Regular** type.</span></span> <span data-ttu-id="f6a70-115">Por lo tanto, sólo podrá crear transacciones de suscripción en las que las fecha de inicio y fin se correspondan con los períodos anteriormente creados en el formulario **Tipos de período**.</span><span class="sxs-lookup"><span data-stu-id="f6a70-115">Therefore, you can only create subscription transactions where the from date and the to date correspond to periods that were previously created in the **Period types** form.</span></span> <span data-ttu-id="f6a70-116">Para obtener más información acerca de las transacciones de gastos, vea [Crear transacciones de gastos de suscripción](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="f6a70-116">For more information about fee transactions, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="f6a70-117">Una vez establecida la suscripción para el cliente, recuerda que se negoció un descuento del 10 por ciento para todos los precios de línea de las oferta de servicio.</span><span class="sxs-lookup"><span data-stu-id="f6a70-117">After you set up the subscription for your customer, you remember that they have negotiated a 10 percent discount on all list prices for service offerings.</span></span> <span data-ttu-id="f6a70-118">Por lo tanto, deberá reducir el precio de la cuota de transacción creada.</span><span class="sxs-lookup"><span data-stu-id="f6a70-118">Therefore, you must reduce the price of the transaction fee that you created.</span></span>

<span data-ttu-id="f6a70-119">Más tarde, el contacto del cliente le llama para avisarle de que, aunque aún desean el acuerdo de servicio para las instalaciones de luz, tienen previsto instalar nuevas luces más adelante.</span><span class="sxs-lookup"><span data-stu-id="f6a70-119">Later in the day, your customer contact calls to say that, although they still want the service agreement for the lighting rig, they plan to introduce a new lighting rig later in the year.</span></span> <span data-ttu-id="f6a70-120">Por lo tanto, sólo necesitan una cobertura de mantenimiento hasta octubre de 2013.</span><span class="sxs-lookup"><span data-stu-id="f6a70-120">Therefore, they only need maintenance coverage until October 2013.</span></span> <span data-ttu-id="f6a70-121">Para reducir el número de meses de la suscripción del cliente, crea una nueva transacción de cuota de suscripción del tipo **Días de reducción**.</span><span class="sxs-lookup"><span data-stu-id="f6a70-121">To reduce the number of months for the customer’s subscription, you create a new subscription fee transaction of the **Reduction days** type.</span></span> <span data-ttu-id="f6a70-122">Para obtener más información acerca de cómo reducir días, consulte [Reducir los días de las cuotas de suscripción](reduce-the-days-on-subscription-fees.md).</span><span class="sxs-lookup"><span data-stu-id="f6a70-122">For more information about how to reduce days, see [Reduce the days on subscription fees](reduce-the-days-on-subscription-fees.md).</span></span>

## <a name="invoice-and-accrue-subscription-transactions"></a><span data-ttu-id="f6a70-123">Facturar y acumular transacciones de suscripción</span><span class="sxs-lookup"><span data-stu-id="f6a70-123">Invoice and accrue subscription transactions</span></span>

<span data-ttu-id="f6a70-124">Ha terminado la configuración de la suscripción y está listo para facturársela al cliente.</span><span class="sxs-lookup"><span data-stu-id="f6a70-124">You have now finished setting up the subscription, and you are ready to invoice your customer for it.</span></span> <span data-ttu-id="f6a70-125">Para obtener más información acerca de cómo facturar suscripciones, consulte [Facturar transacciones de suscripción](invoice-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="f6a70-125">For more information about how to invoice subscriptions, see [Invoice subscription transactions](invoice-subscription-transactions.md).</span></span>

<span data-ttu-id="f6a70-126">Dos días más tarde, el cliente se pone en contacto con usted para indicarle que la suscripción se deberá facturar en dólares estadounidenses y no en euros.</span><span class="sxs-lookup"><span data-stu-id="f6a70-126">Two days later, your customer calls to say that the subscription should be invoiced in U.S. dollars, not Euros.</span></span> <span data-ttu-id="f6a70-127">Por tanto, deberá una nota de abono y una nueva transacción de suscripción en la divisa correcta.</span><span class="sxs-lookup"><span data-stu-id="f6a70-127">Therefore, you create a credit note, and you also create a new subscription transaction in the correct currency.</span></span> <span data-ttu-id="f6a70-128">Para obtener más información acerca de cómo abonar transacciones de suscripción, vea [Abonar transacciones de suscripción](credit-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="f6a70-128">For more information about how to credit subscription transactions, see [Credit subscription transactions](credit-subscription-transactions.md).</span></span>

<span data-ttu-id="f6a70-129">Al final de cada mes, se pueden acumular los ingresos de un mes de la suscripción del cliente en la cuenta de pérdidas y ganancias y las cuentas de trabajo en curso.</span><span class="sxs-lookup"><span data-stu-id="f6a70-129">At the end of each month, one month's revenue can be accrued from the customer's subscription to the profit and loss account and the WIP accounts.</span></span> <span data-ttu-id="f6a70-130">Para obtener más información acerca de cómo se acumulan los ingresos de las suscripciones, vea [Acumular ingresos de suscripción](accrue-subscription-revenue.md).</span><span class="sxs-lookup"><span data-stu-id="f6a70-130">For more information about how to accrue revenue for subscriptions, see [Accrue subscription revenue](accrue-subscription-revenue.md).</span></span>

  



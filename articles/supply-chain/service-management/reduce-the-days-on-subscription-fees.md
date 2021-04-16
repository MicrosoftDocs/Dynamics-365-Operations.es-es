---
title: Reducir los días de las cuotas de suscripción
description: Para reducir el número de días de una cuota de suscripción existente, puede crear una nueva transacción en la que se quitará el período de tiempo que ya no debe formar parte del intervalo de cuotas de suscripción.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e8158c99d2447835f3656027fd73d7c22121536
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836095"
---
# <a name="reduce-the-days-on-subscription-fees"></a><span data-ttu-id="801d8-103">Reducir los días de las cuotas de suscripción</span><span class="sxs-lookup"><span data-stu-id="801d8-103">Reduce the days on subscription fees</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="801d8-104">Para reducir el número de días de una cuota de suscripción existente, puede crear una nueva transacción en la que se quitará el período de tiempo que ya no debe formar parte del intervalo de cuotas de suscripción.</span><span class="sxs-lookup"><span data-stu-id="801d8-104">To reduce the number of days of an existing subscription fee, you can create a new transaction in which you remove the period of time that should no longer be part of the subscription fee interval.</span></span>

## <a name="reduce-the-days-on-a-subscription-fee"></a><span data-ttu-id="801d8-105">Reducir los días de una cuota de suscripción</span><span class="sxs-lookup"><span data-stu-id="801d8-105">Reduce the days on a subscription fee</span></span>

1.  <span data-ttu-id="801d8-106">Haga clic en **Gestión de servicio** \> **Común** \> **Suscripciones de servicio** \> **Todas las suscripciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="801d8-106">Click **Service management** \> **Common** \> **Service subscriptions** \> **All service subscriptions**.</span></span> <span data-ttu-id="801d8-107">Seleccione la suscripción de servicio y, en el panel de acciones, haga clic en **Cuotas de suscripción**.</span><span class="sxs-lookup"><span data-stu-id="801d8-107">Select the service subscription, and on the Action Pane, click **Subscription fees**</span></span>

2.  <span data-ttu-id="801d8-108">En el campo **Tipo de suscripción**, seleccione **Días de reducción**.</span><span class="sxs-lookup"><span data-stu-id="801d8-108">In the **Subscription type** field, select **Reduction days**.</span></span>

3.  <span data-ttu-id="801d8-109">Use los campos **Fecha inicial** y **Fecha final** para definir el intervalo de fechas de la cuota de suscripción que desee quitar el período y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="801d8-109">Use the **From date** field and the **To date** fields to define the date interval of the subscription fee that you want to remove from the subscription fee period, and then click **OK**.</span></span>

<span data-ttu-id="801d8-110">Para ver la transacción creada, en el formulario , haga clic en **Suscripción** y seleccione **Transacciones de cuotas**.</span><span class="sxs-lookup"><span data-stu-id="801d8-110">To view the transaction that was created, in the **Subscription** form, click **Fee transactions**.</span></span>

## <a name="example"></a><span data-ttu-id="801d8-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="801d8-111">Example</span></span>

<span data-ttu-id="801d8-112">Si un período de cuota de suscripción se ejecuta entre el 1 de enero y el 31 de enero y desea reducir el período por 10 días, cree una nueva transacción en la que el período de reducción sea el 1 de enero al 10 de enero.</span><span class="sxs-lookup"><span data-stu-id="801d8-112">If a subscription transaction period runs from January 1 to January 31, and you want to reduce the period by 10 days, create a new transaction in which the reduction period is January 1 to January 10.</span></span> <span data-ttu-id="801d8-113">(El período de reducción también podría ser del 5 de enero al 15 de enero, o cualquier otro período de diez días).</span><span class="sxs-lookup"><span data-stu-id="801d8-113">(The reduction period could also be January 5 to January 15, or any other ten day period).</span></span>

<span data-ttu-id="801d8-114">Asimismo, si el campo **Fecha inicial** del período de reducción es el 21 de enero (31 menos 10), puede establecer el campo **Fecha final** en cualquier fecha después del 31 de enero y se quitarán 10 días del período de transacción de la cuota.</span><span class="sxs-lookup"><span data-stu-id="801d8-114">Also, if the **From date** on the reduction period is January 21 (31 minus 10), you could set the **To date** to any date after January 31, and 10 days will still be removed from the fee transaction period.</span></span>

## <a name="see-also"></a><span data-ttu-id="801d8-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="801d8-115">See also</span></span>

[<span data-ttu-id="801d8-116">Ejemplo de días de reducción</span><span class="sxs-lookup"><span data-stu-id="801d8-116">Reduction days example</span></span>](reduction-days-example.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
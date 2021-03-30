---
title: Reducir los días de las cuotas de suscripción
description: Para reducir el número de días de una cuota de suscripción existente, puede crear una nueva transacción en la que se quitará el período de tiempo que ya no debe formar parte del intervalo de cuotas de suscripción.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 65cd852ca3ce0446550f9ac148a14bbc6bcae500
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234786"
---
# <a name="reduce-the-days-on-subscription-fees"></a>Reducir los días de las cuotas de suscripción 

[!include [banner](../includes/banner.md)]


Para reducir el número de días de una cuota de suscripción existente, puede crear una nueva transacción en la que se quitará el período de tiempo que ya no debe formar parte del intervalo de cuotas de suscripción.

## <a name="reduce-the-days-on-a-subscription-fee"></a>Reducir los días de una cuota de suscripción

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Suscripciones de servicio** \> **Todas las suscripciones de servicio**. Seleccione la suscripción de servicio y, en el panel de acciones, haga clic en **Cuotas de suscripción**.

2.  En el campo **Tipo de suscripción**, seleccione **Días de reducción**.

3.  Use los campos **Fecha inicial** y **Fecha final** para definir el intervalo de fechas de la cuota de suscripción que desee quitar el período y, a continuación, haga clic en **Aceptar**.

Para ver la transacción creada, en el formulario , haga clic en **Suscripción** y seleccione **Transacciones de cuotas**.

## <a name="example"></a>Ejemplo

Si un período de cuota de suscripción se ejecuta entre el 1 de enero y el 31 de enero y desea reducir el período por 10 días, cree una nueva transacción en la que el período de reducción sea el 1 de enero al 10 de enero. (El período de reducción también podría ser del 5 de enero al 15 de enero, o cualquier otro período de diez días).

Asimismo, si el campo **Fecha inicial** del período de reducción es el 21 de enero (31 menos 10), puede establecer el campo **Fecha final** en cualquier fecha después del 31 de enero y se quitarán 10 días del período de transacción de la cuota.

## <a name="see-also"></a>Consulte también

[Ejemplo de días de reducción](reduction-days-example.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Visión general del flujo de trabajo de suscripción
description: Este tema proporciona una visión general del flujo de trabajo de suscripción.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dbc87dc9c6327550020270468346800a7b80f4c3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817398"
---
# <a name="subscription-workflow-overview"></a>Visión general del flujo de trabajo de suscripción 

[!include [banner](../includes/banner.md)]


Usted es el administrador de suscripciones para una empresa de iluminación que ofrece suscripciones para el mantenimiento de las instalaciones de luz. Un cliente se pone en contacto con la empresa para adquirir una suscripción anual para el mantenimiento de las instalaciones de luz.

## <a name="setting-up-subscriptions"></a>Configuración de suscripciones

Para configurar una suscripción, en primer lugar debe crear un grupo de suscripciones para el nuevo acuerdo de servicio, o bien comprobar si existe un grupo de suscripciones. Si ya existe uno, deberá configurarlo para facturar al cliente de forma anual y para acumular los ingresos de ventas todos los meses del año. Para obtener más información acerca de la configuración de suscripciones, consulte [Configurar grupos de suscripciones](set-up-subscription-groups.md).

Una vez creado el grupo de suscripciones, podrá crear la suscripción. Para obtener más información sobre cómo crear suscripciones de servicio, consulte [Crear suscripciones servicio desde un grupo de suscripciones](create-service-subscriptions-from-subscription-group.md).

## <a name="create-and-modify-subscription-transactions"></a>Crear y modificar transacciones de suscripción

Una vez configurada la suscripción, deberá crear la transacción de cuota de suscripción para el primer período de facturación, que en este caso será de un año. Las transacciones son del tipo **Normal**. Por lo tanto, sólo podrá crear transacciones de suscripción en las que las fecha de inicio y fin se correspondan con los períodos anteriormente creados en el formulario **Tipos de período**. Para obtener más información acerca de las transacciones de gastos, vea [Crear transacciones de gastos de suscripción](create-subscription-fee-transactions.md).

Una vez establecida la suscripción para el cliente, recuerda que se negoció un descuento del 10 por ciento para todos los precios de línea de las oferta de servicio. Por lo tanto, deberá reducir el precio de la cuota de transacción creada.

Más tarde, el contacto del cliente le llama para avisarle de que, aunque aún desean el acuerdo de servicio para las instalaciones de luz, tienen previsto instalar nuevas luces más adelante. Por lo tanto, sólo necesitan una cobertura de mantenimiento hasta octubre de 2013. Para reducir el número de meses de la suscripción del cliente, crea una nueva transacción de cuota de suscripción del tipo **Días de reducción**. Para obtener más información acerca de cómo reducir días, consulte [Reducir los días de las cuotas de suscripción](reduce-the-days-on-subscription-fees.md).

## <a name="invoice-and-accrue-subscription-transactions"></a>Facturar y acumular transacciones de suscripción

Ha terminado la configuración de la suscripción y está listo para facturársela al cliente. Para obtener más información acerca de cómo facturar suscripciones, consulte [Facturar transacciones de suscripción](invoice-subscription-transactions.md).

Dos días más tarde, el cliente se pone en contacto con usted para indicarle que la suscripción se deberá facturar en dólares estadounidenses y no en euros. Por tanto, deberá una nota de abono y una nueva transacción de suscripción en la divisa correcta. Para obtener más información acerca de cómo abonar transacciones de suscripción, vea [Abonar transacciones de suscripción](credit-subscription-transactions.md).

Al final de cada mes, se pueden acumular los ingresos de un mes de la suscripción del cliente en la cuenta de pérdidas y ganancias y las cuentas de trabajo en curso. Para obtener más información acerca de cómo se acumulan los ingresos de las suscripciones, vea [Acumular ingresos de suscripción](accrue-subscription-revenue.md).

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
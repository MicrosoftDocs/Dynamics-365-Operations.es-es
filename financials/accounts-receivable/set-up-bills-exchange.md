---
title: Configurar letras de cambio
description: Este tema describe los pasos para configurar letras de cambio.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ce2142d946085d8bfc577accf1bb31a89ea29156
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bills-of-exchange"></a>Configurar letras de cambio

Este tema describe los pasos para configurar letras de cambio.

Una letra de cambio es una orden escrita o electrónica de un cliente que especifica que otra parte, normalmente un banco, debe pagar un importe establecido a la empresa. Al usar una letra de cambio como pago de una factura de pedido de ventas o de servicios, se abona en la cuenta del cliente el importe correspondiente. Ese abono se garantiza mediante la letra de cambio hasta que el cliente la pague al banco. Normalmente, definirá la factura con la letra de cambio en la fecha de vencimiento. Cuando reciba una notificación del banco que indique que la letra de cambio se ha liquidado, podrá cerrarla. Puede librar una letra de cambio a través del banco en cualquiera de estos momentos:

-   En la fecha de vencimiento. Este se conoce como remesa al cobro.
-   Antes de la fecha de vencimiento, normalmente en la fecha de descuento especificada en las condiciones de pago establecidas para el cliente. Al registrar la transacción, el importe del descuento se registra en una cuenta de gastos. El resto del importe es pasivo hasta que el banco recibe el pago del cliente. Este se conoce como remesa al descuento.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Configuración de perfiles de contabilización para letras de cambio
** Use los perfiles de contabilización ** la página para configurar los perfiles de registro que se pueden usar con las letras de cambio, impagos de letras de cambio, remesas al cobro, y remesas al descuento. En ** extracto de cuenta ** campo, seleccione el extracto de cuenta para registrar los importes de las letras de cambio. Esta cuenta se adeuda o se abona, según el tipo de transacción de letra de cambio:
-   Para las letras de cambio, se cargará el importe correspondiente en esta cuenta cuando se registre una letra de cambio, y ha abonado cuando una remesa al descuento o una remesa al cobro se registra.
-   Para los impagos de letra de cambio, se cargará el importe correspondiente en esta cuenta cuando se registre el impago de letra de cambio.
-   Para las remesas al cobro, se cargará el importe correspondiente en esta cuenta cuando se registre una remesa al cobro.
-   Para las remesas al descuento, se cargará el importe correspondiente en esta cuenta cuando se registre una remesa al descuento.

En ** cuenta de Liquidar ** campo, seleccione la cuenta de efectivo para registrar las letras de cambio. Se cargará el importe correspondiente en esta cuenta cuando se liquide la letra de cambio. En ** los pagos por adelantado de los impuestos ** campo, seleccione el extracto de cuenta para registrar los importes de impuestos cuando se usan letras de cambio para anticipos. En ** los pasivos al descuento ** campo, seleccione la cuenta para registrar el importe de descuento de remesas al descuento a. Se abonará el importe correspondiente en esta cuenta cuando se registre una remesa al descuento.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Configurar los parámetros de clientes para letras de cambio
En ** los parámetros de clientes ** la página, los perfiles de registro predeterminado para las letras de cambio se especifican en ** libro mayor y los impuestos ** la ficha. Las secuencias numéricas se definen en ** las secuencias numéricas ** la ficha.
Configurar nombres de diario para letras de cambio
------------------------------------------

En ** los nombres de los diarios ** la página, cree como mínimo cinco nombres de diario para las letras de cambio. Aquí hay tipos de diarios:
-   ** Letra de cambio de cliente ** permite crear un nombre de diario para el diario de creación de letra de cambio.
-   ** Impago de letra de cambio de cliente ** permite crear un nombre de diario para el diario de impago de letras de cambio.
-   ** Letra de cambio de cliente ** permite crear un nombre de diario para el diario de letra de cambio actualizar.
-   ** Remesa bancaria de cliente ** permite crear un nombre de diario para el diario de envíos.
-   ** Letra de cambio de cliente ** permite crear un nombre de diario para el diario de letra de cambio.

En la página del asiento del diario para cada diario de letra de cambio, puede especificar información sobre la letra de cambio en ** letra de cambio ** la ficha. Una vez registradas las líneas de diario de la letra de cambio se hayan registrado, podrá verlas en ** pregunta del diario de letra de cambio ** la página y ** las estadísticas de las letras de cambio ** la página.
Configurar métodos de pago para las letras de cambio
-----------------------------------------------

** En las formas de pago ** la página, configurar al menos un método de pago para las letras de cambio. Si trabaja con más de un banco, configure un método de pago que corresponda al formato de remesa que cada banco requiere para letras de cambio.
Configurar cuotas de pago para letras de cambio
-----------------------------------------

Una cuota de pago es un cargo asociado al proceso de cobro de pagos a los clientes. Las líneas de configuración de cuota de pago que se pueden asociar cada cuota de pago. Puede usar las líneas de configuración para controlar cómo los importes predeterminados para las cuotas de pago se calculan. Por ejemplo, puede crear líneas de configuración para los métodos de pago, especificaciones de pago, divisas y períodos de tiempo. También puede crear líneas de configuración para un porcentaje o importe basado en intervalos diarios. Por ejemplo, puede configurar un porcentaje de interés que se basa en el período de tiempo en que vence un pago. Si distintas cuotas de los gastos bancarios para los distintos tipos de envío, por ejemplo ** ** recopilación o ** ** descuento, configure una línea de cuota de pago independiente para cada tipo de remesa.
Configurar cuotas de envío para archivos de remesa bancarios
------------------------------------------------

** En las cuentas bancarias ** la página, puede configurar cuotas de envío que los gastos bancarios para cada archivo de remesa generado. Estas cuotas se registran cuando se haya confirmado la remesa y se conozcan los importes de cuota realizados. Las cuotas de envío son diferentes de las cuotas de pago, que se cobran a los clientes y están asociadas a las líneas de diario.
Configurar diseños de documento para letras de cambio
---------------------------------------------

** En las cuentas bancarias ** la página, haga clic en ** configuración **, y especifique el diseño de documento que se requiere para cada cuenta bancaria para la que generará documentos de letra de cambio.
Configurar clientes para letras de cambio
--------------------------------------

En ** los clientes ** paginele, para cada cliente que ha acordado pagar mediante una letra de cambio, puede configurar un método de pago predeterminado para las letras de cambio en ** los valores predeterminados de pago ** la ficha.





---
title: Introducción al reconocimiento de ingresos
description: Este tema proporciona información acerca de la función de reconocimiento de ingresos. Esta característica proporciona un marco flexible que permite definir reglas específicas de la empresa para reconocer tanto el precio como la programación de ingresos en pedidos de varios elementos.
author: kweekley
ms.date: 11/11/2019
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: edc0bab7287e271f1d1197d87a95709599e12b5b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820554"
---
# <a name="revenue-recognition-overview"></a>Introducción al reconocimiento de ingresos

[!include [banner](../includes/banner.md)]

Las empresas de sectores que venden múltiples elementos, como productos, servicios, suscripciones, etc., necesitan poder desglosar pedidos con varios elementos para poder reconocer los ingresos en función de un conjunto de directrices específicas de la empresa y del sector.

> [!NOTE]
> La característica Reconocimiento de ingresos no se puede activar a través de Administración de características. Actualmente, debe utilizar las claves de configuración para activarla.

> Reconocimiento de ingresos, incluida la funcionalidad de agrupación de trabajos, no se admite para su uso en los canales de Commerce (comercio electrónico, PDV, centro de llamadas). Los elementos configurados con reconocimiento de ingresos no deben agregarse a pedidos o transacciones creadas en los canales de Commerce.

En general, el proceso de reconocimiento de ingresos se puede usar para realizar estas tareas:

* Asignar ingresos para ayudar a garantizar el reconocimiento del precio de ingresos adecuado, según el valor de los componentes de los pedidos con varios elementos.
* Diferir los ingresos en función de una programación de ingresos que represente el marco contractual y los porcentajes para reconocer ingresos en el tiempo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

El vídeo [Cómo usar el reconocimiento de ingresos en Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (se muestra arriba) se incluye en la [Lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.

La característica de reconocimiento de ingresos proporciona un marco flexible que permite definir reglas específicas de la empresa para reconocer tanto el precio como la programación de ingresos.

Se usan productos liberados para permitir el reconocimiento de ingresos en los documentos de pedido de ventas. Los productos emitidos contienen la configuración necesaria para determinar el precio y la programación de ingresos. El pedido de ventas puede originarse a partir de un proyecto de tiempo y materiales.

Las empresas pueden usar la funcionalidad de programación de ingresos sin usar la funcionalidad de precio de ingresos. Por ello, el precio en las líneas de pedido de ventas se usará como ingresos o ingresos aplazados. Si existe una programación de ingresos en la línea de pedido de ventas, se aplazará el precio de la línea del pedido de ventas. Si una programación de ingresos no existe en la línea de pedido de ventas, se registrará el precio de la línea de pedido de ventas en una cuenta de ingresos cuando se facture.

El precio de ingresos se calcula cuando se confirma el pedido de ventas o cuando se registra la factura. Para obtener una vista previa del precio de ingresos antes de registrar la factura, debe confirmar el pedido de ventas.

Cuando se confirma el pedido de ventas, también se crea una programación de ingresos prevista si alguna línea de pedido de ventas tiene una programación de ingresos. Cuando se factura el pedido de ventas, se elimina la programación de ingresos prevista y se sustituye con la programación de reconocimiento de ingresos real.

Se mantienen los detalles de la programación de reconocimiento de ingresos para cada línea de pedido de ventas. Por lo tanto, el administrador de reconocimiento de ingresos puede ver los detalles y emitir líneas para ingresos cuando finalice la obligación del contrato. Al final de cada período, el administrador de reconocimiento de ingresos puede crear un diario de ingresos para emitir cualquier línea de programación que venza en la fecha que defina. Este diario de ingresos no se registra inmediatamente. Así, el administrador de reconocimiento de ingresos podrá comprobar que se emiten los importes correctos de ingresos aplazados a ingresos reales.

Si un cambio contractual hace que se agregue una nueva línea de pedido de ventas al pedido de ventas existente o a un nuevo pedido de ventas, se puede ejecutar un proceso de reasignación para corregir el precio de ingresos en todas las líneas de los pedidos de ventas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
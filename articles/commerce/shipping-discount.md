---
title: Descuento por envío
description: Este artículo describe las capacidades de descuento de envío en Microsoft Dynamics 365 Commerce y la configuración que se requiere para usarlos.
author: ShalabhjainMSFT
ms.date: 08/23/2020
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2019-01-31
ms.openlocfilehash: 74cfe5246ad72cbdedd0ed4e3b3394bf7277919e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473860"
---
# <a name="shipping-discount"></a>Descuento por envío

[!include [banner](includes/banner.md)]

Este artículo describe las capacidades de descuento de envío en Microsoft Dynamics 365 Commerce y la configuración que se requiere para usarlos.

El envío gratis o con descuento es un factor que influye en las decisiones de compra en línea de los clientes. Para aumentar sus ingresos por transacción, muchos minoristas utilizan un beneficio de envío gratuito para motivar a los clientes a aumentar el tamaño de su carrito.

Commerce admite una capacidad de descuento de envío que permite a los minoristas configurar un porcentaje de descuento en los cargos de envío para un método de envío específico cuando el monto total de las ventas de artículos calificados en la transacción cumple con criterios específicos. Un ejemplo de un escenario que utiliza la capacidad de descuento de envío es "Gaste $50 o más para obtener envío gratuito al día siguiente".

## <a name="prerequisites"></a>Requisitos previos

La capacidad de descuento de envío es compatible con las caracteristicas [cobros automáticos avanzados omnicanal](/dynamics365/unified-operations/retail/omni-auto-charges) de Commerce. Para que funcione la capacidad de descuento de envío, debe habilitar la configuración **Usar cargos automáticos avanzados** en la ficha **Pedidos de los clientes** de la página **Parámetros comerciales** en Commerce headquarters. Los minoristas pueden usar la función de cargos automáticos avanzados para configurar varios tipos de cargos, como manejo, instalación y eliminación.

El descuento de envío se aplican solo a los gastos de envío. Por lo tanto, un minorista debe especificar qué cargos son gastos de envío. Para especificar los gastos de envío, en Commerce headquarters, vaya a **Configuración de canales \> Cargos \> Código de cargos** y establezca la opción **Costo de envío** en **Sí** para los cargos deseados.

![Especificar un cargo como cargo de envío.](./media/Specify_shipping_charge.png)

## <a name="configuration"></a>Configuración

La capacidad de descuento de envío se basa en niveles y solo admite el tipo de cálculo **Porcentaje de descuento**. Para configurar un descuento de envío, en Commerce headquarters, vaya a **Precios y descuentos \> Descuento por umbral de envío**. A continuación, puede especificar el modo de entrega al que se aplica el descuento, definir uno o más umbrales de cantidad y establecer el porcentaje de descuento para cada umbral. También puede configurar una lista de categorías o productos como artículos calificados. De esa manera, solo se contará el monto de las ventas contra esos artículos en una transacción cuando el motor de precios evalúe si el total de la transacción alcanza el umbral.

> [!NOTE]
> A diferencia de otros tipos de descuento, el descuento de envío no crea líneas de descuento. En su lugar, edita directamente el cargo de envío y agrega el nombre del descuento a la descripción del cargo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

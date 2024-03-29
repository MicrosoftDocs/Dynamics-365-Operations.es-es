---
title: Cambiar modo de entrega en PDV
description: En este artículo se describe cómo configurar y usar el modo de cambio de la operación de entrega en PDV.
author: hhainesms
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 583f568164d0de70e22998bf5ded5f4616b00bd2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855830"
---
# <a name="change-mode-of-delivery-in-pos"></a>Cambiar modo de entrega en PDV

[!include [banner](includes/banner.md)]

En este artículo se describe cómo configurar y utilizar la funcionalidad "cambiar modo de entrega" en su entorno de punto de venta (PDV). 

En Dynamics 365 Commerce versión 10.0.10 y posteriores está disponible la operación **Cambiar modo de entrega** (647) y puede agregarla a sus diseños de pantalla de PDV.

La característica de cambio de modo de entrega le ofrece la opción de cambiar el modo de entrega de una o más líneas de venta configuradas para el envío en la transacción de PDV. En versiones anteriores de Commerce, tenía que pasar por los flujos de configuración **Enviar todo** o **Enviar selección** completos si quería cambiar el modo de entrega en una línea existente que estaba configurada para el envío. Este proceso requería mucho tiempo y podía provocar cambios accidentales en el origen de la entrega o las fechas de entrega para la línea. La nueva funcionalidad proporciona un método alternativo para actualizar de forma eficiente el modo de entrega en estas líneas de venta.

Para obtener más información sobre cómo agregar una operación a un botón en la cuadrícula de botones de PDV, consulte [Diseños de pantalla para el punto de venta](pos-screen-layouts.md).

Una vez configurada esta función en PDV, al seleccionar **Cambiar modo de entrega**, se le presentará una página de lista en la que podrá elegir las líneas de la transacción para las que desea cambiar el modo de entrega. Puede elegir algunas de las líneas o todas ellas, o salir sin realizar ningún cambio. Las líneas de ventas que se configuraron previamente para el envío son las únicas líneas que puede cambiar de la lista. Si desea cambiar una línea designada para recogida o reparto para envío, debe usar las operaciones **Enviar todo** o **Enviar selección**. Y a la inversa, si desea cambiar una línea designada como un envío para recogida o reparto, debe usar las operaciones **Recoger todo**, **Recoger selección**, **Repartir todo** o **Repartir selección**.

Después de seleccionar las líneas que desea cambiar, haga clic en **Cambiar modo de entrega** para que se le pida que seleccione las opciones del modo de entrega. Si seleccionó varias líneas para cambiar, el PDV solo mostrará los modos de entrega que se hayan configurado como permitidos para todos los productos seleccionados. Los modos de entrega se pueden configurar para admitir productos y direcciones de entrega específicos. Si hay un modo de entrega que es aceptable para una combinación de producto y dirección pero no es aceptable para otra combinación seleccionada de producto y dirección, el modo de entrega no estará disponible. Es posible que deba seleccionar las líneas una por una y cambiar el modo de entrega para cada línea por separado si desea seleccionar un modo de entrega para un producto que no sea compatible con otro producto.  

Cuando haya seleccionado el nuevo modo de entrega, se mostrará la página de transacción. Para revisar sus nuevas selecciones de modo de entrega, seleccione la pestaña **Entrega** en la lista de transacciones.

## <a name="additional-resources"></a>Recursos adicionales

[Crear pedidos de centro de llamadas](tasks/create-call-center-orders.md)

[Personalizar correos electrónicos transaccionales por modo de entrega](customize-email-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Suspender y reanudar una transacción en el punto de venta (PDV)
description: Este tema explica cómo los usuarios pueden suspender transacciones en curso y reanudarlas después más tarde o en otro registro con Microsoft Dynamics 365 for Retail.
author: jblucher
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ffb04609318c7de4b9ef729a8e03a7f9395806b8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569553"
---
# <a name="suspend-and-resume-transactions-in-the-point-of-sale-pos"></a>Suspender y reanudar transacciones en el punto de venta (PDV)

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Los usuarios de punto de venta (PDV) pueden suspender transacciones en curso y después reanudarlas más tarde o en otro registro. Las transacciones se suspenden a menudo para liberar rápidamente un registro para otra tarea sin perder ningún progreso con respecto a la transacción actual. Por ejemplo, un socio de la tienda empieza a procesar la transacción de un cliente en un dispositivo móvil, pero debe completarla en un registro con una caja registradora. En este caso, el socio de la tienda puede suspender la transacción en el dispositivo móvil y, a continuación recuperarla y reanudarla en un registro.

## <a name="configure-suspend-and-resume-functionality"></a>Configurar la funcionalidad de suspender y reanudar

### <a name="pos-operations"></a>Operaciones de PDV

Dos [Operaciones de PDV](pos-operations.md) permiten que el soporte de PDV suspenda y reanude escenarios. Puede asignar estas operaciones a [cuadrículas de botones](pos-screen-layouts.md) en la página de la transacción o a la página de inicio.

- 503: Suspender transacción
- 504: Recuperar transacción

### <a name="receipt-template"></a>Plantilla de recepción

El PDV se puede configurar para generar un resguardo que se imprime cuando se suspende una transacción. Dicho resguardo se puede utilizar para identificar y recuperar rápidamente la transacción más adelante.

Para permitir al PDV imprimir un resguardo, debe agregar el formato de recepción **Transacción suspendida** al perfil de recepción de la tienda. Puede diseñar el formato de recepción de modo que incluya o excluya detalles específicos acerca de la transacción. Por ejemplo, el formato puede incluir un código de barras para admitir la exploración.

### <a name="receipt-numbering"></a>Numeración del recibo

Con respecto a otros tipos de la transacción PDV que generan un recibo impreso, puede definir una secuencia numérica para las transacciones suspendidas en la sección **Numeración del recibo** del perfil de funcionalidad de la tienda.

### <a name="void-when-closing-shift"></a>Anular al cerrar el turno

Puede usar la opción **Anular al cerrar el turno** para requerir que los usuarios completen o anulen cualquier transacción suspendida antes de que se cierre su cambio. Durante la operación **Cerrar turno** , el PDV solicitará a los usuarios que vean o anulen todas las transacciones suspendidas pendientes.

## <a name="suspend-and-resume-a-transaction"></a>Suspender y reanudar una transacción

### <a name="suspend-a-transaction"></a>Suspender una transacción

Los usuarios que tengan privilegios suficientes, y que tengan un diseño de pantalla que incluye la operación **Suspender transacción** , pueden suspender una transacción para que pueda recuperarse más adelante o en otro registro.

Las transacciones se pueden suspender solo si **no** contienen los siguientes tipos de líneas:

- Líneas de pago activas
- Líneas de tarjeta regalo (para emitir una tarjeta regalo o agregar al saldo de la tarjeta regalo)

Una transacción suspendida no afecta a la información de ventas ni a la información de disponibilidad del inventario para la tienda.

### <a name="resume-a-suspended-transaction"></a>Reanudar una transacción suspendida

Las transacciones suspendidas se pueden recuperar y reanudar en la misma tienda por cualquier usuario que tenga privilegios suficientes, y que también tenga un diseño que incluya la operación **Recuperar transacción**.

Para recuperar de forma rápida y sencilla una transacción suspendida, digitalice el código de barras del resguardo impreso mientras  visualiza la lista de transacciones de la operación **Recuperar transacción**.

### <a name="considerations-for-offline-mode"></a>Consideraciones para el modo sin conexión

- Toda transacción que se haya suspendido mientras PDV se encuentra en el modo en línea no se puede reanudar en modo desconectado, ya que los datos no se sincronizan con la base de datos sin conexión.
- Si suspende una transacción mientras el PDV se encuentra en el modo desconectado, puede recuperarlo en modo desconectado, siempre y cuando no se haya devuelto al PDV al modo conectado en cualquier momento desde que suspendió la transacción. Cuando se devuelve el PDV al estado anterior en modo conectado, los datos sobre transacciones suspendidas se pasan a la base de datos en línea y se quitan de la base de datos sin conexión. Por lo tanto, las transacciones se pueden reanudar solo en modo conectado. Si devuelve el PDV al modo desconectado, no podrá reanudar las transacciones suspendidas, pues ya se han quitado de la base de datos sin conexión.

### <a name="void-a-suspended-transaction"></a>Anular una transacción suspendida

Puede anular transacciones suspendidas recuperando la transacción y después ejecutando la operación **Anular transacción** , o seleccionando la transacción en el lista **Recuperar transacción** y seleccionando **Anular** en la barra de la aplicación. De manera alternativa, el almacén se puede configurar para solicitar a los usuarios que anulen las transacciones suspendidas cuando acaben su turno.

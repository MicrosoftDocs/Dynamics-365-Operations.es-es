---
title: Recibir entregas parciales de artículos devueltos
description: Las entregas parciales se definen en términos de líneas de pedidos de devolución, no de envíos de pedidos de devolución.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c0e27e3a5cb6be36a1d69190ce1b01ecada48a6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677125"
---
# <a name="receive-partial-deliveries-of-returned-items"></a>Recibir entregas parciales de artículos devueltos    

[!include [banner](../includes/banner.md)]


Las entregas parciales se definen en términos de líneas de pedidos de devolución, no de envíos de pedidos de devolución.

Esto significa que si recibe la cantidad completa que se indica en una línea del pedido de devolución pero no recibe ninguna cantidad de las demás líneas del pedido de devolución, ésta no es una entrega parcial. Sin embargo, si en una línea del pedido de devolución se solicitan 10 unidades de un determinado artículo que se va a devolver pero se reciben sólo cuatro unidades, ésta es una entrega parcial.

Si un envío de devolución contiene una cantidad inferior al total de la cantidad de una línea del pedido de devolución, puede configurar la entrega por separado y esperar a que se reciba el resto de la cantidad devuelta, o registrar la cantidad parcial.

## <a name="register-and-post-a-partial-quantity"></a>Registro de una cantidad parcial

1.  Tras seleccionar un pedido de devolución de llegada en el formulario **Visión general de llegadas - Almacén: %1, Muelle: %2, nombre de diario: %3**, haga click en **Iniciar llegada** para crear el diario de recepción y, a continuación haga click en **Diarios** \> **Mostrar llegadas a partir de recepciones** para abrir el formulario **Diario de ubicaciones**.

2.  Seleccione la línea del diario con el que desea trabajar y haga clic en **Líneas** para abrir el formulario **Líneas de diario, ubicaciones**.

3.  Seleccione la línea del número de artículo del que sólo se ha recibido una cantidad parcial y, a continuación, haga clic en **Funciones** \> **Dividir** para abrir el formulario **Dividir**.

4.  En el campo **Cantidad dividida**, especifique la cantidad correspondiente al número total de artículos recibidos y, a continuación, haga clic en **Aceptar**.

5.  En el formulario **Líneas de diario, ubicaciones**, seleccione la línea correspondiente a la cantidad de artículos recibida y, a continuación, haga clic en **Registrar**. Puede registrar la línea de la cantidad adicional después de que se reciban los artículos.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
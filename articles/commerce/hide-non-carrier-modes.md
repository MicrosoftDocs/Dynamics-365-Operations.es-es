---
title: Ocultar modos sin transportistas de la entrega de las opciones de envío en PDV
description: Este tema describe una opción de configuración que pueda evitar que los modos no de transportistas aparezcan en la selección de entrega cuando los pedidos de envío se crean en de la aplicación (PDV) de punto de venta.
author: hhainesms
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: a5f08fc86dc093fd0ead219b808fa720a43f6b6b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797127"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>Ocultar modos sin transportistas de las opciones de entrega de envío en PDV


[!include [banner](includes/banner.md)]

Este tema describe una opción de configuración que está disponible para su de aplicación (PDV) de punto de venta. Esta opción de configuración cambia el comportamiento de la selección de un modo de entrega a pedidos del envío se crean en PDV.

Cuando los usuarios crean pedidos de envío del cliente en el sistema PDV, pueden seleccionar un modo de entrega para el envío. Esta funcionalidad está disponible independientemente de si se envía todo el pedido o solo líneas seleccionadas.

De forma predeterminada, el cuadro de diálogo donde se selecciona un modo de entrega muestra todos los modos de entrega válidos para la combinación de un canal, de un artículo y una dirección de entrega. Estos modos de entrega se definen en la página **Modos de entrega** en Headquarters (**Ventas y marketing \> Configuración \> Distribución \> Modos de entrega**). Los modos de entrega "sin transportista", como **Para llevar** o **Recogida**, pueden aparecer también para su selección en el cuadro de diálogo.

Sin embargo, se ha agregado una función que le permite ocultar modos de entrega sin transportistas en el cuadro de diálogo. Para activar esta característica, en la página **Parámetros de Commerce**, en la pestaña **Pedidos de cliente** establezca la opción **Mostrar solo opciones con transportista para pedidos de envío** en **Sí**. Tras activar esta característica y ejecutar los trabajos de distribución apropiados para sincronizar la información de la base de datos del canal, los modos de entrega sin transportista no aparecerán para su selección durante el proceso de creación órdenes de envío en el PDV.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
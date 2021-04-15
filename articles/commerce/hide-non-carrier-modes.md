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
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a><span data-ttu-id="61972-103">Ocultar modos sin transportistas de las opciones de entrega de envío en PDV</span><span class="sxs-lookup"><span data-stu-id="61972-103">Hide non-carrier delivery modes from the shipping options in POS</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="61972-104">Este tema describe una opción de configuración que está disponible para su de aplicación (PDV) de punto de venta.</span><span class="sxs-lookup"><span data-stu-id="61972-104">This topic describes a configuration option that is available for the point of sale (POS) application.</span></span> <span data-ttu-id="61972-105">Esta opción de configuración cambia el comportamiento de la selección de un modo de entrega a pedidos del envío se crean en PDV.</span><span class="sxs-lookup"><span data-stu-id="61972-105">This configuration option changes the behavior for the selection of a mode of delivery when shipment orders are created in POS.</span></span>

<span data-ttu-id="61972-106">Cuando los usuarios crean pedidos de envío del cliente en el sistema PDV, pueden seleccionar un modo de entrega para el envío.</span><span class="sxs-lookup"><span data-stu-id="61972-106">When users create customer shipment orders in POS, they can select a mode of delivery for the shipment.</span></span> <span data-ttu-id="61972-107">Esta funcionalidad está disponible independientemente de si se envía todo el pedido o solo líneas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="61972-107">This functionality is available regardless of whether the whole order is being shipped or only selected lines.</span></span>

<span data-ttu-id="61972-108">De forma predeterminada, el cuadro de diálogo donde se selecciona un modo de entrega muestra todos los modos de entrega válidos para la combinación de un canal, de un artículo y una dirección de entrega.</span><span class="sxs-lookup"><span data-stu-id="61972-108">By default, the dialog box where a mode of delivery is selected shows all the valid modes of delivery for the combination of a channel, an item, and a delivery address.</span></span> <span data-ttu-id="61972-109">Estos modos de entrega se definen en la página **Modos de entrega** en Headquarters (**Ventas y marketing \> Configuración \> Distribución \> Modos de entrega**).</span><span class="sxs-lookup"><span data-stu-id="61972-109">These modes of delivery are defined on the **Modes of delivery** page in Headquarters (**Sales and marketing \> Setup \> Distribution \> Modes of delivery**).</span></span> <span data-ttu-id="61972-110">Los modos de entrega "sin transportista", como **Para llevar** o **Recogida**, pueden aparecer también para su selección en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="61972-110">"Non-carrier" modes of delivery, such as **Carryout** or **Pickup**, might also appear for selection in the dialog box.</span></span>

<span data-ttu-id="61972-111">Sin embargo, se ha agregado una función que le permite ocultar modos de entrega sin transportistas en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="61972-111">However, a feature has been added that lets you hide non-carrier modes of delivery in the dialog box.</span></span> <span data-ttu-id="61972-112">Para activar esta característica, en la página **Parámetros de Commerce**, en la pestaña **Pedidos de cliente** establezca la opción **Mostrar solo opciones con transportista para pedidos de envío** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="61972-112">To turn on this feature, on the **Commerce parameters** page, on the **Customer orders** tab, set the **Show only carrier mode options for ship orders** option to **Yes**.</span></span> <span data-ttu-id="61972-113">Tras activar esta característica y ejecutar los trabajos de distribución apropiados para sincronizar la información de la base de datos del canal, los modos de entrega sin transportista no aparecerán para su selección durante el proceso de creación órdenes de envío en el PDV.</span><span class="sxs-lookup"><span data-stu-id="61972-113">After you turn on this feature and run the appropriate distribution jobs to sync the information to the channel database, non-carrier modes of delivery won't appear for selection during the process of creating shipment orders in POS.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
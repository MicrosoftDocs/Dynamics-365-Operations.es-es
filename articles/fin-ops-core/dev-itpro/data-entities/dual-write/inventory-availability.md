---
title: Disponibilidad de inventario en doble escritura
description: Este tema proporciona información sobre la disponibilidad de comprobación de inventarios en doble escritura.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426991"
---
# <a name="inventory-availability"></a>Disponibilidad de inventario

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Utilizando la disponibilidad de inventario, puede verificar su inventario antes de agregar un producto a los formularios **Presupuesto**, **Pedidos** o **Facturas** en aplicaciones basadas en modelos en Dynamics 365. Por ejemplo, comprobar el inventario y determinar una fecha de cumplimiento es una tarea clave en el proceso [cliente potencial a efectivo](dual-write-prospect-to-cash.md). Si no tiene suficiente inventario, puede estimar una fecha de entrega basada en los recibos y problemas de inventario proyectados. También puede verificar la información de neto no comprometido (ATP), donde puede encontrar la cantidad de ATP en el intervalo de tiempo predefinido.

## <a name="on-hand-inventory"></a>Inventario disponible 

En el encabezado de los formularios **Citas**, **Pedidos** o **Facturas** en Dynamics 365 Sales, se ha añadido un nuevo botón **Inventario disponible**. Cuando hace clic en el botón, aparece un cuadro de diálogo y puede especificar la empresa y el producto para el que desea comprobar el inventario disponible. Devuelve la información de inventario de Dynamics 365 Supply Chain Management y muestra la misma información que [Inventario disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md). La información incluye estas cantidades:

- **Cantidad disponible**
- **Cantidad disponible reservada**
- **Cantidad disponible lista**
- **Cantidad pedida**
- **Cantidad en pedido**
- **Cantidad solicitada reservada**
- **Cantidad total disponible**

## <a name="atp-information"></a>Información de NNC

En los elementos de línea de los formularios **Citas**, **Pedidos** o **Facturas** en Dynamics 365 Sales, se ha añadido un nuevo botón **Información ATP**. Cuando hace clic en el botón, aparece un cuadro de diálogo y puede especificar la empresa, el producto, el sitio del inventario, el almacén de inventario y la cantidad pedida. Devuelve la **Información ATP** desde Supply Chain Management y muestra la configuración descrita en [Promesas de pedidos](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations). La información incluye **Cantidad ATP**, **Cantidad de recibo**, **Cantidad emitida**y **Cantidad disponible**.

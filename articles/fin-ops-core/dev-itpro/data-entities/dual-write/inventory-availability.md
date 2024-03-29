---
title: Disponibilidad de inventario en doble escritura
description: Este artículo proporciona información sobre cómo comprobar la disponibilidad de inventarios en doble escritura.
author: RamaKrishnamoorthy
ms.date: 05/26/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 442486550d3a7c5132e26f663caaa7c2c02eeb6e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289220"
---
# <a name="inventory-availability-in-dual-write"></a>Disponibilidad de inventario en doble escritura

[!include [banner](../../includes/banner.md)]

Al utilizar la disponibilidad de inventario, puede verificar su inventario antes de agregar un producto a las páginas **Presupuestos**, **Pedidos** o **Facturas** en aplicaciones en Microsoft Dynamics 365 Sales. Por ejemplo, comprueba el inventario y determina una fecha de cumplimiento como una tarea clave en el proceso [cliente potencial a efectivo](dual-write-prospect-to-cash.md).

Si no tiene suficiente inventario, puede estimar una fecha de entrega basada en los recibos y problemas de inventario proyectados. También puede verificar la información de neto no comprometido (ATP), donde puede encontrar la cantidad de ATP en el intervalo de tiempo predefinido.

## <a name="on-hand-inventory"></a>Inventario disponible

En Dynamics 365 Sales, se ha agregado un nuevo botón **Inventario disponible** al encabezado de las páginas **Presupuestos**, **Pedidos** y **Facturas**. Cuando selecciona este botón, aparece un cuadro de diálogo, donde puede especificar la empresa y el producto para el que desea comprobar el inventario disponible. Este cuadro de diálogo muestra la misma información que [Inventario disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

El cuadro de diálogo devuelve la información de inventario desde Dynamics 365 Supply Chain Management. Esta información incluye las siguientes cantidades:

- Cantidad disponible
- Cantidad disponible reservada
- Cantidad disponible lista
- Cantidad pedida
- Cantidad en pedido
- Cantidad solicitada reservada
- Cantidad total disponible

## <a name="atp-information"></a>Información de NNC

En Sales, se ha agregado un nuevo botón **Información de NNC** a los artículos de línea en las páginas **Presupuestos**, **Pedidos** y **Facturas**. Cuando selecciona este botón, aparece un cuadro de diálogo, donde puede especificar la empresa, el producto, el sitio del inventario, el almacén de inventario y la cantidad pedida. Este cuadro de diálogo tiene la misma configuración que se describe en [Compromisos de pedido](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

El cuadro de diálogo devuelve la información de NNC de Supply Chain Management. Esta información incluye las siguientes cantidades:

- Cantidad de NNC
- Cantidad de recepción
- Cantidad de emisión
- Cantidad disponible

## <a name="how-it-works"></a>Cómo funciona

Cuando selecciona el botón **Inventario disponible** en la página **Ofertas**, **Pedidos** o **Facturas**, se realiza una llamada de escritura dual en vivo a la API **Inventario disponible**. La API calcula el inventario disponible para el producto dado. El resultado se almacena en **InventCDSInventoryOnHandRequestEntity** y en las tablas **InventCDSInventoryOnHandEntryEntity**, y luego se escribe en Dataverse mediante escritura dual. Para utilizar esta funcionalidad, debe ejecutar los siguientes mapas de escritura dual. Omita la sincronización inicial cuando ejecute los mapas.

- Entradas de inventario de CDS disponibles (msdyn_inventoryonhandentries)
- Solicitudes de inventario de CDS disponibles (msdyn_inventoryonhandrequests)

## <a name="templates"></a>Plantillas

Las siguientes plantillas están disponibles para exponer los datos de inventario disponibles.

Aplicaciones de Finance and Operations | Aplicaciones Customer Engagement     | Descripción
---|---|---
[Entradas disponibles del inventario de CDS](mapping-reference.md#145) | msdyn_inventoryonhandentries |
[Solicitudes disponibles del inventario de CDS](mapping-reference.md#147) | msdyn_inventoryonhandrequests |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

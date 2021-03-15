---
title: Disponibilidad de inventario en doble escritura
description: Este tema proporciona información sobre cómo comprobar la disponibilidad de inventarios en doble escritura.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: a7bfe998d2d787203a507a831c171fc43b03fedc
ms.sourcegitcommit: cc9921295f26804259cc9ec5137788ec9f2a4c6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "4839558"
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

Aplicaciones de Finance and Operations | Aplicación Customer Engagement | Descripción 
---|---|---
[Entradas disponibles del inventario de CDS](#145) | msdyn_inventoryonhandentries |
[Solicitudes disponibles del inventario de CDS](#147) | msdyn_inventoryonhandrequests |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a>Entradas de inventario de CDS disponibles (msdyn_inventoryonhandentries)

Esta plantilla sincroniza datos entre aplicaciones de Finance and Operations y Dataverse.

Campo de Finance and Operations | Tipo de asignación | Campo Customer Engagement | Valor predeterminado
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a>Solicitudes de inventario de CDS disponibles (msdyn_inventoryonhandrequests)

Esta plantilla sincroniza datos entre aplicaciones de Finance and Operations y Dataverse.

Campo de Finance and Operations | Tipo de asignación | Campo Customer Engagement | Valor predeterminado
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
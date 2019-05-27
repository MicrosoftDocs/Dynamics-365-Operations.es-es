---
title: Búsqueda de inventario en el punto de venta (PDV)
description: En este tema se describen las opciones disponibles para ver la información de inventario en el punto de venta (PDV).
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: cd2dc460c9e862503ebbf1942dcf998d67829d86
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572058"
---
# <a name="inventory-lookup-in-the-point-of-sale-pos"></a>Búsqueda de inventario en el punto de venta (PDV)

[!include [banner](includes/banner.md)]

La búsqueda de inventario en el punto de venta (PDV) ayuda a los minoristas a lograr la excelencia operativa en tiempo real y obtener información conectando tiendas, el PDV y el back-office. Esta funcionalidad proporciona una vista precisa en tiempo real del inventario del producto en tiendas y centros de distribución. También ayuda a los minoristas a impulsar eficacias adicionales y ahorro de costes al mejorar la planificación del inventario en tiempo real.

Una vista precisa en tiempo real del inventario en una organización ayuda a los socios del almacén a proporcionar un servicio al cliente oportuno y superior. El momento que más importa es el momento en que el cliente está listo para tomar una decisión de compra. Es importante que los cajeros de la tienda tenga información en tiempo real sobre el inventario a su alcance, de modo que puedan comprometer con precisión la entrega y la recogida del producto.

Puede abrir la página **Búsqueda de inventario** del espacio de trabajo **Retail Modern POS** o del espacio de trabajo **Retail Cloud POS**.

![Icono de búsqueda de inventario en la página de inicio de PDV](media/POSHomepage.png)

En la página **Búsqueda de inventario**, puede utilizar el teclado numérico para introducir un número de producto. Puede ver la cantidad disponible para múltiples tiendas y almacenes.

![Página de búsqueda de inventario estándar](media/InventoryLookUp.png)

Las cantidades **Reservado** y **Pedido** también se muestran para cada ubicación.

- **Reservado**: la cantidad hace referencia al valor **Física reservada** del back-office para el número de producto especificado en la ubicación.
- **Pedido**: esta cantidad hace referencia al valor **Pedido en total** del back-office para el número de producto especificado en la ubicación.

## <a name="locations-that-inventory-availability-information-is-shown-for"></a>Ubicaciones para las que se muestra información de disponibilidad del inventario

La lista de ubicaciones incluye dos tipos de entidades:

- **Tiendas minoristas**: la lista muestra las tiendas que se configuran usando el grupo de localizadores de tiendas para la tienda actual en Central Retail.
- **Centros de distribución**: los distintos tipos de centros de distribución (como almacenes) pueden configurarse en Microsoft Dynamics 365 for Retail. Sin embargo, la lista muestra información de disponibilidad del inventario solo para centros de distribución del tipo predeterminado **Estándar** .

    > [!NOTE]
    > La información de disponibilidad del inventario no se muestra para almacenes de los tipos **Tránsito**, **Cuarentena** y **Mercancías en ruta** para el PDV.

En la página **Búsqueda de inventario**, puede ver las cantidades de neto no comprometido (NNC) para cada tienda, además de las cantidades disponibles actuales, las cantidades reservadas y las cantidades pedidas. Seleccione la tienda para ver la información de NNC y, a continuación, seleccione **Mostrar disponibilidad en tienda**.

![Cantidades ATP](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a>Apertura de la vista Matriz basada en dimensión para mostrar todas las variantes

En la página **Detalles de producto** de un producto maestro, o en la página **Búsqueda de inventario**, seleccione **Ver todas las variantes** desde la barra de la aplicación en la parte inferior de la página. La vista **Matriz basada en dimensión** para la versión inicial de estas páginas muestra la información de disponibilidad del inventario para todas las variantes de un producto para la tienda actual.

> [!NOTE]
> El botón **Ver todas las variantes** solo está disponible para los productos maestros del artículo que tienen variantes de producto. No está disponible para productos o kits independientes.

![Permite ver el botón de todas las variantes en la página Búsqueda de inventario](media/StandardToMatrix.png)

Seleccione **Ver todas las variantes** en la página **Detalles de producto** de un producto maestro, o en la página **Búsqueda de inventario**, sin seleccionar una ubicación, para ir a la vista **Matriz basada en dimensión** y ver la información de disponibilidad del inventario para todas las variantes de un producto para la tienda actual.

![Vista Matriz basada en dimensión para la página Búsqueda de inventario](media/Matrix.png)

> [!NOTE]
> En la ilustración anterior, el orden de visualización de las dimensiones es alfabético, ya que el orden de visualización de dimensiones no se configuró para el producto seleccionado.

En la vista **Matriz basada en dimensión**, las celdas para las variantes de producto incluyen un valor disponible en la esquina inferior derecha. La siguiente tabla explica el significado de los distintos valores.

| Valor disponible                            | Descripción |
|------------------------------------------|-------------|
| Valor numérico que es superior a 0 (cero) | Se liberó una variante para la ubicación seleccionada y puede realizar acciones adicionales en la celda. (Estas acciones se describirán con más detalle más adelante en este tema.) |
| **0** (cero)                             | Se liberó una variante para la ubicación seleccionada, pero el artículo no está disponible en la ubicación seleccionada. Sin embargo, puede realizar acciones adicionales en la celda. (Estas acciones se describirán con más detalle más adelante en este tema.) |
| **n/a** o una celda inactiva              | No se liberó una variante para la ubicación seleccionada y no puede realizar acciones adicionales en la celda. |

También puede cambiar el pivote para las dimensiones seleccionando la nueva dimensión a utilizar.

![Cambio de pivote](media/ChangePivot.png)

![Pivote modificado](media/PivotChanged.png)

> [!NOTE]
> En las ilustraciones anteriores, el orden de visualización de las dimensiones del producto seleccionado es personalizado (no alfabético). Se basa en el orden de visualización de la dimensión que se establece en el back-office.

Además, en el vista **Matriz basada en dimensión** se pueden realizar más acciones para ayudar a aumentar la productividad de un socio de la tienda. A continuación se incluyen algunos ejemplos:

- Cambie la ubicación de la tienda para buscar la disponibilidad del inventario de todas las variantes de producto en otras ubicaciones. Estas ubicaciones incluyen otras tiendas en el grupo de localizadores de tiendas y los centros de distribución del tipo predeterminado **Estándar** .
- Venda una variante del producto individual a un cliente mediante el uso de pago al contado sin entrega al domicilio, recogida en tienda o envío a una dirección.
- Proporcione al cliente información de NNC para una variante del producto individual en una ubicación concreta.

![Acciones adicionales en los iconos de variantes](media/VariantActions.png)

> [!NOTE]
> En la ilustración anterior, el orden de visualización de las dimensiones es alfabético, ya que el orden de visualización de dimensiones no se configuró para el producto seleccionado.

La siguiente tabla ofrece más información acerca de las acciones adicionales disponibles.

| Acción               | Descripción |
|----------------------|-------------|
| Vender ahora             | Agregue la variante del artículo seleccionada a la transacción y redirija al usuario a la pantalla de transacción. (Esta acción no está disponible cuando la ubicación seleccionada es un centro de distribución.) |
| Recoger en tienda     | Cree un pedido de cliente para la variante del producto que se recogerá de la ubicación seleccionada y redirija al usuario a la pantalla de transacción. (Esta acción no está disponible cuando la ubicación seleccionada es un centro de distribución.) |
| Enviar producto         | Cree un pedido de cliente para la variante del producto que se enviará desde la ubicación seleccionada y redirija al usuario a la pantalla de transacción. |
| Disponibilidad         | Muestre la información de NNC para la combinación de variantes seleccionada para la ubicación seleccionada. |
| Muestre tzodas las ubicaciones   | Cambie a la vista de búsqueda de inventario estándar y resalte la información de disponibilidad del inventario para la variante de artículo en todas las tiendas del grupo de localizadores de tiendas, y también en centros de distribución de tipo **Estándar/Predeterminado**. |
| Ver detalles del producto | Redirija al usuario a la página **Detalles de producto** del producto maestro asociado. |

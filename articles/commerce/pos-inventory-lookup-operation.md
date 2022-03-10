---
title: Operación de búsqueda de inventario en PDV
description: Este tema describe cómo utilizar la operación de búsqueda de inventario en el punto de venta (POS) de Dynamics 365 Commerce para ver la disponibilidad de inventario de productos en tiendas y almacenes.
author: boycezhu
ms.date: 08/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: ded7c0aa00d0806dfe4eb4e182abbbf66fd76d5b
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343845"
---
# <a name="inventory-lookup-operation-in-pos"></a>Operación de búsqueda de inventario en PDV

[!include [banner](includes/banner.md)]

Este tema describe cómo utilizar la operación de búsqueda de inventario en el punto de venta (POS) de Dynamics 365 Commerce para ver la disponibilidad de inventario de productos en tiendas y almacenes.

Una vista precisa del inventario en una organización ayuda a los socios del almacén a proporcionar un servicio al cliente oportuno y eficaz. El momento que más importa es el momento en que un cliente está listo para tomar una decisión de compra. Es importante que los cajeros de la tienda tenga información en tiempo real o casi en tiempo real sobre el inventario a su alcance, de modo que puedan comprometer con precisión la entrega y la recogida del producto.

La operación de búsqueda de inventario en el PDV de Commerce ayuda a los minoristas a lograr la excelencia operativa y obtener información al conectar las tiendas con las oficinas centrales de Commerce. Esta funcionalidad proporciona una vista de disponibilidad de inventario de productos en tiendas y almacenes. También ayuda a los minoristas a impulsar eficacias adicionales y ahorro de costes al mejorar la planificación del inventario en tiempo real.

Cuando la operación de búsqueda de inventario se inicia desde la aplicación del PVD, el cajero del PDV utiliza el teclado numérico para introducir un número de producto para consultar su información de inventario. Si el producto introducido tiene variantes, el cajero puede seleccionar opcionalmente dimensiones u otros valores para verificar la información de inventario de una variante de producto específica.

## <a name="inventory-lookup-list-view-for-individual-products"></a>Vista de lista de búsqueda de inventario para productos individuales

Para un producto individual, la operación de búsqueda de inventario proporciona una vista de lista de búsqueda de inventario que muestra la siguiente información del producto para una lista de ubicaciones:

- **Inventario** – Se refiere a la cantidad "física disponible" de un producto.
- **Reservado** – Se refiere a la cantidad "física reservada" recuperada de la sede central.
- **Pedido** - Se refiere a la cantidad "pedida en total" recuperada de la sede central.
- **Unidad** – Se refiere a la unidad de medida de inventario configurada en la sede central.

La vista de lista de ubicaciones incluye todas las tiendas y almacenes que están configurados en los grupos de proceso de entrega a los que está vinculada la tienda actual, como se muestra en la siguiente imagen de ejemplo.

![Vista de lista de la operación de búsqueda de inventario.](media/inventory-lookup-list-view.png)

> [!NOTE]
> Asegúrese de que su tienda actual esté incluida en los grupos de cumplimiento asociados.

Las siguientes acciones están disponibles en la barra de aplicaciones del PDV:

- **Ordenar** – Esta acción permite al usuario del PDV ordenar los datos en la vista de lista según varios criterios. El orden según la ubicación es la opción predeterminada.

    - **Ubicación geográfica** (desde la ubicación más cercana a la ubicación más lejana, según la distancia a la tienda actual)
    - **Nombre** (en orden ascendente o descendente)
    - **Número de la tienda** (en orden ascendente o descendente)
    - **Inventario** (en orden descendente)
    - **Reservado** (en orden descendente)
    - **Pedido** (en orden descendente)

- **Filtrar** – Esta acción permite al usuario del PDV ver datos filtrados para una ubicación específica.
- **Mostrar disponibilidad en tienda** – Esta acción permite al usuario del PDV ver las cantidades de neto no comprometido (NNC) para un producto en la tienda seleccionada.
- **Mostrar ubicación de la tienda** – Esta acción abre una página diferente para mostrar la vista del mapa, la dirección y el horario de la tienda seleccionada.
- **Recoger en tienda** – Esta acción crea un pedido de cliente para el producto que se recogerá de la tienda seleccionada y redirigirá al usuario a la pantalla de transacción.
- **Enviar producto** – Esta acción crea un pedido de cliente para el producto que se enviará de la tienda seleccionada y redirigirá al usuario a la pantalla de transacción.
- **Ver todas las variantes** – Para un producto con variantes, esta acción cambia de una vista de lista a una vista de matriz que muestra información de inventario para todas las variantes del producto.
- **Agregar a la transacción** – Esta acción agrega el producto al carrito y redirige al usuario a la pantalla de transacciones.

> [!NOTE]
> La clasificación basada en la ubicación que se introdujo en la versión 10.0.17 de Commerce muestra la tienda actual en la parte superior. Para otras ubicaciones, la distancia entre la ubicación y la tienda actual está determinada por las coordenadas (latitud y longitud) definidas en la sede central de Commerce. Para una tienda, la información de ubicación se define en la dirección principal de la unidad operativa asociada con la tienda. Para un almacén que no es una tienda, la información de ubicación se define en la dirección del almacén. Antes de la versión 10.0.17, la vista de lista siempre muestra la tienda actual en la parte superior y ordena otras ubicaciones alfabéticamente.
>
> Las acciones **Mostrar disponibilidad en tienda**, **Mostrar ubicación de la tienda**, **Recoger en tienda** y **Enviar producto** no están disponibles para ubicaciones que no sean tiendas.

## <a name="inventory-lookup-matrix-view-for-variants"></a>Vista de matriz de búsqueda de inventario para variantes

Para un producto maestro con variantes, la operación de búsqueda de inventario también proporciona una vista de matriz basada en dimensiones que muestra información de disponibilidad de inventario para todas las variantes del producto maestro en una ubicación seleccionada. De forma predeterminada, la vista de matriz muestra los datos de la tienda actual. Puede usar la acción **Tienda** en la barra de la aplicación para buscar información de inventario en otras tiendas configuradas en los grupos de proceso de entrega a los que está vinculada la tienda actual.

La siguiente imagen de ejemplo muestra la vista de matriz de búsqueda de inventario en el PDV.

![Vista de matriz de la operación de búsqueda de inventario.](media/inventory-lookup-matrix-view.png)

En la vista de matriz, cada celda representa una variante individual y muestra un valor de inventario disponible (físico disponible) en la esquina inferior derecha, así como valores de **reservado** (reservado físico) y **pedido** (pedidos en total) en la esquina superior izquierda. La siguiente tabla explica el significado de los distintos valores disponibles.

| Valor disponible                            | Descripción |
|------------------------------------------|-------------|
| Valor numérico que es superior a 0 (cero) | Se liberó una variante para la ubicación seleccionada y puede realizar acciones adicionales en la celda. |
| **0** (cero)                             | Se liberó una variante para la ubicación seleccionada, pero el artículo no está disponible en la ubicación seleccionada. Puede realizar acciones adicionales en la celda. |
| **n/a** o una celda inactiva              | No se liberó una variante para la ubicación seleccionada y no puede realizar acciones adicionales en la celda. |

El orden de visualización de los valores de dimensión en la vista de matriz se basa en la configuración del orden de visualización de dimensión en la sede central de Commerce. Puede cambiar la configuración del orden de visualización de la dimensión seleccionando una nueva dimensión para usar. 

Las acciones siguientes están disponibles en la celda de vista de matriz:

- **Vender ahora** – Esta acción agrega la variante seleccionada al carrito y redirige al usuario a la pantalla de transacciones.
- **Recoger en tienda** – Esta acción crea un pedido de cliente para la variante seleccionada que se recogerá de la tienda seleccionada y redirigirá al usuario a la pantalla de transacción.
- **Enviar producto** – Esta acción crea un pedido de cliente para la variante seleccionada que se enviará de la tienda seleccionada y redirigirá al usuario a la pantalla de transacción.
- **Disponibilidad** – Esta acción lleva al usuario a una página diferente que muestra las cantidades de NNC para la variante seleccionada en la tienda seleccionada.
- **Mostrar todas las ubicaciones** – Esta acción cambia a la vista de lista de disponibilidad de inventario estándar que muestra la información de inventario para la variante seleccionada.
- **Ver detalles del producto** – Esta acción redirige al usuario a la página de detalles del producto (PDP) de la variante seleccionada.

## <a name="access-inventory-lookup-from-other-pages-in-pos"></a>Acceder a la búsqueda de inventario desde otras páginas en el PDV

Los usuarios del PDV pueden acceder a la operación de búsqueda de inventario desde otras páginas en el PDV.

La siguiente imagen de ejemplo muestra los resultados de búsqueda de inventario desde una PDP en el PDV.

![Búsqueda de inventario desde la página de detalles del producto.](media/inventory-lookup-from-product-details-page.png)

En la PDP de un producto maestro, puede utilizar la acción **Ver todas las variantes** en la barra de la aplicación para iniciar la vista de matriz de búsqueda de inventario que muestra información de disponibilidad de inventario para la tienda actual en todas las variantes de un producto. Para un producto individual, la PDP muestra el valor de inventario disponible (físico disponible) de ese producto para la tienda actual. Además, puede seleccionar el vínculo **Inventario en otras tiendas** para iniciar la operación de búsqueda de inventario y así verificar la disponibilidad de inventario de un producto en otras tiendas o almacenes.

> [!NOTE]
> La acción **Ver todas las variantes** en la PDP solo está disponible para los productos maestros que tienen variantes. No está disponible para productos o kits específicos.

Puede configurar la operación de búsqueda de inventario para que aparezca como un vínculo en la cuadrícula de botones en la pantalla de transacciones del PDV. Después de la configuración, cuando el usuario selecciona una línea de carro y luego selecciona el botón **Búsqueda de inventario**, se mostrará la vista de lista de búsqueda de inventario para el producto seleccionado. Para obtener más información sobre cómo configurar cuadrículas de botones con la herramienta de diseñador de pantalla del PDV, consulte [Configuraciones visuales de la interfaz de usuario de PDV](pos-screen-layouts.md).

## <a name="inventory-lookup-with-channel-side-calculation"></a>Búsqueda de inventario con cálculo del lado del canal

En la versión 10.0.9 de Commerce y anteriores, el valor **físico disponible** de la operación de búsqueda de inventario se recupera desde la sede central de Commerce a través de una llamada de servicio en tiempo real. En la versión 10.0.10 de Commerce y posteriores, puede configurar la operación de búsqueda de inventario del PDV para usar el cálculo del lado del canal en el servidor de Commerce para determinar el valor físico disponible, lo que puede proporcionar una estimación más fiable y precisa del inventario disponible, teniendo en cuenta los datos transaccionales que aún no están sincronizados con la sede central. Para obtener más información sobre el cálculo del inventario del lado del canal y la configuración del PDV relacionada en la sede central, consulte [Calcular la disponibilidad de inventario para canales comerciales](calculated-inventory-retail-channels.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configuraciones visuales de la interfaz de usuario de PDV](pos-screen-layouts.md)

[Calcular la disponibilidad de inventario para canales comerciales](calculated-inventory-retail-channels.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

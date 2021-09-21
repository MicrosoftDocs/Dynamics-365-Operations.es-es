---
title: Reservas de visibilidad de inventario
description: Este tema describe cómo configurar la función de reserva para crear reservas, consumir reservas o anular la reserva de cantidades de inventario especificadas mediante el uso de Visibilidad de inventario.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: acc5d5f93f3f625892aac37780a44e221b6eb5ac
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475045"
---
# <a name="inventory-visibility-reservations"></a>Reservas de visibilidad de inventario

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tema describe cómo configurar la función de reserva para crear reservas, consumir reservas o anular la reserva de cantidades de inventario especificadas mediante el uso de Visibilidad de inventario.

Las reservas marcan una cantidad de inventario que se utilizará en el futuro. Cuando crea una reserva, el sistema evita que otros pedidos reserven o consuman los bienes reservados hasta que la reserva se consuma o se anule. Las reservas se crean, consumen y cancelan mediante llamadas de API al servicio de visibilidad de inventario.

Opcionalmente, puede configurar Microsoft Dynamics 365 Supply Chain Management (y otros sistemas de terceros) para compensar automáticamente la cantidad que se ha reservado mediante el uso de visibilidad de inventario. La cantidad de compensación se elimina de los registros de reserva en Visibilidad de inventario.

Cuando activa la función de reserva, Supply Chain Management está automáticamente lista para compensar las reservas que se realizan mediante el uso de visibilidad de inventario.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Activar y configurar la función de reserva

Para activar la función de reserva, siga estos pasos.

1. Inicie sesión en Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Gestión de funciones**, active la función *OnHandReservation*.
1. Inicie sesión en de Supply Chain Management.
1. Vaya al espacio de trabajo **[Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** y habilite la función *Integración de visibilidad de inventario con compensación de reserva* (requiere la versión 10.0.22 o posterior).
1. Vaya a **Gestión del inventario \> Configuración \> Parámetros de integración de visibilidad de inventario**, abra la pestaña **Compensación de reserva** y realice los siguientes ajustes:
    - **Habilitar compensación de reserva** - Ajustado a *Sí* para habilitar esta funcionalidad.
    - **Modificador de compensación de reserva** - Seleccione el estado de la transacción de inventario que compensará las reservas realizadas en Visibilidad de inventario. Esta configuración determina la etapa de procesamiento del pedido que desencadena las compensaciones. La etapa se rastrea por el estado de la transacción de inventario del pedido. Elija una opción de las siguientes:
        - *En orden* - Para el estado *En la transacción*, un pedido enviará una solicitud de compensación cuando se cree. La cantidad de compensación será la cantidad del pedido creado.
        - *Reserva* – Para el estado *Transacción de reserva solicitada*, un pedido enviará una solicitud de compensación cuando esté reservado, recogido, publicado en el albarán o facturado. La solicitud se disparará solo una vez, para el primer paso cuando se produzca el proceso mencionado. La cantidad de compensación será la cantidad a partir de la cual cambió el estado de la transacción de inventario de *En orden* a *Reservado ordenado* (o estado posterior) en la línea de pedido correspondiente.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Utilizar la función de reserva en Visibilidad de inventario

Cuando llama a la API de reservas, el sistema marca la reserva de las mercancías y cantidades especificadas. Debe definir una jerarquía de reserva y registrar solicitudes que coincidan con esa jerarquía de reserva. Las reservas se pueden realizar llamando directamente a las API de reservas.

### <a name="configure-the-reservation-hierarchy"></a>Configurar la jerarquía de reservas

La jerarquía de reservas describe la secuencia de dimensiones que deben especificarse cuando se realizan las reservas. Funciona de la misma forma que la jerarquía de índices para las consultas de inventario disponible.

La jerarquía de reservas puede diferir de la jerarquía de índices. Esta independencia le permite implementar la gestión de categorías donde los usuarios pueden desglosar las dimensiones en detalles para especificar los requisitos para hacer reservas más precisas.

Para configurar una jerarquía de reserva flexible en Power Apps, abra la página **Configuración** y luego, en la ficha **Jerarquía de reserva flexible**, configure la jerarquía de reserva agregando o modificando dimensiones y sus niveles de jerarquía.

Su jerarquía de reservas blandas debe contener `SiteId` y `LocationId` como componentes, porque construyen la configuración de la partición.

Para obtener más información sobre cómo configurar reservas, consulte [Configuración de reservas](inventory-visibility-configuration.md#reservation-configuration).

### <a name="call-the-reservation-api"></a>Llamar a la API de reservas

Las reservas se realizan en el servicio de visibilidad de inventario mediante el envío de una solicitud POST a la URL del servicio, como `/api/environment/{environment-ID}/onhand/reserve`.

Para una reserva, el cuerpo de la solicitud debe contener un Id. de organización, un Id. de producto, cantidades reservadas y dimensiones. La solicitud genera un Id. de reserva único para cada registro de reserva. El registro de reservas contiene la combinación única del Id. del producto y las dimensiones.

Cuando llama a la API de reserva, puede controlar la validación de la reserva especificando el parámetro booleano `ifCheckAvailForReserv` en el cuerpo de la solicitud. Un valor `True` significa que se requiere la validación, mientras que un valor `False` significa que la validación no es necesaria. El valor predeterminado es `True`.

Si desea cancelar una reserva o anular la reserva de cantidades de inventario especificadas, establezca la cantidad en un valor negativo y establezca el parámetro `ifCheckAvailForReserv` en `False` para omitir la validación.

A continuación, se muestra un ejemplo del cuerpo de la solicitud, como referencia.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "SoftReservOrdered",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

## <a name="offset-reservations-in-supply-chain-management"></a>Compensar reservas en Supply Chain Management

Para los estados de transacciones de inventario que incluyen un modificador de compensación de reserva específico, la actualización de la transacción compensará el registro de reserva correspondiente cuando se cumplan todas las condiciones siguientes:

- El Id. de reserva en la transacción de inventario coincide con el Id. de reserva del registro de reserva en el servicio de visibilidad de inventario.
- Las dimensiones de la transacción de inventario son idénticas a las dimensiones del registro de reserva en el servicio de visibilidad de inventario.
- Los cambios en el estado de la transacción de inventario desencadenan compensaciones para las reservas cuando el estado de la transacción de inventario refleja el hecho de que se ha completado o omitido un proceso de pedido.

La cantidad de compensación sigue la cantidad de inventario que se especifica en las transacciones de inventario. La compensación no tiene efecto si no queda ninguna cantidad reservada en el servicio de visibilidad de inventario.

### <a name="set-up-the-reservation-offset-modifier"></a>Configurar el modificador de compensación de reserva

Si aún no lo ha hecho, configure el modificador de reserva como se describe en [Encienda y configure la función de reserva](#turn-on).

### <a name="set-up-reservation-ids"></a>Configurar Id. de reserva

El Id. de reserva marca de forma única un registro de reserva en Visibilidad de inventario. En Supply Chain Management, los usuarios colocan reservas en las líneas de pedido para marcar la compensación para el registro de reserva correspondiente.

Para configurar Id. de reserva en Supply Chain Management, siga estos pasos.

1. Abra un pedido de ventas (por ejemplo, desde la página **Todos los pedidos de venta**).
1. En la ficha desplegable **Líneas de pedido de ventas**, seleccione una línea de pedido.
1. En la ficha desplegable **Líneas de pedido de ventas**, en la barra de herramientas, seleccione **Actualizar línea\> Inventario\> Integración de Visibilidad de inventario**.
1. Introduzca los Id. de reserva relevantes.

El cambio de estado del inventario coincide con la configuración del modificador de compensación.

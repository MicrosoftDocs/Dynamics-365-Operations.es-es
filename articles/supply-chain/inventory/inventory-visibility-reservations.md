---
title: Reservas de Inventory Visibility
description: Este artículo describe cómo configurar la función de reserva para crear reservas, consumir reservas o anular la reserva de cantidades de inventario especificadas mediante el uso de Visibilidad de inventario.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0ae0589f8bac7ebf9b43cf0f3bc02680d324b29b
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762751"
---
# <a name="inventory-visibility-reservations"></a>Reservas de Inventory Visibility

[!include [banner](../includes/banner.md)]

Este artículo describe un caso de uso típico para reservas flexibles y explica cómo configurarlas en Inventory Visibility. Incluye información sobre cómo crear reservas flexibles, compensarlas con el consumo físico y ajustar o anular la reserva de cantidades de inventario específicas.

## <a name="sample-use-case-for-soft-reservation"></a>Ejemplo de caso de uso para reserva suave

Las reservas flexibles ayudan a las organizaciones a lograr una única fuente de confianza para el inventario disponible, especialmente durante el proceso de cumplimiento de pedidos. Esta funcionalidad es útil para organizaciones donde existen las siguientes condiciones:

- La organización tiene al menos dos sistemas diferentes que toman directamente los pedidos de salida.
- La organización es muy estricta y quiere evitar la doble reserva de inventario de productos, lo que puede ocurrir si varios sistemas pueden sobrevender la última pieza de stock. Esta situación se evita cuando todos los sistemas de pedidos pueden realizar llamadas API de reserva suave instantáneas a Inventory Visibility, que proporciona una única fuente de información para la disponibilidad de inventario.

[<img src="media/inventory-visibility-soft-reservation.png" alt="Inventory Visibility soft reservation." title="Reservas no en firme de Inventory Visibility" width="720" />](media/inventory-visibility-soft-reservation.png)

La ilustración anterior muestra cómo funciona la reserva suave y destaca las siguientes operaciones:

- Su nivel de inventario inicial está sincronizado con Inventory Visibility de Microsoft Dynamics 365 Supply Chain Management.
- Las reservas flexibles se publican desde cada uno de sus canales o sistemas de pedidos en Visibilidad de inventario. Inventory Visibility valida la disponibilidad del inventario e intenta hacer una reserva suave. Si la reserva anticipada tiene éxito, la visibilidad del inventario se suma a la cantidad reservada anticipada, se deduce de la cantidad disponible para reserva (AFR) y responde con un ID de reserva anticipada.
- En este momento, la cantidad de su inventario físico sigue siendo la misma.
- A continuación, puede sincronizar pedidos con reserva temporal individuales o agregados (líneas de pedido) en Supply Chain Management para realizar reservas en firme y enviarlas al almacén o actualizar la cantidad de inventario final.
- Puede configurar el sistema para [compensar reservas no en firme](#offset-scm) cuando el inventario físico se actualiza en Supply Chain Management.

Las reservas no en firme normalmente se crean, consumen y cancelan mediante llamadas de API al servicio de visibilidad de inventario.

> [!NOTE]
> Opcionalmente, puede configurar Supply Chain Management (y otros sistemas de terceros) para compensar automáticamente la cantidad que se ha reservado mediante el uso de visibilidad de inventario. La cantidad de compensación se elimina de los registros de reserva en Visibilidad de inventario.
>
> De forma predeterminada, la función de compensación se activa automáticamente cuando habilita la función de reserva suave.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Activar y configurar la función de reserva

Para activar la función de reserva, siga estos pasos.

1. Inicie sesión en Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración**.
1. En la ficha **Gestión de funciones**, active la función *OnHandReservation*.
1. Inicie sesión en su entorno de Supply Chain Management.
1. Vaya al espacio de trabajo **[Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** y habilite la función *Integración de visibilidad de inventario con compensación de reserva* (requiere la versión 10.0.22 o posterior).
1. Vaya a **Gestión del inventario \> Configuración \> Parámetros de integración de visibilidad de inventario**, abra la pestaña **Compensación de reserva** y realice los siguientes ajustes:

    - **Habilitar compensación de reserva** - Ajustado a *Sí* para habilitar esta funcionalidad.
    - **Modificador de compensación de reserva** - Seleccione el estado de la transacción de inventario que compensará las reservas que se realizan en Visibilidad de inventario. Esta configuración determina la etapa de procesamiento del pedido que desencadena las compensaciones. La etapa se rastrea por el estado de la transacción de inventario del pedido. Seleccione uno de los siguientes valores:

        - *En orden* - Los pedidos que tienen un estado *En pedido*, un pedido enviará una solicitud de compensación cuando se cree. La cantidad de compensación será la cantidad (de la línea) del pedido creado.
        - *Reservar* – Las órdenes que tienen un estado *Reservar* enviarán una solicitud de compensación cuando estén reservados para pedidos o reservados físicamente. Cuando compensas en el estado *Reservar*, el pedido enviará una solicitud de compensación en cualquier estado de inventario nuevo que sea más cercano al recogido reservado (por ejemplo, recogido, albarán registrado o facturado). Este comportamiento se produce incluso si omite la reserva en Supply Chain Management y continúa con otro estado de inventario (por ejemplo, si salta de liberación a almacén para recoger y empacar). La solicitud se activará una sola vez. Si se activó en el momento de la selección, no duplicará la compensación cuando se registre un albarán. La cantidad de compensación será la misma cantidad de estado de la transacción de inventario cuando se desencadenó la comensación (es decir, *Solicitado reservado*/*Reserva física* o un estado posterior en la línea de pedido correspondiente).

1. Vuelva a iniciar sesión en la aplicación Visibilidad de inventario, vaya a la página **Configuración** y luego, en la pestaña **Reserva no en firme**, revise la jerarquía de reserva flexible predeterminada. Agregue nuevas dimensiones a la jerarquía según sea necesario.
1. En la sección **Establecer asignación de reserva flexible**, vea la configuración predeterminada. De forma predeterminada, las cantidades de inventario con reserva temporal se registrarán en la medida física `softreservephysical` de la fuente de datos `iv`. La medida calculada de *Disponible para reserva* se asigna a `availabletoreserve`. Si desea actualizar la medida calculada `availabletoreserve`, vaya a la página **Configuración** y, luego, en la pestaña **Medida calculada**, expanda y modifique la medida calculada.

Para obtener más información, consulte [Configurar la visibilidad de inventario](inventory-visibility-configuration.md).

> [!NOTE]
> La jerarquía de reservas describe la secuencia de dimensiones que deben especificarse cuando se realizan las reservas. Funciona de la misma manera que la jerarquía de índices para las consultas disponibles, pero se usa de forma independiente para que los usuarios puedan especificar los detalles de las dimensiones para hacer reservas más precisas.
>
> Su jerarquía de reservas blandas debe contener `SiteId` y `LocationId` como componentes, porque construyen la configuración de la partición de Visibilidad de inventario.

Para obtener más información sobre cómo configurar reservas, consulte [Configuración de reservas](inventory-visibility-configuration.md#reservation-configuration).

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Utilizar la función de reserva en Visibilidad de inventario

Cuando llama a la API de reservas, el sistema marca la reserva de las mercancías y cantidades especificadas.

Aquí hay un escenario de ejemplo y un cuerpo de consulta de API de muestra. La empresa Contoso vende el producto D0002 (armario) desde su sitio web de comercio electrónico. Un cliente realiza un pedido de venta de un pequeño gabinete rojo a través del sitio web. Contoso decide cumplir con este pedido mediante las siguientes dimensiones:

- Id. de organización = usmf
- Sitio = 1
- Almacén = 11
- Producto = D0002
- Color = rojo
- Tamaño = pequeño

Contoso ya ha configurado una conexión de API a Visibilidad de inventario desde su propio sistema de comercio electrónico. Cuando se recibe el pedido, el sistema activa instantáneamente una llamada API para hacer una reserva suave para el gabinete en Visibilidad de inventario.

### <a name="create-soft-reservations-using-the-reservation-api"></a>Crear reservas no en firme utilizando la API de reservas

Las reservas se realizan en el servicio de visibilidad de inventario mediante el envío de una solicitud POST a la URL del servicio, como `/api/environment/{environmentId}/onhand/reserve`.

Para una reserva, el cuerpo de la solicitud debe contener un Id. de organización, un Id. de producto, cantidades reservadas y dimensiones.

Cuando llama a la API de reserva, puede controlar la validación de la reserva especificando el parámetro booleano `ifCheckAvailForReserv` en el cuerpo de la solicitud. Un valor `True` significa que se requiere la validación, mientras que un valor `False` significa que la validación no es necesaria. El valor predeterminado es `True`.

Si desea cancelar una reserva o anular la reserva de cantidades de inventario especificadas, establezca la cantidad en un valor negativo y establezca el parámetro `ifCheckAvailForReserv` en `False` para omitir la validación.

Este es un ejemplo del cuerpo de la solicitud que hace referencia al pedido de ventas en el contexto anterior.

```json
# Url

#Replace {endpoint} with your system endpoint.
    {endpoint}/api/environment/{environmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "Testrequest-0005",
    "organizationId": "usmf",
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "softreservphysical",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

Una solicitud de reserva suave exitosa devuelve un *Id. de reserva no en firme* para cada registro de reserva. El ID de reserva flexible no es un identificador único para un registro de reserva flexible individual, sino una combinación del ID del producto y los valores de dimensión que están asociados con la solicitud de reserva flexible. Puede registrar el ID de reserva flexible en la línea del pedido cuando sincroniza los pedidos reservados con éxito con Supply Chain Management u otro sistema ERP para la compensación.

### <a name="offset-soft-reservations-in-supply-chain-management"></a><a name="offset-scm"></a>Compensar reservas no en firme en Supply Chain Management

Puede compensar una cantidad con reserva temporal después de que la cantidad de un pedido se haya deducido físicamente en Supply Chain Management u otro sistema ERP. Inventory Visibility ofrece una integración de compensación de reserva suave lista para usar con Supply Chain Management.

Para compensr una reserva no en firme, siga estos pasos.

1. Inicie sesión en de Supply Chain Management.
1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Vuelva a crear el pedido de ventas externo y agregue una línea de ventas que use exactamente los mismos valores de Id. de producto, organización, sitio, almacén y dimensiones.
1. En la ficha desplegable **Líneas de pedido de ventas**, seleccione la línea de ventas que acaba de introducir y, luego, en la barra de herramientas, **Inventario \> Id. de reserva**.
1. Siga uno de estos pasos:

    - Copie el ID de la reserva provisional en su respuesta de solicitud de reserva provisional y péguelo en el campo **ID de reserva**.
    - Deje el campo **ID de reserva** en blanco, pero seleccione la casilla **Compensación automática del servicio de inventario**. El sistema determinará automáticamente qué producto y qué dimensiones del producto compensar, según el ID del artículo y los valores de dimensión que se ingresan en la línea seleccionada.

1. Seleccione **Aceptar**.
1. Con la misma línea de ventas aún seleccionada, seleccione, reserve físicamente la cantidad solicitada seleccionando **Inventario \> Reserva** en la barra de herramientas de la ficha desplegable **Líneas de pedido de ventas**.
1. Si ha configurado previamente el campo **Modificador de compensación de reserva** como *Reservado*, la compensación se activará cuando la línea de pedido tenga un estado de *Reserva física* o *Reserva ordenada*. Un trabajo por lotes se ejecuta una vez por minuto para sincronizar las solicitudes de compensación de Supply Chain Management con Inventory Visibility.

> [!NOTE]
> Para los estados de transacciones que incluyen un modificador de compensación de reserva específico, la actualización de la transacción compensará el registro de reserva correspondiente cuando se cumplan todas las condiciones siguientes:
>
> - El Id. de reserva en la transacción de inventario coincide con el Id. de reserva del registro de reserva en Visibilidad de inventario.
> - Las dimensiones de la transacción de inventario coinciden con las dimensiones del registro de reserva en Visibilidad de inventario.
> - Los cambios en el estado de la transacción de inventario desencadenan compensaciones para las reservas cuando el estado de la transacción de inventario refleja el hecho de que se ha completado o omitido un proceso de pedido.

Las cantidades de compensación siguen las cantidades de inventario que se especifican en las transacciones de inventario pertinentes. Una compensación tiene efecto solo si queda cantidad reservada en Visibilidad de inventario.

### <a name="cancel-or-revert-a-soft-reservation"></a>Cancelar o revertir una reserva blanda

Si se cancela o elimina una línea de pedido original y debe revertir la reserva flexible correspondiente, publique una cantidad negativa que tenga exactamente la misma información en el cuerpo de su consulta API.

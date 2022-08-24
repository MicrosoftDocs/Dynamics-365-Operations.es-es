---
title: Sincronizar a petición con el motor de precios de Supply Chain Management
description: Este artículo describe cómo usar el motor de precios en Microsoft Dynamics 365 Supply Chain Management de Microsoft Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 727e60ceee3f5c8c33d2da93128eedc1dc7bcb9f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288968"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Sincronizar a petición con el motor de precios de Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management incluye un motor de precios que gestiona acuerdos comerciales, listas de precios, programas de fidelización de clientes, promociones y descuentos. El motor de fijación de precios utiliza reglas complejas para determinar el mejor precio para un presupuesto o pedido determinado. Cuando usa doble escritura, usa precios estáticos o el motor de precios de Supply Chain Management en las páginas de **Presupuesto** y **Pedido** en Microsoft Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Usar el motor de precios de Supply Chain Management en Sales

1. En Sales, vaya a **Ventas \> Pedidos**.
1. Seleccione **Nuevo** para crear un pedido nuevo o seleccione uno ya existente en la lista **Mis pedidos**.
1. Agregar una línea de pedido nueva.
1. Si está creando un nuevo pedido, seleccione **Precio de pedido** en el panel de acciones. Si está actualizando un pedido ya existente, seleccione **Recalcular** en el panel de acciones.
1. Las siguientes columnas se rellenan automáticamente:

    - Detalles del importe
    - % de descuento
    - Descuento
    - Importe previo al flete
    - Importe del flete
    - Impuestos totales
    - Importe total

> [!NOTE]
> Se aplica un proceso similar cuando crea cotizaciones.

## <a name="how-it-works"></a>Cómo funciona

Cuando crea un pedido en Sales, ese pedido se sincroniza inmediatamente con Supply Chain Management utilizando los valores que ingresó en Sales. Cuando selecciona **Pedido de precio** o **Cotización** en Sales, Supply Chain Management calcula el precio de cada línea de pedido y el pedido total, según las reglas del acuerdo comercial que se definen en Supply Chain Management. Los nuevos valores calculados luego se sincronizan con Ventas.

## <a name="set-trade-agreement-evaluation-options-in-supply-chain-management"></a>Establecer opciones de evaluación de acuerdos comerciales en Supply Chain Management

Puede configurar Supply Chain Management para respetar o ignorar los acuerdos comerciales cuando calcula el precio de un pedido que se creó en Sales. Para establecer esta opción, siga estos pasos.

1. Inicie sesión en su entorno de Supply Chain Management.
1. Vaya a **Clientes \> Configuración \> Parámetros de clientes**.
1. En la pestaña **Precios**, en la ficha desplegable **Evaluación de acuerdos comerciales**, agregue o elimine la fila para la directiva **Entrada manual** como usted requiere. La presencia o ausencia de esta política controla si el motor de precios de Supply Chain Management anulará automáticamente el precio de venta que se ingresó en Sales.

    - Si la directiva **Entrada manual** *no está* presente en la configuración de **Evaluación de acuerdos comerciales**, Supply Chain Management es el maestro de precios. Cuando un usuario selecciona **Orden de precio** o **Cotización** en el Panel de acciones en Sales, se llama al motor de precios de Supply Chain Management y se sobrescribe el precio de venta que se ingresó en Sales, a menos que sea igual al precio de venta que se calcula en Supply Chain Management.
    - Si la directiva **Entrada manual** *está* presente en la configuración de **Evaluación de acuerdos comerciales**, Sales es el maestro de precios. Se evita que el precio de venta que se ingresó en Sales se sobrescriba automáticamente cuando un usuario selecciona **Orden de precio** o **Cotización** en el Panel de acciones en Sales.
    - Líneas de pedido y líneas de cotización que tienen un valor de **Precio por unidad** y/o **Descuento** de *0* (cero) en Sales se tratan como un caso especial. Si el precio de un acuerdo comercial relevante está disponible, Supply Chain Management *siempre* lo aplicará a estos campos, independientemente de la configuración de **Evaluación de acuerdos comerciales**.

    Para ver un ejemplo de cada uno de estos casos, consulte los escenarios siguientes.

## <a name="example-scenario-1-trade-agreement-evaluation-without-the-manual-entry-option"></a>Escenario de ejemplo 1: Evaluación de acuerdos comerciales, sin la opción Entrada manual

En este escenario, la configuración **Entrada manual** en Supply Chain Management *no* incluye la directiva de **Entrada manual**. Un usuario de Sales ingresa una línea de pedido que tiene un precio de venta distinto de cero en Sales y no se define ningún precio de venta para el artículo en Supply Chain Management.

1. En Sales, un usuario crea una línea de pedido que tiene un **Precio por unidad** valor de 1 dólar estadounidense (USD).
1. La línea de pedido se sincroniza con Supply Chain Management con un precio de venta de 1 USD.
1. En Sales, el usuario selecciona **Orden de precio** en el Panel de acciones.
1. Supply Chain Management busca precios y descuentos relevantes y luego calcula los totales. Dado que el artículo no tiene precio de venta en Supply Chain Management, el cálculo actualiza la línea para que tenga un precio de venta de 0 USD.
1. El nuevo precio de venta de la línea se sincroniza con Sales.
1. El resultado es una línea de pedido en Sales que tiene un precio de venta de 0 USD.

## <a name="example-scenario-2-trade-agreement-evaluation-with-the-manual-entry-option"></a>Escenario de ejemplo 2: Evaluación de acuerdos comerciales, con la opción Entrada manual

En este escenario, la configuración **Entrada manual** en Supply Chain Management *sí* incluye la directiva de **Entrada manual**. Un usuario de Sales ingresa una línea de pedido que tiene un precio de venta distinto de cero en Sales. Supply Chain Management incluye un acuerdo comercial que establece un precio de venta de 2 USD para el artículo solicitado.

1. En Sales, un usuario crea una línea de pedido para un artículo que tiene un **Precio por unidad** de 1 dólar estadounidense (USD).
1. La línea de pedido se sincroniza con Supply Chain Management con un precio de venta de 1 USD.
1. En Sales, el usuario selecciona **Orden de precio** en el Panel de acciones.
1. Debido a que la opción **Evaluación de acuerdos comerciales** en Supply Chain Management incluye la directiva **Entrada manual**, el precio de venta no cambia, aunque un acuerdo comercial aplicable especifique otro precio de venta.
1. El precio de venta permanece sin cambios en Sales y en Supply Chain Management.

## <a name="example-scenario-3-trade-agreement-evaluation-for-an-item-that-has-a-sales-price-of-zero-in-sales"></a>Escenario de ejemplo 3: Evaluación de acuerdo comercial para un artículo que tiene un precio de venta de cero en Sales

En este escenario, la configuración **Entrada manual** en Supply Chain Management *sí* incluye la directiva de **Entrada manual**. El usuario de Sales ingresa una línea de pedido que tiene un precio de venta de 0 (cero) en Sales. Supply Chain Management incluye un acuerdo comercial que establece un precio de venta de 2 USD para un artículo solicitado.

1. En Ventas, un usuario crea una línea de pedido que tiene un valor de **Precio por unidad** de 0 USD y un valor de **Descuento de línea** de 0 USD.
1. La línea de pedido se sincroniza con Supply Chain Management con un precio de venta de 0 USD.
1. Debido a que recibió una línea de pedido que tiene un precio de venta de 0 (cero), Supply Chain Management llama a su motor de fijación de precios, aunque la opción **Entrada manual** está habilitada. El motor de precios devuelve el precio de venta de 2 USD establecido por el acuerdo comercial y actualiza la línea de pedido en Supply Chain Management.
1. El precio de venta actualizado aún no está sincronizado con la línea de pedido en Ventas.
1. En Sales, el usuario selecciona **Orden de precio** en el Panel de acciones.
1. La línea de pedido en Supply Chain Management mantiene su precio de venta de 2 USD, que ahora está sincronizado con Ventas. Por lo tanto, el valor de **Precio por unidad** de la línea de pedido en Sales se actualiza de 0 USD a 2 USD.
1. En Sales, el usuario ingresa un nuevo valor de **Descuento de línea** de 0,50 USD. Sales ahora calcula que el valor de **Monto extendido** de la línea es 1,50 USD.
1. La línea de pedido se sincroniza con Supply Chain Management con un valor de **Descuento de línea** de 0,50 USD:
1. En Sales, el usuario selecciona **Orden de precio** en el Panel de acciones.
1. No se modifican los precios ni los descuentos para la línea de pedido en Sales.

## <a name="limitations"></a>Limitaciones

Cuando se completan las columnas en Sales, se aplican las siguientes limitaciones:

- La configuración de cargos y asignaciones de cargos en Supply Chain Management no se replica en Sales.
- El precio no considera precios minoristas especiales que se especifican en la columna **Canal minorista** en la página de línea de pedido de ventas en Supply Chain Management.
- Descuentos que se definen en la sección **Gestión de permisos comerciales** de Supply Chain Management no se tienen en cuenta.
- El precio no considera los acuerdos de venta.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

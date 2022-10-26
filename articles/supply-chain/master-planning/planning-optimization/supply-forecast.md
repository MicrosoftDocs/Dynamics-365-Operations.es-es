---
title: Planificación maestra con previsiones de suministro
description: Este artículo describe cómo se consideran las previsiones de suministro durante la planificación maestra.
author: t-benebo
ms.date: 09/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-21
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: dc83d10851958ec67166cb7e40cfd84dceae6651
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690098"
---
# <a name="master-planning-with-supply-forecasts"></a>Planificación maestra con previsiones de suministro

[!include [banner](../../includes/banner.md)]

Las previsiones de suministro le permiten especificar el suministro que espera necesitar durante algún período futuro. Por lo general, basará la estimación en el historial de ventas del año anterior y luego utilizará el pronóstico para fines presupuestarios. También puede configurar sus planes maestros para considerar los pronósticos durante la planificación.

## <a name="set-up-a-master-plan-to-consider-supply-forecasts"></a>Establezca un plan maestro para considerar las previsiones de suministro

Puede especificar si cada plan maestro debe tener en cuenta las previsiones cuando se ejecuta. Utilice el siguiente procedimiento para configurar las opciones de previsión para cada plan.

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. Seleccione un plan maestro existente en el panel de lista, o seleccione **Nuevo** en el Panel de acciones para crear uno nuevo.
1. En la ficha rápida **General**, establezca los siguientes campos:

    - **Modelo de previsión** – Seleccionar el modelo que contiene las previsiones de oferta y/o demanda que debe considerar el plan maestro.
    - **Incluir previsión de suministro** - Establezca esta opción en *Sí* si el plan maestro debe tener en cuenta las previsiones de suministro.
    - **Incluir previsión de demanda** - Establezca esta opción en *Sí* si el plan maestro debe tener en cuenta las previsiones de demanda. Aunque este ajuste es independiente de la configuración **Incluir previsión de suministro**, algunas de las otras configuraciones en la página se aplican tanto a los pronósticos de suministro como a los pronósticos de demanda. Para obtener más información sobre la planificación que tiene en cuenta las previsiones de demanda, consulte [Planificación maestra con pronósticos de demanda](demand-forecast.md).
    - **Método utilizado para reducir los requisitos de pronóstico** - Seleccione el método para reducir los requisitos duarnte la planificación maestra:

        - *Ninguna* – Los requisitos de previsión no se reducirán durante la planificación maestra.
        - *Porcentaje - clave de reducción* - Los requisitos de previsión se reducirán en función de los porcentajes y los períodos de tiempo definidos en la clave de reducción.
        - *Transacciones - clave de reducción* - Los requisitos de previsión se reducirán mediante las transacciones que se producen durante los períodos de tiempo definidos en la clave de reducción.
        - *Transacciones - período dinámico* - Los requisitos de previsión se reducirán por las transacciones de pedidos que tienen lugar durante el período dinámico. El período dinámico cubre las fechas de previsión actuales y finaliza cuando comienza la próxima previsión. El método *Transacciones: período dinámico* no usa ni requiere una clave de reducción, y cuando la usa, se aplican las siguientes condiciones:

            - Si la previsión se reduce por completo, los requisitos de previsión para la previsión actual se convierten en 0 (cero).
            - Si no hay previsión futura, se reducen los requisitos de previsión de la última previsión que se introdujo.
            - Se incluyen límites de tiempo en el cálculo de la reducción de previsión.
            - Se incluyen días positivos en el cálculo de la reducción de previsión.
            - Si las transacciones de pedidos reales sobrepasan a los requisitos previstos, las transacciones restantes no se reenvían al próximo período de previsión.

        > [!NOTE]
        > El ajuste **Método utilizado para reducir los requisitos de pronóstico** también se aplica a los pronósticos de demanda si los ha habilitado para el plan maestro y los afecta de manera similar. Para obtener más información, consulte [Planificación maestra con previsiones de demanda](demand-forecast.md).

## <a name="set-reduction-options-for-coverage-groups"></a>Establecer opciones de reducción para grupos de cobertura

Para establecer opciones que controlen cómo un grupo de cobertura reducirá sus requisitos de pronóstico para planes maestros que usan reducción basada en transacciones, siga estos pasos.

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Grupos de cobertura**.
1. Seleccione un grupo de cobertura existente en el panel de lista o seleccione **Nuevo** en el Panel de acciones para crear uno nuevo.
1. En la ficha desplegalbe **Otro**, en el campo **Reducir el pronóstico en**, especifique cómo se deben reducir los requisitos de previsión de suministro para los elementos del grupo de cobertura, para planes maestros donde el campo **Método utilizado para reducir los requisitos de pronóstico** está configurado en *Transacciones - clave de reducción* o *Transacciones - período dinámico*. Seleccione uno de los siguientes valores:

    - *Todas las transacciones* - Todas las transacciones deben reducir el pronóstico.
    - *Pedidos* - Solo las órdenes del mismo tipo deben reducir el pronóstico.

    Por ejemplo, la configuración de pedido predeterminada para un artículo indica que debe producirse. Hay una línea de pronóstico de suministro para una cantidad de 50 y hay una orden de compra existente para una cantidad de 20. Si el campo **Reducir el pronóstico por** se establece en *Pedidos*, se creará una orden de producción planificada para una cantidad de 50. Si está configurado para *Todas las transacciones*, la orden de producción planificada se reducirá a una cantidad de 30.

    Esta configuración también se aplica a la reducción de la previsión de la demanda. Para obtener más información, consulte [Planificación maestra con previsiones de demanda](demand-forecast.md).

## <a name="enter-a-supply-forecast-for-a-product"></a>Introducir una previsión de suministro para un producto

Para introducir una previsión de suministro, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione el producto para el que desea introducir una previsión.
1. En el panel de acciones, en la pestaña **Plan**, seleccione **Previsión de suministro**.
1. En la página **Previsión de suministro**, en el panel de acciones, seleccione **Nuevo** para agregar una previsión a la cuadrícula.
1. Ingrese la información en la nueva línea según sea necesario para especificar su pronóstico.

## <a name="plan-for-an-item-with-supply-forecast-lines"></a>Planificar un artículo con líneas de previsión de suministro

Cuando ejecuta un plan maestro que incluye un artículo para el que existe un pronóstico de suministro, el sistema creará una orden de compra para las líneas de suministro que se hayan ingresado. Se respetan los ajustes de pedido predeterminados para el artículo. Si esa configuración de orden predeterminada especifica un valor **Tipo de pedido predeterminado** de *Orden de compra* y no se especifica ninguna cuenta de proveedor en la línea de previsión de suministro, el sistema utilizará el proveedor predeterminado para el artículo.

## <a name="check-whether-a-planned-order-is-a-supply-forecast-order"></a>Comprobar si una orden previsional es una orden de previsión de suministro

Utilice el siguiente procedimiento para saber si se creó un pedido planificado como resultado de un pronóstico de suministro.

1. Vaya a **Planificación maestra \> Planificación maestra \> Pedidos planificados**.
1. Abra el pedido planificado que desee inspeccionar.
1. En la ficha desplegable **General**, consulte el valor del campo **Previsión de suministro**. Si el pedido se creó para cubrir una previsión de suministro, este campo se establecerá en *Sí*.

## <a name="examples-of-master-planning-with-supply-forecasts"></a>Ejemplos de planificación maestra con previsiones de suministro

Esta sección proporciona varios ejemplos que muestran cómo la previsión de suministro afecta la planificación maestra.

### <a name="example-1-supply-forecast-for-an-item"></a>Ejemplo 1: Previsión de suministro para un artículo

Tiene un artículo en el que el tipo de pedido predeterminado es *Orden de compra* y el proveedor predeterminado es *US-002*. Tiene la siguiente línea de pronóstico de suministro.

| Modelo    | Fecha     | Cuenta del proveedor | Grupo de proveedores | Quantity | Unidad | Sitio | Almacén |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                |              | 35       | c/u   | 1    | 11        |

Cuando ejecute la planificación maestra, se creará una orden de compra planificada para *35 c/u* del vendedor *US-002*.

### <a name="example-2-several-supply-forecast-lines-with-and-without-a-vendor"></a>Ejemplo 2: Varias líneas de previsión de suministro, con y sin proveedor

Tiene un artículo en el que el tipo de pedido predeterminado es *Orden de compra* y el proveedor predeterminado es *US-002*. Tiene las siguientes líneas de pronóstico de suministro.

| Modelo    | Fecha     | Cuenta del proveedor | Grupo de proveedores | Quantity | Unidad | Sitio | Almacén |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                |              | 35       | c/u   | 1    | 11        |
| CurrentF | 10/10/22 | US-101         |              | 25       | c/u   | 1    | 11        |

En este caso, el sistema trata la línea que no especifica un proveedor como un pronóstico genérico y asume que la línea que sí especifica un proveedor debe restarse del pronóstico genérico. Por lo tanto, la planificación maestra creará las siguientes órdenes de compra planificadas para el artículo:

- Una orden de compra planificada para una cantidad de *25 c/u* del vendedor *US-101* (Se utilizan el proveedor y la cantidad que se especifican en la línea de previsión).
- Una orden de compra planificada para una cantidad de *10 c/u* del vendedor *US-002* (debido a que no se especificó ningún proveedor en la otra línea de pronóstico, se usa el proveedor predeterminado y la cantidad de esta línea de pronóstico se reduce por la cantidad de la línea de pronóstico específica del proveedor).

### <a name="example-3-plans-that-use-the-transactions---dynamic-period-reduction-method-in-a-single-forecast-period"></a>Ejemplo 3: Planes que usan el método Transacciones - período dinámico de reducción en un solo período de pronóstico

Para planes maestros que utilizan *Transacciones - período dinámico* como método de reducción de pronósticos, la planificación maestra reducirá las cantidades pronosticadas si hay transacciones existentes que coinciden con esas características de suministro.

Por ejemplo, tiene un artículo donde el tipo de pedido predeterminado es *Orden de compra*. Tiene la siguiente línea de pronóstico de suministro.

| Modelo    | Fecha     | Cuenta del proveedor | Grupo de proveedores | Quantity | Unidad | Sitio | Almacén |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | c/u   | 1    | 11        |

Debido a que solo hay una línea de pronóstico de suministro, solo hay un período de pronóstico.

Cuando ejecuta un plan maestro que está configurado para usar *Transacciones: período dinámico* como método de reducción, puede ocurrir uno de los siguientes resultados:

- Si existe una orden de compra para el proveedor *US-101* y una cantidad de *10 c/u*, y el campo **Pronóstico de suministro** se establece en *Sí*, la planificación maestra crea un nuevo pedido planificado para la cantidad restante de *10 c/u*. La línea de previsión se reduce porque el proveedor coincide con la orden de compra existente.
- Si existe una orden de compra para el proveedor *US-102*, sitio *1*, depósito *11*, y una cantidad de *10 c/u*, y el campo **Pronóstico de suministro** se establece en *Sí*, la planificación maestra crea una nueva orden de compra planificada para la cantidad total de *25 c/u*. La línea de previsión no se puede reducir porque tiene un proveedor diferente al del pedido de compra existente.

> [!NOTE]
> Esta situación puede ocurrir para órdenes de compra planificadas, porque un proveedor está asociado con ellas. Sin embargo, para las órdenes de transferencia y las órdenes de producción, las cantidades previstas de suministro siempre se reducirán según las órdenes existentes, ya que no se especifica ningún proveedor para este tipo de órdenes.

### <a name="example-4-plans-that-use-the-transactions---dynamic-period-reduction-method-over-several-forecast-periods"></a>Ejemplo 4: Planes que usan el método Transacciones - período dinámico de reducción en varios períodos de pronóstico

Tiene un artículo donde el tipo de pedido predeterminado es *Orden de compra*. Tiene las siguientes líneas de pronóstico de suministro.

| Modelo    | Fecha     | Cuenta del proveedor | Grupo de proveedores | Quantity | Unidad | Sitio | Almacén |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | c/u   | 1    | 11        |
| CurrentF | 10/15/22 | US-101         |              | 25       | c/u   | 1    | 11        |

En este ejemplo, hay dos líneas de pronóstico, cada una de las cuales tiene una fecha diferente. Por lo tanto, las fechas establecen los límites de los períodos de pronóstico. El primer período es del 10 al 14 de octubre de 2022 (10/10/22–10/14/22). El segundo es a partir del 15 de octubre de 2022 (15/10/22) en adelante.

Hay una orden de compra existente para el proveedor *US-101*, una cantidad de *10 c/u*, y la fecha *10/12/22* (12 de octubre de 2022). Cuando ejecuta un plan maestro que está configurado para usar *Transacciones: período dinámico* como método de reducción, creará los siguientes pedidos:

- Una orden planificada para una cantidad de *15 c/u* y la fecha *10/10/22* (La cantidad se reduce por la orden de compra existente que está fechada durante el mismo período de pronóstico).
- Una orden previsional para una cantidad de *25 c/u* y la fecha *15/10/22* (La cantidad es la cantidad total del pronóstico).

### <a name="example-5-plans-that-use-no-reduction"></a>Ejemplo 5: Planes que no usan reducción

Cuando ejecuta un plan donde el método de reducción de previsión es *Ninguno*, la planificación maestra siempre creará un suministro planificado para todas las líneas de previsión de suministro. Después de que se haya aprobado ese suministro planificado, se reducirán los pedidos planificados futuros. Sin embargo, las órdenes de compra no reducirán las líneas de previsión de suministro.

Por ejemplo, tiene un artículo donde el tipo de pedido predeterminado es *Orden de compra*. Tiene la siguiente línea de pronóstico de suministro.

| Modelo    | Fecha     | Cuenta del proveedor | Grupo de proveedores | Quantity | Unidad | Sitio | Almacén |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | c/u   | 1    | 11        |

Hay una orden de compra existente para el proveedor *US-101*, sitio *1*, almacén *11*, una cantidad de *25 c/u* y la fecha *10/10/22*. 

Cuando ejecuta un plan maestro que está configurado para usar *Ninguna* como método de reducción, creará una orden de compra planificada para el proveedor *US-101*, sitio *1*, depósito *11*, una cantidad de *25 c/u* y la fecha *10/10/22*. En otras palabras, la orden de compra existente no se reducirá porque el método de reducción de previsión es *Ninguna*.

Ahora edite la orden de compra planificada que se creó después de la última ejecución de planificación y cambie la cantidad a *15 c/u*. Luego aprueba el pedido. La próxima vez que ejecuta el plan maestro, creará una orden de compra planificada para el proveedor *US-101*, sitio *1*, depósito *11*, una cantidad de *10 c/u* y la fecha *10/10/22*. Esta vez, la cantidad se reducirá para reflejar la cantidad del pedido aprobado existente de la ejecución de planificación anterior.

## <a name="differences-between-planning-optimization-and-the-built-in-planning-engine"></a>Diferencias entre la Optimización de planificación y el motor de planificación incorporado

Las previsiones de suministro se comportan de forma ligeramente diferente en función del motor de planificación que use (Optimización de planificación o la planificación maestra integrada). Esta sección describe las diferencias.

### <a name="vendor-groups"></a>Grupos de proveedores

Cuando agrega una línea pronosticada, puede especificar un proveedor y un grupo de proveedores. En el motor de planificación integrado, los pedidos planificados que se crean se agrupan por la combinación de los valores de proveedor y grupo de proveedores. En Planning Optimization, los pedidos planificados se agrupan por proveedor.

La siguiente tabla proporciona algunos ejemplos de líneas de previsión de suministro para un artículo.

| Modelo    | Fecha     | Cuenta del proveedor | Grupo de proveedores | Quantity | Unidad | Sitio | Almacén |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                | VendorGroupA | 5        | c/u   | 1    | 11        |
| CurrentF | 10/10/22 |                | VendorGroupA | 6        | c/u   | 1    | 11        |
| CurrentF | 10/10/22 |                |              | 7        | c/u   | 1    | 11        |

El proveedor *VendorA* es el proveedor predeterminado para el grupo de proveedores *VendorGroupA*. También es el proveedor predeterminado para el artículo.

El motor de planificación integrado creará los siguientes pedidos:

- Una orden de compra planificada para el proveedor *VendorA*, grupo de proveedores *VendorGroupA* y una cantidad de *11*
- Una orden de compra planificada para el proveedor *VendorA* y una cantidad de *7*

La Optimización de la planificación creará solo un pedido:

- Una orden de compra planificada para el proveedor *VendorA*, grupo de proveedores *VendorGroupA* y una cantidad de *18*

### <a name="reduction-of-general-forecasts-by-more-specific-forecasts"></a>Reducción de previsiones generales por previsiones más específicas

En el motor de planificación maestro incorporado, el resultado es impredecible si algunos pronósticos tienen un proveedor pero otros no.

En Planning Optimization, las previsiones generales siempre se reducen con previsiones más específicas, como muestra el siguiente ejemplo.

La siguiente tabla proporciona algunos ejemplos de líneas de previsión de suministro para un artículo.

| Fecha       | Quantity | Proveedor   | Grupo de proveedores  |
|------------|----------|----------|---------------|
| 02/11/2022 | 5.00     | Vendor-A | VendorGroup-A |
| 02/11/2022 | 6,00     | Vendor-A | VendorGroup-A |
| 02/11/2022 | 15.00    |          |               |

La previsión general (para 15,00 piezas) se reduce por las previsiones más específicas (para 5,00 + 6,00 = 11,00 piezas). El resto se asigna al proveedor predeterminado. La tabla siguiente muestra los pedidos planificados.

| Fecha       | Quantity | Proveedor   | Grupo de proveedores  |
|------------|----------|----------|---------------|
| 02/11/2022 | 11.00    | Vendor-A | VendorGroup-A |
| 02/11/2022 | 4.00     | Vendor-A | VendorGroup-A |

### <a name="respect-for-default-order-settings-when-planned-orders-are-generated"></a>Respecto a la configuración de pedidos predeterminada cuando se generan pedidos planificados

Cada artículo puede tener una configuración de pedido predeterminada, como una cantidad mínima de pedido de compra. El motor de planificación incorporado ignora esta configuración y, por lo tanto, traduce los pronósticos en pedidos planificados que tienen la misma cantidad. La optimización de la planificación respeta esta configuración cuando los pedidos planificados se generan a partir de las previsiones de suministro. 

### <a name="aggregation-of-planned-orders-as-a-result-of-reduction-by-approved-orders"></a>Agregación de pedidos planificados como resultado de la reducción por pedidos aprobados

El motor de planificación maestro incorporado asume que solo un pedido reducirá el pronóstico de suministro existente. Por tanto, si varios pedidos coinciden con una línea de previsión de suministro, sólo el primer pedido la reducirá. En Planning Optimization, todos los pedidos que coincidan con la línea de previsión de suministro la reducirán.

### <a name="reduction-of-forecasts-by-matching-vendors-only"></a>Reducción de las previsiones solo por coincidencia de proveedores

Cuando el motor de planificación maestro incorporado reduce un pronóstico por pedidos de compra emitidos existentes, no garantiza que el proveedor del pedido de compra coincida con el proveedor del pronóstico. La optimización de la planificación reduce los pronósticos solo por órdenes de compra que tienen un valor coincidente en el campo del proveedor.

Para las órdenes de producción y transferencia, el campo del proveedor siempre se ignora porque no es relevante para esos tipos de órdenes.

### <a name="reduction-of-forecasts-by-transfer-orders"></a>Reducción de previsiones por órdenes de transporte

Si el tipo de pedido predeterminado para un artículo es *Transferir*, las previsiones solo se pueden reducir mediante órdenes de transporte planificadas existentes. Sin embargo, para órdenes de producción y órdenes de compra, solo las órdenes emitidas reducen el pronóstico de suministro.

El motor de planificación incorporado reduce para todos los estados de órdenes de transferencia, mientras que la Optimización de la planificación reduce los pronósticos solo para las órdenes de transferencia que están en el estado *Liberado*.

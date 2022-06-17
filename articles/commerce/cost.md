---
title: Configuración de costes para la gestión de pedidos distribuida (DOM)
description: En este artículo se describe la configuración de costes para la funcionalidad de gestión de pedidos distribuida (DOM) de Dynamics 365 Commerce.
author: josaw1
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9aaff8f627adcd00be174a0b5f7bd398300cfef9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862029"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a>Configuración de costes para la gestión de pedidos distribuida (DOM)

[!include [banner](../includes/banner.md)]

Las organizaciones tienen en cuenta varios componentes de costes para determinar la ubicación óptima desde la que satisfacer un pedido. Algunos de estos componentes de costes son el coste de envío, el coste de manipulación y el coste de empaquetado. Se calcula una combinación de estos costes para determinar la ubicación de cumplimiento.

Cuando la primera iteración de gestión de pedidos distribuida (DOM) de Dynamics 365 Commerce optimizó la asignación de pedidos a las ubicaciones de cumplimiento, solo se tuvo en cuenta en la distancia. Aunque la distancia pueda estar correlacionada con el coste, no es lo mismo que el coste. Por ejemplo, un método de envío durante la noche cuesta más que el envío de tres días o el envío de siete días en la misma distancia.

La característica de configuración de costes permite a los minoristas definir y configurar componentes de costes adicionales que se calcularán y tendrán en cuenta para determinar la ubicación óptima desde la que satisfacer las líneas de pedido.

Cuando los componentes de costes se configuran, el solucionador de DOM usa solo esas definiciones de costes para determinar la ubicación óptima para el cumplimiento del pedido. No tiene en cuenta el componente de la distancia como coste. Sin embargo, si no hay componentes de costes configurados, el solucionador de DOM usa el componente de la distancia como coste para determinar la ubicación óptima para el cumplimiento del pedido.

## <a name="set-up-cost-components"></a>Configurar componentes de costes

Se pueden definir dos tipos de componentes de costes principales en el sistema: **Envío** y **Otros**.

Ambos tipos de componentes de costes admiten varias bases de cálculo, como se muestra en la tabla siguiente.

<table>
<thead>
<tr>
<th>Tipo de componente de costes</th>
<th>Base de cálculo</th>
</tr>
</thead>
<tbody>
<tr>
<td>Envío</td>
<td>
<ul>
<li>Sencillo</li>
<li>Por niveles</li>
</ul>
</td>
</tr>
<tr>
<td>Otros</td>
<td>
<ul>
<li>Pedido de ventas</li>
<li>Línea de ventas</li>
<li>Ubicación</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a>Tipo de componente de costes de envío

En esta sección se explica cómo configurar cada combinación del tipo de componente de costes **Envío** y una base del cálculo para los gastos de envío. También explica cómo el solucionador de DOM usa cada combinación.

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a>Tipo de componente de costes = Base de envío y cálculo = Sencillo

Si se usa una combinación del tipo de componente de costes **Envío** y la base de cálculo **Sencillo**, el coste de envío para un modo de entrega se basa en una distancia o coste fijo.

Debe configurar los siguientes campos para esta combinación:

- **Factor de coste**: especifique un identificador único para el factor de coste.
- **Descripción**: escriba el nombre y la descripción del factor de coste.
- **Fecha inicial** y **Fecha de finalización**: puede usar estos campos para limitar el factor de coste para un intervalo de fechas específico. Si deja estos campos en blanco, el factor de coste es válido por un período indefinido.
- **Activo**: indica si el factor de coste está activo. DOM solo tiene en cuenta los factores de coste activos que están asociados al perfil de cumplimiento.
- **Empresa**: especifica la entidad jurídica para la que está configurado el factor de coste. Todas las líneas de los criterios de cálculo deben ser para la misma entidad jurídica.
- **Modos de entrega**: especifique los modos de entrega para los que está configurado el coste.
- **Tipo de cálculo**: especifique cómo se debe calcular el coste para un modo de entrega concreto. Se admiten dos tipos de cálculo:

    - **Fijo**: se usa un coste fijo para el modo de entrega. Si selecciona este tipo de cálculo, el campo **Coste** define el coste fijo.
    - **Por unidad de distancia**: el coste para el modo de entrega se calcula como el valor de coste que se especifica en el campo **Coste** multiplicado por la distancia entre la dirección de entrega y las ubicaciones.

- **Coste**: especifique el valor del coste que se usa junto con el campo **Tipo de cálculo** para calcular el coste de un modo de entrega.

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a>Tipo de componente de costes = Base de envío y cálculo = Por niveles

Si se usa una combinación del tipo de componente de costes **Envío** y la base de cálculo **Por niveles** , el coste de envío para un modo de entrega se basa en una distancia o coste fijo. Sin embargo, en esta combinación, la distancia se basa en un intervalo por niveles de distancias.

Debe configurar los siguientes campos para esta combinación:

- **Factor de coste**: especifique un identificador único para el factor de coste.
- **Descripción**: escriba el nombre y la descripción del factor de coste.
- **Coste predeterminado**: especifique el coste que se debe usar para un modo de entrega si la distancia entre la dirección de entrega y la ubicación no se encuentra en ninguna de las distancias por niveles para el modo de entrega.
- **Fecha inicial** y **Fecha de finalización**: puede usar estos campos para limitar el factor de coste para un intervalo de fechas específico. Si deja estos campos en blanco, el factor de coste es válido por un período indefinido.
- **Activo**: indica si el factor de coste está activo. DOM solo tiene en cuenta los factores de coste activos que están asociados al perfil de cumplimiento.
- **Empresa**: especifica la entidad jurídica para la que está configurado el factor de coste. Todas las líneas de los criterios de cálculo deben ser para la misma entidad jurídica.
- **Modos de entrega**: especifique los modos de entrega para los que está configurado el coste.
- **Tipo de distancia**: especifique si la definición de distancia por niveles es una distancia aérea o una distancia por carretera.
- **Unidades de distancia**: especifique la unidad en la que se mide la distancia por niveles.
- **Distancia desde**: especifique el intervalo de inicio de la distancia por niveles.
- **Distancia a**: especifique el intervalo de finalización de la distancia por niveles.
- **Tipo de cálculo**: especifique cómo se debe calcular el coste para un modo de entrega concreto y una distancia por niveles. Se admiten dos tipos de cálculo:

    - **Fijo**: se usa un coste fijo para el modo de entrega. Si selecciona este tipo de cálculo, el campo **Coste** define el coste fijo.
    - **Por unidad de distancia**: el coste para el modo de entrega y la distancia por niveles se calcula como el valor de coste que se especifica en el campo **Coste** y la distancia entre la dirección de entrega y las ubicaciones.

- **Coste**: especifique el valor del coste que se usa junto con el campo **Tipo de cálculo** para calcular el coste de un modo de entrega.

> [!NOTE]
> - Al definir distancias por niveles, el sistema valida que no haya distancias que falten o que se superpongan.
> - El tipo de distancia que se usa para un modo de entrega debe ser igual en todas las distancias por niveles.

### <a name="other-cost-component-type"></a>Otro tipo de componente de costes

Esta sección explica cómo configurar cada combinación de tipo de componente de costes **Otros** y otro tipo de coste para gastos que no sean de envío. También explica cómo el solucionador de DOM usa cada combinación.

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a>Tipo de componente de costes = Otros y Otro tipo de coste = Pedido de ventas

Se usa una combinación de tipo de componente de costes **Otro** y el otro tipo de coste **Pedido de ventas** para definir gastos que no sean de envío en el nivel de pedido de ventas.

Debe configurar los siguientes campos para esta combinación:

- **Factor de coste**: especifique un identificador único para el factor de coste.
- **Descripción**: escriba el nombre y la descripción del factor de coste.
- **Fecha inicial** y **Fecha de finalización**: puede usar estos campos para limitar el factor de coste para un intervalo de fechas específico. Si deja estos campos en blanco, el factor de coste es válido por un período indefinido.
- **Activo**: indica si el factor de coste está activo. DOM solo tiene en cuenta los factores de coste activos que están asociados al perfil de cumplimiento.
- **Coste**: especifique el valor de coste de un gasto que no sea de envío en el nivel de pedido de ventas.

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a>Tipo de componente de costes = Otros y Otro tipo de coste = Línea de ventas

Se usa una combinación de tipo de componente de costes **Otro** y el otro tipo de coste **Línea de ventas** para definir gastos que no sean de envío en el nivel de línea de pedido de ventas.

Debe configurar los siguientes campos para esta combinación:

- **Factor de coste**: especifique un identificador único para el factor de coste.
- **Descripción**: escriba el nombre y la descripción del factor de coste.
- **Fecha inicial** y **Fecha de finalización**: puede usar estos campos para limitar el factor de coste para un intervalo de fechas específico. Si deja estos campos en blanco, el factor de coste es válido por un período indefinido.
- **Activo**: indica si el factor de coste está activo. DOM solo tiene en cuenta los factores de coste activos que están asociados al perfil de cumplimiento.
- **Coste**: especifique el valor de coste de un gasto que no sea de envío en el nivel de línea de pedido de ventas.

#### <a name="cost-component-type--other-and-other-cost-type--location"></a>Tipo de componente de costes = Otros y Otro tipo de coste = Ubicación

Se usa una combinación del tipo de componente de costes **Otros** y el otro tipo de coste **Ubicación** para definir los gastos que no son de envío para un grupo de ubicaciones o una ubicación individual.

Debe configurar los siguientes campos para esta combinación:

- **Factor de coste**: especifique un identificador único para el factor de coste.
- **Descripción**: escriba el nombre y la descripción del factor de coste.
- **Fecha inicial** y **Fecha de finalización**: puede usar estos campos para limitar el factor de coste para un intervalo de fechas específico. Si deja estos campos en blanco, el factor de coste es válido por un período indefinido.
- **Activo**: indica si el factor de coste está activo. DOM solo tiene en cuenta los factores de coste activos que están asociados al perfil de cumplimiento.
- **Grupo de cumplimiento**: especifique el grupo de ubicaciones para las que se define el gasto que no es de envío.
- **Ubicación de cumplimiento** especifique la ubicación para la que se define el gasto que no es de envío.

    > [!NOTE]
    > No puede especificar un grupo de cumplimiento y una ubicación de cumplimiento en la misma línea para los criterios de cálculo basados en ubicación.

- **Coste**: especifique el valor de coste de un gasto que no sea de envío en el nivel de grupo de cumplimiento o en el nivel de ubicación de cumplimiento.

> [!IMPORTANT]
> Para que DOM tenga en cuenta estos costes cuando se ejecuta, debe agregar el factor de coste al perfil de cumplimiento pertinente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
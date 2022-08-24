---
title: Crear y actualizar franjas horarias para la recogida del cliente
description: En este artículo se describe cómo crear, configurar y actualizar franjas horarias de recogida para el cliente en Commerce headquarters.
author: anupamar-ms
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.15 update
ms.custom: ''
ms.search.industry: Retail
ms.openlocfilehash: 319b2ac2a652e633bc70c477dab52e2676c17001
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282843"
---
# <a name="create-and-update-time-slots-for-customer-pickup"></a>Crear y actualizar franjas horarias para la recogida del cliente

[!include [banner](../../includes/banner.md)]

En este artículo se describe cómo crear, configurar y actualizar franjas horarias de recogida para el cliente en Commerce headquarters.

La característica de franja horaria ofrece a los minoristas una forma de definir franjas horarias para los artículos para los que está activado el modo de recogida de la entrega del cliente. Las franjas horarias permiten a los minoristas definir los días y las horas en que se pueden recoger los pedidos en una tienda. Los minoristas también pueden definir la cantidad de pedidos que se pueden recoger durante un período determinado. De esta forma, los minoristas pueden limitar el número de pedidos que se pueden recoger en un día y en un momento determinados. El resultado es una experiencia de mejor calidad para sus clientes.

> [!NOTE]
> La característica de franja horaria está disponible en Microsoft Dynamics 365 Commerce, versión 10.0.15 y posteriores.

La siguiente ilustración muestra un ejemplo de selección de franjas horarias durante la finalización de la compra de comercio electrónico.

![Ejemplo de selección de franja horaria durante la finalización de la compra en comercio electrónico.](../dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="time-slot-properties"></a>Propiedades de la franja horaria

Una franja horaria es un intervalo específico en el que un cliente puede elegir recoger un pedido en una tienda o ubicación específica. La función de administración de franjas horarias está disponible solo cuando el modo de entrega de recogida del cliente está configurado en Dynamics 365 Commerce.

Una franja horaria se define mediante las siguientes propiedades:

- **Modo de entrega**: especifique el modo de recogida de la entrega al que se aplica la franja horaria.
- **Mínimo de días** y **Máximo de días**: especifique las fechas más próximas y más alejadas que se pueden seleccionar para la recogida en relación con la fecha en que se realiza el pedido. 

    La propiedad **Mínimo de días** garantiza que hay tiempo suficiente para que el minorista procese el pedido antes de que esté listo para su recogida. La propiedad **Máximo de días** garantiza que el usuario no pueda seleccionar una fecha demasiado lejana en el futuro. Por ejemplo, si el valor mínimo se establece en **1**, y se realiza un pedido el 20 de septiembre, el primer día en que el pedido estará disponible para su recogida es el siguiente día elegible (21 de septiembre). De manera similar, al establecer un valor máximo, puede definir el número máximo de días durante los que se puede recoger un pedido. Cuando se definen los valores mínimos y máximos, los usuarios del sitio pueden ver y seleccionar solo un conjunto específico de días durante su experiencia de pago.

    Puede establecer el valor mínimo en un valor decimal menor que 1. Por ejemplo, si la recogida está disponible cuatro horas después de que se realiza un pedido, establezca el valor mínimo en **0,17** (= 4 ÷ 24, redondeado a dos decimales). Sin embargo, si establece el valor mínimo en un valor decimal superior a 1, siempre se redondea hacia arriba, al número entero más cercano. Por ejemplo, un valor de **1,2** será redondeado a **2**. De forma similar, si establece el valor máximo en un valor decimal, siempre se redondea hacia arriba, al número entero más cercano. 

- **Fecha de inicio** y **Fecha finalización**: especifique las fechas de inicio y finalización de la franja horaria. Cada entrada de intervalo de tiempo tiene una fecha de inicio y una fecha de finalización. Por lo tanto, tiene la flexibilidad de agregar diferentes franjas horarias a lo largo del año (por ejemplo, recogidas durante las vacaciones). Si el inicio y las fechas de una franja horaria se cambian después de realizar un pedido, los cambios no se aplicarán a ese pedido. Cuando defina las fechas de inicio y finalización, debe considerar las fechas de cierre de la tienda (por ejemplo, el día de Navidad) y asegurarse de que no se definan franjas horarias para esos días.
- **Horas activas de recogida**: especifique el período en el que se permite la recogida. Por ejemplo, las horas de recogida pueden ser entre las 14:00 horas y las 15:00 horas todos los días. Esta propiedad permite que los horarios de recogida sean independientes del horario de la tienda. Por lo tanto, el minorista puede configurar horarios de recogida que cumplan con sus requisitos comerciales específicos. Cuando defina las horas activas de recogida, debe considerar las horas de la tienda y asegurarse de que las horas de recogida no estén definidas para las horas en que la tienda está cerrada.

    > [!NOTE]
    > El horario de recogida en tienda debe definirse en la zona horaria de la tienda correspondiente.

- **Intervalo de la franja horaria**: especifique la duración que se puede asignar a cada franja horaria. Por ejemplo, la duración de cada franja horaria puede ser en incrementos de 15 minutos, 30 minutos o una hora. Si el valor del intervalo de tiempo es 0, el intervalo estará disponible entre la hora de inicio y la de finalización.
- **Franjas horarias por intervalo**: especifique la cantidad de clientes o pedidos que se pueden atender para la recogida durante cada franja horaria. Por ejemplo, especifique **1**, **2**, **3**, o cualquier otro número entero.
- **Días activos**: especifique los días de la semana en los que las franjas horarias de recogida están activas. Esta propiedad permite al minorista definir los días en los que desea admitir pedidos de recogida.
- **Canales minoristas**: especifique los canales minoristas. Cada franja horaria se puede asociar con una o más tiendas minoristas. Dependiendo del horario de atención de cada tienda, se pueden crear una o más entradas de franjas horarias y asociarlas con un canal. 

<!-- ![HQ Timeslot overview.](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

Solo se puede configurar una plantilla de intervalo de tiempo por canal. Estos canales incluyen tiendas físicas, centros de llamadas, dispositivos móviles y sitios de comercio electrónico.

## <a name="configure-the-time-slot-feature-in-commerce-headquarters"></a>Configurar la función de franja horaria en la sede central de Commerce

Deben definirse franjas horarias para cada modo de recogida de la entrega en la sede central de Commerce, de modo que los puntos de venta (PDV) y los canales de comercio electrónico puedan referenciarlos.

- Solo se puede asociar una plantilla de franja horaria a cada tienda o canal.
- Cada franja horaria que se crea debe ser única para cada modo de entrega en cada plantilla.
- Una vez configurada la característica de franja horaria, el calendario de franjas horarias estará disponible para las tiendas o grupos de tiendas seleccionados. También estará visible en el PDV, como referencia.

Para configurar la función de franja horaria en la sede central de Commerce, siga estos pasos.

1. Vaya a **Commerce** \> **Configuración del canal** \> **Franja horaria de recogida en tienda**.
1. Seleccione **Nuevo** para crear una plantilla nueva de franjas horarias. Para usar una plantilla existente, seleccione la plantilla en el panel izquierdo.
1. Escriba valores en los campos **Id. de franja horaria** y **Descripción**.
1. En la ficha desplegable **Recogida de pedidos: configuración de horas**, seleccione **Agregar**.
1. En el cuadro de diálogo **Recogida de pedidos: configuración de horas**, defina el rango de fechas, el modo de entrega, las horas activas de entrega, los días activos, el intervalo de franja horaria, las franjas horarias por intervalo y otras configuraciones.

    Si las franjas horarias van a ser estáticas en el futuro previsible, establezca el campo **Fecha final** en **Nunca**.

    > [!NOTE]
    > Puede crear varias plantillas, pero solo una plantilla se puede asociar a un solo canal o tienda.

    ![Cuadro de diálogo Recogida de pedidos: configuración de horas.](../dev-itpro/media/Curbside_timeslot_Settings_Page.PNG)

1. Cuando haya terminado, haga clic en **Aceptar**.
1. Si las franjas horarias de un día varían, cree entradas adicionales en la ficha desplegable **Recogida de pedidos: configuración de horas** para asegurarse de que las fechas y las horas no se superpongan.
1. En la ficha desplegable **Canales minoristas**, seleccione **Agregar** para asociar la plantilla de franja horaria con las tiendas o canales donde se utilizará.
1. En el cuadro de diálogo **Elegir nodos organizativos**, use los botones de flecha para seleccionar (o anular la selección) las tiendas, regiones y organizaciones a las que debe asociarse la plantilla.

    <!-- ![HQ Timeslot overview.](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

1. Cuando haya terminado, haga clic en **Aceptar**.
1. En la página **Programador de distribución** , ejecute los trabajos **1070** y **1135** para sincronizar los datos con los canales.

## <a name="time-slot-selection-for-pos-orders"></a>Selección de franja horaria para pedidos en PDV

En el punto de venta (PDV), cuando se identifica un pedido o una línea de pedido para su recogida, el cajero puede seleccionar la tienda o ubicación de recogida, y una fecha y hora. Si un cliente tiene un pedido de recogida en una tienda diferente, el cajero puede seleccionar las fechas en las que la recogida estará disponible en dicha tienda. La búsqueda de la tienda proporcionará una referencia a las fechas y horarios de la tienda.

La siguiente ilustración muestra un ejemplo de selección de franjas horarias para un pedido en el PDV.

![Un ejemplo de selección de franja horaria para un pedido el PDV.](../dev-itpro/media/Curbside_timeslot_POS.png)

## <a name="time-slot-selection-for-e-commerce-orders"></a>Selección de franja horaria para pedidos de comercio electrónico

Para obtener información sobre cómo hacer que la selección de franjas horarias esté disponible para pedidos de comercio electrónico, consulte [Módulo de información de recogida](../pickup-info-module.md).

> [!NOTE]
> Los usuarios pueden ver o editar las franjas horarias de recogida en la página de pago de un sitio de comercio solo si el módulo de información de recogida se ha agregado a esa página. Si la página de pago no incluye el módulo de información de recogida, los pedidos se realizarán sin permitir que los usuarios especifiquen o vean la información de la franja horaria.

La siguiente ilustración muestra un ejemplo de un pedido de comercio electrónico en el que se ha seleccionado un horario de recogida.

![Ejemplo de pedido de comercio electrónico en el que se ha seleccionado un horario de recogida.](../dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="time-slot-selection-for-call-center-orders"></a>Selección de franja horaria para pedidos de centro de llamadas

En la aplicación del centro de llamadas, los agentes del centro de llamadas pueden seleccionar la tienda o la ubicación de recogida, así como una fecha y un intervalo de tiempo, como se muestra en la siguiente ilustración.

![Ejemplo de pedido de central de llamadas en el que se ha seleccionado un horario de recogida.](../dev-itpro/media/Curbside_timeslot_callcenter.png)

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de información de recogida](../pickup-info-module.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

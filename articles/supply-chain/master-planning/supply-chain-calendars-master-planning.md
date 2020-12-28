---
title: Calendarios y planificación maestra
description: Este tema proporciona una visión general de los calendarios de la cadena de suministro y cómo afectan a la planificación maestra.
author: t-benebo
manager: tfehr
ms.date: 08/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2c32957b0bd234ed14e6333a36a46c6a83ec2e91
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436876"
---
# <a name="calendars-and-master-planning"></a>Calendarios y planificación maestra

[!include [banner](../includes/banner.md)]

Este tema proporciona una visión general de los calendarios de la cadena de suministro y cómo afectan a la planificación maestra.  Los distintos calendarios utilizados en el motor de planificación maestra se explican, incluido cómo afectan a las fechas de envío y recepción en los pedidos planificados. Finalmente, las recomendaciones en relación con la asignación, el uso y la actualización de los calendarios se dan.

## <a name="definition-of-a-calendar"></a>Definición de un calendario

Puede definir un calendario que usará en su organización en la página en **Administración de la organización > configuración > Calendarios > Calendarios**. 

Cada entrada de la fecha de un calendario puede ser **abierta** o **cerrada** o **calendario base**. Se especifica en la columna **Control** en la página **Horarios de trabajo**. Para cada fecha: 
- **Abierto** - Indica que el trabajo ha realizado el día seleccionado. El calendario se actualizará en función de la plantilla de horario de trabajo.
- **Cerrado** - Indica trabajo que no se realiza durante el día. 
- **Calendario base** - Indica que la fecha específica heredará los horarios de trabajo y abiertos/cerrados del calendario base. Por lo tanto, cuando se actualiza el calendario base, el calendario seleccionado hereda las horas de operación de él. 

Por cualquier fecha cerrada, la casilla de verificación **Cerrado para recogida** se asignará automáticamente. Por fechas abiertas, puede seleccionar manualmente la opción **Cerrado para recogida**. Esto indica que se realiza trabajo en la fecha, pero el envío no se efectúa. 

## <a name="calendars-that-affect-master-planning"></a>Calendarios que afectan a la planificación maestra

### <a name="calendar-for-a-coverage-group"></a>Calendario para un grupo de cobertura
Un grupo de cobertura indica un conjunto común de parámetros usados para reabastecimiento de artículos que pertenecen al grupo de cobertura dado. 

Para añadir un calendario para un grupo de cobertura, vaya a **Planificación maestra > Configurar > Cobertura > Grupos de cobertura**. Encuentre el grupo de cobertura al que desea asignar el calendario y luego se selecciónelo en el campo **Calendario**.

El grupo de cobertura se puede asignar en distintas páginas: 
    - En la página **Detalles de producto emitido**, haga clic en un artículo. Para ver el grupo de cobertura para un artículo, vaya **Gestión de información de productos > productos > productos emitidos** y seleccionar el artículo para ir a la página **Detalles de productos emitidos**. Puede ver el grupo de cobertura del artículo en la ficha desplegable **plan**.
    - En la página **Cobertura de artículos**. En la página de detalles de los productos emitidos, haga clic en **Cobertura de artículos** para ir a la página de cobertura de artículos. En la ficha de visión general puede ver distintos parámetros para reabastecimiento en función del sitio, el almacén, y las dimensiones del producto. El grupo de cobertura para cada artículo se heredará del grupo de cobertura en la página **Detalles de producto emitido**. Esto se puede anular con **Usar configuración específica** o con **Anular configuración de grupo** en la pestaña **General**.
    - En la página **parámetros de planificación maestra**. Si un artículo no tiene un grupo de cobertura establecido en las páginas anteriores, la planificación maestra tomará el grupo de cobertura general establecido en parámetros de planificación maestra. Esto se configura en **Planificación maestra > configuración > parámetros de planificación maestra** en el campo **Grupo de cobertura general**. 

### <a name="calendar-for-a-vendor"></a>Calendario para un proveedor
Para indicar los días laborables de un proveedor, puede asignar un calendario de compra al proveedor en la página **Valores predeterminados del pedido de compra** para un proveedor. 

Para establecer un calendario para un proveedor, deberá crear el calendario en **Administración de la organización > calendarios > calendarios**. Cuando se crea el calendario, tiene que asignarlo al proveedor. Vaya **Proveedores > proveedores > todos los proveedores** y seleccione el proveedor al que desea asignar el calendario. A continuación, en la página del proveedor en la ficha desplegable **Valores predeterminados del pedido de compra** asigne el nuevo calendario de compra mediante el menú desplegable. 

El calendario de un proveedor indica los días en los que aceptan la realización del pedido de compra y las fechas en que pueden entregar los pedidos a su empresa. Por lo tanto, las fechas de pedido de los pedidos de compra para el proveedor con un calendario de la compra serán fechas definidas como abiertas en el calendario. Las fechas de entrega para esos pedidos también tendrán lugar en días abiertos y así, impactarán en el plazo del artículo comprado. 

#### <a name="define-the-lead-time-for-a-purchased-item"></a>Definición del plazo para un artículo comprado

Para especificar el plazo de compra (y si solo se consideran días laborables) para un artículo, debe ir a la página de la configuración de pedido predeterminada para el producto, que está en **Gestión de información de productos > productos > productos emitidos** y seleccione **Configuración predeterminada de pedido**. 

> [!Note]
> Los **Días laborables**, en el plazo de compra, indican los días laborables del proveedor. Por ejemplo, un calendario para la entrega que sea solo los martes con un plazo de 10 días y la casilla de los días laborables seleccionada indica que el artículo tardará 10 semanas (10 martes) en entregarse.
Así, en la mayoría de los casos no se recomienda seleccionar días laborables para indicar los plazos del pedido de compra.

#### <a name="define-lead-times-from-the-trade-agreements-page"></a>Definir los plazos a partir de la página de los acuerdos comerciales

La planificación maestra se puede configurar para incluir todos los acuerdos comerciales para los proveedores. Los contratos comerciales son precios fijos o contratos de descuento que se configuran para uno o más clientes o proveedores para la venta o compra de productos individuales o varios productos. Vaya a **Planificación maestra > configuración > parámetros de planificación maestra** y en la pestaña **Pedidos planificados** seleccione **Buscar acuerdos comerciales** para incluir los acuerdos comerciales al realizar la planificación. La planificación maestra puede seleccionar el proveedor con el **Plazo mínimo** o con **El precio unitario más bajo**.

### <a name="calendar-for-a-warehouse"></a>Calendario para un almacén
Puede asignar un calendario a un almacén para indicar las fechas abiertas para recibir y enviar. Si no se ha asignado ningún calendario a un almacén, se presupone que está abierto todos los días. 

> [!Note]
> La asignación de un calendario a un almacén de tránsito no tiene ningún impacto. Los almacenes de tránsito se utilizan para admitir pedidos de transferencia. Las fechas de envío o de recepción aplicables para los pedidos se definen mediante los días abiertos en el almacén “Desde” y el almacén “Hasta” y el modo de calendario de entrega.

#### <a name="closed-for-pickup-policy"></a>Cerrado para política de recogida
Para indicar que un almacén está abierto para recibir pero que la recogida no es posible, puede usar la página **Cerrado para la política de recogida** del calendario de almacén. Esto también se aplica a recogidas de clientes. 

### <a name="transport-calendar"></a>Calendario de transporte 
Para indicar las fechas que están disponibles para pedidos de transferencia de envíos **Desde el almacén**, puede asignar un **Calendario de transporte**. Puede configurar un calendario de transporte por modo de entrega, o por modo de entrega y desde almacén. El calendario de transporte se configura en **Ventas y marketing > configuración > distribución > modos de entrega**. Seleccione un modo de entrega y haga clic en el botón **Calendario de transporte**.

Una línea se puede crear para cada almacén y modo de entrega, donde el calendario se agrega en la columna **Calendario de transporte**. Especificará el calendario de transporte que se aplicará cuando la mercancía se envíe desde el almacén mediante el modo de entrega dado. Para aplicar un calendario de transporte a todos los envíos mediante un modo de entrega dado, se puede crear una línea sin especificar el almacén.  Afectará a todos los envíos que usen el modo de entrega dado, independientemente del almacén. 

Si no se asigna un calendario de transporte, se presupone que todos los días están abiertos para transporte.

### <a name="calendar-for-a-customer"></a>Calendario para un cliente
Para indicar las fechas en que un cliente puede aceptar entregas, puede asignar un calendario de recepción al cliente. Si no se ha asignado ningún calendario a un cliente, se presupone que el cliente puede recibir pedidos todos los días. Esto afectará a la fecha de recepción en las líneas de pedido de ventas. Si selecciona una fecha en las líneas de pedido de ventas que no está “abierta” en el calendario de cliente, el sistema indicará que la fecha de recepción no es válida. 

Tenga en cuenta que solo es posible incluir un calendario por cliente. Si necesita incluir un calendario para cada dirección diferente para un cliente, puede crear un cliente por dirección y asignarle su calendario respectivo. 

La fecha de recepción solicitada en las líneas de pedido de ventas se verá afectada por el calendario de cliente y por el método de control de fecha de entrega. Puede leer más sobre cómo se calcula la fecha de entrega más temprana en [Compromisos de pedidos.](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/delivery-dates-available-promise-calculations).

### <a name="shipping-calendar-for-a-legal-entity"></a>Calendario de envíos para una entidad jurídica
Para indicar las fechas en las que una entidad jurídica puede enviar mercancías, puede configurar un calendario de envío en **Administración de la organización > organizaciones > entidades jurídicas**. Seleccione la entidad jurídica y agregue el calendario en la pestaña **Comercio exterior y logística** en el campo **Calendario de envío**. El calendario de envío hará de origen de los valores predeterminados para todos los calendarios de almacén en la entidad jurídica. 

## <a name="how-calendars-affect-dates-in-planning"></a>Cómo los calendarios afectan a las fechas en la planificación

### <a name="order-date-of-a-planned-purchase-order"></a>Fecha de pedido de un pedido de compra planificado 
La fecha del pedido en un pedido de compra planificado indica la fecha en que se realiza el pedido. Será una fecha ambas abierto tanto en el calendario del proveedor como en el calendario del grupo de cobertura. A veces, los proveedores necesitan algunos días de margen entre el momento en que reciben el pedido de compra y cuando pueden enviar las mercancías. Estas fechas se indican en los días de margen del proveedor. No obstante, si el artículo adquirido se asigna a un grupo de cobertura con días de margen, estos días de margen anulan los días de margen del proveedor.

### <a name="delivery-date-of-a-planned-purchase-order"></a>Fecha de entrega de un pedido de compra planificado
La fecha de recepción de una compra indica la fecha en que recibirá las mercancías. Será una fecha abierto en el calendario. El calendario que se tendrá en cuenta para indicar qué días se pueden recibir los pedidos de compra son los siguientes, en orden de mayor a menor prioridad: 
1. Calendario del proveedor
1. Calendario de grupo de cobertura
1. Calendario de almacén para el almacén de recepción

Tenga en cuenta que el calendario del grupo de cobertura se puede establecer en distintas páginas y tendrá prioridad en el siguiente orden:
1. Grupo de cobertura de artículos en la página **Cobertura de artículos**
1. Grupo de cobertura de artículos en la página **Detalles de productos emitidos**
1. Grupo predeterminado de cobertura de artículos en **Parámetros de planificación maestra**

### <a name="shipping-date-of-a-planned-transfer-order"></a>Fecha de envío de un pedido de transferencia planificado
Al crear un pedido de transferencia entre dos almacenes, la fecha de envío y la fecha de recepción se incluyen en la cabecera del pedido de transferencia, junto con el almacén “Desde” y el almacén "Hasta". La diferencia entre estas dos fechas es el tiempo previsto del transporte (en días) entre almacenes.

La fecha de envío de un pedido de transferencia planificado indica la fecha en que se envía la mercancía desde el almacén “Desde”. Los calendarios utilizados para especificar la fecha de envío disponible se enumeran por prioridad: 
1. Calendario de almacén del almacén "Desde"
1. El calendario del grupo de cobertura (consulte pedido de reserva para este calendario arriba). Si hay un calendario de almacén establecido, la fecha de envío será una fecha abierto en el calendario. Si no hay un calendario de almacén establecido, tomará el calendario del grupo de cobertura. 

### <a name="receipt-date-of-a-planned-transfer-order"></a>Fecha de recepción de un pedido de transferencia planificado
La fecha de recepción de un pedido de transferencia planificado indica la fecha en que se recibe la mercancía en el almacén “Hasta”.

Los calendarios utilizados para especificar la fecha de recepción se enumeran por prioridad: 
1. Calendario de grupo de cobertura 
1. El calendario de almacén del almacén “A”. Si hay un calendario de cobertura establecido, la fecha de recepción será una fecha abierta en el calendario. Si no hay un calendario de grupo de cobertura establecido, tomará el calendario del almacén. 

Al buscar las fechas de envío y recepción para la transferencia planificada, los márgenes liquidados por el usuario para enviar y recibir también se considerarán. 

## <a name="using-calendars-in-master-planning"></a>Usar calendarios en la planificación maestra

### <a name="assignment-of-scm-calendars"></a>Asignación de calendarios SCM
Es importante establecer los calendarios para identificar los días laborables de la empresa. La mejor implementación es establecer un calendario para cada artículo con distintos días laborables. Es decir todos los calendarios externos (cliente, proveedor) y todos los internos (almacén, grupo de cobertura y modo de entrega) relacionados con la empresa.

### <a name="recommendation-on-warehouse-calendars"></a>Recomendación sobre los calendarios de almacén
Se recomienda utilizar un calendario por almacén para incluir los cambios específicos que solo afectan al almacén. Por ejemplo, dos o más almacenes podrían tener los mismos días laborables pero una directiva de recogida diferente. En ese caso, un calendario para cada uno de los almacenes con la directiva respectiva de recogida es la mejor implementación para que el sistema incluya las mejores fechas para la compra, transferencia, y pedidos de producción planificados. Si no se establece ningún calendario de almacén, el calendario de la entidad jurídica se puede usar como origen de los valores predeterminados del calendario de almacén. 

### <a name="recommendation-of-coverage-group-calendars"></a>Recomendación de calendarios del grupo de cobertura
En relación con el calendario del grupo de cobertura, es importante tener en cuenta el que tenga un comportamiento de anulación con relación a las fechas de recepción en la planificación maestra. Por lo tanto, se recomienda usarlos con precaución. En especial, resulta útil en el caso en que deba efectuarse un reabastecimiento en días específicos de la semana. 

### <a name="updating-scm-related-calendars"></a>Actualizar calendarios relacionados con SCM
Aunque es importante que todos los calendarios relevantes se asignen en su lugar respectivo (cliente, proveedor, almacén, modo de entrega, o grupo de cobertura), actualizarlos es importante para que reflejen los cambios. El sistema definirá la producción, la transferencia, la compra, y las fechas de pedido de ventas en función de la combinación de los calendarios asignados. Es una práctica recomendada aclarar quién es responsable de asignar y actualizar los calendarios en sus áreas correspondientes. En caso de un desglose o cualquier otro cambio inesperado en días laborables, es fundamental actualizar los calendarios de acuerdo con él. Todas las tareas que dependen de los calendarios, tales como la planificación maestra y la programación de producción, deben volver a ejecutarse cuando los calendarios se actualizan. 

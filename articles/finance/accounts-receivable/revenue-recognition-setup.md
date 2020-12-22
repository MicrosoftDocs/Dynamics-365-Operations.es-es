---
title: Configuración de reconocimiento de ingresos
description: En este tema se describen las opciones de configuración para el reconocimiento de ingresos y sus implicaciones.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 73acfc92777b8fe07b89bea782e13213d38000cd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459865"
---
# <a name="revenue-recognition-setup"></a>Configuración de reconocimiento de ingresos
[!include [banner](../includes/banner.md)]

Se ha agregado un nuevo módulo **Reconocimiento de ingresos** que incluye elementos de menú para toda la configuración necesaria. En este tema se describen las opciones de configuración y sus implicaciones.

> [!NOTE]
> La característica de reconocimiento de ingresos no se puede activar a través de la administración de características. Actualmente hay que usar las claves de configuración para activarla.

El módulo **Reconocimiento de ingresos** contiene las opciones de configuración siguientes:

- Diarios de reconocimiento de ingresos
- Parámetros para el reconocimiento de ingresos
- Programaciones de ingresos 
- Configuración del inventario

    - Grupos de artículos y productos emitidos
    - Definición de programación de ingresos
    - Definición de precio de ingresos

        - Perfiles de contabilización
        - Agrupaciones de trabajos

    - Componentes de agrupación de trabajos
    - Artículo de la agrupación de trabajos

- Configuración del proyecto

## <a name="revenue-recognition-journals"></a>Diarios de reconocimiento de ingresos

Se ha introducido un nuevo tipo de diario para el reconocimiento de ingresos. El diario es obligatorio y se usa en dos casos.

El primer caso se produce después de que se han cumplido todas las obligaciones contractuales, cuando los ingresos diferidos se reconocen mediante la creación de un diario de reconocimiento de ingresos que se basa en los detalles de la programación de ingresos. El diario contiene una entrada contable que mueve el saldo de la cuenta contable de ingresos diferidos a la cuenta contable de ingresos.

El segundo caso se produce cuando se crea un diario tras producirse la reasignación. La reasignación se produce cuando se agrega una línea de pedido de ventas a un pedido de ventas previamente facturado, o cuando se crea un pedido de ventas nuevo que incluye una línea que forma parte del contrato original. Si una factura se registra antes de que se agregue la nueva línea de pedido de ventas, se debe crear una entrada contable correctiva para la factura de cliente registrada.

El diario se configura en la página **Nombres de diarios** (**Reconocimiento de ingresos \> Configuración \> Nombres de diarios**). El tipo de diario se debe establecer en **Reconocimiento de ingresos**. El diario de reconocimiento de ingresos permite seleccionar la capa de registro en la que se va a registrar.

## <a name="parameters-for-revenue-recognition"></a>Parámetros para el reconocimiento de ingresos

Los parámetros de reconocimiento de ingresos se configuran en la pestaña **Reconocimiento de ingresos** de la página **Parámetros de Contabilidad general** (**Reconocimiento de ingresos \> Configuración \> Parámetros de Contabilidad general**). Los siguientes parámetros están disponibles:

- **Nombre del diario de reconocimiento de ingresos**: seleccione el diario que se ha creado para el reconocimiento de ingresos. El diario es obligatorio cuando se reconocen ingresos de la programación de ingresos o cuando se realiza una reasignación para un pedido de ventas que ya se ha facturado.
- **Habilitar método de asignación de descuento**: establezca esta opción en **Sí** para determinar el precio de ingresos mediante la asignación del valor de mercado justo que se define en el precio de ingresos de cada producto emitido. Esta asignación incluye la asignación de cualquier descuento de línea en los artículos. Si esta opción se establece en **No**, el sistema selecciona el precio medio que se define en el precio de ingresos de cada producto emitido. Si esta opción se establece en **No**, pero no se ha configurado ningún precio medio para los productos emitidos, la asignación del precio de ingresos no se produce.
- **Incluir descuentos de encabezado**: establezca esta opción en **Sí** para determinar el precio de ingresos mediante la asignación de descuentos de encabezado en los productos. Si esta opción se establece en **No**, el descuento de encabezado no se incluye en la asignación del precio de ingresos.
- **Deshabilitar condiciones del contrato**: establezca esta opción en **Sí** si los productos que tienen un tipo de ingresos de **Soporte postcontrato** se pueden emitir aunque no se hayan definido fechas iniciales y finales para ellos. Normalmente, las fechas iniciales y finales del contrato son obligatorias para artículos del tipo de ingresos **Soporte postcontrato**. Cuando se definen las fechas iniciales y finales del contrato, los detalles de la programación de ingresos en el registro se calculan mediante el número de repeticiones y la fecha de factura.
- **Registrar correcciones de factura en clientes al reasignar**: al realizar la reasignación para facturas que ya se han registrado, la entrada contable para la factura registrada se debe corregir. Utilice esta opción para especificar cómo se realiza la corrección.

    - Establezca esta opción en **No** para limitar el registro de la transacción correctiva en la contabilidad general. Cuando esta opción se establece en **No**, no se crea ningún documento adicional en los clientes para la corrección de la contabilidad interna. Cuando se abona la factura, el proceso de liquidación utiliza la antigua entrada contable para registrar los descuentos por pronto pago o los beneficios o pérdidas realizados.
    - Establezca esta opción en **Sí** para crear automáticamente un documento de inversión y una nueva factura para la transacción correctiva en los clientes. Puesto que esta corrección es una corrección de la contabilidad interna, los nuevos documentos no se envían o comunican al cliente. El documento de inversión se liquida en la factura original y el cliente abona la nueva factura corregida. Tenga en cuenta que los tres documentos se muestran en informes, como el extracto del cliente.

[![Información de configuración](./media/revenue-recognition-setup-info.png)](./media/revenue-recognition-setup-info.png)

## <a name="revenue-schedules"></a>Programaciones de ingresos

Se debe crear una programación de ingresos para cada repetición para la que se pueden diferir los ingresos. Por ejemplo, si su organización ofrece soporte en períodos de seis, doce, dieciocho y veinticuatro meses, debe crear una programación de ingresos para cada período. La configuración de la programación de ingresos determina cómo se asigna el precio de ingresos a través del número de períodos que seleccione. También determina las fechas predeterminadas que se especifican para la programación de ingresos que se crea al registrar la factura.

Si reconoce ingresos por hito, se recomienda crear una programación de reconocimiento de ingresos para el número de hitos, independientemente de las fechas de reconocimiento. Después de crear las programaciones, podrá editarlas para que reflejen las fechas de hito previstas. Estos registros se pueden colocar en espera hasta que reciba notificación de que se ha cumplido el hito y de que los ingresos se pueden reconocer.

Las programaciones de ingresos se crean en la página **Programaciones de ingresos** (**Reconocimiento de ingresos \> Configuración \> Programaciones de ingresos**).

[![Programaciones de ingresos](./media/revenue-recognition-revenue-schedules.png)](./media/revenue-recognition-revenue-schedules.png)

Especifique valores descriptivos en los campos **Programación de ingresos** y **Descripción**. Los parámetros adicionales siguientes se usan para crear la programación de ingresos cuando se registra la factura.

- **Repeticiones**: especifique el número de meses o repeticiones del aplazamiento de ingresos.
- **Retención automática**: marque esta casilla de verificación si todas las líneas de la programación de ingresos se deben colocar automáticamente en espera cuando se registre la factura. La retención se debe retirar manualmente de cada línea de la programación antes de que se puedan reconocer los ingresos diferidos de la línea.
- **Condiciones del contrato automáticas**: marque esta casilla si las fechas iniciales y finales del contrato se deben establecer automáticamente. Estas fechas se establecen automáticamente solo para los productos emitidos del tipo de ingresos **Soporte postcontrato**. La fecha inicial del contrato se establece automáticamente en la fecha de envío solicitada de la línea de pedido de ventas y la fecha final del contrato se establece automáticamente en la fecha inicial más el número de meses o repeticiones que se define en la configuración de la programación de ingresos. Por ejemplo, el producto en la línea de pedido de ventas es para una garantía de un año. La programación de ingresos predeterminada es **12M** (12 meses) y se marca la casilla de verificación **Condiciones del contrato automáticas** para esta programación de ingresos. Si la línea de pedido de ventas tiene una fecha de envío solicitada del 16 de diciembre de 2019, la fecha inicial predeterminada del contrato es el 16 de diciembre de 2019 y la fecha final predeterminada del contrato es el 15 de diciembre de 2020.
- **Base de reconocimiento**: la base de reconocimiento determina cómo se asigna el precio de ingresos en las repeticiones.

    - **Mensualmente por fechas**: el importe se asigna en función de los días reales de cada mes.
    - **Mensual**: el importe se asigna a partes iguales entre el número de meses que se define en las repeticiones.
    - **Repeticiones**: el importe se asigna a partes iguales entre las repeticiones, pero puede incluir un período adicional si se selecciona **Fecha inicial real** como convención de reconocimiento.

- **Convención de reconocimiento**: la convención de reconocimiento determina las fechas predeterminadas que se establecen en la programación de ingresos para la factura.

    - **Fecha inicial real**: la programación se crea mediante la fecha inicial del contrato (para los elementos de soporte postcontrato \[PCS\]) o la fecha de factura (para los artículos esenciales y no esenciales).
    - **Primero de mes**: la fecha de la primera línea de la programación es la fecha inicial del contrato (o fecha de factura). Sin embargo, todas las líneas siguientes de la programación se crean para el primer día del mes.
    - **División de medio mes**: la fecha de la primera línea de la programación depende de la fecha de factura. Si la factura se registra en los primeros quince días del mes, la programación de ingresos se crea mediante el uso del primer día del mes. Si la factura se registra en los últimos quince días del mes, la programación de ingresos se crea mediante el uso del primer día del mes siguiente.
    - **Primer día del mes siguiente**: la fecha en la programación es el primer día del mes siguiente.

Seleccione el botón **Detalles de la programación de ingresos** para ver los períodos generales y los porcentajes que se reconocen en cada período. De forma predeterminada, el valor de **Porcentaje de reconocimiento** se divide equitativamente entre el número de períodos. Si la base de reconocimiento se establece en **Mensual** o **Repeticiones**, el porcentaje de reconocimiento se puede modificar. Al cambiar el porcentaje de reconocimiento, un mensaje de advertencia le notifica que el total no es igual al 100 por cien. Si recibe el mensaje, puede continuar editando las líneas. Sin embargo, el porcentaje total debe ser igual a 100 antes de cerrar la página.

[![Detalles de programación de ingresos](./media/revenue-recognition-revenue-schedule-details.png)](./media/revenue-recognition-revenue-schedule-details.png)

## <a name="inventory-setup"></a>Configuración del inventario

Puede reconocer ingresos para productos emitidos en pedidos de ventas, pero no con categorías de ventas en los pedidos de ventas o con facturas de servicios, si no hay artículos incluidos en el documento. Las selecciones que realice al configurar productos emitidos determina cómo se reconocen los ingresos del artículo. Por ejemplo, las selecciones determinan si el precio de ingresos está asignado y si los ingresos se difieren mediante el uso de una programación de ingresos.

La configuración puede comenzar en el ficha desplegable **Reconocimiento de ingresos** de la página **Grupo de artículos** (**Reconocimiento de ingresos \> Configuración \> Configuración de inventario y producto \> Grupo de artículos**). Esta página incluye varios campos de configuración. Estos campos se utilizan para definir valores predeterminados solo para los nuevos productos emitidos que se crean en el sistema. A medida que se crean nuevos productos, los valores que se establecen aquí se especifican de forma predeterminada para el grupo de artículos. Puede anular los valores predeterminados para los productos emitidos en la página **Productos emitidos** (**Reconocimiento de ingresos \> Configuración \> Configuración de inventario y producto \> Productos emitidos**). Los valores predeterminados que se definen para los productos emitidos se transfieren a continuación al pedido de ventas.

## <a name="item-groups-and-released-products"></a>Grupos de artículos y productos emitidos

### <a name="define-the-revenue-schedule"></a>Definir la programación de ingresos

Los ingresos en la línea de pedido de ventas se difieren si se define una programación de ingresos para el producto emitido y esta se utiliza de forma predeterminada en la línea de pedido de ventas. Si se debe usar la configuración de forma predeterminada para el producto, puede definir la programación de ingresos en la ficha desplegable **Reconocimiento de ingresos** de la página **Grupo de artículos** (**Reconocimiento de ingresos \> Configuración \> Configuración de inventario y producto \> Grupo de artículos**). También puede definir la configuración del producto emitido en la ficha desplegable **Reconocimiento de ingresos** de la página **Productos emitidos** (**Reconocimiento de ingresos \> Configuración \> Configuración de inventario \> Productos emitidos**).

En el campo **Programación de ingresos**, seleccione la programación de ingresos que represente el período durante el que se deben diferir los ingresos. La programación de ingresos se especifica automáticamente en la línea de pedido de ventas y los detalles de la programación se crean cuando se registra la factura del pedido de ventas.

### <a name="define-the-revenue-price"></a>Definir el precio de ingresos

Los grupos de artículos y los productos emitidos se pueden configurar mediante el método de precio medio o el método de asignación de descuento. Ambos métodos requieren varias configuraciones en la página **Productos emitidos**:

- **Está activa la asignación de ingresos**: establezca esta opción en **Sí** para incluir el producto emitido en el cálculo de asignación de ingresos. Si esta opción se establece en **No**, el producto emitido utiliza el método de precio medio si se ha definido el precio medio. Si el precio medio no se ha definido, se usa el precio unitario en la línea de pedido de ventas para registrar ingresos o ingresos diferidos.
- **Tipo de ingresos**: seleccione el tipo de ingresos que define el producto emitido:

    - **Esencial**: el artículo es un origen principal de ingresos de una organización. Este valor es la configuración predeterminada.
    - **No esencial**: el artículo no es un origen principal de ingresos de una organización. Cuando se usa la configuración de precio medio, el precio se "disocia" del precio medio y, a continuación, se asigna. Por ejemplo, un artículo esencial tiene un precio fijo que se debe reconocer para ingresos. Si existe un descuento, el descuento se puede disociar de los ingresos del artículo esencial, pero **solo** hasta el importe del precio fijo. El resto del descuento se quita de los ingresos para artículos no esenciales. De manera alternativa, el descuento podría no disociarse de los ingresos de artículos esenciales.
    - **Soporte postcontrato**: el artículo admite otros elementos que se incluyen en la venta al cliente. El precio de ingresos se distribuye entre los productos esenciales y no esenciales que se incluyen en la venta. En función de la configuración, los artículos PCS puede que no requieran que se definan fechas iniciales y finales del contrato en la línea de pedido de ventas.

- **Excluir de disociación**: establezca esta opción en **Sí** para indicar que el precio medio del artículo no se puede ajustar por debajo del porcentaje mínimo definido o por encima del porcentaje máximo. Cualquier precio de ingresos se derivará del precio de ingresos de otro producto emitido que se incluya en el pedido de ventas. Si esta opción se establece en **No**, el precio medio del artículo se puede ajustar o disociar. Tenga en cuenta que si vende más de un artículo configurado como precio medio, se debe configurar al menos un producto emitido con la opción **Excluir de disociación** establecida en **No**. De esa manera, hay al menos un artículo al que se pueden asignar las diferencias en el precio de ingresos.
- **Precio medio**: establezca esta opción en **Sí** para indicar que el precio de ingresos del artículo se debe ajustar de forma que sea igual que el precio medio si está por debajo de la tolerancia mínima que especifica o por encima de la tolerancia máxima y que el importe de disociación debe estar asignado a líneas que tengan productos en los que la opción **Excluir de disociación** esté establecida en **No**.

    - **Tolerancia máxima**: especifique el porcentaje que se permite por encima del precio medio.
    - **Tolerancia mínima**: especifique el porcentaje que se permite por debajo del precio medio.

Una vez que haya terminado de configurar los parámetros para el producto emitido, debe definir manualmente el precio de ingresos al especificar el precio de valor justo o el precio medio (si utiliza el método de precio medio) en la página **Precios de ingresos** (vaya a **Reconocimiento de ingresos \> Configuración \> Configuración de inventario \> Productos emitidos** y, a continuación, en el panel de acciones, en la pestaña **Venta**, en el grupo **Reconocimiento de ingresos**, seleccione **Precios de ingresos**).

[![Precios de ingresos](./media/revenue-recognition-revenue-prices.png)](./media/revenue-recognition-revenue-prices.png)

El precio de ingresos que se define manualmente en esta página se usa para determinar la asignación de precios de ingresos en cada pedido de ventas, en función de los criterios definidos. Cada criterio se asocia a la línea de pedido de ventas para determinar el precio de ingresos que se debe usar en el proceso de asignación.

- **Código de artículo** y **Relación de artículos**: un precio de ingresos se puede definir para un producto individual o para un grupo de productos. Si selecciona **Tabla** en el campo **Código de artículo**, elija el producto emitido en el campo **Relación de artículos**. Si selecciona **Grupo** en el campo **Código de artículo**, elija el grupo de artículos en el campo **Relación de artículos**.
- **Código de cuenta** y **Número de grupo/cuenta**: se puede definir un precio de ingresos para todos los clientes, un cliente individual o un grupo de clientes. Si selecciona **Todos** en el campo **Código de cuenta**, el precio se usa para todos los clientes. Si selecciona **Tabla** en el campo **Código de cuenta**, elija el cliente en el campo **Número de grupo/cuenta**. Si selecciona **Grupo** en el campo **Código de cuenta**, elija el grupo de clientes en el campo **Número de grupo/cuenta**.
- **Divisa**: debe especificar un precio de ingresos independiente para cada divisa que especifique en un pedido de ventas. Por ejemplo, si vende actualmente en dólares estadounidenses, dólares canadienses y euros, debe definir un precio de ingresos en las tres divisas. El precio de ingresos no se traduce de una divisa, como la divisa de contabilidad, a ninguna otra divisa de transacción que esté usando.
- **Importe o porcentaje de lista**: especifique si el precio de ingresos está configurado como un importe o como un porcentaje del precio de lista. Si selecciona **Porcentaje del precio de lista**, los usuarios pueden especificar el precio medio como porcentaje del precio de lista en lugar de un importe. El valor de **Porcentaje del precio de lista** solo se usa para productos emitidos que se han configurado como artículos PCS.
- **Precio de asignación de ingresos**: en función del valor seleccionado en el campo **Importe o porcentaje de lista**, especifique un importe o un porcentaje para representar el precio de ingresos que se usa para asignar los ingresos entre los elementos del pedido de ventas.
- **Fecha inicial** y **Fecha final**: especifique el intervalo de fechas en el que estará activo el precio de ingresos. Estos campos son opcionales.

Si la opción **Habilitar método de asignación de descuento** de la página **Parámetros de Contabilidad general** está establecida en **Sí** y el campo **Tipo de ingresos** para su producto emitido se establece en **Soporte postcontrato**, también deberá especificar los artículos que admitirá el producto liberado. Esta configuración se realiza en la página **Base de instalación** (vaya a **Reconocimiento de ingresos \> Configuración \> Configuración de inventario \> Productos emitidos** y, a continuación, en el panel de acciones, en la pestaña **Venta**, en el grupo **Reconocimiento de ingresos**, seleccione **Base de instalación**).

En la página **Base de instalación**, agregue un registro para cada grupo de artículos que sea compatible con el artículo. Cuando se produzca la asignación de ingresos, el precio de ingresos se distribuirá a través de las partes esenciales y no esenciales del artículo PCS.

### <a name="posting-profiles"></a>Perfiles de contabilización

Tres tipos de registro adicionales admiten la capacidad de diferir ingresos. Estos tipos de registro se configuran en la pestaña **Pedido de ventas** de la página **Registro** (**Reconocimiento de ingresos \> Configuración \> Configuración de inventario y producto \> Registro**).

- **Ingresos diferidos**: especifique la cuenta principal para el precio de ingresos que se registra en los ingresos diferidos (en lugar de en los ingresos). El precio de ingresos se difiere si la línea de pedido de ventas tiene una programación de ingresos.
- **Coste diferido de bienes vendidos**: especifique la cuenta principal para el importe de coste de bienes vendidos que se registra en el coste diferido de bienes vendidos si los ingresos también se han diferido.
- **Compensación de ingresos de factura parcial**: especifique la cuenta principal para la cuenta de compensación que se usa cuando el pedido de ventas se factura solo parcialmente o cuando se produce la reasignación. El saldo de esta cuenta vuelve a 0 (cero) si los pedidos de ventas se han facturado completamente.

### <a name="bundles"></a>Agrupaciones de trabajos

Los artículos de agrupación de trabajos son productos emitidos únicos que se han configurado para que incluyan componentes. Esta configuración se realiza mediante la funcionalidad de lista de materiales (L. MAT). Si se especifica un artículo de agrupación de trabajos en un pedido de ventas, se usan los componentes individuales para determinar los precios de ingresos y las programaciones de ingresos. Sin embargo, los documentos impresos para el cliente, como el pedido de ventas y la factura, reflejan el artículo de agrupación de trabajos.

#### <a name="bundle-components"></a>Componentes de agrupación de trabajos

Los componentes que se incluyen en la agrupación de trabajos se deben configurar en la página **Productos emitidos** (**Reconocimiento de ingresos \> Configuración \> Configuración de inventario y producto \> Productos emitidos**). Estos componentes son productos emitidos y se deben configurar de la misma manera que los productos incluidos en una L. MAT. Por ejemplo, un producto emitido puede ser un artículo del tipo **Artículo** o del tipo **Servicio**, pero se debe asignar a un grupo de modelos de artículo en el que la opción **Producto mantenido en existencias** esté establecida en **Sí**. Para obtener más información, consulte la documentación de configuración para artículos de L. MAT.

Los componentes también deben estar configurados para el reconocimiento de ingresos, como si se tratara de productos que se pueden vender de manera individual en un pedido de ventas. Por ejemplo, asegúrese de que se haya definido el precio de ingresos correcto para cada componente y de que el precio base esté configurado para artículos PCS.

#### <a name="bundle-items"></a>Artículos de agrupación de trabajos

Cuando configure un artículo de agrupación de trabajos, debe configurar dos campos en la página **Productos emitidos** (**Reconocimiento de ingresos \> Configuración \> Configuración de inventario y producto \> Productos emitidos**).

- En la ficha desplegable **Ingeniero**, en el campo **Tipo de producción**, el artículo se debe configurar como un artículo de L. MAT.
- En la ficha desplegable **General**, en el campo **Agrupación de trabajos**, el artículo se debe marcar como artículo de agrupación de trabajos.

Los componentes se deben asignar a continuación al artículo principal de agrupación de trabajos/L. MAT en la página **Versiones de L. MAT** (vaya a **Reconocimiento de ingresos \> Configuración \> Configuración de inventario y producto \> Productos emitidos** y, a continuación, en el panel de acciones, en la pestaña **Ingeniero**, en el grupo **L. MAT**, seleccione **Versiones de L. MAT**). Para obtener más información, consulte la documentación de configuración de L. MAT.

[![Productos emitidos, programaciones de L. MAT](./media/revenue-recognition-bom-scheduleds.jpg)](./media/revenue-recognition-bom-scheduleds.jpg)

Si el artículo principal de agrupación de trabajos y los componentes de agrupación de trabajos se establecen para la asignación, el precio de ingresos de la agrupación de trabajos se distribuirá entre los componentes, en función de sus porcentajes de contribución de ingresos.

## <a name="project-setup"></a>Configuración del proyecto

El reconocimiento de ingresos también se puede usar para pedidos de ventas que se crean mediante un proyecto de tiempo y materiales. Para los pedidos de ventas que se originan a partir de proyectos, solo tiene que definir las cuentas principales en perfiles de contabilización de proyectos que se utilizan para registrar facturas de proyecto. Las cuentas principales se definen en la página **Configuración de registro** (**Reconocimiento de ingresos \> Configuración \> Configuración del proyecto \> Configuración de registro**).

- **Ingresos de factura diferidos** (bajo **Cuentas de ingresos**): especifique la cuenta principal para el precio de ingresos que se registra en los ingresos diferidos (en lugar de en los ingresos). El precio de ingresos se difiere si la línea de pedido de ventas tiene una programación de ingresos.
- **Coste diferido** (bajo **Cuentas de costes**): especifique la cuenta principal para el importe de coste de bienes vendidos que se registra en el coste diferido de bienes vendidos si los ingresos también se han diferido.

---
title: Cargos automáticos avanzados omnicanal
description: Este artículo describe las capacidades para gestionar otros cargos de pedidos de los pedidos del canal de Commerce mediante el uso de varias funciones avanzadas de cargos automáticos.
author: hhainesms
ms.date: 03/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.search.form: ''
ms.openlocfilehash: d44bc4ef61341c394b627ddbe10768d2ddf98de0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292715"
---
# <a name="omni-channel-advanced-auto-charges"></a>Cargos automáticos avanzados omnicanal

[!include [banner](includes/banner.md)]

Este artículo proporciona información acerca de la configuración y la implementación de características avanzadas de cargos automáticos disponibles en Dynamics 365 for Retail versión 10.0.

Si se habilitan las funciones avanzadas de cargos automáticos, los pedidos creados en cualquier canal de Commerce admitido (punto de venta (PDV), centro de asistencia telefónica y en línea), pueden aprovechar las configuraciones de [cargos automáticos](/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) definidas en la aplicación de ERP para el encabezado y los cargos relacionados en el nivel de línea.

En las versiones anteriores a Retail versión 10.0 , las configuraciones de [cargo automático](/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) solo están accesibles para los pedidos creados en comercio electrónico y canales de centro de llamadas. En las versiones 10.0 y posteriores, los perdidos creados en PDV pueden usar las configuraciones de cargos automáticos. De esta manera, los cargos adicionales se puede agregar sistemáticamente a las transacciones de ventas.

Al usar versiones previas a la versión 10.0, se debe pedir a un usuario PDV que especifique manualmente una cuota de envío durante la creación de una transacción PDV con “Enviar todo” o “Enviar selección". Aunque las capacidades para cargos varios de la aplicación se usan en relación a cómo se escriben los cargos en el pedido, no se proporciona cálculo sistemático alguno; el cálculo depende de los datos del usuario para determinar el valor de los cargos. Los cargos solo se pueden agregar como único código de cargos tipo “envío” y no pueden editarse o cambiarse fácilmente en el PDV después de que los creen.

El uso de indicadores manuales de agregar cargos de envío aún está disponible en versiones 10.0 y posteriormente. Si una organización no habilita el parámetro **cargos automáticos avanzados** , los indicadores del sistema PDV para la entrada manual de cargos seguirán igual.

Con la función avanzado de cargos automáticos, los usuarios de PDV pueden tener cálculos sistemáticos para los cargos varios definido basados en las tablas de configuración de los cargos automáticos. Además, los usuarios tendrán de la capacidad de agregar o editar un número ilimitado de cargos adicionales y cuotas a cualquier transacción de las ventas PDV en la cabecera o el nivel de línea (para pedidos en efectivo o de clientes).

## <a name="enable-advanced-auto-charges"></a>Activar cargos automáticos avanzados

En la página **Retail y Commerce \> Configuración de sede \> Parámetros \> Parámetros de Commerce**, vaya a la pestaña **Pedidos de cliente**. En la ficha desplegable **Cargos**, establezca **Usar cargos automáticos avanzados** en **Sí**.

![Parámetros de cargos automáticos avanzados.](media/advancedchargesparameter.png)

Cuando se habilitan los cargos automáticos, ya no se pide a los usuarios que especifiquen manualmente un cargo de envío en el terminal del PDV al crear un pedido de cliente con enviar todo o enviar selección. Los cargos de pedidos PDV se calculan sistemáticamente y se añaden a la transacción del PDV (si se encuentra la tabla correspondiente de cargos automáticos que coincide con el criterio del pedido que se está creando). Los usuarios también pueden agregar o mantener los cargos de encabezado o de nivel de línea manualmente con las operaciones recién agregadas de PDV que se pueden agregar a los diseños de pantalla de PDV.

Cuando habilitan los cargos automáticos, los **Parámetros de Commerce** existentes para **Código de los cargos de envío** y **cargos de envío de la devolución** ya no se usan. Estos parámetros solo son aplicables si el parámetro **Usar cargos automáticos avanzados** se establece en **No**.

Antes de habilitar esta función, asegúrese de que se haya probado y haya formado a sus empleados, ya la función habilitada cambiará el flujo de proceso empresarial de cómo calculan y se agrega a los cargos de envío u otros a pedidos de ventas PDV. Asegúrese de que entiende el impacto del flujo de proceso en la creación de transacciones de PDV. Para el centro de asistencia telefónica y pedidos de e-commerce, el impacto de habilitar los cargos automáticos avanzados es mínimo. El centro de asistencia telefónica y las aplicaciones de comercio electrónico seguirán teniendo el mismo comportamiento que han tenido históricamente relacionado con las tablas de cargos automáticos para calcular las cuotas adicionales del pedido. Los usuarios del canal de centro de asistencia telefónica seguirán teniendo la capacidad de editar manualmente a cualquier cargo automático calculado por sistema en la cabecera o el nivel de línea, o agregar manualmente cargos varios extra en la cabecera o el nivel de línea.

## <a name="add-pos-operations"></a>Agregar operaciones de PDV

Para que los cargos automáticos avanzados funcionen correctamente en el entorno de aplicación de PDV se han agregado nuevas operaciones de PDV. Estas operaciones deben agregarse a su [Diseño de pantalla del PDV](/dynamics365/unified-operations/retail/pos-screen-layouts) e implementar en los dispositivos de PDV mientras implementa los cargos automáticos avanzados. Si estas operaciones no se agregan, los usuarios no podrán administrar o mantener cargos varios en las transacciones PDV y no tendrán ningún modo de ajustar o de cambiar los valores de cargos varios que se calculan sistemáticamente en función de la configuración de los cargos automáticos. Como mínimo, se sugiere que implementa la operación **Gestionar los cargos** en su diseño de PDV.

Las nuevas operaciones son las siguientes.

- **142 - Gestionar cargos** - Esta operación permite a los usuarios de PDV editar los cargos varios para la transacción PDV que se han agregado manualmente o sistemáticamente con los cálculos cargos automáticos.
- **141 - Agregar cargos de encabezado** - Use esta operación para dar al usuario la capacidad de agregar manualmente cargos varios en el nivel de encabezado en cualquier transacción de las ventas PDV (y seleccione el código de cargos que se utilizará).
- **140 - Agregar cargos de línea** - Use esta operación para dar al usuario la capacidad de agregar manualmente cargos varios de línea en cualquier transacción de las ventas PDV de línea (y seleccione el código de cargos que se utilizará).
- **143 - Actualizar los cargos** - Esta operación permite realizar una actualización completa de los cargos para la transacción de ventas. Actualizará cualquier cargo automático sobrescrito por el usuario basándose en la configuración de carrito actual.

Como con todas las operaciones de PDV, las configuraciones de seguridad se pueden crear para requerir la aprobación del director para ejecutar la operación.

Es importante tener en cuenta que las operaciones arriba enumeradas de PDV también se pueden agregar al diseño de PDV incluso si se deshabilita el parámetro **Usar cargos automáticos avanzados**. En esta situación, las organizaciones seguirán con los beneficios agregados de poder ver los gastos manualmente agregados y editarlos mediante la operación **Gestionar cargos**. Los usuarios también pueden usar las operaciones **Agregar cargos de encabezado** y **Agregar cargos de línea** para las transacciones de PDV incluso cuando se deshabilita el parámetro **Usar cargos automáticos avanzados**. La operación **Actualizar los cargos** tiene menos funcionalidad si se usa cuando se deshabilita **Usar cargos automáticos avanzados**. En este caso, no se actualizaría nada y cualquier cargo agregado manualmente a la transacción se restablecería en $0,00.

## <a name="use-case-examples"></a>Ejemplos de caso de uso

En esta sección, los casos de uso del ejemplo se muestran para ayudarle a comprender la configuración y uso de cargos automáticos y cargos varios en el contexto de pedidos del canal. En los ejemplos se muestra el comportamiento de la aplicación cuando se ha habilitado el parámetro **Usar cargos automáticos avanzados** .

### <a name="auto-charges-header-charges-example"></a>Ejemplo de cargos automáticos en cargos de encabezado

#### <a name="use-case-scenario"></a>Escenario del caso de uso

Un minoristas desea agregar automáticamente los cargos de flete cuando se realizan transacciones en cualquier canal de Commerce que requieren un envío de productos al cliente. El minorista dos proporciona métodos de entrega: tierra y aire. Si un cliente elige la entrega por tierra y el valor del pedido menos de 100 $, el minoristas desea cobrar al cliente un flete de 10 $. Si el pedido es de más de 100 $ y el cliente tienen el envío por tierra, no cobrará al cliente ninguna cuota de flete adicional. Si el cliente elige aire como método de entrega para todos los pedidos, independientemente de su valor total, se cargarán una cuota de flete de 20 $.

#### <a name="setup-and-configuration"></a>Establecimiento y configuración

Este escenario requiere la configuración de dos tablas de cargos automáticos.

Vaya a **Clientes \> Configuración de cargos \> cargos automáticos**.

Configure dos cargos automáticos en el nivel de encabezado. Configurar uno para el "Modo tierra" de entrega y otro para el “Modo aire” de entrega. Para esta situación, configúrelos para usar para “Todos los clientes”.

Para los cargos de entrega por tierra, en la sección líneas de la página **cargos automáticos** , defina un cargo que se aplique para los pedidos entre 0,01 $ y 100 $ como 10 $. Cree otra línea de cargos para indicar que los pedidos de más de 100,01 $ no tendrán cargos.

![Ejemplo de dos tablas de cobro automático.](media/headerchargesexample.png)

Para los cargos de entrega por aire, en la sección líneas del formulario cargos automáticos, defina un cargo de 20 $ que se aplicará a todos los pedidos (entre un valor de 0,01 $ a 9 999 999 $).

Envíe los cambios a Commerce Scale Unit/DB de canal para que los PDV puedan usarlos ejecutando el trabajo **Programación de distribución 1040**.

#### <a name="sales-processing-for-this-scenario"></a>Procesado de ventas para este escenario

Una vez que los pasos de configuración anteriores se completen y los cambios se han aplicado a la base de datos de canal, cualquier pedido de cliente o la transacción de ventas creada en PDV, el centro de asistencia, telefónica o los canales de e-commerce que tienen los métodos de entrega por tierra o aire establecidos en el nivel de encabezado usarán estos castos y los aplicarán automáticamente a la venta.

En este tiempo los cargos se aplicarán a todas las transacciones de ventas creadas dentro de la entidad jurídica que usen estos modos de entrega, ya que no hay funcionalidad para indicar que una configuración de cargo automático se aplique sólo a un canal vendedor específico.

Para los escenarios de PDV e informes de e-commerce, como no hay “cabecera" definida en estos pedidos, los cargos en el nivel de encabezado solo se aplicarán si todas las líneas de ventas en la transacción se fijan para entregarse con el mismo modo de envío. Si hay “modos mixtos” de cumplimiento en las transacciones realizadas por el sistema PDV o e-commerce, sólo tendrán en cuenta y se aplicarán cargos automáticos en el nivel de línea.

En escenarios de centro de asistencia telefónica, el usuario tiene control sobre el valor del modo de entrega en el encabezado del pedido, por tanto los cargos nivel de encabezado se aplicarán estos pedidos incluso si alguna de las líneas de ventas que se han configurado usan otro modo de entrega. Los cargos en el nivel de encabezado para los pedidos de centro de asistencia telefónica siempre se basarán en el modo de entrega definido en el nivel de encabezado del pedido del pedido de ventas.

### <a name="auto-charges-line-charges-example"></a>Ejemplo de cargos automáticos de cargos de línea

#### <a name="use-case-scenario"></a>Escenario del caso de uso 

Un minorista desea agregar un cargo adicional al cliente para las cuotas de configuración cuando el cliente compra un modelo determinado de equipo. Este equipo requiere las acciones de instalación no opcionales adicionales que el minorista realizará para el cliente. El minorista ha informado a los clientes que habrá una cuota adicional para esta configuración. El minorista prefiere administrar los cargos relacionados con esta cuota de manera independiente del precio de venta del producto para los informes financieros. Se facturará al cliente una cuota de instalación de 19,99 $ cuando este equipo específico se compre en cualquier canal.

#### <a name="setup-and-configuration"></a>Establecimiento y configuración

Este escenario requiere la configuración de una tabla de cargos automáticos en el nivel de línea.

Vaya a **Clientes \> Configuración de cargos \> Cargos automáticos**.

Establezca el menú desplegable **Nivel** en **Línea**, y cree un nuevo registro de cargos automáticos para todos los clientes y para el producto o el grupo de productos específico donde se cargarán las cuotas de configuración.

![Ejemplo de tabla de cargos automáticos de nivel de línea.](media/linechargesexample.png)

Envíe los cargos a Commerce Scale Unit/DB de canal para que los PDV puedan usarlos ejecutando el trabajo **Programación de distribución 1040**.

#### <a name="sales-processing-for-this-scenario"></a>Procesado de ventas para este escenario

Una vez que los pasos de configuración anteriores se completen y los cambios se han aplicado a la base de datos de canal, cualquier pedido de cliente o la transacción de ventas creada en PDV, el centro de asistencia, telefónica o los canales de e-commerce que tienen este elemento activarán un cargo en el nivel de línea que se añadirá sistemáticamente al total del pedido.

En este tiempo, los cargos se aplicarán a cualquier línea de ventas que coincida con la configuración de los cargos automáticos en el nivel de línea dentro de la entidad jurídica, ya que no hay funcionalidad para configurar un cargo automático en el nivel de línea para que se aplique solo a un canal de venta específico.

### <a name="manual-header-charges-example"></a>Ejemplo de cargos manuales de encabezado

#### <a name="use-case-scenario-description"></a>Descripción del escenario caso de uso

Un minorista está creando una excepción a los procesos típicos ofertando un servicio a domicilio especial para productos a clientes que piden productos en la tienda. El minorista y el cliente han acordado que el cliente pagará una cuota de manipulación adicional de 25 $ por este servicio. El que realiza el pedido necesita agregar esta cuota adicional a la transacción. Dado que la cuota es una cuota plana y no relacionada con un producto único del pedido, se va a utilizar un cargo de cabecera.

#### <a name="setup-and-configuration"></a>Establecimiento y configuración

Asegúrese de que el código de cargo que se usará en este escenario se ha configurado correctamente al encabezado **Clientes \> Configuración de cargos \> Cargos** para definir un código de cargo adecuado para la situación.

![Ejemplo de cargos.](media/chargesexample.png)

Si se considerará que el cargo un cargo relacionado con el “envío” con el fin de descuentos de promociones o relacionados de envío, establezca el **Cargo de envío** en el código de cargos en **Sí**. Si se permite que este cargo también pueda reembolsarse sistemáticamente durante el procesamiento de una transacción de devolución en la aplicación del PDV, establezca **Reembolsable** en **Sí**. El indicador **Reembolsable** solo se aplica cuando el parámetro **Usar cargos automáticos avanzados** se establece en **Sí**.

Envíe los cargos a Commerce Scale Unit/DB de canal para que los PDV puedan usarlos ejecutando el trabajo **Programación de distribución 1040**.

La operación **Agregar cargo de encabezado** se debe configurar en su [Diseño de pantalla de PDV](/dynamics365/unified-operations/retail/pos-screen-layouts) de modo que un botón que es accesible al usuario del PDV pueda llamar a esta operación (operación 141). Los cambios del diseño de pantalla se deben dirigir también al canal con la función de programación de la distribución.

#### <a name="sales-processing-of-manual-header-charges"></a>Procesamiento de ventas de cargos del encabezado manuales

Para ejecutar el escenario en la aplicación de PDV, el usuario PDV creará la transacción de ventas como de costumbre, agregando los productos y cualquier otra configuración para la venta. Antes de cobrar el pago, el usuario debe ejecutar la operación **Agregar cargo de encabezado** , que solicitará al usuario seleccione un código de cargos y especifica el valor de los cargos. Una vez que el usuario complete el proceso, agregar el cargo al pedido de ventas como un cargo nivel de encabezado.

Este proceso se puede aplicar al centro de asistencia telefónica mediante la función **Cargos** existente que aparece en la pestaña **Venta** en la barra de herramientas. En la página **Mantener cargos** , el usuario puede agregar nuevos cargos de líneas a la cabecera del pedido.

### <a name="manual-line-charges-example"></a>Ejemplo de cargos manuales de línea

#### <a name="use-case-scenario"></a>Escenario del caso de uso

Un cliente ha solicitado que los dos de cinco artículos en el pedido de ventas se envuelvan para regalo. El minorista ofrece este servicio opcional con una cuota de 2 $ por artículo. El que realice el pedido deberá agregar estas cuotas a los artículos específicos que deben llevarse a envuelto para regalos.

#### <a name="setup-and-configuration"></a>Establecimiento y configuración

Asegúrese de que el código de cargo que se usará en este escenario se ha configurado correctamente al encabezado **Clientes \> Configuración de cargos \> Cargos** para definir un código de cargo adecuado para la situación.

Si se considerará que el cargo debe considerarse un cargo relacionado con el “envío” con el fin de descuentos de promociones, establezca **cargos de envío** en el código de cargos en **Sí**. Si se permite que el cargo también pueda reembolsarse sistemáticamente durante el procesamiento de una transacción de devolución en la aplicación del PDV, establezca **Reembolsable** en **Sí**. El indicador **Reembolsable** solo se aplica cuando el parámetro **Usar cargos automáticos avanzados** se establece en **Sí**.

Envíe los cargos a Commerce Scale Unit/DB de canal para que los PDV puedan usarlos ejecutando el trabajo **Programación de distribución 1040**.

La operación **Agregar cargo de línea** se debe configurar en su [Diseño de pantalla de PDV](/dynamics365/unified-operations/retail/pos-screen-layouts) de modo que un botón que es accesible al usuario del PDV pueda llamar a esta operación (operación 140). Los cambios del diseño de pantalla se deben dirigir también al canal con la función de programación de la distribución.

#### <a name="sales-processing-of-the-manual-line-charge"></a>Procesamiento de ventas de cargos de línea manuales

Para ejecutar el escenario en la aplicación de PDV, el usuario PDV creará la transacción de ventas como de costumbre, agregando los productos y cualquier otra configuración para la venta. Antes de cobrar el pago, el usuario debe seleccionar la línea específica en el cargo que se aplicará en la visualización de la lista de artículos del PDV y ejecutar la operación **Agregar cargo de línea** . Se le solicitará al usuario seleccionar un código de cargos y especifica el valor de los cargos. Una vez que el usuario complete el proceso, el cargo se vinculará a la línea y añadirá al total del pedido como un cargo en el nivel de línea. El usuario puede repetir el proceso para agregar más cargos de línea a otras líneas de los artículos de la transacción, si es necesario.

El mismo proceso se puede aplicar al centro de asistencia telefónica mediante la función “mantener cargos” encontrada bajo el menú **Operaciones financieras** en la sección **Líneas de pedido de ventas** en la página **Pedidos de ventas** . Seleccionar esta opción abrirá la página **Mantener cargos** donde el usuario puede agregar un cargo específico de la nueva línea a la transacción.

## <a name="additional-features"></a>Funciones adicionales

### <a name="editing-charges-on-a-pos-sales-transaction"></a>Editar cargos en una transacción de las ventas PDV

La operación **Gestionar cargos** (142) se debe agregar a [Diseño de pantalla de PDV](/dynamics365/unified-operations/retail/pos-screen-layouts) de modo que un usuario pueda ver y editar o reemplazar los cargos de encabezado o línea calculados por el sistema o creados manualmente. Si la operación no se agrega, los usuarios no podrán ajustar el valor de los cargos en la transacción PDV, ni podrán ver los detalles de los cargos como el tipo de código de cargos atado el cargo.

En la página **Gestionar cargos** en el PDV, el usuario puede ver los detalles de los cargos de encabezado y de nivel de línea. El usuario puede utilizar la función **Editar** disponible en esta página para realizar cambios en el importe cargado en los cargos específicos particular. Una vez un cargo de línea se actualice manualmente no se volverá a calcular sistemáticamente a menos que el usuario inicie la operación **Actualizar cargos** .

Si **Código de motivo de la anulación del cargo** se ha configurado en la página **Parámetros de Commerce**, se le solicitará al usuario especificar un código de motivo cuando hayan modificado los cargos en la aplicación PDV.

Si los códigos de motivo se capturan para cargos sobrescritos, un nuevo informe también estará disponible para revisar y auditar los cambios. El informe se puede encontrar en **Retail y Commerce \> Consultas e informes \> Historial de la anulación de cargos**.

### <a name="refunding-charges-on-a-pos-return-transaction"></a>Recuperación de cargos de una transacción de devolución de PDV

Si el parámetro **Usar cargos automáticos avanzados** se establece en **Sí**, el parámetro de Commerce existente para **Devolver cargos de envío** ya no es aplicable. Para indicar qué cargos se deben devolver sistemáticamente a un cliente al usar cargos automáticos avanzados, asegúrese de que el código de cargos relacionado se ha configurado como **Reembolsable** en la página de configuración **Código de cargos** . Asegúrese de que los valores se hayan sincronizado a las bases de datos del canal de Commerce con el proceso de programación de la distribución.

> [!TIP]
> Para obtener orientación que le ayude a garantizar que los cargos reembolsables en el nivel de línea se calculen en función de la cantidad que se devuelve, consulte [Los cargos reembolsables no están calculados según la cantidad devuelta](/troubleshoot/Refund-charges-miscalculated-for-partial-quantity-returned.md).

### <a name="refunding-charges-on-a-return-order-transaction"></a>Devolución de cargos de una transacción de devolución de pedido

Los cargos no se devuelven sistemáticamente a los **Devolver pedidos** creados en Commerce. Los usuarios deben seleccionar la opción **Copiar cargos** al crear el **Pedido de devolución**. Si **Copiar cargos** no está seleccionada, no se devolverán automáticamente los cargos de la transacción de ventas original. Si se selecciona **Copiar cargos**, se copiarán todos los cargos al pedido de devolución y el usuario puede editar o eliminar manualmente los cargos que éste no desee tener devueltos. El proceso de pedido de devolución de centro de asistencia telefónica no confirma actualmente el indicador **Reembolsable** en la configuración **Código de cargos** .

### <a name="configuring-pos-receipts-to-show-charges"></a>Configurar recibod PDV para mostrar cargos

Los siguientes elementos de recibo se han agregado a la línea y el pie de página del recibo para admitir la funcionalidad avanzada de cargos automáticos.

- **cargos de envío de la línea** - Este artículo de nivel de línea se puede usar para recapitular los códigos de cargos específicos que se aplicaron a la línea de ventas. Sólo los códigos de cargos se han designado marcados como **Envío** en la página **Código de cargos** aparecerán aquí.
- **Otros cargos de línea** - Este artículo de nivel de línea se puede usar para recapitular los códigos de cargos específicos que no son de envío que se aplicaron a la línea de ventas. **Otros cargos de línea** son los códigos de cargos en que el indicador **Envío** en la página **Código de cargos** no se ha habilitado.
- **Detalles de los cargos de envío del pedido** - Este artículo de pie de página nivel muestra las descripciones de los códigos de cargo que se aplicaron al pedido que se han designado como cargos de **Envío** en la página de configuración **Código de cargos**.
- **Cargos de envío del pedido** - Este artículo de pie de página muestra el valor de los cargos relacionados con el envío.
- **Detalles otros cargos del pedido** - Este artículo de pie de página nivel muestra las descripciones de los códigos de cargos que se aplicaron al pedido que no se han designado como cargos relacionados con el envío.
- **Otros cargos de pedido** - Este artículo de pie de página muestra el valor en dólares de los otros cargos que no están relacionados con el envío.

Se recomienda que la organización también añada campos de texto libre al pie del recibo, para definir las áreas en las que se recapitularán los cargos.

### <a name="preventing-charges-from-being-calculated-until-the-pos-order-is-completed"></a>Evitar que se calculen los cargos hasta que el pedido de PDV se complete

Algunas organizaciones pueden preferir espera hasta que el usuario haya terminado de agregar todas las líneas de ventas a la transacción PDV antes de calcular los cargos. Para evitar el cálculo de cargos en artículos a medida que se agregan a la transacción PDV, active el parámetro **Cálculo del cargo manual** en el **Perfil de funcionalidad** que usa la tienda. Habilitar este parámetro requerirán al usuario PDV usar la operación **Calcular totales** cuando han terminado de añadir los productos a la transacción PDV. La operación **Calcular totales** se activará y calculará cualquier cargo automático para el encabezado o líneas del pedido, según sea aplicable.

### <a name="charges-override-reports"></a>Informes de anulación de cargos

Si los usuarios manualmente anulan los gastos calculados o agregan gastos manualmente a la transacción, estos datos estarán disponibles para fines de auditoría en el informe **Historial de la anulación de cargos**. Se puede obtener acceso al informe en **Retail y Commerce \> Consultas e informes \> Historial de la anulación de cargos**. Es importante tener en cuenta que los datos necesarios para este informe se importan de la base de datos del canal en la Sede a través de los trabajos de la programación de distribución “P”. Por lo tanto, la información sobre anulaciones recién efectuadas en el PDV puede no estar disponible inmediatamente en este informe hasta que el trabajo haya cargado los datos de transacciones de la tienda en la Sede.

## <a name="additional-resources"></a>Recursos adicionales

[Habilitar y configurar cargos automáticos por canal](auto-charges-by-channel.md)

[Prorratear los cargos de encabezado con las líneas de ventas coincidentes](pro-rate-charges-matching-lines.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]

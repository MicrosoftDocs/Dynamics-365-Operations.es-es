---
title: Previsiones de flujo de efectivo
description: Este tema proporciona una visión general del proceso de previsión de flujo de efectivo. También explica cómo la previsión de flujo de efectivo se integra con otros módulos del sistema.
author: panolte
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 7d462992816a5a2dee73979ed4cb1521ca4ce4f7
ms.sourcegitcommit: c8dc60bb760553f166409c2e06dd2377f601c006
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2021
ms.locfileid: "7945763"
---
# <a name="cash-flow-forecasting"></a>Previsiones de flujo de efectivo

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Puede usar las herramientas para la previsión del flujo de efectivo para analizar el flujo de efectivo que va a entrar y los requisitos de divisa para estimar la futura necesidad de efectivo de la compañía. Para obtener una previsión fiable del flujo de efectivo, debe completar las tareas siguientes:

- Identifique y haga una lista con todas las cuentas de liquidez. Las cuentas de liquidez son las cuentas de efectivo de la empresa y equivalentes.
- Configurar el comportamiento de las previsiones de transacciones que afecten a las cuentas de liquidez de la empresa.

Una vez completadas estas tareas, puede calcular y analizar las previsiones de flujo de efectivo y los requisitos de divisa para el futuro.

## <a name="cash-flow-forecasting-integration"></a>Integración de la previsión de flujo de efectivo

La previsión del flujo de caja se puede integrar con el Libro mayor, los proveedores, los clientes y la gestión de presupuesto e inventario. El proceso de previsión utiliza la información de transacción que se especifica en el sistema y el proceso de cálculo prevé el impacto del efectivo esperado de cada transacción. Los siguientes tipos de transacciones se tienen en cuenta al calcular el flujo de efectivo:

- **Pedidos de ventas**: pedidos de ventas que aún no se han facturado y que originan ventas físicas o financieras.
- **Facturas de texto libre** - Facturas de texto libre que aún no se han publicado y que generan ventas financieras. 
- **Pedidos de compra**: pedidos de compra que aún no se han facturado y que originan compras físicas o financieras.
- **Clientes**: transacciones de clientes abiertas (facturas impagadas).
- **Proveedores**: transacciones de proveedores abiertas (facturas impagadas).
- **Transacciones contables**: transacciones donde se ha especificado que habrá un registro futuro.
- **Entradas de registro de presupuesto**: asientos de registro presupuestario que se seleccionan para previsiones de flujo de efectivo.
- **Previsiones de la demanda**: líneas de modelo de previsión de inventario seleccionadas para previsiones de flujo de efectivo.
- **Previsiones de suministro**: líneas de modelo de previsión de inventario seleccionadas para previsiones de flujo de efectivo.
- **Fuente de datos externa** - Datos externos que se ingresan o importan en los pronósticos de flujo de efectivo mediante plantillas de hojas de cálculo.
- **Previsiones de proyectos**: gestión de proyectos y previsiones contables mediante modelo de previsión.
- **Pagos de la autoridad fiscal sobre las ventas de flujo de efectivo** - Montos previstos de pago de la autoridad fiscal sobre las ventas y plazos que dan lugar a pagos financieros. Habilite la función Pagos de la autoridad fiscal sobre las ventas de flujo de efectivo.

## <a name="configuration"></a>Configuración

Para configurar el proceso de previsión de flujo de efectivo, use la página **Configuración de la previsión de flujo de efectivo**. En esta página, especifique las cuentas de liquidez de las que se vaya a realizar un seguimiento y los comportamientos predeterminados de previsión para cada área.

### <a name="general-ledger"></a>Contabilidad general

Primero debe definir las cuentas de liquidez a las que se va a realizar el seguimiento a través de previsiones de flujo de caja. Normalmente, estas cuentas de liquidez son las cuentas principales que están asociados a las cuentas bancarias que recibirán y desembolsarán efectivo. En la página **Configuración de la previsión de flujo de efectivo**, en la pestaña **Contabilidad general**, seleccione las cuentas principales para incluir en la previsión. Si una cuenta bancaria se ha asociado a la cuenta principal en la página **Cuenta bancaria**, aparece en el campo **Cuenta bancaria**.

Puede configurar una previsión de flujo de efectivo dependiente para una cuenta principal que contenga transacciones directamente relacionadas con transacciones de otra cuenta principal. Cada línea que agrega en la sección **En cuentas dependientes** crea un importe de previsión de flujo de efectivo en una cuenta principal dependiente. Este importe es un porcentaje de los importes de flujo de efectivo para la cuenta principal seleccionada.

En primer lugar, establezca el campo **Cuenta principal** en la cuenta principal, donde se espera que se produzcan las transacciones inicialmente. Establezca el campo **Cuenta principal dependiente** en la cuenta que se verá afectada por la transacción inicial en la cuenta principal. Establezca los valores adecuados en los demás campos de la línea. Puede cambiar el valor del campo **Porcentaje** para reflejar el efecto de la cuenta principal en la cuenta principal dependiente. Para una previsión de ventas o compras, seleccione el valor **Condiciones de pago** utilice la mayoría de clientes o proveedores. Establezca el campo **Tipo de registro** en el tipo de registro esperado relativo a la previsión de flujo de efectivo.

### <a name="accounts-payable"></a>Proveedores

Puede calcular previsiones para compras usando las opciones de configuración en la pestaña **Proveedores** de la página **Configuración de la previsión de flujo de efectivo**. Para poder configurar la previsión de flujo de efectivo para los proveedores, antes debe configurar las condiciones de pago, los grupos de proveedores y los perfiles de registro de proveedores.

En la sección **Valores predeterminados de previsión de compra**, puede seleccionar los comportamientos predeterminados de compra para la previsión de flujo de efectivo. Tres campos determinan la hora del impacto del efectivo: **Tiempo entre la fecha de entrega y la fecha de la factura**, **Condiciones de pago** y **Tiempo entre la fecha de vencimiento de la factura y la fecha de pago**. La previsión utilizará la configuración predeterminada para el campo **Condiciones de pago** si un valor no se ha especificado en la transacción. Use una condición de pago para describir el número más habitual de días para cada parte del proceso.

El campo **Cuentas de liquidez para pagos** especifica la cuenta de liquidez que sea la utiliza con mayor frecuencia para los pagos. Use el campo **Porcentaje del importe que se va a asignar a la previsión de flujo de efectivo** para especificar si un porcentaje de importes se debe usar durante la previsión. Deje de este campo en blanco si los importes de la transacción completa se utilizan durante la previsión.

Puede anular la configuración predeterminada el campo **Tiempo entre la fecha de vencimiento de la factura y la fecha de pago** para los grupos de proveedores específicos. El pronóstico utilizará el valor predeterminado de la sección **Valores predeterminados de previsión de compra** a menos que un valor diferente se especifique para el grupo de proveedores que está relacionado con el proveedor en la transacción. Para anular el valor predeterminado, seleccione un grupo de proveedores y, después, establezca el nuevo valor para el campo **Hora de compra**.

Puede anular el valor predeterminado para el campo **Cuenta de liquidez** para perfiles de registro de proveedores específicos. El pronóstico utilizará el valor predeterminado de la sección **Valores predeterminados de previsión de compra** a menos que una cuenta de liquidez diferente se especifique para el perfil de registro que está relacionado con el proveedor en la transacción. Para anular el valor predeterminado, seleccione un perfil de registro y, a continuación, especifique la cuenta de liquidez que se espera que vaya a estar afectada.

### <a name="accounts-receivable"></a>Clientes

Puede calcular previsiones para ventas usando las opciones de configuración en la pestaña **Clientes** de la página **Configuración de la previsión de flujo de efectivo**. Para poder configurar la previsión de flujo de efectivo para los clientes, antes debe configurar las condiciones de pago, los grupos de clientes y los perfiles de registro de clientes.

En la sección **Valores predeterminados de previsión de venta**, puede seleccionar los comportamientos predeterminados de venta para la previsión de flujo de efectivo. Tres campos determinan la hora del impacto del efectivo: **Tiempo entre la fecha de envío y la fecha de la factura**, **Condiciones de pago** y **Tiempo entre la fecha de vencimiento de la factura y la fecha de pago**. La previsión utilizará la configuración predeterminada para el campo **Condiciones de pago** si un valor no se ha especificado en la transacción. Use una condición de pago para describir el número más habitual de días para cada parte del proceso. 

El campo **Cuentas de liquidez para pagos** especifica la cuenta de liquidez que sea la utiliza con mayor frecuencia para los pagos. Use el campo **Porcentaje del importe que se va a asignar a la previsión de flujo de efectivo** para especificar si un porcentaje de importes se debe usar durante la previsión. Deje de este campo en blanco si los importes de la transacción completa se utilizan durante la previsión.

Puede anular la configuración predeterminada el campo **Tiempo entre la fecha de vencimiento de la factura y la fecha de pago** para los grupos de clientes específicos. El pronóstico utilizará el valor predeterminado de la sección **Valores predeterminados de previsión de venta** a menos que un valor diferente se especifique para el grupo de clientes que está relacionado con el cliente en la transacción. Para anular el valor predeterminado, seleccione un grupo de clientes y, después, establezca el nuevo valor para el campo **Hora de venta**.

Puede anular el valor predeterminado para el campo **Cuenta de liquidez** para perfiles de registro de clientes específicos. El pronóstico utilizará el valor predeterminado de la sección **Valores predeterminados de previsión de venta** a menos que una cuenta de liquidez diferente se especifique para el perfil de registro que está relacionado con el cliente en la transacción. Para anular el valor predeterminado, seleccione un perfil de registro y, a continuación, establezca la cuenta de liquidez que se espera que vaya a estar afectada.

### <a name="budgeting"></a>Gestión presupuestaria

Los presupuestos creados a partir de los modelos presupuestarios se pueden incluir en previsiones de flujo de efectivo. En la página **Configuración de la previsión de flujo de efectivo**, en la pestaña **Presupuesto** , seleccione los modelos presupuestarios para incluir en la previsión. De forma predeterminada, los nuevos asientos de registro presupuestario se incluyen en las previsiones después de que el modelo presupuestario se haya habilitado para la previsión de flujo de efectivo.

Las entradas del registro presupuestario se pueden incluir en la previsión de flujo de efectivo de forma individual a través de la personalización. Cuando agrega la columna "Incluir en las previsiones de flujo de efectivo" a la página **Entrada de registro presupuestario**, el sistema sobrescribirá la configuración en la página **Configuración de pronóstico de flujo de efectivo** para incluir una entrada de registro de presupuesto individual en el pronóstico.


### <a name="inventory-management"></a>Administración de inventario

Las previsiones de suministro y demanda de inventario se pueden incluir en las previsiones de flujo de efectivo. En la pestaña **Gestión del inventario** de la página **Configuración de la previsión de flujo de efectivo** , seleccione el modelo de previsión que se va a incluir en la previsión de flujo de efectivo. La inclusión en la previsión de flujo de efectivo se puede sobrescribir en líneas de previsión de suministro y demanda individuales.

### <a name="setting-up-dimensions-for-cash-flow-forecasting"></a>Configurar dimensiones para la previsión del flujo de efectivo
Una nueva pestaña de la página **Configuración de pronósticos de flujo de efectivo** le permite controlar qué dimensiones financieras se utilizarán para filtrar en el espacio de trabajo **Previsión de flujo de efectivo**. Esta pestaña solo aparecerá solo cuando la función de pronósticos de flujo de efectivo esté habilitada.

En la pestaña **Dimensiones**, elija de la lista de dimensiones que se utilizarán para el filtrado y utilice las teclas de flecha para moverlas a la columna de la derecha. Solo se pueden seleccionar dos dimensiones para filtrar los datos de pronósticos de flujo de efectivo. 

### <a name="setting-up-external-source"></a>Configurar origen externo
Los datos externos se pueden introducir o importar en forma de pronósticos de flujo de efectivo. Antes de introducir o importar datos externos, debe configurar orígenes externos. En la pestaña **Origen externo**, configure categorías de flujo de efectivo externas. Una categoría puede ser **Saliente** o **Entrante**. **Liquidez** debe seleccionarse como tipo de registro. En la cuadrícula **Configuración de entidad legal**, seleccione las entidades legales y las cuentas principales correspondientes a las que se aplican las categorías de flujo de efectivo externas.

### <a name="project-management-and-accounting"></a>Gestión de proyectos y contabilidad

En la versión 10.0.17, una nueva característica permite la integración con la gestión y contabilidad de proyectos y la previsión de flujo de efectivo. En el espacio de trabajo **Gestión de funciones**, active la característica **Previsión del proyecto de flujo de efectivo** para incluir los costes e ingresos pronosticados en el pronóstico de flujo de efectivo. En la pestaña **Gestión y contabilidad de proyectos** de la página **Configuración de pronóstico de flujo de efectivo**, seleccione los tipos de proyectos y tipos de transacciones que deben incluirse en la previsión de flujo de efectivo. Luego seleccione el modelo de previsión del proyecto. Un submodelo de tipo de reducción funciona mejor. Las cuentas de liquidez que se introdujeron en la configuración de Clientes se utilizan como cuentas de liquidez predeterminadas. Por lo tanto, no es necesario introducir cuentas de liquidez predeterminadas cuando configure el pronóstico de flujo de efectivo. También se puede utilizar un modelo de presupuesto, pero solo se puede seleccionar un tipo en la página **Configuración de pronóstico de flujo de efectivo** para gestión de proyectos y contabilidad. Un modelo de pronóstico proporciona la mayor flexibilidad cuando se utiliza la gestión y contabilidad de proyectos o Project Operations.

Una vez activada la función de pronóstico del proyecto de flujo de efectivo, el pronóstico del flujo de efectivo se puede ver para cada proyecto en la página **Todos los proyectos**. En el panel Acciones, en la pestaña **Plan**, en el grupo **Pronóstico**, seleccione **Pronóstico de flujo de efectivo**. En los espacios de trabajo **Resumen de efectivo** (véase la sección [Informes](#reporting) más adelante en este tema), el tipo de transacción de pronóstico del proyecto muestra las entradas (ingresos del pronóstico del proyecto) y las salidas (costes del pronóstico del proyecto). Los importes pueden incluirse solo si el campo **Etapa del proyecto** campo de los espacios de trabajo **Resumen de flujo de efectivo** están configurados como **En proceso**.

Las transacciones del proyecto siguen incluidas en el pronóstico de flujo de efectivo de varias maneras, independientemente de si se activa la característica **Previsión del proyecto de flujo de efectivo**. Las facturas de proyecto registradas se incluyen en la previsión como parte de las transacciones de cliente abiertas. Los pedidos de ventas y pedidos de compra iniciados por el proyecto se incluyen en la previsión como pedidos abiertos después de registrarlos en el sistema. También puede transferir previsiones de proyecto a un modelo presupuestario contable. Este modelo presupuestario contable se incluye en la previsión de flujo de efectivo como parte de los asientos de registro presupuestario. Si ha activado la característica **Previsión del proyecto de flujo de efectivo**, no transfiera los pronósticos del proyecto a un modelo de presupuesto contable, ya que esta acción hará que los pronósticos del proyecto se cuenten dos veces.

### <a name="sales-tax-authority-payments"></a>Pagos a la autoridad fiscal 

La función de pagos de la autoridad de impuestos sobre las ventas de flujo de efectivo predice el impacto del flujo de efectivo de los pagos de impuestos sobre las ventas. Utiliza transacciones impagas de impuestos sobre las ventas, períodos de liquidación de impuestos y el plazo de pago del período impositivo para predecir la fecha y el monto de los pagos de flujo de efectivo. 

### <a name="calculation"></a>Cálculo

Para poder ver análisis de previsión de flujo de efectivo, antes debe ejecutar el proceso de cálculo del flujo de efectivo. El proceso de cálculo proyectará los impactos futuros de efectivo de las transacciones que se han indicado.

Calcule la previsión de flujo de efectivo mediante la página **Calcular previsiones de flujo de efectivo**. Puede calcular la previsión de flujo de efectivo completa o una previsión de flujo de efectivo incremental. 

- Para borrar todas las transacciones de previsión de flujo de efectivo y volver a calcularlas, establezca el campo **Método de cálculo de previsiones de flujo de efectivo** en **Total**. Se recomienda que use este método si no se han actualizado las previsiones de flujo de efectivo durante mucho tiempo. 
- Para actualizar la información existente de flujo de efectivo para las nuevas transacciones solo, establezca el campo **Método de cálculo de previsiones de flujo de efectivo** en **Nuevo**. La página mostrará la fecha en que el cálculo de flujo de efectivo se estaba ejecutando por última vez.

También puede usar el procesamiento por lotes para la previsión de flujo de efectivo. Para ayudar a garantizar que sus análisis de previsión se actualizan con regularidad, configure un proceso de lote periódico para el cálculo de la previsión de flujo de efectivo.

En la versión 10.0.13, se publicó una mejora en el proceso de cálculo que utiliza el marco de trabajo de automatización de procesos para programar el trabajo de cálculo de flujo de efectivo. Esto se habilita usando la característica **Automatización de la previsión de flujo de efectivo** en el espacio de trabajo **Gestión de funciones**. Una vez habilitada, seleccione el vínculo **Automatización de la previsión de flujo de efectivo** para mostrar la nueva página de automatización donde puede programar el proceso de cálculo del flujo de efectivo. Para crear un nuevo programa de previsión de flujo de efectivo, seleccione **Crear nueva automatización de procesos** y luego seleccione **Automatización de la previsión de flujo de efectivo** en el menú desplegable **Tipo de programa**. Debe establecer un programa para cada compañía para la que está actualizando los datos de previsión del flujo de efectivo.  Esta página también muestra qué trabajos de automatización de la previsión del flujo de efectivo están pendientes y cuándo se completó el último trabajo.  

> [!NOTE] 
> Si los trabajos por lotes existentes ya están programados para las previsiones del flujo de efectivo, recibirá un mensaje de error y no podrá habilitar esta característica. Los trabajos por lotes existentes deberán borrarse antes de que pueda habilitar esta característica. 

Para obtener más información, consulte [Automatización de procesos](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

### <a name="reporting"></a>Notificación

Tras calcularse la previsión de flujo de efectivo, debe actualizar la información asociada a la entidad para el informe de errores analítico. En la página **Almacén de entidades**, seleccione la medida **Agregado de LedgerCovLiquidityMeasurement** y, a continuación, haga clic en **Actualización**.

Existen dos espacios de trabajo que contienen datos de previsión de flujo de efectivo. Un espacio de trabajo contiene datos para todas las empresas y el otro espacio de trabajo tiene solo datos para la empresa actual.

El acceso al espacio de trabajo para todas las empresas se controla con el deber **Ver flujo de efectivo en el espacio de trabajo para todas las empresas**. De forma predeterminada, el espacio trabajo **Visión general del efectivo para todas las empresas** estará disponible para los roles siguientes:

- Director General
- Director financiero
- Controlador financiero

El acceso al espacio de trabajo para la empresa a actual se controla con el debe de espacio de trabajo **Ver flujo de efectivo en el espacio de trabajo para la empresa actual**. De forma predeterminada, el espacio trabajo **Visión general del efectivo para la empresa actual** estará disponible para los roles siguientes:

- Contable
- Administrador contable
- Supervisor contable
- Administrador de proveedores
- Administrador de clientes

El espacio de trabajo **Visión general del efectivo para todas las empresas** muestra los análisis de previsión de flujo de efectivo en la divisa del sistema. La divisa del sistema y el tipo de cambio del sistema que se usan para el análisis se definen en la página **Parámetros del sistema**. Este espacio de trabajo muestra una visión general de la previsión del flujo de efectivo y los saldos de cuenta bancaria para todas las empresas. Un gráfico de los flujos de entrada y de salida de efectivo ofrece una visión general de los movimientos y los saldos de futuros de efectivo en la divisa del sistema, así como información detallada sobre las transacciones de previsión. También puede ver los saldos previstos de la divisa.

El espacio de trabajo **Visión general del efectivo para la empresa actual** muestra los análisis de previsión de flujo de efectivo en la divisa de contabilidad definida de la empresa. La divisa de contabilidad que se usa para el análisis se define en la página **Libro mayor**. Este espacio de trabajo muestra una visión general de la previsión del flujo de efectivo y los saldos de cuenta bancaria para la empresa actual. Un gráfico de los flujos de entrada y de salida de efectivo ofrece una visión general de los movimientos y los saldos de futuros de efectivo en la divisa de contabilidad, así como información detallada sobre las transacciones de previsión. También puede ver los saldos previstos de la divisa.

Para obtener más información sobre los análisis de previsión de flujo de efectivo, consulte [contenido de Power BI de visión general de efectivo](Cash-Overview-Power-BI-content.md).

Además, puede ver los datos de previsión de flujo de efectivo para cuentas, pedidos y artículos específicos en las siguientes páginas:

- **Saldo de comprobación**: seleccione **Previsiones de flujo de efectivo** para ver los flujos de efectivo de futuros para la cuenta principal seleccionada.
- **Todos los pedidos de venta**: en la pestaña **Factura**, seleccione **Previsiones de flujo de efectivo** para ver el impacto de efectivo previsto del pedido de ventas seleccionado.
- **Todos los pedidos de compra**: en la pestaña **Factura**, seleccione **Previsiones de flujo de efectivo** para ver el impacto de efectivo previsto del pedido de compras seleccionado.
- **Previsión de suministro**: seleccione **Previsiones de flujo de efectivo** para ver los flujos de efectivo futuro que están asociados a la previsión de suministro del artículo seleccionado.
- **Previsión de demanda**: seleccione **Previsiones de flujo de efectivo** para ver los flujos de efectivo futuro que están asociados a la previsión de demanda del artículo seleccionado.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

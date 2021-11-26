---
title: Conceptos clave de la administración de cobros
description: Los temas definen conceptos clave de la administración de cobros.
author: JodiChristiansen
ms.date: 11/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: ba64910498732855303e14d3884618597d21510d
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753955"
---
# <a name="collections-management-key-concepts"></a>Conceptos clave de la administración de cobros

[!include [banner](../includes/banner.md)]

Antes de comenzar a configurar cobros o a trabajar con ellos, debe comprender los siguientes conceptos:

- Las instantáneas de vencimiento de los clientes contienen información sobre saldos vencidos en un momento determinado.
- Las secciones de clientes de cobros le ayudan a organizar su trabajo.
- Los agentes de cobros tienen sus propias secciones de clientes.
- En las páginas de lista se organizan los clientes, las actividades y los casos de cobros.
- Toda la información de cobros de un cliente se encuentra en una página, desde donde puede responder.
- El interés y las cuotas se pueden condonar, restablecer o invertir en un solo paso.
- Se pueden crear transacciones de cancelación en un solo paso.
- Se pueden procesar pagos de fondos insuficientes (NSF) en un solo paso.

En este tema se describe cada concepto.

## <a name="customer-aging-snapshots"></a>Instantáneas de vencimientos de clientes

Una instantánea de vencimientos contiene los saldos vencidos calculados en un momento determinado. Esta información aparece en la página de lista **Saldos vencidos** y en la página **Cobros**. Se debe crear una instantánea de vencimientos para poder ver información en las páginas de lista de colecciones (**Saldos vencidos**, **Actividades de cobro** y **Casos de cobro**).

Para cada cliente, las instantáneas de vencimientos contienen un encabezado de instantánea de vencimientos y los registros de detalle que corresponden a cada período de vencimiento en la definición de período de vencimiento.

El encabezado de instantánea de vencimientos contiene el importe vencido total, el límite de crédito, el importe del albarán, el importe del pedido de ventas, el número de transacciones con conflicto y el importe total de las transacciones con conflicto para la cuenta de cliente. Todas las transacciones del cliente se incluyen al calcular estos importes. El importe vencido total, el límite de crédito, el importe del albarán y el importe del pedido de ventas aparecen en el cuadro informativo **Información crediticia** de la página **Cobros**.

Para cada período de vencimiento de la definición de período de vencimiento, se crea un registro de detalle de la instantánea de vencimientos. Cada registro de detalles contiene el id. del período de vencimiento y el importe total de las transacciones que tienen las fechas en el período de vencimiento. Las transacciones tienen asignado un período de vencimiento, como 30 días pasados desde el vencimiento. La fecha es relativa al valor de fecha de **Vencimiento a partir de** que se especifica al crear la instantánea de vencimientos. Esta información se muestra en la página de lista **Saldos vencidos** y en el cuadro informativo **Saldos vencidos** de la página **Cobros**.

## <a name="collections-customer-pools"></a>Secciones de cobros de clientes

Las secciones de clientes son consultas que definen un grupo de registros de clientes. Puede usar estos registros agrupados para ver información de las cuentas de cliente que se incluyen y para administrar cobros o procesos de vencimiento para ellos. Puede usar las secciones de clientes para filtrar información en las página de lista de cobros. También pueden usarlas para filtrar las cuentas de cliente que se incluyen al crear instantáneas de vencimientos.

## <a name="collections-agents"></a>Agentes de cobros

De forma predeterminada, los usuarios pueden ver toda la información de clientes en las páginas de listas de cobros. Los registros de agente de cobros le permiten determinar las secciones de clientes que se pueden usar para filtrar la información de las páginas de listas de cobros y en la página **Cobros**.

Los agentes de cobros trabajan con clientes para asegurarse de que los pagos se cobren a tiempo. Son trabajadores asignados a usuarios en la página **Configuración de usuario**.

## <a name="collections-list-pages"></a> Páginas de listas Cobros 

Las siguientes páginas de lista le ayudan a organizar la información de cobros:

- **Saldos vencidos**: las columnas de esta página de la lista muestran los saldos de los clientes y los importes vencidos por período de vencimiento. Esta información se almacena como una instantánea de vencimientos. Los períodos de vencimiento se determinan por la definición de período de vencimiento que se use. La definición del período de vencimiento se toma de la sección de clientes, si se ha especificado una para la consulta de secciones. Si la sección no tiene una definición de período de vencimiento, se usará la definición de período de vencimiento predeterminada que se haya especificado en la página **Parámetros de clientes**. Si no se especifica ninguna definición de período de vencimiento predeterminada, se usa la primera definición de período de vencimiento de la página **Definiciones de período de vencimiento**.
- **Actividades de cobros**: en las columnas de esta página de lista se muestran las actividades identificadas como actividades de cobros. Estas actividades se crean en la página **Cobros**. Se usan actividades para realizar un seguimiento del trabajo que realiza en relación con los cobros.
- **Casos de cobros**: en las columnas de esta página de lista se muestra información de los casos que pertenecen a una categoría de caso cuyo tipo de caso es **Cobros**.

### <a name="aging-snapshots"></a>Instantáneas de vencimientos

Es necesario crear una instantánea de vencimientos para poder visualizar la información de las páginas de lista de cobros. Sólo se muestra información para aquellos clientes para los que se haya creado una instantánea de vencimientos. Los registros que se muestran en la página de lista se pueden filtrar más, como se explica aquí:

- De forma predeterminada, los usuarios tienen acceso a todos los clientes que dispongan de una instantánea de vencimientos.
- Si existen secciones de clientes, es necesario configurar un usuario como agente de cobros para que pueda usar las secciones para filtrar información de páginas de listas de cobros. El acceso a esta información está limitado a los clientes incluidos en la sección de clientes seleccionada.
- Si un usuario está configurado como agente de cobros, solo estarán disponibles en la página de lista de cobros las secciones seleccionadas para ese agente de cobros. Si se ha seleccionado la opción **Permitir que el agente vea todas las secciones de clientes** en la página **Agente de cobros** para el agente de cobros, todas las secciones quedan disponibles para ese agente.

## <a name="collections-page"></a> Página Cobros

Puede usar la página **Cobros** para ver, administrar y actuar en la información de cobros, actividades y casos de un cliente.

La sección superior de la página muestra casos para el cliente seleccionado, la sección central muestra transacciones para el cliente y la sección inferior muestra actividades para el cliente. Puede crear casos de cobros para realizar seguimientos de la información de cobros de una o varias transacciones y actividades. La información que aparece en la partes superior e inferior se puede filtrar por caso.

En los cuadros informativos se muestran los saldos vencidos y la información de límite de crédito para el cliente seleccionado. Esta información se almacena en la instantánea de vencimientos. En caso necesario, puede actualizar la instantánea de vencimientos con información actual.

El panel de acciones contiene los botones que muestran información relacionada para el cliente, el caso, la transacción o la actividad seleccionada. También puede realizar acciones comunes, como cambiar el estado de cobros de una transacción, enviar mensajes de correo electrónico por medio de la integración con su proveedor de correo electrónico, realizar reembolsos a clientes, procesar pagos NSF y cancelar saldos incobrables.

## <a name="waiving-reinstating-or-reversing-interest-and-fees"></a>Condonar, restablecer o revertir interés y cuotas

Puede renunciar, restablecer o invertir notas de interés completas, o las cuotas e intereses de la transacción que forman parte de las notas de interés. En la pestaña **Cobrar** del panel de acciones de la página de lista **Todos los clientes**, seleccione **Nota de interés**, **Interés de transacción** o **Cuota**.

Estos ajustes sólo afectan a las notas de interés, así como a los intereses y cuotas incluidos en éstos. Para obtener información sobre cómo cancelar todos los cargos que debe un cliente, consulte la sección [Crear transacciones de cancelación](#creating-write-off-transactions) de este tema.

Para obtener más información, consulte Crear un código de interés con un intervalo y Interés del proceso.

## <a name="creating-write-off-transactions"></a>Crear transacciones de cancelación

Puede cancelar las deudas incobrables seleccionando **Cancelar** en la página **Cobros** y en las páginas de lista de cobros.

Al cancelar transacciones para un cliente, todas las transacciones del cliente se marcan automáticamente para liquidación. El importe que se cancela depende del importe neto de las transacciones marcadas. La transacción de cancelación se crea en un diario general, que puede contener hasta tres tipos de líneas de diario:

- El primer tipo de línea de diario contiene la entrada de cancelación del cliente. Si las transacciones marcadas contienen varias combinaciones de códigos de divisa, dimensiones y perfiles de registro, se crea una línea de diario independiente para cada combinación.
- El segundo tipo de línea de diario contiene la entrada de cancelación del libro mayor. Si las transacciones marcadas contienen varias combinaciones de códigos de divisa, dimensiones y perfiles de registro, se crea una línea de diario independiente para cada combinación.
- El tercer tipo de línea del diario contiene información de cancelación del libro mayor para los impuestos sobre las ventas. Esta línea de diario se crea solo si se ha seleccionado **Impuestos independientes** en la página **Parámetros de clientes**. Si las transacciones marcadas contienen varias combinaciones de cuentas a pagar de impuestos, dimensiones y códigos de impuestos, se crea una línea de diario independiente para cada combinación. La transacción de cancelación se crea en la divisa de la transacción. Para obtener más información, consulte Crear un diario de cancelación para un cliente.

## <a name="process-nsf-payments"></a>Procesar pagos NSF

Puede procesar pagos NSF seleccionando **Pago NSF** en la página **Cobros**. Al hacer clic en este botón, se cancela el pago. Si se aplica una cuota NSF para el cliente, se creará una transacción de cargos en un diario de pagos. El importe de la cuota se basa en la configuración de los cargos automáticos. Los cargos automáticos que se aplican a los pagos NSF se especifican en función del grupo de cargos seleccionado en la página **Cuentas bancarias** para la cuenta bancaria afectada.

## <a name="additional-resources"></a>Recursos adicionales

[Configuración de parámetros de la administración de crédito de cliente](./cm-credit-mgmt-setup.md)

[Información de configuración de la administración de crédito de cliente](./cm-setup-information.md)

[Agregar información de administración de crédito para un cliente](./cm-add-credit-mgmt-information-customer.md)

[Grupos de crédito del cliente](./cm-customer-credit-groups.md)

[Ajustes de límite de crédito de cliente](./cm-credit-limit-adjustments.md)

[Retenciones de crédito para pedidos de ventas](./cm-sales-order-credit-holds.md)

[Tareas periódicas de administración de crédito de cliente](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

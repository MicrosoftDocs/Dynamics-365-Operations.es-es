---
title: Parámetros de registro de Commerce
description: Este artículo describe los parámetros que son específicos para el registro de transacciones financieras y físicas en Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 10ea650b7c5c0cad7e1a3d7556c073aecef06036
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887123"
---
# <a name="commerce-posting-parameters"></a>Parámetros de registro de Commerce

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artículo describe los parámetros que son específicos para el registro de transacciones financieras y físicas en Microsoft Dynamics 365 Commerce. Los parámetros de registro de Commerce se encuentran en la sede de Commerce en **Retail y Commerce \> Configuración de la sede \> Parámetros \> Parámetros de Commerce \> Registro**.

## <a name="periodic-discount-parameters"></a>Parámetros de descuento periódicos

La siguiente tabla enumera los parámetros de descuento periódico que son específicos para la contabilización de las operaciones financieras y físicas.

| Parámetro | Description |
|-----------|-------------|
| Registrar descuento periódico | Esta opción controla si las ofertas periódicas se contabilizan en las cuentas del libro mayor. Entre los descuentos periódicos se incluyen descuentos combinados, descuentos de cantidad y ofertas de descuento. Cuando este parámetro está habilitado, se pueden establecer campos adicionales en la sección **Descuentos periódicos**. |
| Tipo de cuenta contable | <p>Seleccione el tipo de cuenta contable que se utiliza para registrar descuentos periódicos:</p><ul><li>**Estándar** – El sistema no utiliza los campos relacionados con descuentos en esta página. En su lugar, utiliza las cuentas que están definidas en la página **Registro** en la sede de Commerce (**Gestión del inventario \> Configuración \> Registro \> Formularios de registro**).</li><li>**Periódico** – El sistema utiliza las cuentas de descuento de Commerce que se especifican en los campos relacionados con el descuento en esta página. Si selecciona esta opción, debe especificar la contabilidad general (GL) para cada tipo de propuesta (descuento, descuento combinado, cantidad y umbral). Cuando configura cada descuento, puede definir una cuenta. Cuando se utiliza la característica de registro de cuentas de descuento en la página de configuración de descuentos, se realiza una entrada de débito y una entrada de crédito adicionales para reclasificar el registro de descuentos de la cuenta del libro mayor de descuentos de Commerce a la cuenta del libro mayor de descuentos. Para obtener más información, consulte [Descuentos de Retail](retail-discounts-overview.md).</li></ul> |
| Registrar descuento por código de información | Esta opción ya no se usa en la solución estándar de Commerce y quedará obsoleta. |
| Registrar descuento periódico para pedidos | Esta opción controla si se registran descuentos periódicos comerciales en el libro mayor para pedidos de clientes y pedidos de centro de llamada. |

## <a name="inventory-update-parameters"></a>Parámetros de actualización de inventario

La siguiente tabla enumera los parámetros de actualización de inventario que son específicos para la contabilización de las operaciones financieras y físicas.

| Parámetro | Description |
|-----------|-------------|
| Usar ID de lote predeterminado cuando no se encuentren números de lote | Esta opción controla si se utiliza un ID de lote por defecto para los artículos habilitados para lote si no se encuentran los números de lote y se permite el inventario negativo. |
| ID. de lote predeterminado | El número de lote que se utilizará si no se encuentran los números de lote de los artículos y el parámetro **Usar ID de lote predeterminado cuando no se encuentren números de lote** está activado. |

## <a name="aggregation-parameters"></a>Parámetros de agregación

La siguiente tabla enumera los parámetros de agregación de inventario que son específicos para la contabilización de las operaciones financieras y físicas.

| Parámetro | Description |
|-----------|-------------|
| Ingreso seguro | Habilite este parámetro para agregar todas las transacciones durante el registro del extracto y cree una sola línea en el diario para la publicación en lugar de una línea separada para cada entrega. |
| Ingreso bancario | Habilite este parámetro para agregar todas las transacciones durante el registro del extracto y cree una sola línea en el diario para la publicación en lugar de una línea separada para cada entrega. |
| Transacciones de ventas | Habilite este parámetro para consolidar las transacciones como parte del proceso de registro del extracto de transacciones. Le recomendamos que habilite este parámetro. Antes se llamaba **Transacciones de asiento**. |
| No agregar devoluciones | Si esta opción está seleccionada, cada transacción de devolución se registrará como pedido de ventas independiente al registrar un extracto comercial. |

## <a name="batch-processing-parameters"></a>Parámetros de procesamiento de lotes

La siguiente tabla enumera los parámetros de procesamiento de lotes que son específicos para la contabilización de las operaciones financieras y físicas.

| Parámetro | Description |
|-----------|-------------|
| Número máximo de extractos paralelos | Este campo define el número de tareas por lotes que se utilizan para registrar varios extractos. |
| Subproceso máximo para el procesamiento de pedidos por extracto | Este campo representa el número máximo de subprocesos que el trabajo por lotes de registro de extractos utiliza para crear y facturar pedidos de cliente para un solo extracto. El número total de subprocesos que se utilizan en el proceso de registro del extracto se calcula multiplicando el valor de este parámetro por el valor del parámetro **Número máximo de registros paralelos del extracto** . Si el valor del parámetro es demasiado alto, puede tener un impacto negativo en el rendimiento del proceso de registro del extracto. |
| Líneas de transacción máximas incluidas en la agregación | Este campo define el número de líneas de transacción que se incluyen en una única transacción agregada antes de que se cree una nueva transacción. Las transacciones agregadas se crean en función de diversos criterios de agregación, como cliente, fecha de negocio o dimensiones financieras. Tenga en cuenta que las líneas de una sola transacción no se dividirán entre diversas transacciones agregadas. Por lo tanto, es posible que el número de líneas en una transacción agregada sean ligeramente mayores o menores basadas en factores como número de productos únicos. |
| Número máximo de subprocesos para validar transacciones de la tienda | Este campo define el número máximo de subprocesos que se usan para validar transacciones. La validación de las transacciones es un paso necesario que debe aparecer antes de que las transacciones se pueden añadir a los extractos. También debe definir un producto de tarjeta regalo en la ficha desplegable **Tarjeta de regalo** en la pestaña **Registro** de la página **Parámetros de Commerce**, incluso si la organización no utiliza tarjetas de regalo. |

La siguiente tabla enumera los valores recomendados para los parámetros en la tabla anterior. Estos valores deben probarse y adaptarse a la configuración de implementación y la infraestructura disponible. Los valores que superen los valores recomendados puede afectar negativamente a otros procesos por lotes y debe validarse.

| Parámetro | Valor recomendado | Detalles |
|-----------|-------------------|---------|
| Número máximo de extractos registrados en paralelo | <p>Establezca este parámetro en el número de tareas por lotes que están disponibles para el grupo de lotes que está ejecutando el trabajo **Declaración**.</p><p>**Regla general:** Multiplique la cantidad de servidores virtuales de Application Object Server (AOS) por la cantidad de tareas por lotes que están disponibles por servidor virtual AOS.</p> | Este parámetro no es aplicable cuando la característica **Estados de cuenta minoristas: alimentación por goteo** está habilitada. |
| Subproceso máximo para el procesamiento de pedidos por extracto | Comience a probar los valores en **4**. Por lo general, el valor no debe exceder **8**. | Este parámetro define el número de subprocesos que se utilizan para crear y publicar pedidos de venta. Representa el número de hilos que están disponibles para publicar por declaración. |
| Líneas de transacción máximas incluidas en la agregación | Comience a probar los valores en **1000**. Según la configuración de la sede de Commerce, los pedidos más pequeños pueden ser más beneficiosos para el rendimiento. | Este parámetro definne el número de líneas que se incluyen en cada orden de venta durante la contabilización del estado de cuenta. Después de alcanzar este número, las líneas se dividirán en un nuevo pedido. El número de líneas de venta no será exactamente igual al número especificado, dado que la división se produce en el nivel de pedido de venta. Sin embargo, el número estará cerca del número que se establece. Este parámetro se usa para generar órdenes de venta para transacciones minoristas que no tienen un cliente designado. |
| Número máximo de subprocesos para validar transacciones de la tienda | Le recomendamos que establezca este parámetro en **4** y que solo lo aumente si no consigue un rendimiento aceptable. La cantidad de subprocesos que utiliza este proceso no puede exceder la cantidad de procesadores que están disponibles para el servidor por lotes. Si la cantidad de subprocesos es demasiado alta, es posible que se vean afectados otros procesos por lotes. | Este parámetro controla la cantidad de transacciones que se pueden validar al mismo tiempo para una tienda determinada. |

> [!NOTE]
> Todos los valores y parámetros asociados a los registros de extracto y que se definen en las tiendas y en la página **Parámetros de Commerce**, son aplicables a la función mejorada del registro de extractos.

## <a name="invoice-parameters"></a>Parámetros de factura

La siguiente tabla enumera los parámetros de factura de inventario que son específicos para la contabilización de las operaciones financieras y físicas.

| Parámetro | Description |
|-----------|-------------|
| Nombre del diario | El nombre del diario de pagos que se usa cuando se crean diarios de pagos de clientes para pagos de pedidos de ventas. Esta configuración se aplica a todos los pagos de pedidos que se registran para pedidos de puntos de venta (PDV), centros de llamadas y canales de comercio electrónico. |
| Nombre de la cuenta | El nombre de la cuenta de pago. |
| Priorizar dimensiones del método de pago | Cuando este indicador está activado, los diarios de pago dan prioridad a las dimensiones del método de pago en lugar de las dimensiones de la tienda. |
| Comportamiento de cálculo de impuestos | Este parámetro especifica el comportamiento cuando se facturan los pedidos de venta que se crean durante la contabilización del estado de cuenta:<ul><li>**Recalcular** – Calcular impuestos de nuevo.</li><li> **no recalcular** – Utilzar los importes de impuestos que se calculan en PDV.</li></ul> |
| Nombre del diario | El nombre del diario que se usa cuando se crea un diario de pago de cliente para reembolsos. Esta configuración se aplica a todos los pagos de pedidos que se registran para pedidos de PDV, centros de llamadas y canales de comercio electrónico. |

## <a name="statement-parameters"></a>Parámetros de extracto

La siguiente tabla enumera los parámetros de extracto que son específicos para la contabilización de las operaciones financieras y físicas.

| Parámetro | Description |
|-----------|-------------|
| Reservar inventario durante el cálculo | Cuando este parámetro está habilitado, el cálculo del estado de cuenta reserva inventario temporalmente hasta que se registra el estado de cuenta. Este parámetro está deshabilitado de forma predeterminada para ayudar a mejorar el rendimiento del cálculo de extractos. La información de inventario actualizada se puede calcular usando el trabajo por lotes **Registrar inventario**. Tenga en cuenta que el trabajo por lotes de inventario **Registrar** ya no se utiliza cuando está habilitada la creación de pedidos basada en [goteo](trickle-feed.md) para transacciones para tiendas minoristas. |
| Deshabilitar recuento obligatorio | Este indicador deshabilita el recuento durante el registro en la sede centra de Commercel. |
| Recalcular las dimensiones financieras en error | Cuando este parámetro está habilitado, las dimensiones financieras pueden ser reevaluadas en contabilizaciones de extractos posteriores si la contabilización de extractos falla. |
| Usar las dimensiones financieras de la tienda de la devolución | Cuando este parámetro está habilitado, se pueden crear pedidos de venta de devolución vinculadas que usan las dimensiones financieras de la tienda en lugar de las dimensiones financieras de la transacción original. |
| Desvincular devoluciones | Cuando este parámetro está habilitado, el extracto puede crear devoluciones de ventas no contabilizadas como devoluciones ciegas. Este parámetro está deshabilitado de manera predeterminada y le recomendamos que lo mantenga deshabilitado. |
| Deshabilitar el registro de la diferencia de redondeo | Este parámetro desactiva el registro de la diferencia de redondeo entre el pago de una operación y el importe bruto durante el procesamiento de los pagos. |
| Liquidar automáticamente depósitos de cuenta | Cuando este parámetro está habilitado, los depósitos de clientes que se contabilizan durante el registro de extractos minoristas se liquidan contra las transacciones abiertas de los clientes. |
| Habilite y utilice la conciliación de gestión de efectivo desde el PDV | Cuando este parámetro está habilitado, la conciliación de la administración de efectivo se realiza en PDV y los valores se transfieren al registro del informe financiero minorista para crear líneas de extractos. |
| Nivel de detalle de asiento contable | Este parámetro define el nivel de detalle que se incluye en el asiento del libro mayor para transacciones seleccionadas que se originan en PDV. Los tipos de transacciones incluyen ingresos, gastos y descuentos. Para los descuentos, este parámetro se considera solo cuando el número de cuenta para un descuento periódico y el número de cuenta para un descuento regular no son iguales. A menos que se requieran detalles, **Resumen** es el valor recomendado para estos registros. Cuando se define el registro a nivel de resumen, **TransactionDiscountTrans.RecID** no se rellenará. En el lanzamiento de la versión 10.0.27 de Commerce, se cambió el nombre de este indicador y se movió. Anteriormente se llamaba **Nivel de detalle** y estaba en la sección **Actualización de inventario**. |

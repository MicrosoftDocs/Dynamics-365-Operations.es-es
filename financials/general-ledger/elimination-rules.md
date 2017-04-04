---
title: "Reglas de eliminación"
description: "Este tema proporciona información acerca de las reglas de eliminación y varias opciones para informar sobre eliminaciones."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: db4b05bc55d735513d7580ca5908a1e84eb760c6
ms.openlocfilehash: 152b63fdfc78b3c4e79b93340d18c5cf69257024
ms.lasthandoff: 03/31/2017


---

# <a name="elimination-rules"></a>Reglas de eliminación

Este tema proporciona información acerca de las reglas de eliminación y varias opciones para informar sobre eliminaciones.

Las transacciones de eliminación se requieren cuando una entidad jurídica trabaja con una o más entidades jurídicas subsidiarias y usa informes financieros consolidados. Los resultados financieros consolidados deben incluir solo las transacciones que tienen lugar entre la organización consolidada y otras entidades fuera de esas organizaciones. Por lo tanto, las transacciones entre entidades jurídicas que forman parte de la misma organización se deben quitar, eliminar, la contabilidad general, por lo que de ellas no aparecen en los informes financieros. Hay varias formas de informar sobre eliminaciones:

-   Se puede crear una regla de eliminación y procesar en una empresa de consolidación o de eliminación.
-   Se pueden usar informes financieros para mostrar las dimensiones y las cuentas de eliminaciones en una fila o una columna específica.
-   Se puede usar una entidad jurídica independiente para registrar entradas de la transacciones manuales para realizar un seguimiento de las eliminaciones.

Este tema se centra en las reglas de eliminación que se procesan en una empresa de consolidación o de eliminación. Puede configurar reglas de eliminación para crear transacciones de eliminación en una entidad jurídica especificada como la entidad jurídica de destino para las eliminaciones. Esta entidad jurídica de destino se conoce como la entidad jurídica de eliminación. Se pueden generar diarios de eliminación o bien durante el proceso de consolidación o mediante una propuesta de diario de eliminación. Antes de configurar reglas de eliminación, debería familiarizarse con los términos siguientes:

-   **Entidad jurídica de origen**: la entidad jurídica en la que se han registrado los importes que se eliminaron.
-   **Entidad jurídica de destino**: la entidad jurídica en la que se registraron las reglas de eliminación.
-   **Entidad jurídica de eliminación**: la entidad jurídica especificada como la entidad jurídica de destino para las eliminaciones.
-   **Entidad jurídica consolidada**: la entidad jurídica creada para notificar los resultados financieros para un grupo de entidades jurídicas. Los datos financieros de las entidades jurídicas se consolidan en esta entidad jurídica y, a continuación, se crea un informe financiero mediante los datos combinados.

La tabla siguiente muestra los tipos de transacciones que podrían tener que eliminarse.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de transacción</th>
<th>ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Entrada de pedido de ventas y facturación (procesamiento centralizado)</td>
<td>Vende un producto a un cliente en nombre de otra entidad jurídica de la organización.</td>
</tr>
<tr class="even">
<td>Entrada de pedido de ventas (empresas vinculadas/relacionadas) y facturación</td>
<td>Vende productos entre entidades jurídicas de la organización.</td>
</tr>
<tr class="odd">
<td>Pedidos de compra (procesamiento centralizado)</td>
<td>Compra inventario, suministros, servicios, activos fijos y otros productos a un proveedor en nombre de otra entidad jurídica de la organización.</td>
</tr>
<tr class="even">
<td>Gestión de inventario (empresas vinculadas/relacionadas)</td>
<td><ul>
<li>Transfiere un inventario de la entidad jurídica a los activos fijos de otra entidad jurídica de la organización.</li>
<li>Transfiere un inventario de la entidad jurídica al inventario de otra entidad jurídica de la organización.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Seguimiento de inventario en tránsito</td>
<td>Transfiere los artículos entre almacenes de la misma entidad jurídica, pero en distintos sitios geográficos.</td>
</tr>
<tr class="even">
<td>Procesamiento de facturas centralizado de proveedores</td>
<td>Registra una factura en nombre de otra entidad jurídica de la organización.</td>
</tr>
<tr class="odd">
<td>Procesamiento de pagos centralizado de proveedores</td>
<td>Paga una factura en nombre de otra entidad jurídica de la organización.</td>
</tr>
<tr class="even">
<td>Gestión de efectivo y cartera (procesamiento centralizado)</td>
<td><ul>
<li>Procese pagos de impuestos, devoluciones de impuestos, cargos de intereses, préstamos, anticipos, pagos de dividendos y regalías o comisiones pagadas por adelantado.</li>
<li>Paga un gasto en nombre de otra entidad jurídica de la organización. La factura se especifica en los libros de la entidad jurídica de destino y debe realizar la liquidación entre entidades jurídicas. Por ejemplo, una entidad jurídica paga el informe de gastos de un empleado en otra entidad jurídica. En este caso, el informe de gastos del empleado tiene gastos relacionados con otra entidad jurídica.</li>
<li>Transfiere efectivo desde una entidad jurídica a otra de su organización.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Clientes (procesamiento centralizado)</td>
<td>Recibe efectivo para la factura de cliente de otra entidad jurídica, y almacena el cheque en la cuenta bancaria de esa entidad jurídica.</td>
</tr>
<tr class="even">
<td>Nómina (procesamiento centralizado, empresas vinculadas/dentro de la empresa)</td>
<td><ul>
<li>Paga la nómina de otra entidad jurídica. Por ejemplo, una entidad jurídica paga su propia nómina a sus empleados, pero cobra el trabajo que un empleado realizó a otra entidad jurídica durante el período de pago. O bien, un empleado trabajó a tiempo parcial para la entidad jurídica A y a tiempo parcial para la entidad jurídica B, y las prestaciones se aplican para todo el salario. En estos casos, el sueldo del empleado incluye el sueldo de ambas entidades jurídicas. No sólo se registran los salarios, sino que también se registran los impuestos, las prestaciones, las deducciones y las provisiones de los salarios.</li>
<li>Transfiere mano de obra de un departamento o división a otro.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Activos fijos (empresas vinculadas/dentro de la empresa)</td>
<td>Transfiere activos fijos a los activos fijos o al inventario de otra entidad jurídica.</td>
</tr>
<tr class="even">
<td>Asignaciones (empresas vinculadas/dentro de la empresa)</td>
<td>Procesa las asignaciones corporativas. Las asignaciones son actividades a cualquier cuenta asignada, independientemente del módulo de origen.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>ejemplo
Su entidad jurídica, entidad jurídica A, vende widgets a otra entidad jurídica de su organización, entidad jurídica B. En el ejemplo siguiente se muestra cómo las transacciones que tienen lugar entre las dos entidades jurídicas pueden tener que ser eliminadas:

-   La entidad jurídica A vende un widget que cuesta 10,00 euros a la entidad jurídica B por 10,00 euros.
-   La entidad jurídica A vende un widget que cuesta 10,00 euros a la entidad jurídica B por 10,00 euros más 2 euros en gastos de envío reales.
-   La entidad jurídica A vende un widget que cuesta 10,00 euros a la entidad jurídica B por 15,00 euros y reconoce un margen para la venta.
-   La entidad jurídica A vende un widget que cuesta 10,00 euros a la entidad jurídica B por 15,00 euros y reconoce la mitad del margen para la venta. La entidad jurídica B reconoce la otra mitad del margen para la venta. Por lo tanto, se dividen los ingresos. Los ingresos divididos ofrecen un incentivo para realizar el pedido a otra entidad jurídica de la organización en lugar de a una organización externa.

Todas estas transacciones crean transacciones de empresas vinculadas a las cuentas de destinatario de pago y remitente de pago. Además, estas transacciones podrían incluir importes de marcado y desmarcado de precios cuando el importe de la venta de empresas vinculadas no es igual al coste de los bienes vendidos.

## <a name="set-up-elimination-rules"></a>Configurar reglas de eliminación
Al configurar reglas de eliminación de Dynamics 365 para las operaciones, se recomienda que cree una dimensión financiera específicamente para la eliminación. La mayoría del nombre de clientes él socio comercial o parte similar. Si decide no utilizar una dimensión financiera, asegúrese de tener cuentas principales que son específicas para las transacciones de empresas vinculadas únicamente. 

La configuración de eliminaciones se encuentra en el área de configuración del módulo de las consolidaciones. Después de especificar una descripción para la regla, debe seleccionar la empresa a la que el diario de eliminaciones registrará. Esta debe ser una empresa que ** uso para el proceso financiero de eliminación ** ha seleccionado en la configuración de la entidad jurídica. 

Puede establecer una fecha en la que la regla de eliminación se haga efectiva y cuando haya caducado, si es necesario. Debe establecer ** activo ** ** Sí ** si desea que esté disponible en el proceso de propuesta de eliminación. Seleccione un nombre de diario del que tiene un tipo ** ** eliminación.

Después de definir los fundamentos, puede definir las reglas de procesamiento reales haciendo clic en ** las líneas **. Existen dos opciones para las eliminaciones, se elimina la cantidad de cambio neto o definiendo un importe fijo. 

Seleccione la cuenta de origen. Puede usar un asterisco (\*) como comodín. Por ejemplo, 1\* seleccionar todas las cuentas que comienzan por 1 como un origen de datos para la asignación. 

Una vez haya seleccionado las cuentas de origen, ** especificación de la cuenta ** determina la cuenta de la empresa de destino que se usa. Seleccione ** origen ** si desea usar la misma cuenta principal definida en ** origen ** la cuenta. Si selecciona ** definido por el usuario **, deberá especificar una cuenta de destino. 

La especificación de la dimensión actúa de la misma manera. Si selecciona ** ** origen, usará las mismas dimensiones en la empresa de destino que la empresa de origen. Si selecciona ** definido por el usuario **, deberá especificar las dimensiones de la empresa de destino haciendo clic en ** las dimensiones de destino ** el elemento de menú. 

Dimensiones seleccionar de origen y las dimensiones financieras y los valores que se usan como origen de la eliminación.

## <a name="process-elimination-transactions"></a>Procesar transacciones de eliminación
Hay dos maneras de procesar transacciones de eliminación, durante el proceso en línea de la consolidación o creando un diario de eliminaciones y la ejecución de la propuesta de eliminación ha procesado. Enfoques de esta sección de crear el diario y ejecución que la eliminación ha procesado. 

En una empresa define como empresa de eliminación, seleccione ** diario de eliminaciones ** en el módulo de las consolidaciones. Una vez haya seleccionado el nombre de diario, haga clic en ** las líneas **. Puede ejecutar la propuesta seleccionando ** las propuestas ** el menú y después seleccionándolo ** propuesta de eliminación **.

Seleccione la empresa que es el origen de los datos consolidados, y después seleccione la regla que desea procesar. Especifique una fecha inicial para iniciar la búsqueda para los importes de eliminación, y una fecha final para finalizar la fecha de la búsqueda para los importes de eliminación. ** Fecha de registro de contabilidad general ** el campo es la fecha utilizada para registrar el diario en la contabilidad general. Después de hacer clic en ** éste **, puede revisar los importes y registrar el diario.



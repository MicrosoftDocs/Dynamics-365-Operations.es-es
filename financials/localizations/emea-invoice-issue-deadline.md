---
title: "Fecha de límite de emisión de factura"
description: "Este artículo explica cómo configurar parámetros para calcular las fechas límite para emitir facturas de cliente y facturas de proveedor en la Unión Europea (UE)."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustParameters, LedgerInvoiceIssueDueDateSetup_W
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10923
ms.assetid: 64ea3343-df94-4a52-b839-6328c8a282bd
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Iceland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 6121be0dd02659e4e8466b0c1381678be64fefc2
ms.lasthandoff: 03/31/2017


---

# <a name="invoice-issue-deadline"></a>Fecha de límite de emisión de factura

Este artículo explica cómo configurar parámetros para calcular las fechas límite para emitir facturas de cliente y facturas de proveedor en la Unión Europea (UE).

La Directiva de la Unión Europea (UE) 45/2010 y otras directorias requieren que los envíos dentro de la UE (envíos en el interior de la Unión Europea) se deben facturar el día quince del mes después de que se realice la entrega o antes de esta fecha. Al mismo tiempo, cada país de la UE puede tener diferentes plazos de facturación para entregas nacionales. La función Fecha de límite de emisión de factura le permite alinear el intervalo de fechas con el tipo de país o región. A continuación, para todos los envíos a y desde un país o región de un tipo concreto, la fecha límite de emisión de la factura se calcula mediante reglas que se establecen en el intervalo de fechas especificado. Además, puede obtener todos los albaranes que tienen una fecha límite de emisión de facturas, filtrar por la fecha límite de emisión de facturas durante la facturación de ventas periódicas y controlar la fecha de emisión de la factura de ventas durante el registro de la factura. Puede configurar un código de intervalo de fechas y, a continuación, configurar una regla de cálculo para la fecha de emisión de factura asignando el código de intervalo de fechas a un país o a un tipo de región. La regla de cálculo se usa para calcular la fecha límite para emitir facturas para las siguientes transacciones:

-   Envíos dentro de la UE
-   Envíos nacionales dentro de un estado miembro de la UE

También puede configurar controles de fecha para ayudar a garantizar que las facturas de cliente y las notas de abono para las transacciones de cliente se generan dentro del período especificado una vez que se realice la entrega.

## <a name="prerequisites"></a>Requisitos previos
La tabla siguiente muestra los requisitos previos que deben cumplirse antes de que pueda usar la función de la fecha límite de emisión de la factura.

| Categoría            | Requisito previo                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| País o región      | La dirección principal de la entidad jurídica debe estar en un estado miembro de la Unión Europea.                                                                                                                                                                                                                                                                                                                    |
| Tareas de configuración relacionada | En la página **Intervalos de fechas**, configure un intervalo de fechas que se usa para calcular la fecha límite de emisión de la factura. Haga clic en (** contabilidad general ** &gt; ** configuración contable ** &gt; ** intervalos de fechas **). En ** los parámetros de comercio exterior ** la página, configurar las propiedades del comercio exterior para los diferentes países/regiones. Haga clic en (Tax ** ** &gt; ** configuración ** &gt; ** comercio exterior ** &gt; ** parámetros de comercio exterior **). |

## <a name="invoice-issue-due-date-calculation-rule"></a>Regla de cálculo de fechas límites de emisión de facturas
Use la página **Configurar cálculo para la fecha límite de emisión de la factura** para configurar una regla de cálculo de fechas límite de emisión de facturas asignando un código de intervalo de fechas a un país o a un tipo de región.

## <a name="date-control-parameters-for-customer-invoices-and-credit-notes"></a>Parámetros de control de fecha para facturas de cliente y notas de abono
También puede configurar parámetros de control para ayudar a garantizar que las facturas de cliente y las notas de abono para las transacciones de cliente se generan dentro del período especificado una vez que se realice la entrega. Encontrará estos parámetros en el área **Control de fechas de factura** de la página **Parámetros de clientes**.

## <a name="example"></a>Ejemplo
Para configurar Microsoft Dynamics 365 para que las operaciones calculen las fechas de vencimiento del problema de factura de envíos en el interior de la UE en el día diez quinto día del mes de que se entregue la fuente, cree un código de intervalo de fechas y una regla de cálculo con los siguientes valores.

### <a name="date-interval-code"></a>Código de intervalo de fechas

| Campo                                                           | Valor                           |
|-----------------------------------------------------------------|---------------------------------|
| Código de intervalo de fechas                                              | 15-NM                           |
| Descripción                                                     | Día quince del mes siguiente |
| Antes (en el grupo de campos **Fecha final**)                         | Mes                           |
| Inicio/Fin (en el grupo de campos **Fecha final**)                      | Fin                             |
| +/- (en el grupo de campos **Fecha final**)                            | 15                              |
| Días, meses, años o períodos (en el grupo de campos **Fecha final**) | Días                            |

### <a name="invoice-issue-due-date-calculation-rule"></a>Regla de cálculo de fechas límites de emisión de facturas

| Campo               | Valor                                                     |
|---------------------|-----------------------------------------------------------|
| Tipo de país/región | **UE**                                                    |
| Fecha inicial          | Especifique la fecha en que la línea de configuración actual entra en vigor. |
| Código de intervalo de fechas  | **15-NM**                                                 |

## <a name="next-steps"></a>Pasos siguientes
Una vez que haya terminado de configurar los parámetros para calcular las fechas límite de emisión de la factura, puede crear y registrar las siguientes transacciones para calcular y actualizar automáticamente las fechas límite para emitir facturas:

-   **Pedidos de ventas**: cuando se crea un pedido de ventas y se registra un albarán, la fecha límite para emitir la factura se calcula y se actualiza en el albarán. La fecha de vencimiento se calcula en función del intervalo de fechas que está asociada al país/región que se especifica en la dirección de entrega del pedido de ventas. Después de registrar el albarán, puede comprobar la fecha de vencimiento de emisión de la factura en ** facturar la fecha de vencimiento de emisión ** los puestos en ** diario de albaranes ** la página. ** Haga clic en (Ventas y marketing ** &gt; ** pedido de ventas ** &gt; ** envío del pedido ** &gt; ** albarán **). Puede ver todos los albaranes que no se han facturado, y sus fechas de vencimiento de emisión de la factura, en ** los albaranes no facturados ** la página. ** Haga clic en (Ventas y marketing ** &gt; ** pedido de ventas ** &gt; ** envío del pedido ** &gt; ** albaranes no facturados **).
-   **Pedidos de compra**: cuando se crea un pedido de compra y se registra una recepción de producto, la fecha límite para emitir la factura se calcula y se actualiza en la recepción de producto. La fecha límite se calcula en función del intervalo de fechas que está asociado al país o región especificado en la dirección principal del proveedor. Después de registrar la recepción de producto, puede comprobar la fecha límite de emisión de la factura en el campo **Fecha de límite de emisión de factura** de la página **Diario de recepciones de producto**. Haga clic en (** Adquisición y abastecimiento ** &gt; ** pedidos de compra ** &gt; ** recibiendo productos ** &gt; ** recepción de producto **). Puede ver todas las recepciones de producto que no se han facturado, y sus fechas de vencimiento de emisión de la factura, en ** las recepciones de producto no facturadas ** la página. Haga clic en (** Adquisición y abastecimiento ** &gt; ** pedidos de compra ** &gt; ** recibiendo productos ** &gt; ** recepciones de producto no facturadas **).

## <a name="technical-information-for-system-administrators"></a>Información técnica para administradores del sistema
Si no tiene acceso a las páginas que se usan para completar las tareas mencionadas en este artículo, póngase en contacto con el administrador del sistema y proporcione la información que se indica en la tabla siguiente.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Requisito previo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration Keys</td>
<td>Haga <strong>Administración del sistema</strong> &gt; <strong>Configuración</strong> &gt; <strong>Autorización</strong> &gt; <strong>Configuración de licencia</strong>clic en. Haga clic en la clave de configuración <strong>Contabilidad general</strong>.</td>
</tr>
<tr class="even">
<td>Roles y responsabilidades de seguridad</td>
<td>Para realizar esta tarea, debe ser miembro de un rol de seguridad que incluya las siguientes responsabilidades:
<ul>
<li><strong>CustInvoiceInvoiceAndCashProcessEnable</strong> (Habilitar el proceso de facturación y efectivo)</li>
<li><strong>VendInvoiceInvoicePaymentProcessEnable</strong> (Habilitar el proceso de facturación y pago)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Roles de seguridad y privilegios</td>
<td>Para realizar esta tarea, debe ser miembro de un rol de seguridad que incluya los siguientes privilegios:
<ul>
<li><strong>CustPackingSlipJournalView</strong> (Ver albaranes de ventas)</li>
<li><strong>VendPackingSlipJournalView</strong> (Ver diario de recepción de producto de pedido de compra)</li>
<li><strong>LedgerInvoiceIssueDueDateSetupMaintain_W</strong> (Calcular fechas límites de emisión de facturas)</li>
</ul></td>
</tr>
</tbody>
</table>





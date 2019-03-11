---
title: Facturación del proyecto
description: Este artículo proporciona una visión general de la facturación del proyecto para Proyectos de tiempo y material y Proyectos de precio fijo. Incluye información acerca de las propuestas de factura (facturas preliminares), control de facturas, facturación a cuenta, facturación de proveedor y notas de abono.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjInvoiceCashFlow, ProjInvoiceControl, ProjInvoiceListPage, ProjInvoiceProposalDetail, ProjInvoiceProposalListPage
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23111
ms.assetid: 1812d6f2-8b34-4258-8f5f-dcf12281547f
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5dd51e442479a05ce715fe91ebab0c99df9a8b6f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "346327"
---
# <a name="project-invoicing"></a>Facturación del proyecto

[!include [banner](../includes/banner.md)]

Este artículo proporciona una visión general de la facturación del proyecto para Proyectos de tiempo y material y Proyectos de precio fijo. Incluye información acerca de las propuestas de factura (facturas preliminares), control de facturas, facturación a cuenta, facturación de proveedor y notas de abono.

El tipo de proyecto determina el procedimiento de facturación que se debe aplicar. Solo se pueden facturar los dos tipos de proyecto externo, Tiempo y material y Precio fijo. Los proyectos de tiempo y material y los proyectos de precio fijo están siempre vinculados a un contrato de proyecto.

-   **Proyectos de precio fijo**: el importe de la factura del cliente se basa en las programaciones de facturación. La facturación se realiza mediante una configuración a cuenta, que también se conoce como programación de facturación. Los proyectos de precio fijo se pueden facturar por proyecto o por contrato de proyecto.
-   **Proyectos de tiempo y material**: el importe de la factura del cliente se basa en las líneas de transacción que se especifican en proyectos. Las transacciones se pueden facturar por proyecto o por contrato de proyecto.

Hay tres maneras de adjuntar proyectos de tiempo y material y proyectos de precio fijo a los proyectos de factura:

-   **Facturación a cuenta**: los proyectos de tiempo y material y los de precio fijo se pueden facturar a cuenta. Son necesarios dos tipos de configuración a cuenta, uno para tipo de proyecto.
-   **Facturación en la sección periódica**: mediante las funciones periódicas, las transacciones se pueden facturar en los proyectos. Las funciones periódicas proporcionan una visión general de las transacciones que se deben facturar.
-   **Mediante el uso de notas de abono en la facturación**: se puede crear una nota de abono para los proyectos de tiempo y material y para los proyectos de precio fijo.

## <a name="invoice-proposals"></a>Propuestas de facturas
Antes de crear una factura de cliente para un proyecto, puede crear una factura preliminar o una propuesta de factura. En una propuesta de factura, puede seleccionar transacciones de proyecto para incluirlas en una factura de proyecto. A continuación, puede revisar los detalles de la factura antes de registrar la factura del proyecto y enviarla al cliente o a otra fuente de financiación.

### <a name="creating-invoice-proposals"></a>Creación de propuestas de factura

Puede crear propuestas de factura manualmente seleccionando una lista de transacciones para un proyecto especificado. También puede configurar reglas de facturación que especifiquen cuándo se debe crear automáticamente una propuesta de factura. Por ejemplo, puede crear una regla de facturación para crear una propuesta de factura cuando el trabajo de un proyecto esté completado al 25 por ciento, 50 por ciento, 75 por ciento y 100 por ciento. 

Puede crear propuestas de factura para las transacciones siguientes:

-   Horas, gastos y otras transacciones de proyecto
-   Importes retenidos por los clientes en las facturas de proyecto anteriores
-   Notas de abono
-   Importes que un cliente le pagó antes del inicio de un proyecto

Puede crear transacciones de gastos en una propuesta de factura. También puede modificar el precio de ventas en horas, gastos, artículos y transacciones de gastos. Cuando se registra una propuesta de factura, los precios y las transacciones actualizadas se agregan a los informes de proyecto y al historial de la transacción. 

Para crear varias facturas de cliente para un proyecto, debe crear una propuesta de factura para cada factura. Por ejemplo, puede crear facturas basadas en el tipo de transacción. Para especificar horas en una factura de cliente y artículos en otra, debe crear propuestas de facturas independientes para transacciones por horas y transacciones de gastos. 

Si un proyecto tiene más de una fuente de financiación, puede crear una propuesta de factura independiente para cada fuente de financiación. En la página **Asignaciones de reglas de financiación**, puede definir el porcentaje del importe de la transacción para asignar a cada fuente de financiación y el origen para registrar diferencias de redondeo.

### <a name="creating-customer-invoices-from-invoice-proposals"></a>Crear facturas de cliente de propuestas de facturas

Después de crear y registrar una propuesta de factura, se crea automáticamente una factura de cliente para las transacciones incluidas en la propuesta de factura. 

Para poder registrar una propuesta de factura, puede agregarle transacciones o eliminarlas de ella. Por ejemplo, puede quitar las transacciones de gastos que se han registrado a un proyecto, pero no son imputables al cliente. 

Si la organización requiere que las propuestas de factura se revisen antes de registrarse, puede que la propuesta de factura se deba aprobar a través de un flujo de trabajo "Revisar propuestas de factura de proyecto" antes de registrarse.

## <a name="on-account-invoicing"></a>Facturación a cuenta
El importe que especifique para un proyecto en una factura a cuenta se basa en la sincronización, el porcentaje de finalización y otras condiciones de facturación que se especifican en el contrato del proyecto relacionado. El importe no se calcula en función de las horas, los artículos, los gastos o las tarifas que se publican en el proyecto. 

Debe crear una transacción a cuenta para un proyecto de tiempo y materiales o un proyecto de precio fijo para poder agregar la transacción a cuenta a una factura de proyecto. En la transacción a cuenta, especifique el importe para facturar a un cliente. Para crear una factura de proyecto para el importe, cree una factura preliminar (propuesta de factura). En la propuesta de factura, seleccione la transacción a cuenta. Puede revisar la información a cuenta en la propuesta de factura antes de crear una factura de proyecto para ella.

### <a name="fixed-price-projects"></a>Proyectos de precio fijo

Para proyectos de precio fijo, las transacciones a cuenta se basan en un hito acordado, la unidad de entrega o el acuerdo de facturación de progreso que se especifica en el contrato del proyecto. Se creará una línea para cada pago que se debe recibir del cliente del proyecto. No se necesitan ningunas deducciones.

### <a name="time-and-material-projects"></a>Proyectos de tiempo y material

Para proyectos de tiempo y material, puede facturar a un cliente u otra fuente de financiación para un importe de anticipo mediante una propuesta de factura a cuenta. Permite especificar transacciones a cuenta como una línea. Opcionalmente, puede especificar las líneas adicionales como deducciones para borrar cualquier pago por adelantado que el cliente ya haya realizado. Para crear líneas de deducción, coloque un signo menos delante del importe.

## <a name="invoice-control"></a>Control de factura
Puede usar el control de factura para realizar un seguimiento de las transacciones facturadas y no facturadas, y para analizar esas transacciones con los presupuestos para una vista de principio a fin de los proyectos desde la fase de presupuesto a la finalización. Puede ver qué transacciones se han cargado en un proyecto específico y qué líneas se han facturado. También puede ver transacciones individuales, de modo que pueda ajustarlas una vez registradas.

## <a name="invoicing-fixed-price-projects"></a>Facturación de proyectos de precio fijo
Para facturar un proyecto de precio fijo, debe definir una programación de facturación y completar el procedimiento de facturación.

### <a name="billing-schedule"></a>Programación de facturación

Las programaciones de facturación permiten facturar proyectos de precio fijo. La programación de facturación se define en términos de hitos del proyecto. Para cada hito, puede definir una fecha, una divisa de ventas, un precio de ventas y una actividad específicos. 

Por ejemplo, puede configurar la siguiente programación de facturación:

-   20 % al firmar el contrato de proyecto
-   30% con la primera entrega
-   15 % con la segunda entrega
-   35% con la entrega final.

### <a name="invoicing-procedure"></a>Procedimiento de facturación

Cuando los pagos por hito están listos para su facturación, se usa el procedimiento de facturación de importes a cuenta.

## <a name="vendor-invoicing"></a>Facturación de proveedor
Cuando solicita un artículo de un proveedor y asigna el artículo a un proyecto, la propiedad de línea seleccionada para la línea de pedido de compra de ese artículo determina si el artículo adquirido se factura a un cliente. Si configura las propiedades de línea predeterminadas, se mostrarán para el artículo en la línea del pedido de compra (Detalles de línea &gt; Proyecto &gt; Propiedad de línea). Hay dos formas de modificar la propiedad de línea:

-   Facturar al cliente del proyecto por el artículo: defina la propiedad de la línea en un valor imputable en el pedido de compra y, a continuación, facture al cliente con el método de facturación de proyecto correcto.
-   No facturar al cliente del proyecto por el artículo: no seleccione la propiedad de línea **Imputable** en la línea del pedido de compra para el artículo. A continuación puede facturar el pedido de compra, sin necesidad de tomar medidas adicionales.

## <a name="credit-notes"></a>Notas de abono
Cuando un importe de una factura de cliente tiene un valor negativo, la factura se clasifica como nota de abono. Cuando se imprime el documento, tiene el título "Nota de abono". 

Cuando se crea una nota de abono para abonar un importe facturado anteriormente, se debe seleccionar primero el importe facturado para la asignación de abono. A continuación, se debe crear una nota de abono mediante el mismo procedimiento usado para crear una factura de cliente corriente. En otras palabras, debe seleccionar las transacciones que se han registrado anteriormente en una factura de cliente y, a continuación, crear y registrar una propuesta de nota de abono. 

El mismo documento puede incluir transacciones seleccionadas para la asignación de abono, las transacciones de crédito y las transacciones que se han registrado. El documento se clasifica como una factura o una nota de abono, en función de si el importe total es positivo o negativo. 

Para abonar un importe facturado, se debe seleccionar primero el importe facturado para abonar y crear a continuación una nota de abono. Se debe crear una nota de abono mediante el mismo procedimiento usado para generar una factura de cliente. 

Puede crear una factura con un importe negativo, que se convierte en una factura que se clasifica como nota de abono. Para crear e imprimir una nota de abono, debe seleccionar las transacciones que se han registrado anteriormente para una factura de cliente y, a continuación, modificar las transacciones. A menos que la dirección principal de la entidad jurídica se encuentre en Alemania, la título de la factura será "Factura correctiva".




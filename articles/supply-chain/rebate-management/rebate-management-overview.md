---
title: Descripción general del módulo de gestión de devoluciones
description: Este tema proporciona una visión general del módulo de Gestión de devoluciones para Microsoft Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 826cee7b1e30020aec99f6148dd9ab16f126c417
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839134"
---
# <a name="rebate-management-module-overview"></a>Descripción general del módulo de gestión de devoluciones

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Puedes usar el módulo de **Gestión de devoluciones** módulo para crear contratos, tratos o acuerdos entre su empresa y sus clientes o proveedores, de modo que pueda calcular devoluciones, deducciones y regalías. La administración de devoluciones rastrea y mantiene las transacciones de devoluciones y deducciones en una ubicación central donde los usuarios pueden crearlas, revisarlas y procesarlas de manera efectiva.

La gestión de devoluciones respalda la creación, el mantenimiento y el procesamiento de *devoluciones*. Una devolución es devolver parte del precio de compra por parte de un vendedor o un comprador. Las devoluciones generalmente se basan en la compra de una cantidad o valor específico de bienes durante un período específico. A diferencia de los descuentos, las devoluciones se realizan después de que el monto de la compra se haya facturado por completo.

La gestión de devoluciones también admite *deducciones*. Una deducción es una compensación, una contraprestación o una tarifa que se paga por una licencia o el privilegio de usar propiedad intelectual como una marca, derechos de autor o patente, o por el privilegio de usar un recurso natural para un propósito como pesca, caza o minería. Las deducciones generalmente se calculan como un porcentaje de los ingresos o ganancias del uso realizado. Cuanto más se utiliza la propiedad intelectual o recurso natural, mayor es la deducción que se realiza.

Además, la gestión de devoluciones admite las *regalías* de cliente. Las regalías son pagos que una parte hace al licenciatario o franquiciado por el derecho a usar un activo.

La gestión de devoluciones le permite definir perfiles de contabilización para provisiones, devoluciones y cancelaciones. Además, las contabilizaciones se pueden definir para un cliente o proveedor específico. De esta manera, las ofertas que no se aplican a todos los escenarios de clientes o proveedores se pueden rastrear a través de contabilizaciones.

Las transacciones de devoluciones se generan automáticamente, según el método de cálculo seleccionado y programado en los trabajos por lotes. Además, puede configurar flujos de trabajo para administrar, revisar y aprobar acuerdos.

## <a name="basis-calculation"></a>Cálculo de base

Las devoluciones de clientes, las regalías de los clientes y las devoluciones de proveedores pueden utilizar una base diferente, según los requisitos de su negocio:

- Las devoluciones de clientes pueden basarse en pedidos de venta, notas de entrega o facturas.
- Las regalías de clientes pueden basarse en pedidos de venta, notas de entrega o facturas de pago.
- Las devoluciones de proveedores pueden basarse en órdenes de compra u órdenes de venta. Se pueden calcular en función de los productos que se compran al proveedor de devoluciones y se venden a los clientes a través de facturas de venta.

## <a name="flexible-calculations"></a>Cálculos flexibles

Los períodos de cálculo de devoluciones están disponibles tanto para ofertas de clientes como para ofertas de proveedores. Un período de cálculo define la duración del acuerdo, la frecuencia de cálculo y el período de cálculo. Las devoluciones se pueden acumular en función de las cantidades de pedidos de venta o los importes de productos calificados durante el período de devolución.

Para cada cálculo de acuerdo, se puede establecer cualquiera de los siguientes períodos:

- Factura
- Día
- Semana
- Mes
- Trimestre
- Año
- Período personalizado
- Cualquier múltiplo de cualquiera de los períodos enumerados anteriormente

El cálculo se puede aplicar a clientes y productos individuales, grupos de clientes y productos, o todos los clientes y productos. Las devoluciones que tienen varias líneas de detalles pueden tener diferentes rangos de fechas de calificación. Los períodos de provisión y reclamación pueden diferir. Por ejemplo, las provisiones se pueden procesar todos los días, mientras que las reclamaciones se procesan una vez al mes.

Las devoluciones se pueden configurar en función de muchos parámetros diferentes. Por ejemplo, se pueden configurar como un porcentaje, una tasa o una cantidad fija. Hay cuatro métodos de cálculo principales:

- Escalonado
- Acumulado
- Constante
- Valor total

Los resultados del cálculo de la devolución también se pueden reducir mediante otras devoluciones, dependiendo de si la devolución está configurada para calcular en función del importe neto.

En el lado del proveedor, las devoluciones pueden calcular el precio según una regla de primero en entrar, primero en salir (FIFO), el último precio de compra, el precio de compra promedio o el precio de venta.

## <a name="rebate-target-transactions"></a>Transacciones de devolución de destino

Los resultados que genera el acuerdo o la devolución pueden ser finanzas o artículos.

Los resultados financieros están determinados por el tipo de pago que se asigna al acuerdo desde el perfil de contabilización. Estos resultados pueden incluir diarios de deducción de clientes, facturas de servicios y facturas de proveedores. Para fines de auditoría, las transacciones de destino de devolución financiera incluyen una referencia al acuerdo de devolución de origen.

Las salidas de artículos crean un pedido de venta de artículos gratuitos para devoluciones de clientes y un pedido de compra para devoluciones de proveedores. Las transacciones de destino de devolución de artículos contienen opciones para determinar qué referencia de devolución se debe introducir en la orden de venta o en la orden de compra de artículos gratuitos.

## <a name="accurate-rebate-calculations"></a>Cálculos precisos de devoluciones

La combinación de las transacciones asociadas, la frecuencia de los cálculos, la base de cálculo y el método de cálculo que se selecciona determina la exactitud y precisión de los cálculos de devolución. Las provisiones de devoluciones se pueden utilizar para acumular valores contabilizados y reclamados.

Las provisiones se pueden gestionar diaria o mensualmente. Sin embargo, la funcionalidad puede asignar o pagar la devolución, o recibir el pago, en cualquier frecuencia definida. Los usuarios pueden ajustar fácilmente un plan o montos de pago en cualquier momento durante el pago.

Los usuarios ya no tienen que gestionar acuerdos o provisiones en dos pasos. Las provisiones y cancelaciones se contabilizan directamente en el libro mayor. Además, las notas de crédito se pueden crear automáticamente. Por lo tanto, existe una integración completa con proveedores y clientes. Durante el procesamiento, los cálculos consideran los descuentos de liquidación, las facturas pagadas, los descuentos comerciales y las notas de crédito existentes para garantizar que las cantidades y los valores se calculen con precisión.

Cuando se calculan las devoluciones, el proceso crea transacciones que se pueden revisar antes de que se produzca la contabilización. A continuación, se puede crear una transacción de diario, nota de crédito o débito. Un proceso separado contabiliza las transacciones de devolución y deducción. Se pueden obtener declaraciones de informes y listados de transacciones para garantizar el cumplimiento, la eficacia y la transparencia.

## <a name="guaranteed-royalty-payments"></a>Pagos de regalías garantizados

En la gestión de devoluciones, la generación automática de pagos permite gestionar las regalías de forma rápida y sencilla, incluso cuando se aplican los mínimos garantizados. 

## <a name="maximizing-spend-versus-rebates"></a>Maximizar el gasto frente a las devoluciones

Los proveedores y los productos se pueden agrupar por territorio, y se pueden proporcionar diferentes ofertas, según el país o la región de la transacción. Cuando los usuarios seleccionan productos, pueden definir los artículos que se incluyen y el número de artículos que se utilizarán en la liquidación de devoluciones.

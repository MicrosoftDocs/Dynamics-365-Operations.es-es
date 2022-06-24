---
title: Descripción general del módulo de gestión de devoluciones
description: Este artículo proporciona una visión general del módulo de Gestión de devoluciones para Microsoft Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: cfba391536559ed3a967d0aafe2e352486777dda
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873648"
---
# <a name="rebate-management-module-overview"></a>Descripción general del módulo de gestión de devoluciones

[!include [banner](../includes/banner.md)]

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

En el lado del proveedor, las devoluciones basadsa en los pedidos de ventas pueden calcular el precio según una regla de primero en entrar, primero en salir (FIFO), el último precio de compra, el precio de compra promedio o el precio de venta.

## <a name="rebate-target-transactions"></a>Transacciones de devolución de destino

Los resultados que genera el acuerdo o la devolución pueden ser finanzas o artículos.

Los resultados financieros están determinados por el tipo de pago que se asigna al acuerdo desde el perfil de contabilización. Estos resultados pueden incluir diarios de deducción de clientes, facturas de servicios y facturas de proveedores. Para fines de auditoría, las transacciones de destino de devolución financiera incluyen una referencia al acuerdo de devolución de origen.

Las salidas de artículos crean un pedido de venta de artículos gratuitos para devoluciones de clientes y un pedido de compra para devoluciones de proveedores. Las transacciones de destino de devolución de artículos contienen opciones para determinar qué referencia de devolución se debe introducir en la orden de venta o en la orden de compra de artículos gratuitos.

## <a name="accurate-rebate-calculations"></a>Cálculos precisos de devoluciones

La combinación de las transacciones asociadas, la frecuencia de los cálculos, la base de cálculo y el método de cálculo que se selecciona determina la exactitud y precisión de los cálculos de devolución. Las provisiones de devoluciones se pueden utilizar para acumular valores contabilizados y reclamados.

Las provisiones se pueden administrar diariamente, semanalmente, mensualmente o según un período personalizado. Sin embargo, la funcionalidad puede asignar o pagar el descuento, o recibir el pago del mismo, en cualquier frecuencia definida que tenga la misma duración o más que la frecuencia de provisión. La cancelación utiliza la misma frecuencia que la devolución. Los usuarios pueden ajustar fácilmente un plan o montos de pago en cualquier momento durante el pago.

Los usuarios ya no tienen que gestionar acuerdos o provisiones en dos pasos. Las provisiones y cancelaciones se contabilizan directamente en el libro mayor. Además, las notas de crédito se pueden crear automáticamente. Por lo tanto, existe una integración completa con proveedores y clientes. Durante el procesamiento, los cálculos pueden considerar los descuentos de liquidación, las facturas pagadas, los descuentos comerciales y las notas de crédito existentes para garantizar que las cantidades y los valores se calculen con precisión.

Cuando se calculan las devoluciones, el proceso crea transacciones que se pueden revisar antes de que se produzca la contabilización. Un proceso separado contabiliza las transacciones de adminstración de devoluciones. Luego, se puede crear una transacción de diario, nota de crédito o débito durante la contabilización en las transacciones propuestas. Se pueden obtener declaraciones de informes y listados de transacciones para garantizar el cumplimiento, la eficacia y la transparencia.

## <a name="guaranteed-royalty-payments"></a>Pagos de regalías garantizados

En la gestión de devoluciones, la generación automática de pagos permite gestionar las regalías de forma rápida y sencilla, incluso cuando se aplican los mínimos garantizados.

## <a name="maximizing-spend-versus-rebates"></a>Maximizar el gasto frente a las devoluciones

Los proveedores y los productos se pueden agrupar por territorio, y se pueden proporcionar diferentes ofertas, según el país o la región de la transacción. Cuando los usuarios seleccionan productos, pueden definir los artículos que se incluyen y el número de artículos que se utilizarán en la liquidación de devoluciones.

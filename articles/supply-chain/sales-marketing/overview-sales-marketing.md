---
title: Visión general de ventas y marketing
description: Puede usar Ventas y marketing para obtener, almacenar y usar distintos tipos de datos en el flujo de ventas. Estos datos incluyen la iniciativa de venta original, la acción de seguimiento futura y las ventas adicionales.
author: Henrikan
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "92303"
- intro-internal
ms.assetid: 65ca9992-bbfa-4224-bf0e-067a25c7e6a4
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 25b87f45e43350f6c5e6ea775ebc3fcd74ec5187
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103812"
---
# <a name="sales-and-marketing-overview"></a>Visión general de ventas y marketing

[!include [banner](../includes/banner.md)]

Puede usar Ventas y marketing para obtener, almacenar y usar distintos tipos de datos en el flujo de ventas. Estos datos incluyen la iniciativa de venta original, la acción de seguimiento futura y las ventas adicionales.

## <a name="marketing"></a>Marketing

Las actividades y las campañas de marketing se usan para encontrar y crear relaciones con clientes potenciales, para que las interacciones iniciales puedan derivar en relaciones de ventas. El siguiente flujo de procesos muestra el proceso empresarial de marketing. [![Proceso empresarial de marketing.](./media/marketing01.jpg)](./media/marketing01.jpg)

### <a name="relationships"></a>Relaciones

En ventas y marketing, las interacciones iniciales que tenga con clientes potenciales se pueden producir en varias situaciones. Por ejemplo, podría encontrar un cliente potencial mientras asista a una feria comercial o puede tener un posible cliente potencial con un cliente después de que la organización dirija una campaña de correo masivo. Es muy importante que comprenda el flujo de la entidad de una parte antes de que dicha parte se convierta en cliente. En el gráfico siguiente se muestra el flujo de las relaciones de entidades conforme un cliente potencial se convierte en un cliente real. [![SalesandMarketing01.](./media/salesandmarketing01.jpg)](./media/salesandmarketing01.jpg)

### <a name="campaigns"></a>Campañas

Una campaña está destinada a los contactos para clientes potenciales, oportunidades y clientes que se han seleccionado para participar en la campaña. En Supply Chain Management, puede crear varios tipos de campañas, como telemarketing, correo y campañas de correo electrónico, para maximizar a su potencial de clientes. Conforme su campaña progresa y recibe respuestas positivas, puede cambiar el proceso de ventas con los destinatarios que han respondido de manera positiva a la campaña.

## <a name="sales"></a>Ventas
Utilice la funcionalidad de venta para crear presupuestos, venta vertical y venta cruzada para clientes nuevos y existentes, crear pedidos de ventas y crear facturas de venta para clientes. El siguiente flujo de procesos muestra el proceso empresarial de ventas. [![Proceso empresarial de ventas.](./media/sales01.jpg)](./media/sales01.jpg)

### <a name="sales-quotations"></a>Presupuestos de ventas

Cree presupuestos de ventas para presentar a los clientes una oferta de los bienes o servicios que va a proporcionar. Un cliente puede solicitar un presupuesto o crear un presupuesto en respuesta a una solicitud de un cliente potencial o existente. Cuando el cliente aprueba el presupuesto de ventas, puede convertirlo en un pedido de ventas.

### <a name="up-sellcross-sell"></a>Venta vertical o venta cruzada

Las ventas verticales y las ventas cruzadas son técnicas para vender productos cuando se introduce un pedido para un cliente. En las ventas verticales, se sugiere otro producto en lugar del producto actual. En las ventas verticales, se sugiere un producto además del producto actual. Al configurar listas de productos, puede crear reglas específicas para indicar el momento en que se debe sugerir un producto como un producto de venta cruzada o de venta vertical.

### <a name="sales-orders"></a>Pedidos de ventas

Al crear un nuevo pedido de ventas, debe seleccionar el tipo de pedido de ventas que se creará. Tiene cinco opciones. **Nota:** Tras crear un pedido de ventas, se puede cambiar cualquier tipo de pedido, excepto el tipo **Requisitos de artículos** si el pedido de ventas tiene un estado de **Entregado**.

| Tipo de pedido de ventas  | Descripción                                                                                                                                                                                                                                                                                            |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Diario           | Utilice este tipo como borrador de un pedido de ventas. Este tipo no afecta a las cantidades en existencias ni genera transacciones de artículos.                                                                                                                                                                    |
| Suscripción      | Utilice estos tipo para los pedidos recurrentes. Una vez facturado el pedido, el estado del pedido se establece automáticamente a un pedido abierto. Se actualizan la cantidad entregada que se facturó y las entregas restantes. No puede usar este tipo de pedido de ventas si está usando la funcionalidad de Administración de almacenes. |
| Pedido de ventas       | Utilice este tipo si un cliente ha realizado o confirmado un pedido.                                                                                                                                                                                                                                        |
| Pedido devuelto    | Utilice este tipo cuando un cliente devuelva un artículo. Se asigna un número de artículo devuelto (número RMA) automáticamente.                                                                                                                                                                                            |
| Artículos requeridos | Este tipo se crea automáticamente al crear una venta de artículos mediante un proyecto.                                                                                                                                                                                                                       |

### <a name="sales-agreements"></a>Acuerdos de venta

Un acuerdo de venta es un contrato que compromete al cliente a comprar un producto en una cantidad específico o por un importe determinado durante un período de tiempo, a cambio de precios especiales y descuentos. Los precios y descuentos de acuerdo de venta anulan todos los precios y descuentos indicados en cualquier contrato comercial que exista. Un acuerdo de venta es válido para un período definido. La fecha de envío solicitada que se especifica para una venta en la página **Pedido de ventas** debería encontrarse en el período de validez. De forma predeterminada, un acuerdo de venta está en espera. Puede realizar un pedido desde un acuerdo de venta cuando está establecido en **Vigente**.

### <a name="backorders"></a>Pedidos pendientes

Al especificar y validar pedidos, es posible que deba gestionar los pedidos pendientes y excepciones para poder completar la venta. Los pedidos pendientes son o bien pedidos aún sin entregar de un proveedor, o bien pedidos de ventas que aún no se han entregado a un cliente. Es importante que se realice un seguimiento de los pedidos pendientes. Por ejemplo, si los productos de un proveedores se retrasan, es posible que tenga que cambiar la fecha de entrega a un cliente y, a continuación, informarle acerca del retraso. Puede ver pedidos pendientes por artículo, cliente o proveedor.

#### <a name="viewing-backorders-by-item"></a>Visualización de pedidos pendientes por artículo

Cuando vea los pedidos pendientes por artículo, puede realizar un seguimiento del flujo de transacciones futuro para a un artículo concreto. Por ejemplo, puede comprobar la siguiente información:

-   El número de pedidos de ventas realizados para un artículo
-   Si aún están pendientes las entregas del artículo de los proveedores
-   Si se deben pedir más artículos para que pueda entregar todos los pedidos de ventas de manera oportuna

Al hacer esta comprobación, puede responder a las solicitudes de los clientes acerca del tiempo de la entrega del artículo. Además, puede priorizar los pedidos pendientes de ventas y, finalmente, dividir los artículos que estén disponibles entre los pedidos.

#### <a name="viewing-backorders-by-customer"></a>Visualización de pedidos pendientes por cliente

Cuando vea los pedidos pendientes por cliente, puede ver el estado de los pedidos restantes del cliente. Esta comprobación es útil cuando debe responder a los clientes que están esperando artículos que se han retrasado.

#### <a name="viewing-backorders-by-vendor"></a>Visualización de pedidos pendientes por proveedor

Cuando vea los pedidos pendientes de proveedor, puede realizar un seguimiento de entregas pendientes y fechas de entregas previstas. Esta comprobación también le ayuda a priorizar los pedidos pendientes cuando los productos provienen de los proveedores y se tienen que seleccionar los pedidos de ventas para la entrega.

### <a name="invoices"></a>Facturas

Puede crear tres tipos de facturas durante el proceso de ventas:

-   Factura del cliente
-   Factura de servicios
-   Factura proforma

#### <a name="customer-invoice"></a>Factura del cliente

Una factura de cliente es una factura que una organización da a un cliente en relación con una venta. Este tipo de factura de cliente se basa en un pedido de venta que incluye un encabezado y una o más líneas para artículos o servicios. La factura de cliente completa el ciclo de pedido de ventas, albarán y factura de ventas.  

Puede registrar e imprimir una factura de cliente única, basada en un pedido de ventas o el albarán y la fecha. También puede registrar e imprimir varias facturas de cliente juntas, basadas en los albaranes y las fechas. Al registrar una factura de cliente única mediante el pedido de ventas, la cantidad **Recordatorio de factura** de cada artículo se actualiza con el total de las cantidades facturadas del pedido de ventas seleccionado.  

Si las cantidades tanto de **Recordatorio de factura** como de **Pendiente de entrega** para todos los artículos de un pedido de ventas son 0 (cero), el estado del pedido de ventas cambia a **Facturado**. Si la cantidad de cualquier de los campos no es cero, el estado del pedido de ventas no cambia y podrá entrar facturas adicionales. Si piensa registrar e imprimir una o varias facturas de cliente basadas en los albaranes, ya debe haber registrado al menos un albarán para cada pedido de ventas. La factura de cliente se basa en los albaranes y refleja las cantidades que se muestran.  

Puede crear una factura de cliente basada en los artículos de línea de albarán enviados hasta la fecha, incluso si aún no se han enviado todos los artículos de un pedido de ventas en particular. Puede hacerlo, por ejemplo, si la entidad jurídica emite una factura por cliente al mes que cubre todas las entregas que se envían durante ese mes. Cada albarán representa una entrega parcial o completa de los artículos del pedido de ventas.  

Al registrar la factura, la cantidad de **Recordatorio de factura** de cada artículo se actualiza con el total de cantidades entregadas de los albaranes seleccionados. Si las cantidades de **Recordatorio de factura** y de **Pendiente de entrega** para todos los artículos de un pedido de ventas son 0 (cero), el estado del pedido de ventas cambia a **Facturado**. Si la cantidad no es cero, el estado del pedido de ventas no cambia y podrá entrar facturas adicionales. Las transacciones de inventario se actualizan con el número de factura y el estado de la línea del pedido de ventas cambia a **Facturado**.

#### <a name="free-text-invoice"></a>Factura de servicios

Las facturas de servicios son facturas no relacionadas con un pedido de ventas. Contienen líneas de pedido que incluyen cuentas contables, descripciones de texto libre y un importe de ventas. No puede especificar un número de artículo en este tipo de factura y debe escribir la información de impuestos correspondiente. Se indica una cuenta principal para la venta en cada línea de factura. El saldo del cliente se registra en la cuenta de resumen del perfil de contabilización que se usa para la factura de servicios.

#### <a name="pro-forma-invoice"></a>Factura proforma

Las facturas proforma son facturas que se preparan como estimación del importe real de la factura antes de registrar la factura. Se puede imprimir una factura proforma para una factura de cliente o para una factura de servicios.

### <a name="additional-resources"></a>Recursos adicionales

#### <a name="blogs"></a>Blogs

Puede encontrar una visión general de un proceso de ventas en el registro [Cómo funcionan las ventas en Dynamics 365 Finance and Operations](https://financefunction.tech/2018/05/15/how-sales-work-in-dynamics-365-for-finance-and-operations).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

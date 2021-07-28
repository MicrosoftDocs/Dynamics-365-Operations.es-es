---
title: Devoluciones de proveedor
description: Este tema proporciona una visión general de las tareas comunes que quiera llevar a cabo al trabajar con devoluciones de proveedor. Las devoluciones de proveedor proporcionan a las empresas un método muy útil de gestionar sus programas de devoluciones; para ello, se automatizan las tareas para así poder gestionar, seguir, y reclamar las devoluciones que se obtengan.
author: omulvad
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMVendRebateAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 2012
ms.openlocfilehash: 42c35fcca90b7dc55c8ef2985283d2ce92c4c8bc
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344229"
---
# <a name="vendor-rebates"></a>Devoluciones de proveedor

[!include [banner](../includes/banner.md)]

Las devoluciones de proveedor proporcionan a las empresas un método muy útil de gestionar sus programas de devoluciones; para ello, se automatizan las tareas para así poder gestionar, seguir, y reclamar las devoluciones que se obtengan.

Este tema proporciona una visión general de las tareas comunes que quiera llevar a cabo al trabajar con devoluciones de proveedor. En esta introducción se detallan las siguientes tareas:

- Revisar los detalles de un acuerdo de devolución
- Identificar los pedidos válidos para realizar devoluciones y generar las reclamaciones de devolución.
- Revisar y aprobar reclamaciones

## <a name="audience-and-purpose"></a>Público y propósito

La información de este tema está destinada a aquellos responsables de la toma de decisiones de las empresas, como gerentes de compras, directores financieros (CFO) y administradores contables, que tienen las responsabilidades siguientes:

- Negociar el precio de proveedor, el descuento y los acuerdos de devoluciones.
- Gestionar el personal que procesa las reclamaciones de las devoluciones y obtiene los pagos.
- Organizar el inventario con los mejores precios.

Las personas de estos puestos buscan formas de conseguir diversos objetivos. A continuación se incluyen algunos ejemplos:

- Adaptar con flexibilidad los diferentes tipos de programas de promoción de proveedores y las condiciones de devolución.
- Reducir la carga administrativa y aquellos errores asociados al rendimiento de los procesos de supervisión y el procesamiento de reclamaciones.
- Mejorar las previsiones del flujo de efectivo mediante la acumulación de futuros cobros.
- Obtener una base cuantificada para las negociaciones en curso y futuras sobre devoluciones con los proveedores.

## <a name="review-details-of-a-vendor-rebate-agreement"></a>Revisar los detalles de un acuerdo de devolución del proveedor

Un acuerdo de devolución del proveedor es el registro de un contrato con un proveedor en el cual se especifican los términos y condiciones bajo los cuales la empresa opta a una recompensa monetaria a cambio de conseguir unos objetivos de compra preestablecidos. Los acuerdos de devoluciones de proveedor se registran en la página **Acuerdos de devoluciones**.

Para abrir la página **Acuerdos de devoluciones del proveedor**, seleccione **Adquisición y abastecimiento** &gt; **Devoluciones del proveedor** &gt; **Acuerdos de devoluciones**.

![Acuerdo de compra.](media/purchase-agreement.PNG)

En la página **Acuerdos de devoluciones del proveedor**, puede ver información detallada sobre las condiciones negociadas en un contrato de proveedor.

La cabecera del acuerdo especifica las condiciones generales que cualifican a una empresa a hacer devoluciones. De hecho, en la información del encabezado se especifica que un proveedor concede una devolución cuando se compra una cantidad específica de cierto producto. También puede especificar en la cabecera la opción de devolución de la unidad de medida y el tipo de datos de cálculo.

- Sobre la pestaña **Visión general**, si tiene líneas con **Código de artículo** establecido en *tabla* para especificar el artículo, el acuerdo es para ese artículo concreto. Si tiene líneas con **Código de artículo** establecido en *Grupo* o *Todos* para especificar los artículos, el acuerdo de reembolso del proveedor se procesará individualmente por cada artículo válido para el código de artículo, no en todos los artículos válidos para el código de artículo.

- En la pestaña **General**, en el campo **Opción de devolución de la unidad de medida**, puede definir si una unidad de medida debe ser una condición para que la línea de pedido de compra pueda tenerse en cuenta para realizar una reclamación de devolución.

    - **Convertir**: es una línea de pedido de compra que permite una devolución de proveedor según el acuerdo de devolución. Recibirá una devolución independientemente de la unidad de medida que se aplique en la línea.
    - **Coincidencia exacta**: para optar a una devolución, la línea de compra debe tener la misma unidad de medida que el contrato.

- En la pestaña **General** , en el campo **Tipo de la fecha de cálculo**, seleccione la fecha que se usará para determinar si la compra se realizará en el período de validez del contrato de devolución.

    - **Fecha de creación**: usa la fecha de creación del pedido de compra.
    - **Entrega solicitada**: usa la fecha solicitada de entrega.

En las líneas del contrato puede especificar el contrato de devolución del proveedor con más detalle.

- En el campo **Acumular la compra por**, puede establecer el cálculo de la reclamación de devolución. El importe se puede configurar para que dependa de un período ya sea de semanas, meses, años, de por vida o personalizado. El valor **Factura** indica que una reclamación de devolución vendrá determinada cada vez que una línea de pedido de compra se facture.
- En el campo **Procedente de**, puede especificar la base para calcular las devoluciones.

    - **Bruto**: la devolución se calcula según el precio bruto del artículo.
    - **Neto**: la devolución se calcula según el precio neto del artículo (esto es, el precio resultante de aplicar otros descuentos).

- Los campos **Cuenta de acumulación del programa de devoluciones** y **Cuenta de gastos del programa de devoluciones** especifican los números de cuenta que recibirán los importes de devolución acumulados durante la etapa intermedia entre la aprobación y el procesamiento.
- Cuando la opción **Aprobación requerida** se establece en **Sí**, la reclamación de devolución debe aprobarse antes de que se pueda acumular o pagar.
- El campo **Tipo de salto de línea de devolución** especifica las bases de las devoluciones.

    - **Cantidad**: devoluciones que se basan en volúmenes.
    - **Importe**: devoluciones que se basan en los importes.

- En la ficha desplegable **Líneas**, puede ver cómo los distintos niveles de cantidad se pueden configurar para conceder distintas devoluciones. Por ejemplo, en la ilustración anterior, los campos **valor De** y **valor A** indican que una cantidad de producto de entre 10 y 19 unidades permitirá realizar una devolución de 15 USD por unidad.

    > [!NOTE]
    > El **valor De** es inclusivo,y el **valor A** es exclusivo. Por ejemplo, el campo **Tipo de salto de línea de devolución** está establecido en **Cantidad** y debe escribir **1** en el campo **valor De** y **3** en el campo **valor A**. En este caso, el importe de devolución se aplica al comprar uno o dos artículos, pero no al comprar tres artículos.

- En el campo **Estado de la aprobación del flujo de trabajo**, el valor **Aprobado** indica que el contrato se puede aplicar a los pedidos de compra que cumplan las condiciones del mismo.

## <a name="identify-orders-that-qualify-for-rebates-and-generate-rebate-claims"></a>Identificar los pedidos válidos para realizar devoluciones y generar las reclamaciones de devolución

Cuando los pedidos de compra corresponden a un proveedor con el cual la empresa tiene un contrato de devolución, el programa identifica cualquier futuro pago a crédito de proveedor. Si se puede realizar una devolución con los pedidos de compra, se crea una reclamación de devolución por cada línea de pedido tan pronto como se registra una factura de compra. Este es un proceso automático. Más adelante podrá revisar las devoluciones esperadas y comprobar el impacto de las mismas en el coste del producto y el margen de beneficio.

### <a name="view-details-of-rebates-that-are-applied-to-a-purchase-order-line-per-the-vendor-rebate-agreement"></a>Ver los detalles de las devoluciones que se aplican a una línea de pedido de compra por contrato de devolución del proveedor

1. En la página **Pedido de compra**, seleccione una línea de pedido y, a continuación, seleccione **Línea de pedido de compra** &gt; **Vista** &gt; **Detalles del precio**.
2. En la página **Detalles del precio**, seleccione la ficha desplegable **Devoluciones**.

La información de la devolución también se muestra en el campo **Devolución del proveedor** que está en la sección **Estimación de margen** de la página **Detalles del precio**.

> [!NOTE]
> En la página **Parámetros de compra y abastecimiento**, en la pestaña **Precios**, compruebe que la opción **Habilitar los detalles del precio** está configurada en **Sí**. Si la opción está en **No**, no podrá ver las devoluciones.

## <a name="review-and-approve-claims"></a>Revisar y aprobar reclamaciones

Las reclamaciones de devolución que se crean representan los pagos futuros que puede esperar del proveedor. Antes de emitir una nota de crédito al proveedor, el dueño del contrato suele querer revisar las reclamaciones para aprobarlas. Sin embargo, tenga en cuenta que el estado de una reclamación determina si la está lista para pasar por el proceso de aprobación.

### <a name="the-status-of-claims-and-the-effect-on-the-approval-process"></a>Estado de las reclamaciones y su efecto en el proceso de aprobación

Cuando se crea una reclamación, su estado se establece en **Para calcular** si se otorga la devolución de forma acumulativa, o se establece como **Calculada** si la devolución se otorga según la factura. Si el estado de una reclamación **Para calcular**, la reclamación debe pasar por un proceso de cálculo que gestiona la función Cumulate. Sólo aquellas reclamaciones que tienen el estado **Calculada** se pueden incluir en el proceso de aprobación.

> [!NOTE]
> Si la opción **Aprobación requerida** del contrato de devolución del proveedor se establece en **No**, cualquier reclamación que se cree tendrá un estado de **Aprobada**. La aprobación es obligatoria para aquellas reclamaciones que se conceden de forma acumulativa.

### <a name="approve-claims-and-view-postings-and-invoice-details"></a>Aprobar reclamaciones y ver los detalles de los registros y las facturas

Una vez aprobadas las reclamaciones, los proveedores (A/P) pueden procesarlas. Una nota de crédito (factura de proveedor) por el importe de la reclamación de devolución se genera automáticamente. Es entonces cuando se puede agregar el crédito al saldo del proveedor y el equipo A/P puede incluirlo en el proceso de liquidación normal.

1. Seleccione **Compra y abastecimiento** &gt; **Devoluciones de proveedor** &gt; **Reclamaciones de devoluciones** para abrir una reclamación de devolución.
2. Cierre la reclamación de devolución.
3. Marque la reclamación y, en el panel de acciones, seleccione **Aprobar**.
4. En la página de la solicitud, en el campo **Proveedor** , seleccione el proveedor del cual está autorizado a recibir una devolución y seleccione **Aceptar**.

    Se publicará un diario de acumulación de devoluciones según el importe reclamado. Este registro carga en la cuenta "Devoluciones del proveedor por cobrar acumuladas" el crédito esperado del proveedor y carga en la cuenta "Devoluciones del proveedor acumuladas recibidas" la ganancia prevista.

    ![Mensaje.](media/message.png)

5. En la lista de devoluciones, seleccione la línea y en el panel de acciones, seleccione **Transacciones de devolución** para consultar el número de lote del diario de este registro de acumulación de devoluciones.

    Para llevar las reclamaciones al proceso de A/P normal, el trabajador A/P debe completar la reclamación de devolución ejecutando la función Process.

6. En el panel de acciones, seleccione **Proceso** y **Filtro**. En el campo **Criterios** del campo **Cuenta de proveedor**, seleccione el proveedor del cual se procesarán las reclamaciones de devolución, seleccione otros filtros relevantes y, a continuación, seleccione **Aceptar**.

    Tanto las barras de mensajes como el estado cambiado a **Completada** indican que se han realizado los siguientes procesos:

    - Un registro de diario de acumulación de devoluciones ha invertido los importes provisionales anteriores en las cuentas por cobrar y de gastos acumulativas.
    - Una factura de proveedor (nota de abono) del importe de devolución se ha creado.

        > [!NOTE]
        > Al establecer la opción **Registro manual de la factura** en la pestaña **Programa de devoluciones** de la página **Parámetros de compra y abastecimiento**, se determina si una factura de proveedor se registró manualmente o automáticamente como parte del procesamiento de la reclamación.

    - Cuando se emite la factura de proveedor ya sea manual o automáticamente, se carga la cuenta del proveedor y se abona el importe en la cuenta "Descuentos y concesiones recibidos".

        > [!NOTE] 
        > El número de cuenta "Descuentos y concesiones recibidos" se especifica en la categoría de compras que se usa al adquirir la línea de factura de la devolución. La categoría de compras, a su vez, se establece en la pestaña **Programa de devoluciones** de la página **Parámetros de compra y abastecimiento**.

7. En la lista de devoluciones, seleccione la línea y en el panel de acciones, seleccione **Transacciones de devolución** para consultar el número de lote del diario de este registro de acumulación de devoluciones y el número de la factura del proveedor.
8. Seleccione la línea de transacción de la factura del proveedor y, a continuación, en el panel de acciones, seleccione **Factura del proveedor**. Si se ha emitido la factura del proveedor, verá el diario de facturas. Si no, verá la factura del proveedor como una factura de proveedor pendiente que requiere un registro manual.

    La línea de factura especifica los detalles de la factura del proveedor de la categoría de compras **Comisiones y devoluciones** .

9. En la página **Todos los proveedores**, seleccione el proveedor del cual recibirá una devolución y, a continuación, en el panel de acciones, seleccione **Transacciones**. Busque la línea de la factura. El importe de la devolución se agregará al saldo del proveedor.

## <a name="summary"></a>Resumen

El proceso para administrar devoluciones de proveedor implica realizar varias tareas manuales de seguimiento que son bastante tediosas. Si automatiza estas tareas, la función de gestión de devoluciones de proveedor puede ayudarle realizar los siguientes procesos:

- Crear reclamaciones de devolución precisas
- Acumular el cobro esperado y las ganancias provisionales en el libro de contabilidad general
- Actualizar el saldo del proveedor y el extracto de ingresos con las concesiones que estén pendientes


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Acuerdos de venta
description: "Este tema proporciona información sobre los acuerdos de ventas. Un acuerdo de venta es un contrato que compromete al cliente a comprar productos en una cantidad específica o por un importe determinado durante un período de tiempo, a cambio de precios especiales y descuentos."
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesAgreementListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 9554
ms.assetid: c5d55c8d-99f2-44f9-a897-5b0dee85fc81
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 4db47f445fe820e65389799ddcb6ea4a99949178
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="sales-agreements"></a>Acuerdos de venta

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre los acuerdos de ventas. Un acuerdo de venta es un contrato que compromete al cliente a comprar productos en una cantidad específica o por un importe determinado durante un período de tiempo, a cambio de precios especiales y descuentos.

Un acuerdo de venta es un contrato que compromete el cliente para comprar productos en una cantidad específica o por un importe específico a lo largo del tiempo, a cambio de precios especiales, descuentos especiales y otras condiciones especiales, como condiciones de pago y de entrega. Los precios y descuentos de acuerdo de venta anulan todos los precios y descuentos indicados en cualquier contrato comercial que pudiera existir.  

El período de validez de un acuerdo de venta se define en los campos **Fecha de vencimiento** y **Fecha de caducidad** del acuerdo. Un pedido de ventas de un cliente es apto para las condiciones del contrato si la fecha de envío del pedido se encuentra dentro del período de validez. Todas las líneas de pedidos de ventas que están vinculadas a un acuerdo de venta contribuyen al cumplimiento de dicho acuerdo de venta.  

Puede crear un pedido de ventas directamente desde un acuerdo de venta mediante la acción **Pedido parcial**. Como alternativa, puede seleccionar un acuerdo de venta en vigor cuando está tomando pedidos (consulte la sección “Aplicación de acuerdos de venta en el proceso de pedidos” de este artículo).  

> [Nota] En versiones anteriores se hace referencia a los acuerdos de ventas, como pedidos marco de ventas.

## <a name="commitment-types"></a>Tipos de compromiso
Cada línea de un acuerdo de venta expresa un compromiso para vender algo. Normalmente hay dos categorías de compromiso:

-   **Compromiso de valor**: el cliente acuerda comprar productos por un importe específico.
-   **Compromiso de cantidad**: el cliente acuerda comprar una cantidad específica de productos.

Además, un contrato puede comprometer al cliente a comprar un producto o productos específicos en una categoría de producto. Al combinar estos dos factores (valor frente a cantidad y productos específicos frente a categorías de productos), conseguimos cuatro tipos de compromiso:

-   **Compromiso de cantidad de producto**: el cliente acuerda comprar una cantidad específica de productos. Las líneas que usan este tipo de compromiso se definen por un número de artículo, así como por la cantidad y la unidad acordadas. El campo **Importe** no está disponible.
-   **Compromiso de valor de producto**: el cliente acuerda comprar productos específicos por un importe específico. Las líneas que utilizan este tipo de compromiso se definen por un número de artículo y el importe acordado. Los campos **Cantidad** y **Unidad** no están disponibles.
-   **Compromiso de valor de la categoría de producto**: el cliente acuerda comprar productos de una categoría de ventas específica por un importe específico. Las líneas que usan este tipo de compromiso se definen por una categoría de ventas en la jerarquía de categorías de ventas y un importe. Los campos **Cantidad** y **Unidad** no están disponibles.
-   **Compromiso de valor**: el cliente acuerda comprar un producto o productos dentro de cualquier categoría de compras por un importe específico. Los campos **Cantidad** y **Unidad** no están disponibles.

Las líneas en el mismo acuerdo de venta pueden tener distintos tipos de compromisos.

## <a name="pricing-terms-for-sales-agreements"></a>Condiciones de precios para acuerdos de venta
Las condiciones de precios pueden variar, en función del tipo de compromiso. En un pedido de ventas que está vinculado a un acuerdo de venta, las condiciones de precios de dicho acuerdo de venta anulan cualquier otro término de precios que se aplique en función de los contratos comerciales. La siguiente tabla describe los campos relacionados al precio afectados por cada tipo de compromiso. "Sí" indica que el campo se puede actualizar en una línea de pedido.

| Tipo de confirmación                   | Precio unitario | Unidad de precio | Porcentaje de descuento | Importe de descuento por pronto pago |
|-----------------------------------|------------|------------|------------------|----------------------|
| Compromiso de cantidad de producto       | Sí        | Sí        | Sí              | Sí                  |
| Compromiso de valor de producto          |            |            | Sí              |                      |
| Compromiso de valor de la categoría de producto |            |            | Sí              |                      |
| Compromiso de valor                  |            |            | Sí              |                      |

## <a name="policies-for-sales-agreements"></a>Directivas de acuerdos de venta
Las siguientes directivas afectan a la forma en que funciona el vínculo entre un compromiso de acuerdo de venta y las líneas de pedido de compra correspondiente:

-   **Máximo aplicado**: el importe o la cantidad total de todas las líneas de pedido no puede superar la cantidad o el importe que se especifica en el compromiso relacionado.
-   **El precio y el descuento es fijo**: el precio en una línea de pedido y el precio del compromiso relacionado no pueden ser diferentes. Si el precio se cambia en la línea de pedido, el vínculo al compromiso se rompe. Si el vínculo se rompe, la línea de pedido no contribuye al cumplimiento del compromiso.
-   **Importe mínimo liberado** e **Importe máximo liberado**: si se especifica un importe, recibirá un mensaje si realiza algún cambio a una línea de pedido que produce que la línea de pedido sea diferente del compromiso relacionado.

## <a name="fulfillment-calculations-for-sales-agreements"></a>Cálculos de cumplimiento para los acuerdos de venta
Las cantidades e importes de cumplimiento se muestran en la ficha **Suministro** de la ficha desplegable **Detalles de línea** de la página **Acuerdos de venta**.  

En el área **Suministro**, puede ver las cantidades y los importes totales para todas las líneas de pedido que están vinculadas al acuerdo de venta especificado. También puede ver el importe o la cantidad restante necesario para cumplir el compromiso.  

En el área **Acuerdo**, puede ver las cantidades e importes del acuerdo de venta especificado. Estas cantidades e importes son las cantidades y los importes totales del compromiso.

## <a name="confirmations-and-version-history-for-sales-agreements"></a>Historial de confirmaciones y versiones de los acuerdos de venta
Cuando se confirma un acuerdo de venta, la versión actual del acuerdo se almacena en una tabla de historial. Si cambia el acuerdo de venta, puede volver a confirmarlo para almacenar otra versión de dicho acuerdo de venta en el historial.  

Si no confirma un acuerdo de venta, puede utilizarlo para crear pedidos de ventas. Sin embargo, la información del historial del acuerdo de venta no se almacena.  

Puede ver o imprimir todas las revisiones de las confirmaciones. Puede compartir las versiones con su cliente para obtener la aprobación.

## <a name="applying-sales-agreements-during-the-ordering-process"></a>Aplicación de acuerdos de venta en el proceso de pedidos
Si no libera pedidos de ventas directamente para un acuerdo de venta, todavía puede vincular un acuerdo de venta a un pedido durante el proceso de entrada de pedidos. Cuando crea un nuevo pedido de ventas y selecciona un acuerdo de venta, las condiciones de dicho acuerdo, como las condiciones de pago, las condiciones de entrega y la dirección de entrega, se aplican al encabezado del pedido y se crean vínculos entre el acuerdo y el pedido. A continuación, en las líneas de pedido, cuando puede seleccionar los productos y las categorías que se han especificado en el acuerdo de venta, los precios y los descuentos se copian de ese acuerdo. El mismo pedido de ventas puede incluir tanto líneas que no están relacionadas con un acuerdo de venta como líneas que tienen un compromiso para un acuerdo de venta.

## <a name="modifying-sales-orders-that-are-linked-to-sales-agreements"></a>Modificación de pedidos de ventas vinculados a acuerdos de venta
Si ha creado (liberado) un pedido de ventas contra un acuerdo de venta, algunos campos de ese pedido de ventas solo se pueden modificar si quita el vínculo con las líneas del acuerdo de venta asociado. En la tabla siguiente aparecen algunos de estos campos.

| Campo                                                             | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fecha de envío solicitada                                               | Si cambia la fecha de envío solicitada por una fecha anterior al valor de **Fecha de vigencia** que aparece en la línea del acuerdo de venta, debe quitar el vínculo con la línea del acuerdo de venta para poder guardar la fecha de envío modificada. Si cambia la fecha de envío solicitada por una fecha posterior al valor **Fecha de caducidad** que aparece en la línea del acuerdo de venta, debe quitar el vínculo con la línea del acuerdo de venta para poder guardar la fecha de envío modificada. |
| Importe de CurrencyDiscount, percentDiscountUnit, pricePrice, unitNet | Si cambia el valor en cualquiera de estos campos y está activada la casilla de verificación **El precio y el descuento es fijo** en una línea del acuerdo de venta asociado, un cuadro de mensaje le solicita que guarde el cambio. Haga clic en **Sí** para quitar el vínculo con la línea del acuerdo de venta y volver a calcular el precio. Haga clic en **No** para quitar el vínculo con la línea del acuerdo de venta sin volver a calcular el precio.                                                                   |
| Importe neto                                                        | Si especifica un importe que excede el importe especificado en una línea del acuerdo de venta en la que la casilla de verificación **Máximo aplicado** está activada, un cuadro de mensaje le solicita que guarde el importe modificado. Haga clic en **Sí** para quitar el vínculo con la línea del acuerdo de venta y volver a calcular el precio. Haga clic en **No** para quitar el vínculo con la línea del acuerdo de venta sin volver a calcular el precio.                                                                 |
| Cantidad                                                          | Si especifica una cantidad que excede la cantidad especificada en una línea del acuerdo de venta en la que la casilla de verificación **Máximo aplicado** está activada, un cuadro de mensaje le solicita que guarde la cantidad modificada. Haga clic en **Sí** para quitar el vínculo con la línea del acuerdo de venta y volver a calcular el precio. Haga clic en **No** para quitar el vínculo con la línea del acuerdo de venta sin volver a calcular el precio.                                                            |

## <a name="returning-an-item-that-was-ordered-from-a-sales-agreement"></a>Devolución de un artículo pedido desde un acuerdo de venta
Cuando un cliente devuelve un producto que se ha pedido desde un acuerdo de venta, Microsoft Dynamics 365 for Finance and Operations puede buscar y actualizar automáticamente el compromiso del acuerdo de venta relacionado para reflejar el cambio de cantidad o de importe. Con la creación de un pedido de devolución que está basado en el pedido de ventas original que está vinculado a un acuerdo de venta, se establece una relación entre el compromiso del acuerdo de venta, la línea del pedido de ventas y la factura del pedido de devolución.  

Si no desea deducir la cantidad del artículo devuelto del compromiso del acuerdo de venta, puede usar el control **Quitar vínculo** de la página **Pedido de devolución** para quitar el vínculo entre el pedido de devolución y el compromiso del acuerdo de venta. Si debe restablecer el vínculo más adelante, haga clic en **Crear vínculo**.  

**Nota**: un pedido de devolución solo se puede vincular a un acuerdo de venta. Si un cliente devuelve varios productos que se han pedido desde más varios acuerdos de venta, debe crear un nuevo pedido de devolución para cada producto y crear un vínculo al acuerdo de venta correspondiente.

## <a name="automatic-search-for-sales-agreements"></a>Búsqueda automática para acuerdos de venta
En algunos casos donde se crean indirectamente los pedidos de ventas, por ejemplo, cuando se crea una nota de abono o pedidos de venta de empresas vinculadas, puede controlar si Microsoft Dynamics 365 for Finance and Operations busca automáticamente los acuerdos de venta aplicables.

## <a name="financial-dimensions-on-sales-agreements"></a>Dimensiones financieras sobre acuerdos de venta
Puede copiar dimensiones financieras en encabezados de documentos o en líneas individuales de un acuerdo de venta. Puede modificar las dimensiones en un encabezado o en una línea de acuerdo en cualquier momento. En este caso, las dimensiones se copian automáticamente al encabezado o la línea de liberación de pedidos parciales.





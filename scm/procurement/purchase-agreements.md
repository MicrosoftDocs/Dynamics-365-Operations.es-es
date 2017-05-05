---
title: Acuerdos de compra
description: "Este artículo proporciona información acerca de los acuerdos de compra. Un acuerdo de compra es un contrato que compromete a una organización a comprar una cantidad o un importe específico mediante varios pedidos de compra en el tiempo. A cambio de este compromiso, el comprador recibe precios y descuentos especiales."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AgreementClassification, AgreementLine, AgreementLinePrompt, PurchAgreement, PurchAgreementCreate, PurchAgreementGenerateReleaseOrder, PurchAgreementHistory, PurchAgreementInvoiceJournal
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11634
ms.assetid: 8ac20adf-7412-4929-be8c-aaedf23a76ad
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: 3f96d12960e90bb05497d1bc2900d4477551c091
ms.lasthandoff: 03/31/2017


---

# <a name="purchase-agreements"></a>Acuerdos de compra

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca de los acuerdos de compra. Un acuerdo de compra es un contrato que compromete a una organización a comprar una cantidad o un importe específico mediante varios pedidos de compra en el tiempo. A cambio de este compromiso, el comprador recibe precios y descuentos especiales. 

Los acuerdos de compra se pueden aplicar a una cantidad específica de un producto, a un importe de un producto en una divisa específica o a una cantidad de productos en una divisa específica dentro de una categoría de compra. Los precios y descuentos de acuerdo de compra anulan todos los precios y descuentos indicados en cualquier contrato comercial que pudieran existir.  

En la página **Acuerdos de compra** puede crear, aplicar y realizar un seguimiento de los acuerdos de compra que existen entre la organización y los proveedores. Por ejemplo, después de crear un acuerdo de compra, puede realizar pedidos directamente desde el acuerdo. Cada acuerdo de compra tiene un período de validez definido por la persona que lo crea. La fecha de entrega de una compra debe estar dentro de las fechas de vigencia del período de validez.  

Tras crear un acuerdo de compra, debe activarlo para que entre en vigor. Para activar un acuerdo de compra, defina la opción **Marcar acuerdo como vigente** en **Sí**.

## <a name="commitment-types"></a>Tipos de compromiso
Cada línea de un acuerdo de compra es un compromiso a comprar algo. Puede usar líneas de varios pedidos de compra para satisfacer el compromiso. Hay cuatro tipos de compromisos:

-   **Compromiso de cantidad de producto**: se compra una cantidad específica de un producto.
-   **Compromiso de valor de producto**: se compra un importe en una divisa específica de un producto.
-   **Compromiso de valor de la categoría de producto**: se compra un importe en una divisa específica en una categoría de compra. El importe puede ser para un artículo de catálogo o un artículo fuera del catálogo.
-   **Compromiso de valor**: se compra un importe en una divisa específica de cualquier producto o productos dentro de cualquier categoría de compras.

## <a name="pricing-terms-for-purchase-agreements"></a>Condiciones de precios para acuerdos de compra
Las condiciones de precios pueden variar, en función del tipo de compromiso. Las condiciones de precios de los acuerdos de compra anulan cualquier otro término de precio configurado para los contratos comerciales. La siguiente tabla describe los campos relacionados al precio afectados por cada tipo de compromiso. Los campos que contengan **Sí **se pueden actualizar en una línea de pedido.

| Tipo de confirmación                   | Precio unitario | Unidad de precio | Porcentaje de descuento | Importe de descuento por pronto pago |
|-----------------------------------|------------|------------|------------------|----------------------|
| Compromiso de cantidad de producto       | Sí        | Sí        | Sí              | Sí                  |
| Compromiso de valor de producto          |            |            | Sí              |                      |
| Compromiso de valor de la categoría de producto |            |            | Sí              |                      |
| Compromiso de valor                  |            |            | Sí              |                      |

## <a name="policies-for-purchase-agreements"></a>Directivas de acuerdos de compra
Las siguientes directivas afectan a cómo funciona el vínculo entre un compromiso de acuerdo de compra y las líneas de pedido de compra correspondiente:

-   **Máximo aplicado**: el importe o la cantidad total de todas las líneas de pedido no puede superar la cantidad o el importe que se especifica en el compromiso relacionado.
-   **El precio y el descuento es fijo**: el precio en una línea de pedido y el precio del compromiso relacionado deben ser iguales. Si el precio se cambia en la línea de pedido, el vínculo al compromiso se rompe. Si el vínculo se ha roto, la línea de pedido no contribuye al cumplimiento del compromiso.
-   **Importe mínimo liberado e Importe máximo liberado**: si se especifica un importe, recibirá un mensaje si realiza algún cambio a una línea de pedido que produce que la línea de pedido sea diferente del compromiso relacionado.

## <a name="fulfillment-calculations-for-purchase-agreements"></a>Cálculos de cumplimientos para los acuerdos de compra
Las cantidades e importes de cumplimiento se muestran en la ficha **Suministro** de la ficha desplegable **Detalles de línea** de la página **Acuerdos de compra**.  

El área **Suministro** muestra el importe o la cantidad restante necesario para cumplir el compromiso.  

El área **Acuerdo** muestra la cantidad total o el importe total para el que es válida la línea del acuerdo de venta.  

Puede obtener acceso a las líneas de pedidos de compra y las líneas de factura que contribuyen al cálculo de cumplimiento seleccionando la acción **Información relacionada** en las líneas o en el encabezado de un acuerdo de compra.

## <a name="confirmations-and-version-history-for-purchase-agreements"></a>Historial de versiones y confirmaciones de los acuerdos de compra
Cuando se confirma un acuerdo de compra, la versión actual del acuerdo se almacena en una tabla del historial. Si cambia el acuerdo de compra, puede volver a confirmarlo para almacenar otra versión del acuerdo de compra en el historial. Si no confirma un acuerdo de compra, puede utilizarlo para crear pedidos de compra. Sin embargo, la información del historial del acuerdo de compra no se almacena. Puede ver o imprimir todas las versiones del acuerdo. Puede compartir las revisiones con su proveedor para obtener la aprobación.

## <a name="applying-purchase-agreements-in-the-ordering-process"></a>Aplicación de acuerdos de compras en el proceso de pedidos
Cuando se crea un pedido de compra, puede aplicarle un acuerdo de compra. La información de las condiciones del acuerdo, como las condiciones de pago, las condiciones de entrega y la dirección de entrega, se copian en el encabezado del pedido de compra. Si el pedido de compra contiene una o varias líneas de productos o categorías cubiertos en el acuerdo de compra, los precios y descuentos del acuerdo de compra se utilizan para estas líneas. El importe o la cantidad de la línea de pedido contribuye al cumplimiento de compromiso en el acuerdo de compra. El mismo pedido de compra puede incluir ambas líneas que no están relacionadas con un acuerdo de compra y las líneas que tienen un compromiso para un acuerdo de compra.  

Puede seleccionar un acuerdo de compra solo si está creando un pedido de compra. No puede seleccionar un acuerdo de compra después de haber creado el pedido de compra.  
En algunos casos en los que los PO se crean indirectamente, se puede controlar si Microsoft Dynamics 365 para Operaciones busca automáticamente acuerdos de compra aplicables. Por ejemplo, puede hacerlo cuando se consoliden automáticamente pedidos de compra planificados en firme o cuando se creen pedidos de compra que se basan en pedidos de ventas.

## <a name="purchase-agreements-and-intercompany-trade"></a>Acuerdos de compra y transacciones comerciales entre empresas vinculadas
Las relaciones comerciales entre empresas vinculadas se pueden crear entre cuentas de proveedor y cuentas de cliente que se encuentran en distintas entidades jurídicas. Cuando un pedido de ventas o un pedido de compra se crea para una de las partes, se crea una cadena de pedidos de empresas vinculadas. En la cadena de pedido, el pedido de ventas y el pedido de compra se crea en las entidades jurídicas adecuadas.  

Puede crear un acuerdo de compra o un acuerdo de venta para una de las partes comerciales de empresas vinculadas. A continuación, puede generar el acuerdo de venta o el acuerdo de compra correspondiente para la otra parte comercial de las empresas vinculadas en la otra entidad jurídica.  

Si se crea un pedido de compra de empresas vinculadas que usa el acuerdo de compra de empresas vinculadas en una entidad jurídica, el pedido de ventas de empresas vinculadas correspondiente usa el acuerdo de venta de empresas vinculadas correspondiente en la otra entidad jurídica. El cumplimiento de los compromisos del acuerdo de venta y el cumplimiento de los acuerdos de compra se sincronizan a medida que se sincroniza el pedido de ventas y el pedido de compra de empresas vinculadas.

## <a name="financial-dimensions-on-purchase-agreements"></a>Dimensiones financieras sobre acuerdos de compra
Puede copiar dimensiones financieras en encabezados de documentos o líneas individuales de un acuerdo de compra. Si modifica las dimensiones en el encabezado del acuerdo o en la línea del acuerdo, el cambio no afecta a ninguno de los pedidos liberados, sino que se reflejará en los pedidos nuevos.

<a name="see-also"></a>Consulte también
--------

[Creación de un acuerdo de compra (guía de tareas)](https://ax.help.dynamics.com/en/wiki/create-a-purchase-agreement/)

[Crear un pedido parcial de compra de un acuerdo de compra (guía de tareas)](https://ax.help.dynamics.com/en/wiki/create-a-purchase-release-order-from-a-purchase-agreement/)





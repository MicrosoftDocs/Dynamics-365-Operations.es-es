---
title: "Vista general de adquisición y abastecimiento"
description: "Este artículo ofrece una visión general de la funcionalidad que está disponible en el módulo Adquisición y abastecimiento."
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 58021
ms.assetid: eea24e23-a803-4de0-a218-6485757cde1b
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0692518afc5c8b385773dad3c44dc4e3c978362b
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="procurement-and-sourcing-overview"></a>Vista general de adquisición y abastecimiento

[!include[banner](../includes/banner.md)]


Este artículo ofrece una visión general de la funcionalidad que está disponible en el módulo Adquisición y abastecimiento.

Adquisición y abastecimiento cubre todos los pasos desde identificar una necesidad de productos y servicios hasta la obtención de productos, recibos, facturación y el proceso de pago con los proveedores. Los procesos de adquisición se pueden configurar con requisitos específicos de la empresa definiendo directivas de compra y flujos de trabajo.

## <a name="identifying-a-need-for-product-and-services"></a>Identificación de la necesidad de productos y servicios
La necesidad de productos o servicios puede surgir de *petición*, por ejemplo, cuando un empleado requiere un producto. Los *Catálogos de productos* se pueden configurar para guiar la selección de productos disponibles para seleccionarlos, o las solicitudes se pueden hacer para los productos que aún no están disponibles en un catálogo, permitiendo así que el departamento de compras considere cómo se puede proporcionar el producto.  

Los *Límites de gasto* pueden usarse para limitar el gasto de la petición, y *flujo de trabajo de compra* agrega la opción de requerir la aprobación antes de realizar el pedido. También es posible especificar la asignación de los fondos de presupuesto, si procede.  
  
El departamento de adquisición identifica a los proveedores para los productos y servicios necesarios, y esto puede implicar que se envíe una *solicitud de presupuesto* a varios proveedores potenciales. Es posible compartir las especificaciones del producto se solicita y los posibles proveedores pueden verlas para ver si pueden entregar un producto que cumpla con ellas. Los proveedores devuelven sus ofertas, que después serán revisadas por el departamento de compras antes de seleccionar el proveedor que desean.  

Los pedidos de compra incluyen una opción para enviar una *consulta de compra* al proveedor como alternativa a un proceso más completo de la solicitud de presupuesto. La consulta de compra se puede usar para ayudar a establecer condiciones como precios, descuentos y fecha de entrega del pedido. Si se configura los proveedores para que usen el portal **Proveedor**, la funcionalidad de consulta de compra estará deshabilitada. En su lugar, el pedido se comparte en el portal**Proveedor**, y cuando se envía una*solicitud de confirmación*, el proveedor puede confirmar directamente el pedido.  

Los *Catálogos de proveedores* puede usarse para recopilar información sobre el surtido de productos que los proveedores pueden suministrar. Los proveedores pueden publicar su propio catálogo, por lo que resulta más fácil mantener el catálogo actualizado. Es posible vincular una *lista de proveedores aprobados* a un producto, y ésto puede ayudar para la selección del proveedor cuando se abren los nuevos pedidos de compra y evitar el uso de proveedores no intencionados.

## <a name="procurement"></a>Adquisición
Los *Pedidos de compra* se pueden crear de varias formas diferentes, como por ejemplo:

-   Como resultado de la planificación maestra que ha identificado una demanda que requiere una compra. Este proceso genera pedidos de compra planificados y cuando estos se liberan, se generan los pedidos de compra.
-   Con el proceso de solicitudes de compra que resultan de la adquisición.
-   Con el proceso de los acuerdos de compra, donde los pedidos de compra se crean como pedidos liberados de los acuerdos. Esto es de uso general cuando se usan los acuerdos de compra para representar pedidos abiertos.
-   Manualmente, cuando el pedido de compra que se crea no se basa en otro documento.

Los pedidos de compra que se configuran con *flujos de trabajo de aprobación de compra* requieren aprobación antes de registrarse como aprobados antes de que el pedido se pueda seguir procesando.  

Los pedidos de compra son *confirmado* para indicar que un acuerdo se ha establecido con el proveedor. El pedido de compra progresará gradualmente a través de los diferentes estados hasta que finalmente sean facturados o cancelados.  

Cuando se crea un pedido de compra, muchos de los campos se rellenan automáticamente con los valores predeterminados de la información almacenada sobre el proveedor en la página **Proveedores**. Esto significa que hay un número limitado de campos que se debe completar en el pedido de compra, aunque puede elegir reemplazar los valores predeterminados.

### <a name="prices-and-discounts"></a>Precios y descuentos

Los precios y descuentos incluyen información sobre los precios, los descuentos y las condiciones de la devolución que ofrecen. Los precios y descuentos se pueden representar como *comercio* *acuerdos*. Los acuerdos comerciales representan listas de precios de proveedor con precios o descuentos y tienen un conjunto concreto de fechas para las que el contrato es válido. Los precios y los descuentos se pueden negociar y representar mediante *acuerdos de compra* con condiciones como compromisos para comprar determinados volúmenes o importes monetarios como condición previa para las condiciones negociadas. Los *Acuerdos de devoluciones* pueden ser creado con los proveedores donde la adquisición de productos o grupos específicos de productos puede desencadenar una devolución del proveedor según el importe o el volumen de la compra.

### <a name="delivery-options"></a>Opciones de entrega

Existen varias opciones para el proceso de entrega asociado a un pedido de compra. Los productos pedidos se pueden dividir en programaciones de *entrega*, donde partes de la cantidad pedida se pueden planificar para su entrega en distintas fechas. La entrega también puede incluir *entrega directa* desde un pedido de ventas, que automatiza la generación del albarán en el pedido de ventas al mismo tiempo que la recepción de producto se registra en el pedido de compra. Los pedidos de compra también pueden formar parte de una cadena de *pedido de empresas vinculadas*, también denominada pedidos de compra de empresas vinculadas, donde los productos se piden a partir de un pedido de ventas de empresas vinculadas coincidente. En esta situación, algunos pasos se automatizan en los dos pedidos de empresas vinculadas relacionados.

### <a name="supplementary-items"></a>Artículos adicionales

Los productos se pueden configurar para que incluyan *artículos adicionales*. Esto es para proponer productos relacionados con el producto que se pide. Los productos adicionales pueden ser necesarios u opcionales. En algunos casos, los artículos adicionales se pueden agregar como productos gratis que acompañan la compra de otros productos.

### <a name="purchase-order-charges"></a>Gastos varios del pedido de compra

Se pueden asignar cargos pedido de compra. Esto puede suceder automáticamente con la configuración de cargos automáticos o agregando los cargos manualmente. Los cargos se pueden asignar al pedido tanto a nivel de cabecera como a nivel de línea. La contabilidad de los cargos se puede configurar de distintas maneras. Por ejemplo, puede configurar un cargo para que se cuente como coste del producto. Si hace esto, los cargos se deben asignar a nivel de la línea de pedido antes de confirmar el pedido. Hay una opción que puede ayudar a asignar cargos del encabezado del pedido a las líneas.

## <a name="product-receipt-and-invoicing"></a>Recepción y facturación de productos
Los pedidos de compra que incluyen productos físicos requieren normalmente que el *registro de llegadas* tenga lugar dentro de un almacén y luego se registra una *recepción de producto* para el pedido. Se pueden configurar pedidos de compra con productos que cumplen las peticiones, de modo que el empleado que ha solicitado los productos también tiene que proporcionar una *confirmación de recepción*.  

Algunos pedidos de compra incluyen productos que son servicios u otros productos no físicos donde no es necesaria la recepción en un almacén. Los productos se pueden crear como servicios o se pueden usar las *categorías de compras* directamente en el pedido de compra para dichos pedidos. Con estos pedidos, la contabilidad de la recepción del producto se omite a veces y el pedido se factura directamente, o el registro de la recepción de producto se realiza en el pedido de compra sin ningún registro anterior de llegada.  

La recepción de productos puede provocar el consumo automático para un propósito específico. Esto incluye el consumo relacionado con la entrega directa, el consumo hacia un proyecto o la contabilidad lel producto como activo fijo.  

Cuando las *facturas de proveedores* llegan del proveedor, se pueden primero registrar en el *registro de facturas*independiente del pedido de compra y se pueden aprobar posteriormente como un registro con el pedido de compra. Registrar la factura de proveedor con el pedido de compra incluye la conciliación de la recepción del producto y la factura.  

Las *Distribuciones contables* se pueden especificar en el pedido de compra para describir cómo se debe realizar la contabilidad en el libro mayor, y también pueden definir cómo se obtiene la asignación de los fondos presupuestarios si esto se incluye en la configuración.  

Los pedidos de compra facturados registrarán el pasivo en la cuenta de proveedor dentro de los proveedores, desde donde el *p*a*go del proveedor* puede ser procesado.

## <a name="vendor-performance"></a>Rendimiento de proveedores
El rendimiento y revisión de la compra es compatible con los *informes repercutidos de adquisición y abastecimiento la cuenta,* que incluye el análisis de gastos y el análisis de rendimiento del proveedor.





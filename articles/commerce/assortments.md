---
title: Administración de surtidos.
description: En este tema se explican los conceptos básicos de administración de surtidos en Dynamics 365 Commerce y se proporcionan consideraciones sobre implementaciones para el proyecto.
author: jblucher
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Global
ms.author: jeffbl
ms.search.validFrom: 2017-11-21
ms.dyn365.ops.version: Application update 5
ms.openlocfilehash: 981d1c604a7ed461f207e78c8c7f073aff03be9e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980007"
---
# <a name="assortment-management"></a>Administración de surtidos

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Información general

Dynamics 365 Commerce proporciona *surtidos* que le permiten gestionar la disponibilidad de productos mediante canales. Los surtidos determinan qué productos están disponibles en tiendas específicas y durante un período concreto.

En Commerce, un surtido es una asignación de uno o varios canales (o grupos de canales, cuando se emplean jerarquías organizativas) para uno o más productos (o grupos de productos, cuando se emplean jerarquías de categorías).

La combinación general de productos de un canal viene determinada por surtidos publicados que se asignan al canal. Por lo tanto, puede configurar varios surtidos activos por canal.

### <a name="basic-assortment-setup"></a>Configuración básica de surtido

En el siguiente ejemplo, se configura un surtido único para cada tienda. En este caso, solo el producto 1 está disponible en la tienda 1, y solo el producto 2 está disponible en la tienda 2.

![Cada producto está disponible en una tienda](./media/Managing-assortments-figure1.png)

Para hace que el producto 2 esté disponible en la tienda 1, puede agregar el producto al surtido 1.

![Producto 2 agregado productos a surtido 1](./media/Managing-assortments-figure2.png)

Como alternativa, puede agregar la tienda 1 al surtido 2.

![Tienda 1 agregada a surtido 2](./media/Managing-assortments-figure3.png)

### <a name="organization-hierarchies"></a>Jerarquías organizativas

En situaciones en las que varios canales comparten los mismos surtidos de productos, puede configurar los surtidos mediante la jerarquía organizativa de surtidos de Commerce. Cuando se agregan nodos de esta jerarquía, se incluirán todos los canales de ese nodo y sus nodos secundarios.

![Jerarquía organizativa](./media/Managing-assortments-figure4.png)

### <a name="product-categories"></a>Categorías de productos

De forma similar, en el lado de los productos, puede incluir grupos de productos mediante jerarquías de categorías de productos. Puede configurar surtidos incluyendo uno o más nodos de jerarquía de categoría. En este caso, el surtido incluirá todos los productos de ese nodo de categorías y sus nodos secundarios.

![Categorías de productos](./media/Managing-assortments-figure5.png)

### <a name="excluded-products-or-categories"></a>Productos o categorías excluidos

Además de incluir productos y categorías en surtidos, puede usar la opción Excluir para definir productos o categorías específicos que se deben excluir de los surtidos. En el siguiente ejemplo, desea incluir todos los productos en una categoría específica, excepto el producto 2. En este caso, no tiene que definir el surtido producto por producto o crear nodos de categorías adicionales. En su lugar, puede incluir solo la categoría pero excluir el producto.

> [!NOTE]
> Si un producto se incluye y excluye en uno o más surtidos por definición, el producto siempre se considerará como excluido.

![Producto excluido](./media/Managing-assortments-figure6.png)

### <a name="global-and-released-products"></a>Productos globales y emitidos

Los surtidos se definen a nivel global y pueden contener canales de varias entidades jurídicas. Los productos y las categorías que se incluyen en surtidos también se comparten entre entidades jurídicas. Sin embargo, un producto debe liberarse antes de que se pueda vender, pedir, contar o recibir en el canal (por ejemplo, en el punto de venta \[PDV\]). Por lo tanto, aunque dos tiendas en distintas entidades jurídicas pueden compartir un surtido que contenga los mismos productos, los productos están disponibles solo si se han liberado a dichas entidades jurídicas.

### <a name="dynamic-and-static-assortments"></a>Surtidos dinámicos y estáticos

Los surtidos se pueden definir con canales y productos específicos o incluyendo unidades organizativas y categorías. Los surtidos que incluyen referencias a estos grupos se consideran surtidos dinámicos. Si la definición o el contenido de estos grupos cambia a medida que el surtido está activo, la definición del surtido también cambiará.

Por ejemplo, un surtido se define y se publica originalmente de modo que haga referencia a una categoría de productos. Si se agregan posteriormente productos adicionales a la categoría, estos productos se incluyen automáticamente en la definición del surtido existente. No es necesario agregar manualmente los productos al surtido. De forma similar, si se agrega una unidad organizativa a un nodo diferente, el surtido de la unidad organizativa se ajusta automáticamente en base a esa definición.

### <a name="stopped-products"></a>Productos detenidos

Puede "detener" productos emitidos para el proceso de ventas activando una configuración en la configuración **Pedido predeterminado**. Esta configuración se emplea con mayor frecuencia cuando un producto se encuentra al final de su ciclo de vida y no debe venderse en ningún canal. Los surtidos respetan esta configuración y los productos detenidos no se surtirán, independientemente de la configuración del surtido.

### <a name="blocked-products"></a>Artículos bloqueados

Además de detener las ventas de un producto, puede bloquear temporalmente las ventas de un producto. Puede configurar esta opción de configuración en la pestaña **Commerce** de un producto liberado. Los productos bloqueados aún están surtidos, pero recibirá un mensaje en el PDV que indica que el producto no se puede vender.

### <a name="date-effectivity"></a>Fecha de vigencia

Los surtidos son fechas de vigencia. Por lo tanto, los minoristas pueden configurar cuando los productos deben o no deben estar disponibles por canal. Puede definir y publicar surtidos con antelación, y especificar las fechas de inicio y fin. Los productos estarán automáticamente disponibles o no disponibles en las fechas especificadas.

### <a name="process-assortments-batch-job"></a>Procesar trabajo por lotes del surtido

Los surtidos que se definen en Commerce deben procesarse antes de que entren en vigor. Este proceso se hace por los siguientes motivos:

- Las definiciones de surtido se deben desnormalizar para que los canales puedan consumirlas con mayor facilidad. Se puede definir una combinación de productos para un canal mediante varios surtidos que abarquen diversos intervalos de fechas. Cuando parte de esta información se calcula con antelación en el servidor, se mejora el rendimiento en el canal.
- Los productos y los canales en el surtido pueden cambiar fuera del propio surtido. Los surtidos dinámicos que contengan referencias a categorías o unidades organizativas deben procesarse periódicamente para que incluyan o excluyan registros, en función de su asignación actual.

## <a name="implementation-considerations"></a>Consideraciones sobre la implementación

Tenga en cuenta los siguientes requisitos de implementación a medida que planifica y administra los surtidos para su implementación de Commerce:

- **Replicación de datos y tamaño de la base de datos**: aunque los surtidos ayudan a la empresa a administrar la disponibilidad de productos, también son una herramienta importante para administrar el tamaño del canal y las bases de datos sin conexión. Los surtidos bien administrados ayudan a reducir la cantidad de datos que deben procesarse y replicarse al canal y las bases de datos sin conexión. También ayudan a reducir el número de registros que deben conservarse. Menos registros en estas bases de datos aumentarán el rendimiento cuado agregue artículos a una transacción, busque y explore productos.
- **Surtidos de fecha de vigencia/caducidad**: una de las herramientas más efectivas para administrar el número de productos en canal y bases de datos sin conexión es la eficacia de la fecha de surtidos. Si deja surtidos abiertos (sin caducidad) para productos estacionales o productos que se encuentran al final de su ciclo de vida, estas bases de datos crecerán de forma indefinida. Puede usar varios enfoques para ayudar a gestionar la situación. Por ejemplo, puede mantener surtidos independientes para productos estacionales y productos que siempre están disponibles.
- **Ventas y devoluciones fuera de surtidos**: esta capacidad ayuda a los minoristas a administrar con eficacia sus surtidos al dejarles limitar el número de productos disponibles a productos que pertenecen a la combinación de producto principal para la tienda. Esta capacidad también ayuda a los minoristas a gestionar las situaciones en las que un producto se omitió por error de un surtido, o en las que un producto se devolvió fuera de las fechas de vigencia para el surtido.

Si no existen datos de un producto en la base de datos del canal, el PDV realiza llamadas en tiempo real a la sede para recuperar la información necesaria, de manera que el producto pueda venderse, devolverse o colocarse en el pedido de un cliente. La información del producto que se recupera de esta manera solo está disponible durante el ámbito de la transacción. El producto no se agrega a la definición del surtido. Por lo tanto, las llamadas en tiempo real posteriores se harán cuando sea necesario.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Búsqueda de precios y descuentos aplicables
description: Este procedimiento muestra cómo encontrar el precio y/o el descuento para un producto actualmente válido para un cliente concreto, sin crear un pedido de ventas.
author: omulvad
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8d5188c4a0e06f116e1fdcab33546e3e0745c4f483c72f954b65b2307a683080
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753900"
---
# <a name="look-up-applicable-prices-and-discounts"></a>Búsqueda de precios y descuentos aplicables

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo encontrar el precio y/o el descuento para un producto actualmente válido para un cliente concreto, sin crear un pedido de ventas. El procedimiento le guía por un ejemplo específico y, para poder seleccionar los valores necesarios, necesita seguir el ejemplo con la empresa de demostración USMF.


## <a name="find-the-applicable-price"></a>Búsqueda del precio aplicable
1. Vaya Ventas y marketing > Precios y descuentos > Buscar precios.
2. En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el cliente US-001.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Código de artículo, escriba 'T0004'.
    * Por defecto, el campo Cantidad se haya definido en 1. No obstante, si conoce el tamaño del pedido que el cliente pretende realizar para el producto en cuestión, especifique en su lugar este valor. Esta información es relevante si los acuerdos comerciales con el cliente se dividen en cantidades por niveles, es decir, el precio del producto depende de la cantidad mínima comprada.  
6. En el campo Fecha, especifique una fecha en la que se prevé que el cliente realice un pedido. 
    * La fecha debe ser la fecha en curso o en cualquier fecha futura.  
    * El sistema devuelve ahora el precio válido para el producto seleccionado cuando lo compra el cliente seleccionado en la fecha seleccionada y de acuerdo con una cantidad especificada. En este ejemplo, si el cliente US-001 compró 1 unidad de producto T0004 hoy, se le cobrarían 350 CAD por cada unidad. Este precio proviene de un acuerdo comercial existente y activo con el cliente.      Los demás campos de la página proporcionan más información acerca del precio del producto y su coste (si se ha configurado en el producto maestro), así como la rentabilidad calculada.  
    * Si está seleccionada la opción Mostrar variantes del producto relacionadas, significa que hay acuerdos comerciales adicionales para las variantes del producto.  
7. Haga clic en la casilla Mostrar variantes del producto relacionadas.
    * Se muestra una lista de variantes del producto con información sobre sus dimensiones.  
8. En la lista, marque la línea que representa el color blanco.
    * Observe cómo el precio del producto es diferente ahora del mostrado anteriormente cuando no se había especificado por dimensión.  
9. Haga clic en Ver precios de venta.
    * La página Precios (ventas) muestra todos los acuerdos comerciales aplicables al producto, incluidas sus variantes.  
10. Cierre la página.

## <a name="find-the-applicable-discount"></a>Búsqueda del descuento aplicable
Asegúrese de que el campo Cuenta de cliente contiene el número de cliente US-001.    
1. En el campo Código de artículo, escriba 'T0012'.
    * Asegúrese de que el campo Cantidad se haya definido en 1.  
    * Los siguientes detalles de precios mostrados para el producto T0012 proceden de uno o varios acuerdos comerciales: el precio unitario es de 1.000 CAD, y el porcentaje de descuento es 5.  
2. Establezca el valor de cantidad en '20'.
    * El aumento de la cantidad del pedido hace que el descuento de línea que se ofrecerá al cliente cambie del 5 al 7 por ciento.  
    * El importe neto se calcula según el precio unitario, el descuento y la cantidad total.  
3. Haga clic en Ver descuento de línea.
    * Existen dos acuerdos de descuento de línea para el producto T0012: un 5 por ciento de descuento para pedidos de 1 a 10 y un 7 por ciento de descuento para pedidos de más de 10. Observe cómo se aplican los descuentos a un grupo de productos, en este ejemplo, el código de grupo 01, al cual pertenece el producto T0012.  
4. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
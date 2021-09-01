---
title: Creación de pedidos de sustitución de artículos
description: Los pedidos de sustitución de artículos se suelen crear una vez devuelto e inspeccionado un producto.
author: josaw1
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnReplaceItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 57bbb8eb638b990914dc00f9700ff0c1925c48852862b02e09f3f26415d3e347
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745511"
---
# <a name="create-an-item-replacement-order"></a>Creación de pedidos de sustitución de artículos 

[!include [banner](../includes/banner.md)]


Los pedidos de sustitución de artículos se suelen crear una vez devuelto e inspeccionado un producto. Sin embargo, si es necesario sustituir un artículo antes de su devolución, o si no se va a devolver el artículo original, puede crear un pedido de sustitución de artículo inmediatamente después de crear un pedido de devolución.

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a>Crear un pedido de sustitución después de recibir un artículo devuelto

1.  Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de devolución** \> **Todos los pedidos de devolución**.

2.  Cree un nuevo pedido de devolución o seleccione un pedido de devolución de la lista para abrir el formulario **Pedido de devolución - Número de RMA: %1, %2**.

3.  Haga clic en **Línea de devolución**, y después seleccione **Artículo de sustitución**.

4.  Seleccione el artículo por el que desee sustituir el artículo devuelto. Introduzca las especificaciones del artículo y, a continuación, haga clic en **Aplicar**.

5.  Haga clic en **Albarán** para generar el albarán del pedido de devolución. Un pedido de ventas se genera para el artículo de sustitución que ha seleccionado.
    
    Después de crear el pedido de ventas del artículo de sustitución, se buscan acuerdos de venta automáticamente y, si existe alguno aplicable, se aplica al pedido de ventas.

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a>Crear un pedido de sustitución antes de recibir un artículo devuelto

1.  Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de devolución** \> **Todos los pedidos de devolución**.

2.  Cree un nuevo pedido de devolución o seleccione un pedido de devolución de la lista para abrir el formulario **Pedido de devolución - Número de RMA: %1, %2**.

3.  Haga clic en **Buscar pedido de ventas** si desea identificar el pedido de ventas del artículo devuelto. Complete el formulario **Buscar pedido de ventas** y después haga clic en **Aceptar** para cerrar el formulario y volver al formulario **Pedido de devolución - número RMA: %1, %2**. La línea de pedido de ventas del artículo devuelto se copia en el pedido de devolución.

4.  Haga clic en **Pedido de sustitución** para abrir el formulario **Crear pedido de ventas**.

5.  Active la casilla de verificación **Copiar líneas de pedidos devueltos** para transferir detalles desde el pedido de devolución que seleccionó en el formulario **Pedido de devolución - Número de RMA: %1, %2** hasta este pedido de ventas.

6.  Introduzca o modifique los detalles según sea necesario.
    
    Si ha identificado el pedido de ventas en el paso 3 y la línea de pedido de ventas del artículo devuelto está vinculada a un acuerdo de venta, el identificador del acuerdo de venta aplicable para el pedido de sustitución del artículo se mostrará automáticamente en el campo **Id. del acuerdo de venta**.

7.  Haga clic en **Aceptar** para cerrar el formulario **Crear pedido de ventas** y abrir el formulario **Pedido de ventas**, donde puede continuar especificando la información del nuevo pedido de ventas. Cualquier línea de pedido de devolución aplicable se copiará en el nuevo pedido de ventas. 
    
    Si el identificador del acuerdo de venta se muestra automáticamente en el campo **Id. del acuerdo de venta**, el acuerdo de venta está vinculado al encabezado de pedido de ventas correspondiente al pedido de sustitución de artículo. Si existe un compromiso aplicable en el acuerdo de venta que no se ha satisfecho aún y se crea el pedido de ventas antes de que venza el acuerdo de venta, se establece un vínculo entre la línea del acuerdo de venta y la línea del pedido de ventas. Por lo tanto, la información del acuerdo de venta, como el precio del artículo, se copia en la nueva línea del pedido de ventas. 
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
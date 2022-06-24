---
title: Precio de recepción fijo
description: Este artículo explica cómo puede configurar y usar precios de recepción fijos en Microsoft Dynamics 365 Supply Chain Management.
author: raprofit
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 2630952f395d1a18202698b4d73b67ef4b760194
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907591"
---
# <a name="fixed-receipt-price"></a>Precio de recepción fijo

[!include [banner](../includes/banner.md)]

**Precio de recepción fijo** es una opción que puede seleccionar en un grupo de modelos de artículos cuando utiliza un modelo de inventario que no sea *Coste estándar* ni *Promedio móvil ponderado*. En las primeras versiones de Microsoft Dynamics AX, esta opción se denominó **Coste estándar**. Fue renombrado como **Precio de recepción fijo** cuando se introdujo el nuevo modelo de inventario de coste estándar en Dynamics AX 2012. Este artículo explica cómo puede configurar y usar precios de recepción fijos en Dynamics 365 Supply Chain Management.

## <a name="about-fixed-receipt-prices"></a>Acerca de los precios de recepción fijos

Cuando selecciona la casilla **Precio de recepción fijo** en la página **Grupo de modelo de artículo** para un artículo, el sistema usa el precio de recepción como un coste estándar para la recepción de inventario. Si el precio de compra y el precio de coste predeterminado del artículo que está configurado para un producto difieren, la diferencia se registra en la cuenta **Beneficio de precio de recepción fijo** o **Pérdida de precio de recepción fijo** y la contrapartida es la cuenta **Desviación de precio de recepción fijo** que especifique en la página **Perfil de contabilización de inventario**.

Dado que el **Precio de recepción fijo** se utiliza junto con diferentes modelos de inventario (como primero en entrar, primero en salir (FIFO); último en entrar, primero en salir (LIFO) y promedio ponderado), el proceso *Cierre y ajuste de inventario* seguirá creando liquidaciones y ajustes de acuerdo con el principio de inventario que seleccione en la página **Grupo de modelo de artículo**. Sin embargo, los ajustes se realizan solo a las emisiones del inventario.

Por ejemplo, configuró un producto con un grupo de modelos de artículos donde el campo **Modelo de inventario** está establecido en *FIFO* y está seleccionada la opción **Precio de recepción fijo**. Cuando recibe inventario a través de un pedido de compra, el valor del inventario se establece en el valor del precio de coste predeterminado del artículo en el momento de la recepción del producto. Cuando factura el pedido de compra, si el precio de la factura es diferente, el sistema registra el precio de coste predeterminado del producto expedido en la cuenta de inventario. Contabiliza la diferencia en la cuenta de pérdidas o ganancias de precio de recepción fijo. Posteriormente, cuando vende o consume el producto, el sistema usa el promedio móvil del artículo en el momento en que se registró la factura del pedido de ventas (a menos que use el marcado).

Al ejecutar el proceso *Cierre de inventario y ajuste*, el sistema crea una liquidación con al primera incidencia frente al primer recepción. La diferencia entre el precio de la recepción que se usó en la recepción y el promedio móvil que se usó en la incidencia se registra en un nuevo comprobante.

## <a name="enable-fixed-receipt-prices"></a>Habilitar precios de recepción fijos

Para habilitar precios de recepción fijos para un artículo, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Inventario \> Grupos de modelos de inventario**.
2. Cree un nuevo grupo de modelos de artículos o seleccione un grupo de modelos existente.
3. En la ficha desplegable **Método de gestión de costes y reconocimiento de costes**, seleccione la casilla **Precio de recepción fijo**.

    > [!NOTE]
    > No puede seleccionar la casilla **Precio de recepción fijo** si el campo **Modelo de inventario** está establecido en *Coste estándar* o *Media móvil*.

4. Cierre la página.

Después de habilitar la opción **Precio de recepción fijo**, debe actualizar su perfil de registro de inventario siguiendo estos pasos.

1. Vaya a **Gestión de inventarios \> Preparar \> Registro \> Registro**.
1. En la pestaña **Pedido de compra**, en la columna **Seleccionar**, seleccione **Beneficio de precio de recepción fijo**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Configure la nueva fila para que se aplique al grupo de modelos de artículos para el que habilitó el precio de recepción fijo y especifique la cuenta principal que se usa para registrar las ganancias del precio de recepción fijo para los pedidos de compra. Configure otras opciones según lo requiera.
1. En la columna **Seleccionar**, seleccione **Pérdida de precio de recepción fijo**. Agregue una nueva fila para que se aplique al grupo de modelos de artículos para el que habilitó el precio de recepción fijo y especifique la cuenta principal que se usa para registrar las pérdidas del precio de recepción fijo para los pedidos de compra. Configure otras opciones según lo requiera.
1. En la columna **Seleccionar**, seleccione **Desviación de precio de recepción fijo**. Agregue una nueva fila para que se aplique al grupo de modelos de artículos para el que habilitó el precio de recepción fijo y especifique la cuenta principal que se usa para registrar las desviaciones del precio de recepción fijo para los pedidos de compra. Configure otras opciones según lo requiera.
1. En la pestaña **Inventario**, en la columna **Seleccionar**, seleccione **Beneficio de precio de recepción fijo**. Agregue una nueva fila para que se aplique al grupo de modelos de artículos para el que habilitó el precio de recepción fijo y especifique la cuenta principal que se usa para registrar los beneficios del precio de recepción fijo para el inventario. Configure otras opciones según lo requiera.
1. En la columna **Seleccionar**, seleccione **Pérdida de precio de recepción fijo**. Agregue una nueva fila para que se aplique al grupo de modelos de artículos para el que habilitó el precio de recepción fijo y especifique la cuenta principal que se usa para registrar las pérdidas del precio de recepción fijo para el inventario. Configure otras opciones según lo requiera.

> [!NOTE]
> Normalmente recomendamos que los campos **Beneficio de precio de recepción fijo** y **Pérdida de precio de recepción fijo** utilicen la misma cuenta principal para los pedidos de compra y el inventario.

> [!IMPORTANT]
> Cuando cambia el valor en el campo **Precio**, en la ficha desplegable **Administrar costes** de la página **Productos expedidos**, el sistema no vuelve a evaluar automáticamente el inventario disponible. Como solución alternativa manual, abra al página **Cierre y ajuste** y seleccione **Ajuste \> Disponible** en el Panel de acciones. Luego seleccione los artículos que están disponibles y ajústelos al precio actual. Una clara ventaja de usar el modelo de inventario de coste estándar es que hace que el sistema vuelva a evaluar automáticamente el inventario disponible.

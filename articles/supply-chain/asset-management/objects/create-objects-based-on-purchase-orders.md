---
title: Crear activos en función de los pedidos de compra
description: En este tema se explica cómo puede crear una lista de artículos de activo que se puede usar como la base para crear activos para trabajos de mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6eba14e285f23338cad0243fca567b30c6d4d3f2
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571585"
---
# <a name="create-assets-based-on-purchase-orders"></a>Crear activos en función de los pedidos de compra

[!include [banner](../../includes/banner.md)]

 

En este tema se explica cómo puede crear una lista de artículos de activo que se puede usar como la base para crear activos para trabajos de mantenimiento en Administración de activos. Según los artículos del activo, podrá ver una lista de las líneas de pedido de compra que se han creado en esos artículos. El propósito de esta funcionalidad es crear fácilmente un activo en Administración de activos a partir de un pedido de compra.

Primero, se configuran los artículos que se van a usar para crear activos a partir de un pedido de compra en **Artículos de activo**. Después de crear una línea de pedido de compra, debe crear los activos en **Activos pendientes**. Se puede decidir en qué etapa del pedido de compra se debe crear el activo.


## <a name="select-asset-items"></a>Seleccionar artículos de activo

1. Haga clic en **Administración de activos** > **Configuración** > **Activos** > **Artículos**.
2. Haga clic en **Nuevo** para crear un nuevo artículo de activo.
3. Seleccione el elemento el campo **Número de artículo**. Al salir de ese campo, el nombre del artículo se inserta automáticamente en el campo **Nombre del producto**.
4. En la ficha desplegable **General**, seleccione un tipo de activo para el artículo.
5. Seleccione el fabricante y el modelo del activo para el artículo.
6. Guarde el artículo.


## <a name="create-assets-from-pending-assets"></a>Crear activos a partir de activos pendientes

1. Haga clic en **Administración de activos** > **Común** > **Activos** > **Activos pendiente**.
2. Verá una lista actualizada de los pedidos de compra en función de los artículos seleccionados en **Artículos de activo**.
3. Puede filtrar el estado de los pedidos de compra para seleccionar en qué estado de ciclo de vida debe crearse el activo. Por ejemplo, puede que solo quiera crear activos cuando se registre una recepción de productos en un pedido de compra.
4. Seleccione el vínculo **Número de referencia** en una línea de pedido de compra para ver información detallada sobre el artículo.
5. Si desea editar las dimensiones que se van a mostrar en la ficha desplegable **Dimensiones de inventario**, haga clic en el botón **Mostrar dimensiones** y realice las selecciones necesarias.
6. Si desea crear un activo a partir de una línea de pedido de compra, active la casilla de la columna **Marcar** para dicha línea en la página de lista, y haga clic en **Crear activos**. Se mostrará un mensaje para notificarle el identificador del activo.
7. Seleccione el activo en la lista **Todos los activos** y haga clic en el botón **Editar** para agregar más información al activo.
8. En **Activos pendientes**, si desea eliminar una línea porque no desea crear un activo, active la casilla en la columna **Marcar** para dicha línea y haga clic en **Descartar activos pendientes**. Se mostrará un mensaje para notificarle el identificador del activo. No se eliminan ni el pedido de compra ni el pedido de ventas, solo se elimina el registro a partir del cual podría haber creado un activo en **Administración de activos**.

>[!NOTE]
>Todas las dimensiones del producto (tamaño, color, configuración, etc.). se transfieren automáticamente a los atributos del activo. Las dimensiones de seguimiento (número de serie) se almacenan directamente en el activo en el momento de su creación.


## <a name="find-pending-assets"></a>Buscar activos pendientes

Puede ejecutar un **Recuento de activos pendientes** para ver si hay activos pendientes. Por ejemplo, esta función puede utilizarse para recibir una notificación cada vez que un activo pendiente esté listo para la creación de un activo.

1. Haga clic en **Administración de activos** > **Periódico** > **Activos** > **Recuento de activos pendientes**.
2. Haga clic en **Aceptar** para ejecutar el trabajo y actualizar la lista en **Activos pendientes**.
3. Puede configurar este trabajo para que se ejecute como un trabajo por lotes (por ejemplo, una vez al día).

**Precaución:** si se cambian los datos en un pedido de compra *después* de crear un activo partir del artículo correspondiente, esos cambios no se reflejarán en el activo.

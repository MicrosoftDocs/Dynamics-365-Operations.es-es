---
title: Crear un pedido de ventas para un producto configurable
description: Este procedimiento muestra cómo se debe aplicar una plantilla de configuración a un producto en un pedido de ventas.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e42f121d1efa66f85a3dd811606962b907ed177d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570594"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Crear un pedido de ventas para un producto configurable

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo se debe aplicar una plantilla de configuración a un producto en un pedido de ventas. Este ejemplo usa el modelo de altavoz D0006 en la empresa de datos de demostración USMF. Normalmente, un procesador del pedido de ventas utiliza este procedimiento.

## <a name="create-a-sales-order"></a>Crear un pedido de ventas

1. Vaya a **Ventas y marketing \> Espacios de trabajo \> Procesamiento y consulta de pedidos de venta**.
1. Seleccione **Nuevo**.
1. Seleccione **Pedido de ventas**.
1. En el campo **Cuenta de cliente**, seleccione *US-001*. 
1. Seleccione **Aceptar**.
1. En el campo **Código de artículo**, seleccione *D0006*.
    * Para esta tarea, debe seleccionar un producto configurable.  
1. Seleccione **Producto y suministro**.
1. Seleccione **Configurar línea**.
    * Tenga en cuenta que el precio ha cambiado, en función de la configuración seleccionada, y que ahora el campo **Incluir cable** se ha establecido como *Verdadero*.  
    * Anote el precio predeterminado y la configuración que se selecciona para el cable.  
1. Seleccione **Cargar plantilla**.
    * Este ejemplo muestra cómo puede aplicar una plantilla para seleccionar una configuración predefinida. Si utiliza este procedimiento como una guía de la tarea y desea ver los otros valores de atributo que están disponibles, debe seleccionar el botón **Desbloquear**.  
1. Seleccione **Aceptar**.
1. Seleccione **Aceptar**.
1. Expanda la sección **Detalles de línea.**
1. Seleccione la pestaña **Producto**.
    * La configuración del artículo se enumera ahora bajo las dimensiones del producto.  
1. Cierre la página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
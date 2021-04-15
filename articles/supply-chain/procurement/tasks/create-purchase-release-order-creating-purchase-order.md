---
title: Creación de un pedido parcial de compra al crear el pedido de compra
description: Este procedimiento muestra cómo usar un acuerdo de compra cuando se crea un pedido de compra.
author: kamaybac
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d2f02961f5f7da9bff389737b447e3b143dd72e3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812282"
---
# <a name="create-a-purchase-release-order-when-creating-the-purchase-order"></a>Creación de un pedido parcial de compra al crear el pedido de compra

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo usar un acuerdo de compra cuando se crea un pedido de compra. El acuerdo de compra se tiene que aplicar en el momento de crear el pedido de compra, ya que hay condiciones generales que se deben copiar al encabezado del pedido de compra. Esta tarea la realizará normalmente el agente de compras. Como requisito previo para este procedimiento, debe tener un acuerdo de compra en vigor con un compromiso de cantidad de productos para un proveedor y para artículos. El mismo procedimiento puede usarse si tiene un acuerdo de compra con otros tipos de compromisos. Puede ejecutar esta guía en la empresa de datos de demostración USMF. Si está usando USMF, puede ejecutar el procedimiento "Creación de un acuerdo de compra" primero para establecer las condiciones previas necesarias para este procedimiento.


## <a name="create-a-purchase-order"></a>Crear un pedido de compra
1. Apertura del espacio de trabajo de preparación del pedido de compra
2. Haga clic en Nuevo pedido de compra.
3. En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Expanda la sección General.
7. En el campo Acuerdo de compra, haga clic en el botón desplegable para abrir la búsqueda.
    * Todos los acuerdos disponibles para el proveedor se muestran aquí. Localice el acuerdo en vigor que desee utilizar.  
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Haga clic en Sí.
10. Haga clic en Aceptar

## <a name="add-a-line"></a>Adición de una línea
1. En el campo Código de artículo, escriba un valor.
    * Si hay dimensiones de inventario o de ubicación específicas en el compromiso, debe especificar los mismos valores en la línea de pedido de compra para poder usar el acuerdo.  
2. En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.
    * El sitio puede ya haberse cumplimentado con el valor predeterminado del pedido, o del proveedor. En tal caso, omita este paso.  
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Cantidad, especifique un número.
    * Verifique que el precio se haya copiado del compromiso.  

## <a name="look-up-the-commitment"></a>Búsqueda del compromiso
1. Haga clic en Actualizar línea.
2. Haga clic en Adjunto.
    * Aquí puede obtener los detalles del acuerdo de compra. Por ejemplo, puede ver el precio y si el precio y el descuento son fijos, lo que significa que, si cambia precios o descuentos en el pedido de compra a un valor diferente que en el compromiso, el sistema quitará el vínculo de modo que la línea de pedido de compra no satisfaga el compromiso. También puede ver si está seleccionada la opción Máximo aplicado, lo que significa que la cantidad en el compromiso no puede sobrepasarse sumando todas las compras que satisfacen el compromiso.  
3. Cierre la página.

## <a name="look-up-the-purchase-agreement"></a>Búsqueda del acuerdo de compra
1. En el panel de acciones, haga clic en General.
2. Haga clic en Acuerdo de compra.
3. Cierre la página.
4. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
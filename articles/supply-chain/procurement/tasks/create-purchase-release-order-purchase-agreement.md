---
title: Aplicar un acuerdo de compra al crear un pedido de compra
description: Este procedimiento muestra cómo usar un acuerdo de compra cuando se crea un pedido de compra.
author: kamaybac
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1913181e85929951ce240ac31a0ac3f1351f6ae51f6ed2790bae577b2100b308
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731256"
---
# <a name="apply-a-purchase-agreement-when-creating-a-purchase-order"></a>Aplicar un acuerdo de compra al crear un pedido de compra

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo usar un acuerdo de compra cuando se crea un pedido de compra. El acuerdo de compra se tiene que aplicar en el momento de crear el pedido de compra, ya que hay condiciones generales que se deben copiar al encabezado del pedido de compra. Esta tarea la realizará normalmente el agente de compras. Como requisito previo para este procedimiento, debe tener un acuerdo de compra en vigor con un compromiso de cantidad de productos para un proveedor y para artículos. El mismo procedimiento puede usarse si tiene un acuerdo de compra con otros tipos de compromisos.

## <a name="create-a-purchase-order"></a>Crear un pedido de compra

1. Vaya a **Producción y abastecimiento \> Espacios de trabajo \> Preparación de pedidos de compra**.
1. En el panel de acciones, seleccione **Nuevo pedido de compra**.
1. Se abre el cuadro de diálogo **Crear pedido de compra**. Seleccione una **Cuenta de proveedor**. Inspeccione y ajuste los otros campos de dirección según sea necesario.
1. Expanda la ficha desplegable **General**.
1. En el campo **Acuerdo de compra**, busque y seleccione el acuerdo efectivo que desea utilizar. Todos los acuerdos disponibles para el proveedor se muestran aquí.  
1. Seleccione **Sí**.
1. Seleccione **Aceptar**.

## <a name="add-a-line"></a>Agregar una línea

1. En el campo **Código de artículo**, escriba un valor. Si hay dimensiones de inventario o de ubicación específicas en el compromiso, debe especificar los mismos valores en la línea de pedido de compra para poder usar el acuerdo.
1. En el campo **Sitio**, seleccione el botón desplegable para abrir la búsqueda. El sitio puede ya haberse cumplimentado con el valor predeterminado del pedido, o del proveedor. En tal caso, omita este paso.  
1. En la lista, busque y seleccione el registro deseado.
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. En el campo **Cantidad**, especifique un número. Verifique que el precio se haya copiado del compromiso.  

## <a name="look-up-the-commitment"></a>Búsqueda del compromiso

1. Seleccione **Actualizar línea**.
1. Seleccione **Adjuntado**. Aquí puede obtener los detalles del acuerdo de compra. Por ejemplo, puede ver el precio y si el precio y el descuento son fijos, lo que significa que, si cambia precios o descuentos en el pedido de compra a un valor diferente que en el compromiso, el sistema quitará el vínculo de modo que la línea de pedido de compra no satisfaga el compromiso. También puede ver si está seleccionada la opción Máximo aplicado, lo que significa que la cantidad en el compromiso no puede sobrepasarse sumando todas las compras que satisfacen el compromiso.  
1. Cierre la página.

## <a name="look-up-the-purchase-agreement"></a>Búsqueda del acuerdo de compra

1. En el **Panel de acciones**, seleccione **General**.
1. Seleccione **Acuerdo de compra**.
1. Cierre la página.
1. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
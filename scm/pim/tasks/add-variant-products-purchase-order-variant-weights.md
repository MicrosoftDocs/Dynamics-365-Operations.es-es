--- 
title: Agregar variantes de productos a pedidos de compra con variantes de peso
description: "Este procedimiento le guía por los pasos para el uso de pesos de variante con el fin de rellenar automáticamente las líneas de pedido de compra para cada variante de un producto."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 410b3a88b3decb31ed6ce9373f14a11bf354acce
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a>Agregar variantes de productos a pedidos de compra con variantes de peso

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le guía por los pasos para el uso de pesos de variante con el fin de rellenar automáticamente las líneas de pedido de compra para cada variante de un producto. Al seleccionar la cantidad del producto que desea comprar, las líneas de pedido de compra se crean para todas las variantes del producto con las cantidades sugeridas basadas en los pesos configurados en las variantes de producto. Este procedimiento no incluye pasos para configurar valores de peso en dimensiones de producto y variantes de producto. Este procedimiento usa la empresa USRT en los datos de demostración.

1. Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.
2. Haga clic en Nuevo.
3. En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Expanda la sección General.
6. En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, busque y seleccione el registro deseado.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. Haga clic en Aceptar
12. Alterne la expansión de la sección Detalles de línea.
13. Haga clic en la pestaña Variantes.
14. Haga clic en Agregar línea.
15. En la lista, marque la fila seleccionada.
16. En el campo Código de artículo, escriba "0140".
17. Establezca el valor de cantidad en '1000'.
18. Haga clic en Guardar.



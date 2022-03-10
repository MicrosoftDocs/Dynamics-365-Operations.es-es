---
title: Agregar variantes de productos a pedidos de compra con variantes de peso
description: Este procedimiento le guía por los pasos para el uso de pesos de variante con el fin de rellenar automáticamente las líneas de pedido de compra para cada variante de un producto.
author: t-benebo
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f9523410447c102481dd2c709b1fa3dd69d03e8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565651"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a>Agregar variantes de productos a pedidos de compra con variantes de peso

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
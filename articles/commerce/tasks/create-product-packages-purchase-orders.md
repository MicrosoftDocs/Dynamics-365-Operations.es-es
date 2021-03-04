---
title: " Crear paquetes de producto para pedidos de compra"
description: Este procedimiento le guía por la creación de un paquete de producto y su uso en un pedido de compra.
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b0084c6b4acbf14e3afec552575d5be26114237
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415583"
---
# <a name="create-product-packages-for-purchase-orders"></a> Crear paquetes de producto para pedidos de compra

[!include [banner](../includes/banner.md)]

Este procedimiento le guía por la creación de un paquete de producto y su uso en un pedido de compra. El pedido de compra se usará para crear un pedido para un conjunto predefinido de productos. Este procedimiento usa la empresa de datos de demostración USRT.


## <a name="create-a-product-package"></a>Crear un paquete de producto
1. Vaya a Retail y Commerce > Gestión del inventario > Reabastecimiento > Paquetes de productos.
2. Haga clic en Nuevo.
3. En el campo Número de paquete, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. Haga clic en Agregar.
8. En el campo Código de artículo, escriba "0160".
9. En el campo Tamaño, haga clic en el botón desplegable para abrir la búsqueda.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. En el campo Cantidad, especifique un número.
12. Haga clic en Agregar.
13. En el campo Código de artículo, escriba "0160".
14. En el campo Número de variante, haga clic en el botón desplegable para abrir la búsqueda.
15. En la lista, haga clic en el vínculo de la fila seleccionada.
16. En el campo Cantidad, especifique un número.
17. Haga clic en Agregar.
18. En el campo Código de artículo, escriba "0175".
19. En el campo Cantidad, especifique un número.
20. Haga clic en Guardar.
21. Cierre la página.

## <a name="add-package-to-purchase-order"></a>Agregar paquete a pedido de compra
1. Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.
2. Haga clic en Nuevo.
3. En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, seleccione el mismo proveedor que el paquete de producto para el que se creó anteriormente, si se seleccionó un proveedor.
5. Expanda la sección General.
6. En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, haga clic en el vínculo de la fila seleccionada.
10. Haga clic en Aceptar
11. Alterne la expansión de la sección Detalles de línea.
12. Haga clic en la ficha Paquetes de productos.
13. Haga clic en Línea de pedido de compra.
14. Haga clic en Crear líneas de paquete.
15. En la lista, busque y seleccione el paquete de producto creado en el paso anterior.
16. En el campo Cantidad, especifique un número.
17. Haga clic en Crear.
18. Haga clic en Guardar.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
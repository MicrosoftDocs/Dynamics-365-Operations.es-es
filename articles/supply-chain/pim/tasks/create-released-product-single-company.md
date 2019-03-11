---
title: Creación de un producto liberado para una sola empresa
description: Este procedimiento le muestra cómo crear un único producto liberado en el contexto de una sola unidad legal.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9265ee4311ac89ae88ff7dd089519251828b1e3c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "315967"
---
# <a name="create-a-released-product-for-a-single-company"></a>Creación de un producto liberado para una sola empresa

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo crear un único producto liberado en el contexto de una sola unidad legal. Una vez creado el producto liberado, estará disponible inmediatamente solo en esta unidad. Puede examinar este procedimiento en la empresa de datos de demostración USMF. Esta tarea la lleva a cabo normalmente un diseñador de productos.


## <a name="create-a-released-product"></a>Creación de un producto liberado
1. Vaya a Productos emitidos.
2. Haga clic en Nuevo.
3. En el campo Número de producto, escriba un valor.
    * Si un número de producto no se especifica automáticamente en el campo Número de producto, escriba un número de producto único. Este paso solo es necesario si no se ha configurado ninguna secuencia numérica para los números de producto.  
4. En el campo Nombre de producto, escriba un valor.
    * El nombre del producto se establece de forma predeterminada como el nombre de búsqueda. Si es necesario, puede seleccionar cambiar el nombre de búsqueda.  
5. En el campo Grupo de modelos de artículo, haga clic en el botón desplegable para abrir la búsqueda.
    * Los grupos de modelos de artículos contienen configuraciones que determinan la forma de controlar y gestionar artículos en las emisiones y recepciones de artículos. Las configuraciones también determinan cómo se calcula el consumo de artículos.  
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo Grupo de artículos, haga clic en el botón desplegable para abrir la búsqueda.
    * Los grupos de artículos se utilizan para administrar el inventario dividiendo los artículos de inventario en grupos en función de sus características. Por ejemplo, para gestionar cómo se registra la información en las cuentas principales, puede crear una serie de diferentes grupos de artículos asociados a cuentas principales concretas. Esto permite realizar un seguimiento del valor de inventario de los artículos en distintas etapas.  
9. En la lista, busque y seleccione el registro deseado.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. En el campo Grupo de dimensiones de almacenamiento, haga clic en el botón desplegable para abrir la búsqueda.
    * Las dimensiones de almacenamiento ayudan a controlar el modo en que los artículos se almacenan y se toman del inventario. Por ejemplo, una dimensión de almacenamiento puede ser el sitio y el almacén.  
12. En la lista, busque y seleccione el registro deseado.
13. En la lista, haga clic en el vínculo de la fila seleccionada.
14. En el campo Grupo de dimensiones de seguimiento, haga clic en el botón desplegable para abrir la búsqueda.
    * El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento puede agregar a un producto. Por ejemplo, el número de lote y el número de serie se utilizan para hacer un seguimiento de los artículos de inventario.  
15. En la lista, busque y seleccione el registro deseado.
16. En la lista, haga clic en el vínculo de la fila seleccionada.
17. En el campo Unidad de inventario, haga clic en el botón desplegable para abrir la búsqueda.
    * La unidad de inventario determina cómo se cuantifica el producto cuando se ha almacenado en el inventario.  
18. En la lista, busque y seleccione el registro deseado.
19. En la lista, haga clic en el vínculo de la fila seleccionada.
20. En el campo Unidad de compra, haga clic en el botón desplegable para abrir la búsqueda.
    * La unidad de compra determina cómo se cuantifica el producto cuando lo ha comprado un proveedor.  
21. En la lista, busque y seleccione el registro deseado.
22. En la lista, haga clic en el vínculo de la fila seleccionada.
23. En el campo Unidad de venta, haga clic en el botón desplegable para abrir la búsqueda.
    * La unidad de ventas determina cómo se cuantifica el producto cuando se ha vendido a un cliente.  
24. En la lista, busque y seleccione el registro deseado.
25. En la lista, haga clic en el vínculo de la fila seleccionada.
26. En el campo Unidad de L. MAT, haga clic en el botón desplegable para abrir la búsqueda.
    * La unidad de L. MAT determina cómo se cuantifica el producto cuando se incluye en una lista de materiales (L. MAT).  
27. En la lista, busque y seleccione el registro deseado.
28. En la lista, haga clic en el vínculo de la fila seleccionada.
29. En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.
    * El grupo de impuestos de artículo del grupo de impuestos sobre las ventas determina cómo se calculan los impuestos de venta para cada artículo.  
30. En la lista, busque y seleccione el registro deseado.
31. En la lista, haga clic en el vínculo de la fila seleccionada.
32. En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.
    * El grupo de impuestos de artículo del grupo de impuestos de compra determina cómo se calculan los impuestos de compra para cada artículo.  
33. En la lista, busque y seleccione el registro deseado.
34. En la lista, haga clic en el vínculo de la fila seleccionada.
35. Haga clic en Aceptar

## <a name="add-product-characteristics"></a>Adición de características del producto
1. Expanda o contraiga la sección Administrar inventario.
2. En el campo Peso neto, escriba un número.
3. En el campo Tara, escriba un número.
4. En el campo Profundidad bruta, especifique un número.
5. En el campo Ancho bruto, especifique un número.
6. En el campo Alto bruto, especifique un número.
7. En el campo Volumen, escriba un número.

## <a name="add-financial-dimensions"></a>Adición de dimensiones financieras
1. Expanda o contraiga la sección Dimensiones financieras.
2. En el campo de unidad de negocio, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo de centro de coste, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo Departamento, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, busque y seleccione el registro deseado.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. En el campo de grupo de artículos, haga clic en el botón desplegable para abrir la búsqueda.
12. En la lista, busque y seleccione el registro deseado.
13. En la lista, haga clic en el vínculo de la fila seleccionada.


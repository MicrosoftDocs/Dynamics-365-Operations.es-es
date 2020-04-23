---
title: Crear una nomenclatura de números de producto para las variantes de producto configuradas
description: Este procedimiento muestra cómo configurar una nomenclatura del número de producto para las variantes de producto configuradas y cómo se puede adjuntar a un producto maestro configurable.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6970b37594bc999f8f1ea112a6056f15faccc02c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213264"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>Crear una nomenclatura de números de producto para las variantes de producto configuradas

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo configurar una nomenclatura del número de producto para las variantes de producto configuradas y cómo se puede adjuntar a un producto maestro configurable. Este procedimiento también demuestra la manera de crear una nomenclatura de la configuración para un componente del modelo de configuración de productos. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. La nueva nomenclatura del número de producto se asigna al producto maestro D0004. Esta tarea normalmente la realiza un diseñador de productos.


## <a name="create-a-product-number-nomenclature"></a>Crear una nomenclatura de número de producto
1. Haga clic en Definición de modelo de variante del producto.
2. Haga clic en Nomenclatura de producto.
3. Haga clic en Nuevo.
4. En el campo Nombre, escriba un valor.
5. En el campo Descripción, escriba un valor.
6. Haga clic en Agregar.
7. Haga clic en Número de producto maestro.
8. Haga clic en Agregar.
9. Haga clic en Constante de texto.
10. En la lista, marque la fila seleccionada.
11. En el campo Texto, escriba un valor.
12. Haga clic en Agregar.
13. Haga clic en Configuración.
14. Cierre la página.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Asignar la nomenclatura del número de producto a un producto maestro
1. Haga clic en Productos maestros.
2. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Número de producto con un valor de "D".
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Haga clic en Editar.
5. Seleccione Sí en el campo Usar nomenclatura.
6. En el campo Nomenclatura del número de variante del producto, especifique o seleccione un valor.
7. Cierre la página.
8. Cierre la página.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Crear una nomenclatura para un componente de modelo de configuración de productos
1. Haga clic en Modelos de configuración del producto.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Haga clic en Editar.
5. Seleccione Sí en el campo Usar nomenclatura de configuración.
6. Haga clic en Agregar.
7. Haga clic en Valor de atributo.
8. En la lista, marque la fila seleccionada.
9. En el campo Atributo, especifique o seleccione un valor.
10. Haga clic en Agregar.
11. Haga clic en Constante de texto.
12. En la lista, marque la fila seleccionada.
13. En el campo Texto, escriba un valor.
14. Haga clic en Agregar.
15. Haga clic en Valor de atributo.
16. En la lista, marque la fila seleccionada.
17. En el campo Atributo, especifique o seleccione un valor.
18. Haga clic en Agregar.
19. Haga clic en Constante de texto.
20. En la lista, marque la fila seleccionada.
21. En el campo Texto, escriba un valor.
22. Haga clic en Agregar.
23. Haga clic en Valor de atributo.
24. En la lista, marque la fila seleccionada.
25. En el campo Atributo, especifique o seleccione un valor.
26. Haga clic en Agregar.
27. Haga clic en Constante de texto.
28. En la lista, marque la fila seleccionada.
29. En el campo Texto, escriba un valor.
30. Haga clic en Agregar.
31. Haga clic en Valor de atributo.
32. En la lista, marque la fila seleccionada.
33. En el campo Atributo, especifique o seleccione un valor.
34. Haga clic en Agregar.
35. Haga clic en Constante de texto.
36. En la lista, marque la fila seleccionada.
37. En el campo Texto, escriba un valor.
38. Haga clic en Agregar.
39. Haga clic en Valor de secuencia numérica.
40. En la lista, marque la fila seleccionada.
41. En el campo Código de secuencia numérica, especifique o seleccione un valor.
42. Cierre la página.
43. Cierre la página.
44. Cierre la página.


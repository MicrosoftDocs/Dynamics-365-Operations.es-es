---
title: Completar la configuración básica de un producto maestro liberado
description: Este procedimiento muestra cómo completar la configuración mínima requerida para poder usar el producto maestro en versiones de L. MAT.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d3a91977c38c0ce0f9fe114bec943c7cb32a5d4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568783"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Completar la configuración básica de un producto maestro liberado

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo completar la configuración mínima requerida para poder usar el producto maestro en versiones de L. MAT.

Este es el tercer procedimiento de ocho que explica cómo crear combinaciones para la configuración basada en dimensiones. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a Gestión de información de productos > Productos > Productos emitidos.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione el producto maestro que ha emitido en el segundo procedimiento. Este producto maestro se crea con la tecnología de configuración basada en dimensiones.  
3. En el panel de acciones, haga clic en Producto.
4. Haga clic en Grupos de dimensiones para abrir el cuadro de diálogo.
5. En el campo Grupo de dimensiones de almacenamiento, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
    * El grupo de dimensiones de almacenamiento determina qué dimensiones de almacenamiento se usan para la transacción de producto. Seleccione Sitio para este procedimiento.  
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo Grupo de dimensiones de seguimiento, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, busque y seleccione el registro deseado.
    * El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento se usan para la transacción de producto. Seleccione Ninguno para este procedimiento.  
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. Haga clic en Aceptar
12. En la lista, haga clic en el vínculo de la fila seleccionada.
13. Haga clic en Editar.
    * Abra el formulario Detalles de producto emitido para continuar con la tarea de configuración.  
14. En el campo Grupo de modelos de artículo, haga clic en el botón desplegable para abrir la búsqueda.
15. En la lista, busque y seleccione el registro deseado.
    * Los grupos de modelos de artículos contienen ajustes que determinan la forma de controlar y gestionar artículos en emisiones y recepciones de artículos. También determina la forma de calcular el consumo de los artículos. Seleccione FIFO para este procedimiento.  
16. En la lista, haga clic en el vínculo de la fila seleccionada.
17. Expanda o contraiga la sección Gestionar costes.
18. En el campo Grupo de artículos, haga clic en el botón desplegable para abrir la búsqueda.
19. En la lista, busque y seleccione el registro deseado.
    * Los grupos de artículos se utilizan para administrar el inventario dividiendo los artículos en grupos. Seleccione CarAudio para este procedimiento.  
20. En la lista, haga clic en el vínculo de la fila seleccionada.
21. En el panel de acciones, haga clic en Plan.
22. Haga clic en Configuración predeterminada de pedido.
23. En el campo Tipo de pedido predeterminado, seleccione una opción.
    * Seleccione Producción para especificar que la opción de suministro predeterminado para este producto maestro sea producirlo.  
24. Cierre la página.
25. Cierre el formulario Detalles de producto emitido.


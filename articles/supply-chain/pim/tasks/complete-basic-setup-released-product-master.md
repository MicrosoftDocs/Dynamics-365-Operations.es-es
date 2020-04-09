---
title: Completar la configuración básica de un producto maestro liberado
description: En este tema se muestra cómo completar la configuración mínima requerida para poder usar el producto maestro en versiones de L. MAT.
author: ShylaThompson
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f93f3db022b7b338bfa18ff6aea79f8086ea997f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147949"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Completar la configuración básica de un producto maestro liberado

[!include [banner](../../includes/banner.md)]

En este tema se muestra cómo completar la configuración mínima requerida para poder usar el producto maestro en versiones de L. MAT.

Este es el tercer procedimiento de ocho que explica cómo crear combinaciones para la configuración basada en dimensiones. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Productos > Productos emitidos**.
2. En la lista, busque y seleccione el registro deseado. Seleccione el producto maestro que ha emitido en el segundo procedimiento. Este producto maestro se crea con la tecnología de configuración basada en dimensiones.  
3. En el panel de acciones, seleccione **Producto**.
4. Seleccione **Grupos de dimensiones** para abrir el cuadro de diálogo.
5. En el campo **Grupo de dimensiones de almacenamiento**, haga clic en el botón de la lista desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado. El grupo de dimensiones de almacenamiento determina qué dimensiones de almacenamiento se usan para la transacción de producto. Seleccione **Sitio** para este procedimiento.  
7. En el campo **Grupo de dimensiones de seguimiento**, seleccione en el botón de la lista desplegable para abrir la búsqueda.
8. En la lista, busque y seleccione el registro deseado. El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento se usan para la transacción de producto. Seleccione **Ninguno** para este procedimiento.  
9. Haga clic en **Aceptar**.
10. Haga clic en **Editar**.
11. En el campo **Grupo de modelos de artículo**, seleccione el botón de la lista desplegable para abrir la búsqueda.
12. En la lista, busque y seleccione el registro deseado. Los grupos de modelos de artículos contienen ajustes que determinan la forma de controlar y gestionar artículos en emisiones y recepciones de artículos. También determina la forma de calcular el consumo de los artículos. Seleccione **FIFO** para este procedimiento.  
13. Expanda la sección **Administrar costes**.
14. En el campo **Grupo de artículos**, seleccione el botón de la lista desplegable para abrir la búsqueda.
15. En la lista, busque y seleccione el registro deseado. Los grupos de artículos se utilizan para administrar el inventario dividiendo los artículos en grupos. Seleccione **CarAudio** para este procedimiento.  
16. En el panel de acciones, haga clic en **Plan**.
17. Seleccione **Configuración predeterminada de pedido**.
18. En el campo **Tipo de pedido predeterminado**, seleccione una opción. Seleccione **Producción** para especificar que la opción de suministro predeterminado para este producto maestro sea producirlo.  
19. Seleccione **Guardar**.
20. Cierre la página.
21. Cierre el formulario **Detalles de producto emitido**.


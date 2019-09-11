---
title: Creación y mantenimiento de un bloqueo del inventario
description: Este procedimiento muestra cómo impedir que se reserve inventario disponible físico a través de otros documentos de origen de salida mediante el bloqueo de inventario.
author: perlynne
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2485eaf31226b11106895074ae0ad95e561777b
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916608"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Creación y mantenimiento de un bloqueo del inventario

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo impedir que se reserve inventario disponible físico a través de otros documentos de origen de salida mediante el bloqueo de inventario. Puede ejecutar el procedimiento en la empresa de datos de demostración USMF con los valores de ejemplo que se muestran. Necesita tener un artículo con inventario disponible físico antes de comenzar este procedimiento.


## <a name="create-an-inventory-blocking"></a>Creación de un bloqueo de inventario
1. En el **Panel de exploración**, vaya a **Módulos > Gestión de inventario > Tareas periódicas > Bloqueo del inventario**.
2. Haga clic en **Nuevo**.
3. En el campo **Código de artículo**, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, seleccione el artículo que desee elegir. Seleccione un número de artículo con inventario disponible físico que desee bloquear. Si está usando USMF, puede seleccionar el artículo M9201.  
5. En el campo **Cantidad**, especifique un número. Si está usando el artículo M9201, es necesario seleccionar un valor inferior a 200.
6. Expanda la ficha desplegable **Dimensiones de inventario**.
7. En el campo **Almacén**, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, busque y seleccione el registro deseado. Si está usando el artículo M9201, puede seleccionar el almacén 51.  
9. Haga clic en **Guardar**.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Actualización de las condiciones de bloqueo de inventario
1. En la ficha desplegable **General**, en el campo **Cantidad**, especifique un número. Actualice el campo de cantidad de inventario para reflejar la cantidad que bloquear.  
2. En el campo **Fecha prevista**, especifique una fecha. Es posible que desee indicar cuándo se espera que el inventario bloqueado quede disponible para reserva asignando una fecha prevista. Si la opción Recepciones previstas está seleccionada para el bloqueo de inventario, como lo está de manera predeterminada cuando se crea manualmente un bloqueo, esta fecha aparecerá en la transacción prevista.  
3. Haga clic en **Guardar**.

## <a name="remove-the-inventory-blocking"></a>Eliminación del bloqueo de inventario
1. En el **panel de acciones**, haga clic en **Eliminar**.
2. Haga clic en **Sí**.
3. Cierre la página.


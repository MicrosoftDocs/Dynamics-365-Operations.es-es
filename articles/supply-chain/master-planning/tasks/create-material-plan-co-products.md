--- 
title: "Creación de un plan de materiales para coproductos"
description: "El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-material-plan-for-co-products"></a>Creación de un plan de materiales para coproductos

[!include [task guide banner](../../includes/task-guide-banner.md)]

El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula. La empresa de datos de demostración utilizada para crear este procedimiento es USP2.


## <a name="create-requirement-for-a-co-product"></a>Creación de un requisito para un coproducto
1. Vaya al panel predeterminado.
2. Haga clic en Consulta y procesamiento de pedido de ventas.
3. Haga clic en Nuevo.
4. Haga clic en Pedido de ventas.
5. En el campo Cuenta de cliente, escriba un valor.
    * Ejemplo: US-001  
6. Haga clic en Aceptar
7. En el campo Código de artículo, escriba un valor.
    * Ejemplo: P6003  
8. En el campo Cantidad, especifique un número.
    * Ejemplo: 50000  
9. Haga clic en Guardar.

## <a name="create-a-material-plan-for-co-products"></a>Creación de un plan de materiales para coproductos
1. Haga clic en Planificación maestra.
2. En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Ejemplo: Plan maestro  
4. Haga clic en Ejecutar.
5. Expanda o contraiga la sección Registros que incluir.
6. Haga clic en Filtro.
7. En la lista, seleccione la fila para Campo = Número de artículo.
8. En el campo Criterios, escriba un valor.
    * Ejemplo: P6003  
9. Haga clic en Aceptar
10. Haga clic en Aceptar
11. Haga clic en Pedidos planificados.
12. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Número de artículo con un valor de "P6000".
    * Filtre por el producto de fórmula que tiene como coproducto el producto para el cual ha creado un pedido de ventas.  
13. En la lista, marque la fila seleccionada.
    * Seleccione cualquiera de las filas que haya devuelto el filtro.  
14. En la lista, haga clic en el vínculo de la fila seleccionada.
15. Expanda o contraiga la sección Diagrama de árbol.
16. En la lista, haga clic en el vínculo de la fila seleccionada.
    * El pedido planificado se adjunta al pedido de ventas para el coproducto.  
17. Cierre la página.



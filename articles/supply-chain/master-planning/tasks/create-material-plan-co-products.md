---
title: Creación de un plan de materiales para coproductos
description: El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a8e9067cdd8851da31c07a92217001e447f400d4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983400"
---
# <a name="create-a-material-plan-for-co-products"></a>Creación de un plan de materiales para coproductos

[!include [banner](../../includes/banner.md)]

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

## <a name="create-a-material-plan-for-co-products"></a>Crear un plan de materiales para coproductos
1. Cierre la página.
2. Cierre la página.
3. Haga clic en Planificación maestra.
4. En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Ejemplo: Plan maestro  
6. Haga clic en Ejecutar.
7. Expanda o contraiga la sección Registros que incluir.
8. Haga clic en Filtro.
9. En la lista, seleccione la fila para Campo = Número de artículo.
10. En el campo Criterios, escriba un valor.
    * Ejemplo: P6003  
11. Haga clic en Aceptar
12. Haga clic en Aceptar
13. Haga clic en Pedidos planificados.
14. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Número de artículo con un valor de "P6000".
    * Filtre por el producto de fórmula que tiene como coproducto el producto para el cual ha creado un pedido de ventas.  
15. En la lista, marque la fila seleccionada.
    * Seleccione cualquiera de las filas que haya devuelto el filtro.  
16. En la lista, haga clic en el vínculo de la fila seleccionada.
17. Expanda o contraiga la sección Diagrama de árbol.
18. En la lista, haga clic en el vínculo de la fila seleccionada.
    * El pedido planificado se adjunta al pedido de ventas para el coproducto.  
19. Cierre la página.

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

## <a name="create-a-material-plan-for-co-products"></a>Crear un plan de materiales para coproductos
1. En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.
2. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Ejemplo: Plan maestro  
3. Haga clic en Ejecutar.
4. Expanda o contraiga la sección Registros que incluir.
5. Haga clic en Filtro.
6. En la lista, seleccione la fila para Campo = Número de artículo.
7. En el campo Criterios, escriba un valor.
    * Ejemplo: P6003  
8. Haga clic en Aceptar
9. Haga clic en Aceptar
10. Haga clic en Pedidos planificados.
11. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Número de artículo con un valor de "P6000".
    * Filtre por el producto de fórmula que tiene como coproducto el producto para el cual ha creado un pedido de ventas.  
12. En la lista, marque la fila seleccionada.
    * Seleccione cualquiera de las filas que haya devuelto el filtro.  
13. En la lista, haga clic en el vínculo de la fila seleccionada.
14. Expanda o contraiga la sección Diagrama de árbol.
15. En la lista, haga clic en el vínculo de la fila seleccionada.
    * El pedido planificado se adjunta al pedido de ventas para el coproducto.  
16. Cierre la página.
17. Haga clic en Planificación maestra.
18. Vaya a Planificación maestra > Configuración > Parámetros de planificación maestra.
19. Seleccione No en el campo Deshabilitar todos los procesos de planificación.
20. Cierre la página.


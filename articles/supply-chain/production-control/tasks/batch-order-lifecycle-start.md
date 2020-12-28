---
title: Ciclo de vida de pedidos de lote desde la creación hasta el inicio
description: Este procedimiento le lleva por la primera parte del ciclo de vida de un pedido de lote.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e57cd9254185b73f544e8ff4f7658cf743b672f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436584"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a>Ciclo de vida de pedidos de lote desde la creación hasta el inicio

[!include [banner](../../includes/banner.md)]

Este procedimiento le lleva por la primera parte del ciclo de vida de un pedido de lote.

Desde la creación, la estimación de costes y la programación de trabajos de sobreproducción hasta el inicio real de un pedido de lote.



La empresa de datos de prueba utilizada para crear este procedimiento es USMF. 



Los requisitos previos para ejecutar el procedimiento con otro conjunto de datos son un producto liberado con una versión de ruta y fórmula activa.


## <a name="create-a-batch-order"></a>Crear un pedido de lote
1. Vaya a Todos los pedidos de producción.
2. Haga clic en Nuevo pedido de lote.
3. En el campo Número de artículo, especifique o seleccione un valor.
4. Haga clic en Crear.
5. Use un filtro rápido para filtrar el campo Producción con un valor "b".

## <a name="view-production-formula-and-expected-co-products"></a>Ver fórmula de la producción y coproductos previstos
1. En el panel de acciones, haga clic en Pedido de producción.
2. Haga clic en Fórmula.
3. Cierre la página.
4. Haga clic en Productos conjuntos.
5. Cierre la página.

## <a name="estimate-the-batch-order"></a>Estimar el pedido de lote
1. Haga clic en Estimación.
2. Haga clic en Aceptar
3. En el panel de acciones, haga clic en Gestionar costes.
4. Haga clic en Ver detalles de cálculo.
5. Cierre la página.

## <a name="release-the-batch-order"></a>Liberar el pedido de lote
1. En el panel de acciones, haga clic en Pedido de producción.
2. Haga clic en Liberar.
3. Haga clic en Aceptar

## <a name="schedule-production-jobs"></a>Programar trabajos de producción
1. En el panel de acciones, haga clic en Programar.
2. Haga clic en Programar trabajos.
3. Seleccione No en el campo Capacidad limitada.
4. Seleccione No en el campo Material limitado.
5. Haga clic en Aceptar
6. En el panel de acciones, haga clic en Pedido de producción.
7. Haga clic en Todos los trabajos.
8. Cierre la página.

## <a name="start-the-batch-order"></a>Iniciar el pedido de lote
1. Haga clic en Inicio.
2. Haga clic en la pestaña General.
3. Seleccione No en el campo Registrar ahora la lista de selección.
4. Haga clic en Aceptar
5. En el panel de acciones, haga clic en Ver.
6. Haga clic en Lista de selección.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Cierre la página.
9. Cierre la página.
10. Haga clic en tarjeta de ruta.
11. En la lista, haga clic en el vínculo de la fila seleccionada.
12. Cierre la página.
13. Cierre la página.


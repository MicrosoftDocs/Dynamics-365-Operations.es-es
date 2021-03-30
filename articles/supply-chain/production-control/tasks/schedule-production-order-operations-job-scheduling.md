---
title: Programar un pedido de producción con programación de operaciones y trabajo
description: En tema se centra en la programación de un pedido de producción con programación de operaciones y programación de trabajos.
author: ChristianRytt
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32ace204f1ec79cc8f9ce10ebfdc3606879e40d4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215850"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Programar un pedido de producción con programación de operaciones y trabajo

[!include [banner](../../includes/banner.md)]

En tema se centra en la programación de un pedido de producción con programación de operaciones y programación de trabajos. No se crea ningún trabajo con la programación de tareas mientras que los trabajos se crean con programación de operaciones. La empresa de datos de prueba utilizada para crear esta tarea es USMF. Este procedimiento está pensado para el director de producción, el planificador de producción o el supervisor de planta que trabaja en un entorno de fabricación discreto.


## <a name="create-a-production-order"></a>Crear un pedido de producción
1. En el panel de navegación, vaya a **Módulos > Control de producción > Pedidos de producción > Todos los pedidos de producción**.
2. Seleccione **Nuevo pedido de producción**.
3. En el campo **Número de artículo**, especifique o seleccione un valor. Seleccione el número de artículo **D0001**.  
4. Seleccione **Crear**.

## <a name="schedule-operations-for-the-production-order"></a>Programe operaciones para el pedido de producción
1. Marque la fila recién creada.      
2. En el panel de acciones, seleccione **Programación**.
3. Seleccione **Programar operaciones**.
4. En el campo **Dirección de programación**, seleccione **A partir de la fecha de programación**.
5. En el campo **Fecha de programación**, especifique una fecha. Seleccione una fecha futura, por ejemplo, hoy más una semana. Con la dirección de programación seleccionada, el pedido de producción se programará hacia delante a partir de esta fecha.  
6. Seleccione **Aceptar**.
7. En la lista, marque la fila seleccionada. Tenga en cuenta que el estado cambia a **Programado**. 
8. Seleccione **Todos los trabajos**. Tenga en cuenta que ningún trabajo se crea con la programación de operaciones.  
9. Cierre la página.

## <a name="schedule-jobs-for-the-production-order"></a>Programe tareas para el pedido de producción
1. En el panel de acciones, seleccione **Programación**.
2. Seleccione **Programar trabajos**.
3. En el campo **Dirección de programación**, seleccione **A partir de la fecha de programación**.
4. En el campo **Fecha de programación**, especifique una fecha. Seleccione una fecha en el futuro, por ejemplo, hoy más una semana. Con la dirección de programación seleccionada, el pedido de producción se programará hacia delante a partir de esta fecha.  
5. Seleccione **Aceptar**.
6. En el panel de acciones, seleccione **Pedido de producción**.
7. Seleccione **Todos los trabajos**. Tenga en cuenta que basándose en la ruta activa, se crean 5 trabajos con la programación de trabajos.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
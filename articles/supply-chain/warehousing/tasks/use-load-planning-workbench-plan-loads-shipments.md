--- 
title: "Planificar cargas y envíos mediante el área de trabajo de planificación de la carga"
description: "Este procedimiento muestra cómo usar el área de trabajo de planificación de cargas para crear una carga para un pedido de ventas."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f840a4c15305af5f55451ae7f1cec2da25e685a4
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Planificar cargas y envíos mediante el área de trabajo de planificación de la carga

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo usar el área de trabajo de planificación de cargas para crear una carga para un pedido de ventas. Es necesario crear primero el pedido de ventas. Este procedimiento forma parte del trabajo diario del coordinador de transporte. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-a-sales-order"></a>Crear un pedido de ventas
1. Vaya a Clientes > Pedidos > Todos los pedidos de venta.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.
4. Seleccione la cuenta US-004.
5. Haga clic en Aceptar
6. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
7. Seleccione el artículo A0001.
    * A0001 está habilitado para administración del transporte.  
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo Cantidad, especifique un número.
10. En el campo Almacén, escriba "24".
    * En este ejemplo, seleccione el almacén 24. Este almacén está habilitado para administrar el transporte y gestionar almacenes de forma avanzada.  
11. Haga clic en Guardar.
12. Cierre la página.

## <a name="create-a-new-load"></a>Creación de una nueva carga
1. Vaya a Administración de transporte > Planificación > Área de trabajo de planificación de la carga.
2. Haga clic en la ficha Líneas de ventas.
    * Ahora construirá la carga para el pedido de ventas que acaba de crear. Las cargas se pueden crear según la oferta y la demanda de los pedidos de compra, los pedidos de transferencia y los pedidos de ventas.  
3. En el panel de acciones, haga clic en Oferta y demanda.
4. Haga clic en A nueva carga.
5. En el campo Id. de plantilla de carga, haga clic en el botón desplegable para abrir la búsqueda.
    * La plantilla de carga define las medidas máximas para el peso y el volumen de la carga completa. Por ejemplo, la plantilla de carga puede representar el tamaño de un contenedor o de un camión.  
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. Haga clic en Aceptar

## <a name="rate-and-route-the-load"></a>Tasa y ruta para la carga
1. Haga clic en Clasificación y ruta.
2. Haga clic en Área de trabajo de la ruta de la tasa.
3. Haga clic en Opciones de tasas.
4. En la lista, busque y seleccione el registro deseado.
5. Haga clic en Asignar.
6. Cierre la página.
7. Cierre la página.



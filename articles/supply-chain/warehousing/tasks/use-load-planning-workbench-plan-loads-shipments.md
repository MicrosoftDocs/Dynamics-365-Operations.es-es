---
title: Planificar cargas y envíos mediante el área de trabajo de planificación de la carga
description: Este artículo muestra cómo usar el área de trabajo de planificación de cargas para crear una carga para un pedido de ventas.
author: Mirzaab
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e53b7667dd4589a7c6c14b8aaf8ba51017eee0d
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068342"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Planificar cargas y envíos mediante el área de trabajo de planificación de la carga

[!include [banner](../../includes/banner.md)]

Este artículo muestra cómo usar el área de trabajo de planificación de cargas para crear una carga para un pedido de ventas. Es necesario crear primero el pedido de ventas. Este procedimiento forma parte del trabajo diario del coordinador de transporte. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-a-sales-order"></a>Crear un pedido de ventas
1. Vaya a **panel de navegación > Módulos > Clientes > Pedidos > Todos los pedidos de vents**.
2. Seleccione **Nuevo**.
3. En el campo **Cuenta de cliente**, seleccione el botón desplegable para abrir la búsqueda.
4. Seleccione la cuenta **US-004**.
5. Seleccione **Aceptar**.
6. En el campo **Código de artículo**, seleccione el botón desplegable para abrir la búsqueda.
7. Seleccione el artículo **A0001**. **A0001** está habilitado para administración del transporte.  
8. En el campo **Sitio**, seleccione el botón de la lista desplegable para abrir la búsqueda y seleccione un articulo.
9. En el campo **Cantidad**, especifique un número.
10. En el campo **Almacén** , escriba “24" en este ejemplo. Este almacén está habilitado para administración del transporte y procesos de gestión de almacenes (WMS).  
11. Seleccione **Guardar**.
12. Cierre la página.

## <a name="create-a-new-load"></a>Creación de una nueva carga
1. Vaya al **panel de navegación > Módulos > Administración de transporte > Planificación > Área de trabajo de planificación de la carga**.
2. Seleccione la pestaña **Líneas de ventas**. Ahora construirá la carga para el pedido de ventas que acaba de crear. Las cargas se pueden crear según la oferta y la demanda de los pedidos de compra, los pedidos de transferencia y los pedidos de ventas.  
3. En el panel de acciones, haga clic en **Oferta y demanda**.
4. Seleccione **A nueva carga**.
5. En el campo **Id. de plantilla de carga**, seleccione el botón desplegable para abrir la búsqueda. La plantilla de carga define las medidas máximas para el peso y el volumen de la carga completa. Por ejemplo, la plantilla de carga puede representar el tamaño de un contenedor o de un camión. Seleccione un artículo.
6. Seleccione **Aceptar**.

## <a name="rate-and-route-the-load"></a>Tasa y ruta para la carga
1. Seleccione **Clasificación y ruta**.
2. Seleccione **Área de trabajo índice y la ruta**.
3. Seleccione **Tienda de tasas**.
4. En la lista, busque y seleccione el registro deseado.
5. Seleccione **Asignar**.
6. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
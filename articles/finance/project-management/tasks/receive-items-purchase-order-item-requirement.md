---
title: Recibir artículos de un pedido de compra a partir de un artículo requerido
description: En este tema se explica cómo recibir artículos en un pedido de compra desde un artículo requerido.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7afdae65c5ae7e3196c6b9f142dd87aec39b5ea3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174429"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a>Recibir artículos de un pedido de compra a partir de un artículo requerido

[!include [task guide banner](../../includes/task-guide-banner.md)]

En este tema se explica cómo recibir artículos en un pedido de compra desde un artículo requerido.

Si usa un requisito de artículo en lugar de una transacción de artículos, podrá planificar la entrega justo antes del uso real del artículo, crear un pedido de compras, incluir el artículo en el marco del acuerdo comercial e incluir el requisito de artículo en la planificación de producción. 

Esta tarea usa el conjunto de datos USSI.

1. En el panel de navegación, vaya a **Módulos > Gestión y contabilidad de proyectos > Proyectos > Todos los proyectos**.
2. En la lista, seleccione el vínculo de la fila deseada.
3. En el panel de acciones, haga clic en **Plan**.
4. Seleccione **Requisitos de artículos**.
5. Seleccione **Nuevo**.
6. En la nueva fila, introduzca o seleccione un valor en el campo **Número de artículo**.
7. En el campo **Cantidad**, especifique un número.
8. Seleccione **Guardar**.
9. En el panel de acciones, seleccione **Administrar**.
10. Seleccione **Funciones**.
11. Seleccione **Crear pedido de compra**.
12. Seleccione la casilla **Incluir todos**.
13. En el campo **Cuenta de proveedor**, especifique o seleccione un valor.
14. Seleccione **Aceptar**.
15. En el panel de navegación, vaya a **Módulos > Proveedores > Pedidos de compra > Todos los pedidos de compra**.
16. En la lista, seleccione el vínculo de la fila deseada.
17. En el panel de acciones, selecione **Compra.**
18. Seleccione **Confirmar**.
19. En el panel de acciones, seleccione **Recibir**.
20. Seleccione **Recepción de producto**.
21. En el campo **Recepción de producto**, escriba un valor.
22. Seleccione **Aceptar**.


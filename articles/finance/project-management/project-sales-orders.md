---
title: Proyecto de pedidos de ventas según el tiempo y materiales del proyecto
description: Este tema explica cómo crear los pedidos de ventas basados en proyectos según el tiempo y materiales del proyecto.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: 2f27e3e0a2d6aadc4c5224b55f8a416cbe4e83aa
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551211"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a>Proyecto de pedidos de ventas según el tiempo y materiales del proyecto

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

En este tema se describe cómo crear un pedido de ventas para un proyecto. Sólo se pueden crear pedidos de ventas para proyectos del tipo **tiempo y materiales**.

Si un proyecto de tiempo y materiales tiene varias fuentes de financiación en el contrato del proyecto, debe habilitar el parámetro **Permitir pedidos de ventas para proyectos con varias fuentes de financiación** en la página **Parámetros de administración del proyecto y contabilidad**. 

> [!NOTE]
> - La compatibilidad para los pedidos de ventas de proyecto con varias fuentes de financiación estará disponible a partir de la versión 10.0.2 de la aplicación y posteriores.
> - El parámetro para habilitar el soporte para los pedidos de ventas de proyecto con varias fuentes de financiación se eliminará en la oleada de versiones de abril de 2020, tras la cual la funcionalidad siempre estará habilitada.

Puede crear pedidos de ventas basados en proyectos de dos formas:

- Vaya al propio proyecto. En el panel de acciones, seleccione **Gestionar > Tareas del artículo > Pedido de ventas**. La información de proyecto será la predeterminada para el pedido de ventas del proyecto. Si el contrato de proyecto tiene más de una fuente de financiación, deberá seleccione la fuente de financiación para establecer el cliente para el pedido de ventas. Si sólo existe una fuente de financiación para el proyecto, el cliente se establecerá automáticamente.
- Vaya a la página lista **Todos los perdidos de ventas** y cree un nuevo pedido de ventas. Deberá seleccionar el proyecto para el pedido de ventas. Tras seleccionar el proyecto, se establecerá al cliente de la fuente de financiación o deberá seleccionar la fuente de financiación si el contrato de proyecto tiene varias fuentes de financiación.


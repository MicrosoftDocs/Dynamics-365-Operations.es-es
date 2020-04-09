---
title: Crear una nueva regla kanban al duplicar una regla existente
description: Este procedimiento se centra en la creación de un duplicado de una regla kanban existente.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0bc65dd80221cedd25890037afcb3d2617f22793
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149224"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a>Crear una nueva regla kanban al duplicar una regla existente

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en la creación de un duplicado de una regla kanban existente. Esto resulta útil si desea crear nuevas reglas kanban basadas en reglas kanban existentes. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento está pensado para el ingeniero de procesos o el administrador de flujo de valor, ya que preparan la producción para un flujo de producción cambiado o una nueva regla de reabastecimiento.


## <a name="select-a-kanban-rule"></a>Seleccionar una regla kanban
1. Vaya a Reglas kanban.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione la regla kanban 000017 para el producto M0006.  

## <a name="duplicate-a-kanban-rule"></a>Duplicar una regla kanban
1. Haga clic en Duplicar regla kanban.
    * Al duplicar una regla kanban, es posible cambiar el tipo, las fechas, las actividades y la selección de productos. Cambie el producto para este procedimiento en el paso siguiente.  
2. En el campo Producto, especifique o seleccione un valor.
    * Seleccione M0007.  
3. Haga clic en Aceptar
    * Tenga en cuenta que se ha crea un duplicado de la regla kanban 000017.    


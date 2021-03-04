---
title: Cambiar las reglas kanban para un trabajo de proceso
description: Este procedimiento se centra en el cambio de la regla kanban usada para un kanban dado.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d4c8fd8251aca2cc53e59afe4c104f2e5198426
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436583"
---
# <a name="change-kanban-rules-for-a-process-job"></a>Cambiar las reglas kanban para un trabajo de proceso

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en el cambio de la regla kanban usada para un kanban dado. Esto resulta útil para nivelar recursos de carga o en caso de desglose. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento está para el planificador, que trabaja en una empresa de lean manufacturing, el responsable del flujo de valor.


## <a name="copy-kanban-rule"></a>Copiar regla kanban
1. Vaya a Reglas kanban.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione la regla kanban de evento 000022 para L0001.  
3. Haga clic en Duplicar regla kanban.
4. Haga clic en Aceptar

## <a name="change-kanban-rule"></a>Cambiar regla kanban
1. Cierre la página.
2. Vaya a Programación de trabajos kanban.
3. En la lista, marque la fila seleccionada.
    * Seleccione la línea con kanban 000177.  
4. Haga clic en Usar regla kanban alternativa.
5. Haga clic en Siguiente.
6. En el campo Regla kanban, especifique o seleccione un valor.
    * Seleccione la regla kanban que se creó anteriormente. Esta es la regla kanban con el número mayor.  
7. Haga clic en Finalizar.
    * Ahora el trabajo kanban está usando otra regla kanban. Esto puede resultar útil para nivelar celdas de trabajo de carga.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
--- 
title: "Crear tipos de solicitud y criterios de puntuación para solicitudes de presupuesto"
description: "Esta guía le muestra cómo crear un tipo de solicitud y asociar esto a un método de puntuación."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 095855d552d228375635bdbaa9fca37c47a3b952
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>Crear tipos de solicitud y criterios de puntuación para solicitudes de presupuesto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía le muestra cómo crear un tipo de solicitud y asociar esto a un método de puntuación. También muestra cómo utilizar el tipo de solicitud en una solicitud de presupuesto que después establece el método de puntuación predeterminado. Estas tareas las realizará normalmente el director de compras. Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Necesita tener un método de puntuación disponible antes de empezar.


## <a name="create-a-solicitation-type"></a>Crear un tipo de solicitud
1. Vaya a Adquisición y abastecimiento > Configuración > Solicitud de presupuesto > Tipo de solicitud.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Método de puntuación, seleccione el método de puntuación que desea usar para este tipo de solicitud.
6. Haga clic en Guardar.
7. Cierre la página.

## <a name="use-the-solicitation-type"></a>Use el tipo de solicitud
1. Vaya a Adquisición y abastecimiento > Solicitudes de presupuestos > Todas las solicitudes de presupuesto.
2. Haga clic en Nuevo.
3. En el campo Tipo de solicitud, seleccione el tipo de la solicitación que acaba de crear. 
    *   
4. Haga clic en Aceptar
5. Haga clic en Criterios de puntuación.
    * Los criterios de puntuación que se muestran son los del método de puntuación que asoció al tipo de solicitud. Puede elegir agregar o eliminar criterios en esta página. También es posible agregar nuevos criterios copiándolos de otros métodos de puntuación.  
6. Haga clic en Copiar criterios.
7. En el campo Método de puntuación, especifique o seleccione un valor.
8. Haga clic en Aceptar
9. Cierre la página.



---
title: "Grupos de cuentas de consolidación y cuentas adicionales de consolidación"
description: "Este tema proporciona información sobre los grupos de cuentas de la consolidación y las cuentas adicionales de consolidación, y explica cómo los utilizan en Microsoft Dynamics 365 para las operaciones."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f9c5aaa389c9c2f85d1ab91cbf3d2222cbebef55
ms.lasthandoff: 03/31/2017


---

# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Grupos de cuentas de consolidación y cuentas adicionales de consolidación

Este tema proporciona información sobre los grupos de cuentas de la consolidación y las cuentas adicionales de consolidación, y explica cómo los utilizan en Microsoft Dynamics 365 para las operaciones.

<a name="consolidation-account-groups"></a>Grupos de cuentas de consolidación
----------------------------

Los grupos de cuentas de consolidación permiten crear grupos de las cuentas que desee usar para consolidar los datos. Normalmente, un grupo de cuentas de consolidación representa un plan contable licencia obligatorio o asigna cuentas a un grupo definido por Retail Headquarters de la empresa. Puede encontrar grupos de cuentas de la consolidación en ** configuración ** el área ** las consolidaciones ** del módulo. Al agregar un nuevo grupo, especifique un identificador único para el grupo de cuentas y un nombre.

## <a name="additional-consolidation-accounts"></a>Cuentas de consolidación adicionales
Las cuentas adicionales de consolidación le permiten asignar una cuenta de un plan contable existente a un grupo de cuentas de la consolidación. Puede especificar un valor y un nombre de la cuenta de consolidación. 

Puede encontrar cuentas adicionales de consolidación en ** configuración ** el área ** las consolidaciones ** del módulo. Al crear una nueva cuenta de consolidación, debe especificar la siguiente información:

-   ** La cuenta principal ** – este campo es una búsqueda que muestra todas las cuentas principales que se basan en el plan contable que seleccionó en la página. Cuando selecciona una cuenta, el nombre se especifica en ** nombre de cuenta principal ** el campo.
-   ** Grupo de cuentas de consolidación ** – utilice este campo para especificar un grupo al que asignar la cuenta. Si el poner en firme de dos formas diferentes, debe agregar la misma cuenta a los cuatro grupos de cuentas de consolidación.
-   ** Cuenta de consolidación ** – especifique el valor de la cuenta de consolidación. Este valor no tiene que ser una cuenta de un plan contable. Puede ser cualquier valor que pueda necesitar.
-   ** Nombre de cuenta de consolidación ** permite especificar el nombre de la cuenta que desea que aparezca en consultas e informes.
-   ** El nivel del SAT ** – este campo se usa para informar extractos de cuenta a las autoridades fiscales mexicanas. 

Cuando haya terminado de crear los grupos de cuentas de la consolidación y cuentas adicionales de consolidación, puede seleccionar el grupo en el proceso en línea de la consolidación.




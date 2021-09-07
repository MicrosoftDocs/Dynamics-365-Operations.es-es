---
title: Directivas de idoneidad para beneficio
description: Este tema proporciona información sobre las directivas de idoneidad de prestaciones, que definen quién es apto para prestaciones específicas.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 88b801be5be4f9abcec4632fe1d96dbd83aaec96
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416938"
---
# <a name="benefit-eligibility-policies"></a>Directivas de idoneidad para beneficio

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema proporciona información sobre las directivas de idoneidad de prestaciones, que definen quién es apto para prestaciones específicas.

Cuando crea prestaciones, decide qué beneficios estarán disponibles para qué empleados. En la tabla siguiente se muestran ejemplos de las prestaciones que puede poner a disposición de empleados específicos.

| Prestación          | Para quién está disponible la prestación |
|------------------|---------------------------------|
| Seguro médico | Todos los empleados                   |
| Teléfono móvil     | Personal de ventas, ejecutivos         |
| Pases para aparcamiento   | Ejecutivos                      |

Se usan los siguientes componentes para crear directivas de idoneidad:

-   Tipos de reglas de directivas
-   Directivas de idoneidad para prestación

Los tipos de reglas de directivas definen los parámetros de consulta que se usan al desarrollar reglas de directivas específicas. Tras crear tipos de reglas de directivas, puede crear directivas de idoneidad de prestación. Las directivas le permiten crear una colección de reglas que se aplican a una o más entidades jurídicas. Dentro de cada directiva, puede ver cualquiera de los tipos de reglas de directivas de idoneidad de prestación que haya creado anteriormente. 

Define el ámbito de la regla dentro de la directiva. Por ejemplo, si crea un tipo de regla de directivas de idoneidad de prestación que se llama **Ejecutivo**, puede especificar cuáles es la regla dentro de dicha directiva. En este ejemplo, la regla podría indicar que se debe incluir en la regla cualquier título de trabajo que contenga la palabra "ejecutivo". Una vez que haya definido los parámetros de la regla o las reglas que se incluyen en la directiva, puede asignar una regla específica a la prestación.






[!INCLUDE[footer-include](../includes/footer-banner.md)]

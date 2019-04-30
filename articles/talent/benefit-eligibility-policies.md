---
title: Directivas de idoneidad para beneficio
description: Este artículo proporciona información acerca de las directivas de idoneidad de prestación, que le ayudan a definir quién es apto para las prestaciones específicas.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: ad179e505d045dc40898105e1cfd090daafa09a8
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "855971"
---
# <a name="benefit-eligibility-policies"></a>Directivas de idoneidad para beneficio

[!include [banner](includes/banner.md)]

Este tema proporciona información acerca de las directivas de idoneidad de prestación, que le ayudan a definir quién es apto para las prestaciones específicas.

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

<a name="additional-resources"></a>Recursos adicionales
--------

[Definir y gestionar un programa de prestaciones](manage-benefit-program.md)




---
title: Definir reglas y directivas de idoneidad para prestaciones
description: En este tema se explica cómo crear reglas y directivas de idoneidad para prestaciones y después asignar reglas a las prestaciones.
author: twheeloc
ms.date: 08/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 4781a00ae63bb2d27df0610a1886cc43e52798f9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861200"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Definir reglas y directivas de idoneidad para prestaciones


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En este artículo se explica cómo crear reglas y directivas de idoneidad para prestaciones y después asignar reglas a las prestaciones.  

## <a name="create-benefit-eligibility-policy-rule-type"></a>Creación de tipos de reglas de directivas de opción de prestaciones

1. Vaya a **Recursos humanos > Prestaciones > Idoneidad > Tipos de reglas de idoneidad de prestaciones**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre de regla**, escriba un valor.
4. En el campo **Descripción**, especifique un valor.
5. En el campo **Nombre de la consulta**, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, seleccione el vínculo de la fila seleccionada.
7. Seleccione **Guardar**.
8. Cierre la página.

## <a name="benefit-eligibility-policy"></a>Directiva de idoneidad de beneficio

1. Vaya a **Recursos humanos > Prestaciones > Idoneidad > Directivas de idoneidad para prestaciones**.
2. Seleccione una directiva de prestación existente.
3. En la lista, seleccione el vínculo de la fila seleccionada.
4. Expanda las secciones **Organizaciones de directivas**. Puede agregar o quitar cualquier organización que desee incluir en la directiva.
5. Expanda o contraiga la sección **Reglas de directivas**.
6. En la lista, busque la regla de directiva que creó anteriormente.
7. Seleccione **Crear regla de directivas**.
8. En el campo **Fecha de vigencia**, especifique la fecha en la que desea que la directiva entre en vigor.
    * Establecer las fechas finales vigentes permite realizar cambios futuros en las reglas de las directivas para no tener que volver a la directiva cuando se desee que los cambios surtan efecto.  
9. Si es necesario, agregue una cláusula Donde al campo **Agregar condición**.
    * Por ejemplo, si quisiera que la regla solo se aplicase a los directores de ventas, podría crear la cláusula Donde para decir: Donde la descripción del puesto es igual a director de ventas. Puede agregar varias cláusulas Donde a la regla.  
10. Seleccione **Aceptar**.
11. Cierre la página.

## <a name="assign-rule-to-benefit"></a>Asignación de reglas a prestaciones

1. Vaya a **Recursos humanos > Prestaciones > Prestaciones**.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, seleccione el vínculo de la fila seleccionada.
4. Expanda o contraiga la sección **Reglas de idoneidad**.
5. Seleccione **Editar**.
6. En el campo **Idoneidad**, seleccione la regla.
7. En el campo **Tipo de regla**, seleccione la regla que creó anteriormente.
9. En la lista, seleccione el vínculo de la fila seleccionada.
10. Seleccione **Guardar**.
11. Cierre el formulario.



[!INCLUDE[footer-include](../includes/footer-banner.md)]

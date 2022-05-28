---
title: Proceso de idoneidad para prestación
description: Este procedimiento muestra cómo funciona el proceso de idoneidad de la prestación.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 61818ad8d397fe2b61952003aa562818c4bad2f5
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687712"
---
# <a name="benefit-eligibility-process"></a>Proceso de idoneidad para prestación


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este procedimiento muestra cómo funciona el proceso de idoneidad de la prestación. Cuando se complete el proceso, podrá ver los resultados. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a **Recursos humanos \> Prestaciones \> Prestaciones**.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, seleccione el vínculo de la fila seleccionada.
4. Seleccione **Editar**.
5. En el campo **Idoneidad**, seleccione **Basada en reglas**.
6. En el campo **Tipo de regla**, seleccione la regla de directiva de prestación para aplicar a la prestación.
7. En el panel de acciones, seleccione **Prestación**.
8. Seleccione **Crear evento de idoneidad**.
9. En el cuadro de diálogo desplegable, en el campo **Evento**, introduzca un valor.
10. En el campo **Descripción**, especifique un valor.
11. Seleccione **Abrir inscripción** en el campo **Tipo de evento**.
12. En el campo **Fecha de inicio de la cobertura**, especifique una fecha y una hora.
13. En el campo **Fecha de inicio del período de inscripción**, especifique una fecha y una hora.
14. En el campo **Días para inscribirse**, especifique un número.
15. Seleccione **Crear evento**.
16. En la ficha desplegable **Trabajadores**, seleccione **Agregar**.
17. En el campo **Mostrar por tipo**, seleccione **Empleados**.
18. En el campo **Mostrar por entidad jurídica**, seleccione **Entidad jurídica actual**.
19. En la lista, active o desactive todas las filas.
20. Seleccione **Aceptar**.
21. Seleccione **Procesar**.
22. Seleccione **Aceptar**.
23. Actualice la página.
24. Seleccione **Mostrar resultados**.
25. Abra el filtro de columna **Estado**.
26. Ordene la columna de la A a la Z.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

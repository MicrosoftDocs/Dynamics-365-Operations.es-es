---
title: Definir directivas de auditoría para documentos de origen
description: En este artículo se explica cómo configurar y ejecutar las reglas de directivas de auditoría.
author: panolte
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b8aa106cd5a5596f6b9a6663390e03ebc3f91a7b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872539"
---
# <a name="define-audit-policies-for-source-documents"></a>Definir directivas de auditoría para documentos de origen

[!include [banner](../../includes/banner.md)]

En este artículo se explica cómo configurar y ejecutar las reglas de directivas de auditoría. En el ejemplo se usan informes de gastos con el tipo de gastos de hotel. Este procedimiento usa la empresa de demostración USMF. El rol de auditor contiene los permisos correctos para llevar a cabo estas tareas.

1. En el panel de exploración, vaya a **Módulos > Área de trabajo de auditoría > Configuración > Tipo de regla de directivas**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre de regla**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. En el campo **Nombre de la consulta**, seleccione **Línea de informe de gastos**.
6. En el campo **Tipo de consulta**, seleccione **Agregado**.
7. En el campo **Entidad jurídica**, seleccione **Entidad jurídica**.
8. En el campo **Referencia de fecha de documento**, seleccione **Fecha y hora de modificación**.
9. Seleccione **Guardar**.
10. En el panel de exploración, vaya a **Módulos > Área de trabajo de auditoría > Configuración > Directivas de auditoría**.
11. Seleccione **Nuevo**.
12. En el campo **Nombre**, escriba un valor.
13. Expanda la sección **Organizaciones de directivas**.
14. En el árbol, seleccione **Contoso Entertainment System USA** y, después, **Agregar**.
15. En el árbol, seleccione **Contoso Consulting USA** y, después, **Agregar**.
16. En el árbol, seleccione **Contoso Retail USA** y, después, **Agregar**.
17. Contraiga la sección **Organizaciones de directivas**.
18. Expanda la sección **Reglas de directivas**.
19. En la lista, busque y seleccione la regla de directivas que creó anteriormente.
20. Seleccione **Crear regla de directivas**.
21. En el campo **Fecha de vigencia**, especifique una fecha y una hora.
22. Seleccione **Filtro**.
23. En la lista, seleccione la fila para **Categoría de gastos** y establezca los detalles en **Hotel**.
24. En el campo **Criterios**, especifique o seleccione un valor.
25. Seleccione la pestaña **Agregado**.
26. Seleccione **Agregar**.
27. En la lista, seleccione un valor de campo de **Importe de la transacción**.
28. En el campo **Campo**, especifique o seleccione un valor.
29. En el campo de **AggregateFunction**, seleccione **Suma**.
30. Seleccione la ficha **Agrupar por**.
31. Seleccione **Agregar**.
32. En la lista, seleccione un valor de **Empleado**.
33. Seleccione **Agregar**.
34. En la lista, seleccione un valor de **Categoría de gastos**.
35. En el campo **Campo**, especifique o seleccione un valor.
36. Seleccione la pestaña **Tiene**.
37. Seleccione **Agregar**.
38. Seleccione **Importe de transacción**.
39. En el campo **Campo**, especifique o seleccione un valor.
40. En el campo de **AggregateFunction**, seleccione **Suma**.
41. En el campo **Criterios**, escriba `>2000`.
42. Seleccione **Aceptar**.
43. Seleccione **Prueba**.
44. En el campo **Fecha inicial de selección de documentos**, especifique una fecha y hora.
45. En el campo **Fecha final de selección de documentos**, especifique una fecha y hora.
46. Seleccione **Ejecutar prueba**.
47. En el panel de acciones, seleccione **Directiva de auditoría**.
48. Seleccione **Opciones adicionales**.
49. En el campo **Fecha inicial**, especifique una fecha y una hora.
50. En el campo **Fecha de finalización**, especifique una fecha y una hora.
51. Seleccione **Lote**.
52. Expanda la sección **Ejecutar en segundo plano**.
53. Seleccione **Sí** en el campo **Procesamiento por lotes**.
54. Seleccione **Aceptar**.
55. En el panel de exploración, vaya a **Módulos > Área de trabajo de auditoría > Configuración > Casos de auditoría**.
56. En la lista, busque y seleccione el registro deseado.
57. Expanda la sección **Asociaciones**.
58. En la lista, busque y seleccione el registro deseado.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

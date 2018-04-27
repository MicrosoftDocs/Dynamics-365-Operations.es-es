--- 
title: "Definir directivas de auditoría para documentos de origen"
description: "En este procedimiento se muestra cómo configurar y ejecutar las reglas de directivas de auditoría."
author: ryansandness
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b05f744120e940bfea3e92b8aac3e41fc8151d9
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="define-audit-policies-for-source-documents"></a>Definir directivas de auditoría para documentos de origen

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

En este procedimiento se muestra cómo configurar y ejecutar las reglas de directivas de auditoría. En el ejemplo se usan informes de gastos con el tipo de gastos de hotel. Este procedimiento usa la empresa de demostración USMF. El rol de auditor contiene los permisos correctos para llevar a cabo estas tareas.

1. Vaya a Área de trabajo de auditoría > Configuración > Tipo de regla de directivas.
2. Haga clic en Nuevo.
3. En el campo Nombre de regla, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Nombre de la consulta, seleccione la línea Informe de gastos.
6. En el campo Tipo de consulta, seleccione Agregado.
7. En el campo Entidad jurídica, seleccione una entidad jurídica.
8. En el campo Referencia de fecha de documento, seleccione la fecha y la hora de modificación.
9. Haga clic en Guardar.
10. Vaya a Área de trabajo de auditoría > Configuración > Directivas de auditoría.
11. Haga clic en Nuevo.
12. En el campo Nombre, escriba un valor.
13. Expanda la sección Organizaciones de directivas.
14. En el árbol, seleccione "Contoso Entertainment System USA".
15. Haga clic en Agregar.
16. En el árbol, seleccione "Contoso Consulting USA".
17. Haga clic en Agregar.
18. En el árbol, seleccione "Contoso Retail USA".
19. Haga clic en Agregar.
20. Contraiga la sección Organizaciones de directivas.
21. Expanda la sección Reglas de directivas.
22. En la lista, busque y seleccione la regla de directivas que creó anteriormente.
23. Haga clic en Crear regla de directivas.
24. En el campo Fecha de vigencia, especifique una fecha y una hora.
25. Haga clic en Filtro.
26. En la lista, seleccione la fila de la categoría Gastos y defina los detalles de Hotel.
27. En el campo Criterios, especifique o seleccione un valor.
28. Haga clic en la ficha Agregado.
29. Haga clic en Agregar.
30. En la lista, seleccione un valor de campo del importe de la transacción.
31. En el campo Campo, especifique o seleccione un valor.
32. En el campo de AggregateFunction, seleccione “Suma”.
33. Haga clic en la ficha Agrupar por.
34. Haga clic en Agregar.
35. En la lista, seleccione un valor de Empleado.  
36. Haga clic en Agregar.
37. En la lista, seleccione un valor de Categoría de gastos.
38. En el campo Campo, especifique o seleccione un valor.
39. Haga clic en la ficha Tiene.
40. Haga clic en Agregar.
41. Seleccionar el importe de transacción
42. En el campo Campo, especifique o seleccione un valor.
43. En el campo de AggregateFunction, seleccione “Suma”.
44. En el campo Criterios, escriba >2000".
45. Haga clic en Aceptar
46. Haga clic en Probar.
47. En el campo Fecha inicial de selección de documentos, especifique una fecha y hora.
48. En el campo Fecha final de selección de documentos, especifique una fecha y hora.
49. Haga clic en Ejecutar prueba.
50. En el panel de acciones, haga clic en Directiva de auditoría.
51. Haga clic en Opciones adicionales.
52. En el campo Fecha inicial, especifique una fecha y una hora.
53. En el campo Fecha de finalización, especifique una fecha y una hora.
54. Haga clic en Lote.
55. Expanda la sección Ejecutar en segundo plano.
56. Seleccione Sí en el campo Procesamiento por lotes.
57. Haga clic en Aceptar
58. Vaya a Área de trabajo de auditoría '>Casos de auditoría.
59. En la lista, busque y seleccione el registro deseado.
60. En la lista, haga clic en el vínculo de la fila seleccionada.
61. Expanda la sección Asociación.
62. En la lista, busque y seleccione el registro deseado.
63. En la lista, haga clic en el vínculo de la fila seleccionada.



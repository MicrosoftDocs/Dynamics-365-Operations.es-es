---
title: Usar las configuraciones de asignación de modelo para cálculos agregados en el nivel de la base de datos
description: Este procedimiento proporciona información acerca de cómo diseñar una nueva configuración de asignación de modelo de informes electrónicos (ER) y utilizar las funciones de ER integradas para realizar cálculos agregados eficientes.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a462a3997644a494b5cea89c9530ddba67c32450
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "313644"
---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a>Usar las configuraciones de asignación de modelo para cálculos agregados en el nivel de la base de datos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento proporciona información acerca de cómo diseñar una nueva configuración de asignación de modelo de informes electrónicos (ER) y utilizar las funciones de ER integradas para realizar cálculos agregados eficientes. En este procedimiento, creará una configuración para la empresa de ejemplo Litware, Inc. 

Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados. Estos pasos se pueden completar mediante cualquier conjunto de datos.

 Para completar estos pasos, primero debe completar los pasos del procedimiento “ER mejora la eficiencia de los cálculos globales efectuándolos en el nivel de la base de datos (Parte 1: Preparación de las configuraciones)”.

1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, expanda "Intrastat modelo".
3. En el árbol, seleccione 'Intrastat model\Intrastat sample mapping'.
4. Haga clic en Diseñador.
5. Haga clic en Diseñador.
6. En el árbol, seleccione "Dynamics 365 for Operations\Registros de tabla".
7. Haga clic en Agregar raíz.
    * Agregar un nuevo origen de datos que representa los registros que desea agrupar.  
8. En el campo Nombre, escriba "Transacciones".
    * Transacciones  
9. En el campo Tabla, escriba "Intrastat".
    * intrastat  
10. Haga clic en Aceptar
11. En el árbol, seleccione "Funciones\Agrupar por".
    * Este tipo de origen de datos se utiliza para especificar un nuevo origen de datos en el tiempo de ejecución para agrupar registros y calcular las agregaciones necesarias.  
12. Haga clic en Agregar raíz.
13. En el campo Nombre, escriba "TransactionsGroups".
    * TransactionsGroups  
14. Haga clic en Editar grupo por.
15. En el árbol, seleccione Transacciones.
    * Seleccione el origen de datos agregado del tipo "Lista de registros" que representa los registros que desea agrupar.  
16. Haga clic en Agregar campo a.
17. Haga clic en Elementos para agrupar.
18. En el árbol, expanda Transacciones.
19. En el árbol, seleccione 'Transactions\Direction'.
20. Haga clic en Agregar campo a.
21. Haga clic en Campos agrupados.
    * Seleccione el campo para especificar el nivel de agrupación. En función de esta selección, el origen de datos devolverá en el tiempo de ejecución tantos grupos de transacciones como códigos de dirección que se deben cumplir en la tabla Intrastat.  
22. En el árbol, seleccione 'Transactions\Invoice amount(AmountMST)'.
    * Seleccione el campo para especificar el origen del cálculo de agregación.  
23. Haga clic en Agregar campo a.
24. Haga clic en Campos de agregación.
25. En la lista, marque la fila seleccionada.
26. En el campo Método, seleccione 'Suma'.
    * Seleccionar el tipo de agregación.  
27. En el campo Nombre, escriba "SumOfAmountMST".
    * Especifique el nombre de esta agregación en el origen de datos configurado.  
28. Haga clic en Guardar.
    * Tenga en cuenta que el campo "Ejecución en" indica que esta agrupación se llevará a cabo en el tiempo de ejecución en la base de datos SQL.  
29. Cierre la página.
30. Haga clic en Aceptar
31. En el árbol, expanda 'Totals'.
32. En el árbol, expanda 'TransactionsGroups'.
33. En el árbol, expanda 'TransactionsGroups\aggregated'.
34. En el árbol, seleccione 'TransactionsGroups\aggregated\SumOfAmountMST'.
35. En el árbol, seleccione 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.
36. Haga clic en Enlazar.
    * Basándose en este valor, este origen de datos calculará la suma de los valores del campo “AmountMST” para cada grupo de transacciones. Este cálculo de agregaciones estará disponible como artículo TransactionsGroups.aggregated.TotalAmount.  
37. En el árbol, expanda 'TransactionsGroups'.
38. En el árbol, seleccione 'TransactionsGroups'.
39. Haga clic en Editar.
40. Haga clic en Editar grupo por.
41. En el árbol, expanda Transacciones.
42. En el árbol, seleccione 'Transactions\Invoice amount(AmountMST)'.
43. Haga clic en Agregar campo a.
44. Haga clic en Campos de agregación.
45. En la lista, marque la fila seleccionada.
46. En el campo Método, seleccione 'Máx'.
47. En el campo Nombre, escriba 'MaxOfAmountMST'.
48. Haga clic en Guardar.
    * Actualmente, la ejecución de los orígenes de datos GROUPBY se puede traducir al nivel de la base de datos SQL con algunas limitaciones. La traducción se puede efectuar para los orígenes del tipo "Lista de registros" o los orígenes de datos representados como expresión usando la función FILTRO. También se puede realizar cuando la única la agregación se configura para un solo campo de los registros de agrupación.  
    * Tenga en cuenta que aunque más de una agregación se configuró para el campo de AmountMST, el campo "Ejecución en" sigue indicando que esta agrupación se realizará en el tiempo de ejecución en la base de datos SQL. Esto se debe a que una sola agregación está enlazada al artículo del modelo de datos y se usará en el tiempo de ejecución para extraer datos de este origen de datos.  
49. Cierre la página.
50. Haga clic en Aceptar
51. En el árbol, expanda 'TransactionsGroups'.
52. En el árbol, expanda 'TransactionsGroups\aggregated'.
53. En el árbol, expanda 'TransactionsGroups\aggregated\MaxOfAmountMST'.
54. En el árbol, seleccione 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.
55. Haga clic en Enlazar.
56. En el árbol, expanda 'TransactionsGroups'.
57. En el árbol, seleccione 'TransactionsGroups'.
58. Haga clic en Editar.
59. Haga clic en Editar grupo por.
    * Tenga en cuenta que el campo "Ejecución en" indica que esta agrupación se realizará en la memoria del tiempo de ejecución porque las dos agregaciones del mismo campo están vinculadas a los artículos de modelo de datos.   
60. En la lista, active o desactive todas las filas.
61. Haga clic Eliminar.
62. Haga clic en Sí.
63. Haga clic Eliminar.
64. Haga clic en Sí.
65. Haga clic en Agregar campo a.
66. Haga clic en Elementos para agrupar.
67. En el árbol, expanda 'Commodity record(Intrastat)'.
68. Haga clic en Guardar.
    * Tenga en cuenta que el campo "Ejecución en" indica que esta agrupación se llevará a cabo en la memoria del tiempo de ejecución aunque no haya agregaciones definidas y el origen de datos seleccionado del tipo "Registros de tabla” haga referencia a la misma tabla de "Intrastat". Esto se debe a que el origen de datos contiene algunos campos calculados que no se pueden traducir aún al nivel de la base de datos SQL.  


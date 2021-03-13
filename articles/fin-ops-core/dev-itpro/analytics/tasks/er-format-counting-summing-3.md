---
title: 'Informe electrónico Configurar el formato para contar y sumar (Parte 3: Uso de los cálculos para crear la salida)'
description: Este tema describe cómo configurar un formato de informes electrónicos para realizar recuentos y sumas en función de los datos de la salida de texto ya generados. (Parte 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a69dd28051d8e98643eb95c663525075bed8dec
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092981"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a>Informe electrónico Configurar el formato para contar y sumar (Parte 3: Uso de los cálculos para crear la salida)

[!include [banner](../../includes/banner.md)]

Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Configurar el formato para contar y sumar (Parte 2: Configuración de cálculos)".

Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.


## <a name="configure-this-report-to-use-counting-and-summing-info"></a>Configurar este informe para utilizar la información de recuento y suma
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Configuraciones de informes.
3. En el árbol, expanda "Intrastat modelo".
4. En el árbol, expanda "Modelo de Intrastat\Intrastat (DE)".
5. En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)\Intrastat (DE) con recuento & suma".
6. Haga clic en Diseñador.
7. Haga clic en la ficha Asignación.
8. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
    * Agregue un nuevo origen de datos para obtener la lista de bloqueos memorizados.  
9. En el árbol, seleccione el apartado "Funciones\Campo calculado".
10. En el campo Nombre, escriba "$BlocksList".
    * $BlocksList  
11. Haga clic en Editar fórmula.
12. En el árbol, seleccione "Funciones de recopilación de datos\COLLECTEDLIST".
13. Haga clic en Agregar función.
14. Haga clic en Agregar origen de datos.
15. En el campo Fórmula, especifique "COLLECTEDLIST('$BlockName',".
    * COLLECTEDLIST('$BlockName',  
16. En el campo Fórmula, especifique "COLLECTEDLIST('$BlockName', "*")".
    * COLLECTEDLIST('$BlockName', "*")  
17. Haga clic en Guardar.
    * El patrón "*" significa que todos los bloqueos se incluirán en la lista de este registro.  
18. Cierre la página.
19. Haga clic en Aceptar
20. Haga clic en la ficha Formato.
21. En el árbol, seleccione "Intrastat\Datos".
22. Haga clic en Agregar para abrir el cuadro desplegable.
23. En el árbol, seleccione "Texto\Secuencia".
24. En el campo Nombre, escriba "Totales por bloqueos".
    * Totales por bloqueos  
25. En el campo Caracteres especiales, seleccione "Línea nueva - Windows (CR LF)".
26. Haga clic en Aceptar
27. En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos".
28. Haga clic en Agregar para abrir el cuadro desplegable.
29. En el árbol, seleccione "Texto\Cadena".
30. En el campo Nombre, escriba "Código de bloqueo".
    * Código de bloqueo  
31. Haga clic en Aceptar
32. Haga clic en Agregar cadena.
33. En el campo Nombre, escriba "Recuento de líneas".
    * Recuento de líneas  
34. Haga clic en Aceptar
35. Haga clic en Agregar cadena.
36. En el campo Nombre, escriba "Importe total".
    * Importe total  
37. Haga clic en Aceptar
38. Haga clic en la ficha Asignación.
39. En el árbol, seleccione "$BlocksList".
40. Haga clic en Enlazar.
    * Cree una línea de resumen para cada bloqueo memorizado.  
41. Haga clic en la ficha Formato.
42. En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Código de bloqueo".
43. Haga clic en la ficha Asignación.
44. Haga clic en Editar fórmula.
45. En el campo Fórmula, introduzca '"Id. de bloqueo: " & '.
    * "Id. de bloqueo: " &  
46. En el árbol, expanda "$BlocksList".
47. En el árbol, seleccione "$BlocksList\Value".
48. Haga clic en Agregar origen de datos.
49. Haga clic en Guardar.
50. Cierre la página.
51. Haga clic en la ficha Formato.
52. En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Recuento de líneas".
53. Haga clic en la ficha Asignación.
54. Haga clic en Editar fórmula.
    * Cree la salida para el número de líneas para cada bloqueo que se muestra en este informe.  
55. En el campo Fórmula, introduzca '"Número de líneas en este bloqueo: " & '.
    * "Número de líneas en este bloqueo: " &  
56. En el campo Fórmula, introduzca '"Número de líneas en este bloqueo: " & TEXT('.
    * "Número de líneas en este bloqueo: " & TEXT(  
57. En el árbol, seleccione "Funciones de recopilación de datos\COUNTIFS".
58. Haga clic en Agregar función.
59. Haga clic en Agregar origen de datos.
60. En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '.
    * "Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName',  
61. En el árbol, expanda "$BlocksList".
62. En el árbol, seleccione "$BlocksList\Value".
63. Haga clic en Agregar origen de datos.
64. En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.
    * "Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,  
65. En el árbol, seleccione "$RecName".
66. Haga clic en Agregar origen de datos.
67. En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.
    * "Número de líneas en este bloque: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
68. Haga clic en Guardar.
69. Cierre la página.
70. Haga clic en la ficha Formato.
71. En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Importe total".
72. Haga clic en la ficha Asignación.
73. Haga clic en Editar fórmula.
    * Cree la salida que será el total del importe facturado para cada bloqueo que se muestra en este informe.  
74. En el campo Fórmula, especifique '"Total del importe facturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.
    * "Total del importe facturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
75. Haga clic en Guardar.
76. Cierre la página.
77. Haga clic en Guardar.
78. Cierre la página.


---
title: 'Informe electrónico Configurar el formato para contar y sumar (Parte 2: Configuración de cálculos)'
description: Este artículo describe cómo configurar un formato de informes electrónicos para realizar recuentos y sumas en función de los datos de la salida de texto ya generados. (Parte 2)
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
ms.openlocfilehash: f7cdfff15ac157d69f0b60de8b36acc870a9cf49
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290676"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a>Informe electrónico Configurar el formato para contar y sumar (Parte 2: Configuración de cálculos)

[!include [banner](../../includes/banner.md)]

Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Configurar el formato para contar y sumar (Parte 1: Creación de formato)".

Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a>Creación de una configuración de formato para agregar los detalles de recuento y suma
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Configuraciones de informes.
3. En el árbol, expanda "Intrastat modelo".
4. En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)".
    * Supongamos que necesita personalizar el formato proporcionado por Microsoft agregando líneas con los detalles de resumen al final del informe de Intrastat. Tiene que hacerlo derivando nuestra propia instancia de la configuración Intrastat de la instancia de Microsoft para realizar modificaciones.  
5. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
6. En el campo Nuevo, especifique "Derivar del nombre: Intrastat (DE), Microsoft".
7. En el campo Nombre, escriba "Intrastat (DE) con recuento & suma".
8. Haga clic en Crear configuración.

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a>Configurar este informe para realizar el recuento y la suma en función de los detalles de salida
1. Haga clic en Diseñador.
2. Seleccione Sí en el campo Recopilar detalles de salida.
    * Este indicador activará en el tiempo de ejecución el proceso de recopilación de los detalles de salida para generar el archivo Intrastat.  
    * Tiene que realizar el recuento para varias directrices de Intrastat, por lo que debe agregar una enumeración de modelo dedicada a la lista de los orígenes de datos de esta configuración del formato.  
3. Haga clic en la ficha Asignación.
4. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
5. En el árbol, seleccione "Modelo de datos\Enumeración".
6. Escriba "Directriz" en el campo Nombre.
7. En el campo Enumeración de modelo, especifique o seleccione un valor.
    * Seleccione el valor Dirección.  
8. Haga clic en Aceptar
9. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
10. En el árbol, seleccione el apartado "Funciones\Campo calculado".
11. En el campo Nombre, escriba "$BlockName".
12. Haga clic en Editar fórmula.
13. En el campo Fórmula, especifique "bloqueo".
14. Haga clic en Guardar.
15. Cierre la página.
16. Haga clic en Aceptar
17. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
18. En el árbol, seleccione el apartado "Funciones\Campo calculado".
19. En el campo Nombre, escriba "$RecName".
20. Haga clic en Editar fórmula.
21. En el campo Fórmula, especifique "registro".
22. Haga clic en Guardar.
23. Cierre la página.
24. Haga clic en Aceptar
25. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
26. En el árbol, seleccione el apartado "Funciones\Campo calculado".
27. En el campo Nombre, escriba "$InvName".
28. Haga clic en Editar fórmula.
29. En el campo Fórmula, especifique "InvoicedAmountEUR".
30. Haga clic en Guardar.
31. Cierre la página.
32. Haga clic en Aceptar
33. En el árbol, seleccione "Intrastat\Datos".
34. Haga clic en el botón Editar para el campo "Nombre de clave de datos recopilados"
35. Haga clic en Agregar origen de datos.
    * $BlockName  
36. Haga clic en Guardar.
37. Cierre la página.
38. Haga clic en el botón Editar para el campo "Valor de clave de datos recopilados".
39. En el campo Fórmula, especifique "IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")".
    * IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")  
40. Haga clic en Guardar.
41. Cierre la página.
    * Cuente las líneas de esta secuencia. Los resultados se usarán con el nombre "bloqueo" por separado para distintas directrices. El valor "Importar" se usará para cualquier transacción de entradas de Intrastat. El valor "Exportar" se usará para cualquier transacción de envío de Intrastat. Considere esto como una hoja de cálculo de Excel virtual. Para cada transacción una fila donde la primera columna "bloqueo" se rellena con los valores "Importar"y "Exportar" en consecuencia.  
42. En el árbol, expanda "Intrastat\Datos: Secuencia".
43. En el árbol, seleccione "Intrastat\Datos: Secuencia\¿Entradas?".
44. Haga clic en el botón Editar para el campo "Nombre de clave de datos recopilados".
    * Cuente las líneas de esta secuencia. Los resultados se memorizarán con el nombre "registro".  
45. En el árbol, seleccione "$RecName".
46. Haga clic en Agregar origen de datos.
47. Haga clic en Guardar.
48. Cierre la página.
49. Haga clic en el botón Editar para el campo "Valor de clave de datos recopilados"
50. En el campo Fórmula, especifique "Intrastat.CommodityRecord.CommodityCode".
51. Haga clic en Guardar.
52. Cierre la página.
    * Cuente las líneas de esta secuencia. Los resultados se usarán con el nombre "registro" por separado para distintos códigos de mercancías. Considere esto como una hoja de cálculo de Excel virtual. Para cada transacción una fila donde la primera columna "bloqueo" se rellena con los valores "Importar"y "Exportar" en consecuencia y el segundo bloque "registro" se rellena con el valor de código de mercancía.  
53. En el árbol, seleccione "Intrastat\Datos: Secuencia\¿Envíos?".
54. Haga clic en el botón Editar para el campo "Nombre de clave de datos recopilados"
55. En el árbol, seleccione "$RecName".
56. Haga clic en Agregar origen de datos.
57. Haga clic en Guardar.
58. Cierre la página.
59. Haga clic en el botón Editar para el campo "Valor de clave de datos recopilados".
60. En el campo Fórmula, especifique "Intrastat.CommodityRecord.CommodityCode".
61. Haga clic en Guardar.
62. Cierre la página.
63. En el árbol, expanda "Intrastat\Datos: Secuencia\Envíos: ¿Secuencia?".
64. En el árbol, expanda "Intrastat\Datos: Secuencia\Envíos: ¿Secuencia?\Registro = Intrastat.CommodityRecord".
65. Haga clic en la ficha Formato.
66. En el árbol, seleccione "Intrastat\Datos\Envíos\Registro\Importe de factura en euros".
67. Haga clic en la ficha Asignación.
68. Haga clic en el botón Editar para el campo "Nombre de clave de datos recopilados".
69. En el árbol, seleccione "$InvName".
70. Haga clic en Agregar origen de datos.
71. Haga clic en Guardar.
72. Cierre la página.
    * Resuma los valores del importe facturado para las líneas de esta secuencia. Los resultados se usarán con el nombre "InvoicedAmountEUR" por separado para distintas directrices de Intrastat y códigos de mercancías. Considere esto como una creación virtual en una hoja de cálculo de Excel. Para cada transacción una fila donde la primera columna "bloqueo" se rellena con los valores "Importar"y "Exportar" en consecuencia. El segundo bloque "registro" se rellena con el valor de código de mercancía y la tercera columna "InvoicedAmountEUR" se rellena con el valor de importe de la factura.  
73. En el árbol, expanda "Intrastat\Datos\¿Entradas?".
74. En el árbol, expanda "Intrastat\Datos\¿Entradas?\Registro = Intrastat.CommodityRecord".
75. Haga clic en la ficha Formato.
76. En el árbol, seleccione "Intrastat\Datos\Entradas\Registro\Importe de factura en euros".
77. Haga clic en la ficha Asignación.
78. Haga clic en el botón Editar para el campo "Nombre de clave de datos recopilados".
79. En el árbol, seleccione "$InvName".
80. Haga clic en Agregar origen de datos.
81. Haga clic en Guardar.
82. Cierre la página.
83. Haga clic en Guardar.
84. Cierre la página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

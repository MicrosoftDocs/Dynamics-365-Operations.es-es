---
title: Configuración de perfiles de registro de activos fijos
description: Este procedimiento muestra cómo configurar perfiles de contabilización de activos fijos.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: be8001428cf2df111458fddd0ecbcdae0daf9b25
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863083"
---
# <a name="set-up-fixed-asset-posting-profiles"></a>Configuración de perfiles de registro de activos fijos

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo configurar perfiles de contabilización de activos fijos. Los ejemplos proporcionados en el artículo son para un perfil de contabilización básico, aunque se deben crear perfiles de contabilización para sus requisitos específicos de plan de cuentas y de informes financieros.

1. En el panel de navegación, vaya a **Módulos > activos fijos > Configuración > Perfiles de contabilización de activos fijos**.
2. Haga clic en **Nuevo**.
3. En el campo **Perfil de contabilización**, escriba un valor.
4. En el campo **Descripción**, escriba un valor. Deberá crear un perfil de contabilización para cada tipo de transacción de activo fijo que usará al trabajar con los activos fijos. Esta guía de la tarea empezará con el tipo de transacción Adquisición.  
5. Haga clic en **Agregar** en la barra de herramientas.
6. En el campo **Libro**, especifique o seleccione un valor. El campo **Agrupaciones** permite definir el perfil de contabilización hasta el nivel de tabla (una cuenta configurada para cada activo fijo) o de grupo (una cuenta configurada para cada grupo de activos fijos). Para esta guía de tareas, deje el valor establecido en “Todos” para aplicar a todos los activos fijos con el libro especificado.  
7. En el campo **Cuenta principal**, especifique los valores deseados. Para las adquisiciones, puede especificar una cuenta de contrapartida o dejar el cuadro en blanco para que se rellene con la transacción específica.    
8. En el menú desplegable, en fastTab **Cuentas contables** , seleccione “Ajuste de adquisición”. Para las transacciones de ajuste de adquisición, utilizaremos las mismas cuentas que se usan para las transacciones de adquisición.  
9. Haga clic en **Agregar**.
10. En el campo **Libro**, especifique o seleccione un valor.
11. En el campo **Cuenta principal**, especifique los valores deseados. Para los ajustes de adquisiciones, puede especificar una cuenta de contrapartida o dejar el cuadro en blanco para que se rellene con la transacción específica.    
12. En el menú desplegable, en fastTab **Cuentas contables** , seleccione “Depreciación”.
13. Haga clic en **Agregar**.
14. En el campo **Libro**, especifique o seleccione un valor.
15. En el campo **Cuenta principal**, especifique los valores deseados.
16. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
17. En el menú desplegable, en fastTab **Cuentas contables** , seleccione “Ajuste de depreciación”. Para las transacciones de ajuste de depreciación, utilizaremos las mismas cuentas que se usan para las transacciones de depreciación.  
18. Haga clic en **Agregar**.
19. En el campo **Libro**, especifique o seleccione un valor.
20. En el campo **Cuenta principal**, especifique los valores deseados.
21. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
22. En el menú desplegable, en fastTab **Cuentas contables** , seleccione “Venta de cancelación”.
23. Haga clic en **Agregar**.
24. En el campo **Libro**, especifique o seleccione un valor.
25. En el campo **Cuenta principal**, especifique los valores deseados. Para las cancelaciones, puede especificar una cuenta de contrapartida o dejar el cuadro en blanco para que se rellene con la transacción específica.  
26. En el menú desplegable, en fastTab **Cuentas contables** , seleccione “Residuo de cancelación”. Utilice las mismas cuentas para venta y residuo.  
27. Haga clic en **Agregar**.
28. En el campo **Libro**, especifique o seleccione un valor.
29. En el campo **Cuenta principal**, especifique los valores deseados. Para las cancelaciones, puede especificar una cuenta de contrapartida o dejar el cuadro en blanco para que se rellene con la transacción específica.  
30. Expanda la ficha desplegable **Cancelación**. Debe configurar los perfiles de contabilización de cancelación para la venta y el valor residual.  Comenzaremos con transacciones de venta.  
31. Haga clic en **Agregar**.
32. En el campo **Libro**, especifique o seleccione un valor.
33. En el campo de **valor contable**, seleccione “Valor de adquisición”.
    * El valor de adquisición dirigirá los valores de adquisición o de ajuste de adquisición para todos los años. También puede definir cuentas para estos tipos de transacción por separado.  
    * Puede establecer el proceso de cancelación para utilizar distintas cuentas en función de que la cancelación resulte en una pérdida o en una ganancia. Estableceré el tipo de valor de ventas como “Todos” para usar las mismas cuentas para todos los tipos de cancelaciones.  
34. En el campo **Cuenta principal**, especifique los valores deseados.
35. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
36. Haga clic en **Agregar**.
37. En el campo **Libro**, especifique o seleccione un valor.
38. En el campo **Valor contable**, seleccione “Depreciación (años anteriores)”.  
38. En el campo **Cuenta principal**, especifique los valores deseados.
39. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
40. Haga clic en **Agregar**.
41. En el campo **Libro**, especifique o seleccione un valor.
42. En el campo **Valor contable**, seleccione “Depreciación (este año)”.
43. En el campo **Cuenta principal**, especifique los valores deseados.
44. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
45. Haga clic en **Agregar**.
46. En el campo **Libro**, especifique o seleccione un valor.
47. En el campo **Valor contable**, seleccione “Ajustes de depreciación (años anteriores)”.
48. En el campo **Cuenta principal**, especifique los valores deseados.
49. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
50. Haga clic en **Agregar**.
51. En el campo **Libro**, especifique o seleccione un valor.
52. En el campo **Valor contable**, seleccione “Ajustes de depreciación (este año)”.
53. En el campo **Cuenta principal**, especifique los valores deseados.
54. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
55. Haga clic en **Agregar**.
56. En el campo **Libro**, especifique o seleccione un valor.
57. En el campo **Valor contable**, seleccione “Valor neto en los libros”.
58. En el campo **Cuenta principal**, especifique los valores deseados.
59. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
60. En el campo **Venta o residual**, seleccione “Residuo”.
61. Haga clic en **Agregar**.
62. En el campo **Libro**, especifique o seleccione un valor.
63. En el campo de **valor contable**, seleccione “Valor de adquisición”.
64. En el campo **Cuenta principal**, especifique los valores deseados.
65. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
66. Haga clic en **Agregar**.
67. En el campo **Libro**, especifique o seleccione un valor.
67. En el campo **Valor contable**, seleccione “Depreciación (años anteriores)”.  
68. En el campo **Cuenta principal**, especifique los valores deseados.
69. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
70. Haga clic en **Agregar**.
71. En el campo **Libro**, especifique o seleccione un valor.
72. En el campo **Valor contable**, seleccione “Depreciación (este año)”.
73. En el campo **Cuenta principal**, especifique los valores deseados.
74. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
75. Haga clic en **Agregar**.
76. En el campo **Libro**, especifique o seleccione un valor.
77. En el campo **Valor contable**, seleccione “Ajustes de depreciación (años anteriores)”.
78. En el campo **Cuenta principal**, especifique los valores deseados.
79. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
80. Haga clic en **Agregar**.
81. En el campo **Libro**, especifique o seleccione un valor.
82. En el campo **Valor contable**, seleccione “Ajustes de depreciación (este año)”.
83. En el campo **Cuenta principal**, especifique los valores deseados.
84. En el campo **Cuenta de contrapartida**, especifique los valores deseados.
85. Haga clic en **Agregar**.
86. En el campo **Libro**, especifique o seleccione un valor.
87. En el campo **Valor contable**, seleccione “Valor neto en los libros”.
88. En el campo **Cuenta principal**, especifique los valores deseados.
89. En el campo **Cuenta de contrapartida**, especifique los valores deseados.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

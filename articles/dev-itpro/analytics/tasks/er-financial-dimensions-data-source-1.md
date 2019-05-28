---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 1: Modelo de datos de diseño)'
description: En los pasos siguientes se explica cómo un administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 84f546b73eefe3ead78c6ab3fdbbc05d0db5fef5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544711"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1-design-data-model"></a>ER Usar dimensiones financieras como origen de datos (Parte 1: Modelo de datos de diseño)

[!include [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".


## <a name="create-a-new-data-model"></a>Crear un nuevo modelo de datos
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Asegúrese de que el proveedor “Litware, Inc.” está disponible y marcado como activo.  
2. Haga clic en Configuraciones de informes.
3. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
4. En el campo Nombre, escriba "Modelo de ejemplo de las dimensiones financieras".
5. Haga clic en Crear configuración.
6. Haga clic en Diseñador.
7. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
8. En el campo Nombre, escriba "Entrada".
9. Haga clic en Agregar.
10. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
11. Escriba "Empresa" en el campo Nombre.
12. Haga clic en Agregar.
    * Agregaremos nuestro modelo a una lista de registro nuevo. Esta lista expondrá (para cualquier informe ER que utilice este modelo como origen de datos) los valores de dimensiones financieras seleccionadas. Cada dimensión financiera se mostrará en esta lista como registro con los campos adecuados que representan el valor de la dimensión.  
13. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
14. En el campo Nombre, escriba "Configuración de dimensiones".
15. En el campo Tipo de artículo, seleccione Lista de registros.
16. Haga clic en Agregar.
17. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
18. En el campo Nombre, escriba "Código".
19. En el campo Tipo de artículo, seleccione Cadena.
20. Haga clic en Agregar.
21. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
22. En el campo Nombre, escriba "Nombre".
23. Haga clic en Agregar.
24. En el árbol, seleccione "Entrada".
25. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
26. En el campo Nombre, escriba "Diario".
27. En el campo Tipo de artículo, seleccione Lista de registros.
28. Haga clic en Agregar.
29. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
30. En el campo Nombre, escriba "Lote".
31. En el campo Tipo de artículo, seleccione Cadena.
32. Haga clic en Agregar.
33. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
34. En el campo Nombre, escriba "Transacción".
35. En el campo Tipo de artículo, seleccione Lista de registros.
36. Haga clic en Agregar.
37. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
38. En el campo Nombre, escriba "Fecha".
39. En el campo Tipo de artículo, seleccione Fecha.
40. Haga clic en Agregar.
41. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
42. En el campo Nombre, escriba "Débito".
43. En el campo Tipo de artículo, seleccione Real.
44. Haga clic en Agregar.
45. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
46. En el campo Nombre, escriba "Crédito".
47. Haga clic en Agregar.
48. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
49. En el campo Nombre, escriba "Divisa".
50. En el campo Tipo de artículo, seleccione Cadena.
51. Haga clic en Agregar.
52. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
53. En el campo Nombre, escriba "Asiento".
54. Haga clic en Agregar.
55. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
56. En el campo Nombre, escriba "Datos de dimensiones".
57. En el campo Tipo de artículo, seleccione Lista de registros.
58. Haga clic en Agregar.
    * Agregaremos a nuestro modelo a una lista de registro nuevo. Esta lista expondrá (para cualquier informe ER que utilice este modelo como origen de datos) los valores de las dimensiones financieras seleccionadas. Cada dimensión financiera se mostrará en esta lista como registro con los campos adecuados que representan los valores de la dimensión. El nombre de la dimensión también se mostrará en este registro como campo que se utilizará, si procede, para fines de selección.  
59. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
60. En el campo Nombre, escriba "Código".
61. En el campo Tipo de artículo, seleccione Cadena.
62. Haga clic en Agregar.
63. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
64. En el campo Nombre, escriba "Descripción".
65. Haga clic en Agregar.
66. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
67. En el campo Nombre, escriba "Nombre".
68. Haga clic en Agregar.
69. Haga clic en Guardar.
70. Cierre la página.


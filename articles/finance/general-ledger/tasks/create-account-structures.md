---
title: Crear estructuras contables
description: Esta guía de tareas describe los pasos de la creación de una estructura contable.
author: aprilolson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 93cc2e9ceb15070491bb3d0a790367e6d5bf8c4a30cd7efa690fd825963165b6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779550"
---
# <a name="create-account-structures"></a>Crear estructuras contables

[!include [banner](../../includes/banner.md)]

Esta guía de tareas describe los pasos de la creación de una estructura contable. Los pasos usan la empresa de datos de prueba USMF.

1. Vaya a **Panel de exploración > Módulos > Contabilidad general > Plan de cuentas > Estructuras > Configurar estructuras contables**.
2. En el panel **Acción**, haga clic en **Nuevo** para abrir el diálogo desplegable.
3. En el campo **Estructura contable**, escriba un nombre para describir el propósito de la estructura contable.
4. En el campo **Descripción**, escriba una descripción para especificar el propósito de la estructura contable.
5. Haga clic en **Crear**.
6. En **Segmentos y valores permitidos**, haga clic en **Agregar segmento**.
7. En la lista de dimensiones, seleccione la dimensión que se agregará a la estructura contable.
8. Al final de la lista, haga clic en **Agregar segmento**.
9. Repita del paso 6 al 9 según sea necesario.
10. En la sección **Detalles de valores permitidos**, seleccione el segmento para editar los valores permitidos.
    Por ejemplo, haga clic en **Cuenta principal**.  
11. En el campo **Operador**, seleccione una opción, como está entre e incluye.
12. En el campo **Valor**, escriba un valor. Por ejemplo, 600000.  
13. En el campo **hasta**, escriba un valor. Por ejemplo, 699999.  
14. En la sección **Detalles de valores permitidos** , haga clic en **Aplicar**.
15. Repita del paso 10 al 15 según sea necesario.  
16. En la sección **Detalles de valores permitidos** , haga clic en **Agregar nuevo criterio**.
17. En el campo Operador, seleccione una opción, como está entre e incluye.
18. En el campo **Valor**, escriba un valor. Por ejemplo, 033.  
19. En el campo **hasta**, escriba un valor. Por ejemplo, 034.  
20. Haga clic en **Aplicar**.
21. En la cuadrícula, seleccione el segmento para editar los valores permitidos. Por ejemplo, Centro de coste.  
22. En el campo **CostCenter**, escriba un valor. Por ejemplo, 007..021.  
23. En **Segmentos y valores permitidos**, haga clic en **Agregar**.
24. En el campo **MainAccount**, escriba un valor. Por ejemplo, 600000..699999  
25. En la cuadrícula, seleccione el segmento para editar los valores permitidos. Por ejemplo, Departamento.  
26. En el campo Departamento, escriba un valor. Por ejemplo, 032.  
27. En el campo CostCenter, escriba un valor. Por ejemplo, 086.  
28. En el panel **Acciones**, haga clic en **Validar**.
29. En el panel de **Acción**, haga clic en **Activar**.
30. Haga clic en **Activar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
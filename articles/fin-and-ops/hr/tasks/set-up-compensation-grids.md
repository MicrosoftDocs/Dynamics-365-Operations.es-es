---
title: Configuración de cuadrículas de compensación
description: Las cuadrículas de compensación se usan para definir y mantener las estructuras de pagos para los planes de compensación fija.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 139c4e2adbf5029f8084c7c934a05def04cd31ca
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "340416"
---
# <a name="set-up-compensation-grids"></a>Configuración de cuadrículas de compensación

[!include [task guide banner](../../includes/task-guide-banner.md)]

Las cuadrículas de compensación se usan para definir y mantener las estructuras de pagos para los planes de compensación fija. Las cuadrículas de compensación se pueden compartir entre varios planes o copiarse al crear un nuevo plan de compensación.  Antes de crear una cuadrícula de compensación, los niveles y los puntos de referencia deben estar configurados. Este ejemplo creará un nuevo tipo de categoría de cuadrícula de compensación con los datos de demostración para los niveles y los puntos de referencia. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="set-up-information-about-the-compensation-grid"></a>Configurar información sobre la cuadrícula de compensación
1. Vaya a Recursos humanos > Compensación > Compensación fija > Cuadrículas de compensación.
2. Haga clic en Nuevo.
3. En el campo Cuadrícula, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Tipo, seleccione una opción.
6. En el campo Configuración de referencia, especifique o seleccione un valor.
7. En el campo Divisa, especifique o seleccione un valor.
8. En el campo Divisa, escriba un valor.
9. En el campo Fecha de vigencia, especifique una fecha.

## <a name="add-levels-to-the-compensation-structure"></a>Agregar niveles a la estructura de compensación
1. Haga clic en Estructura de compensación.
2. En la lista, marque la fila seleccionada.
3. En el campo Nivel, especifique o seleccione un valor.
4. Haga clic en Nuevo.
5. En la lista, marque la fila seleccionada.
6. En el campo Nivel, especifique o seleccione un valor.
7. Haga clic en Nuevo.
8. En la lista, marque la fila seleccionada.
9. En el campo Nivel, especifique o seleccione un valor.
10. Haga clic en Nuevo.
11. En la lista, marque la fila seleccionada.
12. En el campo Nivel, especifique o seleccione un valor.
13. Haga clic en Nuevo.
14. En la lista, marque la fila seleccionada.
15. En el campo Nivel, especifique o seleccione un valor.

## <a name="fill-in-the-compensation-structure-with-values"></a>Rellenar la estructura de compensación con valores
1. En la lista, marque la fila seleccionada.
    * En este momento, los valores de compensación se pueden especificar manualmente en cada campo de la tabla o la funcionalidad de cambio masivo se puede usar para rellenar fácilmente varios campos y realizar cálculos básicos.  
2. Haga clic en Cambio masivo.
    * Para esta cuadrícula, aplicaremos primero el valor para punto medio del primer nivel a todos los campos de la tabla. Esta será la base para la matriz de compensación.  
3. En el campo Tipo de ajuste, seleccione una opción.
4. En el campo Importe del ajuste, escriba un número.
5. En la lista, active o desactive todas las filas.
6. Haga clic en Aplicar a la cuadrícula.
    * Ahora utilizaremos la función de cambio masivo para incrementar los importes en cada nivel posterior por un porcentaje o importe determinado. En este ejemplo, cada categoría tendrá una propagación del 12,5 % entre los puntos medios.  
7. En el campo Tipo de ajuste, seleccione una opción.
8. En el campo Importe del ajuste, escriba un número.
9. En la lista, busque y seleccione el registro deseado.
10. En la lista, busque y seleccione el registro deseado.
11. En la lista, busque y seleccione el registro deseado.
12. En la lista, busque y seleccione el registro deseado.
13. Haga clic en Aplicar a la cuadrícula.
14. En la lista, busque y seleccione el registro deseado.
15. En la lista, busque y seleccione el registro deseado.
16. En la lista, busque y seleccione el registro deseado.
17. Haga clic en Aplicar a la cuadrícula.
18. En la lista, busque y seleccione el registro deseado.
19. En la lista, busque y seleccione el registro deseado.
20. Haga clic en Aplicar a la cuadrícula.
21. En la lista, busque y seleccione el registro deseado.
22. Haga clic en Aplicar a la cuadrícula.
    * Ahora utilizaremos la función de cambio masivo para ajustar los puntos de referencia mínimo y máximo para cada nivel. Este ejemplo utilizará una propagación del 50 % de manera que el punto de referencia mínimo se ajustará un -20 % y el máximo se ajustará un +20 %.  
23. En el campo Importe del ajuste, escriba un número.
24. En el campo Punto de referencia, especifique o seleccione un valor.
25. En la lista, active o desactive todas las filas.
26. Haga clic en Aplicar a la cuadrícula.
27. En el campo Importe del ajuste, escriba un número.
28. En el campo Punto de referencia, especifique o seleccione un valor.
29. En la lista, active o desactive todas las filas.
30. Haga clic en Aplicar a la cuadrícula.


--- 
title: "Diseñar un informe para usar dimensiones financieras como origen de datos para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: c67bf235f3514a19893bcefcaae6e3bb11bbb151
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="design-a-report-to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a>Diseñar un informe para usar dimensiones financieras como origen de datos para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Usar dimensiones financieras como origen de datos (Parte 2: Asignación de modelo)".


## <a name="design-a-report-to-present-financial-dimensions"></a>Diseñar un informe para mostrar las dimensiones financieras
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, seleccione "Modelo de ejemplo de las dimensiones financieras".
3. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
4. En el campo Nuevo, especifique "Formato basado en modelo de datos Modelo de ejemplo de las dimensiones financieras".
    * Usar el modelo que se ha creado por adelantado como origen de datos para su nuevo informe.  
5. En el campo Nombre, escriba "Informe del diario contable".
6. En el campo Definición del modelo de datos, seleccione Entrada.
7. Haga clic en Crear configuración.
8. Haga clic en Diseñador.
9. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
10. En el árbol, seleccione XML\Elemento.
11. Escriba "Raíz" en el campo Nombre.
12. Haga clic en Aceptar
13. Haga clic en Agregar para abrir el cuadro desplegable.
14. En el árbol, seleccione XML\Atributo.
15. Escriba "Empresa" en el campo Nombre.
16. Haga clic en Aceptar
17. Haga clic en Agregar para abrir el cuadro desplegable.
18. En el árbol, seleccione XML\Elemento.
19. En el campo Nombre, escriba "Diario".
20. Haga clic en Aceptar
21. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML".
22. Haga clic en Agregar para abrir el cuadro desplegable.
23. En el árbol, seleccione XML\Atributo.
24. En el campo Nombre, escriba "Lote".
25. Haga clic en Aceptar
26. Haga clic en Agregar para abrir el cuadro desplegable.
27. En el árbol, seleccione XML\Elemento.
28. En el campo Nombre, escriba "Transacción".
29. Haga clic en Aceptar
30. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML".
31. Haga clic en Agregar para abrir el cuadro desplegable.
32. En el árbol, seleccione XML\Atributo.
33. En el campo Nombre, escriba "Asiento".
34. Haga clic en Aceptar
35. Haga clic en Agregar atributos.
36. En el campo Nombre, escriba "Fecha".
37. Haga clic en Aceptar
38. Haga clic en Agregar atributos.
39. En el campo Nombre, escriba "Divisa".
40. Haga clic en Aceptar
41. Haga clic en Agregar atributos.
42. En el campo Nombre, escriba "Dt".
43. Haga clic en Aceptar
44. Haga clic en Agregar atributos.
45. En el campo Nombre, escriba "Ct".
46. Haga clic en Aceptar
47. Haga clic en Agregar para abrir el cuadro desplegable.
48. En el árbol, seleccione XML\Elemento.
49. En el campo Nombre, escriba "Dimensiones".
50. Haga clic en Aceptar
51. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML".
52. Haga clic en Agregar para abrir el cuadro desplegable.
53. En el árbol, seleccione XML\Atributo.
54. En el campo Nombre, escriba "Código".
55. Haga clic en Aceptar
56. Haga clic en Agregar atributos.
57. En el campo Nombre, escriba "Valor".
58. Haga clic en Aceptar
59. Haga clic en Agregar atributos.
60. En el campo Nombre, escriba "Desc".
61. Haga clic en Aceptar

## <a name="map-report-elements-to-data-sources"></a>Asignar elementos del informe a orígenes de datos
1. Haga clic en la ficha Asignación.
2. En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras".
3. En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros".
4. En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros".
5. En el árbol, expanda "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros".
6. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML\Desc: Atributo XML".
7. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros\Descripción: Cadena".
8. Haga clic en Enlazar.
9. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML\Valor: Atributo XML".
10. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros\Código: Cadena".
11. Haga clic en Enlazar.
12. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML\Código: Atributo XML".
13. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros\Nombre: Cadena".
14. Haga clic en Enlazar.
15. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Datos de dimensiones: Lista de registros".
16. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dimensiones: Elemento XML".
17. Haga clic en Enlazar.
18. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Ct: Atributo XML".
19. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Crédito: Real".
20. Haga clic en Enlazar.
21. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Dt: Atributo XML".
22. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Débito: Real".
23. Haga clic en Enlazar.
24. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Divisa: Atributo XML".
25. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Divisa: Cadena".
26. Haga clic en Enlazar.
27. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Fecha: Atributo XML".
28. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Fecha: Fecha".
29. Haga clic en Enlazar.
30. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML\Asiento: Atributo XML".
31. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros\Asiento: Cadena".
32. Haga clic en Enlazar.
33. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Transacción: Elemento XML".
34. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Transacción: Lista de registros".
35. Haga clic en Enlazar.
36. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML\Lote: Atributo XML".
37. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros\Lote: Cadena".
38. Haga clic en Enlazar.
39. En el árbol, seleccione "Raíz: Elemento XML\Diario: Elemento XML".
40. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Diario: Lista de registros".
41. Haga clic en Enlazar.
42. En el árbol, seleccione "Raíz: Elemento XML\Empresa: Atributo XML".
43. En el árbol, seleccione "modelo: Modelo de datos Modelo de ejemplo de las dimensiones financieras\Empresa: Cadena".
44. Haga clic en Enlazar.
45. Haga clic en Guardar.
46. Cierre la página.



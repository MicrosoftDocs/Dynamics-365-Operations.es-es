---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 2: Asignación de modelo)'
description: En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48ce4942f8407242013df45f533390784694d4e6
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142556"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a>ER Usar dimensiones financieras como origen de datos (Parte 2: Asignación de modelo)

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Usar dimensiones financieras como origen de datos (Parte 1: Diseño del modelo de datos)".


## <a name="add-required-data-sources-to-model-mapping"></a>Agregar los orígenes de datos necesarios a la asignación de modelos
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, seleccione "Modelo de ejemplo de las dimensiones financieras".
3. Haga clic en Diseñador.
4. Haga clic en Asignar modelo a origen de datos.
5. Haga clic en Nuevo.
6. En el campo Definición, seleccione Entrada.
7. En el campo Nombre, escriba "Asignación de datos de dimensiones".
8. En el campo Descripción, escriba "Asignación de datos de dimensiones".
9. Haga clic en Guardar.
10. Haga clic en Diseñador.
11. En el árbol, seleccione "Dynamics 365 for Operations\Tabla".
12. Haga clic en Agregar raíz.
13. Escriba "Empresa" en el campo Nombre.
14. En el campo Tabla, escriba "CompanyInfo".
15. Haga clic en Aceptar
16. En el árbol, seleccione "Funciones\Detalles de las dimensiones financieras".
17. Haga clic en Agregar raíz.
    * Este origen de datos especifica cómo el ámbito de dimensiones financieras se definirá para los informes que usen este modelo como origen de datos.  
18. En el campo Nombre, escriba un valor.
19. Seleccione Sí en el campo Pedir dimensiones.
    * Seleccione Sí para permitir al usuario seleccionar las dimensiones en el tiempo de ejecución en el formulario del cuadro de diálogo de usuario. Si selecciona No, se utilizarán todas las dimensiones financieras de la instancia actual de forma predeterminada.  
20. En el campo Selección de dimensiones financieras, elija "Entidad jurídica".
    * Seleccione Todos para permitir al usuario seleccionar las dimensiones deseadas para la instancia actual en el campo Buscar.  Seleccione Entidad legal para permitir al usuario seleccionar las dimensiones para la empresa en el campo Buscar.  Seleccione Dimensión para permitir al usuario seleccionar las dimensiones usando un conjunto de dimensiones único.  
21. Seleccione Sí en el campo Pedir cuenta principal.
    * Establezca "Pedir cuenta principal" en Sí para permitir a los usuarios seleccionar la cuenta principal como parte de la lista de dimensiones.   Si se establece en No, la cuenta principal no se incluirá en la lista de dimensiones y la opción "La cuenta principal es obligatoria" se habilita. Si "La cuenta principal es obligatoria" se establece en Sí, incluya la cuenta principal en la lista de dimensiones independientemente de la selección del usuario.  
22. Haga clic en Aceptar.
23. En el árbol, seleccione "Dynamics 365 for Operations\Registros de tabla".
24. Haga clic en Agregar raíz.
25. En el campo Nombre, escriba "LedgerJournal".
26. Seleccione Sí en el campo Pedir consulta.
27. En el campo Tabla, escriba "LedgerJournalTable".
28. Haga clic en Aceptar

## <a name="map-data-model-elements-to-added-data-sources"></a>Asignar los elementos del modelo de datos a los orígenes de datos agregados
1. En el árbol, expanda "Diario".
2. En el árbol, expanda "Diario\Transacción".
3. En el árbol, expanda "Diario\Transacción\Datos de dimensiones".
4. En el árbol, expanda "Configuración de dimensiones".
5. En el árbol, expanda "LedgerJournal".
6. En el árbol, expanda "LibroDiario\<Relaciones".
7. En el árbol, expanda "LibroDiario\<Relaciones\LibroDiarioTrans".
8. En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Comprobante".
9. En el árbol, seleccione "Diario\Transacción\Asiento".
10. Haga clic en Enlazar.
11. En el árbol, seleccione "LibroDiario\<Relations\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)".
    * Tenga en cuenta que para las referencias a las dimensiones financieras en las que se fija, por ejemplo, LedgerDimension, está disponible un elemento de orígenes de datos correspondiente (LedgerDimension.Dimension). Este elemento de origen de datos proporciona las dimensiones financieras de las dimensiones establecidas como la lista del registro.  
12. En el árbol, expanda "LibroDiariol\<Relaciones\LibroDiarioTrans\Contabilidad.Dimensión(DimensiónContable.Dimensión)".
13. En el árbol, expanda "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensionContable.Dimensión)\Cuenta principal y dimensiones".
14. En el árbol, expanda "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimension)\Cuenta principal y dimensiones\Valor".
15. En el árbol, expanda "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)\Cuenta principal y dimensiones\Definición".
16. En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)\Cuenta principal y dimensiones\Definición\Nombre".
17. En el árbol, seleccione "Diario\Transacción\Datos de dimensiones\Nombre".
18. Haga clic en Enlazar.
19. En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)\Cuenta principal y dimensiones\Valor\Descripción".
20. En el árbol, seleccione "Diario\Transacción\Datos de dimensiones\Descripción".
21. Haga clic en Enlazar.
22. En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)\Cuenta principal y dimensiones\Valor\Código".
23. En el árbol, seleccione "Diario\Transacción\Datos de dimensiones\Código".
24. Haga clic en Enlazar.
25. En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)\Cuenta principal y dimensiones".
26. En el árbol, seleccione "Diario\Transacción\Datos de dimensiones".
27. Haga clic en Enlazar.
28. En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Débito(ImporteMonedaDébito)".
29. En el árbol, seleccione "Diario\Transacción\Débito".
30. Haga clic en Enlazar.
31. En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Fecha(TransFecha)".
32. En el árbol, seleccione "Diario\Transacción\Fecha".
33. Haga clic en Enlazar.
34. En el árbol, seleccione "LibroDiario\<Relaciones\LibriDiarioTrans\Moneda(MonedaCódigo)".
35. En el árbol, seleccione "Diario\Transacción\Divisa".
36. Haga clic en Enlazar.
37. En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Crédito(ImporteMonedaCrédito)".
38. En el árbol, seleccione "Diario\Transacción\Crédito".
39. Haga clic en Enlazar.
40. En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans".
41. En el árbol, seleccione "Diario\Transacción".
42. Haga clic en Enlazar.
43. En el árbol, seleccione "LedgerJournal\Número de lote de diario(JournalNum)".
44. En el árbol, seleccione "Diario\Lote".
45. Haga clic en Enlazar.
46. En el árbol, seleccione "LedgerJournal".
47. En el árbol, seleccione "Diario".
48. Haga clic en Enlazar.
49. En el árbol, expanda "Dimensiones".
50. En el árbol, expanda "Dimensiones\Cuenta principal y dimensiones".
51. En el árbol, expanda "Dimensiones\Cuenta principal y dimensiones\Definición".
52. En el árbol, seleccione "Dimensiones\Cuenta principal y dimensiones\Definición\Nombre".
53. En el árbol, seleccione "Configuración de dimensiones\Código".
54. Haga clic en Enlazar.
55. En el árbol, seleccione "Dimensiones\Cuenta principal y dimensiones\Definición\Nombre de columna de informe".
56. En el árbol, seleccione "Configuración de dimensiones\Nombre".
57. Haga clic en Enlazar.
58. En el árbol, seleccione "Dimensiones\Cuenta principal y dimensiones".
59. En el árbol, seleccione "Configuración de dimensiones".
60. Haga clic en Enlazar.
61. En el árbol, seleccione "Empresa".
62. Haga clic en Editar.
63. En el campo expressionAsStringText, especifique "Company.'find()'.'name()".
    * Company.'find()'.'name()'  
64. Haga clic en Guardar.
65. Cierre la página.
66. Haga clic en Guardar.
67. Cierre la página.

## <a name="complete-this-draft-models-version"></a>Completar la versión de este modelo de borrador
1. Cierre la página.
2. Cierre la página.
3. Haga clic en Cambiar estado.
4. Haga clic en Completar.
5. Haga clic en Aceptar


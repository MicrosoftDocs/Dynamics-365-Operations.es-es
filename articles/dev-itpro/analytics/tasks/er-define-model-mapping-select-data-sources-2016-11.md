--- 
title: "Definir asignaciones de modelo de ER y seleccionar orígenes de datos para ellas"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema desarrollador de informes electrónicos puede seleccionar orígenes de datos para un modelo de datos de informes electrónicos."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 2beda3555274fee3f17ad13c54c6823307216385
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a>Definir asignaciones de modelo de ER y seleccionar orígenes de datos para ellas

[!include [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema desarrollador de informes electrónicos puede seleccionar orígenes de datos para un modelo de datos de informes electrónicos. Los orígenes de datos estarán vinculados a componentes individuales del modelo de datos seleccionado en el momento del diseño y rellenarán los datos empresariales según ese modelo de datos en el tiempo de ejecución. En este ejemplo, seleccionará orígenes de datos para un modelo de datos existente que se ha creado para la empresa de demostración, Litware, Inc. Para completar estos pasos, debe completar primero los pasos del procedimiento "Creación de un nuevo modelo de datos".


## <a name="open-the-electronic-reporting-configurations-tree"></a>Abra árbol de configuraciones de Electronic Reporting (informes electrónicos)
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Configuraciones de informes.

## <a name="insert-a-new-model-mapping"></a>Inserción de una asignación de modelo nueva
1. En el árbol, seleccione Pagos (modelo simplificado).
2. Haga clic en Diseñador.
3. Haga clic en Asignar modelo a origen de datos.
4. Haga clic en Nuevo.
    * Esto creará un nuevo registro que asignará el modelo de datos a orígenes de datos. En este ejemplo, asignará el modelo de datos a orígenes de datos para el tipo de pago deseado: transferencia de crédito.     Es posible diseñar más de una asignación para un modelo de datos en particular. Por ejemplo, podría crear una asignación para los distintos tipos de pagos, por ejemplo de domiciliaciones bancarias o transferencias de crédito. En este ejemplo, creará una asignación para transferencias de crédito.  
5. En el campo Nombre, escriba "Asignación CT".
    * Asignación CT  
6. En el campo Descripción, escriba "Asignación CT para modelo de pago".
    * Asignación del modelo de pago CT  
7. En el campo Definición, escriba "CustomerCreditTransferInitiation".
    * CustomerCreditTransferInitiation  
8. ResolveChanges la Definición.
9. Haga clic en Guardar.

## <a name="define-required-data-sources-for-the-current-model-mapping"></a>Definición de orígenes de datos necesarios para la asignación de modelo actual
1. Haga clic en Diseñador.
2. En el árbol, seleccione "Dynamics 365 for Operations\Registros de tabla".
3. Haga clic en Agregar raíz.
    * Especifique este origen de datos para acceder a las transacciones de pago.  
4. En el campo Nombre, escriba "Transacciones".
    * Transacciones  
5. Especifique "Transacciones" en el campo Etiqueta.
    * Transacciones  
6. En el campo Ayuda, especifique "Líneas de diario de contabilidad".
    * Líneas de diario de contabilidad  
7. Seleccione Sí en el campo Pedir consulta.
    * Seleccione Sí.  
8. En el campo Tabla, escriba "LedgerJournalTrans".
    * LedgerJournalTrans  
9. Haga clic en Aceptar
    * Seleccione la tabla LedgerJournalTrans como origen de datos para el modelo de datos actual.  
10. En el árbol, seleccione el apartado "Funciones\Campo calculado".
11. Haga clic en Agregar.
    * Haga clic en Agregar para agregar un nuevo campo calculado.  
12. En el campo Nombre, escriba "$EndToEndID".
    * $EndToEndID  
13. Haga clic en Editar fórmula.
14. En el árbol, seleccione String\CONCATENATE.
15. Haga clic en Agregar función.
16. En el árbol, expanda Transacciones.
17. En el árbol, seleccione Transacciones\Asiento.
18. Haga clic en Agregar origen de datos.
19. En el campo Fórmula, escriba "CONCATENATE(Transactions.Voucher, "-", '.
    * Escriba [ , “-“, ] al final de la fórmula.  
20. En el árbol, seleccione String\TEXT.
21. Haga clic en Agregar función.
22. En el árbol, seleccione Transacciones\Record-ID(RecId).
23. Haga clic en Agregar origen de datos.
24. En el campo Fórmula, escriba "CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))".
    * Escriba [))] al final de la fórmula.  
25. Haga clic en Guardar.
    * Asegúrese de que no se hayan detectado errores en la fórmula creada. Consulte la ficha ERRORES debajo del control de edición de la fórmula.  
26. Cierre la página.
27. Haga clic en Aceptar
    * Agregue el campo calculado a este origen de datos.  
28. Haga clic en Agregar.
    * Haga clic en Agregar para agregar un nuevo campo calculado.  
29. Escriba "$Amount'" en el campo Nombre.
    * $Amount  
30. Haga clic en Editar fórmula.
31. En el árbol, expanda Transacciones.
32. En el árbol, seleccione Transacciones\Débito(AmountCurDebit).
33. Haga clic en Agregar origen de datos.
34. En el campo Fórmula, escriba 'Transactions.AmountCurDebit - '.
    * Escriba [ - ] al final de la fórmula.  
35. En el árbol, seleccione Transacciones\Crédito(AmountCurCredit).
36. Haga clic en Agregar origen de datos.
37. Haga clic en Guardar.
38. Cierre la página.
39. Haga clic en Aceptar
    * Esto agregará el campo calculado $Amount al origen de datos seleccionado para el modelo de datos actual.  
40. En el árbol, seleccione 'Transacciones\$Importe'.
41. En el árbol, expanda Transacciones.
42. En el árbol, expanda o contraiga 'Transacciones\$Importe'.
43. En el árbol, expanda o contraiga "Transacciones".
44. En el árbol, seleccione "Dynamics 365 for Operations\Registros de tabla".
45. Haga clic en Agregar raíz.
    * Especifique este origen de datos para acceder a los detalles de la cuenta bancaria de la empresa.  
46. En el campo Nombre, escriba "BankAccount".
    * BankAccount  
47. Especifique "Cuenta bancaria" en el campo Etiqueta.
    * Cuenta bancaria  
48. Especifique "Cuenta bancaria" en el campo Ayuda.
    * Cuenta bancaria  
49. Seleccione Sí en el campo Pedir consulta.
    * Seleccione Sí.  
50. En el campo Tabla, escriba "BankAccountTable".
    * BankAccountTable  
51. Haga clic en Aceptar
    * Seleccione la tabla BankAccountTable como origen de datos para el modelo de datos actual.  
52. Haga clic en Agregar raíz.
    * Especifique este origen de datos para acceder a los requisitos de la empresa.  
53. Escriba "Empresa" en el campo Nombre.
    * Compañía  
54. En el campo Etiqueta, escriba un valor.
    * Información de la empresa  
55. En el campo Ayuda, escriba "Información de la empresa".
    * Información de la empresa  
56. Seleccione Sí en el campo Pedir consulta.
    * Seleccione Sí.  
57. En el campo Tabla, escriba "CompanyInfo".
    * CompanyInfo  
58. Haga clic en Aceptar
    * Seleccione la tabla CompanyInfo como origen de datos para el modelo de datos actual.  
59. En el árbol, seleccione el apartado "Funciones\Campo calculado".
60. Haga clic en Agregar raíz.
    * Inserte un campo calculado como un nuevo origen de datos.  
61. En el campo Nombre, escriba "ProcessingDateTime".
    * ProcessingDateTime  
62. En el campo Etiqueta, escriba "Fecha y hora de procesamiento".
    * Fecha y hora de procesamiento  
63. Haga clic en Editar fórmula.
64. En el árbol, seleccione "Fecha/hora\SESSIONNOW"
65. Haga clic en Agregar función.
66. Haga clic en Guardar.
67. Cierre la página.
68. Haga clic en Aceptar
    * Agregue el campo calculado ProcessingDateTime como origen de datos para el modelo de datos actual.  
69. Haga clic en Guardar.
70. Cierre la página.
71. Cierre la página.
72. Cierre la página.



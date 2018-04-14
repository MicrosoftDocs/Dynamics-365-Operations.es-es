--- 
title: "Asignar un modelo de datos para seleccionar orígenes de datos para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario con rol de Administrador del Sistema o Desarrollador de Informes Electrónicos puede asignar un modelo de datos de Informes Electrónicos (ER) a los orígenes de datos seleccionados de Dynamics 365 for Finance and Operations, Enterprise edition (noviembre de 2016)."
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 13b7fe7f7bfe24bd275428e931993aa46ecb9945
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---
# <a name="map-a-data-model-to-selected-data-sources-for-electronic-reporting-er"></a>Asignar un modelo de datos para seleccionar orígenes de datos para informes electrónicos (ER)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de Administrador del Sistema o Desarrollador de Informes Electrónicos puede asignar un modelo de datos de Informes Electrónicos (ER) a los orígenes de datos seleccionados de Dynamics 365 for Finance and Operations. Esta asignación de modelo se usará posteriormente como origen de datos en una configuración de formato que se usará para gestionar documentos de pago electrónico. En este ejemplo, asignará un modelo de datos de la empresa de demostración Litware, Inc. a los orígenes de datos. Para completar estos pasos, primero debe completar los pasos del procedimiento "Selección de orígenes de datos para asignar modelos".


## <a name="open-er-configurations-tree"></a>Apertura del árbol de configuraciones de informes electrónicos
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Configuraciones.

## <a name="select-created-model-mapping"></a>Selección de la asignación de modelo creada
1. En el árbol, seleccione Pagos (modelo simplificado).
    * Asegúrese de que la configuración del modelo "Pagos (modelo simplificado)" se haya creado antes. Si no, detenga ahora y vuelva tras completar la guía de tareas “Crear una nueva configuración con el modelo de datos del dominio seleccionado”.  
2. Haga clic en Diseñador de modelo.
3. Haga clic en Asignar modelo a origen de datos.
4. Seleccione el registro Asignación CT.
    * Asignación CT  

## <a name="bind-created-data-sources-to-data-model-elements"></a>Enlace de los orígenes de datos creados con elementos del modelo de datos
1. Haga clic en Diseñador.
2. En el árbol, seleccione "Fecha y hora de procesamiento(ProcessingDateTime)".
3. En el árbol, seleccione Fecha de procesamiento(ProcessingDateTime).
4. Haga clic en Enlazar.
5. En el árbol, seleccione Identificación del mensaje de pago(MessageIdentification).
6. En el árbol, expanda Transacciones.
7. En el árbol, seleccione Transacciones\Número de lote de diario(JournalNum).
8. Haga clic en Enlazar.
9. En el árbol, seleccione Pagos.
10. En el árbol, seleccione Transacciones.
11. Haga clic en Enlazar.
12. En el árbol, expanda Pagos = Transacciones.
13. En el árbol, expanda Pagos = Transacciones\Acreedor.
14. En el árbol, expanda Pagos = Transacciones\Acreedor\Cuenta.
15. En el árbol, seleccione Pagos = Transacciones\Acreedor\Cuenta\Código de divisa(Currency).
16. En el árbol, expanda Transacciones\vendBankAccountInTransactionCompany().
17. En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()\Divisa(CurrencyCode).
18. Haga clic en Enlazar.
19. En el árbol, seleccione Pagos = Transacciones\Acreedor\Cuenta\Código IBAN(IBAN).
20. En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()\IBAN(BankIBAN).
21. Haga clic en Enlazar.
22. En el árbol, seleccione Pagos = Transacciones\Acreedor\Cuenta\Número.
23. En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()\Número de cuenta bancaria(AccountNum)'.
24. Haga clic en Enlazar.
25. En el árbol, expanda Pagos = Transacciones\Acreedor\Agente.
26. En el árbol, seleccione Pagos = Transacciones\Acreedor\Agente\Nombre.
27. En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()Name.
28. Haga clic en Enlazar.
29. En el árbol, seleccione Pagos = Transacciones\Acreedor\Agente\Número de ruta(RoutingNumber).
30. En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()\Número de ruta(RegistrationNum).
31. Haga clic en Enlazar.
32. En el árbol, seleccione Pagos = Transacciones\Acreedor\Agente\Código SWIFT(SWIFT).
33. En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()\Código SWIFT(SWIFTNo).
34. Haga clic en Enlazar.
35. En el árbol, seleccione Pagos = Transacciones\Acreedor\Nombre.
36. En el árbol, expanda Transacciones\findVendTable().
37. En el árbol, seleccione "Transacciones\findVendTable()\name()".
38. Haga clic en Enlazar.
39. En el árbol, seleccione Pagos = Transacciones\Código de divisa(Currency).
40. En el árbol, expanda "Transacciones\>Relaciones".
41. En el árbol, expanda "Transacciones\>Relaciones\Tabla de divisas(Divisa)".
42. En el árbol, seleccione "Transacciones\>Relaciones\Tabla de divisas(Divisa)\Código de divisa(CurrencyCodeISO).
43. Haga clic en Enlazar.
44. En el árbol, expanda Pagos = Transacciones\Deudor.
45. En el árbol, expanda Pagos = Transacciones\Deudor\Cuenta.
46. En el árbol, seleccione Pagos = Transacciones\Deudor\Cuenta\Código de divisa(Currency).
47. En el árbol, seleccione Cuenta bancaria(BankAccount).
48. En el árbol, expanda Cuenta bancaria(BankAccount).
49. En el árbol, seleccione Cuenta bancaria(BankAccount)\Divisa(CurrencyCode).
50. Haga clic en Enlazar.
51. En el árbol, seleccione Cuenta bancaria(BankAccount)\IBAN.
52. En el árbol, seleccione Pagos = Transacciones\Deudor\Cuenta\Código IBAN(IBAN).
53. Haga clic en Enlazar.
54. En el árbol, seleccione Pagos = Transacciones\Deudor\Cuenta\Número.
55. En árbol, seleccione Cuenta bancaria(BankAccount)\Número de cuenta bancaria(AccountNum).
56. Haga clic en Enlazar.
57. En el árbol, expanda Pagos = Transacciones\Deudor\Agente.
58. En el árbol, seleccione Pagos = Transacciones\Deudor\Agente\Nombre.
59. En el árbol, seleccione Cuenta bancaria(BankAccount)\Nombre.
60. Haga clic en Enlazar.
61. En el árbol, seleccione Pagos = Transacciones\Deudor\Agente\Número de ruta(RoutingNumber).
62. En árbol, seleccione Cuenta bancaria(BankAccount)\Número de ruta(RegistrationNum).
63. Haga clic en Enlazar.
64. En el árbol, seleccione Pagos = Transacciones\Deudor\Agente\Código SWIFT(SWIFT).
65. En el árbol, seleccione Cuenta bancaria(BankAccount)\Código SWIFT(SWIFTNo).
66. Haga clic en Enlazar.
67. En el árbol, seleccione Pagos = Transacciones\Deudor\Nombre.
68. En el árbol, seleccione Información de la empresa(Company).
69. En el árbol, expanda Información de la empresa(Company).
70. En el árbol, seleccione Información de la empresa(Company)\Nombre.
71. Haga clic en Enlazar.
72. En el árbol, seleccione Pagos = Transacciones\Descripción.
73. En el árbol, seleccione Transacciones\Descripción(Txt).
74. Haga clic en Enlazar.
75. En el árbol, seleccione Pagos = Transacciones\Código de identificación de extremo a extremo(End2EndID).
76. En el árbol, seleccione Transacciones\$EndToEndID.
77. Haga clic en Enlazar.
78. En el árbol, seleccione Pagos = Transacciones\Importe ordenado(InstructedAmount).
79. En el árbol, seleccione 'Transacciones\$Importe'.
80. Haga clic en Enlazar.
81. En el árbol, seleccione Pagos = Transacciones\Fecha de la transacción(TransactionDate).
82. En el árbol, seleccione Transacciones\Fecha(TransDate).
83. Haga clic en Enlazar.

## <a name="validate-created-mapping"></a>Validación de la asignación creada
1. Haga clic en Validar.
    * Valide la nueva asignación para garantizar que todos los enlaces son aceptables.  
2. Haga clic en la flecha para expandir o contraer la sección Lista de errores.
3. Haga clic en Guardar.
4. Cierre la página.
5. Cierre la página.
6. Cierre la página.

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a>Cambio del estado de la versión actual de la configuración del modelo
1. Haga clic en Cambiar estado.
    * Cambie el estado de la configuración del modelo diseñado: de Borrador a Completado para que esté disponible para el diseño del formato de pago.  
2. Haga clic en Completar.
    * Seleccione Completar.  
3. En el campo Descripción, escriba un valor.
    * Para ver un ejemplo, "versión 1".  
4. Haga clic en Aceptar
5. Seleccione la versión finalizada de la configuración actual.
    * Observe cómo la configuración creada se guarda como versión completada 1.  



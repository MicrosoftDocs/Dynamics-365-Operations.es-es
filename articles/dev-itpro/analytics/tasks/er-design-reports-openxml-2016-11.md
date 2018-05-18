--- 
title: "Diseñar una configuración para generar informes con formato OpenXML para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga una plantilla para generar documentos electrónicos en formato OPENXML."
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
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 09789957839097ba2898544102af908c198090c7
ms.contentlocale: es-es
ms.lasthandoff: 11/14/2017

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a>Diseñar una configuración para generar informes con formato OpenXML para informes electrónicos (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga una plantilla para generar documentos electrónicos en formato OPENXML. Esta configuración se usará para procesar los pagos de proveedor.



En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en empresa GBSI.



Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones. También debe descargar y guardar el archivo de Microsoft Excel, [Plantilla de informe de pago](https://go.microsoft.com/fwlink/?linkid=862266). 

## <a name="upload-the-payments-data-model-configuration"></a>Cargar la configuración del modelo de datos de pagos
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. En la lista, marque la fila seleccionada.
    * Seleccione el proveedor de la configuración de la empresa de ejemplo, Litware, Inc. Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".  
3. Haga clic en Definir como activo.
4. Haga clic en Repositorios.
    * Seleccione un repositorio para el tipo de recursos de operaciones, si está disponible. Si está disponible, omita los siguientes pasos acerca de la creación de un nuevo repositorio.  
5. Haga clic en Agregar para abrir el cuadro desplegable.
6. En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".
7. Haga clic en Crear repositorio.
8. Haga clic en Aceptar
9. Haga clic en Abrir.
10. En el árbol, seleccione "Modelo de pago".
11. Haga clic en Importar.
    * Importe este modelo de datos. Se usará como origen de datos en una nueva configuración de formato. Omita este paso si esta configuración ya se ha importado.  
12. Haga clic en Sí.
13. Cierre la página.
14. Cierre la página.

## <a name="create-a-new-format-configuration"></a>Creación de una configuración de formato nueva
1. Haga clic en Configuraciones de informes.
2. En el árbol, seleccione "Modelo de pago".
3. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
4. En el campo Nuevo, especifique "Formato basado en modelo de datos PaymentModel".
    * Cree un formato que se base en el modelo de datos de PaymentModel.  
5. En el campo Nombre, escriba "Informe de hoja de cálculo de muestra".
    * Informe de hoja de cálculo de muestra  
6. En el campo Descripción, escriba "Informe de hoja de cálculo para pagos de proveedores".
    * Informe de hoja de cálculo para pagos de proveedores.  
7. En el campo definición del modelo de Datos, introduzca o seleccione un valor.
    * Seleccione la definición "CustomerCreditTransferInitiation".  
8. Haga clic en Crear configuración.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Diseñar un documento nuevo en formato de hoja de cálculo OPENXML
1. En el árbol, seleccione "Modelo de pago\Informe de hoja de cálculo de muestra".
2. Haga clic en Diseñador.
3. En el panel de acciones, haga clic en Importar.
4. Haga clic en Importar desde Excel.
5. Haga clic en Archivos adjuntos.
    * Adjunte el documento de Excel existente como plantilla.  
6. Haga clic en Nuevo.
7. Haga clic en Archivo.
    * Señale al archivo de Excel existente.  
8. Cierre la página.
9. En el campo Plantilla, especifique o seleccione un valor.
    * Seleccione el archivo de Excel adjunto que se usará como plantilla.  
10. Haga clic en Aceptar
    * Tenga en cuenta que los componentes en formato ER se han creado en el formato de diseño basado en la estructura del documento de MS Excel de referencia (intervalos con nombre).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Crear un nuevo origen de datos para calcular totales por códigos de divisa
1. Haga clic en la ficha Asignación.
2. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
3. En el árbol, seleccione "Funciones\Agrupar por".
4. En el campo Nombre, escriba "PaymentByCurrency".
    * PaymentByCurrency  
5. Haga clic en Editar grupo por.
6. En el árbol , expanda "modelo".
7. En el árbol, seleccione modelo\Pagos.
8. Haga clic en Agregar campo a.
9. Haga clic en Elementos para agrupar.
10. En el árbol, expanda modelo\Pagos.
11. En el árbol, seleccione "modelo\Pagos\Divisa".
12. Haga clic en Agregar campo a.
13. Haga clic en Campos agrupados.
14. En el árbol, seleccione "modelo\Pagos\Importe ordenado(InstructedAmount)".
15. Haga clic en Agregar campo a.
16. Haga clic en Campos de agregación.
17. En el campo Método, seleccione una opción.
    * Seleccione la función de agregación SUMA.  
18. En el campo Nombre, escriba "TotalInstructuredAmount".
    * TotalInstructuredAmount  
19. Haga clic en Guardar.
20. Cierre la página.
21. Haga clic en Aceptar

## <a name="map-format-components-to-data-sources"></a>Asignar componentes de formato a orígenes de datos
1. En el árbol , expanda "modelo".
2. En el árbol, expanda modelo\Pagos.
3. En el árbol, expanda "modelo\Pagos\Parte iniciadora(InitiatingParty)".
4. En el árbol, seleccione "modelo\Pagos\Parte iniciadora(InitiatingParty)\Name".
5. En el árbol, expanda 'Excel\ReportHeader'.
6. En el árbol, seleccione ''Excel\ReportHeader\CompanyName".
7. Haga clic en Enlazar.
8. En el árbol, expanda modelo\Pagos\Acreedor.
9. En el árbol, expanda "modelo\Pagos\Acreedor\Identificación".
10. En el árbol, seleccione "modelo\Pagos\Cuenta de acreedor(Creditor)\Identification\Source ID(SourceID)".
11. En el árbol, expanda 'Excel\PaymLines'.
12. En el árbol, seleccione ''Excel\PaymLines\VendAccountName".
13. Haga clic en Enlazar.
14. En el árbol, seleccione modelo\Pagos\Acreedor\Nombre.
15. En el árbol, seleccione ''Excel\PaymLines\VendName".
16. Haga clic en Enlazar.
17. En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)”.
18. En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Nombre”.
19. En el árbol, seleccione ''Excel\PaymLines\Bank".
20. Haga clic en Enlazar.
21. En el árbol, seleccione "modelo\Pagos\Agente del acreedor(CreditorAgent)\Número de ruta(RoutingNumber)".
22. En el árbol, seleccione ''Excel\PaymLines\RoutingNumber".
23. Haga clic en Enlazar.
24. En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)”.
25. En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)\Identification”.
26. En el árbol, seleccione "modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Identification\Número”.
27. En el árbol, seleccione ''Excel\PaymLines\AccountNumber".
28. Haga clic en Enlazar.
29. En el árbol, seleccione "modelo\Pagos\Importe ordenado(InstructedAmount)".
30. En el árbol, seleccione ''Excel\PaymLines\Débito".
31. Haga clic en Enlazar.
32. En el árbol, expanda modelo\Pagos\Acreedor.
33. En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)”.
34. En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)”.
35. En el árbol, seleccione "modelo\Pagos\Divisa".
36. En el árbol, seleccione ''Excel\PaymLines\Moneda".
37. Haga clic en Enlazar.
38. En el árbol, expanda "PaymentByCurrency".
39. En el árbol, expanda "PaymentByCurrency\agrupado".
40. En el árbol, seleccione "PaymentByCurrency\agrupado\Divisa".
41. En el árbol, expanda "Excel\SummaryLines".
42. En el árbol, seleccione ''Excel\SummaryLines\SummaryCurrency".
43. Haga clic en Enlazar.
44. En el árbol, expanda "PaymentByCurrency\agregado".
45. En el árbol, seleccione "PaymentByCurrency\agregado\TotalInstructuredAmount".
46. En el árbol, seleccione ''Excel\SummaryLines\SummaryAmount".
47. Haga clic en Enlazar.
48. En el árbol, seleccione "PaymentByCurrency".
49. En el árbol, seleccione "Excel\SummaryLines".
50. Haga clic en Enlazar.
51. En el árbol, seleccione modelo\Pagos.
52. En el árbol, seleccione ''Excel\PaymLines".
53. Haga clic en Enlazar.
54. Haga clic en Guardar.
55. Cierre la página.

## <a name="use-the-created-configuration-for-payments-processing"></a>Usar la configuración creada para procesar los pagos
1. Haga clic en Cambiar estado.
2. Haga clic en Completar.
3. Haga clic en Aceptar
4. Cierre la página.
5. Cierre la página.
6. Vaya a Proveedores > Configuración de pagos > Formas de pago.
7. Use el Filtro Rápido para filtrar el campo Método de pago con un valor de "Electronic".
    * Electrónica  
8. Haga clic en Editar.
9. Expanda la sección Formatos de archivo.
10. Seleccione Sí en el campo Informes electrónicos genéricos.
11. En el campo Configuración de formato de exportación, especifique o seleccione un valor.
    * Seleccione la configuración "Informe de hoja de cálculo de muestra”.  
12. Haga clic en Guardar.
13. Cierre la página.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Usar la configuración creada para probar el procesamiento de diarios de pago
1. Vaya a Proveedores > Pagos > Diario de pagos.
2. Haga clic en Nuevo.
    * Crear un diario de pago nuevo.  
3. En el campo Nombre, escriba "VendPay".
    * VendPay  
4. Haga clic en Líneas.
5. En el campo Cuenta, especifique los valores "GB_SI_000001".
    * GB_SI_000001  
6. Establezca Débito en "1000".
7. Haga clic en Nuevo.
8. En el campo Cuenta, especifique los valores "GB_SI_000005".
    * GB_SI_000005  
9. Establezca Débito en "2000".
10. En el campo Divisa, escriba "EUR".
    * EUR  
11. En el campo Cuenta de contrapartida, especifique los valores "GBSI OPER".
    * GBSI OPER  
12. En el campo Forma de pago, escriba un "Electrónica".
    * Electrónica  
13. Haga clic en Guardar.
14. Haga clic en Generar pagos.
15. En el campo Forma de pago, escriba un "Electrónica".
    * Electrónica  
16. En el campo Nombre, escriba "Pagos".
    * Por ejemplo, escriba Pagos.  
17. En el campo Cuenta bancaria, escriba "GBSI OPER".
    * GBSI OPER  
18. Haga clic en Aceptar
19. Haga clic en Aceptar
    * Revise la hoja de trabajo creada, incluidos los detalles de líneas de pago así como los totales para cada código de divisa usado en este mensaje de pago.  



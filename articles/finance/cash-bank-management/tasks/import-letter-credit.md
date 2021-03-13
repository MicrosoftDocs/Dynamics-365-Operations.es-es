---
title: Importar créditos documentarios
description: Este procedimiento le muestra el proceso para importar una carta de crédito.
author: kweekley
manager: AnnBe
ms.date: 02/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 76dedb12eef0f8282f04f680cab51a8ccf3e8221
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009552"
---
# <a name="import-letter-of-credit"></a>Importar créditos documentarios

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra el proceso para importar una carta de crédito. Se debe configurar lo siguiente para completar este procedimiento: instalaciones bancarias, perfiles de contabilización, un acuerdo de instalaciones bancarias e información bancaria del proveedor.

Este procedimiento usa la empresa de demostración USMF.


## <a name="create-a-purchase-order-with-letter-of-credit"></a>Crear un pedido de compra con carta de crédito
1. Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.
2. Haga clic en Nuevo.
3. En el campo Cuenta de proveedor, especifique o seleccione un valor.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Expanda la sección General.
7. En el campo Sitio, especifique o seleccione un valor.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo Almacén, especifique o seleccione un valor.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. En el campo Fecha contable, escriba una fecha.
12. En el campo Fecha de entrega, especifique una fecha.
    * Nota: Se debe seleccionar el campo "Tipo de documento bancario" con el valor "Crédito documentario".  
13. Haga clic en Aceptar
14. En el campo Número de artículo, especifique o seleccione un valor.
15. En la lista, busque y seleccione el registro deseado.
16. En la lista, haga clic en el vínculo de la fila seleccionada.
17. Expanda la sección Detalles de línea.
18. Haga clic en la ficha Entrega.
19. En el campo Fecha de entrega, especifique una fecha.
20. En el campo Fecha de entrega confirmada, especifique una fecha.
21. En el campo Precio unitario, escriba un número.
    * Defina los detalles de la carta de crédito.  
22. En el panel de acciones, haga clic en Gestionar.
23. Haga clic en Crédito documentario/remesa documentaria.
24. En el campo Fecha de solicitud, especifique una fecha y una hora.
    * Compruebe que el campo "Cuenta bancaria" tiene la cuenta bancaria activa predeterminada, que se basa en la fecha de la solicitud.  
25. En el campo Número de documento bancario, escriba un valor.
26. En el campo Fecha de recepción, especifique una fecha y una hora.
27. Expanda la sección Documento bancario.
28. En el campo Fecha de vencimiento, especifique una fecha y una hora.
29. Expanda la sección Detalles del banco.
30. En el campo Banco avisador, especifique o seleccione un valor.
31. En la lista, haga clic en el vínculo de la fila seleccionada.
32. Haga clic en Guardar.
33. Haga clic en Obtener envíos de pedido de compra.
34. Cierre la página.
35. En el panel de acciones, haga clic en Compra.
36. Haga clic en Confirmar.
37. En el panel de acciones, haga clic en Gestionar.
38. Haga clic en Crédito documentario/remesa documentaria.
39. Haga clic Procesar.
40. Haga clic en Confirmar.
    * Compruebe que el saldo del crédito reduce el importe del pedido de compra.  En este ejemplo, Importe de compra = 500,00, Límite de crédito = 10000,00, por lo tanto, Saldo del crédito = 9500,00.  
41. Cierre la página.
42. En el campo Precio unitario, escriba un número.
43. Haga clic en Guardar.
44. En el panel de acciones, haga clic en Compra.
45. Haga clic en Confirmar.
    * Modifique la carta de crédito, debido al cambio del precio por unidad.  
46. En el panel de acciones, haga clic en Gestionar.
47. Haga clic en Crédito documentario/remesa documentaria.
    * Modifique la carta de crédito, debido al cambio del Precio unitario de compra.  
48. Haga clic Procesar.
49. Haga Clic en Enmendar.
50. Haga clic en Quitar.
51. Haga clic en Sí.
52. Haga clic en Obtener envíos de pedido de compra.
53. Haga clic Procesar.
54. Haga clic en Confirmar.
    * Compruebe que el saldo del crédito reduce el importe del pedido de compra.  En este ejemplo, Importe de compra editado= 600,00, Límite de crédito = 10000,00, por lo tanto, Saldo del crédito = 9400,00.  
55. Cierre la página.

## <a name="post-packing-slip"></a>Registrar albarán
1. En el panel de acciones, haga clic en Recibir.
2. Haga clic en Recepción de producto.
3. En el campo PurchParmTable_Num, escriba un valor.
    * Seleccione el Número de envío creado con referencia a la carta de crédito.  
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Fecha de recepción de producto, especifique una fecha.
6. Haga clic en Aceptar
7. Cierre la página.
8. Cierre la página.

## <a name="verify-import-letter-of-credit-status"></a>Compruebe el estado de la carta de crédito de importación.
1. Vaya a Gestión de efectivo y bancos > Carta de crédito > Importar carta de crédito e importar cobro.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Compruebe el estado de la carta de crédito de importación.     
4. Cierre la página.
5. Cierre la página.

## <a name="post-purchase-invoice"></a>Registrar factura de compra
1. Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.
    * Seleccione el pedido de compra creado con la carta de crédito.  
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el panel de acciones, haga clic en Factura.
5. Haga clic en Factura.
6. En el campo Número, escriba un valor.
7. En el campo Número de envío, especifique o seleccione un valor.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo Fecha de la factura, especifique una fecha.
10. Haga clic en Actualizar estado de conciliación.
11. Haga clic en Registrar.
12. Cierre la página.
13. Cierre la página.

## <a name="verify-import-letter-of-credit-status"></a>Compruebe el estado de la carta de crédito de importación.
1. Vaya a Gestión de efectivo y bancos > Carta de crédito > Importar carta de crédito e importar cobro.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Compruebe la carta de crédito de importación.  
    * Validar: Estado de envío = detalles de créditos bancarios facturados  
4. Haga clic en Ver.
5. Haga clic en Imprimir solicitud.
6. Haga clic en Aceptar
    * Compruebe que se imprime la solicitud de la carta de crédito.  
7. Cierre la página.
8. Cierre la página.
9. Cierre la página.

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a>Registre el diario de pagos del proveedor para la factura de compra creada con la carta de crédito
1. Vaya a Proveedores > Pagos > Diario de pagos.
2. Haga clic en Nuevo.
3. En el campo Nombre, especifique o seleccione un valor.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Haga clic en Líneas.
6. En el campo Fecha, escriba una fecha.
7. En el campo Cuenta, especifique los valores deseados.
8. Haga clic en Liquidar transacciones.
9. Expanda la sección Totales.
10. En el campo Mostrar, seleccione una opción.
    * Compruebe que se han actualizado los campos Número de documento bancario y Número de envío.  
11. Active la casilla Marcar.
12. Haga clic en Aceptar
13. Haga clic en la ficha Pago.
    * Compruebe que se han actualizado los campos Número de documento bancario y Número de envío.  
14. Haga clic en Registrar.
15. Cierre la página.
16. Cierre la página.

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a>Comprobar el estado de la carta de crédito de importación tras el pago de la factura
1. Vaya a Gestión de efectivo y bancos > Carta de crédito > Importar carta de crédito e importar cobro.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Compruebe el estado de la carta de crédito de importación.   
4. Cierre la página.

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a>Comprobar el límite de crédito bancario y el informe de utilización
1. Vaya a Gestión de efectivo y bancos > Consultas e informes > Cartas de crédito o garantía > Informe de créditos bancarios y uso.
2. Expanda la sección Registros que incluir.
3. Haga clic en Filtro.
    * Defina el campo Criterios con la cuenta bancaria necesaria.  
4. En el campo Criterios, especifique o seleccione un valor.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en Aceptar
7. Haga clic en Aceptar
    * Compruebe el informe que muestra las transacciones.  
    * Compruebe que el informe muestra las transacciones con número de documento bancario, límite de crédito, importe usado y el importe de saldo del crédito.  
8. Cierre la página.


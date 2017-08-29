--- 
title: "Exportar una carta de crédito"
description: "Este procedimiento le muestra el proceso de la carta de crédito de exportación."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 55f62b501b545db54d717d8c66d09ec831cb286f
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="export-a-letter-of-credit"></a>Exportar una carta de crédito

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra el proceso de la carta de crédito de exportación.

Una carta de crédito es un contrato que emite un banco, por el cual el banco garantiza el pago en nombre del comprador, siempre que se cumplan las condiciones del contrato entre el comprador y el vendedor.



Ejecute los procedimientos "Configuración de instalaciones bancarias y perfiles de contabilización" y "Carta de crédito_Crear un acuerdo de instalaciones bancarias instalaciones bancarias" antes de este procedimiento. Se debe seleccionar la empresa de demostración USMF para ejecutar este procedimiento correctamente.




## <a name="create-sales-order-for-export-letter-of-credit"></a>Crear un pedido de ventas para carta de crédito de exportación
1. Vaya a Clientes > Pedidos > Todos los pedidos de venta.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Expanda o contraiga la sección General.
7. En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.
    * Permite seleccionar el sitio en el que se mantiene en existencias el artículo que se va a emitir.  
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.
    * Permite seleccionar el Almacén en el que se mantiene en existencias el artículo que se va a emitir.  
10. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Nota: Se debe seleccionar el campo Tipo de documento bancario con el valor Crédito documentario.  
11. En el campo Tipo de documento bancario, seleccione "Crédito documentario".
12. Expanda o contraiga la sección Entrega.
    * Seleccione Control de fecha de entrega = Ninguno.  
13. En el campo Fecha de recepción solicitada, especifique una fecha.
14. Haga clic en Aceptar
15. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione el artículo requerido para su emisión o venta.  
16. En la lista, busque y seleccione el registro deseado.
17. En la lista, haga clic en el vínculo de la fila seleccionada.
18. En el campo Precio unitario, escriba un número.
19. Expanda o contraiga la sección Detalles de línea.
20. Haga clic en la ficha Entrega.
21. En el campo Fecha de envío solicitada, especifique una fecha.
22. En el campo Fecha de envío confirmada, especifique una fecha.
23. En el panel de acciones, haga clic en Gestionar.
24. Haga clic en Crédito documentario.
25. En el campo Número de documento bancario, escriba un valor.
26. En el campo Fecha de vencimiento, especifique una fecha y una hora.
27. Expanda o contraiga la sección Detalles del banco.
28. En el campo Banco emisor, haga clic en el botón desplegable para abrir la búsqueda.
29. En la lista, haga clic en el vínculo de la fila seleccionada.
30. En el campo Banco avisador, haga clic en el botón desplegable para abrir la búsqueda.
31. En la lista, busque y seleccione el registro deseado.
32. En la lista, haga clic en el vínculo de la fila seleccionada.
33. Haga clic en Obtener envíos de pedido de ventas.
34. Haga clic en Emitir documento bancario.
35. Cierre la página.

## <a name="post-packing-slip"></a>Registrar albarán
1. En el panel de acciones, haga clic en Seleccionar y empaquetar.
2. Haga clic en Registrar albarán.
3. Expanda o contraiga la sección Parámetros.
4. En el campo Cantidad, seleccione "Todo".
5. Expanda o contraiga la sección Configuración.
6. En el campo Fecha de entrega, especifique una fecha.
7. Seleccione el Número de envío.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Haga clic en Aceptar
10. Haga clic en Aceptar

## <a name="post-sales-invoice"></a>Registrar factura de ventas
1. En el panel de acciones, haga clic en Factura.
2. Haga clic en Factura.
3. Expanda o contraiga la sección Visión general.
4. Seleccione el Número de envío.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Expanda o contraiga la sección Configuración.
7. En el campo Fecha de la factura, especifique una fecha.
8. Haga clic en Aceptar
9. Haga clic en Aceptar

## <a name="shipment-document-submitted-status"></a>Estado enviado de documento de envío
1. En el panel de acciones, haga clic en Gestionar.
2. Haga clic en Crédito documentario.
3. Expanda o contraiga la sección Líneas.
    * Nota: El campo "Documento enviado" se debe establecer en "Sí".  

## <a name="verify-export-letter-of-credit"></a>Comprobar Exportar crédito documentario
1. Vaya a Gestión de efectivo y bancos > Carta de crédito > Exportar carta de crédito e importar cobro.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Compruebe que la carta de crédito de exportación tienen un estado de envío de "Facturado".  

## <a name="customer-payment"></a>Cobros
1. Vaya a Clientes > Pagos > Diario de pagos.
2. Haga clic en Nuevo.
3. En la lista, marque la fila seleccionada.
4. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en Líneas.
7. En el campo Fecha, escriba una fecha.
8. En el campo Cuenta, especifique los valores deseados.
9. Haga clic en Liquidación.
10. Active la casilla en el encabezado de Totales.
    * Nota: Establezca el campo Mostrar en "Carta de crédito".  
11. En la lista, busque y seleccione el registro deseado.
12. Active o desactive la casilla Marcar.
13. Haga clic en Aceptar
14. Haga clic en la ficha Pago.
    * Comprobar los detalles del Número de documento bancario y Número de envío  
15. Haga clic en Registrar.

## <a name="verify-export-letter-of-credit-after-payment"></a>Comprobar Exportar crédito documentario después del pago
1. Vaya a Gestión de efectivo y bancos > Carta de crédito > Exportar carta de crédito e importar cobro.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Compruebe Estado de envío = Pago recibido e importe de saldo = 0,00.  



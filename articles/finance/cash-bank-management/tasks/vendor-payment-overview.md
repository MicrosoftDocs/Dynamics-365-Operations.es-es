---
title: Visión general de pagos de proveedor
description: Este procedimiento le mostrará los distintos métodos usados para crear pagos de proveedor, incluido cómo usar una propuesta de pago o especificar manualmente un pago único.
author: kweekley
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fcf22a3e9564f991b0cb5ebbd6a2282e3e749990
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179792"
---
# <a name="vendor-payment-overview"></a>Visión general de pagos de proveedor

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le mostrará los distintos métodos usados para crear pagos de proveedor, incluido cómo usar una propuesta de pago o especificar manualmente un pago único. Este procedimiento usa la empresa de demostración USMF.

1. Vaya a **Panel de exploración > Módulos > Proveedores > Pagos > Diario de pagos**.
2. Haga clic en **Nuevo**.
3. Seleccione el diario de pagos en el que guardar los pagos de proveedor. 
4. Seleccione el diario o especifíquelo manualmente.
5. Haga clic en **Líneas**.
6. En el **Panel de acción**, haga clic en **Propuesta de pago**.
7. Haga clic en **Crear propuesta de pago**. La propuesta de pago es una consulta que se utiliza para seleccionar facturas de pago. Puede editar la lista de facturas de pago antes de crear o de generar pagos de proveedor.
8. Seleccione las facturas para el pago por la fecha de vencimiento, descuento por pronto pago, o ambos. 
9. Especifique la fecha que comparar con la fecha de vencimiento o de descuento por pronto pago. 
10. Opcional: especifique una fecha de pago para todos los pagos. La fecha especificada aquí será la fecha de pago para todos los pagos creados, independientemente de la fecha de vencimiento o de descuento por pronto pago.  
11. Opcional: especifique una fecha de pago mínima posible como fecha de pago. La fecha de pago mínima será la fecha más temprana al crear pagos. Por ejemplo, si una factura tiene una fecha de vencimiento posterior a la fecha de pago mínima, la fecha de vencimiento se convertirá en la fecha de pago, en lugar de la fecha de pago mínima, como última fecha posible para pagar la factura.
12. Especifique las restricciones adicionales de la consulta bajo **Registros que incluir**. El filtro se usa a menudo para restringir las facturas seleccionadas para pago por grupo de proveedores o por método de pago. Por ejemplo, puede agregar un filtro para pagar solo facturas por cheque en este período de pago.
13. Especifique otras opciones predeterminadas de pago o de restricción de consulta. Los parámetros adicionales se pueden usar para definir la divisa de pago o para habilitar pagos centralizados para este período de pago.  
14. Haga clic en **Aceptar**. Después de hacer clic en **Aceptar**, aparecerán los resultados de la consulta. Si no desea obtener una vista previa de la lista de facturas seleccionadas para pagarse, puede volver a la ficha desplegable **Parámetros** y cambiar el ajuste **Crear pagos sin vista previa de factura** a "Sí".  
15. Elija el botón **Mostrar visión general de pagos** para ver los pagos que se crearán para el proveedor en la factura seleccionada.
16. Elija el botón **Ocultar visión general de pagos** para ocultar los pagos. 
17. Haga clic en **Crear pagos**. Antes de elegir **Crear pagos**, puede hacer clic con el botón derecho en la cuadrícula y exportar la lista de facturas a Excel. El botón **Crear pagos** creará los pagos de proveedor en el diario de pagos.  
18. Explore sus pagos y asegúrese de que se haya definido una forma de pago para todos los pagos. Si genera los pagos, como impresión de un cheque o creación de un pago electrónico, deberá definir la forma de pago. La forma de pago también incluirá de forma predeterminada la cuenta bancaria desde donde se hará el pago.  
19. Haga clic en **Nuevo** para crear un pago único. Se puede agregar un pago único a un diario de pagos en cualquier momento antes del registro. Para ello, se hace clic en el botón **Nuevo** y se agrega la información de pago manualmente, en lugar de usar la **Propuesta de pago**.  
20. Seleccione el proveedor al que se efectuará el pago.
21. Si hay una factura por pagar, seleccione **Liquidar transacciones** para seleccionar la factura que pagar. Si es un anticipo, este paso es opcional. Puede crear el pago sin seleccionar ninguna factura. 
22. Marque las facturas que se pagarán. Si usa **Liquidar transacciones** para seleccionar las facturas para el pago, el importe del pago se calcula automáticamente en función de qué facturas se marquen para el pago, y qué importe se especifique en **Importe para liquidar**.
23. Haga clic en **Aceptar**.
24. Si desea eliminar un pago, marque la fila correspondiente.
25. Haga clic **Eliminar**. Al eliminarse un pago solo se eliminará el pago. Las facturas marcadas para su pago seguirán estando disponibles para desembolsarse con otro pago.
26. Haga clic en **Sí**.
27. Elija **Generar pago** para imprimir cheques o para crear el archivo de pago electrónico.
28. Seleccione la forma de pago que desee generar. El diario de pagos puede contener pagos para cheques y para pagos electrónicos, pero solo se puede generar un único tipo de pago cada vez.
29. Seleccione la cuenta bancaria desde la que se van a generar los pagos.
30. Haga clic en **Aceptar**. Los pagos se generarán solo para los pagos que coincidan con el **Método de pago** y la **Cuenta bancaria** seleccionada.
31. Si va a generar **Cheques**, elija **Documento** para garantizar el destino correcto de impresión para los cheques.
32. Haga clic en **Aceptar**.
33. Haga clic en **Aceptar** para generar los pagos.
34. Haga clic en **Registrar** si se han aprobado y generado todos los pagos. 


---
title: "Conversión de divisas contables o de notificación"
description: 
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 78223
ms.assetid: 31c56f9a-9c64-40a2-90e3-1969a760614b
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4f5dae90c5fcaaa52a7087d7c20b2de343b7da0
ms.openlocfilehash: c738207f3088da151ec2317ce2b445f83278ec79
ms.contentlocale: es-es
ms.lasthandoff: 08/01/2017

---

# <a name="convert-accounting-or-reporting-currencies"></a>Conversión de divisas contables o de notificación

[!include[banner](../includes/banner.md)]


Una empresa que debe cambiar la divisa de contabilidad o la divisa de notificación tiene dos opciones. La primera opción es crear una nueva empresa y comenzar de cero. La segunda opción es ejecutar el proceso de conversión de la divisa de contabilidad y de notificación. Este es un proceso muy prolongado que cambia todas las transacciones en el sistema. También se requiere configuración adicional para poder ejecutar el proceso.

## <a name="preparing-the-legal-entity-for-currency-conversion"></a>Preparación de la entidad jurídica para una conversión de divisas
Antes de poder convertir la divisa de la entidad jurídica, debe invertir cualquier importe de la revalorización de divisa extranjera para las cuentas de cliente y proveedor, y cerrar los ejercicios anteriores. También debe preparar la base de datos para la conversión y después realizar los cambios necesarios a la cuenta de la entidad jurídica que está experimentando la conversión de divisas. Después de completar una conversión de divisas, debe completar algunos procedimientos adicionales. Debe conciliar diferencias de redondeo en importes convertidos, volver a calcular las estadísticas comerciales, registrar en el diario las transacciones contables, limitar el acceso a la herramienta de conversión y revalorizar los importes en divisa extranjera para las cuentas de cliente y proveedor.

## <a name="setting-up-accounts-for-automatic-transactions"></a>Configuración de cuentas para transacciones automáticas
Durante el proceso de conversión de divisas, las pérdidas o ganancias, o las diferencias de decimales, se registran en las cuentas definidas en la página **Cuentas para transacciones automáticas**. Las cuentas principales se deben asignar a los siguientes tipos de transacción para poder ejecutar el proceso de conversión:

-   Ganancia en la conversión de la divisa de contabilidad
-   Pérdida en la conversión de la divisa de contabilidad
-   Diferencia de decimales en la divisa de contabilidad
-   Diferencia de decimales en la divisa de notificación
-   Resultado de fin de año

## <a name="posting-rounding-differences-and-sum-recalculations"></a>Contabilización de diferencias de redondeo y nuevos cálculos de suma
La siguiente información explica dónde se pueden encontrar las diferencias en el redondeo:

-   Si los precios de los productos se han convertido a 0 (cero), se genera un informe que muestra el número de producto, el tipo de módulo, el precio antes de la conversión y la unidad.
-   Las diferencias de redondeo entre el impuesto sobre las ventas y la contabilidad general se registran en el diario general.
-   Los importes de revalorización de divisa extranjera se calculan y los importes de transacciones de cliente y proveedor se vuelven a calcular.
-   Los registros de liquidación de clientes y proveedores se crean para las diferencias de redondeo de cada la transacción del cliente y proveedor.
-   Las diferencias de redondeo para clientes y proveedores se registran en el diario general.
-   Los importes de coste liquidados y los importes de ajuste de coste en las transacciones de inventario cerradas se recalculan.
-   Las diferencias de redondeo en la gestión de inventarios se registran en el diario general.
-   El inventario disponible se recalcula.
-   Los importes totales de los diarios contables se recalculan.
-   Las hojas de cierre de contabilidad se recalculan.
-   Los saldos contables se recalculan.
-   Las diferencias de redondeo en la contabilidad general se registran en el diario general.
-   Las transacciones contables abiertas se recalculan.
-   Se calcula el importe final de los saldos contables.

Si convierte a una nueva divisa de contabilidad general y se produce un error durante el nuevo cálculo de los importes totales o el registro de las diferencias de redondeo, debe cerrar la página **Conversión de divisa de contabilidad del libro mayor**. A continuación se recalculan los importes totales y se registran las diferencias de redondeo.

## <a name="processing-the-currency-conversion"></a>Procesamiento de la conversión de divisa
Cuando inicia el proceso de conversión de divisas, todos los usuarios deben haber cerrado la sesión en el sistema. Debe definir el nuevo libro mayor o la divisa de notificación, asín como los tipos de cambio. Al hacer clic en **Aceptar**, se ejecuta el proceso y se actualizan todas las transacciones en el sistema. La conversión de divisas es un proceso excesivamente largo. Una vez completado, verá que la divisa de contabilidad o de notificación se actualiza en la página **Libro mayor**.

## <a name="completing-the-currency-conversion"></a>Finalización de conversión de divisas
Después de la conversión de divisas, debe generar todos los informes de conciliación de nuevo para comprobar que todos los importes convertidos son correctos.

-   Si la conversión de la divisa de contabilidad produce diferencias de redondeo, estas diferencias no se registran mediante el asiento en el que se ha producido la diferencia de redondeo. En su lugar, las diferencias se registran mediante el asiento especificado para los registros de conversión. Tras la conversión, todos los informes que se comprueban por asiento y fecha incluirán estas diferencias de redondeo. Este comportamiento es correcto y se puede ignorar.
-   Si los informes de conciliación de cliente y proveedor muestran un importe de diferencia en la línea de total y no existía un importe de diferencia antes de la conversión, este importe de diferencia se debe registrar. La cuenta es el extracto de cuenta para los clientes y los proveedores. La cuenta de contrapartida es la cuenta contable para las pérdidas por conversión o ganancias por conversión.

Una vez eliminados todos los diarios de transacción contable, puede registrar en el diario las transacciones contables. Haga clic en **Contabilidad general** &gt; **Periódico** &gt; **Diarios** &gt; **Creación de diarios**. Puede revalorizar los importes en divisa extranjera tras la conversión de divisa si se requiere revalorización. Los importes en divisa extranjera se revalorizan si selecciona **Estándar** en el campo **Método** para la revalorización.

Para obtener más información, consulte [Registre las entradas de diario anotadas](tasks/journalize-posted-journal-entries.md).



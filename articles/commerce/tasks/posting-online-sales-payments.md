---
title: Registro de ventas y pagos en línea
description: Este procedimiento le guía por la configuración y ejecución de un trabajo por lotes periódico para crear pedidos de ventas y pagos para transacciones de la tienda en línea.
author: psimolin
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 58af31464768e988bfa8727bcd836032d06b3a9dcfb416c3b9ed274af3285c79
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720913"
---
# <a name="posting-of-online-sales-and-payments"></a>Registro de ventas y pagos en línea

[!include [banner](../includes/banner.md)]

Este procedimiento le guía por la configuración y ejecución de un trabajo por lotes periódico para crear pedidos de ventas y pagos para transacciones de la tienda en línea.

El registro ventas y pagos en línea es un proceso de dos etapas.

- Extraer los datos de transacción de Commerce en línea en la sede.
- Sincronizar pedidos para crear pedidos de ventas en la sede.

La extracción de los datos de transacción en línea se puede hacer manualmente ejecutando el trabajo P o creando un trabajo por lotes periódico.

### <a name="manually-running-the-p-job"></a>Ejecutar manualmente el trabajo P

1. Vaya a Todos los espacios de trabajo > TI de Retail y Commerce.
2. Haga clic en Programación de distribución.
3. Seleccione P-0001.
4. Ajuste los grupos de la base de datos del canal, si es necesario.
5. Haga clic en Ejecutar ahora.
6. Haga clic en Sí.

### <a name="scheduling-a-recurring-p-job"></a>Programar un trabajo P periódico

1. Vaya a Todos los espacios de trabajo > TI de Retail y Commerce.
2. Haga clic en Programación de distribución.
3. Seleccione P-0001.
4. Haga clic en Crear trabajo por lotes.
5. Haga clic en Ejecutar en segundo plano.
5. Habilite Procesamiento por lotes.
6. Haga clic en Periodicidad.
7. Seleccione la opción No hay fecha final.
8. En el campo Recuento, introduzca el intervalo entre las ejecuciones en minutos. Normalmente, este sería 5-10.
9. Haga clic en Aceptar.
10. Haga clic en Aceptar.

Los pedidos se pueden sincronizar manualmente ejecutando el trabajo "Sincronizan pedidos" o creando un trabajo por lotes periódico.

### <a name="manually-running-order-synchronization"></a>Ejecutar manualmente la sincronización de pedidos 

Siga estos pasos para ejecutar manualmente el trabajo "sincronizar pedidos" una vez.

1. Vaya a Todos los espacios de trabajo > Operaciones financieras de tiendas.
2. Haga clic en Sincronizar pedidos.
3. En el campo Jerarquía organizativa, seleccione "Tiendas por región".
    * Seleccione una tienda en línea concreta o un nodo si desea crear el trabajo por lotes para un grupo de tiendas.  
    * Haga clic en la flecha para agregar su selección.  
4. Haga clic en la ficha Ejecutar en segundo plano.
5. Deshabilite Procesamiento por lotes
6. Haga clic en Periodicidad.
7. Seleccione la opción Finalizar tras
8. En el campo Finalizar tras, introduzca 1.
9. Haga clic en Aceptar.
10. Haga clic en Aceptar.

### <a name="scheduling-recurring-order-synchronization"></a>Programar sincronización de pedidos periódica

Este procedimiento le guía por la configuración y ejecución de un trabajo por lotes periódico para crear pedidos de ventas y pagos para transacciones de la tienda en línea. Este procedimiento usa la empresa USRT en los datos de demostración.

1. Vaya a Todos los espacios de trabajo > Operaciones financieras de tiendas.
2. Haga clic en Sincronizar pedidos.
3. En el campo Jerarquía organizativa, seleccione "Tiendas por región".
    * Seleccione una tienda en línea concreta o un nodo si desea crear el trabajo por lotes para un grupo de tiendas.  
    * Haga clic en la flecha para agregar su selección.  
4. Haga clic en la ficha Ejecutar en segundo plano.
5. Habilite Procesamiento por lotes
6. Haga clic en Periodicidad.
7. Seleccione la opción No hay fecha final.
8. En el campo Recuento, introduzca el intervalo entre las ejecuciones en minutos. Normalmente, este sería 2-20
9. Haga clic en Aceptar.
10. Haga clic en Aceptar.

## <a name="data-entities-involved-in-the-process"></a>Entidades de datos implicadas en el proceso

- RetailTransactionTable
- RetailTransactionAddressTrans
- RetailTransactionInfocodeTrans
- RetailTransactionTaxTrans
- RetailTransactionSalesTrans
- RetailTransactionTaxMeasure
- RetailTransactionDiscountTrans
- RetailTransactionTaxTransGTE
- RetailTransactionMarkupTrans
- RetailTransactionPaymentTrans
- RetailTransactionAttributeTrans


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
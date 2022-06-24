---
title: Configurar períodos de liquidación de impuestos
description: Este artículo explica cómo configurar períodos de liquidación de impuestos en Dynamics 365 Finance.
author: twheeloc
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f8514494b5d3534fc236def817df0d58fe80d70
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846694"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Configurar períodos de liquidación de impuestos

[!include [banner](../../includes/banner.md)]

Este artículo explica cómo configurar períodos de liquidación de impuestos. Los períodos de liquidación de impuestos contienen información sobre los intervalos de períodos para los que tienen que notificarse y pagarse los impuestos. Un proceso de liquidación se puede ejecutar para un período de liquidación de un intervalo de fechas concreto. Todos los códigos de impuestos asociados con el período de liquidación se liquidarán. Según la configuración de la autoridad fiscal relacionada, la deuda tributaria se registra en un proveedor o en una cuenta de contabilidad general.

Esta tarea usa la empresa de demostración USMF.

1. Vaya a **Impuestos > Impuestos indirectos > Impuestos > Períodos de liquidación de impuestos**.
2. Seleccione **Nuevo**.
3. En el campo **Período de liquidación**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. En el campo **Autoridad**, seleccione la autoridad fiscal que recibe los informes y los pagos creados para el período de liquidación.
6. En la lista, busque y seleccione el registro deseado.
7. En el campo **Condiciones de pago**, seleccione en el menú desplegable el registro que desee. La autoridad fiscal relacionada se puede establecer como proveedor y la liquidación de impuestos creará una factura de proveedor abierta. Las condiciones de pago definen la fecha de vencimiento de la factura de proveedor abierta.  
8. Seleccione un tipo para los intervalos del período de liquidación.
9. Especifique el número de unidades del intervalo de períodos por período. Por ejemplo, un trimestre tiene 3 meses.
10. Active o desactive la casilla **Usar procesamiento por lotes para la liquidación de impuestos**. El proceso de liquidación para el período de liquidación se puede procesar como un trabajo por lotes en segundo plano. Esto se recomienda para un gran número de transacciones de impuestos dentro de un intervalo de períodos.
11. Seleccione o borre la casilla **Evitar generar transacciones de impuestos de contrapartida**. De forma predeterminada, el sistema genera transacciones de impuestos de contrapartida durante el proceso de liquidación, lo que puede crear un problema de rendimiento si existe un gran número de transacciones de impuestos dentro de un intervalo de períodos. Seleccione esta casilla de verificación para evitar generar transacciones de impuestos de contrapartida.
12. Expanda la pestaña **Intervalos de período**.
13. Seleccione **Agregar**.
14. En el campo **Fecha inicial** en la nueva fila, especifique una fecha.
15. En el campo **Fecha final**, especifique una fecha.
16. Seleccione **Intervalo de período nuevo**. Una vez que se ha especificado el primer intervalo de períodos, los nuevos períodos se pueden crear automáticamente. Puede volverse y agregar nuevos intervalos de períodos en caso necesario.  
17. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

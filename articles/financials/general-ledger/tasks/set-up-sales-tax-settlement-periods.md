---
title: Configurar períodos de liquidación de impuestos
description: Los períodos de liquidación de impuestos contienen información sobre los intervalos de períodos para los que tienen que notificarse y pagarse los impuestos.
author: twheeloc
manager: AnnBe
ms.date: 10/15/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1087ed78e91b487ca7157bfdac1d72ae3f477875
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569595"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Configurar períodos de liquidación de impuestos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Los períodos de liquidación de impuestos contienen información sobre los intervalos de períodos para los que tienen que notificarse y pagarse los impuestos. Un proceso de liquidación se puede ejecutar para un período de liquidación de un intervalo de fechas concreto. Todos los códigos de impuestos asociados con el período de liquidación se liquidarán. Según la configuración de la autoridad fiscal relacionada, la deuda tributaria se registra en un proveedor o en una cuenta de contabilidad general.



Esta tarea usa la empresa de demostración USMF.



1. Vaya a Impuestos > Impuestos indirectos > Impuestos > Períodos de liquidación de impuestos.
2. Haga clic en Nuevo.
3. En el campo Período de liquidación, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Autoridad, seleccione la autoridad fiscal que recibe los informes y los pagos creados para el período de liquidación.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo Condiciones de pago, haga clic en el botón desplegable para abrir la búsqueda.
    * La autoridad fiscal relacionada se puede establecer como proveedor y la liquidación de impuestos creará una factura de proveedor abierta. Las condiciones de pago definen la fecha de vencimiento de la factura de proveedor abierta.  
9. En la lista, busque y seleccione el registro deseado.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. Seleccione un tipo para los intervalos del período de liquidación.
12. Especifique el número de unidades del intervalo de períodos por período. Por ejemplo, un trimestre tiene 3 meses.
13. Active o desactive la casilla Usar procesamiento por lotes para la liquidación de impuestos.
    * El proceso de liquidación para el período de liquidación se puede procesar como un trabajo por lotes en segundo plano. Esto se recomienda para un gran número de transacciones de impuestos dentro de un intervalo de períodos.  
14. Seleccione o borre la casilla Evitar generar transacciones de impuestos de contrapartida.
    * De forma predeterminada, el sistema genera transacciones de impuestos de contrapartida durante el proceso de liquidación, lo que puede crear un problema de rendimiento si existe un gran número de transacciones de impuestos dentro de un intervalo de períodos. Seleccione esta casilla de verificación para evitar generar transacciones de impuestos de contrapartida.
15. Expanda la ficha Intervalos de período.
16. Haga clic en Agregar.
17. En la lista, marque la fila seleccionada.
18. En el campo Fecha inicial, escriba una fecha.
19. Especifique una fecha en el campo Fecha final.
20. Haga clic en Intervalo de período nuevo.
    * Una vez que se ha especificado el primer intervalo de períodos, los nuevos períodos se pueden crear automáticamente. Puede volverse y agregar nuevos intervalos de períodos en caso necesario.  
21. Cierre la página.


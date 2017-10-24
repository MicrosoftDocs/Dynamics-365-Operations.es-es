--- 
title: "Configurar períodos de liquidación de impuestos"
description: "Los períodos de liquidación de impuestos contienen información sobre los intervalos de períodos para los que tienen que notificarse y pagarse los impuestos."
author: twheeloc
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
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: ab7d3a00a327f42a9f70c954d9b64a360a7f9163
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-sales-tax-settlement-periods"></a>Configurar períodos de liquidación de impuestos

[!include[task guide banner](../../includes/task-guide-banner.md)]

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
14. Expanda la ficha Intervalos de período.
15. Haga clic en Agregar.
16. En la lista, marque la fila seleccionada.
17. En el campo Fecha inicial, escriba una fecha.
18. Especifique una fecha en el campo Fecha final.
19. Haga clic en Intervalo de período nuevo.
    * Una vez que se ha especificado el primer intervalo de períodos, los nuevos períodos se pueden crear automáticamente. Puede volverse y agregar nuevos intervalos de períodos en caso necesario.  
20. Cierre la página.



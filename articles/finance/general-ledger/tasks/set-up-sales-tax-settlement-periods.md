---
title: Configurar períodos de liquidación de impuestos
description: Este tema explica cómo configurar períodos de liquidación de impuestos en Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5972c44261a6ebd49df0fcbcef9a8c60aaa487e2
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144729"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Configurar períodos de liquidación de impuestos

[!include [banner](../../includes/banner.md)]

Este tema explica cómo configurar períodos de liquidación de impuestos. Los períodos de liquidación de impuestos contienen información sobre los intervalos de períodos para los que tienen que notificarse y pagarse los impuestos. Un proceso de liquidación se puede ejecutar para un período de liquidación de un intervalo de fechas concreto. Todos los códigos de impuestos asociados con el período de liquidación se liquidarán. Según la configuración de la autoridad fiscal relacionada, la deuda tributaria se registra en un proveedor o en una cuenta de contabilidad general.

Esta tarea usa la empresa de demostración USMF.

1. En el panel de navegación, vaya a **Módulos > Impuestos > Impuestos indirectos > Impuestos > Períodos de liquidación de impuestos**.
2. Seleccione **Nuevo**.
3. En el campo **Período de liquidación**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. En el campo **Autoridad**, seleccione la autoridad fiscal que recibe los informes y los pagos creados para el período de liquidación.
6. En la lista, busque y seleccione el registro deseado.
7. En el campo **Condiciones de pago**, seleccione en el menú desplegable el registro que desee. La autoridad fiscal relacionada se puede establecer como proveedor y la liquidación de impuestos creará una factura de proveedor abierta. Las condiciones de pago definen la fecha de vencimiento de la factura de proveedor abierta.  
8. Seleccione un tipo para los intervalos del período de liquidación.
9. Especifique el número de unidades del intervalo de períodos por período. Por ejemplo, un trimestre tiene 3 meses.
10. Active o desactive la casilla **Usar procesamiento por lotes para la liquidación de impuestos**. El proceso de liquidación para el período de liquidación se puede procesar como un trabajo por lotes en segundo plano. Esto se recomienda para un gran número de transacciones de impuestos dentro de un intervalo de períodos.  
    > [!NOTE]
    > No se admite actualmente en España, Japón y Países Bajos.
11. Seleccione o borre la casilla **Evitar generar transacciones de impuestos de contrapartida**. De forma predeterminada, el sistema genera transacciones de impuestos de contrapartida durante el proceso de liquidación, lo que puede crear un problema de rendimiento si existe un gran número de transacciones de impuestos dentro de un intervalo de períodos. Seleccione esta casilla de verificación para evitar generar transacciones de impuestos de contrapartida.
12. Expanda la pestaña **Intervalos de período**.
13. Seleccione **Agregar**.
14. En el campo **Fecha inicial** en la nueva fila, especifique una fecha.
15. En el campo **Fecha final**, especifique una fecha.
16. Seleccione **Intervalo de período nuevo**. Una vez que se ha especificado el primer intervalo de períodos, los nuevos períodos se pueden crear automáticamente. Puede volverse y agregar nuevos intervalos de períodos en caso necesario.  
17. Cierre la página.


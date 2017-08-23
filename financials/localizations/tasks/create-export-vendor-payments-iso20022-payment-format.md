--- 
title: "Creación y exportación de pagos de proveedor mediante el formato de pago de ISO20022"
description: "Este procedimiento muestra cómo crear líneas de pago en el diario de pago de proveedor y generar un archivo de pago de proveedor utilizando el ejemplo ISO2022 Transferencia de crédito."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 16c2af862a73047a2e6ebdc056275392fa8a0d93
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Creación y exportación de pagos de proveedor mediante el formato de pago de ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear líneas de pago en el diario de pago de proveedor y generar un archivo de pago de proveedor utilizando el ejemplo ISO2022 Transferencia de crédito. 

La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.

Este es el quinto procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos. Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="create-payment-lines"></a>Creación de líneas de pago
1. Vaya a Proveedores > Pagos > Diario de pagos.
2. Haga clic en Nuevo.
3. En la lista, marque la fila seleccionada.
4. En el campo Nombre, especifique o seleccione un valor.
5. Haga clic en Líneas.
6. Haga clic en Propuesta de pago.
7. Haga clic en Crear propuesta de pago.
8. Expanda la sección Registros que incluir.
9. Haga clic en Filtro.
10. En la lista, seleccione la fila para la tabla Proveedores y el campo Cuenta de proveedor.
11. En el campo Criterios, especifique o seleccione un valor.
    * Puede aplicar cualquier criterio para seleccionar transacciones de proveedor para pagar, por ejemplo, use DE-001 como cuenta de proveedor.  
12. Haga clic en Aceptar
13. Haga clic en Aceptar
14. Haga clic en Crear pagos.

## <a name="generate-an-iso20022-payment-file"></a>Generación de un archivo de pago ISO20022



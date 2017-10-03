--- 
title: "Introducir datos de factura en el sistema de proveedores mediante un diario de aprobación"
description: "Esta guía de la tarea le mostrará cómo usar el registro de facturas para crear facturas y, después, utilizar el diario de aprobación para actualizar las cuentas de gastos."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d7cf810f1d8eabb9989fdd858585afcdf2e9574b
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>Introducir datos de factura en el sistema de proveedores mediante un diario de aprobación

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta guía de la tarea le mostrará cómo usar el registro de facturas para crear facturas y, después, utilizar el diario de aprobación para actualizar las cuentas de gastos.


## <a name="create-and-post-and-invoice"></a>Crear y registrar una factura
1. Vaya a Proveedores > Facturas > Registro de facturas.
2. Haga clic en Nuevo.
3. Seleccione el nombre del registro de facturas que desee usar.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Haga clic en las líneas para abrir el registro y especificar las líneas de gastos.
6. Seleccione un proveedor. Por ejemplo, escriba o seleccione US-104
7. En el campo Factura, escriba un valor.
8. En el campo Descripción, escriba un valor.
9. En el campo Crédito, escriba un número.
10. En el campo Aprobado por, haga clic en el botón desplegable para abrir la búsqueda.
11. Resalte un aprobador y haga clic en Seleccionar para seleccionar el aprobador.
12. Haga clic en Registrar.
13. Cierre la página.
14. Cierre la página.

## <a name="approve-an-invoice"></a>Aprobar una factura
1. Vaya a Proveedores > Facturas > Aprobación de facturas.
2. Haga clic en Nuevo.
3. Seleccione el nombre del diario de aprobación de facturas que desee usar.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Haga clic en las líneas para mostrar una página donde podrá seleccionar las facturas que desea aprobar.
6. Seleccione Buscar asientos para mostrar todas las facturas que están listas para su aprobación.
7. Marque la factura que ha creado.
8. Haga clic en Seleccionar.
    * Los asientos que seleccionó arriba se mueven en esta lista después de que los seleccione.  
9. Haga clic en Aceptar
10. Haga clic en el campo del número de cuenta para agregar una cuenta de gastos en la factura.
11. Especifique un número de cuenta y salga del campo con el tabulador. Por ejemplo, escriba 600120.
12. Haga clic en Registrar.
13. Haga clic en el asiento para ver las entradas que se han registrado.
    * La cuenta de factura pendiente de aprobación se anula y se reemplaza con la cuenta de gastos real.  



--- 
title: Introducir datos de factura en el sistema de proveedores mediante un grupo de facturas
description: "Esta guía de la tarea le mostrará cómo usar el registro de facturas para crear facturas."
author: abruer
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
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 08f66db0f62d5d985177b1d4ec0161df0b9961b3
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Introducir datos de factura en el sistema de proveedores mediante un grupo de facturas

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta guía de la tarea le mostrará cómo usar el registro de facturas para crear facturas.  A continuación use el grupo de facturas para que coincida con la factura de un pedido de compra y para finalizar el gasto en la página de la factura de proveedor.


## <a name="create-a-purchase-order"></a>Crear un pedido de compra
1. Vaya a Proveedores > Pedidos de compra > Pedidos de compra.
2. Haga clic en Nuevo para crear un pedido de compra.
3. En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.
4. Seleccionar el proveedor en la lista. Por ejemplo, el proveedor 1001.
5. Haga clic en Aceptar
6. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
7. Busque el número de artículo de servicios en la lista. Por ejemplo, seleccione S0001.
8. Haga clic en el número de artículo y selecciónelo.
    * El importe neto es 75,00.  Este es el importe que se espera en la factura.  
9. En el panel de acciones, haga clic en Compra.
10. Haga clic en Confirmar.

## <a name="create-and-post-and-invoice"></a>Crear y registrar una factura
1. Vaya a Proveedores > Facturas > Registro de facturas.
2. Haga clic en Nuevo.
3. Abra la búsqueda para seleccionar el nombre del registro de facturas que desea usar.
4. Seleccione el nombre del registro de facturas que desee usar.
5. Haga clic en las líneas para abrir el registro y especificar las líneas de gastos.
6. En la búsqueda, seleccione un proveedor. Por ejemplo, haga clic en el proveedor 1001.
7. En el campo Factura, especifique el número de factura.
8. En el campo Descripción, escriba un valor.
9. En el campo Crédito, escriba un número.
10. En el campo Pedido de compra, haga clic en el botón desplegable para abrir la búsqueda.
11. Seleccione el pedido de compra que ha creado anteriormente.
12. En el campo Aprobado por, haga clic en el botón desplegable para abrir la búsqueda.
13. Resalte un aprobador y haga clic en Seleccionar para seleccionar el aprobador.
14. Haga clic en Registrar.
15. Cierre el formulario.
16. Cierre el formulario.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Abrir una factura del grupo y conciliarla con un pedido de compra para completar el proceso de la factura
1. Vaya a Proveedores > Facturas > Grupo de facturas.
2. Haga clic en Pedido de compra para crear una factura de proveedor a partir de la factura del grupo.
3. Seleccione la factura que desea revisar.
4. Haga clic en Actualizar estado de conciliación para completar la conciliación.
5. En el panel de acciones, haga clic en Opciones.
6. Haga clic en Cambiar vista.
7. Haga clic en Vista de cuadrícula.
8. Haga clic en Registrar.
9. Cierre el formulario.
10. Vaya a Proveedores > Proveedores > Proveedores.
11. Seleccione el proveedor que estaba en el pedido de compra. Por ejemplo, seleccione el proveedor 1001.
12. En la lista, haga clic en el vínculo de la fila seleccionada.
13. En el panel de acciones, haga clic en Proveedor.
14. Haga clic en Transacciones.
15. Seleccione la factura que ha creado.
    * La acumulación de registro de facturas se ha invertido y registrado en la cuenta de gastos apropiada.  



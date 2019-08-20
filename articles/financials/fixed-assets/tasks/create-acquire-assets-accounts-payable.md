---
title: Crear y adquirir activos desde Proveedores
description: Esta guía de la tarea le guiará por la creación y la adquisición de un activo fijo con el proceso de compra.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2626877c907994d03cdae960c8501a858ca214bd
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840034"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Crear y adquirir activos desde Proveedores

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía de la tarea le guiará por la creación y la adquisición de un activo fijo con el proceso de compra.  Usa los roles de contable y responsable de proveedores y la empresa de prueba USMF.


## <a name="set-fixed-assets-parameters"></a>Configurar los parámetros de activos fijos
1. Vaya a Activos fijos > Configuración > Parámetros de activos fijos.
2. Expanda o contraiga la sección Pedidos de compra.
3. Active la casilla Permite la adquisición de activos desde Compras.
4. Active la casilla Crear activo durante la recepción de producto o el registro de facturas.

## <a name="create-a-new-vendor-invoice"></a>Crear una nueva factura de proveedor
1. Vaya a Proveedores > Áreas de trabajo > Entrada de factura de proveedor.
2. Haga clic en Nueva factura de proveedor.
3. En el campo Cuenta de facturación, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Número, escriba un valor.
6. En el campo Fecha de registro, escriba una fecha.
7. Haga clic en Agregar línea.
8. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
    * Los artículos sin existencias o las categorías de compras se pueden usar para la adquisición del activo fijo.  
9. En la lista, haga clic en el vínculo de la fila seleccionada.
10. En el campo Cantidad, especifique un número.
    * Una línea de factura creará solo un activo fijo, independientemente de la cantidad.  El valor del campo de cantidad de factura se transferirá a la cantidad de activo fijo.  
11. En el campo Precio unitario, escriba un número.
12. Expanda o contraiga la sección Detalles de línea.
13. Haga clic en la ficha Activos fijos.
14. Active la casilla Crear un activo fijo nuevo.
15. En el campo Grupo de activos fijos, haga clic en el botón desplegable para abrir la búsqueda.
16. En la lista, seleccione el grupo de activos fijos que se usará al crear el nuevo activo fijo.
17. En la lista, haga clic en el vínculo de la fila seleccionada.
18. Haga clic en Registrar.
    * El activo fijo se creará y adquirirá cuando se registre la factura.  


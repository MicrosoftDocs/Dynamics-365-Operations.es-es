---
title: Crear un pedido de compra regido por el presupuesto
description: Use este procedimiento para crear un pedido de compra que se compruebe para ver si hay presupuesto disponible.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 319eb0070a3677035e2a5d89744e80cd38c08d8e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980516"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Crear un pedido de compra regido por el presupuesto

[!include [banner](../../includes/banner.md)]

Use este procedimiento para crear un pedido de compra que se compruebe para ver si hay presupuesto disponible. Este registro usa la empresa USMF con los datos para demostración.


## <a name="review-the-budget-control-configuration"></a>Revisar la configuración de control presupuestario
1. Vaya a Gestión presupuestaria > Configuración > Control presupuestario > Configuración de control presupuestario.
2. Haga clic en la pestaña Fondos presupuestarios disponibles.
3. Haga clic en la pestaña Documentos y diarios.
4. Haga clic en la pestaña Definir reglas de control presupuestario.
5. Haga clic en la pestaña Definir grupos presupuestarios.
6. Cierre la página.

## <a name="create-the-purchase-order-header"></a>Crear el encabezado del pedido de compra
1. Vaya a Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra.
2. Haga clic en Nuevo.
3. En el campo Cuenta de proveedor, especifique o seleccione un valor.
4. Expanda la sección General.
5. En el campo de Fecha de contabilidad, defina la fecha a "2016-01-01".
6. Haga clic en Aceptar

## <a name="add-a-purchase-order-line"></a>Agregar una línea de pedido de compra
1. En el campo Categoría de compras, especifique o seleccione un valor.
2. Establezca Cantidad en "2".
3. En el campo Unidad, especifique o seleccione un valor.
4. Establezca el precio unitario en "10000".
5. Haga clic en Operaciones financieras.
6. Haga clic en Distribuir importes.
7. En el campo Cuenta contable, especifique el valor "601300-001-023--".
8. Cierre la página.

## <a name="perform-budget-checking"></a>Realizar comprobación presupuestaria
1. Haga clic en Operaciones financieras.
2. Haga clic en Realizar comprobación presupuestaria.
3. Haga clic en Operaciones financieras.
4. Haga clic en Errores o advertencias de la comprobación presupuestaria.
5. Haga clic en Cerrar.


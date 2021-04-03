---
title: Registro de artículos habilitados para almacenamiento básico mediante un diario de recepción de artículos
description: Este procedimiento muestra cómo registrar artículos mediante el diario de recepción de artículos cuando se usa el "almacenamiento básico" en el módulo de gestión del inventario.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3edf84135e675b6259972327f80c9b6a91821139
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254176"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a>Registro de artículos habilitados para almacenamiento básico mediante un diario de recepción de artículos

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo registrar artículos mediante el diario de recepción de artículos cuando se usa el "almacenamiento básico" en el módulo de gestión del inventario. Esto lo realiza normalmente un empleado de recepción. Puede ejecutar este procedimiento en la empresa de datos de demostración USMF con los valores de ejemplo que se muestran.  Si no está utilizando USMF, necesita tener un pedido de compra confirmado con una línea de pedido de compra abierta antes de comenzar esta guía. El artículo de la línea debe mantenerse en existencias. El artículo debe estar asociado con un grupo de dimensiones de almacenamiento, donde estén activos el sitio y el almacén.


## <a name="create-item-arrival-journal-header"></a>Creación del encabezado del diario de recepción de artículos
1. Vaya a Gestión del inventario > Movimientos de diario > Recepción de artículos > Recepción de artículos.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
    * Si está usando USMF, puede escribir WHS. Si está usando otros datos, el diario cuyo nombre elija tiene que tener las siguientes propiedades: Comprobar ubicación de picking debe estar definida en No, y Gestión de cuarentena debe estar definida en No.  
4. En el campo Albarán, escriba un valor.
    * Esta es el identificador del albarán emitido por el proveedor. Agregue un número único.  
5. En el campo Número, seleccione el pedido de compra.
6. Haga clic en Aceptar

## <a name="add-lines-to-item-arrival-journal"></a>Adición de líneas al diario de recepción de artículos
1. Haga clic en Funciones.
2. Haga clic en Crear líneas.
    * Las líneas se pueden especificar manualmente en este diario o se pueden crear automáticamente. Aquí se le mostrará cómo crearlas automáticamente.  
3. Active o desactive la casilla Inicializar cantidad.
    * Esto inicializará la cantidad en las líneas de diario con la cantidad no registrada desde línea de pedido de compra.  
4. Haga clic en Aceptar

## <a name="post-the-journal"></a>Registrar el diario
1. Haga clic en Registrar.
2. Haga clic en Aceptar

## <a name="generate-the-product-receipt"></a>Generación de la recepción del producto
1. Haga clic en Funciones.
2. Haga clic en Recepción de producto.
3. Haga clic en Aceptar



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
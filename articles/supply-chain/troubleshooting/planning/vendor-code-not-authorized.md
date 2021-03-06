---
title: El código de proveedor no está autorizado para un producto y una fecha específicos
description: Cuando intenta confirmar un pedido planificado o agregar una línea a un pedido de compra, recibe un mensaje de error que indica que el código de proveedor no está autorizado para un producto y una fecha.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294176"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a>El código de proveedor no está autorizado para un producto y una fecha específicos

Código de error: SYP4881415

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un pedido planificado o agregar una línea a un pedido de compra, recibe el siguiente mensaje de error:

> El código de proveedor %1 no está autorizado para %2 en %3.

## <a name="cause"></a>Causa

El error se produce porque el campo **Método de verificación de proveedor aprobado** está configurado en *Solo advertencia* o *No permitido* para el producto especificado, y el proveedor no está autorizado actualmente para suministrar ese producto.

## <a name="resolution"></a>Resolución

Para solucionar este problema, desactive la verificación del proveedor para el producto relevante o apruebe al proveedor.

Para deshabilitar la verificación de proveedor de un producto, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Abrir el producto relevante.
1. En la ficha desplegable **Compra**, establezca el campo **Método de verificación de proveedor aprobado** en un valor que no sea *Solo advertencia* o *No permitido*.

Para aprobar un proveedor de un producto, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Abrir el artículo relevante.
1. En el panel de acciones, en la ficha **Compra**, en el grupo **Proveedor aprobado**, haga clic en **Configurar**.
1. En la página de lista **Proveedor aprobado**, agregue una fila a la cuadrícula y después establezca los siguientes valores.

    - **Proveedor** - Seleccione el proveedor para aprobar el producto actual.
    - **Fecha efectiva** - Seleccione la primera fecha para la que se aprueba el proveedor.
    - **Fecha de vencimiento** - Seleccione la primera fecha para la que se aprueba el proveedor.

Para más información, consute [Aprobar proveedores para productos específicos](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).

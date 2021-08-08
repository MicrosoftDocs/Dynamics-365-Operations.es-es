---
title: Devolver productos controlados por número de serie en POS
description: Este tema describe las capacidades para validar artículos serializados como parte del proceso de devolución en la aplicación del punto de venta (PDV) de Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e53c8ceb91a007775fa74f0c9598a65745f01cec
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638106"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a>Devolver productos controlados por número de serie en PDV

[!include [banner](includes/banner.md)]

Este tema describe las capacidades para validar artículos serializados como parte del proceso de devolución en la aplicación del punto de venta (PDV) de Microsoft Dynamics 365 Commerce.

> [!NOTE]
> En el lanzamiento de Commerce versión 10.0.20 y posteriores, está disponible una nueva característica que se llama **Experiencia unificada de procesamiento de devoluciones en PDV**. Para utilizar la validación del número de serie durante el procesamiento de pedidos de devolución en PDV, debe activar esta función. Para obtener información sobre otras capacidades que ofrece esta función cuando está activada, consulte [Crear devoluciones en PDV)](POS-returns.md).
>
> Una vez activada la función, no se puede desactivar.

## <a name="options-for-validating-serialized-returns"></a>Opciones para validar devoluciones serializadas

Cuando la característica **Experiencia unificada de procesamiento de devoluciones en PDV** está activada, las organizaciones pueden realizar una validación en las devoluciones de artículos controlados por número de serie a través de PDV. Esta capacidad puede advertir a los usuarios si el número de serie que se devuelve difiere del número de serie original que se vendió. En la versión de Commerce 10.0.20 y posteriores, el mensaje que reciben los usuarios es solo un mensaje de advertencia. Los usuarios pueden continuar procesando una devolución con un número de serie que difiera del número de serie que se vendió originalmente.

Para configurar la validación del número de serie para una organización después de activar la función **Experiencia unificada de procesamiento de devoluciones en PDV**, vaya a **Retail y Commerce \> Configuración de la sede central \> Parámetros \> Parámetros de Commerce** en la sede central de Commerce. En la pestaña **Inventario**, en la ficha desplegable **Operaciones de inventario de la tienda**, establezca la opción **Habilitar la validación de los números de serie en las devoluciones de PDV** en **Sí**.

## <a name="process-returns-for-serialized-items-in-pos"></a>Procesar devoluciones de artículos serializados en PDV

Si la opción **Habilitar la validación de los números de serie en las devoluciones de PDV** se ha establecido en **Sí**, cuando un artículo controlado por número de serie se devuelve a través de PDV, el usuario puede ingresar el número de serie para la línea de devolución en el panel de detalles en la página **Productos que se pueden devolver**. Si el número de serie que se ingresa no coincide con el número de serie original que se vendió para la transacción de venta, el usuario recibe un mensaje de advertencia. Sin embargo, la aplicación no impide que el usuario continúe procesando la devolución.

> [!NOTE]
> Actualmente, PDV admite la validación de números de serie solo en líneas de devolución donde la cantidad original pedida no es más de uno. Si la línea de pedido de venta original se creó en un canal que no es PDV, y si la cantidad solicitada para el artículo serializado en una línea de venta determinada es más de uno, el artículo no se puede devolver correctamente a través de PDV.

## <a name="additional-resources"></a>Recursos adicionales

[Crear devoluciones en PDV.](POS-returns.md)

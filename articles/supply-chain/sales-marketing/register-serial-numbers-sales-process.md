---
title: Trabajo con artículos serializados
description: Este artículo explica cómo puede registrar los números de serie en albaranes o facturas durante el proceso de ventas. Esta funcionalidad es útil si una empresa desea capturar los números de serie para propósitos de servicio y de garantía, pero no tiene que mantener los números de serie en el inventario desde recepción a emisión.
author: Henrikan
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResTrackingDimensionGroup, InventTrackingRegisterTrans, SalesEditLines, SalesTable, InventSerial
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28931
ms.assetid: 5d39630f-607e-492b-8c1e-790ca53effa0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b89e9ab547d13e68ead88d76f9922d14fde4beb3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901861"
---
# <a name="working-with-serialized-items"></a>Trabajo con artículos serializados

[!include [banner](../includes/banner.md)]

Este artículo explica cómo puede registrar los números de serie en albaranes o facturas durante el proceso de ventas. Esta funcionalidad es útil si una empresa desea capturar los números de serie para propósitos de servicio y de garantía, pero no tiene que mantener los números de serie en el inventario desde recepción a emisión.

Muchas empresas solo desean capturar los números de serie para propósitos de servicio y de garantía, y no tienen que mantener los números de serie en el inventario desde recepción a emisión. En estos casos puede registrar los números de serie en los albaranes o facturas al vender productos. Si más adelante los productos se devuelven, puede realizar un seguimiento de cada producto en una factura para determinar si vendió el producto, y si las obligaciones de servicio o de garantía son válidas.

Debe habilitar los números de serie del proceso de ventas seleccionando la opción **Activo en el proceso de ventas** en la página **Grupos de dimensiones de seguimiento**. Los eventos siguientes aparecerán en Supply Chain Management:
-   En la ficha desplegable **Números de serie**, la opción **Control de números de serie** está seleccionada. Si se selecciona esta opción, debe registrar un número de serie para cada artículo en el albarán o en la factura.
-   Todas las selecciones del grupo de dimensiones de seguimiento para los números de serie se anulan, excepto la opción **Emisión en blanco permitida**. Puede seleccionar la opción **Emisión en blanco permitida** para anular el control del número de serie y permitir que los productos se empaqueten o facturen sin registrar números de serie.

## <a name="when-do-i-register-serial-numbers-during-the-sales-process"></a>¿Cuándo debo registrar números de serie durante el proceso de ventas?
Puede registrar números de serie en el albarán para un pedido de ventas o en la factura. Cuando prepara una factura para un artículo serializado enviado junto con un albarán, puede seleccionar qué números de serie del albarán desea facturar. El número de números de serie registrados no debe superar la cantidad de artículos enviados. Si está creando una factura parcial, puede seleccionar menos artículos serializados de los que se registraron en el albarán. Al imprimir un albarán o una factura, los números de serie que se registraron se incluyen.

## <a name="can-i-enter-serial-numbers-by-scanning-them-or-do-i-have-to-type-them"></a>¿Se pueden especificar números de serie escaneándolos, o debo introducirlos?
Puede escanear o escribir los números de serie. Si se usa un escáner, el modo de escaneo determina si agregar o quitar los números de serie de la lista de números de serie de la factura o el albarán. Si desea escanear números de serie, por ejemplo, con un escáner de código de barras manual, configure el escáner para enviar un comando Entrar o un comando TABULADOR tras el número de serie. Este comando indicará el final de la secuencia de datos. De lo contrario, debe presionar Entrar o TABULADOR en el teclado después de escanear cada número de serie.

## <a name="if-i-enable-serial-numbers-for-the-sales-process-do-i-have-to-register-all-serial-numbers-for-all-items"></a>Si permito números de serie para el proceso de ventas, ¿necesito registrar todos los números de serie para todos los artículos?
La configuración del grupo de dimensiones de seguimiento que se asigna al producto determina si se deben registrar los números de serie para todos los artículos en un albarán o una factura. Si habilitan los números de serie para el proceso de ventas, la opción **Control de números de serie** se selecciona automáticamente. Debe entonces registrar un número de serie, o registrar un registro en blanco para un número ilegible, para cada artículo en el albarán o la factura. Si no desea requerir un número de serie para cada artículo, active la opción **Emisión en blanco permitida** en el grupo de dimensiones de seguimiento que se asigna al artículo. Puede registrar menos números de serie que la cantidad de artículos enviados. Si se registran más números de serie que la cantidad de artículos que se envían, no podrá registrar el albarán o la factura.

## <a name="can-i-register-serial-numbers-for-partial-invoices-and-partial-shipments"></a>¿Se pueden registrar números de serie para las facturas parciales y los envíos parciales?
Puede crear facturas y albaranes parciales para los pedidos de ventas y registrar solo los números de serie de los artículos que incluyen estas facturas y albaranes. Si desea crear una factura parcial y tiene más de un albarán para el pedido de ventas, puede incluir los números de serie de más de un albarán. Sin embargo, solo puede haber un albarán que no incluya todos los números de serie. Por ejemplo, si tiene tres albaranes y cada uno incluye dos artículos serializados, no puede crear una factura parcial para un artículo de cada albarán.

## <a name="what-do-i-do-when-a-serial-number-isnt-readable"></a>¿Qué hago cuando un número de serie no es legible?
Si un número de serie no se puede leer ni escanear, puede crear una línea en blanco para el artículo haciendo clic en **No se puede leer** en la página **Números de serie**. Si el número de serie queda disponible más adelante, puede actualizar la factura o el albarán. Para obtener más información, consulte la sección siguiente, "¿Puedo corregir o cambiar los números de serie que he registrado para un pedido de ventas?"

## <a name="can-i-correct-or-change-the-serial-numbers-that-i-have-registered-for-a-sales-order"></a>¿Puedo corregir o cambiar los números de serie que he registrado para un pedido de ventas?
Sí, podrá corregir números de serie cuando se cumplan las siguientes condiciones:
-   **Facturas**: puede cambiar los números de serie de los artículos que aún no ha facturado. El albarán se actualiza también. No obstante, si una línea de pedido de ventas se corrige registrando una cantidad negativa, no puede cambiar los números de serie de la línea de pedido de ventas.
-   **Albaranes**: no puede corregir parcialmente una línea del albarán que contenga artículos serializados. Debe invertir la cantidad completa de la línea. Si un albarán se ha cancelado o corregido, no es necesario registrar los números de serie invertidos de nuevo al crear un nuevo albarán para los mismos artículos serializados. Se usarán los números que se registraron.

## <a name="can-i-view-the-serial-numbers-that-were-shipped-together-with-a-specific-packing-slip-or-that-were-included-on-an-invoice"></a>¿Puedo visualizar los números de serie que se enviaron junto con un albarán específico, o se incluyeron en una factura?
Sí, puede ejecutar una consulta en la línea del diario de albaranes o la línea del diario de facturas para ver una lista de todos los números de serie que estaban incluidos en el documento.

## <a name="can-i-view-the-serialized-items-that-i-have-on-hand"></a>¿Puedo visualizar los artículos serializados que tengo disponibles?
No, no puede ver los artículos serializados que tiene disponibles porque los números de serie no se registran para los artículos hasta que los artículos no se han vendido.

## <a name="can-i-register-serial-numbers-for-catchweight-items"></a>¿Puedo registrar números de serie de los artículos con peso capturado?
No, no puede registrar números de serie de los artículos con peso capturado durante el proceso de ventas. Además, si un producto se configura como artículo con peso capturado, no puede asignar el producto a un grupo de dimensiones de seguimiento configurado para usar números de serie solo durante el proceso de ventas.

## <a name="can-i-register-serial-numbers-at-the-retail-pos"></a>¿Puedo registrar números de serie en el PDV minorista?

Sí, el punto de venta minorista (PDV) solicitará al usuario que especifique un número de serie cuando venda un artículo asignado a un grupo de dimensiones de seguimiento configurado para usar números de serie solo durante el proceso de ventas.

## <a name="what-security-roles-are-required-in-order-to-register-serial-numbers-during-the-sales-process"></a>¿Qué roles de seguridad se requieren para registrar números de serie durante el proceso de ventas?
Esta funcionalidad está disponible para todos los roles que pueden mantener albaranes y facturas de ventas. Los siguientes controles permiten a los trabajadores corregir números de serie y registrar entradas en blanco para números de serie que no se pueden leer o escanear:
-   Mantener correcciones de números de serie
-   Mantener registro de números de serie ilegibles







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
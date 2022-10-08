---
title: Crear pedido de repetición de compra
description: Este artículo le muestra cómo crear un pedido de compra de repetición copiando líneas de un documento de pedido de compra anterior en un pedido de compra nuevo o en un pedido de compra existente.
author: GalynaFedorova
ms.date: 09/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 335461d60fa0bc92e9711806c6e42643a3f75d02
ms.sourcegitcommit: 073604c07116e0a87f78ab2c76cb89ae83ebba3c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9608121"
---
# <a name="create-a-repeat-purchase-order"></a>Crear pedido de repetición de compra

[!include [banner](../../includes/banner.md)]

Este artículo le muestra cómo crear un pedido de compra de repetición copiando líneas de un documento de pedido de compra anterior en un pedido de compra nuevo o en un pedido de compra existente. Hay dos métodos para crear pedidos de repetición. Puede utilizar las acciones disponibles en el nivel del documento en el Panel de acciones o utilizar las acciones de detalles de línea. Las acciones del nivel del documento están pensadas para crear un nuevo pedido de compra agregando líneas e información de encabezado de otro pedido, mientras que la acción de detalles de línea es principalmente para agregar líneas a una orden existente. El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF. Esta tarea la realizaría normalmente un agente de compras.

## <a name="create-a-new-repeat-purchase-order"></a>Crear un nuevo pedido de compra de repetición

1. En el panel de navegación, vaya a **Módulos \> Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**. En primer lugar intentaremos la opción de copiar la información en un nuevo pedido.  
1. Seleccione **Nuevo**.
1. En el campo **Cuenta de proveedor**, escriba `US-101`.
1. Seleccione **Aceptar**.
1. En el panel Acciones, abra la pestaña **Pedido de compra** y, desde el grupo **Copiar**, seleccione **De todos**. El cuadro de diálogo **Copiar de otros documentos** se abre. Desde aquí puede copiar desde los pedidos existentes a su pedido. Hay diversas opciones para cómo se copian las líneas y diferentes tipos de documentos desde los que puede copiar. Miraremos las opciones para cómo se copian las líneas primero.
1. Expanda la ficha desplegable **Parámetros**.

    - El campo **Factor de cantidad** es útil si necesita utilizar una cantidad que sea diferente de la que se encuentra en el pedido desde el que está copiando. Por ejemplo, si desea pedir dos veces la cantidad que se encuentra en las líneas desde las que está copiando, escribirá “2" en este campo y, a continuación, el sistema agregaría líneas en las que se haya duplicado la cantidad original.  
    - El campo **Invertir el signo** también admite el cambio de la cantidad pedida al cambiar el signo de la cantidad para las líneas de pedido que se agregan. Esto puede ser útil si tiene que invertir una transacción, creando las líneas de pedido que niegan la transacción. Esta opción se selecciona automáticamente cuando se abre la página desde la acción **Crear nota de abono**.  
    - La opción **Copiar gastos** permite copiar gastos en su nuevo pedido del documento del que está copiando las líneas de pedido.  
    - La opción **Volver a calcular** el precio utiliza los precios y descuentos actuales en lugar de copiarlos del documento desde el que está copiando otra información.  
    - La opción **Copiar con exactitud** copia los valores de varios campos de las líneas y del encabezado del pedido. Si esta opción no está seleccionada, los valores predeterminados se utilizan para muchos de los campos relativos al proveedor, al igual que cuando se crea un nuevo pedido manualmente. Por ejemplo, si configura **Copiar con exactitud** en *Sí* y copia un pedido que anule la cuenta de la factura predeterminada para el proveedor, entonces esa misma cuenta de factura se copiará en el nuevo pedido. Si configura **Copiar con exactitud** en *No*, la cuenta de la factura predeterminada para el proveedor se usaría en su lugar en el nuevo pedido. Los valores para los siguientes campos se copian cuando **Copiar con exactitud** se establece en *Sí*:
        - Idioma
        - Condiciones de pago
        - Método de pago
        - Especificación del pago
        - Grupo de secuencias numéricas
        - Descuento por pronto pago
        - Porcentaje de descuento
        - Divisa
        - Condiciones de entrega
        - Modo de entrega
        - Dimensión
        - Grupo de impuestos
        - Anular impuestos
        - Los precios incluyen impuestos
        - Transporte
        - Puerto
        - Procedimiento de las estadísticas
        - Id. de plantilla
        - Nombre de entrega
        - Dirección postal
        - Referencia
        - Id. de la tabla de referencia
    - La opción **Eliminar las líneas** de compra elimina todas las líneas de pedido de compra que ya existen en el pedido de compra en el que está copiando, antes de aplicar las líneas nuevas. Utilice esta opción con precaución, ya que elimina todas las líneas existentes sin ninguna advertencia adicional.  
    - Si utiliza la opción **Copiar la cabecera de pedido**, usted no necesita crear manualmente la información de la cabecera en su nuevo pedido. Esta opción dará como resultado valores predeterminados que se utilizan para los campos asociados al proveedor. Si el documento desde el que está copiando tiene valores que no son predeterminados que desea copiar, use también la opción **Copiar con exactitud**.
    - Hay diferentes orígenes de documento desde los que puede copiar y cada uno de ellos tiene una sección independiente en esta página. Por ejemplo, la sección **Pedidos de compra** le permite copiar de pedidos de compra existentes.  

1. En la sección **Pedidos de compra**, seleccione las líneas que desea copiar en el portapapeles. Es posible seleccionar líneas de pedidos de compra adicionales de otros pedidos de compra y copiarlos también en el pedido. También es posible agregar líneas de otros tipos de documentos de compra. En los pasos siguientes pasos se revisan las diferentes opciones.  
1. Expanda la sección **Confirmación**. Aquí puede seleccionar confirmaciones de pedidos de compra desde la que copiar. Las confirmaciones de pedidos de compra se identifican por el id. de diario de compra asociado o el id. de pedido de compra.  
1. Expanda la sección **Recepciones de producto**. Aquí puede seleccionar diarios de recepciones de producto desde los que copiar. Los diarios de recepciones de producto se identifican por el asiento de recepción de producto o el id. de pedido de compra.
1. Expanda la sección **Facturas**. Aquí puede seleccionar facturas de proveedor desde las que copiar. Las facturas se identifican por el asiento de factura o el id. de pedido de compra.
1. Expanda la sección **Líneas o encabezados seleccionados que se copiarán**. Esta vista le muestra un resumen de todos los documentos y líneas que se han seleccionado para copiarlas en su pedido.
1. Seleccione **Aceptar**. Las líneas que ha seleccionado se han copiado en su nuevo pedido de compra.

## <a name="copy-lines-to-an-existing-purchase-order"></a>Copiar líneas en un pedido de compra existente  

En vez de copiar un pedido completo, es más habitual crear un nuevo pedido de compra y la información completa de la cabecera del pedido y, a continuación, copias líneas individuales de los pedidos existentes.  

1. Seleccione la línea **Pedido de compra**.
1. Seleccione **De todos**. La página que se abre es idéntica a la mostrada antes, pero se seleccionan diferentes opciones cuando se abre desde la vista de líneas de pedido. Revisemos los parámetros.
1. Expanda la sección **Parámetros**.

    - La opción **Eliminar las líneas de compra** no está seleccionada. Esto significa que puede copiar nuevas líneas en su pedido sin eliminar las líneas existentes.
    - No se selecciona tampoco la opción **Copiar la cabecera de pedido**, pues solo estamos agregando líneas adicionales al pedido.
    - Para este ejemplo, copiaremos líneas de un pedido de compra existente.

1. Seleccione la línea para la orden de pedido que desea. Observe que la línea de pedido única que se encuentra en este pedido de compra también está seleccionada.  
1. Seleccione **Aceptar**. Se ha agregado la línea de pedido adicional a su pedido de compra.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
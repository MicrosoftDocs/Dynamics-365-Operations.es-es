--- 
title: "Creación de pedido de repetición de compra"
description: "Este procedimiento le muestra cómo crear un pedido de compra de repetición copiando líneas de un documento de pedido de compra anterior en un pedido de compra nuevo o en un pedido de compra existente."
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 406a59ffdbca4e7a5de54b4cb283a9a46c977ed1
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-repeat-purchase-order"></a>Creación de pedido de repetición de compra

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo crear un pedido de compra de repetición copiando líneas de un documento de pedido de compra anterior en un pedido de compra nuevo o en un pedido de compra existente. Hay dos métodos para crear pedidos de repetición. Puede utilizar las acciones disponibles en el nivel del documento en el Panel de acciones o utilizar las acciones de detalles de línea. Las acciones del nivel del documento están pensadas principalmente para crear un nuevo pedido de compra agregando líneas e información de encabezado de otro pedido, mientras que la acción de detalles de línea es principalmente para agregar líneas a una orden existente. El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF. Esta tarea la realizaría normalmente un agente de compras.


## <a name="create-a-new-repeat-purchase-order"></a>Crear un nuevo pedido de compra de repetición
1. Vaya a Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra.
    * En primer lugar intentaremos la opción de copiar la información en un nuevo pedido.  
2. Haga clic en Nuevo.
3. En el campo Cuenta de proveedor, escriba "US-101".
4. Haga clic en Aceptar
5. En el panel de acciones, haga clic en Pedido de compra.
6. Haga clic en De todos.
    * Esta es la página desde la que puede copiar desde pedidos existentes en su pedido. Hay diversas opciones para cómo se copian las líneas y diferentes tipos de documentos desde los que puede copiar. Miraremos las opciones para cómo se copian las líneas primero.   
7. Expanda la sección Parámetros.
    * El campo Factor de cantidad es útil si necesita utilizar una cantidad que sea diferente de la que se encuentra en el pedido desde el que está copiando. Por ejemplo, si desea pedir dos veces la cantidad que se encuentra en las líneas desde las que está copiando, escribirá “2" en este campo y, a continuación, el sistema agregaría líneas en las que se haya duplicado la cantidad original.  
    * El campo Invertir el signo también admite el cambio de la cantidad pedida al cambiar el signo de la cantidad para las líneas de pedido que se agregan. Esto puede ser útil si tiene que invertir una transacción, creando las líneas de pedido que niegan la transacción. Esta opción se selecciona automáticamente cuando se abre la página desde la acción Crear nota de abono.  
    * La opción Copiar gastos permite copiar gastos en su nuevo pedido del documento del que está copiando las líneas de pedido.  
    * La opción Volver a calcular el precio utiliza los precios y descuentos actuales en lugar de copiarlos del documento desde el que está copiando otra información.  
    * La opción Copiar con exactitud crea una copia exacta de los valores en todos los campos de las líneas y del encabezado del documento de pedido. Si esta opción no está seleccionada, los valores predeterminados se utilizan para muchos de los campos relativos al proveedor y a los productos como si estuviera creando el nuevo pedido manualmente. Por ejemplo, si el pedido desde el que está copiando había anulado la cuenta de la factura predeterminada para el proveedor, esa misma cuenta de factura se copiaría en el pedido. Si no seleccionó la opción Copiar con exactitud, la cuenta de la factura predeterminada para el proveedor se usaría en su lugar en el pedido.  
    * La opción Eliminar las líneas de compra elimina todas las líneas de pedido de compra que ya existen en el pedido de compra en el que está copiando, antes de aplicar las líneas nuevas. Utilice esta opción con precaución, ya que elimina todas las líneas existentes sin ninguna advertencia adicional.  
    * Si utiliza la opción Copiar la cabecera de pedido, usted no necesita crear manualmente la información de la cabecera en su nuevo pedido. Observe que esta opción dará como resultados valores predeterminados que se utilizan para los campos asociados al proveedor. Si el documento desde el que está copiando tiene valores que no son predeterminados que desea copiar, use también la opción Copiar con exactitud.  
8. Contraiga la sección Parámetros.
    * Hay diferentes orígenes de documento desde los que puede copiar y cada uno de ellos tiene una sección independiente en esta página. Por ejemplo, la sección Pedidos de compra le permite copiar de pedidos de compra existentes.  
9. Haga clic en la línea del pedido de compra que tiene un id. de 00015. 
10. Para seleccionar la línea, haga clic en la casilla.
11. Desactive la casilla para la línea para que no se copie en el pedido.
    * Ahora se han seleccionado 4 líneas para copiarla en su pedido de compra. Es posible seleccionar líneas de pedidos de compra adicionales de otros pedidos de compra y copiarlos también en el pedido. También es posible agregar líneas de otros tipos de documentos de compra. En los pasos siguientes pasos se revisan las diferentes opciones.  
12. Contraiga la sección Pedidos de compra.
13. Expanda la sección Confirmación.
    * Aquí puede seleccionar confirmaciones de pedidos de compra desde la que copiar. Las confirmaciones de pedidos de compra se identifican por el id. de diario de compra asociado o el id. de pedido de compra.  
14. Contraiga la sección Confirmación.
15. Expanda la sección Recepciones de producto.
    * Aquí puede seleccionar diarios de recepciones de producto desde los que copiar. Los diarios de recepciones de producto se identifican por el asiento de recepción de producto o el id. de pedido de compra.   
16. Contraiga la sección Recepciones de producto.
17. Expanda la sección Facturas.
    * Aquí puede seleccionar facturas de proveedor desde las que copiar. Las facturas se identifican por el asiento de factura o el id. de pedido de compra.   
18. Contraiga la sección Facturas.
19. Expanda la sección Líneas o encabezados seleccionados que se copiarán.
    * Esta vista le muestra un resumen de todos los documentos y líneas que se han seleccionado para copiarlas en su pedido.   
20. Contraiga la sección Líneas o encabezados seleccionados que se copiarán.
21. Haga clic en Aceptar
    * Las 4 líneas que ha seleccionado se han copiado en su nuevo pedido de compra.   

## <a name="copy-lines-to-an-existing-purchase-order"></a>Copiar líneas en un pedido de compra existente
    * En vez de copiar un pedido completo, es más habitual crear un nuevo pedido de compra y la información completa de la cabecera del pedido y, a continuación, copias líneas individuales de los pedidos existentes.  
1. Haga clic en Línea de pedido de compra.
2. Haga clic en De todos.
    * La página que se abre es idéntica a la mostrada antes, pero se seleccionan diferentes opciones cuando se abre desde la vista de líneas de pedido. Revisemos los parámetros.   
3. Expanda la sección Parámetros.
    * La opción Eliminar las líneas de compra no está seleccionada. Esto significa que puede copiar nuevas líneas en su pedido sin eliminar las líneas existentes.   
    * No se selecciona tampoco la opción Copiar la cabecera de pedido, pues solo estamos agregando líneas adicionales al pedido.   
4. Contraiga la sección Parámetros.
    * Para este ejemplo, copiaremos líneas de un pedido de compra existente.   
5. Haga clic en la línea del pedido de compra que tiene un id. de 00034. 
6. Para seleccionar la línea, haga clic en la casilla.
    * Observe que la línea de pedido única que se encuentra en este pedido de compra también está seleccionada.  
7. Haga clic en Aceptar
    * Se ha agregado la línea de pedido adicional a su pedido de compra.  



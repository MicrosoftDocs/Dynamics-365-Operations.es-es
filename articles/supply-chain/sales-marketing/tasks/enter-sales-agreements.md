--- 
title: Especificar los acuerdos de ventas
description: "Este procedimiento le muestra cómo crear un acuerdo de venta que compromete uno de los clientes a comprar un producto en una cantidad acordada durante un período de tiempo a cambio de descuentos especiales."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a1c4b7623f3409d4474adcd04fb1331b944b9fbb
ms.openlocfilehash: a0d49068d2c6a62bf7912c2fd7cccd53308bd196
ms.contentlocale: es-es
ms.lasthandoff: 02/13/2018

---
# <a name="enter-sales-agreements"></a>Especificar los acuerdos de ventas

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo crear un acuerdo de venta que compromete uno de los clientes a comprar un producto en una cantidad acordada durante un período de tiempo a cambio de descuentos especiales. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.


## <a name="set-up-sales-agreement-header"></a>Configurar el encabezado del acuerdo de venta
1. Vaya a Ventas y marketing > Acuerdos de venta > Acuerdos de venta.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. En el campo Clasificación del acuerdo de venta, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Expanda la sección General.
9. En el campo Compromiso predeterminado, seleccione "Compromiso de valor de producto".
    * Un tipo de compromiso es un criterio obligatorio que debe asignar el acuerdo para definir cómo se cumplirá el contrato del acuerdo. Los cuatro tipos predefinidos le permiten configurar el destino de compromiso del cliente, expresado como cantidad o valor. El tipo de compromiso de cantidad solo puede aplicarse a un producto específico, pero los tipos basados en valores son aplicables a la venta tanto de productos específicos como no específicos.  
10. En el campo Fecha de vencimiento, establezca la fecha en una fecha futura en la que desea que expire el acuerdo.
11. Haga clic en Aceptar

## <a name="set-up-product-value-commitment-lines"></a>Configurar líneas de compromiso de valor de producto
1. Haga clic en Agregar línea.
2. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
    * El tipo de compromiso que ha elegido para el acuerdo afecta a la clase de información que puede especificar para las líneas del acuerdo. Por ejemplo, para un acuerdo basado en valor debe especificar el importe neto total (en la divisa acordada) para el que el cliente se compromete a comprarle mercancías. En este ejemplo, los campos Cantidad y Unidad de la línea no están disponibles porque está creando un acuerdo para que el cliente compre un valor específico de un producto.   
5. En el campo Importe neto, especifique el importe monetario que el cliente se ha comprometido a comprar.
6. En el campo Porcentaje de descuento, especifique un valor de porcentaje que se aplicará a las líneas de pedidos de ventas del cliente que están vinculadas al acuerdo.
7. Expanda la sección Detalles de línea.
8. Seleccione Sí en el campo Máximo aplicado.
    * La selección de la Máximo aplicado es obligatoria implica que el importe total de todas las líneas de pedidos de ventas que usan los precios especiales del compromiso, los descuentos y las condiciones de pago no deben superar el importe especificado en el compromiso.  
    * Los importes mínimo y máximos parciales especifican un intervalo de valores que se deben vender en cada pedido de ventas que usa el acuerdo seleccionado.   
9. Expanda la sección Encabezado del acuerdo de venta.
    * A menos que el estado del acuerdo se establezca en Vigente, los pedidos de ventas no se pueden asociar al acuerdo y por tanto no pueden contribuir a su cumplimiento. No puede modificar el estado de forma manual en esta etapa. Sin embargo, el estado se cambiaría normalmente cuando confirma el acuerdo para el cliente.  
10. En el panel de acciones, haga clic en Acuerdo de venta
11. Haga clic en Confirmación.
    * Asegúrese de que la opción Marcar acuerdo como vigente se establece en Sí.  
12. Seleccione Sí en el campo Imprimir informe.
13. Haga clic en Aceptar
14. Cierre la página.
    * El acuerdo está ahora vigente y puede empezar a vincular los pedidos del cliente al acuerdo, para compensar contra el objetivo comprometido.  



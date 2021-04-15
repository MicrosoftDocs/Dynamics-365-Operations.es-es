---
title: Solucionar problemas de fabricación discreta
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con fabricación discreta.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: b9c43d59e8022a365853f4b9cbb32ac3c3074e3f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810927"
---
# <a name="troubleshoot-discrete-manufacturing"></a>Solucionar problemas de fabricación discreta

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con fabricación discreta.

## <a name="i-receive-the-following-error-message-warehouse-management-processes-are-currently-being-used-if-work-lines-are-not-yet-registered-you-can-cancel-the-created-work-and-any-load-or-shipment-lines-and-then-continue-with-the-picking-or-shipping-process"></a>Recibo el siguiente mensaje de error: "Actualmente se están utilizando procesos de gestión de almacenes. Si las líneas de trabajo aún no están registradas, puede cancelar el trabajo creado y cualquier línea de carga o envío, y luego continuar con el proceso de selección o envío ".

### <a name="issue-description"></a>Descripción del problema

Este problema ocurre si intenta reservar o liberar trabajo para una línea, pero la transacción de inventario tiene un estado *Escogido*, que indica que el material ha sido recogido.

### <a name="issue-resolution"></a>Solución del problema

Para arreglar este problema, siga uno de estos pasos.

- Cambiar el estado de la orden de producción a *Estimado* o *Liberado*.
- Abra la página de detalles del pedido de producción pertinente. En el panel de acciones, en la pesetaña **Almacén**, en el grupo **Detener**, seleccione **Detener y cancelar selección** para anular todas las transacciones seleccionadas. Luego seleccione **Quitar parada** para procesar la orden de producción.

Aquí hay una explicación de las funciones *Cancelar selección* y *Detener*:

- **Anular selección** - Esta función invierte el estado de las transacciones de inventario para las líneas de lista de materiales (L. MAT.) y las líneas de fórmula que tienen un estado de *Seleccionado* pasando por *En orden*. Cuando se completa el trabajo para el picking de materia prima, el estado de las líneas se establece en *Seleccionado*. Este estado evita que la orden de producción se restablezca a estado *Creado*. En este caso, puede utilizar la función *Anular selección* función para revertir las transacciones de estado *Seleccionado* y luego restablecer la orden de producción a estado *Creado*.
- **Detener** - Esta función establece un indicador **Detenido** en la orden de producción para evitar cualquier actualización de estado en la orden. Puede encontrar el indicador **Detenido** en la ficha desplegable **Almacén** de la página de detalles de la orden de producción.

> [!NOTE]
>
> - Los botones están visibles solo cuando se crea la orden de producción para los artículos que están habilitados para los procesos de almacén.
> - El grupo **Detener** es visible solo en la pestaña **Almacén** del Panel de acciones de la página de detalles de la orden de producción. No es visible en la ficha desplegable **Almacén** de la página de lista **Órdenes de producción**.

## <a name="the-matching-resource-name-isnt-updated-after-i-change-a-worker-name-in-the-global-address-book"></a>El nombre del recurso coincidente no se actualiza después de cambiar el nombre de un trabajador en la libreta de direcciones global.

### <a name="issue-description"></a>Descripción del problema

El nombre del recurso coincidente no se actualiza en el maestro del grupo de recursos si se cambia el nombre de un trabajador en la libreta de direcciones global.

### <a name="issue-resolution"></a>Solución del problema

Este escenario no se admite actualmente. Para solucionar el problema, debe actualizar manualmente el nombre del recurso.

## <a name="when-i-create-a-new-production-order-i-dont-receive-the-following-message-insert-the-active-version-of-bill-of-material-and-route"></a>Cuando creo una nueva orden de producción, no recibo el siguiente mensaje: "¿Insertar la versión activa de la lista de materiales y la ruta?"

### <a name="issue-description"></a>Descripción del problema

Cuando crea una nueva orden de producción, después de ingresar el número de artículo, los campos **Sitio** y **Almacén** se establecen automáticamente en el sitio y el almacén predeterminados que se definen en la página **Configuración de orden predeterminada** para el artículo de productos terminados. Además, el número de lista de materiales activo y el número de ruta se ingresan automáticamente. No recibe el siguiente mensaje que le solicita esos valores:

> ¿Insertar versión activa para lista de materiales y ruta?

### <a name="issue-resolution"></a>Solución del problema

No se le solicitará que inserte los números de lista de materiales y de ruta si selecciona un producto para el que se definen un sitio y un almacén en la página **Configuración de orden predeterminada**. Solo se le solicitará si esos valores no están definidos para el producto seleccionado.

## <a name="production-orders-arent-shown-on-the-marking-page"></a>Las órdenes de producción no se muestran en la página Marcado.

### <a name="issue-description"></a>Descripción del problema

Algunas órdenes de producción no se muestran en la página **Marcado**.

### <a name="issue-resolution"></a>Solución del problema

Los productos que tienen la siguiente configuración no están disponibles para marcar. Por lo tanto, no se mostrarán en la página **Calificación**:

- Los productos se definen como productos del tipo *peso capturado*.
- Están habilitados para los procesos de almacén avanzados.
- Están configurados para ser controlados por el principio *Costo estándar*.

## <a name="when-i-try-to-end-a-production-order-i-receive-the-following-error-message-calculating-bom-consumptioncost-value-must-be-negative-upon-issue-from-inventory"></a>Cuando intento finalizar una orden de producción, recibo el siguiente mensaje de error: "Calculando el consumo de la lista de materiales El valor del costo debe ser negativo en el momento de la emisión del inventario".

Este problema se solucionó en la versión 10.0.15.

## <a name="when-the-status-of-a-production-order-is-changed-from-reported-as-finished-to-end-i-receive-the-following-error-messages-update-conflict-the-standard-cost-does-not-match-with-the-financial-inventory-value-after-the-update-and-a-critical-error-has-occurred-in-function-inventcostmovementcheckvariance"></a>Cuando el estado de una orden de producción cambia de Reportado como terminado a Finalizado, recibo los siguientes mensajes de error: "Conflicto de actualización. El costo estándar no coincide con el valor del inventario financiero después de la actualización" y "Se ha producido un error crítico en la función InventCostMovement.checkVariance".

Este problema se produce porque otro proceso cambió los datos subyacentes. El proceso intentará actualizar los datos hasta cinco veces. Si el conflicto persiste después de cinco intentos, recibirá los siguientes mensajes de error:

> Actualizar conflicto. El costo estándar no coincide con el valor del inventario financiero después de la actualización.

> Se ha producido un error crítico en la función InventCostMovement.checkVariance.

Este comportamiento se debe al diseño. Para mitigar el problema, reanude el trabajo por lotes. Debería terminar de funcionar.

Si el trabajo por lotes falla constantemente después de reanudarlo, verifique que la precisión de redondeo para la moneda predeterminada del libro mayor cumpla con el redondeo que se aplica a los valores en la tabla InventSum. Si la precisión de redondeo se ha cambiado a un valor no compatible, probablemente deba volver a cambiarlo a un valor compatible. Buscar **ModifiedDateTime**. En este caso, el valor normalmente mostrará que la precisión de redondeo se cambió recientemente.

## <a name="when-i-release-to-a-warehouse-i-receive-the-following-error-message-item-rm-could-not-be-fully-reserved-ensure-that-the-full-quantity-is-available-or-reserve-the-items-manually-if-the-reservation-field-on-the-bom-line-is-set-to-manual-or-started-could-not-release-the-order-to-warehouse-because-some-materials-could-not-be-reserved-however-the-status-is-updated-to-released"></a>Cuando lo envío a un almacén, recibo el siguiente mensaje de error: "El artículo RM no se pudo reservar por completo. Asegúrese de que la cantidad completa esté disponible o reserve los artículos manualmente si el campo Reserva en la línea de la lista de materiales está configurado como Manual o Iniciado. No se pudo liberar el pedido al almacén porque no se pudieron reservar determinados materiales". Sin embargo, el estado se actualiza a Liberado.

### <a name="issue-description"></a>Descripción del problema

Si no todas las partidas de la lista de materiales están disponibles físicamente cuando se libera una orden de producción, **Liberar al almacén** la política está establecida en *Requiere reserva completa* en la orden de producción, recibirá el siguiente mensaje de error:

> El artículo RM no se pudo reservar por completo. Asegúrese de que la cantidad completa esté disponible o reserve los artículos manualmente si el campo Reserva en la línea de la lista de materiales está configurado como Manual o Iniciado. No se pudo liberar el pedido al almacén porque no se pudieron reservar determinados materiales.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento es por diseño y funciona como se esperaba.

## <a name="when-i-try-to-end-a-production-order-and-report-as-finished-i-receive-the-following-error-message-total-good-quantity-reported-as-finished-for-the-production-will-be-1-feedback-for-the-last-operation-is-000-in-total"></a>Cuando trato de finalizar una orden de producción e informar como terminada, recibo el siguiente mensaje de error: "La cantidad total buena reportada como terminada para la producción será %1. La realimentación para la última operación es 0.00 en total".

### <a name="issue-description"></a>Descripción del problema

Cuando intenta publicar un informe como diario terminado en una orden de producción, recibe el siguiente mensaje de error:

> La cantidad sin errores total notificada como terminada para la producción será %1. La realimentación para la última operación es 0.00 en total.

### <a name="possible-cause"></a>Causa posible

Este problema ocurre si las cantidades contabilizadas en las últimas operaciones eran incorrectas. Por ejemplo, si se inicia la producción, pero no se asigna la cantidad que debe iniciarse, el diario de la tarjeta de ruta se contabilizará sin líneas. Para confirmar la situación, abra la orden de producción y luego, en el Panel de acciones, en la pestaña **Ver**, seleccione **Tarjeta de ruta**.

### <a name="workaround"></a>Solución alternativa

Puede solucionar este problema publicando diarios adicionales para las operaciones para las que los diarios no se publicaron correctamente. Reinicie la orden de producción y seleccione contabilizar los diarios adicionales. Esta acción no iniciará la orden de producción, pero registrará los diarios. La tarjeta de ruta debería mostrar las cantidades que se registraron y debería poder finalizar las órdenes de producción correctamente.

## <a name="can-i-report-a-production-order-as-finished-while-i-report-the-error-quantity-but-not-while-i-report-the-time-or-material-quantity"></a>¿Puedo informar una orden de producción como terminada mientras informo la cantidad de error, pero no mientras informo la cantidad de tiempo o material?

No puede informar la cantidad de error en una orden de producción a menos que también informe la cantidad buena. Este escenario **no** se admite. El informe como actualización finalizada eventualmente fallará cuando intente finalizar la orden de producción, y recibirá el siguiente mensaje de error:

> Falta notificación de cantidad como terminada.

## <a name="can-i-trace-the-serial-numbers-of-finished-goods-against-the-serial-numbers-of-consumed-goods"></a>¿Puedo rastrear los números de serie de los productos terminados con los números de serie de los productos consumidos?

No puede rastrear los números de serie de los productos terminados con los números de serie del material que consume una orden de producción para fabricar esos productos terminados. Este escenario no se admite actualmente. La solución es crear órdenes de producción por una cantidad de 1.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
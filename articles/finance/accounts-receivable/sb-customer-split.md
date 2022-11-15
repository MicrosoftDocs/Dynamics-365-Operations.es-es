---
title: División del cliente en programaciones de facturación
description: Este artículo describe cómo dividir un cliente cuando se utiliza la facturación de suscripción.
author: JodiChristiansen
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-11-05
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: cfbe61ca4b7e809a8183f4622bf6db4fc83a4d83
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746321"
---
# <a name="customer-split-on-billing-schedules"></a>División del cliente en programaciones de facturación

En un calendario de facturación, la *cuenta factura* es el cliente que recibe la factura del pedido de venta para que pueda pagar la factura. En algunos escenarios, más de un cliente puede pagar una factura. La funcionalidad **División de clientes** le permite agregar más clientes a los que se les puede facturar con el mismo programa de facturación. Para habilitar esta funcionalidad, vaya a **Facturación de suscripción \> Facturación de contratos recurrentes \> Configuración \> Parámetros de facturación de contratos recurrentes**, y establezca la opción **División de clientes** en **Sí**.

## <a name="customer-split-on-the-billing-schedule-header"></a>División del en el encabezado de programación de facturación

Después de crear un programa de facturación, se pueden agregar clientes adicionales al encabezado del programa de facturación.

Para agregar un cliente, siga estos pasos.

1. En la pestaña **Programa de facturación**, seleccione **División del cliente**. Los campos **Cuenta de cliente** y **Nombre de la cuenta del cliente** los campos en la parte superior especifican el cliente que se asigna como el **Calendario de facturación al cliente**.

    > [!NOTE]
    > La cuenta de cliente que agregue no puede ser la misma que la cuenta de facturación.

2. En la pestaña **Líneas de división de cliente**, seleccione **Agregar línea**.
3. Seleccione un cliente y luego ingrese el porcentaje de cada factura para ese cliente.
4. De forma predeterminada, las fechas de inicio y finalización del programa de facturación se utilizan como fechas de inicio y finalización. Ingrese diferentes fechas de inicio y finalización si el nuevo cliente pagará el porcentaje especificado solo por una parte del cronograma de facturación. Por ejemplo, si el programa de facturación tiene como fecha de inicio el 1 de enero y como fecha de finalización el 31 de diciembre, y al nuevo cliente se le factura el 40 por ciento durante los primeros nueve meses, especifique el 1 de enero como fecha de inicio y el 30 de septiembre como fecha de finalización, e introduzca **40,00** como el porcentaje.

No se puede agregar más de un cliente a las líneas de división de cliente. En este caso, el porcentaje total que se ingresa no debe exceder el 100 por ciento. Ingrese una referencia de cliente y una solicitud de cliente como campos informativos que se mostrarán en la línea de orden de venta durante el proceso **Generar factura**.

Los detalles de la línea mostrarán la información de contacto, la dirección de entrega, la dirección de facturación y los detalles de pago de los clientes agregados. Esta información también se mostrará en la orden de venta para los clientes.

Cuando agrega información de división del cliente al encabezado del programa de facturación, si hay líneas del programa de facturación no facturadas en el programa de facturación, recibirá el siguiente mensaje que le indicará que reduzca los cambios: "¿Desea reducir el cambio de el encabezado de las líneas? Los cambios solo actualizarán las líneas del programa de facturación que no se facturan". Seleccione **Sí** para actualizar la información de división del cliente en la línea de programación de facturación. Los cambios no se actualizarán si la línea del programa de facturación ya se facturó.

Si se crea un programa de facturación utilizando la opción **Copiar programación**, la información predeterminada se ingresará en las líneas de encabezado de división del cliente. No puede ser la misma que la cuenta del cliente.

Cuando el proceso **Generar factura** se completa, se crearán múltiples órdenes de venta. (También se crearán varias facturas de venta si se utiliza la contabilización automática). Estas órdenes de venta y facturas de venta se pueden ver en la pestaña **Factura** en la ficha desplegable **Detalles de línea** de la página **Ver detalle de facturación**. **Múltiple** se muestra en la línea de detalle de facturación para indicar que se crearon varias órdenes de venta y facturas de venta.

## <a name="customer-split-on-billing-schedule-lines"></a>División del cliente en líneas programaciones de facturación

La división del cliente se puede agregar a líneas de programación de facturación individuales si desea dividir solo líneas de programación de facturación específicas. Seleccione la casilla de verificación en la línea **División de clientes** y, a continuación, seleccione **División de clientes** en el menú de la línea del programa de facturación para actualizar o ingresar la información de división del cliente.

La información de auditoría se actualiza si el programa de facturación ya se facturó, pero luego se cambió el porcentaje en la línea del programa de facturación. Cualquier línea que se facture después de ese cambio utilizará el nuevo porcentaje.

> [!NOTE]
> - La opción de división del cliente no se puede utilizar con productos almacenados.
> - Si la casilla de verificación **Ingresos no facturados** está seleccionada, la casilla de verificación **División de clientes** no se puede seleccionar.
> - Si utiliza la opción **Solo división de ingresos**, la línea principal tiene la opción **División de clientes**, pero las líneas de pedido secundarias no.

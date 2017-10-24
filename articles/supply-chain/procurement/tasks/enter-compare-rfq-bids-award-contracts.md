--- 
title: Especificar y comparar ofertas de la solicitud de presupuesto y conceder contratos
description: "Este procedimiento le muestra cómo especificar respuestas a una solicitud de presupuesto, puntuar y comparar ofertas y, a continuación, conceder la oferta a uno de los proveedores."
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5dea9d7bfb1bf7b11f6c49cccaab1b73d4e58d16
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Especificar y comparar ofertas de la solicitud de presupuesto y conceder contratos

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo especificar respuestas a una solicitud de presupuesto, puntuar y comparar ofertas y, a continuación, conceder la oferta a uno de los proveedores. Puede utilizar este procedimiento en la empresa de datos de demostración USMF. Antes de empezar, debe tener una solicitud de presupuesto con dos líneas que se ha enviado al menos a dos proveedores. Puede ejecutar el procedimiento "Crear una solicitud de presupuesto" como requisito previo para crear esto. Es necesario haber configurado criterios de puntuación para poder ejecutar este procedimiento.


## <a name="enter-a-reply-from-a-vendor"></a>Introduzca una respuesta de un proveedor
1. Vaya a Adquisición y abastecimiento > Solicitudes de presupuestos > Todas las solicitudes de presupuesto.
2. Seleccione una solicitud de presupuesto que tenga un estado de Enviado y haga clic en el vínculo del Caso de solicitud de presupuesto.
    * La solicitud de presupuesto se debe haber enviado al menos a 2 proveedores.  
3. Haga clic en Encabezado para ir a la lista de proveedores.
4. Seleccione el proveedor para el que desea escribir una respuesta en la solicitud de presupuesto.
5. Haga clic en Especificar respuesta.
6. En el panel de acciones, haga clic en Contestación.
7. Haga clic en Copiar datos en respuesta.
    * Esta acción copiará los datos seleccionados, por ejemplo, la cantidad del caso de solicitud de presupuesto a la respuesta de solicitud de presupuesto. También puede omitir esta acción y rellenar todos los campos de respuesta manualmente al editar la respuesta.  
8. Haga clic en Editar.
9. En el campo Precio unitario, escriba un número.
10. Elija la otra línea de presupuesto.
11. En el campo Precio unitario, escriba un número.

## <a name="score-the-bid"></a>Puntuar la oferta
1. Haga clic en Encabezado para ir a la puntuación de la oferta.
2. Expanda la sección Puntuación de oferta.
3. En el campo Resultado, escriba un número para uno de los criterios de puntuación.
    * Si mantiene el puntero por encima de los criterios de puntuación, una información sobre herramientas muestra el intervalo que tiene que puntuar dentro. En esta demostración puede agregar un número entre 1 y 5 a cualquiera de los criterios.  
4. Seleccione otro criterio de puntuación.
5. En el campo Puntuación, escriba un número.
6. Expanda la sección Cuestionarios.
    * Si el caso de la solicitud de presupuesto tiene un cuestionario que se envió a los proveedores, puede especificar sus respuestas en la sección del cuestionario.  
7. Cierre la página.

## <a name="enter-a-reply-for-another-vendor"></a>Escribir una respuesta para otro proveedor
1. Seleccione el siguiente proveedor desactivando el proveedor para el que acaba de escribir la respuesta y seleccionando a continuación la fila del siguiente proveedor.
2. En la lista, busque y seleccione el registro deseado.
3. Haga clic en Especificar respuesta.
4. Haga clic en Copiar datos en respuesta.
5. Haga clic en Editar.
6. En el campo Precio unitario, escriba un número.
7. Elija la otra línea de presupuesto.
8. En el campo Precio unitario, escriba un número.

## <a name="score-the-second-bid"></a>Puntuar la segunda oferta
1. Haga clic en Encabezado para ir a la puntuación de la oferta.
2. En el campo Puntuación, escriba un número.
3. En la lista, busque y seleccione el registro deseado.
4. En el campo Puntuación, escriba un número.

## <a name="compare-the-replies"></a>Comparar las respuestas
1. En el panel de acciones, haga clic en General.
2. Haga clic en Comparar respuestas.
3. En el campo Categoría, escriba un número.
    * Esta página muestra las ofertas con el encabezado y las líneas, y la puntuación total en el nivel de encabezado. Puede comparar las líneas ordenando en la cuadrícula de modo que las líneas comparables estén una junto a la otra. La información también incluye: Cantidad: La cantidad presupuestada por el proveedor. Esta cantidad puede no ser igual a la cantidad especificada en la solicitud de presupuesto.   Importe neto: el precio presupuestado por un proveedor, después de restar los descuentos, para los artículos de la línea.   Desviación: el número de días que se desplaza la fecha de entrega en la cabecera de la oferta o la línea de la fecha de entrega solicitada en la cabecera o línea de solicitud de presupuesto.   Puede especificar una categoría para cada oferta.  
4. Seleccione la línea de encabezado para la otra oferta que desea clasificar.
5. En el campo Categoría, escriba un número.
6. Haga clic en Guardar.

## <a name="reject-a-bid"></a>Rechazar una oferta
1. Seleccione la línea de encabezado para la oferta que desea rechazar.
    * Solo puede aceptar, rechazar o devolver una oferta o líneas dentro de una oferta cada vez.  
2. Active la casilla Marcar.
    * Si activa la casilla Marcar en el encabezado de la oferta, se marcarán también todas las líneas. También podría elegir marcar un subconjunto de las líneas dentro de la oferta para rechazarlas o aceptarlas. Es posible aceptar la propuesta de un proveedor para algunas líneas de la solicitud de presupuesto y después conceder otras líneas de la solicitud de presupuesto a otro proveedor. No obstante necesita hacer esto en 2 pasos, una oferta cada vez. Si las líneas alternativas están presentes, solo puede aceptar la línea de oferta original o su alternativa, pero no ambas.  
3. Haga clic en Rechazar.
4. Haga clic en Parámetros para abrir el cuadro de diálogo desplegable.
5. En el campo Motivo de rechazo, especifique o seleccione un valor.
    * El motivo del rechazo se almacenará en la respuesta.  
6. Haga clic en Aceptar
7. Haga clic en Aceptar
8. Cierre la página.
9. Cierre la página.
10. Actualice la página.

## <a name="accept-a-bid"></a>Aceptar una oferta
1. Seleccione la oferta que desea aceptar y haga clic en el vínculo del campo Solicitud de presupuesto.
2. En el panel de acciones, haga clic en Contestación.
3. Haga clic en Aceptar.
    * Si ha marcado líneas específicas y no otras, la acción de aceptación solo incluirá las líneas marcadas. Si desea aceptar todas las líneas de la oferta, no es necesario marcar las líneas.  
4. Haga clic en Parámetros para abrir el cuadro de diálogo desplegable.
    * Esto le permite registrar un motivo para aceptar la oferta. El motivo se almacenará en la oferta.  
5. En el campo Motivo de aceptación, especifique o seleccione un valor.
6. Haga clic en Aceptar
7. Haga clic en Aceptar
    * Al hacer clic en Aceptar esto genera un pedido de compra basado en las líneas que se incluyen en la aceptación de solicitud de presupuesto. Si hay otras ofertas que no se han procesado (aceptado, rechazado o devuelto), el sistema le pedirá rechazar las ofertas restantes.  

## <a name="view-the-purchase-order-thats-been-generated"></a>Ver el pedido de compra que se ha generado
1. En el panel de acciones, haga clic en General.
2. Haga clic en Pedido de compra.
    * Aquí puede ver el pedido de compra que se generó al aceptar la oferta.  
3. Cierre la página.
4. Cierre la página.
5. Cierre la página.
6. Cierre la página.



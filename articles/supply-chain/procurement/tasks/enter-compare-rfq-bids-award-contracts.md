---
title: Especificar y comparar ofertas de la solicitud de presupuesto y conceder contratos
description: Este artículo explica cómo especificar respuestas a una solicitud de presupuesto (RFQ por sus siglas en inglés), puntuar y comparar ofertas y, a continuación, conceder el contrato a uno de los proveedores.
author: GalynaFedorova
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchRFQCaseTable, PurchRFQReplyTable, PurchRFQCompare, PurchRFQEditLines, PurchRFQEditLinesParameters, PurchTable, PurchTablePart, PurchRFQCompareLinePrices, PurchRFQCompareRFQ
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3ef754f2d5d58254a7c6f0e572115f8a2981ad9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893392"
---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Especificar y comparar ofertas de la solicitud de presupuesto y conceder contratos

[!include [banner](../../includes/banner.md)]

Este artículo explica cómo especificar respuestas a una solicitud de presupuesto (RFQ por sus siglas en inglés), puntuar y comparar ofertas y, a continuación, conceder el contrato a uno de los proveedores. Puede utilizar este procedimiento en la empresa de datos de demostración **USMF**.

Antes de empezar este procedimiento, debe tener una solicitud de presupuesto con dos líneas y que se haya enviado al menos a dos proveedores. Para crear la solicitud de presupuesto, complete el procedimiento [Crear una solicitud de presupuesto](create-request-quotation.md). Es necesario haber configurado criterios de puntuación para poder completar este procedimiento.

Puede especificar la propuesta como proveedor o profesional de compras. Para obtener más información, consulte [Configuar y mantener la colaboración del proveedor](../set-up-maintain-vendor-collaboration.md).

## <a name="enter-a-reply-as-a-vendor"></a>Introduzca una respuesta como un proveedor

1. Vaya a **Colaboración de proveedores \> Espacios de trabajo \> Ofertas de proveedores**.
2. En el lista **Nuevas invitaciones de la oferta**, encuentre una solicitud de presupuesto que acaba de registrar. Seleccione la solicitud de presupuesto para revisar qué se solicitó.
3. Seleccione **Datos adjuntos de la solicitud de presupuesto** para revisar los archivos adjuntos que se hayan agregado.
4. Seleccione **Propuesta** para hacer que los campos puedan editarse. Observe que el campo **Progreso de la oferta** está establecido en **El proveedor está actualizando**.
5. En la cabecera y las líneas, especifique los parámetros de respuesta de la propuesta.
6. Si algunos datos adjuntos se agregan a la propuesta, seleccione **Datos adjuntos de propuesta**.
7. Seleccione la ficha desplegable **Elementos de guía de la oferta** para ver si algunos documentos son obligatorios.
8. Seleccione la ficha desplegable **Modificaciones** para ver si se enmendó la solicitud de presupuesto.
9. Seleccione la ficha desplegable **Cuestionario**. Cualquier cuestionario que aparezca aquí debe ser respondido.
10. Seleccione la ficha desplegable **Detalles de línea** para ver información detallada sobre la línea.
11. Seleccione **Restaurar desde la solicitud de presupuesto** solo si debe restablecer los valores que se han especificado en los valores originales de la solicitud de presupuesto.
12. Puede guardar la propuesta en cualquier momento y hacer procesos adicionales más tarde, siempre que la fecha y hora de caducidad no hayan pasado. En este caso, puede encontrar la propuesta en la lista **Propuestas en curso** en el espacio de trabajo **Propuesta de proveedor** .
13. Cuando la propuesta esté lista para enviarse, seleccione **Enviar**. Seleccione **Rechazar** si no desea realizar ninguna oferta. Las propuestas registradas están disponibles en la lista **Propuestas enviadas** en el espacio de trabajo **Propuesta de proveedor** .  
14. Una vez registrada la propuesta, puede volver a llamarla en cualquier momento antes de la fecha y hora de vencimiento. Observe que cuando se recupera una propuesta, no se tratara como enviada. Cuando la propuesta se acepte o rechace por el departamento de compras, aparecerá en **Propuestas concedidas** o la lista **Propuestas perdidas** en el espacio de trabajo **Propuesta de proveedor** .  

## <a name="enter-a-reply-from-a-vendor-as-a-procurement-professional"></a>Especificar una respuesta de un proveedor como profesional de compras

1. Asegúrese de que el permiso para editar propuestas de proveedor esté configurado. Vaya a **Adquisición y abastecimiento \> Configuración \> Parámetros de adquisición y abastecimiento**. En la pestaña **Solicitud de presupuesto**, establezca la opción **El comprador puede editar propuesta de los proveedores** a **Sí**.
2. Vaya a **Adquisición y abastecimiento\> Solicitudes de presupuestos \> Todas las solicitudes de presupuesto**.
3. Seleccione una solicitud de presupuesto que tenga un estado de **Enviado** y después seleccione el vínculo del campo **Caso de solicitud de presupuesto**.
4. Seleccione **Administrar las respuestas**. La página que aparece muestra una solicitud de presupuesto por cada proveedor que se invitado a realizar una oferta.
5. Seleccione una solicitud de presupuesto a la que no se ha respondido. (El campo **Progreso de la respuesta** debe estar establecido en **No iniciado**.)
6. Seleccione **Edición \> Editar respuesta a solicitud de presupuesto**. Aparecerá la página **Respuesta a solicitud de presupuesto**. Como profesional de compras, puede especificar la respuesta en nombre del proveedor. Observe que el campo **Progreso de la oferta** está establecido en **El comprador está actualizando**.  
7. Introduzca los datos de la propuesta. Cuando haya terminado, haga clic en **Enviar**.

## <a name="score-the-bids"></a>Puntuar las ofertas

1. En la página **Todas las solicitudes de presupuesto**, seleccione el caso de solicitud de presupuesto para el que desea puntuar las respuestas.
2. Seleccione **Administrar las respuestas**.
3. Seleccionar la respuesta a puntuar.
4. Seleccione **Encabezado** de modo que pueda ver la puntuación de la propuesta.
5. En la ficha desplegable **Puntuación de la propuesta** introduzca un número en el campo **Puntuación** para uno de los criterios de puntuación. Si mantiene el puntero por encima de un criterio de puntuación, una información sobre herramientas muestra el intervalo en el que tiene que puntuar. En esta demostración puede introducir un número entre 1 y 5 en cualquiera de los criterios de puntuación.  
6. Repita el paso 5 para otro criterio de puntuación.
7. Si el caso de la solicitud de presupuesto tiene un cuestionario que se envió a los proveedores, puede especificar las respuestas del proveedor en la ficha desplegable **Cuestionarios**.
8. Cierre la página.
9. Repita los pasos 1 a 8 para el resto de propuestas.

## <a name="compare-the-replies"></a>Comparar las respuestas

1. En el panel de acciones, en la pestaña **General**, seleccione **Comprar respuestas**.
2. En el campo **Categoría**, escriba un número.  
    - Esta página muestra las ofertas con el encabezado, la información de línea, y también la puntuación total en el nivel de encabezado. Puede comparar las líneas ordenando en la cuadrícula de modo que las líneas comparables estén una junto a la otra. También se incluye la siguiente información:
    - **Cantidad**: la cantidad presupuestada por el proveedor. Esta cantidad puede no ser igual a la cantidad especificada en la solicitud de presupuesto.
    - **Importe neto**: el precio presupuestado por un proveedor, después de restar los descuentos, para los artículos de la línea.
    - **Desviación**: el número de días la fecha de entrega en la cabecera de la oferta o línea difiere de la fecha de entrega solicitada en la cabecera o línea de la solicitud de presupuesto. Puede especificar una categoría para cada oferta.  
3. Seleccione la línea de encabezado para la otra oferta que desea clasificar.
4. En el campo **Categoría**, escriba un número.
5. Seleccione **Guardar**.

## <a name="reject-a-bid"></a>Rechazar una oferta

1. Seleccione la línea de encabezado para la oferta que desea rechazar. Solo puede aceptar, rechazar o devolver una oferta o líneas en tan solo una oferta cada vez.
2. Selecciona la casilla **Marcar**.  
    - Si activa la casilla **Marcar** en el encabezado de la oferta, se marcarán también todas las líneas. Para rechazar o aceptar solo algunas de las líneas de la propuesta, puede marcar sólo estas líneas. Además puede aceptar una oferta de proveedor en algunas líneas de una solicitud de presupuesto pero conceder otras líneas de solicitud de presupuesto a otro proveedor. Sin embargo, debe hacerlo propuesta a propuesta.  
    - Si las líneas alternativas están presentes, puede aceptar la línea de oferta original o su alternativa, pero no ambas.  
3. Seleccione **Rechazar**.
4. Seleccione **Parámetros** y, a continuación, en el campo **Motivo del rechazo**, escriba o seleccione el motivo para rechazar la propuesta. El motivo se almacena en la respuesta.  
5. Seleccione **Aceptar**.
6. Seleccione **Aceptar**.

## <a name="accept-a-bid"></a>Aceptar una oferta

1. Seleccione la oferta que desea aceptar y después seleccione el vínculo del campo **Solicitud de presupuesto**. Si se encuentra en la página **Comparar respuestas a solicitud de presupuesto**, la propuesta resaltada que tiene el foco es la propuesta que el sistema tendrá en cuenta durante la acción de aceptación. Solo puede aceptar líneas de una sola oferta al mismo tiempo.  
2. En el panel de acciones, haga clic en **Responder**.
3. Seleccione **Aceptar**. Si ha marcado sólo líneas específicas, la acción de Aceptar incluirá únicamente estas líneas. Si desea aceptar todas las líneas de la oferta, no es necesario marcar las líneas.  
4. Seleccione **Parámetros** y, a continuación, en el campo **Motivo de aceptar**, escriba o seleccione el motivo para aceptar la propuesta. El motivo se almacena en la propuesta.  
5. Seleccione **Aceptar**.
6. Seleccione **Aceptar**. Al seleccionar **Aceptar** esto genera un pedido de compra basado en las líneas que se incluyen en la aceptación de solicitud de presupuesto. Si hay otras ofertas que no se han procesado (aceptado, rechazado o devuelto), el sistema le pedirá rechazarlas.  

## <a name="view-the-purchase-order-that-is-generated"></a>Ver el pedido de compra que se ha generado

En el panel de acciones, en la pestaña **General**, seleccione **Pedido de compra**. La página que aparece muestra el pedido de compra que se generó al aceptar la oferta.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: No puede confirmar un envío porque los artículos no se han recogido
description: No puede confirmar un envío porque los artículos no se han recogido
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7b57d3151852c9a2880185b7d9414e4246b7efb6429fcfce04c7cdae4ee00e37
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760933"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>No puede confirmar un envío porque los artículos no se han recogido

Código de error: LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:

> Algunos de los artículos necesarios para la carga %1 todavía no se han recogido y movido a la ubicación de envío final.

Por lo tanto, no puede confirmar el envío de la carga.

## <a name="cause"></a>Causa

La carga o el envío no se puede confirmar en su estado actual porque podría existir una de las siguientes condiciones:

- El trabajo relacionado aún no se ha seleccionado y trasladado a la ubicación de envío final.
- La cantidad de trabajo escogido no coincide con la cantidad de trabajo creada en la línea de carga.
- La directiva de ubicación se ha configurado con la ubicación de embalaje como la ubicación de envío final mientras se utiliza la contenedorización de plantilla Wave.

## <a name="resolution"></a>Resolución

La carga o el envío se encuentran actualmente en un estado en el que falla la confirmación del envío. Para solucionar este problema, complete una o más de las siguientes tareas:

- Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.
- Cancele las ID de trabajo que se han creado con la ubicación de embalaje como la ubicación de envío final, reconfigure la directiva de ubicación y vuelva a liberar la carga.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan

Use el siguiente procedimiento para revisar las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Seleccione la carga para la que el envío no se puede confirmar.
1. En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.
1. Anote el valor del campo **Cantidad de trabajo creado**.
1. En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.
1. Verifique que el trabajo se haya completado en la ubicación de envío final y que la cantidad de trabajo recogido coincida con la cantidad de trabajo creada en la línea de carga.
1. Repita este procedimiento para todas las líneas de carga para asegurarse de que se cumplan todos los criterios.

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a>Cancele las ID de trabajo que se han creado con la ubicación de embalaje como la ubicación de envío final, reconfigure la directiva de ubicación y vuelva a liberar la carga

Utilice el siguiente procedimiento para cancelar las ID de trabajo que tienen la ubicación de embalaje como la ubicación de colocación final con contenedorización automatizada en su lugar.

1. Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.
1. Se abre el cuadro de diálogo **Cancelar trabajo**. En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar. La identificación de trabajo seleccionada debe tener un valor **Situación laboral** de *Abierto*, *En curso*, *Cancelado*, *Combinado* o *Cerrado*.
1. Seleccione **Aceptar**.
1. Seleccione **Sí** para confirmar que desea cancelar el trabajo.
1. Repita este procedimiento para las otras ID de trabajo según sea necesario.

Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).

Utilice el siguiente procedimiento para reconfigurar la directiva de ubicación de modo que no utilice la ubicación de embalaje como la ubicación de envío final cuando se configure la contenedorización automatizada para la plantilla de oleada.

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el campo **Tipo de orden de trabajo**, seleccione *Pedidos de ventas*.
1. Seleccione la directiva de ubicación que está utilizando para la contenedorización automatizada.
1. En la barra de herramientas de la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Distancia**, busque la fila donde **Campo** se establece en *Perfil de ubicación* y verifique que el campo **Criterios** de esa fila no está configurado para un perfil de ubicación que tenga un **Tipo de ubicacion** de *Embalaje*. Ajuste el campo **Criterios** para corregir la ubicación de colocación final.

Utilice el siguiente procedimiento para liberar la carga y crear ID de trabajo con la ubicación de envío final correcta.

1. Vaya a **Gestión de almacén \> Cargas \> Área de trabajo de planificación de la carga**.
1. En la sección **Cargas**, busque la carga que necesita ser liberada.
1. En la barra de herramientas de la sección **Cargas**, seleccione **Despachar \> Despachar al almacén** para liberar la carga seleccionada al almacén.
1. Repita este procedimiento para las otras cargas según sea necesario.

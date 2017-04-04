---
title: Colabore con proveedores mediante el portal de proveedores
description: "Este tema describe cómo los agentes de compras pueden usar el portal de proveedores para colaborar con los proveedores externos durante el proceso de confirmación del pedido de compra. Esta información solo se aplica a las versiones &amp; de febrero de 2016 en mayo de 2016 de las Dynamics AX."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: e6c731109dddb7dd47595126c4bf5f1f09425a7d
ms.lasthandoff: 03/31/2017


---

# <a name="collaborate-with-vendors-by-using-the-vendor-portal"></a>Colabore con proveedores mediante el portal de proveedores

Este tema describe cómo los agentes de compras pueden usar el portal de proveedores para colaborar con los proveedores externos durante el proceso de confirmación del pedido de compra. Esta información solo se aplica a las versiones &amp; de febrero de 2016 en mayo de 2016 de las Dynamics AX.

La información de este tema se aplica solo a las versiones de febrero de 2016 y mayo de 2016 de Dynamics AX. La funcionalidad del portal de proveedores se ha sustituido por la funcionalidad extendida de colaboración del proveedor en Dynamics 365 para la versión 1611 de las operaciones. Para obtener más información acerca de la nueva funcionalidad de colaboración de proveedor, vea [mediante la colaboración del proveedor a trabajar con los proveedores externos vendor-collaboration-work-external-vendors.md] ().  

El portal de proveedores está dirigido a proveedores que no tienen integración de intercambio electrónico de datos (EDI) con Microsoft Dynamics AX para intercambiar la información de pedidos de compra. El portal permite que los agentes de compra envíen un pedido de compra al proveedor y que reciban una respuesta de Confirmada o Rechazado directamente en Dynamics AX.  

El proceso se puede configurar de modo que una confirmación del proveedor confirma automáticamente el pedido. En este caso, solo se requiere seguimiento en algunas ocasiones, cuando se rechaza un pedido o si la confirmación del proveedor se registra como una respuesta pero el estado de OC no se actualiza a **Confirmado** debido a un problema durante el proceso de confirmación.

## <a name="po-confirmation-and-rejection"></a>Confirmación y rechazo de OC
Las OC se preparan en Dynamics AX. Cuando tiene una OC que tiene un estado **Aprobado**, envíelo al proveedor generando una solicitud de confirmación. Si quiere que el proveedor se fije en una nueva OC, también puede usar el sistema de gestión de impresión para enviar la OC por correo electrónico. El pedido de compra aparece en el portal de proveedores e incluye una opción que el proveedor puede usar para confirmarlo o rechazarlo. El proveedor también puede agregar comentarios para comunicar información como cambios al pedido de compra.  

En el portal de proveedores, el proveedor puede ver líneas de pedidos. Estas líneas incluyen información como el número de producto externo, las dimensiones, la información de precios, la cantidad, la fecha de entrega y la dirección de entrega. El proveedor puede generar un informe que muestre la información del pedido de compra y también el precio total. Se muestran los gastos relevantes para el proveedor si el proveedor hace clic en el botón **Gastos** del encabezado o en las líneas. Los proveedores pueden importar la información de OC en su propio sistema mediante la funcionalidad **Exportar a Excel**.  

La siguiente tabla muestra el intercambio de información normal, en función de cómo responde el proveedor cuando se le envía un pedido de compra para confirmación.

| Tipo de respuesta                                                                                                  | Resultado                                                                                                                                                                                                                                                                                          |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| El proveedor confirma el pedido. El sistema se configura para confirmar automáticamente los pedidos de compra cuando el proveedor confirma.    | El estado del pedido se actualiza a **Confirmado**. Si algo impide que el pedido se actualice, la respuesta del proveedor se registra igualmente como **Confirmado** pero el estado del pedido de compra permanece en estado **Revisión externa**.                                                                       |
| El proveedor confirma el pedido. El sistema no está configurado para confirmar automáticamente los pedidos de compra cuando el proveedor confirma. | La respuesta del proveedor se registra como **Confirmado** pero el estado de la OC permanece en estado **Revisión externa**.                                                                                                                                                                                      |
| El proveedor rechaza el pedido.                                                                                     | La respuesta del proveedor se registra como **Rechazado** y el estado de la OC permanece en estado **Revisión externa**. El rechazo se recibe junto con el motivo y una sugerencia para el cambio, como una fecha de entrega alternativa. Se actualiza el pedido de compra y después se envía una nueva versión para confirmación. |

## <a name="changes-to-a-po"></a>Cambios a una OC
Si tiene que cambiar una OC que ya ha sido confirmada, le puede enviar una nueva OC al proveedor mediante el portal de proveedores. El nuevo pedido de compra tendrá un sufijo de versión para indicar que es una versión modificada de un pedido de compra que se comunicó anteriormente. El portal de proveedores permite a los proveedores el seguimiento del historial de cada pedido. La versión confirmada anteriormente del pedido de compra permanecerá en la lista de pedidos de compra confirmados hasta que se haya confirmado el nuevo pedido de compra.  

Al cancelar una OC, el estado se cambia a **Aprobado**. Debe enviar de nuevo la OC al proveedor a través del portal de proveedores de modo que el proveedor pueda confirmar o rechazar la cancelación. Después de que se confirme la cancelación, la OC aparece en la lista de OC confirmadas del proveedor como **Cancelado**.

## <a name="versions-status-transitions-and-change-management"></a>Versiones, transiciones de estado y administración de cambios
Cuando una OC se envía al proveedor, se registra en el sistema como una versión específica del pedido de compra y el estado se cambia de **Aprobado** a **En revisión externa**. Si la OC se cambia después, se crea una versión nueva de la OC y el estado vuelve a **Aprobado** (o **Borrador**, si la administración de cambios está activada).  

La siguiente tabla muestra un ejemplo de los cambios de estado y versión que puede tener una OC.

| Acción                                                   | Estado y versión                                                                                    |
|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| La versión inicial de la OC se crea en Dynamics AX. | El estado es **Aprobado**.                                                                           |
| Se envía la OC al portal del proveedor.                     | Una versión se registra en el portal de proveedores y se cambia el estado a **Revisión externa**.    |
| Tiene que realizar algunos cambios que pide el proveedor.  | El estado se cambia a **Aprobado**.                                                            |
| Envíe la nueva versión de la OC al portal de proveedores. | Una nueva versión se registra en el portal de proveedores y se cambia el estado a **Revisión externa**. |
| El proveedor aprueba la nueva versión de la OC.           | El estado cambia a **Confirmado**.                                                                |

Para ver las versiones de PO que se han enviado al proveedor, y las respuestas de proveedor, haga clic ** diarios ** &gt; ** solicitudes de la confirmación ** de PC.  

Los pedidos que se han enviado al proveedor para una respuesta y que tienen el estado de **Revisión externa** aparecerán en la lista **Pedidos de compra enviados al portal de proveedores, en espera de respuesta** o **Pedidos de compra enviados al portal de proveedores, la respuesta requiere acción**. Cuando modifica un pedido que se ha enviado al proveedor, de modo que el estado se cambia a **Aprobado**, el pedido ya no aparece en estas listas. Para ver si anteriormente se ha realizado una respuesta al pedido del proveedor, haga clic ** diarios ** &gt; ** solicitudes de la confirmación **.  

Los proveedores no tienen que confirmar la OC en el portal de proveedores. También pueden enviar un mensaje de correo electrónico o comunicar la aceptación de una OC a través de otros canales. A continuación puede confirmar el pedido manualmente en Dynamics AX. En este caso, recibirá una advertencia de que se está confirmando el pedido aunque no haya respuesta del proveedor. La OC aparece a continuación en el historial de confirmaciones del portal de proveedores como un pedido confirmado abierto que no tiene ninguna respuesta. Además, el proveedor ya no tiene la opción de confirmar o de rechazar el pedido de compra.  

**Nota:** La versión de la OC que está disponible para otros procesos en Dynamics AX siempre es la última versión, incluso si dicha versión no se ha registrado todavía.

### <a name="change-management"></a>Gestión de cambios

Si ha activado la administración de cambios para una OC, la OC pasa por un flujo de trabajo de aprobación para lograr el estado **Aprobado**. Este proceso no es visible para el proveedor.  

Cuando la administración de cambios está activada para una OC, se registra la versión cuando se aprueba la OC, no cuando la OC se envía al proveedor o se confirmar.  

La siguiente tabla muestra un ejemplo de los cambios de estado y versión que puede tener una OC cuando está activada la gestión de cambios.

| Acción                                                                                                        | Estado y versión                                                                                                                                                                                                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| La versión inicial de la OC se crea en Dynamics AX.                                                      | El estado es **Borrador**.                                                                                                                                                                                                                                                                                                                                                                    |
| La OC se envía al proceso de aprobación. (Esto es un proceso interno en el que el proveedor no está involucrado.) | El estado se cambia de **Borrador** a **En revisión** a **Aprobación** si la OC no se rechaza durante el proceso de aprobación. El pedido de compra aprobado se registra como versión.                                                                                                                                                                                                                     |
| Se envía la OC al portal del proveedor                                                                           | La versión se registra en el portal de proveedores y se cambia el estado a **Revisión externa**.                                                                                                                                                                                                                                                                                        |
| Tiene que realizar algunos cambios que pide el proveedor.                                                       | El estado se vuelve a cambiar a **Borrador**.                                                                                                                                                                                                                                                                                                                                                    |
| La OC se envía al proceso de aprobación de nuevo.                                                            | El estado se cambia de **Borrador** a **En revisión** a **Aprobación** si la OC no se rechaza durante el proceso de aprobación. De manera alternativa, el sistema puede estar configurado de modo que los cambios de campo específicos no necesitan volver a ser aprobados. En este caso, el estado cambia primero a **Borrador** y a continuación se actualizan automáticamente a **Aprobado**. El pedido de compra aprobado se registra como nueva versión. |
| Envíe la nueva versión de la OC al portal de proveedores.                                                      | La nueva versión se registra en el portal de proveedores y se cambia el estado a **Revisión externa**.                                                                                                                                                                                                                                                                                    |
| El proveedor aprueba la nueva versión de la OC.                                                                | El estado se cambia a **Confirmado** automáticamente o cuando reciba la respuesta del proveedor y después confirma la OC.                                                                                                                                                                                                                                                     |
<a name="see-also"></a>Consulte también
--------

[Configuración de la seguridad para los usuarios de la colaboración de proveedor](configure-security-vendor-portal-users.md)

[Espacio de trabajo de facturación de colaboración de proveedor](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace)



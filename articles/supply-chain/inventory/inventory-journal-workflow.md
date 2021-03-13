---
title: Flujos de trabajo de aprobación de diario de inventario
description: Este tema describe cómo puede establecer y usar flujos de trabajo de aprobación de diarios de inventario para registrar diversos tipos de transacciones de inventario físico. Los flujos de trabajo del diario de inventario ayudan a garantizar que solo los diarios de inventario aprobados puedan contabilizarse en las transacciones.
author: sherry-zheng
manager: tfehr
ms.date: 07/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTableWorkflowDropDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-21
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: d9f57d35adac0820d0635ab97a4cb4cefc1d504c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011681"
---
# <a name="inventory-journal-approval-workflows"></a>Flujos de trabajo de aprobación de diario de inventario

[!include [banner](../includes/banner.md)]

En este tema se describe cómo establecer y usar flujos de trabajo de aprobación de inventarios para varios para registrar transacciones de inventario físico de distintos tipos, como el registro de emisiones y recepciones, los movimientos de inventario, listas de materiales (L. MAT.) y la conciliación del inventario físico. Los flujos de trabajo del diario de inventario ayudan a garantizar que solo los diarios de inventario aprobados puedan contabilizarse en las transacciones.

> [!NOTE]
> Los flujos de trabajo de aprobación de diarios de inventario se aplican solo a las transacciones registradas utilizando el módulo de Gestión de inventario. No funcionan con diarios de inventario activados desde el módulo Gestión de almacenes.

## <a name="turn-on-the-inventory-journal-approval-workflows-feature"></a>Active la característica de flujos de trabajo de aprobación de diario de inventario

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo**: *gestión de inventario y almacenes*
- **Feature name:** *Flujo de trabajo de aprobación del diario de inventario*

## <a name="create-your-inventory-journal-approval-workflows"></a>Crear flujos de trabajo de aprobación de diario de inventario

Para configurar esta función, debe crear un flujo de trabajo para cada uno de los tipos de diario de inventario que desea controlar. Debido a que los diferentes tipos de diario de inventario pueden tener diferentes jerarquías de aprobación y pasos de flujo de trabajo, puede configurar flujos de trabajo individuales para cada tipo de diario de inventario.

Los flujos de trabajo admiten el control de versiones, y cada uno tiene un identificador de flujo de trabajo y una versión activa. Puede elegir activar cada nueva versión de flujo de trabajo inmediatamente después de la creación o mantenerla inactiva. Si necesita diferentes flujos de trabajo para el mismo tipo de diario, cree múltiples flujos de trabajo para ese tipo de diario y luego asigne cada uno de ellos a un nombre de diario diferente que use ese tipo.

Para crear flujos de trabajo de aprobación de diario de inventario:

1. Vaya a **Gestión del inventario \> Configuración\> Flujos de trabajo de gestión de inventario**.
1. En el panel Acciones, seleccione **Nuevo**.
1. Elija el tipo de diario de inventario para el que desea configurar un flujo de trabajo:
    - **Diario de recuento de etiquetas de inventario**
    - **Diario de cambio de propiedad de inventario**
    - **Diario de movimientos de inventario**
    - **Diario de transferencia de inventario**
    - **Diario de recuento de inventario**
    - **Diario de L. MAT de inventario**
    - **Diario de ajustes de inventario**

    ![El cuadro de diálogo Crear flujo de trabajo](media/journal-workflow-create-workflow.png "El cuadro de diálogo Crear flujo de trabajo")

1. La aplicación del editor de flujo de trabajo se inicia en su máquina. (Es posible que se le solicite que apruebe esta acción). Úsela para diseñar su flujo de trabajo según sea necesario. Para obtener detalles sobre cómo usar el editor de flujo de trabajo, vea [Resumen del sistema de flujo de trabajo](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).
1. Después de guardar y cerrar la aplicación del editor de flujo de trabajo, debe elegir si desea activar esta versión de flujo de trabajo o mantenerla inactiva.

> [!NOTE]
> Los flujos de trabajo proporcionan control de versiones, lo que significa que puede ver una lista de versiones que ha creado y elegir cuál está activa. Para ver la lista de versiones disponibles y elegir cuál activar, seleccione un flujo de trabajo enumerado en la página **Flujos de trabajo de gestión de inventario**. En el Panel acciones, abra la pestaña **Flujo de trabajo** y seleccione **Versiones**. Solo una versión puede estar activa a la vez para cada identificador de flujo de trabajo.

## <a name="assign-approval-workflows-to-inventory-journal-names"></a>Asignar flujos de trabajo de aprobación para los nombres de diario de inventario

El siguiente paso es asignar un flujo de trabajo de diario de inventario a cada nombre de diario de inventario. Para cada tipo de diario de inventario, puede configurar varios nombres de diario de inventario.

Para asociar un flujo de trabajo de diario de inventario con un nombre de diario de inventario:

1. Vaya a **Gestión del inventario \> Configurar \> Nombres de diarios \> Inventario**.
1. Seleccione el nombre de un diario en la columna de la lista para abrir su página de configuración.
1. En la ficha desplegable **General**, establezca **Aprobación del flujo de trabajo** en **Sí**. Si se le solicita aprobar la acción, seleccione **Sí**.

    ![Asignar un flujo de trabajo a un nombre de diario](media/journal-workflow-journal-name.png "Asignar un flujo de trabajo a un nombre de diario")

1. Abra la lista desplegable **Flujo de trabajo** y seleccione el flujo de trabajo apropiado. La lista muestra cada flujo de trabajo activo que ha creado utilizando la aplicación del editor de flujo de trabajo.

## <a name="create-an-inventory-journal-and-send-it-for-approval"></a>Crear un diario de inventario y envíelo para su aprobación

Después de asociar un nombre de diario de inventario con su flujo de trabajo de aprobación de diario de inventario correspondiente, podrá crear nuevos diarios de inventario que usen ese nombre y luego enviar estos diarios para su aprobación usando ese flujo de trabajo. No podrá publicar el diario de inventario hasta que haya sido aprobado por los aprobadores configurados en el flujo de trabajo.

1. En el panel de navegación, expanda **Gestión del inventario \> Entradas de diario \> Artículos** y luego seleccione un tipo de diario de inventario.
1. Seleccione **Nuevo** para crear un nuevo diario de su tipo seleccionado.
1. El cuadro de diálogo **Crear diario de inventario** se abre. Complete el formulario según sea necesario y luego seleccione **Aceptar** para guardar el diario.
1. Complete el diario según sea necesario.
1. Cuando crea o abre un diario de inventario con un flujo de trabajo de aprobación asociado, el botón **Flujo de trabajo** estará activo en el Panel de acciones. Cuando esté listo para enviar la revista para su aprobación, seleccione el botón **Flujo de trabajo** para abrir un cuadro de diálogo desplegable y luego seleccione **Enviar**. La solicitud de aprobación se dirigirá al aprobador correspondiente, a quien se alertará utilizando el método de notificación configurado para el flujo de trabajo.

    ![Enviar un diario para su aprobación](media/journal-workflow-inventory-journal.png "Enviar un diario para su aprobación")

Para recuperar una solicitud de aprobación, abra el diario relevante, seleccione el botón **Flujo de trabajo** y luego seleccione **Recordar**. Esto restablecerá el flujo de trabajo.

Cuando su diario haya sido aprobado, podrá publicarlo. Para publicar el diario, seleccione **Enviar** desde el Panel de acciones. Si el botón **Enviar** no está activo, el diario aún no ha sido aprobado.

## <a name="respond-to-an-inventory-journal-approval-request"></a>Responder a una solicitud de aprobación del diario de inventario

Si es un aprobador, debería recibir un mensaje cada vez que necesite su aprobación (como se configuró en el flujo de trabajo relevante). Luego puede aprobar o rechazar una solicitud de aprobación de diario haciendo lo siguiente:

1. En el panel de navegación, expanda **Gestión del inventario \> Entradas de diario \> Artículos** y luego seleccione un tipo de diario de inventario.
1. Abra el diario relevante y revíselo.
1. Seleccione el botón **Flujo de trabajo** en el Panel de acciones para abrir un cuadro de diálogo desplegable. Seleccione una de las opciones siguientes:
    - **Aprobar**: para aprobar la solicitud.
    - **Rechazar**: para rechazar la solicitud.
    - **Más \> Solicitar cambio**: para enviar un mensaje al solicitante pidiéndole que cambie algo específico y luego vuelva a enviarlo.
    - **Más \> Delegar**: para delegar la aprobación a otro usuario.
    - **Más \> Recuperar**: para recuperar la solicitud de aprobación (restablece el flujo de trabajo).
    - **Más \> Historial de flujo de trabajo**: para ver el historial de este flujo de trabajo de aprobación hasta ahora.

## <a name="review-the-approval-history"></a>Revisar el historial de aprobación

Al igual que con otros tipos de flujos de trabajo, puede usar la página **Historial de flujo de trabajo** para ver el historial de aprobación del flujo de trabajo de cualquier diario.

Para revisar el historial de flujo de trabajo de un diario:

1. En el panel de navegación, expanda **Gestión del inventario \> Entradas de diario \> Artículos** y luego seleccione un tipo de diario de inventario.
1. Abrir el diario relevante.
1. Seleccione el botón **Flujo de trabajo** en el Panel de acciones para abrir un cuadro de diálogo desplegable. Seleccione **Historial de flujo de trabajo**. Para obtener más información, consulte [Ver historial de flujo de trabajo](../../fin-ops-core/fin-ops/organization-administration/tasks/view-workflow-history.md).

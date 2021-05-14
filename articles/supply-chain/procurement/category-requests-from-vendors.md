---
title: Solicitudes de categoría desde proveedores
description: Este tema describe cómo los proveedores pueden solicitar categorías de compras para su cuenta. También describe el proceso de aprobación que completan los agentes de compras.
author: kamaybac
ms.date: 04/19/2021
ms.topic: article
ms.search.form: VendRequestNewCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: fb3555e6d923fe37479c3204f0b78f7cdf510118
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938543"
---
# <a name="category-requests-from-vendors"></a>Solicitudes de categoría desde proveedores

[!include [banner](../includes/banner.md)]

El proceso de solicitud de categoría permite a los proveedores solicitar que se asocien nuevas categorías de compras con su cuenta. Luego, esas categorías de compras pueden ser utilizadas por los procesos de compras y abastecimiento relacionados. (Para obtener más información, consulte [Visión general de catálogos de compras](procurement-catalogs.md)).

Las solicitudes de categoría las inician los proveedores, en el espacio de trabajo **Informacion del proveedor**. Luego se envían a su agencia para su revisión y aprobación. Las categorías aprobadas se agregan a la lista de categorías de compras para la cuenta del proveedor.

## <a name="turn-on-the-feature-in-your-system"></a>Activar la función en el sistema

Si su sistema aún no incluye la función que se describe en este tema, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la característica *Permitir que los proveedores soliciten categorías de adquisiciones mediante la colaboración de proveedores*.

Una vez activada la función, aún puede agregar manualmente categorías de compras a las cuentas de los proveedores. Para obtener información, consute [Aprobar proveedores para categorías de compras específicas](tasks/approve-vendors-specific-procurement-categories.md).

## <a name="vendor-collaboration-requirements"></a>Requisitos de colaboración de proveedores

Antes de que un proveedor pueda interactuar con las solicitudes de categoría, debe configurarse para la colaboración de proveedores.

El proveedor debe tener al menos un usuario de colaboración de proveedor. Solo los usuarios de proveedores que tienen uno o ambos de los siguientes roles de seguridad pueden crear y enviar solicitudes de categoría:

- Contacto del proveedor (externo)
- Administrador de proveedor (externo)

Para obtener más información, consulte [Configuar y mantener la colaboración del proveedor](set-up-maintain-vendor-collaboration.md).

## <a name="set-up-the-vendor-category-request-workflow"></a>Configurar el flujo de trabajo de solicitud de categoría de proveedor

El flujo de trabajo *Solicitud de categoría de proveedor* debe configurarse en los flujos de trabajo de adquisiciones y abastecimiento. Los proveedores enviarán solicitudes de nuevas categorías que puede revisar y aprobar. Las categorías de compras solicitadas se agregan a una cuenta de proveedor después de aprobarse una solicitud de categoría.

El siguiente ejemplo muestra cómo configurar un simple flujo de trabajo *Solicitud de categoría de proveedor* que tiene un único aprobador. Debe revisar sus procesos internos para determinar la configuración de flujo de trabajo adecuada para su agencia.

1. Vaya a **Adquisición y abastecimiento \> Configuración \> Flujos de trabajo de adquisición y abastecimiento**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo, seleccione **Flujo de trabajo de solicitud de categoría de proveedor** para abrir el editor de flujo de trabajo.
1. Inicie sesión en el editor de flujo de trabajo.
1. En el panel Acciones, seleccione **Propiedades**.
1. En la página **Propiedades** del flujo de trabajo, en el campo **Instrucciones de envío**, introduzca el texto de la instrucción. Las instrucciones serán visibles para los proveedores cuando envíen una solicitud de categoría.
1. Cierre la página **Propiedades**.
1. Arrastre el elemento de flujo de trabajo **Aprobar solicitud de nueva categoría** al lienzo.
1. Arrastre un enlace desde el elemento de flujo de trabajo **Comenzar** al elemento de flujo de trabajo **Aprobar solicitud de nueva categoría**.
1. Arrastre un enlace desde el elemento de flujo de trabajo **Aprobar solicitud de nueva categoría** al elemento de flujo de trabajo **Final**.
1. Toque dos veces (o haga doble clic) en el elemento de flujo de trabajo **Aprobar solicitud de nueva categoría**.
1. Seleccione y mantenga (o haga clic con el botón derecho) el elemento de flujo de trabajo **Paso 1** y, a continuación, seleccione **Propiedades**.
1. En la página **Propiedades** del elemento de flujo de trabajo, en el campo **Asunto del elemento de trabajo**, introduzca el texto del asunto. Este texto se mostrará como el valor del campo **Asunto** de la página **Elementos de trabajo asignados a mí**.
1. En el campo **Instrucciones del elemento de trabajo**, introduzca el texto de instrucciones. Las instrucciones serán visibles para los aprobadores cuando seleccionen **Flujo de trabajo** en el panel de acciones de una solicitud de categoría.
1. En el panel izquierdo, seleccione **Asignación**.
1. En la pestaña **Tipo de asignación**, seleccione **Asignar usuarios a este elemento de flujo de trabajo** en *Usuario*.
1. En la pestaña **Usuario**, en la lista **Usuarios disponibles**, seleccione un aprobador. Por ejemplo, seleccione un usuario en el departamento de Compras.
1. Seleccione el botón de flecha derecha (**\>**) para mover el aprobador a la lista **Usuarios seleccionados**.
1. Cierre la página **Propiedades**.
1. Seleccione **Guardar y cerrar**.
1. En el campo **Notas de la versión**, introduzca notas sobre el flujo de trabajo.
1. Seleccione **Aceptar** para guardar el flujo de trabajo.
1. Si está listo para comenzar a probar el flujo de trabajo, seleccione **Activar la nueva versión**. De lo contrario, seleccione **No activar la nueva versión**.
1. Seleccione **Aceptar** para completar e flujo de trabajo.

> [!TIP]
> Si su agencia no requiere la aprobación de las solicitudes de categoría, debe configurar el flujo de trabajo para la aprobación automática.

Para obtener más información sobre cómo configurar los flujos de trabajo, consulte [Visión general del sistema de flujos de trabajo](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

## <a name="create-and-submit-a-category-request"></a>Crear y enviar una solicitud de categoría

Esta sección describe cómo los proveedores pueden utilizar el espacio de trabajo **Informacion del proveedor** para crear, editar, ver y enviar solicitudes de categorías.

### <a name="start-a-new-request"></a>Iniciar una nueva solicitud

Para iniciar una nueva solicitud de categoría, siga estos pasos.

1. En el espacio de trabajo **Informacion del proveedor**, seleccione el mosaico **Solicitudes de categoría**.
1. En la página **Solicitudes de categoría**, en el panel de acciones, seleccione **Solicitud de nueva categoría**.
1. En el cuadro de diálogo **Solicitud de nueva categoría** busque la categoría que desea solicitar navegando por el árbol y/o usando el filtro en la parte superior de la lista. Seleccione la casilla para cada categoría relevante.

    Tenga en cuenta los aspectos siguientes:

    - Las categorías que están actualmente activas en su cuenta de proveedor se muestran como seleccionadas y no se pueden eliminar.
    - Puede solicitar varias categorías de compras en una sola solicitud de categoría.

1. Seleccione **Aceptar** para crear la solicitud en borrador.

    La nueva solicitud de borrador ahora aparece en la página **Solicitudes de categoría**.

1. Abra el nuevo borrador de la solicitud para revisarlo y editarlo según sea necesario.

    - Para ver la lista de categorías que se incluyen actualmente en la solicitud, seleccione la ficha desplegable **Categorías solicitadas**.
    - Para ver sus categorías activas, abra el cuadro informativo **Categorías activas** del lado derecho de la página.
    - Para agregar una categoría a la solicitud, seleccione **Agregar** en la barra de herramientas de la ficha desplegable **Categorías solicitadas**.
    - Para eliminar una categoría de la solicitud, seleccione la categoría en la ficha desplegable **Categorías solicitadas** y luego seleccione **Eliminar** en la barra de herramientas.
    - Para adjuntar un documento a la solicitud, seleccione **Archivos adjuntos** en el panel de acciones. Los documentos adjuntos estarán disponibles para los aprobadores cuando revisen la solicitud de categoría.
    - Para quitar un documento adjunto de la solicitud, seleccione **Archivos adjuntos** en el panel de acciones. Seleccione el documento a quitar y luego seleccione **Eliminar** en el panel de acciones.

1. Si está listo para enviar la solicitud, seleccione **Enviar** en el panel de acciones. De lo contrario, simplemente cierre la página y omita los pasos restantes de este procedimiento. Luego puede volver a la solicitud más tarde.
1. Lea las instrucciones de envío que aparezcan y luego seleccione **Enviar**.
1. En el cuadro **Comentario**, especifique información adicional necesaria. Luego seleccione **Enviar** para completar la solicitud.

### <a name="edit-a-draft-or-recalled-request"></a>Editar una solicitud en borrador o recuperada

Para editar un borrador o una solicitud de categoría recuperada, siga estos pasos.

1. En el espacio de trabajo **Informacion del proveedor**, seleccione el mosaico **Solicitudes de categoría**.
1. Seleccione el borrador o la solicitud recuperada para abrirlos.
1. Edite la solicitud según sea necesario y, a continuación, ciérrela o envíela como se describe en el procedimiento anterior.

### <a name="submit-a-draft-or-recalled-request"></a>Enviar una solicitud en borrador o recuperada

Para enviar un borrador o una solicitud de categoría recuperada, siga estos pasos.

1. En el espacio de trabajo **Informacion del proveedor**, seleccione el mosaico **Solicitudes de categoría**.
1. Seleccione el borrador o la solicitud recuperada que desea enviar.
1. En el panel de acciones, seleccione **Enviar**.
1. Lea las instrucciones de envío que aparezcan y luego seleccione **Enviar**.
1. En el cuadro **Comentario**, especifique información adicional necesaria. Luego seleccione **Enviar** para completar la solicitud.

    El estado de la solicitud de categoría cambia a uno de los siguientes valores:

    - _Revisión pendiente_: la solicitud se encuentra en el flujo de trabajo.
    - _Aprobación pendiente_: se requiere aprobación.

### <a name="recall-a-submitted-request-that-hasnt-yet-been-approved"></a>Recuperar una solicitud enviada que aún no ha sido aprobada

Para recuperar una solicitud de categoría que se envió pero aún no se aprobó, siga estos pasos.

1. En el espacio de trabajo **Informacion del proveedor**, seleccione el mosaico **Solicitudes de categoría**.
1. Seleccione la solicitud pendiente que desea recuperar.
1. En el panel de acciones, haga clic en **Recuperar**.
1. En el cuadro **Introducir un comentario**, especifique cualquier información adicional necesaria. Luego seleccione **Enviar** para completar la solicitud.

    El estado de la solicitud de categoría se cambia a _Cancelada_. La solicitud permanecerá en este estado hasta que la elimine o la vuelva a enviar.

### <a name="delete-a-draft-or-recalled-request"></a>Eiminar una solicitud en borrador o recuperada

Para eliminar un borrador o una solicitud de categoría recuperada, siga estos pasos.

1. En el espacio de trabajo **Informacion del proveedor**, seleccione el mosaico **Solicitudes de categoría**.
1. Seleccione el borrador o la solicitud recuperada que desea eliminar.
1. En el panel de acciones, seleccione **Eliminar**.
1. Seleccione **Sí** para confirmar el borrado.

### <a name="view-completed-requests"></a>Ver solicitudes completadas

Para ver las solicitudes completadas, abra el espacio de trabajo **Informacion del proveedor** y seleccione el mosaico **Solicitudes de categoría**. Las solicitudes de categoría que se hayan completado tendrán uno de los siguientes estados:

- _Aprobada_: la solicitud se ha aprobado. Para ver las categorías recién agregadas, vuelva al espacio de trabajo **Informacion del proveedor**, abra la lista desplegable **Más detalles** en el panel izquierdo y luego seleccione **Categorías**.
- _Rechazada_: la solicitud se ha rechazado. Puede crear una nueva solicitud de categoría según sea necesario.

## <a name="review-category-requests"></a>Revisar las solicitudes de categoría

Esta sección explica cómo aprobar, rechazar y delegar las solicitudes de categorías que envían los proveedores y cómo ver las solicitudes completadas. Estas acciones de flujo de trabajo son para toda la solicitud de categoría.

### <a name="view-category-requests"></a>Ver solicitudes de categoría

Para ver las solicitudes de categoría, siga estos pasos.

1. Vaya a **Adquisiciones y abastecimiento \> Proveedores \> Solicitudes de colaboración de proveedores \> Solicitudes de categoría**.

    Aparece la página **Solicitudes de categoría**. La vista de página predeterminada muestra las solicitudes de categoría que tienen un estado de *Acción pendiente*.

1. Para ver todas las solicitudes, seleccione *Todas* en el campo **Mostrar solicitudes**.
1. Abra una solicitud para revisarla y editarla según sea necesario.

    - Para ver la lista de categorías que se incluyen actualmente en la solicitud, seleccione la ficha desplegable **Categorías solicitadas**.
    - Para ver las categorías activas, abra el cuadro informativo **Categorías activas** del lado derecho de la página.
    - Si se presentaron documentos, el botón **Archivos adjuntos** (clip de papel) del panel de acciones muestra un recuento de los documentos adjuntos. Para ver los documentos adjuntos, seleccione el botón **Archivos adjuntos**. Luego seleccione el documento a ver y elija **Abrir** para verlo.
    - Para adjuntar un documento a la solicitud, seleccione **Archivos adjuntos** en el panel de acciones. Los documentos adjuntos estarán disponibles para los aprobadores cuando revisen la solicitud de categoría.
    - Para quitar un documento adjunto de la solicitud, seleccione **Archivos adjuntos** en el panel de acciones. Seleccione el documento a quitar y luego seleccione **Eliminar** en el panel de acciones.
    - En el panel de acciones, seleccione **Flujo de trabajo** para ver el historial de flujos de trabajo. En las opciones de flujo de trabajo, seleccione **Más** y luego **Historial de flujos de trabajo**. Aparece la página **Historial de flujos de trabajo**.

### <a name="approve-a-pending-category-request"></a>Aprobar una solicitud de categoría pendiente

Para aprobar una solicitud de categoría pendiente, siga estos pasos.

1. Vaya a **Adquisiciones y abastecimiento \> Proveedores \> Solicitudes de colaboración de proveedores \> Solicitudes de categoría**.
1. Seleccione la solicitud pendiente a aprobar.
1. Revise la solicitud de categoría.
1. Opcional: en la ficha desplegable **General**, en el campo **Código de razón**, seleccione un código de razón. Entonces, en el campo **Comentario de la razón**, introduzca un comentario sobre el código de razón.
1. En el panel de acciones, seleccione **Flujo de trabajo**.
1. En las opciones de flujo de trabajo, seleccione **Aprobar**.
1. En el campo **Comentario**, especifique cualquier información adicional necesaria. Luego seleccione **Aprobar** para completar la solicitud.

    El estado de la solicitud de categoría cambia a _Aprobado_ y las categorías de compras se agregan a la cuenta de proveedor.

### <a name="reject-a-pending-category-request"></a>Rechazar una solicitud de categoría pendiente

Para rechazar una solicitud de categoría pendiente, siga estos pasos.

1. Vaya a **Adquisiciones y abastecimiento \> Proveedores \> Solicitudes de colaboración de proveedores \> Solicitudes de categoría**.
1. Seleccione la solicitud pendiente a rechazar.
1. Revise la solicitud de categoría.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **General**, en el campo **Código de razón**, seleccione un código de razón. Entonces, en el campo **Comentario de la razón**, introduzca un comentario sobre el código de razón.
1. En el panel Acciones, seleccione **Guardar**.
1. En el panel de acciones, seleccione **Flujo de trabajo**.
1. En las opciones de flujo de trabajo, seleccione **Más** y luego **Rechazar**.
1. En el campo **Comentario**, especifique cualquier información adicional necesaria. Luego seleccione **Rechazar** para completar la solicitud.

    El estado de la solicitud de categoría se cambia a _Rechazada_. En este punto, el proveedor puede crear una nueva solicitud de categoría según sea necesario.

### <a name="delegate-a-pending-category-request"></a>Delegar una solicitud de categoría pendiente

Para delegar una solicitud de categoría pendiente a otro usuario, siga estos pasos.

1. Vaya a **Adquisiciones y abastecimiento \> Proveedores \> Solicitudes de colaboración de proveedores \> Solicitudes de categoría**.
1. Seleccione la solicitud pendiente que desea aprobar.
1. En el panel de acciones, seleccione **Flujo de trabajo**.
1. En las opciones de flujo de trabajo, seleccione **Más** y luego **Delegar**.
1. En el campo **Usuario**, seleccione el usuario al que asignar la solicitud de categoría para su revisión.
1. En el campo **Comentario**, especifique cualquier información adicional necesaria.
1. Seleccione **Delegar** para completar la delegación. El usuario seleccionado ahora puede revisar la solicitud de categoría.

### <a name="view-procurement-categories-for-a-vendor"></a>Ver categorías de compras de un proveedor

Para ver las categorías de compras para un proveedor después de aprobarse una solicitud de categoría, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento \> Proveedores \> Todos los proveedores**.
1. En la página **Todos los proveedores**, seleccione el proveedor para el que desea ver las categorías de compras.
1. En el panel de acciones, abra la pestaña **General** y, desde el grupo **Configurar**, seleccione **Categorías**.

    Aparecerá la página **Categorías**. La ficha desplegable **Compra** muestra las categorías de compras que se agregaron a través de la solicitud de categoría.

1. En la ficha desplegable **Compra**, puede realizar cambios si es necesario. Por ejemplo, puede configurar el campo **Estado de categoría de proveedor** en _Preferido_.

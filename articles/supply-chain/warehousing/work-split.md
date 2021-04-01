---
title: División del trabajo
description: Este tema proporciona información sobre la funcionalidad de división de trabajo. Esta funcionalidad le permite dividir órdenes de trabajo grandes en varias órdenes de trabajo más pequeñas que luego puede asignar a varios trabajadores del almacén. De esta forma, el mismo trabajo puede ser recogido simultáneamente por varios trabajadores del almacén.
author: mirzaab
manager: tfehr
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6dbf0f6dd0c691db74eaad2174d8f9849b4cb26a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245091"
---
# <a name="work-split"></a>División del trabajo

La funcionalidad de división del trabajo le permite dividir las ID de trabajo grandes (es decir, las órdenes de trabajo que tienen varias líneas) en varias ID de trabajo más pequeñas que luego puede asignar a varios trabajadores del almacén. De esta forma, el mismo número de creación de trabajo puede ser recogido simultáneamente por varios trabajadores del almacén.

> [!IMPORTANT]
> Solo puede dividir las órdenes de trabajo que tienen un estado *Abierto* o *En progreso*.

## <a name="turn-on-the-work-split-functionality"></a>Activar la función de división del trabajo

Antes de poder utilizar la función de división del trabajo, debe activar la función y su función de requisito previo en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de las funciones y activarlas si es necesario.

Primero, active el requisito previo de la función *Bloqueo de trabajo en toda la organización*, si aún no está activada. En el espacio de trabajo **Administración de características**, esta característica aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Bloqueo de trabajo en toda la organización*

> [!NOTE]
> Cuando esta función está activada, una actualización de datos se aplica automáticamente después de que la función se activa en todas las entidades legales.

A continuación, active la característica *Trabajo dividido*, que se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de la función:** *Trabajo dividido*

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a>Mejoras en los detalles del trabajo y todas las páginas de trabajo

La función *Trabajo dividido* añade los siguientes dos botones a la pestña **Trabajo** en el Panel de acciones de las páginas **Detalles del trabajo** y **Todo el trabajo**:

- **Dividir trabajo** – Dividir el identificador de trabajo actual en varios Id. más pequeños de trabajo para que se puedan procesar por trabajadores independientes.
- **Cancelar sesión de trabajo dividido** - Cancelar la sesión de trabajo dividido y hacer que el trabajo esté disponible para su procesamiento.

![Botones dividir trabajo y cancelar trabajo dividido sesión](media/Work_split_buttons.png "Botones dividir trabajo y cancelar trabajo dividido sesión")

> [!IMPORTANT]
> El botón **Trabajo dividido** no estará disponible si se cumple alguna de las siguientes condiciones:
>
> - El estado del trabajo es algo diferente a *Abierto* o *En progreso*.
> - Un ID de contenedor está asociado con el ID de trabajo. (Un contenedor no se puede dividir sistemáticamente porque requiere acciones físicas).
> - El trabajo está asociado a un clúster.
> - El tipo de orden de trabajo es diferente a uno de los siguientes tipos:
>
>    - Pedidos de ventas
>    - Picking de materia prima
>    - Emisión de transferencia
>
> - Actualmente, otro usuario está dividiendo el trabajo. Si intenta abrir la página de división para un trabajo que ya está siendo dividido por otro usuario, recibirá el siguiente mensaje de error: "El trabajo con ID \#\#\#\# actualmente se está dividiendo. Vuelva a intentarlo en unos minutos. Si continúa recibiendo este mensaje, comuníquese con un supervisor ".

Una nueva razón para bloquear el trabajo, *Trabajo dividido*, indica cuando el ID de trabajo está en proceso de ser dividido. Se muestra tanto en la página **Trabajo dividido** como en la aplicación del almacén si un usuario intenta ejecutar el trabajo. Cuando se utilizan motivos de bloqueo, el nombre del campo **Ola bloqueada** del ID de trabajo se cambia a **Bloqueado**.

## <a name="initiate-a-work-split"></a>Iniciar una división de trabajo

La función agrega una nueva página **Trabajo dividido** que permite a los usuarios dividir las líneas de trabajo de la identificación del trabajo. Cuando la página se abre por primera vez, muestra líneas que tienen un estado de trabajo *Abierto* y que están disponibles para dividirse. En el panel de acciones, seleccione **Trabajo dividido** para procesar la obra seleccionada.

Para dividir el trabajo, siga estos pasos.

1. Abra una de las páginas de trabajo siguientes:

    - **Detalles de trabajo** (**Gestión de almacenes \> Trabajo \> Detalles de trabajo**)
    - **Todo el trabajo** (**Gestión de almacenes \> Trabajo \> Todo el trabajo**)

1. En la cuadrícula, seleccione una ID de trabajo para dividir. El campo **Tipo de orden de trabajo** debe establecerse en uno de los siguientes valores:

    - Pedidos de ventas
    - Picking de materia prima
    - Emisión de transferencia

1. En el panel de acciones, en la pestaña **Trabajo**, en el grupo **Trabajo**, seleccione **Trabajo dividido**.

    La página **Trabajo dividido** aparece la página y muestra las líneas de trabajo que están abiertas y disponibles para dividirse. De forma predeterminada, solo se muestran las líneas de trabajo disponibles. Para ver todas las líneas para el ID de trabajo (por ejemplo, líneas que tienen un tipo de trabajo de *Ubicación*), seleccione la casilla **Mostrar todas las líneas** sobre la cuadrícula.

    Se muestra el siguiente mensaje: "Los usuarios no pueden procesar líneas del trabajo hasta que termine de dividir y cierre esta página".

    El campo **Motivo de bloqueo del trabajo** para el trabajo actual se establecerá en *Trabajo dividido* y el trabajo se bloqueará.

    ![Razón de bloqueo](media/Blocking_reason.png "Razón de bloqueo")

1. Seleccione las líneas para eliminar de la identificación de trabajo actual y agregar a una nueva identificación de trabajo. Se producen los eventos siguientes:

    - Cuando divide el trabajo, la línea o líneas seleccionadas del ID de trabajo original se cancelan y luego se copian en un nuevo ID de trabajo.
    - Se conservan la estructura de la plantilla de trabajo existente y la ubicación de la opción put (y también los pares pick / put futuros). Los valores de los siguientes campos de ID de trabajo se copian del trabajo original al nuevo trabajo:

        - Id. de la carga
        - Id. del envío
        - Tipo de orden de trabajo
        - Número de pedido
        - Sitio
        - Almacén
        - Prioridad de trabajo
        - Id. del grupo de trabajo
        - Id. de oleada
        - Número de creación de trabajo

    - Los siguientes campos no se copian en el nuevo ID de trabajo:

        - **ID de trabajo** - Se genera un nuevo ID de trabajo a partir de la secuencia numérica adecuada.
        - **Situación laboral** - Este campo se establece en *Abierto*.
        - **Bloqueado por** - Este campo se establece inicialmente en blanco.
        - **ID de matrícula de destino** - Este campo se deja en blanco.
        - **Fecha y hora de creación** - Este campo se establece en la fecha y hora actuales.
        - **Ola bloqueada/congelada** - Este campo se vuelve a calcular para el ID de trabajo original y el nuevo ID de trabajo.

1. En el panel de acciones, seleccione **Trabajo dividido**.

Mientras se divide el trabajo, se muestra el siguiente mensaje: "Operación de procesamiento - Trabajo dividido". Mientras este mensaje está visible, puede cancelar la operación seleccionando **Cancelar** en el cuadro de mensaje.

Si la casilla **Mostrar todas las líneas** está desactivada, la línea que se separó y canceló ya no aparecerá en la cuadrícula. Si la casilla de verificación está seleccionada, debería ver que el valor del campo **Situación laboral** de esa línea ha cambiado a *Cancelado*.

Se muestra la siguiente notificación para indicar que se ha creado el nuevo ID de trabajo: "El trabajo \#\#\#\# se ha creado separándolo del trabajo original \#\#\#\#".

Otras líneas de trabajo del ID de trabajo original (como líneas de *Ubicación*) se ajustarán según sea necesario para reflejar las líneas de trabajo que se han cancelado. Por ejemplo, si el ID de trabajo original tenía una línea de *Ubicación* para una cantidad de 15 y se cancelaron líneas de *Selección* que tienen una cantidad total de 10, la nueva cantidad de *Ubicación* en el ID de trabajo original ahora será 5.

El nuevo trabajo no se asignará inmediatamente a ningún usuario. Sin embargo, ahora puede asignarlo a un usuario, según sea necesario, utilizando la funcionalidad estándar de la página **Detalles del trabajo**.

> [!IMPORTANT]
> Puede dividir solo las ID de trabajo que contengan dos o más líneas de trabajo disponibles. Si selecciona **Trabajo dividido** cuando solo hay una línea de trabajo, recibirá el siguiente mensaje de error: "Al menos una línea de trabajo debe permanecer en el trabajo inicial". En este caso, no se producirá ninguna división.

## <a name="finish-a-work-split"></a>Finalizar una división de trabajo

Para terminar de dividir el trabajo, debe eliminarse el motivo de bloqueo de *Trabajo dividido*. Hay dos maneras para completar este paso:

- El usuario que está dividiendo el trabajo cierra la página **Trabajo dividido** seleccionando el botón **Cerrar** (**X**) en la esquina superior derecha. Cuando se cierra la página, se eliminará el motivo de bloqueo de *Trabajo dividido*. Se volverá a calcular el estado de *Bloqueo* de este trabajo y, si no quedan razones de bloqueo para este trabajo, se desbloqueará el trabajo.
- Cualquier usuario abre el ID de trabajo y selecciona el botón **Cancelar sesión de trabajo dividido** en el panel de acciones. El motivo de bloqueo de *Trabajo dividido* se eliminará y se volverá a calcular el estado *Bloqueado* de este trabajo, al igual que cuando se cierra la página **Trabajo dividido**.

Después de que se elimina la razón de bloqueo de *Trabajo dividido*, el trabajo se puede ejecutar en el dispositivo móvil, siempre que el estado **Bloqueado** esté configurado en *No* en la identificación del trabajo.

## <a name="user-blocking-on-the-warehouse-app"></a>Bloqueo de usuarios en la aplicación del almacén

Si intenta utilizar la aplicación del almacén para ejecutar el trabajo de picking con un ID de trabajo que se está dividiendo, recibirá el siguiente mensaje de error: "El trabajo con ID \#\#\#\# se está dividiendo actualmente". Si recibe este mensaje, seleccione **Cancelar**. Luego puede continuar procesando otro trabajo.

## <a name="other-blocked-operations"></a>Otras operaciones bloqueadas

Cualquier operación que modifique líneas de trabajo, transacciones de inventario de trabajo o enlaces de reabastecimiento que estén relacionados con el trabajo que se está dividiendo fallará y se mostrará el siguiente mensaje de error: "El trabajo con ID \#\#\#\# se está dividiendo actualmente".


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
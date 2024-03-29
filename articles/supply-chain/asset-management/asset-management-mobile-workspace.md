---
title: Usar el área de trabajo móvil de gestión de activos
description: Este artículo proporciona información acerca del área de trabajo móvil de Administración de activos.
author: johanhoffmann
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: 8f215d5f6758f222a9dc6b382b172009836547ec
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067013"
---
# <a name="use-the-asset-management-mobile-workspace"></a>Usar el área de trabajo móvil de gestión de activos

[!include [banner](../../includes/banner.md)]
[!include [mobile app deprecated](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Este artículo proporciona información acerca del área de trabajo móvil de **Administración de activos**. Este espacio de trabajo permite a los usuarios ver y crear solicitudes de mantenimiento y pedidos de trabajo. Los usuarios también pueden ver los trabajos de pedidos de trabajo asignadas en una vista de calendario o de lista. Los activos y ubicaciones funcionales también se pueden ver y buscar.

## <a name="overview"></a>Visión general

Administración de activos es un módulo avanzado para gestionar activos y trabajos de pedidos de trabajo en Dynamics 365 Supply Chain Management. El área de trabajo móvil **Administración de activos** permite a los usuarios ver rápidamente trabajos asignados del pedido de trabajo en el dispositivo móvil de su elección. Los usuarios también pueden crear y gestionar solicitudes de mantenimiento, actualizar estados del ciclo de vida y ver detalles de la ubicación técnica y los activos mediante el dispositivo móvil.

En concreto, el área de trabajo móvil **Gestión de activos** permite a los usuarios realizar las tareas siguientes:

- Crear, ver, y editar solicitudes de mantenimiento, realizar una foto o asociar una imagen existente a la solicitud de mantenimiento, cambiar el estado de ciclo de vida de la solicitud de mantenimiento. 
- Crear, ver, y editar pedidos de trabajo, realizar una foto o asociar una imagen existente al pedido de trabajo , cambiar el estado de ciclo de vida del pedido de trabajo, ver trabajos de pedidos de trabajo.
- Ver trabajos de pedidos de trabajo asignadas en una vista de calendario.
- Crear, ver, y editar trabajo del pedido de trabajo, actualizara contadores de activos, ver listas de comprobación de mantenimiento, ver y editar las notas de trabajo del pedido de trabajo, ver las herramientas necesarias para el trabajo del pedido de trabajo.
- Ver o buscar un activo específico o una ubicación técnica.

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda usar el área de trabajo móvil de **Administración de activos**, su administrador debe configurar las cuentas de usuario y trabajador requeridas, y publicar el área de trabajo. Para obtener más información, consulte [Configurar el área de trabajo móvil de Administración de activos](set-up-asset-management-mobile.md).

## <a name="download-and-install-the-mobile-app"></a>Descargar e instalar la aplicación móvil

Descargar e instalar la aplicación móvil de finanzas y operaciones (Dynamics 365):

- [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Iniciar sesión en la aplicación móvil

1. Inicie la aplicación en su dispositivo móvil.

1. Escriba la URL de Dynamics 365.

1. La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.

1. Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.

    ![Seleccionar un espacio de trabajo.](media/am-mobile-01.png "Seleccionar un espacio de trabajo")

## <a name="view-assigned-work-order-jobs-in-calendar-view"></a>Ver trabajos de pedidos de trabajo asignados en una vista de calendario

1. En su dispositivo móvil, abra el área de trabajo **Gestión de activos**.

1. Seleccione **Mi calendario de trabajos del pedido de trabajo**.

1. Seleccione la fecha para la que desea ver trabajos del pedido de trabajo. En la lista verá el identificador del activo y el identificador de la ubicación técnica de cada trabajo del pedido de trabajo.

1. Seleccione un trabajo del pedido de trabajo en la lista para ver los detalles de trabajo: detalles de la ubicación técnica y los activos, así como otros vínculos de navegación para ver **Datos adjuntos**, **Listas de comprobación**, **Herramientas**, **Contadores de activos**, **Notas**, **Diarios**.

    ![Ver trabajos de pedidos de trabajo asignados en una vista de calendario.](media/am-mobile-02.png "Ver trabajos de pedidos de trabajo asignados en una vista de calendario")

## <a name="create-a-work-order-job"></a>Crear un trabajo de un pedido de trabajo

1. En su dispositivo móvil, abra el área de trabajo **Gestión de activos**.

1. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

1. Seleccione el pedido de trabajo para el que desea crear un nuevo trabajo del pedido de trabajo.

1. Seleccione el botón **Agregar línea**.

1. Seleccione el **Activo** para el que desea crear un nuevo trabajo del pedido de trabajo.

1. Seleccione **Tipo de trabajo de mantenimiento**, **Variante del tipo de trabajo de mantenimiento** y **Comercio**.

1. Seleccione **Listo**.

    ![La pantalla Agregar línea.](media/am-mobile-03.png "La pantalla Agregar línea")


## <a name="add-attachment-to-a-work-order-job"></a>Agregar datos adjuntos a un trabajo de pedido de trabajo

1. En su dispositivo móvil, abra el área de trabajo **Gestión de activos**.

1. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

1. Seleccione el pedido de trabajo > trabajo del pedido de trabajo al que desea agregar datos adjuntos.
    - Como alternativa, también puede seleccionar **Mi calendario de los trabajos del pedido de trabajo** o **Mi lista de trabajos del pedido de trabajo** en la página principal para navegar a la página **Detalles del trabajo del pedido de trabajo**.

1. Seleccione **Datos adjuntos** en la página **Detalles del trabajo del pedido de trabajo**.

1. Se verán los datos adjuntos existentes en el trabajo del pedido de trabajo. Seleccione **Agregar datos adjuntos**.

1. Especifique el **Nombre** y las **Notas** para los datos adjuntos.

1. Seleccione **Elegir imagen** para seleccionar una foto de la galería móvil, o **Tomar foto** para tomar una foto.

1. Seleccione **Listo**.

    ![Ver y agregar archivos adjuntos para un trabajo de un pedido de trabajo.](media/am-mobile-04.png "Ver y agregar archivos adjuntos para un trabajo de un pedido de trabajo")

## <a name="view-maintenance-checklist-on-a-work-order-job"></a>Ver la lista de comprobación de mantenimiento de un trabajo de un pedido de trabajo

1. En su dispositivo móvil, abra el área de trabajo **Gestión de activos**.

1. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

1. Seleccione el pedido de trabajo  trabajo de pedido de trabajo para el que desea ver las listas de comprobación.
    - Como alternativa, también puede seleccionar **Mi calendario de los trabajos del pedido de trabajo** o **Mi lista de trabajos del pedido de trabajo** en la página principal para navegar a la página **Detalles del trabajo del pedido de trabajo**.

1. Seleccione **Listas de comprobación** en la página **Detalles del trabajo del pedido de trabajo**.

1. Se verá una lista de líneas de la lista de comprobación relacionadas con el trabajo del pedido de trabajo. Seleccione una línea de la lista de comprobación para ver **Instrucciones** y agregar **Notas**.

1. Seleccione el botón Atrás (**<**) para volver a la página anterior.

    ![Lista de comprobación de mantenimiento y detalles de la línea.](media/am-mobile-05.png "Lista de comprobación de mantenimiento y detalles de la línea")

## <a name="view-and-update-asset-counters-on-a-work-order-job"></a>Ver y actualizar contadores de activos en un trabajo de pedidos de trabajo

1. En su dispositivo móvil, abra el área de trabajo **Gestión de activos**.

1. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

1. Seleccione el pedido de trabajo  trabajo de pedido de trabajo para el que desea ver los contadores de activos.
    - Como alternativa, también puede seleccionar **Mi calendario de los trabajos del pedido de trabajo** o **Mi lista de trabajos del pedido de trabajo** en la página principal para navegar a la página **Detalles del trabajo del pedido de trabajo**.

1. Seleccione **Contadores de activos** en la página **Detalles del trabajo del pedido de trabajo**.

1. Se verá una lista de contadores de activos relacionados con el trabajo del pedido de trabajo. Seleccione el icono de lápiz en una línea del contador de activos para actualizar el valor de un contador.

1. Introduzca un nuevo valor de contador y seleccione **Listo**.

    ![Ver y actualizar los contadores de activos.](media/am-mobile-06.png "Ver y actualizar los contadores de activos")

## <a name="register-consumption-on-a-work-order-job"></a>Registrar el consumo en un trabajo de pedido de trabajo

1. En su dispositivo móvil, abra el área de trabajo **Gestión de activos**.

1. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

1. Seleccione el pedido de trabajo  trabajo de pedido de trabajo para el que desea agregar registros de consumo.
    - Como alternativa, también puede seleccionar **Mi calendario de los trabajos del pedido de trabajo** o **Mi lista de trabajos del pedido de trabajo** en la página principal para navegar a la página **Detalles del trabajo del pedido de trabajo**.

1. Seleccione **Diarios** en la página **Detalles del trabajo del pedido de trabajo**.

1. Seleccione **Agregar horas** para crear registros de horas de trabajo.
    1. Seleccionar la **categoría** en la búsqueda.
    1. En el campo **Horas**, especifique el número de horas de trabajo gastadas en el trabajo del pedido de trabajo.
    1. Seleccione la **propiedad del línea** adecuada.
    1. Seleccione **Listo**.

1. Seleccione **Agregar artículos** para crear registros de artículos.
    1. Seleccione el **Número de artículo** en la búsqueda.
    1. Seleccione el **Sitio** en la búsqueda.
    1. Indique la **cantidad** de artículos consumidos.
    1. Seleccione **Listo**.

1. Seleccione **Agregar gasto** para crear registros de gastos.
    1. Seleccionar la **categoría** en la búsqueda.
    1. Escriba la cantidad para el registro de gasto.
    1. Seleccione la **divisa de ventas** en la búsqueda.
    1. Escriba el **Precio de coste** para el registro de gasto.
    1. Seleccione **Listo**.

    ![Actualizar un diario de pedidos de trabajo.](media/am-mobile-07.png "Actualizar un diario de pedidos de trabajo")

## <a name="update-lifecycle-state-on-a-work-order"></a>Actualizar el estados de ciclo de vida de un pedido de trabajo

1. En su dispositivo móvil, abra el área de trabajo **Gestión de activos**.

1. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

1. Seleccione el pedido de trabajo para el que desea actualizar el estado de ciclo de vida.

1. Seleccione el botón **Actualizar estado** en la parte inferior de la pantalla.

1. Seleccione un nuev estado del ciclo de vida de la lista.

1. Seleccione **Listo**.

    ![Actualizar el estados de ciclo de vida de un pedido de trabajo.](media/am-mobile-08.png "Actualizar el estados de ciclo de vida de un pedido de trabajo")

## <a name="create-a-maintenance-request"></a>Crear una solicitud de mantenimiento

1. En su dispositivo móvil, abra el área de trabajo **Gestión de activos**.

1. Seleccione **Todas las solicitudes de mantenimiento**.

1. Seleccione **Acciones** en la parte inferior de la pantalla, y seleccione **Crear solicitud de mantenimiento**.

1. Si la secuencia numérica está habilitada para las solicitudes de mantenimiento en **Administración de activos**, se oculta el campo **Solicitud de mantenimiento** porque se completa automáticamente. Si el campo **Solicitud de mantenimiento** está visible, especifique un identificador de solicitud de mantenimiento.

1. Seleccione un **Tipo de solicitud de mantenimiento**.

1. Especifique una **Descripción** para la solicitud de mantenimiento.

1. Seleccionar el **Activo** para el que desea crear la solicitud.

1. Seleccione el **Nivel de servicio** para la solicitud de mantenimiento.

1. Seleccione **Listo**.

    ![Crear una solicitud de mantenimiento.](media/am-mobile-09.png "Crear una solicitud de mantenimiento")

## <a name="add-attachment-to-a-maintenance-request"></a>Agregar datos adjuntos a una solicitud de mantenimiento

1. En su dispositivo móvil, abra el área de trabajo **Gestión de activos**.

1. Seleccione **Todas las solicitudes de mantenimiento**.

1. Seleccione la solicitud de mantenimiento a la que desea agregar un archivo adjunto.

1. Seleccione **Datos adjuntos** en la parte inferior de la pantalla.

1. Seleccione **Agregar datos adjuntos**.

1. Especifique el **Nombre** y las **Notas** para los datos adjuntos.

1. Seleccione **Elegir imagen** para seleccionar una foto de la galería móvil o **Tomar foto** para tomar una foto.

1. Seleccione **Listo**.

    ![Agregar un archivo adjunto a una solicitud de mantenimiento.](media/am-mobile-10.png "Agregar un archivo adjunto a una solicitud de mantenimiento")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]


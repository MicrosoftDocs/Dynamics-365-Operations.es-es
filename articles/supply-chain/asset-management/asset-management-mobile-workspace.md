---
title: Espacio de trabajo móvil de gestión de activos
description: Este tema proporciona información acerca del espacio de trabajo móvil de gestión de activos.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: fd6f45a7dc9d062a3602499e89a6473b3b4aeaee
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278399"
---
# <a name="asset-management-mobile-workspace"></a>Espacio de trabajo móvil de gestión de activos

[!include [banner](../../includes/banner.md)]


Este tema proporciona información acerca del espacio de trabajo móvil de gestión de activos. Este espacio de trabajo permite a los usuarios ver y crear solicitudes de mantenimiento y órdenes de trabajo. Los usuarios también pueden ver los trabajos de órdenes de trabajo asignadas en una vista de calendario o de lista. Los activos y ubicaciones funcionales también se pueden ver y buscar.


## <a name="overview"></a>Visión general

Administración de activos es un módulo avanzado para gestionar activos y trabajos de órdenes de trabajo en Dynamics 365 Supply Chain Management. El espacio de trabajo móvil **Administración de activos** permite a los usuarios ver rápidamente trabajos asignados del pedido de trabajo en el dispositivo móvil de su elección. Los usuarios también pueden crear y gestionar solicitudes de mantenimiento, actualizar estados del ciclo de vida y ver detalles de la ubicación técnica y los activos mediante el dispositivo móvil.

En concreto, el espacio de trabajo móvil **Gestión de activos** permite a los usuarios realizar las tareas siguientes:

- Crear, ver, y editar solicitudes de mantenimiento, realizar una foto o asociar una imagen existente a la solicitud de mantenimiento, cambiar el estado de ciclo de vida de la solicitud de mantenimiento. 
- Crear, ver, y editar órdenes de trabajo, realizar una foto o asociar una imagen existente a la orden de trabajo, cambiar el estado de ciclo de vida de la orden de trabajo, ver trabajos de órdenes de trabajo.
- Ver trabajos de órdenes de trabajo asignadas en una vista de calendario.
- Crear, ver, y editar trabajo de la orden de trabajo, actualizara contadores de activos, ver listas de comprobación de mantenimiento, ver y editar las notas de trabajo de la orden de trabajo, ver las herramientas necesarias para el trabajo de la orden de trabajo.
- Ver o buscar un activo específico o una ubicación técnica.


## <a name="prerequisites"></a>Requisitos previos

Los requisitos previos varían, en función de la versión de Dynamics 365 Supply Chain Management que se ha implementado para su organización.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-supply-chain-management"></a>Requisitos previos si usa Microsoft Dynamics 365 Supply Chain Management 
Si Microsoft Dynamics 365 Supply Chain Management se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Administración de activos**. Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

## <a name="download-and-install-the-mobile-app"></a>Descargar e instalar la aplicación móvil
Descargue e instale la aplicación móvil Dynamics 365 for Unified Operations:

- [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Iniciar sesión en la aplicación móvil
1. Inicie la aplicación en su dispositivo móvil.

2. Escriba la URL de Dynamics 365.

3. La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.

4. Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.

![Figura 1](media/am-mobile-01.png)


## <a name="view-assigned-work-order-jobs-in-calendar-view"></a>Ver trabajos de órdenes de trabajo asignados en una vista de calendario

1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.

2. Seleccione **Mi calendario de trabajos de la orden de trabajo**.

3. Seleccione la fecha para la que desea ver trabajos de la orden de trabajo. En la lista verá el identificador del activo y el identificador de la ubicación técnica de cada trabajo de la orden de trabajo.

4. Seleccione un trabajo del pedido de trabajo en la lista para ver los detalles de trabajo: detalles de la ubicación técnica y los activos, así como otros vínculos de navegación para ver **Datos adjuntos**, **Listas de comprobación**, **Herramientas**, **Contadores de activos**, **Notas**, **Diarios**.

![Figura 2](media/am-mobile-02.png)


## <a name="create-a-work-order-job"></a>Crear un trabajo de una orden de trabajo

1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.

2. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

3. Seleccione el pedido de trabajo para el que desea crear un nuevo trabajo de la orden de trabajo.

4. Seleccione el botón **Agregar línea**.

5. Seleccione el **Activo** para el que desea crear un nuevo trabajo de la orden de trabajo.

6. Seleccione **Tipo de trabajo de mantenimiento**, **Variante del tipo de trabajo de mantenimiento** y **Comercio**.

7. Seleccione **Listo**.

![Figura 3](media/am-mobile-03.png)


## <a name="add-attachment-to-a-work-order-job"></a>Agregar datos adjuntos a un trabajo de pedido de trabajo

1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.

2. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

3. Seleccione la orden de trabajo > trabajo de la orden de trabajo al que desea agregar datos adjuntos.
    - Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.

4. Seleccione **Datos adjuntos** en la página **Detalles del trabajo de la orden de trabajo**.

5. Se verán los datos adjuntos existentes en el trabajo del pedido de trabajo. Seleccione **Agregar datos adjuntos**.

6. Especifique el **Nombre** y las **Notas** para los datos adjuntos.

7. Seleccione **Elegir imagen** para seleccionar una foto de la galería móvil, o **Tomar foto** para tomar una foto.

8. Seleccione **Listo**.

![Figura 4](media/am-mobile-04.png)


## <a name="view-maintenance-checklist-on-a-work-order-job"></a>Ver la lista de comprobación de mantenimiento de un trabajo de una orden de trabajo

1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.

2. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

3. Seleccione la orden de trabajo > trabajo de orden de trabajo para el que desea ver las listas de comprobación.
    - Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.

4. Seleccione **Listas de comprobación** en la página **Detalles del trabajo de la orden de trabajo**.

5. Se verá una lista de líneas de la lista de comprobación relacionadas con el trabajo de la orden de trabajo. Seleccione una línea de la lista de comprobación para ver **Instrucciones** y agregar **Notas**.

6. Seleccione el botón Atrás (**<**) para volver a la página anterior.

![Figura 5](media/am-mobile-05.png)


## <a name="view-and-update-asset-counters-on-a-work-order-job"></a>Ver y actualizar contadores de activos en un trabajo de pedidos de trabajo

1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.

2. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

3. Seleccione la orden de trabajo > trabajo de orden de trabajo para el que desea ver los contadores de activos.
    - Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.

4. Seleccione **Contadores de activos** en la página **Detalles del trabajo de la orden de trabajo**.

5. Se verá una lista de contadores de activos relacionados con el trabajo de la orden de trabajo. Seleccione el icono de lápiz en una línea del contador de activos para actualizar el valor de un contador.

6. Introduzca un nuevo valor de contador y seleccione **Listo**.

![Figura 6](media/am-mobile-06.png)


## <a name="register-consumption-on-a-work-order-job"></a>Registrar el consumo en un trabajo de orden de trabajo

1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.

2. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

3. Seleccione la orden de trabajo > trabajo de orden de trabajo para el que desea agregar registros de consumo.
    - Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.

4. Seleccione **Diarios** en la página **Detalles del trabajo de la orden de trabajo**.

5. Seleccione **Agregar horas** para crear registros de horas de trabajo.
    1. Seleccionar la **categoría** en la búsqueda.
    2. En el campo **Horas**, especifique el número de horas de trabajo gastadas en el trabajo de la orden de trabajo.
    3. Seleccione la **propiedad del línea** adecuada.
    4. Seleccione **Listo**.

6. Seleccione **Agregar artículos** para crear registros de artículos.
    1. Seleccione el **Número de artículo** en la búsqueda.
    2. Seleccione el **Sitio** en la búsqueda.
    3. Indique la **cantidad** de artículos consumidos.
    4. Seleccione **Listo**.

7. Seleccione **Agregar gasto** para crear registros de gastos.
    1. Seleccionar la **categoría** en la búsqueda.
    2. Escriba la cantidad para el registro de gasto.
    3. Seleccione la **divisa de ventas** en la búsqueda.
    4. Escriba el **Precio de coste** para el registro de gasto.
    5. Seleccione **Listo**.

![Figura 7](media/am-mobile-07.png)


## <a name="update-lifecycle-state-on-a-work-order"></a>Actualizar el estados de ciclo de vida de una orden de trabajo

1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.

2. Seleccione **Todos los pedidos de trabajo de mantenimiento**.

3. Seleccione la orden de trabajo para la que desea actualizar el estado de ciclo de vida.

4. Seleccione el botón **Actualizar estado** en la parte inferior de la pantalla.

5. Seleccione un nuev estado del ciclo de vida de la lista.

6. Seleccione **Listo**.

![Figura 8](media/am-mobile-08.png)


## <a name="create-a-maintenance-request"></a>Crear una solicitud de mantenimiento

1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.

2. Seleccione **Todas las solicitudes de mantenimiento**.

3. Seleccione **Acciones** en la parte inferior de la pantalla, y seleccione **Crear solicitud de mantenimiento**.

4. Si la secuencia numérica está habilitada para las solicitudes de mantenimiento en **Administración de activos**, se oculta el campo **Solicitud de mantenimiento** porque se completa automáticamente. Si el campo **Solicitud de mantenimiento** está visible, especifique un identificador de solicitud de mantenimiento.

5. Seleccione un **Tipo de solicitud de mantenimiento**.

6. Especifique una **Descripción** para la solicitud de mantenimiento.

7. Seleccionar el **Activo** para el que desea crear la solicitud.

8. Seleccione el **Nivel de servicio** para la solicitud de mantenimiento.

9. Seleccione **Listo**.

![Figura 9](media/am-mobile-09.png)


## <a name="add-attachment-to-a-maintenance-request"></a>Agregar datos adjuntos a una solicitud de mantenimiento

1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.

2. Seleccione **Todas las solicitudes de mantenimiento**.

3. Seleccione la solicitud de mantenimiento a la que desea agregar un archivo adjunto.

4. Seleccione **Datos adjuntos** en la parte inferior de la pantalla.

5. Seleccione **Agregar datos adjuntos**.

6. Especifique el **Nombre** y las **Notas** para los datos adjuntos.

7. Seleccione **Elegir imagen** para seleccionar una foto de la galería móvil, o **Tomar foto** para tomar una foto.

8. Seleccione **Listo**.

![Figura 10](media/am-mobile-10.png)


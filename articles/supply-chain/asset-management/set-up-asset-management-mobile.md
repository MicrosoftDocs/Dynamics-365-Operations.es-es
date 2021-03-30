---
title: Configurar el espacio de trabajo móvil de gestión de activos
description: Este tema describe cómo configurar Microsoft Dynamics 365 Supply Chain Management y la aplicación móvil Finance and Operations (Dynamics 365) para ejecutar un espacio de trabajo móvil de administración de activos que los trabajadores pueden usar para realizar tareas de administración de activos.
author: johanhoffmann
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 54da27a022dcc800438b96224370228aa8eed261
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226156"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>Configurar el espacio de trabajo móvil de gestión de activos

[!include [banner](../includes/banner.md)]

Este tema describe cómo configurar Microsoft Dynamics 365 Supply Chain Management y la aplicación móvil Finance and Operations (Dynamics 365) para ejecutar un espacio de trabajo móvil de **administración de activos** que los trabajadores pueden usar para realizar tareas de administración de activos.

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a>Configurar usuarios de trabajadores de mantenimiento en Supply Chain Management

Para cada usuario que requiera acceso al espacio de trabajo móvil de **gestión de activos**, siga estos pasos.

1. En Supply Chain Management, vaya a **Recursos humanos \> Trabajadores** y asegúrese de que exista un registro de trabajador para el usuario que desea configurar. Cree un nuevo registro de trabajador según sea necesario.
1. Vaya a **Gestión de activos \> Configuración \> Trabajadores \> Trabajadores** y asegúrese de que el registro de trabajador que identificó (o creó) en el paso anterior esté asignado a un registro de trabajador de mantenimiento. Cree un nuevo registro de trabajador de mantenimiento según sea necesario y establezca el campo **Trabajador** en el registro de trabajador del paso anterior.
1. Vaya a **Gestión de activos \> Configuración \> Trabajadores \> Grupos de trabajador de mantenimiento** y asegúrese de que el registro de trabajador de mantenimiento que identificó (o creó) en el paso anterior pertenezca a un grupo de trabajador de mantenimiento.
1. Vaya a **Administración del sistema \> Usuarios > Usuarios**.
1. Seleccione el usuario correspondiente en la cuadrícula.
1. En la ficha desplegable **Detalles de usuario**, establezca el campo **Persona** en la cuenta de trabajador que desea asociar con la cuenta de usuario actual. Esta cuenta de trabajador debe ser el registro de trabajador que identificó (o creó) en el paso 1 y que se asignó a un registro de trabajador de mantenimiento en el paso 2.

> [!NOTE]
> Los permisos de usuario y los roles de seguridad se aplican a las funciones del espacio de trabajo móvil de **gestión de activos** tal como se aplican a las funciones de la interfaz de usuario de Supply Chain Management. Por lo tanto, cada usuario que configure para acceder al espacio de trabajo móvil de **gestión de activos** debe tener los roles de seguridad necesarios para realizar operaciones similares directamente en Supply Chain Management.

## <a name="publish-the-asset-management-mobile-workspace"></a>Publicación del espacio de trabajo móvil de gestión de activos

Para que las funciones de gestión de activos estén disponibles en la aplicación móvil de Finance and Operations (Dynamics 365), debe publicar el espacio de trabajo móvil de **Gestión de activos**.

1. En Supply Chain Management, seleccione el botón **Configuraciones** (el símbolo del engranaje en la esquina superior derecha) y luego seleccione **Aplicación movil** en el menú.
1. En el cuadro de diálogo **Administrar aplicación móvil**, busque el icono de **Gestión de activos**. Si contiene el texto "En metadatos, no publicado", el espacio de trabajo aún no se ha publicado. Si contiene el texto "En metadatos: publicado", el espacio de trabajo ya se ha publicado y puede omitir el resto de este procedimiento.

    ![Cuadro de diálogo Administrar aplicación móvil](media/mobile-workspaces.png "Cuadro de diálogo Administrar aplicación móvil")

1. Seleccione el icono **Gestión de activos** y luego seleccione **Publicar** en la barra de herramientas. Después de unos segundos, debería recibir una notificación que indica que el espacio de trabajo se ha publicado correctamente. Además, el texto del icono debería cambiar a "En metadatos: publicado".

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>Instale y configure la aplicación móvil Finance and Operations (Dynamics 365)

1. Vaya a una de las siguientes tiendas de aplicaciones para instalar la aplicación **Microsoft Finance and Operations (Dynamics 365)** en su dispositivo móvil:

    - [Para dispositivos Google Android](https://go.microsoft.com/fwlink/?linkid=850662)
    - [Para dispositivos Apple iOS](https://go.microsoft.com/fwlink/?linkid=850663)

1. Abra la aplicación Finance and Operations (Dynamics 365). Debería aparecer la página de inicio de sesión. En el campo **Iniciar sesión**, ingrese su URL de Supply Chain Management o seleccione una URL reciente en la lista **Entornos recientes** y luego toque **Conectar**.

    ![Página de inicio de sesión](media/mobile-app-sign-in.png "Página de inicio de sesión")

1. Si se le solicita que confirme la conexión, seleccione la casilla de verificación **Entendido** y luego toque **Conectar**.
1. En la página **Elegir una cuenta**, use su cuenta de Microsoft para iniciar sesión en la aplicación móvil.

    Aparecerá la página **Espacios de trabajo**. Enumera todos los espacios de trabajo móviles que ha publicado su instancia de Supply Chain Management.

    ![Lista de espacios de trabajo](media/mobile-app-workspaces.png "Lista de espacios de trabajo")

1. Si debe cambiar la entidad legal (empresa), toque el botón Menú (a veces denominado hamburguesa o botón de hamburguesa) en la esquina superior izquierda, y luego toque **Cambiar empresa**.

    ![Cambio de entidad jurídica](media/mobile-app-change-comp.png "Cambio de entidad jurídica")

1. En la página **Espacios de trabajo**, seleccione el espacio de trabajo con el que desea trabajar para abrirlo.

    ![Espacio de trabajo móvil de gestión de activos](media/mobile-app-asset-workspace.png "Espacio de trabajo móvil de gestión de activos")

## <a name="work-with-the-asset-management-mobile-workspace"></a>Trabajo con el espacio de trabajo móvil de administración de activos

Para obtener más información sobre cómo trabajar con el espacio de trabajo **Administración de activos**, consulte [Uso del espacio de trabajo móvil de administración de activos](asset-management-mobile-workspace.md).

Para obtener más información sobre la aplicación móvil Finance and Operations (Dynamics 365), consulte la [Página de inicio de la aplicación móvil](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
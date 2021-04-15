---
title: Configurar la administración de tareas
description: Este tema describe cómo configurar las funciones de administración de tareas en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 742d49b1b7b46952d0a8bb6c8a33cde2a35d124f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791713"
---
# <a name="configure-task-management"></a>Configurar la administración de tareas

[!include [banner](includes/banner.md)]

Este tema describe cómo configurar las funciones de administración de tareas en Microsoft Dynamics 365 Commerce.

Antes de que los gerentes y empleados en Dynamics 365 Commerce puedan usar las funciones de administración de tareas en Commerce, la administración de tareas debe estar configurada. Los pasos de configuración incluyen otorgar permisos a gerentes y empleados, distribuir permisos a clientes de puntos de venta (PDV), configurar notificaciones de PDV y configurar el mosaico **Tareas** en la página de inicio de una aplicación PDV.

## <a name="configure-permissions-for-store-managers"></a>Configurar permisos para gerentes de tienda

Todos los trabajadores de una tienda determinada pueden ver todas las tareas asignadas a esa tienda. También pueden actualizar el estado de las tareas que se les asignan. Sin embargo, personas como los gerentes de la tienda deben tener permisos de administración de tareas para administrar las tareas que se asignan a la tienda y crear tareas de un solo propósito.

Para configurar permisos de administración de tareas para gerentes de tienda, siga estos pasos.

1. Vaya a **Retail y Commerce \> Empleados \> Grupos de permiso**.
1. Seleccione un grupo de permisos específico (por ejemplo, **Gerente**) y luego seleccione **Editar**.
1. En la ficha desplegable **Permisos**, configure la opción **Permitir gestión de tareas** a **Sí**.
1. En la ficha desplegable **Notificaciones**, agregue la operación **Administración de tareas** e introduzca un valor en el campo **Orden de visualización**. Por ejemplo, introduzca **2** si la operación **Cumplimiento de pedido** ya tiene un valor de **Orden de visualización** de **1**.
    
> [!NOTE]
> Si una persona que no es gerente debe tener permisos de administración de tareas en el PDV, puede otorgar permiso a la persona. Alternativamente, puede crear un nuevo grupo de permisos para los no administradores y establecer la opción **Permitir gestión de tareas** a **Sí**.

La siguiente ilustración muestra cómo configurar los permisos de gestión de tareas para gerentes de tienda.

![Configurar permisos de administración de tareas para gerentes de tienda](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a>Configurar permisos para empleados

Los empleados deben tener permisos para crear listas de tareas, administrar criterios de asignación y configurar la recurrencia de cualquier lista de tareas. Para configurar estos permisos, asigne empleados el rol de **Gerente de tareas de Retail**.

Para configurar permisis para un empleado, siga estos pasos.

1. Vaya a **Retail y Commerce \> Empleados \> Usuarios**.
1. Seleccione un empleado.
1. En la ficha desplegable **Roles de usuarios** seleccione **Asignar roles**.
1. En el cuadro de diálogo **Asignar roles al usuario**, seleccione el rol **Gerente de tareas de Retail**, y luego seleccione **Aceptar**.

## <a name="distribute-permissions-to-pos-clients"></a>Distribuir permisos a clientes PDV

Antes de que los empleados puedan usar clientes PDV, los permisos deben distribuirse y sincronizarse con esos clientes.

Para distribuir permisos a los clientes PDV, siga estos pasos.

1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
1. Seleccione el calendario de distribución **1060** (**Personal**) y luego seleccione **Ejecutar ahora**.
1. Seleccione el calendario de distribución **1070** (**Configuración de canal**) y luego seleccione **Ejecutar ahora**.

## <a name="configure-pos-notifications-for-tasks"></a>Configurar notificaciones de PDV para tareas

La gestión de tareas debe configurarse de modo que las notificaciones estén disponibles en la aplicación PDV.

Para configurar las notificaciones PDV para tareas, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> PDV \> Operaciones PDV**.
1. Encuentre la operación **1400** (**Administración de tareas**) y seleccione la casilla **Permitir notificaciones** para ello.

La siguiente ilustración muestra la operación **Administración de tareas** en la página **Operaciones PDV**.

![Operación de gestión de tareas en la página de operaciones de PDV](media/HQ-POS-Tasks-Notifications.png)

Para obtener más información sobre cómo configurar las notificaciones de PDV, vea [Mostrar notificaciones de pedidos en el punto de venta (PDV)](notifications-pos.md).

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a>Configure el mosaico Tareas en la página de inicio de una aplicación PDV

Antes de configurar el mosaico **Tareas** en la página de inicio de una aplicación PDV, vea [Diseños de pantalla para el punto de venta (PDV)](pos-screen-layouts.md) para obtener información sobre cómo configurar y agregar nuevos botones a un diseño de pantalla PDV.

Para configurar el mosaico **Tareas** en la página de inicio de una aplicación PDV, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> PDV \> Diseños de pantalla**.
1. Seleccione un diseño de pantalla, seleccione un tamaño de diseño y seleccione una cuadrícula de botones.
1. En la ficha desplegable **Cuadrículas de botones**, seleccione **Diseñador** para editar la cuadrícula del botón seleccionado.
1. Agregue un mosaico **Tareas** a la sección correspondiente de la página de inicio.

La ilustración siguiente muestra un ejemplo de un mosaico **Tareas** en una página principal PDV.

![Mosaico de tareas en una página de principal de PDV](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la administración de tareas](task-mgmt-overview.md)

[Crear listas de tareas y agregar tareas](task-mgmt-create-lists.md)

[Asignar listas de tareas a tiendas o empleados](task-mgmt-assign-lists.md)

[Administración de tareas en PDV](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV
description: Este tema describe cómo sincronizar la administración de tareas entre Microsoft Teams y Dynamics 365 Commerce punto de venta (PDV).
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 74d53a850113c83979fba6baa4ff3c3e5d9ca02d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020636"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a>Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV

[!include [banner](includes/banner.md)]

Este tema describe cómo sincronizar la administración de tareas entre Microsoft Teams y Dynamics 365 Commerce punto de venta (PDV).

Uno de los propósitos principales de la integración de Teams es permitir la sincronización de la administración de tareas entre la aplicación PDV y Teams. De esta manera, los empleados de la tienda pueden usar la aplicación PDV o Teams para administrar tareas y no tienen que cambiar de aplicación.

Debido a que Planner se usa como repositorio de tareas en Teams, debe haber un vínculo entre Teams y Dynamics 365 Commerce. Este vínculo se establece mediante el uso de un ID de plan específico para un equipo de tienda determinado.

Los siguientes procedimientos muestran cómo configurar la sincronización de la administración de tareas entre las aplicaciones PDV y Teams.

## <a name="publish-a-test-task-list-in-teams"></a>Publica una lista de tareas de prueba en Teams

El siguiente procedimiento asume que los equipos de su tienda están usando la integración de la gestión de tareas de Microsoft Teams con Commerce por primera vez.

Para publicar una lista de tareas de prueba en Teams, siga estos pasos.

1. Inicie sesión en el Teams como director de comunicaciones. Por lo general, los administradores de comunicaciones son usuarios que tienen el rol **Administrador regional** en Commerce.
1. En el panel de navegación izquierdo, seleccione **Tareas por planificador**.
1. En la pestaña **Listas publicadas**, seleccione **Lista nueva** en la parte inferior izquierda y nombre a la nueva lista **Lista de tareas de prueba**.
1. Seleccione **Crear**. La nueva lista aparece en **Borradores**.
1. Bajo **Título de la tarea**, dele a la primera tarea el título **Integración de Teams de prueba**. Luego seleccione **Introducir**.
1. En la lista **Borradores**, seleccione la lista de tareas. Luego seleccione **Publicar** en la esquina superior derecha.
1. En el cuadro de diálogo **Seleccione a quién publicar**, seleccione los equipos que deben recibir la lista de tareas de prueba.
1. Seleccione **Siguiente** para revisar su plan de publicación. Si debe realizar cambios, seleccione  **Atrás**. 
1. Seleccione **Confirmar para continuar** y luego seleccione **Publicar**.
1. Una vez finalizada la publicación, aparecerá un mensaje en la parte superior de la pestaña **Listas publicadas** indica si su lista de tareas se entregó correctamente.

Para más información, consulte [Publique listas de tareas para crear y realizar un seguimiento del trabajo en su organización](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).

## <a name="link-pos-and-teams-for-task-management"></a>Vincular PDV y Teams para la gestión de tareas

Para vincular las aplicaciones PDV y Microsoft Teams para la gestión de tareas en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Administración de tareas \> Integración de tareas con Microsoft Teams**.
1. En el panel Acciones, seleccione **Editar**.
1. Establezca la opción **Habilitar la integración de integración de tareas** en **Sí**.
1. En el panel Acciones, seleccione **Guardar**.
1. En el panel de acciones, seleccione **Configurar administración de tarea**. Debería recibir una notificación que indique que un trabajo por lotes que se denomina **Provisión de equipos** se está creando.
1. Vaya a **Administración del sistema \> Consultas \> Trabajos por lotes** y busque el trabajo más reciente que tenga la descripción **Provisión de equipos**. Espere hasta que este trabajo termine de ejecutarse.
1. Ejecute el **trabajo CDX 1070** para publicar el identificador del plan y almacenar referencias en Retail Server.

## <a name="additional-resources"></a>Recursos adicionales

[Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams](commerce-teams-integration.md)

[Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams](enable-teams-integration.md)

[Aprovisionar Microsoft Teams desde Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Administrar roles de usuario en Microsoft Teams](manage-user-roles-teams.md)

[Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams](map-stores-existing-teams.md)

[Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams](teams-integration-faq.md)

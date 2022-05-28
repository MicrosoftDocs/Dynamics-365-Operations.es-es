---
title: Preguntas más frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams
description: Este tema proporciona respuestas a las preguntas frecuentes sobre la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 16ad6cec0fb852d863039740e9f2c3406467e899
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692518"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a>Preguntas más frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams

[!include [banner](includes/banner.md)]

Este tema proporciona respuestas a las preguntas frecuentes sobre la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a>¿Quién en la tienda se convierte en propietario de un equipo mientras aprovisiona Teams de Commerce? 

Todos los gerentes de tienda se agregan automáticamente como propietarios al grupo de equipo correspondiente para que puedan realizar operaciones como agregar un canal privado y agregar o eliminar miembros. 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a>¿Cómo asigno el rol de "gerente de comunicaciones" a un empleado en la sede de Commerce? 

Responsables de comunicación en Microsoft Teams tienen la capacidad de crear y publicar listas de tareas. Los empleados de la organización que necesitan convertirse en gerentes de comunicación deben tener asignado el rol de "gerente de tareas minoristas" en la sede de Commerce.

Para asignar el rol de administrador de tareas minoristas a un empleado en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Empleados \> Usuarios**.
1. Seleccione un empleado.
1. En la ficha desplegable **Roles de usuarios** seleccione **Asignar roles**.
1. En el cuadro de diálogo **Asignar roles al usuario**, seleccione el rol **Gerente de tareas de Retail**, y luego seleccione **Aceptar**.

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a>¿Cómo puedo hacer que una jerarquía organizativa específica esté disponible para cargar en Microsoft Teams?

En la sede de Commerce, la jerarquía de cada organización está asociada con uno o más propósitos. Asegúrese de que la jerarquía en la que desea aprovisionar Microsoft Teams tiene el propósito **Informes minoristas** asociado con él, como se muestra en la siguiente imagen de ejemplo. 

![Ejemplo de un propósito de jerarquía organizativa en la sede de Commerce.](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a>¿Cómo puedo permitir que los trabajadores de la tienda minorista inicien sesión en el punto de venta (PDV) de Commerce usando Azure Active Directory (Azure AD)?

Para obtener información sobre cómo configurar la experiencia de inicio de sesión de Commerce PDV para usar autenticación de Azure AD, vea [Habilitar autenticación Azure Active Directory para el inicio de sesión de PDV](aad-pos-logon.md).

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a>¿Cómo asigno las tiendas y los equipos correspondientes en la sede de Commerce si mi organización ya ha creado equipos en Microsoft Teams?

Para obtener información sobre cómo asignar tiendas y equipos si hay equipos preexistentes, consulte [Asignar tiendas y equipos correspondientes si su organización tiene equipos preexistentes en Microsoft Teams](map-stores-existing-teams.md).

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a>¿Cómo borro el token de la API de Microsoft Graph almacenado en el almacenamiento de la sesión?

Un usuario que ha iniciado sesión en el punto de venta (PDV) con una cuenta Azure Active Directory (Azure AD) debe cerrar sesión en el PDV o cerrar la aplicación para borrar el almacenamiento de la sesión. 

> [!TIP]
> Una mejor práctica recomendada es hacer que los trabajadores de la tienda bloqueen siempre el terminal PDV o cierren la sesión cuando no estén usando el terminal. 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a>¿Qué sucede si una tienda no tiene gerentes de tienda?

Si una tienda no tiene gerentes, no se creará un grupo de equipo para la tienda o en Teams. 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a>¿Qué sucede si el gerente de una tienda deja la empresa?

Cualquiera con el rol de propietario puede agregar un nuevo gerente de tienda en la sede de Commerce y reaprovisionar Teams para que el nuevo gerente tenga los privilegios necesarios en Teams para el grupo. 

## <a name="additional-resources"></a>Recursos adicionales

[Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams](commerce-teams-integration.md)

[Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams](enable-teams-integration.md)

[Aprovisionar Microsoft Teams desde Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV](synchronize-tasks-teams-pos.md)

[Administrar roles de usuario en Microsoft Teams](manage-user-roles-teams.md)

[Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams](map-stores-existing-teams.md)

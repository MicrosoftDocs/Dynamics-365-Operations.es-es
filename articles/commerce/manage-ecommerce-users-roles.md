---
title: Administrar usuarios y roles de comercio electrónico
description: Este tema explica cómo conceder acceso a los usuarios para el entorno de creación del sitio de Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8d4987a824b786401c41c6ae63c8486ce7eb0c5d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995700"
---
# <a name="manage-e-commerce-users-and-roles"></a>Administrar usuarios y roles de comercio electrónico


[!include [banner](includes/banner.md)]

Este tema explica cómo conceder acceso a los usuarios para el entorno de creación del sitio de Microsoft Dynamics 365 Commerce.

Para ayudar a controlar el acceso de los usuarios y conceder permiso a los usuarios para realizar tareas específicas, el entorno de creación de sitios usa grupos de seguridad que crea en Microsoft Azure Active Directory (Azure AD). Primero asigna un grupo de seguridad nuevo o existente desde Azure AD a cada rol en el entorno de creación. A continuación, concede o revoca permisos para usuarios individuales agregando esos usuarios a un grupo de seguridad adecuado o quitándolos de un grupo de seguridad.

## <a name="overview-of-roles-in-the-authoring-environment"></a>Visión general de roles en el entorno de creación

El entorno de creación de Dynamics 365 for Commerce admite los roles siguientes.

| Función                 | Descripción |
|----------------------|-------------|
| Administrador del sistema | Los usuarios con este rol tienen todos los privilegios para todas las herramientas, y para todas las calificaciones y revisiones. También pueden crear sitios. |
| Administrador   | Usuarios que tienen este rol cuentan con todos los privilegios para todas las herramientas y RnR en una estructura de sitio dada. |
| Productor web         | Los usuarios con este rol pueden crear páginas, fragmentos y plantillas, cargar y administrar activos, y enriquecer productos y categorías. |
| Lector               | Los usuarios que tengan este rol pueden ver páginas, plantillas, activos, fragmentos, diseños y valores, pero no pueden realizar cambios. |
| Moderador RnR        | Los usuarios que tienen este rol pueden moderar revisiones de productos. |

## <a name="system-administrator-role"></a>Rol Administrador del sistema

Al aprovisionar Dynamics 365 Commerce en el entorno de Lifecycle Services (LCS) de Microsoft Dynamics, se te pedirá que proporciones un grupo de seguridad para el rol **Administrador del sistema**. A continuación, este rol se aplicará automáticamente a todos los sitios que cree en el entorno que está configurando. El grupo de seguridad para este rol solo se puede actualizar en LCS. En la página **Administración del sitio** para todos los sitios, aparece como de solo lectura y es meramente informativo.

## <a name="administrator-role"></a>Rol Administrador

Al crear un nuevo sitio en comercio, se le pide proporcionar un grupo de seguridad para el rol **Administrador**. Consulte la tabla anterior de este tema para obtener una visión general de los permisos que este rol concede.

## <a name="add-or-update-security-groups"></a>Agregar o actualizar grupos de seguridad

Una vez creado el sitio, solo los usuarios que se encuentren en los grupos de seguridad que están asociados a los roles **Administrador del sistema** y **Administrador** pueden tener acceso al entorno de creación para ese sitio. Para asignar usuarios a los roles **Productor web**, **Moderador RnR** y Lector **Reader**, debe asignar grupos de seguridad a esos roles. Para agregar un grupo de seguridad a un rol, o actualizar un grupo de seguridad que está asignado actualmente a un rol, siga estos pasos.

1. Vaya al sitio que desea actualizar.
1. En el **Administración del sitio**, abra la página **Seguridad**.
1. Seleccione el rol que se va a modificar.
1. Agregue grupos de seguridad a roles, o quite grupos de seguridad de roles.

## <a name="additional-resources"></a>Recursos adicionales

[Agregar secuencia de comandos a páginas del sitio para admitir telemetría](add-telemetry.md)

[Consideraciones de optimización de motor de búsqueda (SEO) para su sitio](search-engine-optimization-considerations.md)

[Gestionar la directiva de seguridad de contenido (CSP)](manage-csp.md)

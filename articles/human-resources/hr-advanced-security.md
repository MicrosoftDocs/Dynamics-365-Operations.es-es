---
title: Restringir el acceso a los trabajadores por entidad jurídica
description: En este artículo se explica cómo configurar el acceso de los trabajadores por entidad jurídica.
author: twheeloc
ms.date: 11/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadd2c34d31bbd259255596c06a8e7517f7a774b
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780398"
---
# <a name="restrict-access-to-workers-by-legal-entity"></a>Restringir el acceso a los trabajadores por entidad jurídica

En este artículo se explica cómo configurar el acceso de los trabajadores por entidad jurídica.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Los empleados están empleados en personas jurídicas. A continuación, encontrará algunos ejemplos:

- Aaron Con está empleado en la entidad legal USSI.
- Ahmed Barnett está empleado en la entidad legal USMF.
- Alicia Thornber trabaja en las entidades legales GLSI y USMF.

Según el rol de un usuario en la empresa, es posible que necesite acceso para ver a todos los empleados en todas las entidades legales. Alternativamente, es posible que un usuario deba estar restringido, de modo que pueda ver solo a los empleados en la entidad legal a la que tiene acceso. Para controlar qué empleados puede ver un usuario, seleccione el parámetro **Restringir el acceso a la información del trabajador** en la página **Parámetros compartidos de recursos humanos**.

Por ejemplo, un usuario tiene acceso a la página **Trabajador** y tiene acceso solo a la entidad legal USMF. En este caso, el usuario puede visualizar la siguiente información para los empleados de la lista anterior:

- Si la función para restringir el acceso a la información del trabajador no está habilitada, el usuario puede ver la información de Aaron, Ahmed y Alicia.
- Si la característica está habilitada, el usuario puede ver información solo para Alicia y Ahmed, porque también están empleados en la entidad legal USMF.

La información que se muestra varía según la aplicación que esté utilizando.

## <a name="dynamics-365-human-resources-stand-alone"></a>Dynamics 365 Human Resources independiente

Si la función para restringir el acceso a la información del trabajador está habilitada, el usuario restringido verá un valor en blanco en algunas listas que contienen el nombre del trabajador.

Por ejemplo, un usuario que solo tiene acceso a la entidad jurídica USMF experimenará el siguiente comportamiento.

- En la lista **Posiciones activas**, la columna **Trabajador** estará en blanco para el puesto de Aaron, porque el usuario no tiene acceso a los empleados en la entidad legal de USSI.
- Si el usuario profundiza en el nombre del trabajador, aparecerá una página **Trabajador** en blanco.

## <a name="dynamics-365-human-resources-on-finance-infrastructure"></a>Dynamics 365 Human Resources en la infraestructura de Finance

Si la función para restringir el acceso a la información del trabajador está habilitada, el usuario restringido verá un valor en blanco en algunas listas.

Por ejemplo, un usuario que solo tiene acceso a la entidad jurídica USMF experimenará el siguiente comportamiento.

- En la lista **Posiciones activas**, la columna **Trabajador** mostrará el nombre de Aaron. Si el usuario pasa el cursor sobre el nombre del trabajador, solo se mostrarán el nombre y el cargo.
- Si el usuario profundiza en el nombre del trabajador, aparecerá una página **Trabajador** en blanco.

> [!TIP]
> Si utiliza Dynamics 365 Human Resources en la infraestructura de Finanzas y desea que los usuarios restringidos vean valores en blanco para los nombres de los trabajadores, puede agregar el pivilegio de seguridad **Restringir el acceso a los trabajadores** a los roles de usuario en la página **Configuración de seguridad**.

Una vez habilitada la característica, debe completar algunos pasos extra para establecer los permisos adecuados para cada usuario cuya vista deba restringirse.

1. Sobre la página **Usuarios**, seleccione un usuario.
2. Seleccione un rol para el usuario. La opción **Asignar organizaciones** está disponible.
3. Seleccione **Asignar organizaciones**.
4. En la nueva página, seleccione **Otorgar acceso a organizaciones específicas de forma individual** y luego seleccione las organizaciones a las que el usuario debe tener acceso.
5. Repita los pasos 2 a 4 para todos los demás roles que tenga el usuario, incluido el rol de usuario del sistema.

> [!NOTE]
> Las entidades jurídicas a las que tiene acceso un usuario deben coincidir en todos los roles del usuario.

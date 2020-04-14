---
title: Solucione problemas con el módulo de doble escritura en aplicaciones Finance and Operations
description: Este tema proporciona información de solución de problemas que puede ayudarlo a solucionar problemas con el módulo de escritura doble en aplicaciones Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172769"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>Solucione problemas con el módulo de doble escritura en aplicaciones Finance and Operations

[!include [banner](../../includes/banner.md)]



Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service. Específicamente, proporciona información que puede ayudarlo a solucionar problemas con el módulo de **Escritura doble** en aplicaciones Finance and Operations.

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una función o credenciales específicas.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>No puede cargar el módulo de doble escritura en una aplicación Finance and Operations

Si no puede abrir la página **Doble escritura** seleccionando el mosaico **Doble escritura** en el espacio de trabajo **Gestión de datos**, el servicio de integración de datos probablemente esté inactivo. Cree un ticket de soporte para solicitar un reinicio del servicio de integración de datos.

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a>Error al intentar crear una nueva asignación de entidad

**Credenciales requeridas para arreglar el problema:** Administrador de inquilinos Azure AD

Es posible que reciba el siguiente mensaje de error cuando intente configurar una nueva entidad para doble escritura:

*El código de estado de respuesta no indica éxito: 401 (No autorizado)*

Este error ocurre porque solo un administrador de inquilino Azure AD puede agregar una nueva asignación de entidad.

Para solucionar el problema, inicie sesión en aplicaciones Finance and Operations como inquilino administrador Azure AD. También debe ir a web.PowerApps.com y revalidar su conexión.

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Error al abrir la interfaz de usuario de doble escritura

Es posible que reciba el siguiente mensaje de error cuando intente acceder a la escritura doble desde el espacio de trabajo **Gestión de datos**:

*login.microsoftonline.com se negó a conectarse.*

Para solucionar el problema, inicie sesión utilizando una ventana InPrivate en Microsoft Edge, una ventana de incógnito en Chromium o una ventana de incógnito en Google Chrome. También debe desbloquear o borrar las cookies de terceros.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a>Error al vincular el entorno para doble escritura o agregar una nueva asignación de entidad

**Credenciales requeridas para arreglar el problema:** Administrador de inquilinos Azure AD

Puede encontrar el siguiente error al vincular o crear mapas:

*El código de estado de respuesta no indica éxito: 403 (tokenexchange).<br> ID de sesión: \<su id de sesión\><br> ID de actividad raíz: \<su id de actividad raíz\>*

Este error puede ocurrir si no tiene permisos suficientes para vincular escritura doble o crear mapas. Debes usar una cuenta de administrador de inquilinos de Azure AD para vincular entornos y agregar nuevas asignaciones de entidades. Sin embargo, después de la configuración, puede usar una cuenta que no sea de administrador para seguir el estado y editar las asignaciones.

## <a name="error-when-you-stop-the-entity-mapping"></a>Error al detener la asignación de entidad

Es posible que reciba el siguiente mensaje de error cuando intenta detener las asignaciones de entidad:

*\[Prohibido\], \[{"status": 403,"source":"","message":"Error del intercambio de tokens: el usuario no puede acceder a la conexión dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], El servidor remoto devolvió un error: (403) Prohibido.*

Este error ocurre cuando el entorno vinculado Common Data Service no está disponible.

Para solucionar el problema, cree un ticket para el equipo de integración de datos. Adjunte la traza de red para que el equipo de integración de datos pueda marcar los mapas como **No ejecutando** en el back-end.

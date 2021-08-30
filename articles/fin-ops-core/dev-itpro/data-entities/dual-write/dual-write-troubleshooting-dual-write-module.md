---
title: Solucionar problemas de doble escritura en aplicaciones de Finance and Operations
description: Este tema proporciona información de solución de problemas que puede ayudarlo a solucionar problemas con el módulo de escritura doble en aplicaciones Finance and Operations.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 6689fae215937f58c93cce72df3fa0a1b5aecd3a5ac9913981b253344a1ba13f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720745"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>Solucionar problemas de doble escritura en aplicaciones de Finance and Operations

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse. Específicamente, proporciona información que puede ayudarlo a solucionar problemas con el módulo de **Escritura doble** en aplicaciones Finance and Operations.

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una función o credenciales específicas.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>No puede cargar el módulo de doble escritura en una aplicación Finance and Operations

Si no puede abrir la página **Doble escritura** seleccionando el mosaico **Doble escritura** en el espacio de trabajo **Gestión de datos**, el servicio de integración de datos probablemente esté inactivo. Cree un ticket de soporte para solicitar un reinicio del servicio de integración de datos.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Error al intentar crear una nueva asignación de tabla

**Credenciales necesarias para solucionar el problema**: el mismo usuario que configuró la doble escritura.

Es posible que reciba el siguiente mensaje de error cuando intente configurar una nueva tabla para doble escritura. El único usuario que puede crear una asignación es el usuario que configuró la conexión de doble escritura.

*El código de estado de respuesta no indica éxito: 401 (No autorizado)*


## <a name="error-when-you-open-the-dual-write-user-interface"></a>Error al abrir la interfaz de usuario de doble escritura

Es posible que reciba el siguiente mensaje de error cuando intente acceder a la escritura doble desde el espacio de trabajo **Gestión de datos**:

*login.microsoftonline.com se negó a conectarse.*

Para solucionar el problema, inicie sesión utilizando una ventana InPrivate en Microsoft Edge, una ventana de incógnito en Chromium o una ventana de incógnito en Google Chrome. También debe desbloquear o borrar las cookies de terceros.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Error al vincular el entorno para doble escritura o agregar una nueva asignación de tabla

**Rol requerido para solucionar el problema**: Administrador del sistema en aplicaciones de Finance and Operations y Dataverse.

Puede encontrar el siguiente error al vincular o crear mapas:

*El código de estado de respuesta no indica éxito: 403 (tokenexchange).<br> Id. de sesión: \<your session id\><br> Id. de actividad raíz: \<your root activity id\>*

Este error puede ocurrir si no tiene permisos suficientes para vincular escritura doble o crear mapas. Este error también puede ocurrir si el entorno de Dataverse se restableció sin desvincular la doble escritura. Cualquier usuario con rol de administrador del sistema en aplicaciones de Finance and Operations y Dataverse puede vincular los entornos. Solo el usuario que configuró la conexión de doble escritura puede agregar nuevas asignaciones de tabla. Después de la configuración, cualquier usuario con función de administrador del sistema puede monitorear el estado y editar las asignaciones.

## <a name="error-when-you-stop-the-table-mapping"></a>Error al detener la asignación de tabla

Es posible que reciba el siguiente mensaje de error cuando intenta detener las asignaciones de tabla:

*\[Prohibido\], \[{"status": 403,"source":"","message":"Error del intercambio de tokens: el usuario no puede acceder a la conexión dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], El servidor remoto devolvió un error: (403) Prohibido.*

Este error ocurre cuando el entorno vinculado Dataverse no está disponible.

Para solucionar el problema, cree un ticket para el equipo de integración de datos. Adjunte la traza de red para que el equipo de integración de datos pueda marcar los mapas como **No ejecutando** en el back-end.

## <a name="error-while-trying-to-start-a-table-mapping"></a>Error al intentar iniciar una asignación de tabla

Es posible que reciba un error como el siguiente cuando intenta establecer ese estado de una asignación como **En ejecución**:

*No se puede completar la sincronización de datos inicial. Error: error de doble escritura - error en el registro del complemento: no se pueden construir metadatos de búsqueda de doble escritura. La referencia de objeto de error no está establecida en una instancia de un objeto*.

La solución para este error depende de la causa del error:

+ Si la asignación tiene asignaciones dependientes, asegúrese de habilitar las asignaciones dependientes de esta asignación de tabla.
+ Es posible que falten columnas de origen o destino en la asignación. Si falta una columna en la aplicación de Finance and Operations, siga los pasos de la sección [Problema de columnas de tabla faltantes en asignaciones](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Si falta una columna en Dataverse, haga clic en el botón **Actualizar tablas** en la asignación para que las columnas se rellenen automáticamente en la asignación.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
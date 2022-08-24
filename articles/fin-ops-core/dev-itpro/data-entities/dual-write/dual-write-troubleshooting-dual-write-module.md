---
title: Solucionar problemas de doble escritura en aplicaciones de finanzas y operaciones
description: Este artículo proporciona información de solución de problemas que puede ayudarlo a solucionar problemas con el módulo de escritura doble en aplicaciones de finanzas y operaciones.
author: RamaKrishnamoorthy
ms.date: 04/18/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 5678cd38e48eb5226e36851679436d3b6c117cf9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289586"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>Solucionar problemas de doble escritura en aplicaciones de finanzas y operaciones

[!include [banner](../../includes/banner.md)]



Este artículo proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de finanzas y operaciones y Dataverse. Específicamente, proporciona información que puede ayudarlo a solucionar problemas con el módulo de **Escritura doble** en aplicaciones de finanzas y operaciones.

> [!IMPORTANT]
> Algunos de los problemas que aborda este artículo pueden requerir la característica de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una característica o credenciales específicas.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>No puede cargar el módulo de doble escritura en una aplicación de finanzas y operaciones

Si no puede abrir la página **Doble escritura** seleccionando el mosaico **Doble escritura** en el espacio de trabajo **Gestión de datos**, el servicio de integración de datos probablemente esté inactivo. Cree un ticket de soporte para solicitar un reinicio del servicio de integración de datos.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Error al intentar crear una nueva asignación de tabla

**Credenciales necesarias para solucionar el problema**: el mismo usuario que configuró la doble escritura.

Es posible que reciba el siguiente mensaje de error cuando intente configurar una nueva tabla para doble escritura. El único usuario que puede crear una asignación es el usuario que configuró la conexión de doble escritura.

*El código de estado de respuesta no indica éxito: 401 (No autorizado).*

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Error al abrir la interfaz de usuario de doble escritura

Es posible que reciba el siguiente mensaje de error cuando intente acceder a la escritura doble desde el espacio de trabajo **Gestión de datos**:

*login.microsoftonline.com se negó a conectarse.*

Para solucionar el problema, inicie sesión utilizando una ventana InPrivate en Microsoft Edge, una ventana de incógnito en Chromium o una ventana de incógnito en Google Chrome. También debe desbloquear o borrar las cookies de terceros.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Error al vincular el entorno para doble escritura o agregar una nueva asignación de tabla

**Rol requerido para solucionar el problema**: Administrador del sistema en aplicaciones de finanzas y operaciones y Dataverse.

Puede encontrar el siguiente error al vincular o crear mapas:

```dos
Response status code does not indicate success: 403 (tokenexchange).
Session ID: \<your session id\>
Root activity ID: \<your root activity\> id
```

Este error puede ocurrir si no tiene permisos suficientes para vincular escritura doble o crear mapas. Este error también puede ocurrir si el entorno de Dataverse se restableció sin desvincular la doble escritura. Cualquier usuario con rol de administrador del sistema en aplicaciones de finanzas y operaciones y Dataverse puede vincular los entornos. Solo el usuario que configuró la conexión de doble escritura puede agregar nuevas asignaciones de tabla. Después de la configuración, cualquier usuario con función de administrador del sistema puede monitorear el estado y editar las asignaciones.

## <a name="error-when-you-stop-the-table-mapping"></a>Error al detener la asignación de tabla

Es posible que reciba el siguiente mensaje de error cuando intenta detener las asignaciones de tabla:

*\[Prohibido\], \[{"status": 403,"source":"","message":"Error del intercambio de tokens: el usuario no puede acceder a la conexión dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], El servidor remoto devolvió un error: (403) Prohibido.*

Este error ocurre cuando el entorno vinculado Dataverse no está disponible.

Para solucionar el problema, cree un ticket para el equipo de integración de datos. Adjunte la traza de red para que el equipo de integración de datos pueda marcar los mapas como **No ejecutando** en el back-end.

## <a name="enable-parallel-processing-in-finance-and-operations-apps-to-improve-performance"></a>Habilitar el procesamiento paralelo en las aplicaciones de finanzas y operaciones para mejorar el rendimiento

Habilitar el procesamiento paralelo puede reducir el tiempo necesario para importar datos de las aplicaciones de Dynamics 365 customer engagement y Microsoft Dataverse a las aplicaciones de finanzas y operaciones. 

Para habilitar el procesamiento paralelo en las aplicaciones de finanzas y operaciones, realice los pasos siguientes.

1. Inicie sesión en su entorno de finanzas y operaciones.
2. Vaya a **Administración de datos > Parámetros de marco**.
3. Seleccione **Configuración de la entidad** y seleccione **Configurar parámetros de ejecución de entidad**.
4. Agregue los parámetros para el procesamiento paralelo:
    - **Recuento de registros de umbral de importación**: el número de registros que se deben cumplir antes de que se habilite el procesamiento paralelo.
    - **Importar recuento de tareas**: el número de subprocesos (tareas) para ejecutar en paralelo.
5. Seleccione **Guardar**.


## <a name="errors-while-trying-to-start-a-table-mapping"></a>Errores al intentar iniciar una asignación de tabla

### <a name="unable-to-complete-initial-data-sync"></a>No se pudo completar la sincronización de datos inicial

Es posible que reciba un mensaje de error como el siguiente cuando intente ejecutar la sincronización de datos inicial:

*No se puede completar la sincronización de datos inicial. Error: error de doble escritura - error en el registro del complemento: no se pueden construir metadatos de búsqueda de doble escritura. La referencia de objeto de error no está establecida en una instancia de un objeto*.

Es posible que aparezca este error cuando intenta establecer ese estado de una asignación como **En ejecución**. La solución depende de la causa del error:

+ Si la asignación tiene asignaciones dependientes, asegúrese de habilitar las asignaciones dependientes de esta asignación de tabla.
+ Es posible que falten columnas de origen o destino en la asignación. Si falta una columna en la aplicación de finanzas y operaciones, siga los pasos de la sección [Problema de columnas de tabla faltantes en asignaciones](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Si falta una columna en Dataverse, haga clic en el botón **Actualizar tablas** en la asignación para que las columnas se rellenen automáticamente en la asignación.

### <a name="version-mismatch-error-and-upgrading-dual-write-solutions"></a>Error de discrepancia de versión y actualización de soluciones de doble escritura

Es posible que reciba los siguientes mensajes de error cuando intenta ejecutar las asignaciones de tabla:

+ *Grupos de clientes (msdyn_customergroups): error de doble escritura - La versión de la solución 'Dynamics365Company' de Dynamics 365 for Sales no coincide. Versión: '2.0.2.10', Versión requerida: '2.0.133'*
+ *La versión de la solución 'Dynamics365FinanceExtended' de Dynamics 365 for Sales no coincide. Versión: '1.0.0.0', Versión requerida: '2.0.227'*
+ *La versión de la solución 'Dynamics365FinanceAndOperationsCommon' de Dynamics 365 for Sales no coincide. Versión: '1.0.0.0', Versión requerida: '2.0.133'*
+ *La versión de la solución 'CurrencyExchangeRates' de Dynamics 365 for Sales no coincide. Versión: '1.0.0.0', Versión requerida: '2.0.133'*
+ *La versión de la solución 'Dynamics365SupplyChainExtended' de Dynamics 365 for Sales no coincide. Versión: '1.0.0.0', Versión requerida: '2.0.227'*

Para solucionar los problemas, actualice las soluciones de doble escritura en Dataverse. Asegúrese de actualizar a la solución más reciente cuya versión coincida con la versión de solución requerida.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]


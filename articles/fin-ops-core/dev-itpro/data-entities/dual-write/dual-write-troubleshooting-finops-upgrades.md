---
title: Solucionar problemas con actualizaciones de aplicaciones de Finance and Operations
description: Este tema proporciona información de solución de problemas que puede ayudarlo a solucionar problemas relacionados con las actualizaciones de aplicaciones Finance and Operations.
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
ms.openlocfilehash: 5a68e17e3bce4efdd1a10f8f8319ff996690604572d57e9f8232f5ec45fa39e7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728172"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>Solucionar problemas con actualizaciones de aplicaciones de Finance and Operations

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse. Especificamente proporciona información que puede ayudarlo a solucionar problemas relacionados con las actualizaciones de aplicaciones Finance and Operations.

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una función o credenciales específicas.

## <a name="database-synchronization-errors"></a>Errores de sincronización de la base de datos

**Rol requerido para arreglar el error:** Administrador del sistema

Es posible que reciba un mensaje de error similar al siguiente ejemplo cuando intenta utilizar la tabla **DualWriteProjectConfiguration** para actualizar una aplicación Finance and Operations a la Platform update 30.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Para arreglar el problema, siga estos pasos.

1. Inicie sesión en la máquina virtual (VM) para la aplicación Finance and Operations.
2. Abra Visual Studio como administrador y abra el Árbol de objetos de aplicación (AOT).
3. Buscar **DualWriteProjectConfiguration**.
4. En el AOT, haga clic derecho en **DualWriteProjectConfiguration** y seleccione **Agregar al nuevo proyecto**. Seleccione **Aceptar** para crear el nuevo proyecto que usa opciones predeterminadas.
5. En el Explorador de soluciones, haga clic con el botón derecho en **Propiedades del proyecto** y establezca **Sincronizar base de datos en la compilación** a **Verdadero**.
6. Compile el proyecto y confirme que la compilación es exitosa.
7. En el menú **Dynamics 365**, seleccione **Sincronizar base de datos**.
8. Seleccione **Sincronizar** para hacer una sincronización completa de la base de datos.
9. Después de que la sincronización completa de la base de datos sea exitosa, vuelva a ejecutar el paso de sincronización de la base de datos en Microsoft Dynamics Lifecycle Services (LCS) y use los scripts de actualización manual según corresponda, para que pueda continuar con la actualización.

## <a name="missing-table-columns-issue-on-maps"></a>Problema de columnas de tabla faltantes en asignaciones

**Rol requerido para arreglar el error:** Administrador del sistema

En la página **Doble escritura**, puede recibir un mensaje de error similar al siguiente ejemplo:

*Falta el campo de origen \<field name\> en el esquema*.

![Ejemplo del mensaje de error de la columna fuente faltante.](media/error_missing_field.png)

Para solucionar el problema, primero siga estos pasos para asegurarse de que las columnas estén en la tabla.

1. Inicie sesión en la máquina virtual para la aplicación Finance and Operations.
2. Vaya a **Espacios de trabajo \> Administración de datos**, seleccione el mosaico **Parámetros de marco**, y luego, en la pestaña **Configuración de tabla**, seleccione **Actualizar lista de tablas** para actualizar las tablas.
3. Vaya a **Espacios de trabajo \> Administración de datos**, seleccione la pestaña **Tablas de datos** y asegúrese de que la tabla esté en la lista. Si la tabla no aparece en la lista, inicie sesión en la máquina virtual para la aplicación Finance and Operations y asegúrese de que la tabla esté disponible.
4. Abra la página **Asignación de tablas** de la página **Doble escritura** en la aplicación Finance and Operations.
5. Seleccione **Actualizar lista de tablas** para completar automáticamente las columnas en las asignaciones de tablas.

Si el problema aún no se soluciona, siga estos pasos.

> [!IMPORTANT]
> Estos pasos lo guían a través del proceso de eliminar una tabla y luego agregarla nuevamente. Para evitar problemas, asegúrese de seguir los pasos exactamente.

1. En la aplicación Finance and Operations, vaya a **Espacios de trabajo \> Gestión de datos** y seleccione el mosaico **Tablas de datos**.
2. Encuentre la tabla a la que le falta el atributo. Haga clic en **Modificar asignación de destino** en la barra de herramientas.
3. En el panel **Asignar ubicación provisional a destino**, haga clic en **Generar asignación**.
4. Abra la página **Asignación de tablas** de la página **Doble escritura** en la aplicación Finance and Operations.
5. Si el atributo no se rellena automáticamente en la asignación, agréguelo manualmente haciendo clic en el botón **Agregar atributo** y luego haga clic en **Guardar**. 
6. Seleccione la asignación y haga clic en **Ejecutar**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
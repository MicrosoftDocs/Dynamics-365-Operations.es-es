---
title: Solucionar problemas de sincronización en vivo
description: Este tema proporciona información para la solución de problemas que puede ayudarlo a solucionar problemas con la sincronización en vivo.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 82bdcc71196c22689cc65601f98187aaa9e5e9d6
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997311"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Solucionar problemas de sincronización en vivo

[!include [banner](../../includes/banner.md)]



Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service. Proporciona información específica que puede ayudarlo a solucionar problemas con la sincronización en vivo.

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una función o credenciales específicas.

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a>La sincronización en vivo arroja un error prohibido 403 cuando crea un registro en una aplicación Finance and Operations

Es posible que reciba el siguiente mensaje de error cuando crea un registro en una aplicación Finance and Operations:

*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"El usuario no es miembro de la organización.\\"}}\], El servidor remoto devolvió un error: (403) Prohibido."}}".*

Para solucionar el problema, siga los pasos en [Requisitos del sistema y requisitos previos](requirements-and-prerequisites.md). Para completar esos pasos, los usuarios de la aplicación de doble escritura que se crea en Common Data Service deben tener el rol de administrador del sistema. El equipo propietario predeterminado también debe tener el rol de administrador del sistema.

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a>La sincronización en vivo para cualquier entidad genera de forma regular un error similar cuando crea un registro en una aplicación Finance and Operations

**Rol requerido para arreglar el error:** Administrador del sistema

Es posible que reciba un mensaje de error como el siguiente cada vez que intente guardar datos de entidad en una aplicación Finance and Operations:

*No se pueden guardar los cambios en la base de datos. La unidad de trabajo no puede confirmar la transacción. No se pueden escribir datos en la entidad uoms. Las escrituras en UnitOfMeasureEntity fallaron con el mensaje de error No se puede sincronizar con las entidades uoms.*

Para solucionar el problema, debe asegurarse de que los datos de referencia de requisitos previos existan en la aplicación Finance and Operations y Common Data Service. Por ejemplo, si el cliente en el que está en la aplicación Finance and Operations pertenece a un grupo de clientes específico, asegúrese de que el grupo de clientes exista en Common Data Service.

Si existen datos en ambos lados y ha confirmado que el problema no está relacionado con los datos, siga estos pasos.

1. Detener la entidad relacionada.
2. Inicie sesión en la aplicación de Finance and Operations y asegúrese de que existan registros para la entidad que falla en las tablas DualWriteProjectConfiguration y DualWriteProjectFieldConfiguration. Por ejemplo, así es como se ve la consulta si la entidad **Clientes** está fallando.

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. Si hay registros para la entidad anómala incluso después de detener la asignación de la entidad, elimine los registros relacionados con la entidad anómala. Tome nota de la columna **projectname** en la tabla DualWriteProjectConfiguration y obtenga el registro en la tabla DualWriteProjectFieldConfiguration utilizando el nombre del proyecto para eliminar el registro.
4. Inicie la asignación de la entidad. Valide si los datos se sincronizan sin ningún problema.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Gestionar errores de privilegio de lectura o escritura cuando crea datos en una aplicación Finance and Operations

Es posible que reciba un mensaje de error "Solicitud incorrecta" similar al siguiente ejemplo cuando crea datos en una aplicación Finance and Operations

![Ejemplo del mensaje de error de solicitud incorrecta](media/error_record_id_source.png)

Para solucionar el problema, debe asignar la función de seguridad correcta al equipo de la unidad de negocio asignada a Dynamics 365 Sales o Dynamics 365 Customer Service para habilitar el privilegio faltante.

1. En la aplicación Finance and Operations, busque la unidad de negocio que está asignada en el conjunto de conexión de integración de datos.

    ![Asignación de la organización](media/mapped_business_unit.png)

2. Inicie sesión en el entorno en la aplicación basada en modelos en Dynamics 365, vaya a **Configuración \> Seguridad** y encuentre el equipo de la unidad de negocio asignada.

    ![Equipo de la unidad de negocio asignada](media/setting_security_page.png)

3. Abra la página para que el equipo la edite y luego seleccione **Administrar roles** para abrir la ventana de diálogo **Administrar roles de equipo**.

    ![Botón de administrar roles](media/manage_team_roles.png)

4. Asigne el rol que tiene el privilegio de lectura / escritura para las entidades relevantes y luego seleccione **Aceptar**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a>Solucione problemas de sincronización en un entorno que ha cambiado recientemente el entorno Common Data Service

**Rol requerido para arreglar el error:** Administrador del sistema

Es posible que reciba el siguiente mensaje de error cuando crea datos en una aplicación Finance and Operations:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":" **No se puede generar la carga útil para la entidad CustCustomerV3Entity** ","logDateTime":" 2019-08-27T18:51:52.5843124Z","verboseError":"Error en la creación de la carga útil con error URI no válido: el URI está vacío".}\], isErrorCountUpdated":true}*

Este es el aspecto del error en la aplicación basada en modelos en Dynamics 365:

*Se produjo un error inesperado del código ISV. (ErrorType = ClientError) Excepción inesperada del complemento (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: no se pudo procesar la cuenta de la entidad - (Un intento de conexión falló porque la parte conectada no respondió correctamente después de un período de tiempo, o la conexión establecida falló porque el anfitrión conectado no pudo responder).*

Este error ocurre cuando el entorno Common Data Service se restablece incorrectamente al mismo tiempo que intenta crear datos en la aplicación Finance and Operations.

Para arreglar el problema, siga estos pasos.

1. Inicie sesión en la máquina virtual (VM) Finance and Operations, abra SQL Server Management Studio (SSMS) y busque registros en la tabla DUALWRITEPROJECTCONFIGURATIONENTITY donde **internalentityname** es igual a **Clientes V3** y **externalentityname** es igual a **cuentas**. Así es como se ve la consulta.

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. Use el nombre del proyecto de los resultados de la consulta anterior para ejecutar la siguiente consulta.

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. Asegúrese de que la columna **externalenvironmentURL** tiene el Common Data Service o URL de la aplicación correctos. Elimine cualquier registro duplicado que apunte al error Common Data Service URL. Elimine los registros correspondientes en las tablas DUALWRITEPROJECTFIELDCONFIGURATION y DUALWRITEPROJECTCONFIGURATION.
4. Detenga la asignación de entidad y luego reiníciela

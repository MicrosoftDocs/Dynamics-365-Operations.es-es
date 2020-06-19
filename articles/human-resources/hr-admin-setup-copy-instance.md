---
title: Copiar una instancia
description: Puede utilizar los servicios Microsoft Dynamics Lifecycle Services (LCS) para copiar una base de datos de Microsoft Dynamics 365 Human Resources en un entorno de espacio retirado.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8385b7dfcd1d7294542c7f54f609b26b7988ac4
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431254"
---
# <a name="copy-an-instance"></a>Copiar una instancia

Puede utilizar los servicios Microsoft Dynamics Lifecycle Services (LCS) para copiar una base de datos de Microsoft Dynamics 365 Human Resources en un entorno de espacio retirado. Si tiene otro entorno de espacio retirado, también puede copiar la base de datos del entorno a un entorno de espacio aislado destinado.

Para copiar una instancia, debe asegurarse de lo siguiente:

- La instancia de Human Resources que desea sobrescribir debe ser un entorno de espacio aislado.

- Los entornos desde los que está copiando deben estar en la misma región. No puede copiar entre regiones.

- Debe ser un administrador en el entorno de destino para poder iniciar sesión después de copiar la instancia.

- Cuando copia la base de datos de Human Resources, no copia los elementos (aplicaciones o datos) contenidos en un entorno de Microsoft PowerApps. Para obtener información sobre cómo copiar elementos en un entorno de PowerApps, vea [Copiar un entorno](https://docs.microsoft.com/power-platform/admin/copy-environment). El entorno de PowerApps que desea sobrescribir debe ser un entorno de espacio aislado. Debe ser un administrador global de inquilinos para cambiar un entorno de producción de PowerApps a un entorno de espacio aislado. Para obtener más información sobre cómo cambiar un entorno de PowerApps, vea [Cambiar una instancia](https://docs.microsoft.com/dynamics365/admin/switch-instance).

## <a name="effects-of-copying-a-human-resources-database"></a>Efectos de copiar una base de datos de Human Resources

Los siguientes eventos ocurren cuando copia una base de datos de Human Resources:

- El proceso de copia borra la base de datos existente en el entorno de destino. Una vez que se completa el proceso de copia, no puede recuperar la base de datos existente.

- El entorno de destino no estará disponible hasta que se complete el proceso de copia.

- Los documentos de almacenamiento en blobs de Microsoft Azure no se copian de un entorno a otro. Por lo tanto, los documentos y plantillas que se adjunten no se copiarán y permanecerán en el entorno de origen.

- Se deshabilitarán todos los usuarios, excepto el usuario Admin, y otras cuentas de usuario de servicio interno no estarán disponibles. Por lo tanto, el usuario administrador puede eliminar u ofuscar datos antes de permitir que otros usuarios vuelvan al sistema.

- El usuario administrador debe realizar los cambios de configuración necesarios, como volver a conectar los puntos finales de integración a servicios o URL específicos.

## <a name="copy-the-human-resources-database"></a>Copiar la base de datos de Human Resources

Para completar esta tarea, primero copie una instancia y luego inicie sesión en el Centro de administración de Microsoft Power Platform para copiar su entorno de PowerApps.

> [!WARNING]
> Cuando copia una instancia, la base de datos se borra en la instancia de destino. La instancia de destino no está disponible durante este proceso.

1. Inicie sesión en LCS y seleccione el proyecto LCS que contiene la instancia que desea copiar.

2. En su proyecto de LCS seleccione el mosaico **Gestión de la app Human Resources**.

3. Seleccione la instancia que se debe copiar y, a continuación, seleccione **Copiar**.

4. En el panel de tareas **Copiar una instancia**, seleccione la instancia para sobrescribir y luego seleccione **Copiar**. Espere a que el valor del campo **Estado de copia** se actualice a **Terminado**.

   ![[Seleccionar instancia para sobrescribir](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Seleccione **Power Platform** e inicie sesión en el Centro de administración de Microsoft Power Platform.

   ![[Seleccione Power Platform](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Seleccione el entorno de PowerApps para copiar y luego seleccione **Copiar**.

7. Cuando se complete el proceso de copia, inicie sesión en la instancia de destino y habilite la integración con Common Data Service. Para obtener más información e instrucciones, consulte [Configurar la integración de Common Data Service](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).

## <a name="data-elements-and-statuses"></a>Elementos de datos y estados

Los siguientes elementos de datos no se copian cuando copia una instancia de Human Resources:

- Direcciones de correo electrónico en la tabla **LogisticsElectronicAddress**

- Historial de trabajos por lotes en las tablas **BatchJobHistory**, **BatchHistory** y **BatchConstraintHistory**

- Contraseña del Protocolo simple de transferencia de correo (SMTP) en la tabla **SysEmailSMTPPassword**

- El servidor de retransmisión SMTP en la tabla **SysEmailParameters**

- Configuración de gestión de impresión en las tablas **PrintMgmtSettings** y **PrintMgmtDocInstance**

- Registros específicos del entorno en las tablas **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** y **BatchServerGroup**

- Documentos adjuntos en la tabla DocuValue Estos archivos adjuntos incluyen cualquier plantilla de Microsoft Office que se sobrescribió en el entorno de origen.

- La cadena de conexión en la tabla **PersonnelIntegrationConfiguration**

Algunos de estos elementos no se copian porque son específicos del entorno. Algunos ejemplos son los registros **BatchServerConfig** y **SysCorpNetPrinters**. Otros elementos no se copian debido al volumen de incidencias de soporte. Por ejemplo, se pueden enviar correos electrónicos duplicados porque SMTP todavía está habilitado en el entorno de pruebas de aceptación del usuario (sandbox), se pueden enviar mensajes de integración no válidos porque los trabajos por lotes aún están habilitados y los usuarios pueden habilitarse antes de que los administradores puedan realizar acciones de limpieza posteriores a la actualización.

Además, los siguientes estados cambian cuando copia una instancia:

- Todos los usuarios, excepto el administrador, están establecidos en **Deshabilitado**.

- Todos los trabajos por lotes, excepto algunos trabajos del sistema, están configurados como **Retener**.

## <a name="environment-admin"></a>Administración del entorno

Todos los usuarios del entorno de espacio aislado de destino, incluidos los administradores, son reemplazados por los usuarios del entorno de origen. Antes de copiar una instancia, asegúrese de ser administrador en el entorno de destino. Si no lo está, no podrá iniciar sesión en el entorno de espacio aislado de destino una vez que se haya completado la copia.

Todos los usuarios que no son administradores en el entorno de espacio aislado de destino están deshabilitados para evitar inicios de sesión no deseados en el entorno de espacio aislado. Los administradores pueden volver a habilitar a los usuarios si es necesario.

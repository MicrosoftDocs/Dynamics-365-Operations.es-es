---
title: Actualizar al modelo de parte y libreta de direcciones global
description: Este tema describe cómo actualizar datos de escritura dual al modelo de libreta de direcciones global y de grupo.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 673c3a68e2eccdabdfc2df281389537297ec3524bee5e744e910c50d38b8d298
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720697"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Actualizar al modelo de parte y libreta de direcciones global

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

La [Plantilla de Microsoft Azure Data Factory](https://aka.ms/dual-write-gab-adf) le ayuda a actualizar los datos de tabla **Cuenta**, **Contacto** y **Proveedor** en escritura dual en el modelo de libreta de direcciones global y de grupo. La plantilla reconcilia los datos de aplicaciones de aplicaciones Finance and Operations y aplicaciones Customer Engagement. Al final del proceso, los campos **Parte** y **Contacto** de registros de **Parte** se crearán y asociarán con los registros **Cuenta**, **Contacto** y **Vendedor** en aplicaciones de participación del cliente. Un archivo .csv (`FONewParty.csv`) se genera para crear nuevos registros de **Parte** dentro de la aplicación Finance and Operations. Este tema proporciona instrucciones sobre cómo usar la plantilla de Data Factory y actualizar sus datos.

Si no tiene ninguna personalización, puede usar la plantilla tal cual. Si tiene personalizaciones para **Cuenta**, **Contacto** y **Vendedor**, debe modificar la plantilla siguiendo las siguientes instrucciones.

> [!NOTE]
> La plantilla solo actualiza los datos de **Parte**. En una versión futura, se incluirán direcciones postales y electrónicas.

## <a name="prerequisites"></a>Requisitos previos

Se requieren los siguientes requisitos previos para actualizar al modelo de libreta de direcciones global y de grupo:

+ [Suscripción a Azure](https://portal.azure.com/)
+ [Acceso a la plantilla](https://aka.ms/dual-write-gab-adf)
+ Debe ser un cliente de escritura dual existente.

## <a name="prepare-for-the-upgrade"></a>Prepararse para la actualización
Se necesitan las siguientes actividades para prepararse para la actualización:

+ **Totalmente sincronizado**: ambos entornos están en un estado completamente sincronizado para **Cuenta (cliente)**, **Contacto** y **Proveedor**.
+ **Claves de integración**: las tablas **Cuenta (cliente)**, **Contacto** y **Vendedor** de las aplicaciones de interacción con el cliente utilizan las claves de integración que se envían listas para usar. Si personalizó las claves de integración, debe personalizar la plantilla.
+ **Número de parte**: todos los registros de **Cuenta (cliente)**, **Contacto** y **Vendedor** que se actualizarán tienen un número de **Parte**. Los registros sin número de **Parte** se ignorarán. Si desea actualizar esos registros, agregue un número de **Parte** antes de iniciar el proceso de actualización.
+ **Interrupción del sistema**: durante el proceso de actualización, deberá desconectar los entornos de Finance and Operations y entornos sin conexión Customer Engagement.
+ **Instantánea**: toma instantáneas de aplicaciones de Finance and Operaciones y aplicaciones Customer Engagement. Utilice las instantáneas para restaurar el estado anterior si es necesario.

## <a name="deployment"></a>Implementación

1. Descarga la plantilla de [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).

2. Inicie sesión en [Microsoft Azure](https://portal.azure.com/).

3. Cree un [grupo de recursos](/azure/azure-resource-manager/management/manage-resource-groups-portal).

4. Cree una [cuenta de almacenamiento](/azure/storage/common/storage-account-create?tabs=azure-portal) en el grupo de recursos que creó.

5. Cree una [factoría de datos](/azure/data-factory/quickstart-create-data-factory-portal) en el grupo de recursos anterior que creó.

6. Abra la fábrica de datos y seleccione el mosaico **Autor y monitor**.

7. Sobre la pestaña **Gestionar**, seleccione **Plantilla ARM**.

8. Seleccione **Importar plantilla ARM** para importar la plantilla de **Parte**.

9. Importe la plantilla a la factoría de datos. Ingrese los siguientes valores para **Detalles del proyecto** y **Detalles de la instancia**.

    Campo | Valor
    ---|---
    Suscripción | Suscripción a Azure
    Grupo de recursos | Proporcione el mismo recurso con el que se crea la cuenta de almacenamiento.
    Región | Especifique la región.
    Nombre de la fábrica | Especifique el nombre de la fábrica.
    FO Linked Service_service Clave principal | Especifique la clave de la aplicación.
    Cadena de conexión de Azure Blob Storage | Cadena de conexión de Azure Blob Storage.
    Contraseña de servicio vinculado de Dynamics CRM | La contraseña de la cuenta de usuario que especificó como nombre de usuario.
    FO Linked Service_properties_type Properties_url  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    FO Linked Service_properties_type Properties_tenant | Especifique la información del inquilino (nombre de dominio o ID de inquilino) bajo la cual reside su aplicación.
    FO Linked Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com`
    FO Linked Service_properties_type Properties_service Principal Id | Especifique el Id. de cliente de la aplicación.
    Dynamics Crm Linked Service_properties_type Properties_username | El nombre de usuario para conectarse a Dynamics 365.

    Para obtener más información, consulte los temas siguientes: 
    
    - [Promocionar manualmente una plantilla de Resource Manager para cada entorno](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Propiedades de servicios vinculados](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Copiar datos con Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Después de la implementación, valide los conjuntos de datos, el flujo de datos y el servicio vinculado de la factoría de datos.

   ![Conjuntos de datos, flujo de datos y servicio vinculado.](media/data-factory-validate.png)

11. Navegar a **Gestionar**. Debajo de **Conexiones**, seleccione **Servicio vinculado**. Seleccione **DynamicsCrmLinkedService**. En el formulario **Editar servicio vinculado (Dynamics CRM)**, ingrese los siguientes valores.

    Campo | Valor
    ---|---
    Nombre | DynamicsCrmLinkedService
    Descripción | Servicios vinculados para conectarse con la instancia de CRM para obtener datos de entidades
    Conectarse a través del tiempo de ejecución de integración | AutoResolvelntegrationRuntime
    Tipo de implementación | En línea
    URI del servicio | `https://<organization-name>.crm[x].dynamics.com`
    Tipo de autenticación | Office365
    Nombre de usuario |
    Contraseña o Azure Key Vault | Contraseña
    Contraseña |

## <a name="run-the-template"></a>Ejecutar la plantilla

1. Detenga las asignaciones de doble escritura de **Cuenta**, **Contacto** y **Proveedor** a continuación usando la aplicación Finance and Operations.

    + Clientes V3 (cuentas)
    + Clientes V3 (contactos)
    + Contactos de CDS V2 (contactos)
    + Contactos de CDS V2 (contactos)
    + Proveedor V2 (msdyn_vendors)

2. Asegúrese de que los mapas se eliminen de la tabla `msdy_dualwriteruntimeconfig` en Dataverse.

3. Instale [Soluciones de libreta de direcciones global y de fiesta de escritura dual](https://aka.ms/dual-write-gab) de AppSource.

4. En la aplicación Finance and Operations, si las siguientes tablas contienen datos, ejecuta **Sincronización inicial** para ellos.

    + Formas de saludo
    + Tipos de carácter personal
    + Cierre de agradecimiento
    + Cargos de persona de contacto
    + Roles de toma de decisiones
    + Niveles de fidelización

5. En la aplicación de interacción con el cliente, desactive los siguientes pasos del complemento.

    + Actualización de cuenta
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: actualización de cuenta
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: actualización de cuenta
    + Actualización de contacto
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: actualización de contacto
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: actualización de contacto
    + Actualización de msdyn_party
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: actualización de msdyn_party
    + Actualización de msdyn_vendor
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: actualización de msdyn_vendor

6. En la aplicación de interacción con el cliente, desactive los siguientes flujos de trabajo:

    + Crear proveedores en la tabla Cuentas
    + Crear proveedores en la tabla Cuentas
    + Crear proveedores de tipo persona en la tabla Contactos
    + Crear proveedores de tipo Persona en la tabla Proveedores
    + Actualizar proveedores en la tabla Cuentas
    + Actualizar proveedores en la tabla Proveedores
    + Actualizar proveedores de tipo Persona en la tabla Contactos
    + Actualizar proveedores de tipo Persona en la tabla Proveedores

7. En la factoría de datos, ejecute la plantilla seleccionando **Activar ahora** como se muestra en la siguiente imagen. Este proceso puede tardar algunas horas en completarse según el volumen de datos.

    ![Ejecución de desencadenador.](media/data-factory-trigger.png)

    > [!NOTE]
    > Si tiene personalizaciones para **Cuenta**, **Contacto** y **Proveedor**, debe modificar la plantilla.

8. Importe los nuevos registros de **Parte** en la aplicación Finance and Operations.

    + Descargue el archivo `FONewParty.csv` de Azure Blob Storage. La ruta es `partybootstrapping/output/FONewParty.csv`.
    + Convierta el archivo `FONewParty.csv` en un archivo de Excel e importe el archivo de Excel en la aplicación de Finances and Operations. Si la importación de csv funciona para usted, puede importar el archivo csv directamente. La importación puede tardar unas horas en ejecutarse, según el volumen de datos. Para obtener más información, consulte [Resumen de trabajos de importación y exportación de datos](../data-import-export-job.md).

    ![Importar los registros del partido de Datavers.](media/data-factory-import-party.png)

9. En la aplicación de interacción con el cliente, habilite los siguientes pasos del complemento:

    + Actualización de cuenta
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: actualización de cuenta
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: actualización de cuenta
    + Actualización de contacto
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: actualización de contacto
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: actualización de contacto
    + Actualización de msdyn_party
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: actualización de msdyn_party
    + Actualización de msdyn_vendor
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: actualización de msdyn_vendor

10. En las aplicaciones de participación del cliente, active los siguientes flujos de trabajo si los desactivó en los pasos anteriores:

    + Crear proveedores en la tabla Cuentas
    + Crear proveedores en la tabla Cuentas
    + Crear proveedores de tipo persona en la tabla Contactos
    + Crear proveedores de tipo Persona en la tabla Proveedores
    + Actualizar proveedores en la tabla Cuentas
    + Actualizar proveedores en la tabla Proveedores
    + Actualizar proveedores de tipo Persona en la tabla Contactos
    + Actualizar proveedores de tipo Persona en la tabla Proveedores

11. Ejecute los mapas relacionados con la **Parte** como se indica en [Parte y libreta de direcciones global](party-gab.md).

## <a name="troubleshooting"></a>Solución de problemas

1. Si el proceso falla, vuelva a ejecutar la factoría de datos a partir de la actividad fallida.
2. La factoría de datos genera algunos archivos que puede utilizar con fines de validación de datos.
3. La factoría de datos se ejecuta en función de archivos csv delimitados por comas. Si hay un valor de campo que tiene una coma, puede interferir con los resultados. Necesitas quitar las comas.
4. La pestaña **Supervisión** proporciona información sobre todos los pasos y datos procesados. Seleccione un paso específico para depurarlo.

    ![Pestaña de seguimiento.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>Más información sobre la plantilla

Puede encontrar información adicional sobre la plantilla en [Comentarios para el archivo Léame de la plantilla de Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).

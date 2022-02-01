---
title: Actualizar al modelo de parte y libreta de direcciones global
description: Este tema describe cómo actualizar datos de escritura dual al modelo de libreta de direcciones global y de grupo.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: eaafe8d98049cb8838317396f28e9d6ca720a677
ms.sourcegitcommit: 08dcbc85e372d4e4fb3ba64389f6d5051212c212
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2022
ms.locfileid: "8015724"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Actualizar al modelo de parte y de libreta de direcciones global

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Las [plantillas de Microsoft Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema) ayudan a actualizar los siguientes datos existentes en escritura dual en el modelo de libreta de direcciones global y de parte: los datos de las tablas **Cuenta**, **Contacto** y **Vendedor**, y las direcciones postales y electrónicas.

Se proporcionan las siguientes tres plantillas de Data Factory. Ayudan a conciliar los datos de las aplicaciones de Finanzas y Operaciones y de las de Customer Engagement.

- **[Plantilla de parte](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/arm_template.json) (Actualizar datos al esquema Party-GAB de escritura dual/arm_template.json)** - Esta plantilla ayuda a actualizar los datos de **Parte** y **Contacto** que están asociados con datos de **Cuenta**, **Contacto** y **Vendedor**.
- **[Plantilla de dirección postal de parte](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Postal%20Address%20-%20GAB/arm_template.json) (Actualizar los datos al esquema Party-GAB de escritura dual/Actualizar a la dirección postal de Parte - GAB/arm_template.json)** - Esta plantilla ayuda a actualizar las direcciones postales asociadas con los datos de **Cuenta**, **Contacto** y **Vendedor**.
- **[Plantilla de dirección electrónica de parte](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Electronic%20Address%20-%20GAB/arm_template.json) (Actualizar los datos al esquema Party-GAB de escritura dual/Actualizar a la dirección electrónica de Parte - GAB/arm_template.json)** - Esta plantilla ayuda a actualizar las direcciones electrónicas asociadas con los datos de **Cuenta**, **Contacto** y **Vendedor**.

Al final del proceso, se generan los siguientes archivos de valores separados por comas (.csv).

| Nombre de archivo | Propósito |
|---|---|
| FONewParty.csv | Este archivo ayuda a crear nuevos registros de **Entidad** dentro de la aplicación de Finanzas y Operaciones. |
| ImportFONewPostalAddressLocation.csv | Este archivo ayuda a crear nuevos registros **Ubicación de dirección postal** en la aplicación de Finanzas y Operaciones. |
| ImportFONewPartyPostalAddress.csv | Este archivo ayuda a crear nuevos registros **Dirección postal de la parte** en la aplicación de Finanzas y Operaciones. |
| ImportFONewPostalAddress.csv | Este archivo ayuda a crear nuevos registros **Dirección postal** en la aplicación de Finanzas y Operaciones. |
| ImportFONewElectronicAddress.csv | Este archivo ayuda a crear nuevos registros **Dirección electrónica** en la aplicación de Finanzas y Operaciones. |

Este tema explica cómo usar las plantillas de Data Factory y actualizar sus datos. Si no tiene ninguna personalización, puede usar las plantillas tal cual. Sin embargo, si tiene personalizaciones para datos de **Cuenta**, **Contacto** y **Vendedor**, debe modificar las plantillas como se describe en este tema.

> [!IMPORTANT]
> Hay instrucciones especiales para ejecutar la dirección postal de la Parte y las plantillas de dirección electrónica de la Parte. Primero debe ejecutar la plantilla de Parte, luego la plantilla de dirección postal de la Parte y luego la plantilla de dirección electrónica de la Parte. Cada plantilla está diseñada para importarse en una factoría de datos separada.

## <a name="prerequisites"></a>Requisitos previos

Debe cumplir los siguientes requisitos previos para actualizar al modelo de libreta de direcciones global y de grupo:

+ Debe tener una [suscripción de Azure](https://portal.azure.com/).
+ Debe tener acceso a [las plantillas](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
+ Debe ser un cliente de escritura dual existente.

## <a name="prepare-for-the-upgrade"></a>Prepararse para la actualización

Una actualización requiere la siguiente preparación:

+ **Sincronización completa:** Tanto el entorno de Finance and Operations como el entorno de participación del cliente se encuentran en un estado completamente sincronizado para las tablas **Cuenta (cliente)**, **Contacto** y **Vendedor**.
+ **Claves de integración**: las tablas **Cuenta (cliente)**, **Contacto** y **Vendedor** de las aplicaciones de interacción con el cliente utilizan las claves de integración predefinidas. Si personalizó las claves de integración, debe personalizar la plantilla.
+ **Número de parte:** todos los registros de **Cuenta (cliente)**, **Contacto** y **Vendedor** que se actualizarán tienen un número de parte. Se ignorarán los registros que no tengan un número de parte. Si desea actualizar esos registros, agregue un número de parte antes de iniciar el proceso de actualización.
+ **Interrupción del sistema**: durante el proceso de actualización, deberá desconectar los entornos de Finance and Operations y entornos sin conexión de participación del cliente.
+ **Instantánea**: toma una instantánea de aplicaciones de Finance and Operaciones y aplicaciones Customer Engagement. A continuación podrá utilizar las instantáneas para restaurar el estado anterior si es necesario.

## <a name="deployment"></a>Implementación

1. Descarga las plantillas de [Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
2. Inicie sesión en el [portal de Azure](https://portal.azure.com/).
3. Cree un [grupo de recursos](/azure/azure-resource-manager/management/manage-resource-groups-portal).
4. Cree una [cuenta de almacenamiento](/azure/storage/common/storage-account-create?tabs=azure-portal) en el grupo de recursos que creó.
5. Cree una [factoría de datos](/azure/data-factory/quickstart-create-data-factory-portal) en el grupo de recursos anterior que creó.
6. Abra la fábrica de datos y seleccione el icono **Autor y monitor**.
7. Sobre la pestaña **Gestionar**, seleccione **Plantilla ARM**.
8. Seleccione **Importar plantilla ARM** para importar la plantilla de **Parte**.
9. Importe la plantilla a la factoría de datos. Ingrese los siguientes valores para **Detalles del proyecto** y **Detalles de la instancia**.

    | Campo | Valor |
    |---|---|
    | Suscripción | La suscripción a Azure |
    | Grupo de recursos | Proporcione el mismo recurso con el que se crea la cuenta de almacenamiento. |
    | Región | La región |
    | Nombre de la fábrica | El nombre de fábrica |
    | FO Linked Service_service Clave principal | La clave de la aplicación |
    | Cadena de conexión de Azure Blob Storage | La cadena de conexión de Azure Blob Storage |
    | Contraseña de servicio vinculado de Dynamics CRM | La contraseña de la cuenta de usuario que especifica como nombre de usuario |
    | FO Linked Service_properties_type Properties_url | `https://sampledynamics.sandbox-operationsdynamics.com/data` |
    | FO Linked Service_properties_type Properties_tenant | Información (nombre de dominio o ID de inquilino) del inquilino bajo el cual reside su aplicación |
    | FO Linked Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com` |
    | FO Linked Service_properties_type Properties_service Principal Id | El Id. de cliente de la aplicación |
    | Dynamics Crm Linked Service_properties_type Properties_username | El nombre de usuario que se utiliza para conectarse a Dynamics 365 |

    Para obtener más información, consulte los siguientes temas:

    - [Promocionar manualmente una plantilla de Resource Manager para cada entorno](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Propiedades de servicios vinculados](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Copiar datos con Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Después de la implementación, valide los conjuntos de datos, el flujo de datos y el servicio vinculado de la factoría de datos.

    ![Conjuntos de datos, flujo de datos y servicio vinculado.](media/data-factory-validate.png)

11. Vaya a **Gestionar**. Debajo de **Conexiones**, seleccione **Servicio vinculado**. A continuación, seleccione **DynamicsCrmLinkedService**. En el cuadro de diálogo **Editar servicio vinculado (Dynamics CRM)**, ingrese los siguientes valores.

    | Campo | Valor |
    |---|---|
    | Name | DynamicsCrmLinkedService |
    | Descripción | Servicios vinculados para conectarse con la instancia de CRM para obtener datos de entidades |
    | Conectarse a través del tiempo de ejecución de integración | AutoResolvelntegrationRuntime |
    | Tipo de implementación | En línea |
    | URI del servicio | `https://<organization-name>.crm[x].dynamics.com` |
    | Tipo de autenticación | Office365 |
    | Nombre de usuario | |
    | Contraseña o Azure Key Vault | Contraseña |
    | Contraseña | |

## <a name="prepare-to-run-the-data-factory-templates"></a>Prepárese para ejecutar las plantillas de Data Factory

Esta sección describe la configuración que se requiere antes de ejecutar las plantillas de Data Factory de dirección postal de la Parte y dirección electrónica de la Parte.

### <a name="setup-to-run-the-party-postal-address-template"></a>Configuración para ejecutar la plantilla de dirección postal de la Parte

1. Inicie sesión en las aplicaciones de interacción con el cliente y vaya a **Configuración** \> **Configuración de personalización**. A continuación, en la pestaña **General**, configure la zona horaria para la cuenta de administrador del sistema. La zona horaria debe estar en la Hora universal coordinada (UTC) para actualizar las fechas "válido desde" y "válido hasta" de las direcciones postales de las aplicaciones de Finanzas y Operaciones.

    ![Configuración de zona horaria para la cuenta de administrador del sistema.](media/ADF-1.png)

2. En Data Factory, en la pestaña **Administrar**, en **Parámetros globales**, cree el siguiente parámetro global.

    | Número | Name | Tipo | Valor |
    |---|---|---|---|
    | 1 | PostalAddressIdPrefix | cadena | Este parámetro agrega un número de serie a las direcciones postales recién creadas como prefijo. Asegúrese de proporcionar una cadena que no entre en conflicto con las direcciones postales en aplicaciones de Finanzas y Operaciones y aplicaciones de Customer Engagement. Por ejemplo, use **ADF-PAD-**. |

    ![Parámetro global PostalAddressIdPrefix creado en la pestaña Administrar.](media/ADF-2.png)

3. Cuando haya terminado, seleccione **Publicar todo**.

    ![Botón Publicar todo.](media/ADF-3.png)

### <a name="setup-to-run-the-party-electronic-address-template"></a>Configuración para ejecutar la plantilla de dirección electrónica de la Parte

1. En Data Factory, en la pestaña **Administrar**, en **Parámetros globales**, cree los siguientes parámetros globales.

    | Número | Name | Tipo | Valor |
    |---|---|---|---|
    | 1 | IsFOSource | bool | Este parámetro determina qué direcciones del sistema principal se reemplazan en caso de conflictos. Si el valor es **true**, las direcciones principales en las aplicaciones Finanzas y Operaciones reemplazarán las direcciones principales en las aplicaciones de Customer Engagement. Si el valor es **false**, las direcciones principales en las aplicaciones Customer Engagement reemplazarán las direcciones principales en las aplicaciones de Finanzas y Operaciones. |
    | 2 | ElectronicAddressIdPrefix | cadena | Este parámetro agrega un número de serie a las direcciones electrónicas recién creadas como prefijo. Asegúrese de proporcionar una cadena que no entre en conflicto con las direcciones electrónicas en aplicaciones de Finanzas y Operaciones y aplicaciones de Customer Engagement. Por ejemplo, use **ADF-EAD-**. |

    ![Parámetros globales IsFOSource y ElectronicAddressIdPrefix creados en la pestaña Administrar.](media/ADF-4.png)

2. Cuando haya terminado, seleccione **Publicar todo**.

## <a name="run-the-templates"></a>Ejecutar las plantillas

1. Detenga las asignaciones de doble escritura de **Cuenta**, **Contacto** y **Proveedor** a continuación que usan la aplicación Finanzas y Operaciones:

    + Clientes V3 (cuentas)
    + Clientes V3 (contactos)
    + Contactos de CDS V2 (contactos)
    + Contactos de CDS V2 (contactos)
    + Proveedor V2 (msdyn_vendors)

2. Asegúrese de que las asignaciones se eliminen de la tabla **msdy_dualwriteruntimeconfig** en Dataverse.
3. Instale [Soluciones de libreta de direcciones global y de fiesta de escritura dual](https://aka.ms/dual-write-gab) de AppSource.
4. En la aplicación Finanzas y Operaciones, si las siguientes tablas contienen datos, ejecute **Sincronización inicial**:

    + Formas de saludo
    + Tipos de carácter personal
    + Cierre de agradecimiento
    + Cargos de persona de contacto
    + Roles de toma de decisiones
    + Niveles de fidelización

5. En la aplicación de interacción con el cliente, desactive los siguientes pasos del complemento:

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

    + Customeraddress

        + Crear

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: creación de customeraddress

        + Actualizar

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: actualización de customeraddress

        + Suprimir

            + Microsoft.Dynamics.GABExtended.Plugins.DeleteCustomerAddress: eliminación de customeraddress

    + msdyn_partypostaladdress

        + Crear

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: creación de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: creación de msdyn_partypostaladdress

        + Actualizar

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: actualización de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: actualización de msdyn_partypostaladdress

    + msdyn_postaladdress

        + Crear

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: creación de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: creación de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: creación de msdyn_postaladdress

        + Actualizar

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: actualización de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: actualización de msdyn_postaladdress

    + msdyn_partyelectronicaddress

        + Crear

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: creación de msdyn_partyelectronicaddress

        + Actualizar

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: actualización de msdyn_partyelectronicaddress

        + Suprimir

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: eliminación de msdyn_partyelectronicaddress

6. En la aplicación de interacción con el cliente, desactive los siguientes flujos de trabajo:

    + Crear proveedores en la tabla Cuentas
    + Crear proveedores en la tabla Cuentas
    + Crear proveedores de tipo persona en la tabla Contactos
    + Crear proveedores de tipo Persona en la tabla Proveedores
    + Actualizar proveedores en la tabla Cuentas
    + Actualizar proveedores en la tabla Proveedores
    + Actualizar proveedores de tipo Persona en la tabla Contactos
    + Actualizar proveedores de tipo Persona en la tabla Proveedores

7. En la factoría de datos, ejecute la plantilla seleccionando **Activar ahora** como se muestra en la siguiente ilustración. Este proceso puede tardar algunas horas en completarse, según el volumen de datos.

    ![Ejecutar la plantilla.](media/data-factory-trigger.png)

    > [!NOTE]
    > Si tiene personalizaciones para **Cuenta**, **Contacto** y **Vendedor**, debe modificar la plantilla.

8. Importe los nuevos registros de **Parte** en la aplicación Finanzas y Operaciones.

    1. Descargue el archivo **FONewParty.csv** de Azure Blob Storage. La ruta es **partybootstrapping/output/FONewParty.csv**.
    2. Convierta el archivo **FONewParty.csv** en un archivo de Excel e importe el archivo de Excel en la aplicación de Finanzas y Operaciones. Alternativamente, si la importación de CSV funciona para usted, puede importar el archivo .csv directamente. Este paso puede tardar algunas horas en completarse, según el volumen de datos. Para obtener más información, consulte [Resumen de trabajos de importación y exportación de datos](../data-import-export-job.md).

    ![Importar los registros de Parte de Dataverse.](media/data-factory-import-party.png)

9. En la factoría de datos, ejecute las plantillas dirección postal de la Parte y dirección electrónica de la Parte, una tras otra.

    + La plantilla de dirección postal de la Parte actualiza o inserta todos los registros de direcciones postales en la aplicación de interacción con el cliente y los asocia con los correspondientes registros de **Cuenta**, **Contacto** y **Vendedor**. También genera tres archivos .csv: ImportFONewPostalAddressLocation.csv, ImportFONewPartyPostalAddress.csv y ImportFONewPostalAddress.csv.
    + La plantilla de dirección electrónica de la Parte actualiza o inserta todas las direcciones electrónicas en la aplicación de interacción con el cliente y los asocia con los correspondientes registros de **Cuenta**, **Contacto** y **Vendedor**. También genera un archivo .csv: ImportFONewElectronicAddress.csv.

    ![Ejecución de las plantillas de dirección postal y dirección electrónica de la Parte.](media/ADF-7.png)

10. Para actualizar la aplicación de Finanzas y Operaciones con estos datos, debe convertir los archivos .csv en un libro de Excel e [importarlo en la aplicación de Finanzas y Operaciones](/data-entities/data-import-export-job). Alternativamente, si la importación de CSV funciona para usted, puede importar los archivos .csv directamente. Este paso puede tardar algunas horas en completarse, según el volumen.

    ![Importación correcta.](media/ADF-8.png)

11. En la aplicación de interacción con el cliente, habilite los siguientes pasos del complemento:

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

    + msdyn_partypostaladdress

        + Crear

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: creación de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: creación de msdyn_partypostaladdress

        + Actualizar

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: actualización de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: actualización de msdyn_partypostaladdress

    + msdyn_postaladdress

        + Crear

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: creación de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: creación de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: creación de msdyn_postaladdress

        + Actualizar

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: actualización de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: actualización de msdyn_postaladdress
 
    + msdyn_partyelectronicaddress

        + Crear

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: creación de msdyn_partyelectronicaddress

        + Actualizar

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: actualización de msdyn_partyelectronicaddress

        + Suprimir

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: eliminación de msdyn_partyelectronicaddress

12. En la aplicación de participación del cliente, active los siguientes flujos de trabajo si los desactivó anteriormente:

    + Crear proveedores en la tabla Cuentas
    + Crear proveedores en la tabla Cuentas
    + Crear proveedores de tipo persona en la tabla Contactos
    + Crear proveedores de tipo Persona en la tabla Proveedores
    + Actualizar proveedores en la tabla Cuentas
    + Actualizar proveedores en la tabla Proveedores
    + Actualizar proveedores de tipo Persona en la tabla Contactos
    + Actualizar proveedores de tipo Persona en la tabla Proveedores

13. Ejecute los mapas relacionados con registros de la **Parte** como se indica en [Parte y libreta de direcciones global](party-gab.md).

## <a name="explanation-of-the-data-factory-templates"></a>Explicación de las plantillas de Data Factory

Esta sección lo lleva a través de los pasos de cada plantilla de Data Factory.

### <a name="steps-in-the-party-template"></a>Pasos de la plantilla de Parte

1. Los pasos del 1 al 6 identifican las empresas que están habilitadas para escritura dual y crean una cláusula de filtro para ellas.
2. Los pasos 7-1 a 7-9 recuperan datos de aplicación de Finanzas y Operaciones y la aplicación de Customer Engagement, y prepara esos datos para actualizarlos.
3. Los pasos 8 a 9 comparan el número de parte para registros **Cuenta**, **Contacto** y **Proveedor** entre la aplicación de Finanzas y Operaciones y la aplicación de Customer Engagement. Se ignorarán los registros que no tengan un número de parte.
4. El paso 10 genera dos archivos .csv para los registros de la parte que deben crearse en la aplicación de Customer Engagement y la aplicación de Finanzas y Operaciones.

    - **FOCDSParty.csv** - Este archivo contiene todos los registros de parte de ambos sistemas, independientemente de si la empresa está habilitada para escritura dual.
    - **FONewParty.csv** - Este archivo contiene un subconjunto de los registros de parte que Dataverse conoce (por ejemplo, cuentas de tipo **Cliente potencial**).

5. El paso 11 crea las partes en la aplicación de interacción con el cliente.
6. El paso 12 recupera los identificadores únicos globales (GUID) de las partes de la aplicación de participación del cliente y los prepara para que puedan asociarse con registros **Cuenta**, **Contacto** y **Vendedor** en pasos posteriores.
7. El paso 13 asocia los registros **Cuenta**, **Contacto** y **Vendedor** con GUID de parte.
8. Los pasos 14-1 a 14-3 actualizan los registros **Cuenta**, **Contacto** y **Vendedor** en la aplicación de interacción con el cliente con GUID de parte.
9. Los pasos 15-1 a 15-3 preparan registros **Contacto de parte** para registros **Cuenta**, **Contacto** y **Vendedor**.
10. Los pasos 16-1 a 16-7 recuperan datos de referencia, como formas de saludo y tipos de caracteres personales, y los asocian con registros **Contacto de parte**.
11. El paso 17 combina los registros **Contacto de parte** para registros **Cuenta**, **Contacto** y **Vendedor**.
12. El paso 18 importa los registros **Contacto de parte** en la aplicación de interacción con el cliente.

### <a name="steps-in-the-party-postal-address-template"></a>Pasos de la plantilla de dirección postal de la Parte

1. Los pasos 1-1 a 1-10 recuperan datos de aplicación de Finanzas y Operaciones y la aplicación de Customer Engagement, y prepara esos datos para actualizarlos.
2. El paso 2 desnormaliza los datos de dirección postal en la aplicación de Finanzas y Operaciones uniendo la dirección postal y la dirección postal de parte.
3. El paso 3 elimina los duplicados y combina los datos de cuenta, contacto y dirección del proveedor desde la aplicación de interacción con el cliente.
4. El paso 4 crea archivos .csv para la aplicación de Finanzas y Operaciones para crear nuevos datos de direcciones basados en cuentas, contactos y direcciones de proveedores.
5. El paso 5-1 crea archivos .csv para que la aplicación de interacción con el cliente cree todos los datos de dirección, basándose en la aplicación de Finanzas y Operaciones y la aplicación de Customer Engagement.
6. El paso 5-2 convierte los archivos .csv al formato de importación de Finanzas y Operaciones para importación manual.

    - ImportFONewPostalAddressLocation.csv
    - ImportFONewPartyPostalAddress.csv
    - ImportFONewPostalAddress.csv

7. El paso 6 importa los datos de recopilación de direcciones postales a la aplicación de interacción con el cliente.
8. El paso 7 recupera los datos de recopilación de direcciones postales de la aplicación de interacción con el cliente.
9. El paso 8 crea datos de dirección del cliente y asocia un ID de recopilación de dirección postal.
10. Los pasos 9-1 a 9-2 asocian Identificaciones de recopilación de direcciones postales y de parte con direcciones postales y direcciones postales de parte.
11. Los pasos del 10-1 al 10-3 importan direcciones de clientes, direcciones postales y direcciones postales de parte en la aplicación de interacción con el cliente.

### <a name="steps-in-the-party-electronic-address-template"></a>Pasos de la plantilla de dirección electrónica de la Parte

1. Los pasos 1-1 a 1-5 recuperan datos de aplicación de Finanzas y Operaciones y la aplicación de Customer Engagement, y prepara esos datos para actualizarlos.
2. El paso 2 consolida las direcciones electrónicas en la aplicación de interacción con el cliente a partir de entidades de cuenta, contacto y proveedor.
3. El paso 3 combina los datos de dirección electrónica principal desde la aplicación de Customer Engagement y la aplicación Finanzas y Operaciones.
4. El paso 4 crea archivos .csv.

    - Cree nuevos datos de direcciones electrónicas para la aplicación Finanzas y Operaciones, basándose en las direcciones de cuenta, contacto y proveedor.
    - Cree nuevos datos de direcciones electrónicas para la aplicación de interacción con el cliente, basados en direcciones electrónicas, cuentas, contactos y proveedores en la aplicación de Finanzas y Operaciones.

5. El paso 5-1 importa direcciones electrónicas a la aplicación de interacción con el cliente.
6. El paso 5-2 crea archivos .csv para actualizar las direcciones principales de cuentas y contactos en la aplicación de interacción con el cliente.
7. Los pasos 6-1 a 6-2 importan cuentas y direcciones principales de contacto en la aplicación de interacción con el cliente.

## <a name="troubleshooting"></a>Solución de problemas

1. Si el proceso falla, vuelva a ejecutar la factoría de datos. Empiece por la actividad fallida.
2. La factoría de datos genera algunos archivos que pueden utilizarse con fines de validación de datos.
3. La factoría de datos se ejecuta en función de archivos .csv. Por tanto, si se incluye una coma en cualquier valor de campo, puede interferir con los resultados. Debe eliminar todas las comas de los valores de campo.
4. La pestaña **Supervisión** proporciona información sobre todos los pasos y datos que se han procesado. Seleccione un paso específico para depurarlo.

    ![Pestaña de seguimiento.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>Más información sobre la plantilla

Para más información sobre la plantilla, vea [Comentarios para el archivo Léame de la plantilla de Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).

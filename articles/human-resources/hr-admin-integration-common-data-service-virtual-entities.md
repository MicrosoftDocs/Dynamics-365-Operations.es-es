---
title: Configurar entidades virtuales de Common Data Service
description: Este tema muestra cómo configurar entidades virtuales para Dynamics 365 Human Resources. Generar y actualizar entidades virtuales existentes y analizar entidades generadas y disponibles.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2b590faeab600d04c9d5303693ec1e9ac682250d
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645610"
---
# <a name="configure-common-data-service-virtual-entities"></a>Configurar entidades virtuales de Common Data Service

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Dynamics 365 Human Resources es una fuente de datos virtual en Common Data Service. Proporciona operaciones completas de creación, lectura, actualización y eliminación (CRUD) de Common Data Service y Microsoft Power Platform. Los datos de las entidades virtuales no se almacenan en Common Data Service, pero en la base de datos de la aplicación. 

Permitir operaciones CRUD en entidades de Human Resources desde Common Data Service, debe hacer que las entidades estén disponibles como entidades virtuales en Common Data Service. Esto le permite realizar operaciones CRUD desde Common Data Service y Microsoft Power Platform en datos que se encuentran en Human Resources. Las operaciones también respaldan las validaciones de la lógica empresarial completa de Human Resources para garantizar la integridad de los datos al escribir datos en las entidades.

## <a name="available-virtual-entities-for-human-resources"></a>Entidades virtuales disponibles para Human Resources

Todas las entidades de Protocolo de datos abiertos (OData) de Human Resources están disponibles como entidades virtuales en Common Data Service. También están disponibles en Power Platform. Ahora puede crear aplicaciones y experiencias con datos directamente de Human Resources con capacidad CRUD completa, sin copiar ni sincronizar datos en Common Data Service. Puede usar los portales de Power Apps para construir sitios web externos que habiliten escenarios de colaboración para procesos comerciales en Human Resources.

Puede ver la lista de entidades virtuales habilitadas en el entorno y comenzar a trabajar con las entidades en [Power Apps](https://make.powerapps.com), en la solución **Entidades virtuales de Dynamics 365 HR**.

![Entidades virtuales de Dynamics 365 HR en Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a>Entidades virtuales versus entidades naturales

Las entidades virtuales de Human Resources no son lo mismo que las entidades naturales de Common Data Service creadas para Human Resources. Las entidades naturales para Human Resources se generan por separado y se mantienen en la solución HCM Common en Common Data Service. Con entidades naturales, los datos se almacenan en Common Data Service y requiere la sincronización con la base de datos de la aplicación de Human Resources.

> [!NOTE]
> Para obtener una lista de las entidades naturales de Common Data Service para Human Resources, vea[Entidades de Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).

## <a name="setup"></a>Configurar

Siga estos pasos de configuración para habilitar entidades virtuales en su entorno.

### <a name="enable-virtual-entities-in-human-resources"></a>Habilitar entidades virtuales en Human Resources

Primero, debe habilitar las entidades virtuales en el espacio de trabajo **Administración de características**.

1. En Human Resources, seleccione **Administración del sistema**.

2. Seleccione la ventana **Gestión de funciones**.

3. Seleccione **Soporte de entidad virtual en HR/CDS** y, a continuación, **Habilitar**.

Para obtener más información sobre cómo habilitar y deshabilitar características, consulte [Administrar características](hr-admin-manage-features.md).

### <a name="register-the-app-in-microsoft-azure"></a>Registrar la aplicación en Microsoft Azure

Debe registrar su instancia de Human Resources en Azure Portal para que la plataforma de identidad de Microsoft pueda proporcionar servicios de autenticación y autorización para la aplicación y los usuarios. Para obtener más información sobre cómo registrar aplicaciones en Azure, consulte [Inicio rápido: registre una aplicación con la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

1. Abra el [portal de Microsoft Azure](https://portal.azure.com).

2. En la lista de servicios de Azure, seleccione **Registros de aplicación**.

3. Seleccione **Nuevo registro**.

4. En el campo **Nombre**, especifique un nombre descriptivo para la aplicación. Por ejemplo, **Entidades virtuales de Dynamics 365 Human Resources**.

5. En el campo **Redirigir URI**, ingrese la URL del espacio de nombres de su instancia de Human Resources.

6. Seleccione **Registrar**.

7. Cuando se completa el registro, Azure Portal muestra el panel **Visión de conjunto** del registro de la aplicación, que incluye su **ID de aplicación (cliente)**. Tome nota del **ID de aplicación (cliente)** en este momento. Ingresará esta información al [Configurar la fuente de datos de la entidad virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

8. En el panel de navegación izquierdo, seleccione **Certificados y secretos**.

9. En la sección **Secretos del cliente** de la página, seleccione **Nuevo secreto de cliente**.

10. Proporcione una descripción, seleccione una duración y seleccione **Añadir**.

11. Registre el valor del secreto. Ingresará esta información al [Configurar la fuente de datos de la entidad virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

    > [!IMPORTANT]
    > Asegúrese de tomar nota del valor del secreto en este momento. El secreto nunca se vuelve a mostrar después de salir de esta página.

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a>Instalar la aplicación Dynamics 365 HR Virtual Entity

Instale la aplicación Dynamics 365 HR Virtual Entity en su entorno de Power Apps para implementar el paquete de solución de entidad virtual para Common Data Service.

1. Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).

2. En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.

3. En la sección **Recursos** de la página, seleccione **Aplicaciones de Dynamics 365**.

4. Seleccione la acción **Instalar aplicación**.

5. Seleccione **Dynamics 365 HR Virtual Entity** y seleccione **Siguiente**.

6. Revise y marque para aceptar los términos de servicio.

7. Seleccione **Instalar**.

La instalación tarda unos minutos. Cuando se complete, continúe con los siguientes pasos.

![Instalar la aplicación Dynamics 365 HR Virtual Entity desde el centro de administración de Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a>Configurar la fuente de datos de la entidad virtual 

El siguiente paso es configurar la fuente de datos de la entidad virtual en el entorno de Power Apps. 

1. Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).

2. En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.

3. Seleccione la **URL del entorno** la sección **Detalles** de la página.

4. En el **Centro de estado de la solución**, selecciona el icono **Búsqueda avanzada** en la parte superior derecha de la página de la aplicación.

5. En la página **Búsqueda avanzada**, en la lista desplegable **Buscar**, seleccione **Configuraciones de fuentes de datos virtuales de Finance and Operations**.

6. Seleccione **Resultados**.

7. Seleccione el registro **Fuente de datos de recursos humanos de Microsoft**.

8. Introduzca la información requerida para la configuración del origen de datos:

   - **URL de destino**: la URL del espacio de nombres de Human Resources. El formato de la URL de destino es:
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     Por ejemplo:
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >Asegúrese de incluir el carácter "**/**" al final de la URL para evitar recibir un error.

   - **ID de inquilino**: el ID de inquilino de Azure Active Directory (Azure AD).

   - **ID de la aplicación de AAD**: id. de aplicación (cliente) creado para la aplicación registrada en el portal de Microsoft Azure. Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   - **Secreto de aplicación de AAD**: secreto de aplicación creado para la aplicación registrada en el portal de Microsoft Azure. Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   ![Fuente de datos de HR de Microsoft](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. Seleccione **Guardar y cerrar**.

### <a name="grant-app-permissions-in-human-resources"></a>Conceder permisos de aplicación en Human Resources

Otorgar permisos para los las dos aplicaciones de Azure AD en Human Resources:

- La aplicación creada para su inquilino en el portal de Microsoft Azure
- La aplicación Dynamics 365 HR Virtual Entity instalada en el entorno de Power Apps 

1. En Human Resources, abra la página **Aplicaciones de Azure Active Directory**.

2. Seleccione **Nuevo** para crear un nuevo registro de aplicación.

    - En el campo **Id. de cliente**, ingrese el ID de cliente de la aplicación que registró en el portal de Microsoft Azure.
    - En el campo **Nombre**, ingrese el nombre de la aplicación que registró en el portal de Microsoft Azure.
    - En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.

3. Seleccione **Nuevo** para crear un segundo registro de aplicación:

    - **Id. de cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Nombre**: Dynamics 365 HR Virtual Entity
    - En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.

## <a name="generate-virtual-entities"></a>Generar entidades virtuales

Cuando se completa la configuración, puede seleccionar las entidades virtuales que desea generar y habilitar en su instancia de Common Data Service.

1. En Human Resources, abra la página **Integración de Common Data Service (CDS)**.

2. Seleccione la pestaña **Entidades virtuales**.

> [!NOTE]
> El botón de alternancia **Habilitar la entidad virtual** se establecerá en **Sí** automáticamente cuando se haya completado toda la configuración necesaria. Si el botón de alternancia está configurado en **No**, revise los pasos de las secciones anteriores de este documento para asegurarse de completar toda la configuración los requisitos previos.

3. Seleccione la entidad (o entidades) que desea generar en Common Data Service.

4. Seleccione **Generar/actualizar**.

![Integración de Common Data Service](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a>Comprobar el estado de generación de la entidad

Las entidades virtuales se generan en Common Data Service mediante un proceso asincrónico en segundo plano. Actualizaciones de la visualización del proceso en el centro de actividades. Los detalles del proceso, incluidos los registros de errores, aparecen en la página **Automatizaciones de procesos**.

1. En Recursos humanos, abra la página **Automatizaciones de procesos**.

2. Seleccione la pestaña **Procesos en segundo plano**.

3. Seleccione **Proceso en segundo plano de operación asincrónica de sondeo de entidad virtual**.

4. Seleccione **Ver los resultados más recientes**.

El panel deslizante muestra los resultados de ejecución más recientes del proceso. Puede ver el registro del proceso, que incluye los errores devueltos por Common Data Service.

## <a name="see-also"></a>Consulte también

[¿Qué es Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[Información general sobre las entidades](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[Descripción general de las relaciones entre entidades](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[Crear y editar entidades virtuales que contienen datos de una fuente de datos externa](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[¿Que son los portales de Power Apps?](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[Descripción general de la creación de aplicaciones en Power Apps](https://docs.microsoft.com/powerapps/maker/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
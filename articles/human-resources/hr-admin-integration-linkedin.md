---
title: Integrar con LinkedIn Talent Hub
description: Este tema explica cómo configurar la integración entre Microsoft Dynamics 365 Human Resources y LinkedIn Talent Hub.
author: jaredha
manager: tfehr
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6f70e3a6ccf9770c75334d355db5e9df9ee912dd
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527894"
---
# <a name="integrate-with-linkedin-talent-hub"></a>Integrar con LinkedIn Talent Hub

[!include [banner](includes/preview-feature.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) es una plataforma de sistema de seguimiento de candidatos (ATS). Permite buscar, administrar y contratar empleados, todo en un solo lugar. Mediante la integración de Microsoft Dynamics 365 Human Resources con LinkedIn Talent Hub, puede crear fácilmente registros de empleados en Human Resources para los solicitantes contratados para un puesto.

## <a name="setup"></a>Configurar

Un administrador del sistema debe completar las tareas de configuración para permitir la integración con LinkedIn Talent Hub. Primero, en el entorno de Power Apps, debe configurar un usuario y un rol de seguridad para otorgar a LinkedIn Talent Hub los permisos necesarios para escribir datos en Human Resources.

### <a name="link-your-environment-to-linkedin-talent-hub"></a>Vincular su entorno a LinkedIn Talent Hub

1. Abra [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).

2. En el menú desplegable de usuarios, seleccione **Configuración del producto**.

3. En el panel de navegación izquierdo, en la sección **Avanzado**, seleccione **Integraciones**.

4. Seleccione **Autorizar** para la integración de Microsoft Dynamics 365 Human Resources.

5. En la página **Dynamics 365 Human Resources**, seleccione el entorno al que vincular LinkedIn Talent Hub y, a continuación, seleccione **Vincular**.

    ![Incorporación a LinkedIn Talent Hub.](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > Puede vincular solo a entornos para los que su cuenta de usuario tenga acceso de administrador tanto al entorno de Human Resources como al entorno de Power Apps asociado. Si no se muestra ningún entorno en la página de vínculo de Human Resources, asegúrese de que tiene entornos de Human Resources con licencia en el inquilino y que el usuario que inició sesión en la página de vínculo tiene permisos de administrador tanto para el entorno de Human Resources como para el entorno de Power Apps.

### <a name="create-a-power-apps-security-role"></a>Crear un rol de seguridad de Power Apps

1. Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).

2. En la lista **Entornos**, seleccione el entorno que está asociado al entorno de Human Resources al que desea vincular su instancia de LinkedIn Talent Hub.

3. Seleccione **Configuración**.

4. Expanda el nodo **Usuarios + Permisos** y seleccione **Roles de seguridad**.

5. En la página **Roles de seguridad**, en la barra de herramientas, seleccione **Nuevo rol**.

6. En la pestaña **Detalles**, escriba un nombre para el rol, como **Integración HRIS de LinkedIn Talent Hub**.

7. En la pestaña **Personalización**, seleccione el permiso **Leer** de nivel de organización para las siguientes entidades:

    - Entidad
    - Campo
    - Relación

8. Guarde y cierre el rol de seguridad.

### <a name="create-a-power-apps-application-user"></a>Crear un usuario de aplicación de Power Apps

Hay que crear un usuario de aplicación para que el adaptador de LinkedIn Talent Hub otorgue permisos al adaptador para escribir registros de candidatos en el entorno de Power Apps.

1. Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).

2. En la lista **Entornos**, seleccione el entorno que está asociado al entorno de Human Resources al que desea vincular su instancia de LinkedIn Talent Hub.

3. Seleccione **Configuración**.

4. Expanda el nodo **Usuarios + Permisos** y seleccione **Usuarios**.

5. Seleccione **Administrar usuarios en Dynamics 365**.

6. Utilice el menú desplegable situado encima de la lista para pasar de la vista predeterminada **Usuarios habilitados** a **Usuarios de la aplicación**.

    ![Vista Usuarios de la aplicación](./media/hr-admin-integration-power-apps-application-users.jpg)

7. En la barra de herramientas, seleccione **Nuevo**.

8. En la página **Nuevo usuario**, siga estos pasos:

    1. Cambie el valor del campo **Tipo de usuario** a **Usuario de la aplicación**.
    2. Establezca el campo **Nombre de usuario** en **Integración HRIS de LinkedIn y Dynamics365 HR**.
    3. Establezca el campo **Id. de aplicación** en **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    4. Escriba los valores que desee en los campos **Nombre**, **Apellidos** y **Correo electrónico principal**.
    5. En la barra de herramientas, seleccione **Guardar \& Cerrar**

### <a name="assign-a-security-role-to-the-new-user"></a>Asignar un rol de seguridad al nuevo usuario

Después de guardar y cerrar el nuevo usuario de la aplicación en la sección anterior, volverá a la página **Lista de usuarios**.

1. En la página **Lista de usuarios**, cambie la vista a **Usuarios de la aplicación**.

2. Seleccione el usuario de la aplicación que ha creado en la sección anterior.

3. En la barra de herramientas, seleccione **Administrar roles**.

4. Seleccione el rol de seguridad que creó anteriormente para la integración.

5. Seleccione **Aceptar**.

### <a name="add-an-azure-active-directory-app-in-human-resources"></a>Agregar una aplicación de Azure Active Directory a Human Resources

1. En Dynamics 365 Human Resources, abra la página **Aplicaciones de Azure Active Directory**.
2. Agregue un registro nuevo a la lista y establezca los campos siguientes:

    - **Id. de cliente**: especifique **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    - **Nombre**: escriba el nombre del rol de seguridad de Power Apps que creó anteriormente, como **Integración HRIS de LinkedIn Talent Hub**.
    - **Id. de usuario**: seleccione un usuario que tenga permisos para escribir datos en Dirección de personal.

### <a name="create-the-entity-in-common-data-service"></a>Crear la entidad en Common Data Service

> [!IMPORTANT]
> La integración con LinkedIn Talent Hub depende de entidades virtuales de Common Data Service para Human Resources. Como requisito previo para este paso de la configuración, debe configurar las entidades virtuales. Para obtener más información sobre cómo configurar entidades virtuales, consulte [Configurar entidades virtuales de Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

1. En Human Resources, abra la página **Integración de Common Data Service (CDS)**.

2. Seleccione la pestaña **Entidades virtuales**.

3. Filtre la lista de entidades por etiqueta de entidad para encontrar **Candidato exportado de LinkedIn**.

4. Seleccione la entidad jurídica y, a continuación, seleccione **Generar/actualizar**.

## <a name="exporting-candidate-records"></a>Exportar registros de candidatos

Una vez completada la configuración, los reclutadores y los profesionales de recursos humanos (RR. HH.) podrán utilizar la función **Exportar a HRIS** en LinkedIn Talent Hub para exportar registros de candidatos contratados desde LinkedIn Talent Hub a Human Resources.

### <a name="export-records-from-linkedin-talent-hub"></a>Exportar registros desde LinkedIn Talent Hub

Una vez que un candidato ha pasado por el proceso de contratación y ha sido contratado, puede exportar el registro de candidato desde LinkedIn Talent Hub a Human Resources.

1. En LinkedIn Talent Hub, abra el proyecto para el que se contrató al nuevo empleado.

2. Seleccione un registro de candidato.

3. Seleccione **Cambiar etapa** y, a continuación, seleccione **Contratado**.

4. En el menú de puntos suspensivos (**...**) para el candidato, seleccione **Exportar a HRIS**.

5. En el panel **Exportar a HRIS**, especifique la información que se debe exportar:

    - En el campo **Proveedor de HRIS**, seleccione **Microsoft Dynamics 365 Human Resources**.
    - En el campo **Fecha de inicio** seleccione un valor para el nuevo empleado.
    - En el campo **Cargo**, especifique un cargo para el trabajo del nuevo empleado.
    - En el campo **Ubicación**, especifique la ubicación en la que estará basado el empleado.
    - Escriba o compruebe la dirección de correo electrónico del empleado.

![Exportar al panel HRIS en LinkedIn Talent Hub](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a>Completar la incorporación en Human Resources

Los registros de candidatos que se exportan desde LinkedIn Talent Hub a Human Resources aparecen en la sección **Candidatos a contratar** de la página **Administración de personal**.

1. En Human Resources, abra la página **Administración de personal**.

2. En la sección **Candidatos a contratar**, seleccione **Contratar** para el candidato seleccionado.

3. En el cuadro de diálogo **Contratar trabajador nuevo**, revise el registro y agregue la información necesaria. También puede seleccionar el número de cargo para el que se ha contratado al candidato.

Después de especificar la información necesaria, puede continuar con los procesos estándar para crear registros de empleados e incorporar empleados.

Se importan los siguientes detalles y se incluyen en el nuevo registro de empleado:

- Nombre
- Apellidos
- Fecha inicial del empleo
- Dirección de correo electrónico
- Número de teléfono

## <a name="see-also"></a>Consulte también

[Configurar entidades virtuales de Common Data Service](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[¿Qué es Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
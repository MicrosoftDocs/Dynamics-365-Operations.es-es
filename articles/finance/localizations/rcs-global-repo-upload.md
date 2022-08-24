---
title: Crear configuraciones de ER en RCS y cargarlas en el repositorio global
description: Este artículo explica cómo crear una configuración de informes electrónicos (ER) en Regulatory Configuration Services (RCS) de Microsoft y cargarla al repositorio global.
author: kfend
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
ms.openlocfilehash: 21e6ab3a7066fda23f1f5672f6f74bc6bd1ff1f6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283005"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Crear configuraciones en Regulatory Configuration Services (RCS) y cargarlas en el repositorio global

[!include [banner](../includes/banner.md)]

Puede usar Regulatory Configuration Services (RCS) de Microsoft para diseñar configuraciones de informes electrónicos (ER) y luego publicarlas, de forma que se puedan usar en su organización.

Los siguientes procedimientos explican cómo un usuario en el rol de Administrador del sistema o Desarrollador de informes electrónicos puede crear una versión derivada de una configuración de ER que se haya configurado en una instancia de RCS y luego cargar la configuración derivada al repositorio global. 

Para poder completar estos procedimientos, primero debe completar los siguientes requisitos previos:

- Tener acceso a un entorno RCS para su organización.
- Crear un proveedor de configuraciones activo y activarlo. Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Debe asegurarse de que se aprovisione un entorno RCS para su organización. Si no tiene una instancia de RCS aprovisionada para su organización, puede hacerlo siguiendo los siguientes pasos:

1. En una aplicación de finanzas y operaciones, vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En **Vínculos relacionados/Vínculos externos**, seleccione **Regulatory services: configuración** y luego siga las instrucciones para **Registrarse** y aprovisionar una.

Si ya se ha aprovisionado un entorno RCS para su organización, use la URL de la página para acceder a él y seleccione la opción **iniciar sesión**.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Crear una versión derivada de una configuración en RCS

> [!NOTE]
> Si es la primera vez que utiliza RCS, no tendrá ninguna configuración disponible para derivar. Deberá importar una configuración del repositorio global. Para obtener más información, consulte [Descargue las configuraciones de ER del repositorio global del servicio de configuración](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

1. **Inicie sesión** en RCS y seleccione el icono del espacio de trabajo **Informes electrónicos**.
2. Verifique que tiene un proveedor de configuración activo para su organización que esté activo (ver requisitos previos). 
3. Seleccione **Configuraciones de informes**.
4. Seleccione la configuración de la que desea derivar una nueva versión. Puede utilizar el campo de filtro que hay sobre el árbol para precisar la búsqueda.
5. Seleccione **Crear configuración** \> **Derivar del nombre**.
6. Introduzca un nombre y una descripción, y luego seleccione **Crear configuración** para crear una nueva versión derivada con estado "Borrador".
7. Seleccione la configuración recién derivada y realice cambios adicionales en el formato de configuración si es necesario. 
8. Después de completar los cambios, debe establecer **Cambiar estado** en la configuración a **Completado** para poder registrarla en el repositorio. Seleccione **Aceptar**.

![Nueva versión de configuración en RCS.](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Cuando se cambia el estado de la configuración, es posible que reciba un mensaje de error de validación relacionado con las aplicaciones conectadas. Para desactivar la validación, en el Panel de acciones de la pestaña **Configuraciones**, seleccione **Parámetros de usuario** y luego establezca la opción **Omitir validación en el cambio de estado y reorganización de la configuración** en **Sí** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Cargar una configuración al repositorio global

Para compartir una configuración nueva o derivada con su organización, puede subirla al repositorio global si sigue los siguientes pasos:

1. Seleccione la versión completa de la configuración y luego seleccione **Cargar al repositorio**.
2. Seleccione la opción **Global (Microsoft)** y luego seleccione **Cargar**.

    ![Cargar en opciones de repositorio.](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. En el cuadro de mensaje de confirmación, haga clic en **Sí**. 
4. Actualice la descripción de la versión según sea necesario y luego seleccione **Aceptar**. También puede cargar opcionalmente la versión en una aplicación conectada o en un repositorio GIT.  

El estado de la configuración se actualiza a **Compartido**, y la configuración se carga en el repositorio global. También se crea una versión preliminar de la configuración que cargó y se puede usar si se requieren cambios posteriores.

Después de cargar la configuración en el repositorio global, puede trabajar con ella allí de las siguientes maneras:

- Impórtela a su instancia de Dynamics 365. Para obtener más información, consulte [Importar configuraciones (ER) desde RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Compártalo con un tercero o una organización externa, consulte [Configuraciones de informes electrónicos (ER) de uso compartido de RCS con organizaciones externas](rcs-global-repo-share-configuration.md)

    ![Versión de configuración de Intrastat Contoso derivada en el repositorio global.](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Eliminar una configuración del repositorio global
Complete los siguientes pasos para eliminar una configuración creada por su organización.

1. En el espacio de trabajo **Informes electrónicos**, compruebe que su proveedor de configuración esté **Activo**. Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. En el proveedor de configuración activo, seleccione **repositorio**.
3. Seleccione el tipo de repositorio **Global** y después seleccione **Abrir**.
4. En la ficha desplegable **Filtrar**, busque la configuración que desea eliminar mediante la funcionalidad de **Filtro**.
5. En la ficha desplegable **Versión**, seleccione la versión de la configuración que desea eliminar y, a continuación, seleccione **Eliminar**:

    ![Eliminar una configuración del repositorio global.](media/RCS_Delete_from_GlobalRepo.JPG)

6. En el cuadro de mensaje de confirmación, haga clic en **Sí**.

    ![Eliminar el mensaje de confirmación de una versión de configuración.](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
Se elimina la versión de configuración y se muestra un mensaje de confirmación. 

> [!NOTE]
> Las configuraciones solo las puede eliminar el proveedor de configuración que las creó. Si la configuración se ha compartido con otra organización, será necesario dejar de compartir la configuración antes de eliminarla.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]


---
title: Crear configuraciones de ER en RCS y cargarlas en el repositorio global
description: Este tema explica cómo crear una configuración de informes electrónicos (ER) en Regulatory Configuration Service (RCS) de Microsoft y cargarla al repositorio global.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 5b2b8f35b9931f8fd1824c20e9045da68af33ad5
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834242"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Crear configuraciones en Regulatory Configuration Services (RCS) y cargarlas en el repositorio global

[!include [banner](../includes/banner.md)]

Puede usar Regulatory Configuration Services (RCS) de Microsoft para diseñar configuraciones de informes electrónicos (ER) y luego publicarlas, de forma que se puedan usar en su organización.

Los siguientes procedimientos explican cómo un usuario en el rol de Administrador del sistema o Desarrollador de informes electrónicos puede crear una versión derivada de una configuración de ER que se haya configurado en una instancia de RCS y luego cargar la configuración derivada al repositorio global. 

Para poder completar estos procedimientos, primero debe completar los siguientes requisitos previos:

- Acceda a una instancia RCS.
- Cree un proveedor de configuración activo. Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

También debe asegurarse de que se aprovisione un entorno RCS para su empresa.

1. En una aplicación de Finance and Operations, vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. Si no está aprovisionado ningún entorno RCS en la empresa, seleccione **Regulatory services: configuración externa** y luego siga las instrucciones para aprovisionar uno.

Si ya se ha aprovisionado un entorno RCS para su empresa, use la URL de la página para acceder a él seleccionando la opción de inicio de sesión.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Crear una versión derivada de una configuración en RCS

1. En el espacio de trabajo **Informes electrónicos**, verifique tener un proveedor de configuración activo para su organización. 
2. Seleccione **Configuraciones de informes**.
3. Seleccione la configuración de la que desea derivar una nueva versión. Puede utilizar el campo de filtro que hay sobre el árbol para precisar la búsqueda.
4. Seleccione **Crear configuración** \> **Derivar del nombre**.
5. Introduzca un nombre y una descripción, y luego seleccione **Crear configuración** para crear una nueva versión derivada.
6. Seleccione la configuración recién derivada, agregue una descripción de la versión y luego seleccione **Aceptar**. El estado de la configuración se cambia a **Completado**.

![Nueva versión de configuración en RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Cuando se cambia el estado de la configuración, es posible que reciba un mensaje de error de validación relacionado con las aplicaciones conectadas. Para desactivar la validación, en el Panel de acciones de la pestaña **Configuraciones**, seleccione **Parámetros de usuario** y luego establezca la opción **Omitir validación en el cambio de estado y reorganización de la configuración** en **Sí** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Cargar una configuración al repositorio global

Para compartir una configuración nueva o derivada con su organización, puede subirla al repositorio global.

1. Seleccione la versión completa de la configuración y luego seleccione **Cargar al repositorio**.
2. Seleccione la opción **Global (Microsoft)** y luego seleccione **Cargar**.

    ![Cargar en opciones de repositorio](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. En el cuadro de mensaje de confirmación, haga clic en **Sí**. 
4. Actualice la descripción de la versión según sea necesario y luego seleccione **Aceptar**. 

El estado de la configuración se actualiza a **Compartir**, y la configuración se carga en el repositorio global. A partir de ahí, puede trabajar con ella de las siguientes formas:

- Impórtela a su instancia de Dynamics 365. Para obtener más información, consulte [Importar configuraciones (ER) desde RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Compártalo con un tercero o una organización externa, consulte [Configuraciones de informes electrónicos (ER) de uso compartido de RCS con organizaciones externas](rcs-global-repo-share-configuration.md)

    ![Versión de configuración de Intrastat Contoso derivada en el repositorio global](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Eliminar una configuración del repositorio global
Complete los siguientes pasos para eliminar una configuración creada por su organización.

1. En el espacio de trabajo **Informes electrónicos**, compruebe que su proveedor de configuración esté **Activo**. Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. En el proveedor de configuración activo, seleccione **repositorio**.
3. Seleccione el tipo de repositorio **Global** y después seleccione **Abrir**.
4. En la ficha desplegable **Filtrar**, busque la configuración que desea eliminar mediante la funcionalidad de **Filtro**.
5. En la ficha desplegable **Versión**, seleccione la versión de la configuración que desea eliminar y, a continuación, seleccione **Eliminar**:

    ![Eliminar una configuración del repositorio global](media/RCS_Delete_from_GlobalRepo.JPG)

6. En el cuadro de mensaje de confirmación, haga clic en **Sí**.

    ![Eliminar el mensaje de confirmación de una versión de configuración](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
Se elimina la versión de configuración y se muestra un mensaje de confirmación. 

> [!NOTE]
> Las configuraciones solo las puede eliminar el proveedor de configuración que las creó. Si la configuración se ha compartido con otra organización, será necesario dejar de compartir la configuración antes de eliminarla.
 

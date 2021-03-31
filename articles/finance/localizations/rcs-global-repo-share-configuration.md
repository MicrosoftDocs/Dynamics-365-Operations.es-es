---
title: Compartir configuraciones de ER en RCS/repositorio global con organizaciones externas
description: Este tema explica cómo compartir configuraciones de informes electrónicos (ER) en los Regulatory Configuration Service (RCS) de Microsoft/repositorio global directamente con organizaciones externas.
author: JaneA07
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: e7ec24ddc532ee3b87108d076d5103538be903be
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218839"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a>Compartir configuraciones de informes electrónicos (ER) en el repositorio global de Regulatory Configuration Service (RCS) con organizaciones externas.

[!include [banner](../includes/banner.md)]

Puede usar los Regulatory Configuration Services (RCS) de Microsoft para compartir configuraciones de informes electrónicos (ER) y luego publicarlas en organizaciones externas.

Los siguientes procedimientos explican cómo un usuario de RCS puede compartir una versión de una configuración de ER que se ha configurado en una instancia de RCS con una organización externa. Para poder completar estos procedimientos, primero debe completar los siguientes requisitos previos:

- Acceda a una instancia RCS.
- Cree un proveedor de configuración activo. Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
- Cree y cargue una nueva versión de una configuración de ER. Para obtener más información, consulte [Crear y cargar una nueva versión de una configuración de informes electrónicos (ER)](rcs-global-repo-upload.md).

También debe asegurarse de que se aprovisione un entorno RCS para su empresa.

1. En una aplicación de Finance and Operations, vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. Si no está aprovisionado ningún entorno RCS en la empresa, seleccione **Regulatory services: configuración externa** y luego siga las instrucciones para aprovisionar uno.

Si ya se ha aprovisionado un entorno RCS para su empresa, use la URL de la página para acceder a él seleccionando la opción de inicio de sesión.

## <a name="verify-the-configuration-that-you-want-to-share"></a>Verificar la configuración que se desea compartir

Siga estos pasos para verificar que la configuración que desea compartir ya se haya cargado en el repositorio global.

1. En el espacio de trabajo **Informes electrónicos**, seleccione **Repositorios** para su proveedor de configuración.

    ![Proveedores de configuración](media/1_RCS_Repo_for_config_provider.JPG)

2. Seleccione **Repositorio global** \> **Abierto**.
3. Busque la configuración que desea compartir. Puede utilizar el campo de filtro para precisar los resultados de la búsqueda. Si no puede encontrar la configuración en el repositorio global, siga los pasos de [Crear y cargar una nueva versión de una configuración de informes electrónicos (ER)](rcs-global-repo-upload.md).

## <a name="share-er-configurations-with-external-organizations"></a>Compartir configuraciones de ER con organizaciones externas

Después de crear una configuración con su proveedor de configuración, puede compartirla directamente con organizaciones externas utilizando la ficha desplegable **Compartido con** en la página **Repositorio de configuración global**.

1. En el espacio de trabajo **Informes electrónicos**, seleccione **Repositorios** para su proveedor de configuración.
2. Seleccione **Repositorio global** \> **Abierto**. 
3. Seleccione la configuración que desea compartir.
4. En la ficha desplegable , **Compartido con**, seleccione **Organización**.

    ![Ficha desplegable Compartido con](media/1_RCS_Repo_for_Share_with_org.JPG)

5. En el cuadro de diálogo, introduzca el nombre de dominio para la organización externa y luego seleccione **Aceptar**.

    ![Cuadro de diálogo Compartir versión de configuración con organización externa](media/1_RCS_Repo_for_Share_with_form.JPG)

La configuración se comparte con la organización externa y está disponible para esa organización en el repositorio global. A partir de ahí, se puede importar a la instancia de RCS de la organización o a sus instancias de las aplicaciones de Finance and Operations.

6. Para dejar de compartir una configuración que se ha compartido previamente con una organización externa, seleccione la configuración y haga clic en **Dejar de compartir** y luego seleccione **Aceptar**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
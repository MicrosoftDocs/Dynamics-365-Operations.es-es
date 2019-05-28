---
title: Espacio de trabajo móvil de entrada de tiempo de proyecto
description: Este tema proporciona información acerca del espacio de trabajo móvil de entrada de horas del proyecto. Este espacio de trabajo permite a los usuarios especificar y guardar la hora en un proyecto mediante el dispositivo móvil.
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: e671fe6e7c99bfb6d66f3b00560c3b0c404d2343
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545133"
---
# <a name="project-time-entry-mobile-workspace"></a>Espacio de trabajo móvil de entrada de tiempo de proyecto

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca del espacio de trabajo móvil **Entrada de tiempo del proyecto**. Este espacio de trabajo permite a los usuarios especificar y guardar la hora en un proyecto mediante el dispositivo móvil.

Este espacio de trabajo móvil se debe usar con la aplicación Microsoft Dynamics 365 for Unified Operations mobile. 

## <a name="overview"></a>Información general
Como parte de su trabajo diario, los recursos de proyecto están a menudo in situ o de viaje. El espacio de trabajo móvil **Entrada de horas del proyecto** permite a los usuarios especificar su tiempo facturable o no facturable relativo a un proyecto, en el dispositivo móvil de su elección. Por lo tanto, los recursos de proyecto pueden registrar las entradas de horas en cualquier momento y cualquier lugar. También se pueden ver las entradas de horas que ya se han registrado. 

Específicamente, en el espacio de trabajo móvil **Entrada de tiempo del proyecto**, los usuarios pueden realizar las tareas siguientes:

-   Para cualquier fecha seleccionada, especifique el número de horas empleadas en una tarea específica.
-   Busque por nombre del proyecto o el cliente para encontrar el proyecto para el que debe especificar las horas.
-   Especifique la categoría y la actividad de las horas empleadas.
-   Registre la hora como facturable o no facturable para el proyecto.
-   También puede especificar cualquier comentario externo o interno.

## <a name="prerequisites"></a>Requisitos previos
Los requisitos previos varían, en función de la versión de Microsoft Dynamics 365 que se ha implementado para su organización.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Requisitos previos si usa Microsoft Dynamics 365 for Finance and Operations
Si Microsoft Dynamics 365 for Finance and Operations se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Entrada de tiempo del proyecto**. Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Los requisitos previos si usa Microsoft Dynamics 365 for Operations versión 1611 con la actualización de plataforma 3 o posterior
Si se ha implementado Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior en su organización, el administrador del sistema debe cumplir los requisitos siguientes. 

<table>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Función</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td>Implementar 4018050 KB.</td>
<td>Administrador del sistema</td>
<td>KB 4018050 es una sustitución de actualización o de metadatos X++ que contiene el espacio de trabajo móvil <strong>Entrada de horas del proyecto</strong>. Para implementar KB 4018050, el administrador del sistema debe seguir estos pasos.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Descargar la revisión de metadatos de Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar la revisión de metadatos</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crear un paquete desplegable</a> que contenga los modelos <strong>ApplicationSuite</strong> y <strong>ProjectMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar el paquete implementable</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publique el espacio de trabajo móvil <strong>Entrada de tiempo del proyecto</strong>.</td>
<td>Administrador del sistema</td>
<td>Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Descargar e instalar la aplicación móvil

Descargue e instale la aplicación móvil Dynamics 365 for Unified Operations:

-   [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Iniciar sesión en la aplicación móvil
1.  Inicie la aplicación en su dispositivo móvil.
2.  Escriba la URL de Dynamics 365.
3.  La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.
4.  Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.

[![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Especifique las horas mediante el espacio de trabajo móvil de entrada de horas del proyecto
1.  En el dispositivo móvil, seleccione el espacio de trabajo **Entrada de horas del proyecto**.
2.  Seleccione **Entrada de horas** Se muestran las fechas de calendario de la semana actual.
3.  Para una fecha seleccionada, seleccione **Acciones** &gt; **Nueva entrada**.
4.  Escriba la cantidad de horas que deben registrarse.
5.  Seleccione el proyecto de la entrada de horas. Una lista muestra los proyectos que están cargados en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, consulte [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
6.  Si el proyecto no está en la lista, seleccione **Buscar**. Busque por su nombre, o cambie a la búsqueda al nombre del proyecto o el cliente.
7.  Permite seleccionar una categoría. Una lista muestra las categorías que están cargadas en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, consulte [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
8.  Si la categoría no está en la lista, seleccione **Buscar**. Busque por categoría o cambie a buscar por nombre de categoría.
9.  Seleccione una actividad. Una lista muestra las actividades que están cargadas en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, consulte [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
10. Si la actividad no está en la lista, seleccione **Buscar**. Busque por número de actividad o cambie a buscar por propósito.

11. Seleccione la propiedad del línea.
12. Opcional: puede especificar cualquier comentario externo o interno.
13. Seleccione **Listo**.

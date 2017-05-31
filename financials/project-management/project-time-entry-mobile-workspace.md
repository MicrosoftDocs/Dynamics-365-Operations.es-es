---
title: "Espacio de trabajo móvil de entrada de horas de proyecto para la aplicación Microsoft Dynamics 365 for Operations"
description: "Este tema proporciona información acerca del espacio de trabajo móvil de entrada de horas del proyecto. Este espacio de trabajo permite a los usuarios especificar y guardar la hora en un proyecto mediante el dispositivo móvil."
author: annbe
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9c592c301908898915164e9236850759b73543fe
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="project-time-entry-mobile-workspace"></a>Espacio de trabajo móvil de entrada de tiempo de proyecto

[!include[banner](../includes/banner.md)]



Este tema proporciona información acerca del espacio de trabajo móvil de entrada de horas del proyecto para la aplicación móvil Microsoft Dynamics 365 for Operations. Este espacio de trabajo permite a los usuarios especificar y guardar la hora en un proyecto mediante el dispositivo móvil.

<a name="overview-of-the-project-time-entry-mobile-workspace"></a>Visión general del espacio de trabajo móvil de entrada de horas del proyecto
---------------------------------------------------

Como parte de su trabajo diario, los recursos de proyecto están a menudo in situ o de viaje. El espacio de trabajo móvil **Entrada de horas del proyecto** permite a los usuarios especificar su tiempo facturable o no facturable relativo a un proyecto, en el dispositivo móvil de su elección. Por lo tanto, los recursos de proyecto pueden registrar las entradas de horas en cualquier momento y cualquier lugar. También se pueden ver las entradas de horas que ya se han registrado. 

En concreto, el espacio de trabajo móvil **Entrada de horas del proyecto** proporciona estas características:

-   Para cualquier fecha seleccionada, especifique el número de horas empleadas en una tarea específica.
-   Busque por nombre del proyecto o el cliente para encontrar el proyecto para el que debe especificar las horas.
-   Especifique la categoría y la actividad de las horas empleadas.
-   Registre la hora como facturable o no facturable para el proyecto.
-   También puede especificar cualquier comentario externo o interno.

Para implementar el espacio de trabajo móvil **Entrada de horas del proyecto** , vea las siguientes secciones de este tema.

## <a name="prerequisites"></a>Requisitos previos
Para poder implementar el espacio de trabajo móvil **Entrada de horas del proyecto**, asegúrese de que el administrador del sistema haya completado los requisitos previos siguientes.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Función</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior debe estar implementado.</td>
<td>Administrador del sistema</td>
<td>Si todavía no tiene Dynamics 365 for Operations implementado en su organización, el administrador del sistema debería ver <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Implementar un entorno de demostración de Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>KB 4018050 debe implementarse.</td>
<td>Administrador del sistema</td>
<td>KB 4018050 es una sustitución de actualización o de metadatos X++ que contiene el espacio de trabajo móvil <strong>Entrada de horas del proyecto</strong>. Para implementar KB 4018050, el administrador del sistema debe seguir estos pasos.
<ol>
<li>Descargar KB 4018050 de Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar la revisión de metadatos</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Crear un paquete desplegable</a> que contenga los modelos <strong>ApplicationSuite</strong> y <strong>ProjectMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Aplicar el paquete desplegable</a> a su sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>El espacio de trabajo móvil <strong>Entrada de horas del proyecto</strong> debe estar publicado en la aplicación móvil Dynamics 365 for Operations.</td>
<td>Administrador del sistema</td>
<td><ol>
<li>Inicie Dynamics 365 for Operations en su explorador.</li>
<li>En la página <strong>Parámetros del sistema</strong>, en la ficha <strong>Gestionar los espacios de trabajo móviles</strong>, seleccione el espacio de trabajo <strong>Entrada de horas del proyecto</strong>.</li>
<li>Haga clic en <strong>Publicar espacio de trabajo móvil</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Descargue e instale la aplicación móvil Dynamics 365 for Operations
Descargue e instale la aplicación móvil Microsoft Dynamics 365 for Operations desde la tienda de aplicaciones móviles.

-   Para Android: [Dynamics 365 for Operations en Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Para iPhone: [Dynamics 365 for Operations en la tienda de aplicaciones de iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Inicie sesión en la aplicación móvil Dynamics 365 for Operations
1.  Inicie la aplicación en su dispositivo móvil.
2.  Entre en la URL de Dynamics 365 for Operations.
3.  Escriba la empresa en la que va a iniciar sesión. Por ejemplo, escriba **USMF**.
4.  La primera vez que inicia sesión, se le pedirá el nombre de usuario y la contraseña de su cuenta Dynamics 365 for Operations. Escriba sus credenciales.
5.  Tras iniciar sesión, verá los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, puede tocar la pantalla para actualizar la lista de espacios de trabajo móviles.

[![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Especifique las horas mediante el espacio de trabajo móvil de entrada de horas del proyecto
1.  En el dispositivo móvil, seleccione el espacio de trabajo **Entrada de horas del proyecto**.
2.  Seleccione **Entrada de horas** Verá las fechas de calendario de la semana actual.
3.  Para una fecha seleccionada, seleccione **Acciones** &gt; **Nueva entrada**.
4.  Escriba la cantidad de horas que deben registrarse.
5.  Seleccione el proyecto de la entrada de horas. Verá una lista de los proyectos que están cargados en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
6.  Si su proyecto no está en la lista, seleccione **Buscar** para realizar una búsqueda en línea en Dynamics 365 for Operations. Busque por su nombre, o cambie a la búsqueda al nombre del proyecto o el cliente.
7.  Permite seleccionar una categoría. Verá una lista de las categorías que están cargadas en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
8.  Si su categoría no está en la lista, seleccione **Buscar** para realizar una búsqueda en línea en Dynamics 365 for Operations. Busque por categoría o cambie a buscar por nombre de categoría.
9.  Seleccione una actividad. Verá una lista de las actividades que están cargadas en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
10. Si su actividad no está en la lista, seleccione **Buscar** para realizar una búsqueda en línea en Dynamics 365 for Operations. Busque por número de actividad o cambie a buscar por propósito.
11. Seleccione la propiedad del línea.
12. Opcional: puede especificar cualquier comentario externo o interno.
13. Seleccione **Listo**.







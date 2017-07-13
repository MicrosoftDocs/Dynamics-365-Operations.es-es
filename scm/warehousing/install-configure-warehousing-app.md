---
title: "Instalación y configuración de Microsoft Dynamics 365 for Finance and Operations #8211; Warehousing"
description: "Este tema describe cómo instalar y configurar Microsoft Dynamics 365 for Finance and Operations - Warehousing."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: 2e6b0fb81396eef945dbce3be8aee17c9fd455bc
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Instalación y configuración de Microsoft Dynamics 365 for Finance and Operations #8211; Warehousing
<a id="install-and-configure-microsoft-dynamics-365-for-finance-and-operations-8211-warehousing" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este tema describe cómo instalar y configurar Microsoft Dynamics 365 for Finance and Operations - Warehousing.

Finance and Operations - Warehousing es una aplicación disponible en Google Play Store y Windows Store. En la versión actual de Finance and Operations, esta aplicación se proporciona como componente independiente, con implementación propia en los dispositivos utilizados para las tareas de almacén. Para usar la aplicación en su entorno de Finance and Operations, deberá descargar la aplicación en cada dispositivo y configurarla para conectarse al entorno de Finance and Operations. Este tema describe cómo instalar la aplicación en los dispositivos. También se explica cómo configurar la aplicación para conectarla al entorno de Finance and Operations.

## Requisitos previos
<a id="prerequisites" class="xliff"></a>
La aplicación está disponible para los sistemas operativos Android y Windows. Para utilizar esta aplicación, debe tener uno de los sistemas operativos admitidos siguientes instalado en los dispositivos. También debe tener una de las siguientes versiones admitidas de Finance and Operations. Use la información de la siguiente tabla para evaluar si su entorno de hardware y software está listo para admitir la instalación.

| Plataforma                    | Versión                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (todas las versiones)                                                                                                                                                   |
| Finance and Operations | Versión 1611 de Microsoft Finance and Operations <br>– O bien – <br>La versión 7.0/7.0.1 de Microsoft Dynamics Dynamics AX y la plataforma de Microsoft Dynamics AX actualización 2 con la revisión KB 3210014 |

## Obtenga la aplicación
<a id="get-the-app" class="xliff"></a>
-   Windows (UWP): [Finance and Operations - Warehousing en Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android:
    - [Finance and Operations - Warehousing en Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)
    - [Finance and Operations - Warehousing en Zebra App Gallery](https://appgallery.zebra.com/showcase/apps/146?type=showcase)

## Crear una aplicación de servicio Web en Active Directory
<a id="create-a-web-service-application-in-active-directory" class="xliff"></a>
Para habilitar la aplicación para que interactúe con un servidor específico de Finance and Operations, debe registrar una aplicación de servicio Web en un Azure Active Directory para el inquilino de Finance and Operations. Por razones de seguridad, se recomienda que cree una aplicación de servicio Web para cada dispositivo que utilice. Para crear una solicitud de servicio Web en Azure Active Directory (Azure AD), realice los pasos siguientes:

1.  En un explorador web, vaya a <https://manage.windowsazure.com>.
2.  Especifique el nombre y la contraseña del usuario que tiene acceso a la suscripción de Azure.
3.  En Azure Portal, en el panel de navegación izquierdo, haga clic en **Active Directory**.[](./media/wh-01-active-directory-example.png)[![wh-01-active-directory-example](./media/wh-01-active-directory-example.png)](./media/wh-01-active-directory-example.png)
4.  En la cuadrícula, seleccione la instancia de Active Directory que usa Finance and Operations.
5.  En la barra de herramientas superior, haga clic en **Solicitudes**. [![wh-02-active-directory-applications](./media/wh-02-active-directory-applications-1024x197.png)](./media/wh-02-active-directory-applications.png)
6.  En el panel inferior, haga clic en **Agregar**. Se inicia el asistente de **Agregar aplicación**.
7.  Escriba un nombre para la aplicación y seleccione **Aplicación web y/o API web**. [![wh-03-active-directory-add-application](./media/wh-03-active-directory-add-application.png)](./media/wh-03-active-directory-add-application.png)
8.  Indique la dirección URL de inicio de sesión, que es la dirección URL de la aplicación web. Esta dirección URL es la misma que la dirección URL de la implementación, pero se añade oauth al final. Indique el URI del identificador de la aplicación, este valor es obligatorio, pero no se requiere para la autenticación. Asegúrese de que el URI de este identificador de la aplicación sea un URI simulado https://contosooperations/wmapp, ya que el uso de la dirección URL de la implementación puede provocar problemas de inicio de sesión en otras aplicaciones AAD como el complemento de Excel. [![WH-04-AD-add-properties3](./media/WH-04-AD-add-properties3.png)](./media/WH-04-AD-add-properties3.png)
9.  Vaya a la ficha **Configurar**. [![wh-05-ad-configure-app](./media/wh-05-ad-configure-app.png)](./media/wh-05-ad-configure-app.png)
10. Desplácese hasta que vea la sección **Permisos para otras aplicaciones**. Haga clic en **Agregar aplicación**. [![wh-06-ad-app-add-permissions](./media/wh-06-ad-app-add-permissions.png)](./media/wh-06-ad-app-add-permissions.png)
11. Seleccione **Microsoft Dynamics ERP** en la lista. Haga clic en el botón **Comprobación completa** en la esquina derecha de la página. [![wh-07-ad-select-permissions](./media/wh-07-ad-select-permissions.png)](./media/wh-07-ad-select-permissions.png)
12. En la lista **Delegar permisos**, seleccione todas las casillas. Haga clic en **Guardar**. [![wh-08-ad-delegate-permissions](./media/wh-08-ad-delegate-permissions.png)](./media/wh-08-ad-delegate-permissions.png)
13. Tenga en cuenta la siguiente información:
    -   **Id. de cliente** - A medida que se desplaza hacia arriba en la página, verá **Id. de cliente**.
    -   **Clave** - En la sección **Claves** cree una clave seleccionando la duración y copie la clave. Posteriormente se hará referencia a esta clave como **Secreto de cliente**.

## Crear y configurar una cuenta de usuario en Finance and Operations
<a id="create-and-configure-a-user-account-in-finance-and-operations" class="xliff"></a>
Para que Finance and Operations pueda utilizar su aplicación Azure AD, debe completar los siguientes pasos de configuración:

1.  Cree una nueva cuenta de usuario en Azure Active Directory para el inquilino de Finance and Operations. El propósito de esta cuenta de usuario es tener acceso al servicio personalizado específico de la aplicación Warehousing a la que se expone el servidor de Finance and Operations. Tras completar este paso, tendrá credenciales del usuario de WMDP, compuestas por una dirección de correo electrónico de WMDP y una contraseña de WMDP. Para obtener información acerca de los pasos básicos para agregar usuarios a Azure AD y Finance and Operations, consulte a este tutorial: [Inscríbase para suscribirse a Finance and Operations](/dynamics365/unified-operations/dev-itpro/dev-tools/sign-up-preview-subscription).
2.  Crear un usuario de Finance and Operations correspondiente a las credenciales de usuario de la aplicación Warehousing.
    1.  En Finance and Operations, vaya a **Administración del sistema** &gt; **Común** &gt; **Usuarios**.
    2.  Cree un nuevo usuario.
    3.  Asigne el usuario del dispositivo móvil de almacén como se muestra en el captura de pantalla siguiente. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  Asocie su aplicación Azure Active Directory con el usuario de la aplicación Warehousing.
    1.  En Finance and Operations, vaya a **Administración del sistema** &gt; **Configuración** &gt; **Aplicaciones de Azure Active Directory**.
    2.  Cree una línea nueva.
    3.  Introduzca el **Id. de cliente** (obtenido en la última sección), asígnele un nombre y seleccione el usuario creado previamente. Recomendamos que etiquete todos los dispositivos de modo que pueda quitar fácilmente su acceso a Finance and Operations de esta página en caso de que se pierdan. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## Configurar la aplicación
<a id="configure-the-application" class="xliff"></a>
Debe configurar la aplicación en el dispositivo para conectarse al servidor Finance and Operations a través de la aplicación Azure AD. Para ello, realice los pasos siguientes:

1.  En la aplicación, vaya a **Configuración de la conexión**.
2.  Borre el campo **Modo de demostración**. <br>[![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Especifique la siguiente información: 
    + **Id. de cliente de Azure Active Directory** - El identificador secreto de cliente se obtiene en el paso 13 en "Crear una aplicación de servicio Web en Active Directory". 
    + **Secreto de cliente de Azure Active Directory** - El secreto de cliente se obtiene en el paso 13 en "Crear una aplicación de servicio Web en Active Directory". 
    + **Recurso de Azure Active Directory** - El recurso del directorio Azure AD representa la URL raíz de Finance and Operations. **Nota**: No termine este campo con un carácter de barra diagonal (/). 
    + **Inquilino de Azure Active Directory**- El inquilino del directorio Azure AD empleado con el servidor de Finance and Operations: https://login.windows.net/your-AD-tenant-ID. Por ejemplo: https://login.windows.net/contosooperations.onmicrosoft.com. 
    <br>**Nota**: No termine este campo con un carácter de barra diagonal (/). 
    + **Empresa** - Especifique la entidad jurídica en Finance and Operations a la que desea que se conecte la aplicación. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Seleccione el botón **Atrás** en la esquina superior izquierda de la aplicación. La aplicación se conectará ahora a su servidor Finance and Operations y aparecerá la pantalla de inicio de sesión del trabajador de almacén. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

## Quitar el acceso de un dispositivo
<a id="remove-access-for-a-device" class="xliff"></a>
En caso de un dispositivo perdido o defectuoso, debe quitar el acceso a Finance and Operations del dispositivo. Los siguientes pasos describen el proceso recomendado para quitar acceso.

1.  En Finance and Operations, vaya a **Administración del sistema** &gt; **Configuración** &gt; **Aplicaciones de Azure Active Directory**.
2.  Elimine la línea correspondiente al dispositivo del que desea eliminar el acceso. Anote el **Id. de cliente** utilizado para el dispositivo quitado.
3.  Inicie sesión en el portal clásico de Azure en <https://manage.windowsazure.com>.
4.  Haga clic en el icono de **Active Directory** en el menú izquierdo y haga clic en el directorio deseado.
5.  En el menú superior, haga clic en **Aplicaciones** y, a continuación, haga clic en la aplicación que desea configurar. Aparecerá la página de **Inicio rápido** con el inicio de sesión único y otra información de configuración.
6.  Haga clic en la pestaña **Configurar**, desplácese hacia abajo y asegúrese de que el **Id. de cliente** de la aplicación sea el mismo que en el paso 2 de esta sección.
7.  Haga clic en el botón **Eliminar** de la barra de comandos.
8.  Haga clic en **Sí** en el mensaje de confirmación.






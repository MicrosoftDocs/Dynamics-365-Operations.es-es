---
title: Instalar y configurar Microsoft Dynamics 365 for Finance and Operations &#8211; Warehousing
description: Este tema describe cómo instalar y configurar Microsoft Dynamics 365 for Finance and Operations - Warehousing.
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f5e99351d79cb5898c6d5565d3d3197a8fe860df
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "316128"
---
# <a name="install-and-configure-microsoft-dynamics-365-for-finance-and-operations-8211-warehousing"></a>Instalar y configurar Microsoft Dynamics 365 for Finance and Operations &#8211; Warehousing

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 
> Este tema describe cómo configurar el almacenamiento para implementaciones en la nube. Si busca cómo configurar el almacenamiento para implementaciones locales, consulte [Almacenamiento para implementaciones locales](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).


Este tema describe cómo instalar y configurar Microsoft Dynamics 365 for Finance and Operations - Warehousing.

Finance and Operations - Warehousing es una aplicación disponible en Google Play Store y Windows Store. En la versión actual de Finance and Operations, esta aplicación se proporciona como componente independiente, con implementación propia en los dispositivos utilizados para las tareas de almacén. Para usar la aplicación en su entorno de Finance and Operations, deberá descargar la aplicación en cada dispositivo y configurarla para conectarse al entorno de Finance and Operations. Este tema describe cómo instalar la aplicación en los dispositivos. También se explica cómo configurar la aplicación para conectarla al entorno de Finance and Operations.

## <a name="prerequisites"></a>Requisitos previos
La aplicación está disponible en Android para los sistemas operativos Android y Windows. Para utilizar esta aplicación, debe tener uno de los sistemas operativos admitidos siguientes instalado en los dispositivos. También debe tener una de las siguientes versiones admitidas de Finance and Operations. Use la información de la siguiente tabla para evaluar si su entorno de hardware y software está listo para admitir la instalación.

| Plataforma                    | Versión                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0, 7.0, 8.0                                                                                                                                                     |
| Windows (UWP)               | Windows 10 (todas las versiones)                                                                                                                                                   |
| Finance and Operations | Microsoft Dynamics 365 for Operations, versión 1611 <br>– O bien – <br>Microsoft Dynamics AX versión 7.0/7.0.1 y actualización de plataforma Microsoft Dynamics AX 2 con revisión KB 3210014 |

## <a name="get-the-app"></a>Obtenga la aplicación
-   Windows (UWP)
     - [Finance and Operations - Warehousing en Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android
    - [Finance and Operations - Warehousing en Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

> [!NOTE]
> Se ha retirado la galería de la aplicación de Zebra, lo que significa que la aplicación Finance and Operations - Warehousing ya no estará disponible para descarga en dicha ubicación.

## <a name="create-a-web-service-application-in-azure-active-directory"></a>Creación de una web de aplicación de servicio en Azure Active Directory
Para habilitar la aplicación para que interactúe con un servidor específico de Finance and Operations, debe registrar una aplicación de servicio Web en un Azure Active Directory para el inquilino de Finance and Operations. Por razones de seguridad, se recomienda que cree una aplicación de servicio Web para cada dispositivo que utilice. Para crear una solicitud de servicio web en Azure Active Directory (Azure AD), realice los pasos siguientes:

1.  En un explorador web, vaya a <https://portal.azure.com>.
2.  Especifique el nombre y la contraseña del usuario que tiene acceso a la suscripción de Azure.
3.  En Azure Portal, en el panel de navegación izquierdo, haga clic en **Azure Active Directory**.[](./media/WMA-01-active-directory-example.png)[![WMA-01-active-directory-example](./media/WMA-01-active-directory-example.png )](./media/WMA-01-active-directory-example.png)
4.  Asegúrese de que la instancia de Active Directory es una que usa Finance and Operations.
5.  En la lista, haga clic en **Registros de aplicación**. [![WMA-02-active-directory-app-registrations](./media/WMA-02-active-directory-app-registrations.png)](./media/WMA-02-active-directory-app-registrations.png)
6.  En el panel superior, haga clic en **Nuevo registro de aplicación**. Se inicia el asistente de **Agregar aplicación**.
7.  Escriba un nombre para la aplicación y seleccione **Aplicación web/API web**. Indique la dirección URL de inicio de sesión, que es la dirección URL de la aplicación web. Esta dirección URL es la misma que la dirección URL de la implementación, pero se añade oauth al final. Haga clic en **Crear**. [![WMA-03-active-directory-add-application](./media/WMA-03-active-directory-add-application.png)](./media/WMA-03-active-directory-add-application.png)
8.  Seleccione la nueva aplicación en la lista. [![WMA-04-active-directory-configure-app](./media/WMA-04-active-directory-configure-app.png)](./media/WMA-04-active-directory-configure-app.png)
9.  Recuerde el **Id. de aplicación**, lo necesitará más adelante. El **Id. de aplicación** hará referencia más adelante al **Id. del cliente**.
10. Haga clic en **Claves** en el **panel Configuración**. Cree una clave introduciendo una descripción clave y una duración en la sección **Contraseñas** . 
11. Haga clic en **Guardar** y copie la clave. Posteriormente se hará referencia a esta clave como **Secreto de cliente**. [![WMA-05-active-directory-create-key](./media/WMA-05-active-directory-create-key.png)](./media/WMA-05-active-directory-create-key.png)

## <a name="create-and-configure-a-user-account-in-finance-and-operations"></a>Crear y configurar una cuenta de usuario en Finance and Operations
Para que Finance and Operations pueda utilizar su aplicación Azure AD, debe completar los siguientes pasos de configuración:

1.  Crear un usuario de Finance and Operations correspondiente a las credenciales de usuario de la aplicación Warehousing.
    1.  En Finance and Operations, vaya a **Administración del sistema** &gt; **Común** &gt; **Usuarios**.
    2.  Cree un nuevo usuario.
    3.  Asigne el usuario del dispositivo móvil de almacén como se muestra en el captura de pantalla siguiente. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

2.  Asocie su aplicación Azure Active Directory con el usuario de la aplicación Warehousing.
    1.  En Finance and Operations, vaya a **Administración del sistema** &gt; **Configuración** &gt; **Aplicaciones Azure Active Directory**.
    2.  Cree una línea nueva.
    3.  Introduzca el **Id. de cliente** (obtenido en la última sección), asígnele un nombre y seleccione el usuario creado previamente. Recomendamos que etiquete todos los dispositivos de modo que pueda quitar fácilmente su acceso a Finance and Operations de esta página en caso de que se pierdan. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Configurar la aplicación
Debe configurar la aplicación en el dispositivo para conectarse al servidor Finance and Operations a través de la aplicación Azure AD. Para ello, realice los pasos siguientes:

1.  En la aplicación, vaya a **Configuración de la conexión**.
2.  Borre el campo **Modo de demostración**. <br>[![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Especifique la siguiente información: 
    + **Id. de cliente de Azure Active Directory** - El identificador secreto de cliente se obtiene en el paso 9 en "Crear una aplicación de servicio Web en Active Directory". 
    + **Secreto de cliente de Azure Active Directory** - El secreto de cliente se obtiene en el paso 11 en "Crear una aplicación de servicio Web en Active Directory". 
    + **Recurso de Azure Active Directory** - El recurso del directorio Azure AD representa la URL raíz de Finance and Operations. **Nota**: No termine este campo con un carácter de barra diagonal (/). 
    + **Inquilino de Azure Active Directory**: el inquilino del directorio Azure AD empleado con el servidor de Finance and Operations: `https://login.windows.net/your-AD-tenant-ID`. Por ejemplo: `https://login.windows.net/contosooperations.onmicrosoft.com.` 
    <br>**Nota**: No termine este campo con un carácter de barra diagonal (/). 
    + **Empresa** - Especifique la entidad jurídica en Finance and Operations a la que desea que se conecte la aplicación. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Seleccione el botón **Atrás** en la esquina superior izquierda de la aplicación. La aplicación se conectará ahora a su servidor Finance and Operations y aparecerá la pantalla de inicio de sesión del trabajador de almacén. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

Para obtener información acerca de cómo configurar Dynamics 365 for Finance and Operations – Warehousing para digitalizar códigos de barras mediante una cámara en un dispositivo móvil, consulte [Escanear códigos de barras utilizando una cámara en Dynamics 365 for Finance and Operations – Warehousing](scan-bar-codes-using-a-camera.md)

## <a name="remove-access-for-a-device"></a>Quitar el acceso de un dispositivo
En caso de un dispositivo perdido o defectuoso, debe quitar el acceso a Finance and Operations del dispositivo. Los siguientes pasos describen el proceso recomendado para quitar acceso.

1.  En Finance and Operations, vaya a **Administración del sistema** &gt; **Configuración** &gt; **Aplicaciones Azure Active Directory**.
2.  Elimine la línea correspondiente al dispositivo del que desea eliminar el acceso. Recuerde el **Id. del cliente** empleado para el dispositivo eliminado, lo necesitará más adelante.
3.  Inicie sesión en el portal Azure en <https://portal.azure.com>.
4.  Haga clic en el icono de **Active Directory** en el menú izquierdo y asegúrese de que se encuentra en el directorio correcto.
5.  En la lista, haga clic en **Registros de aplicación** y, a continuación, haga clic en la aplicación que desea configurar. La página **Valores** aparecerá con la información de configuración.
6.  Asegúrese de que el **Id. del cliente** de la aplicación es el mismo que en el paso 2 de esta sección.
7.  Haga clic en el botón **Eliminar** del panel superior.
8.  Haga clic en **Sí** en el mensaje de confirmación.

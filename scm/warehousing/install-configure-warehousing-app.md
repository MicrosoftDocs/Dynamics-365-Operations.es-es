---
title: "Instalación y configuración de Microsoft Dynamics 365 para las operaciones &#8211; Almacenamiento"
description: "Este tema describe cómo instalar y configurar Microsoft Dynamics 365 para las operaciones (almacenamiento de datos."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 231c087ddc976aa552fc9cd6c89188f82a0247d1
ms.lasthandoff: 03/31/2017


---

# <a name="install-and-configure-microsoft-dynamics-365-for-operations-8211-warehousing"></a>Instalación y configuración de Microsoft Dynamics 365 para las operaciones &#8211; Almacenamiento

Este tema describe cómo instalar y configurar Microsoft Dynamics 365 para las operaciones (almacenamiento de datos.

Dinámica 365 para las operaciones (el almacenamiento de datos es una aplicación disponibles en Google Play Store y Windows Store. Para la versión actual de Microsoft Dynamics 365 para las operaciones, esta aplicación se proporciona como componente independiente, que significa propio implementación de los dispositivos utilizados para las tareas de almacén. Para usar la aplicación del 365 dinámica para el entorno de las operaciones, deberá descargar la aplicación en cada dispositivo y configurarla para conectar el Dynamics 365 del entorno de las operaciones. Este tema describe cómo instalar la aplicación en los dispositivos. También se explica cómo configurar la aplicación para conectar el Dynamics 365 del entorno de las operaciones.

## <a name="prerequisites"></a>Requisitos previos
La aplicación está disponible en Android y los sistemas operativos Windows. Para utilizar esta solicitud, debe tener uno de los sistemas operativos admitidos siguientes instalados en los dispositivos. También debe tener una de las siguientes versiones admitidas de las Dynamics 365 para las operaciones. Use la información de la siguiente tabla para evaluar si el hardware y entorno de software se listos para admitir la instalación.

| Plataforma                    | Versión                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (todas las versiones)                                                                                                                                                   |
| Dinámica 365 para las operaciones | Microsoft Dynamics 365 para la versión 1611 de las operaciones) o bien la versión 7.0/7.0.1 de Dynamics AX de Microsoft Dynamics y la plataforma de Microsoft Dynamics AX 2 actualizan con el reemplazo 3210014 KB |

## <a name="get-the-app"></a>Obtenga la aplicación
-   UWP Windows (-) [Dynamics 365 para las operaciones (almacenamiento de datos en Windows Store (https://www.microsoft.com/store/apps/9p1bffd5tstm)]
-   Android - dinámica [365 para las operaciones (almacenamiento de datos en el Google Store Play (https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)]

## <a name="create-a-web-service-application-in-active-directory"></a>Crear una aplicación de servicio Web en Active Directory
Para habilitar la aplicación interactuar con una específica Dynamics 365 para las operaciones servidor, debe registrar una aplicación de servicio Web en Azure Active Directory para Dynamics 365 para el arrendatario de las operaciones. Por razones de seguridad, se recomienda que cree una aplicación de servicio Web para cada dispositivo que utilice. Para crear una solicitud de servicio Web en Azure Active Directory (ANUNCIO blanco cielo), realice los pasos siguientes:

1.  En un explorador web, vaya< a https://manage.windowsazure.com>.
2.  Especifique el nombre y contraseña del usuario que tiene acceso a la suscripción blanco ciela.
3.  Azure Portal En, en el panel de navegación izquierdo, haga clic en Active Directory ** **. [] (. /media/wh-01-active-directory-example.png![) [] (wh-01-active-directory-example. /media/wh-01-active-directory-example.png])(. /media/wh-01-active-directory-example.png)
4.  En la cuadrícula, seleccione la instancia de Active Directory que usa Dynamics 365 para las operaciones.
5.  En la barra de herramientas superior, haga clic ** ** aplicaciones. ![wh-02-active-directory-applications [] (. /media/wh-02-active-directory-applications-1024x197.png])(. /media/wh-02-active-directory-applications.png)
6.  En la sección inferior, haga clic ** agregue **. ** Agregue la aplicación ** el inicio del asistente.
7.  Escriba un nombre para la aplicación y seleccione ** aplicación web y/o Web API **. ![wh-03-active-directory-add-application [] (. /media/wh-03-active-directory-add-application.png])(. /media/wh-03-active-directory-add-application.png)
8.  Permite especificar la dirección de inicio URL, que es la dirección URL de la aplicación del arrendatario, la dirección URL de las operaciones de la raíz. Signo- en dirección URL no se está utilizando actualmente en activamente autenticar la aplicación, pero es un campo obligatorio. Especifique la misma dirección URL en el campo URI de la identificación de la aplicación. ![wh-04-ad-add-properties [] (. /media/wh-04-ad-add-properties.png])(. /media/wh-04-ad-add-properties.png)
9.  Ir ** configurar ** a la ficha. ![wh-05-ad-configure-app [] (. /media/wh-05-ad-configure-app.png])(. /media/wh-05-ad-configure-app.png)
10. Desplace siguiente hasta que se visualizan ** los permisos a otras aplicaciones ** la sección. Haga clic en ** agregue la aplicación **. ![wh-06-ad-app-add-permissions [] (. /media/wh-06-ad-app-add-permissions.png])(. /media/wh-06-ad-app-add-permissions.png)
11. Seleccione ** ERP de Microsoft Dynamics ** en la lista. Haga clic en ** comprobación completa ** botón en la esquina derecha de la página. ![wh-07-ad-select-permissions [] (. /media/wh-07-ad-select-permissions.png])(. /media/wh-07-ad-select-permissions.png)
12. En ** los permisos de delegado ** la lista, seleccione todas las casillas. Click **Save**. ![wh-08-ad-delegate-permissions [] (. /media/wh-08-ad-delegate-permissions.png])(. /media/wh-08-ad-delegate-permissions.png)
13. Tenga en cuenta la siguiente información:
    -   ** Identificador de cliente - ** manera que desplaza por arriba de la página, verá ** identificador del cliente ** indicado.
    -   ** La clave ** - ** en las teclas ** la sección, crea una clave seleccionando la duración, y copia la clave. Esta clave se hace referencia posteriormente como ** secreto ** del cliente.

## <a name="create-and-configure-a-user-account-in-dynamics-365-for-operations"></a>Crear y configurar una cuenta de usuario en Dynamics 365 para las operaciones
Para permitir a Dynamics 365 para las operaciones para utilizar la aplicación blanco ciela del ANUNCIO, debe completar los siguientes pasos de configuración:

1.  Cree una nueva cuenta de usuario en Azure Active Directory para Dynamics 365 para el arrendatario de las operaciones. El propósito de esta cuenta de usuario es tener acceso al servicio personalizado específico de la solicitud de almacenamiento de datos, que Dynamics 365 para el servidor de las operaciones expone. Tras completar este paso, tendrá credenciales del usuario de WMDP, que constan en una dirección de correo electrónico de WMDP y una contraseña de WMDP. Para obtener información acerca de los pasos básicos para agregar usuarios al ANUNCIO blanco cielo y Dynamics 365 para las operaciones, consulte a este tutorial: [Inscribirse en un Microsoft Dynamics 365 para la suscripción] de las operaciones (/dynamics365/operations/dev-itpro/sign-up-preview-subscription).
2.  Crear una Dynamics 365 para el usuario de las operaciones que corresponde a las credenciales del usuario de una aplicación de almacenamiento de datos.
    1.  En Dynamics 365 para las operaciones, vaya ** Administración del sistema ** &gt; ** el común ** &gt; ** los usuarios **.
    2.  Cree un nuevo usuario.
    3.  Asigne el usuario del dispositivo móvil del almacén, como se muestra en el captura de pantalla siguiente. ![wh-09-add-user-security-role [] (. /media/wh-09-add-user-security-role.png])(. /media/wh-09-add-user-security-role.png)

3.  Asociar la aplicación Azure Active Directory con el usuario de la aplicación de almacenamiento de datos.
    1.  En Dynamics 365 para las operaciones, vaya ** Administración del sistema ** &gt; ** la configuración ** &gt; ** las aplicaciones Azure Active Directory Azure Active Directory **.
    2.  Cree una línea nueva.
    3.  Permite especificar ** identificador del cliente (obtenido ** en la última sección), asígneles un nombre y, seleccione el usuario creado previamente. Es recomendable etiqueta todos los dispositivos de modo que pueda fácilmente quitar su acceso a Dynamics 365 para las operaciones de esta página en caso de que se pierdan. ![wh-10-ad-applications-form [] (. /media/wh-10-ad-applications-form.png])(. /media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Los la aplicación
Debe configurar la aplicación en el dispositivo para conectarse a Dynamics 365 para el servidor de las operaciones con la aplicación blanco ciela del ANUNCIO. Para ello, realice los pasos siguientes.

1.  En la aplicación, vaya ** los parámetros de conexión **.
2.  Borre ** modo de demostración ** el campo. ![wh-11-app-connection-settings-demo-mode [] (. /media/wh-11-app-connection-settings-demo-mode-169x300.png])(. /media/wh-11-app-connection-settings-demo-mode.png)
3.  Especifique la siguiente información: - ** Identificador del cliente del directorio Azure Active Azure Active - ** El identificador del cliente se recogen en el paso 13 “en crea una aplicación de servicio Web en Active Directory”. - ** El secreto del cliente del directorio Azure Active Azure Active ** - secreto del cliente se recogen en el paso 13 “en crea una aplicación de servicio Web en Active Directory”. - ** El recurso del directorio Azure Active Azure Active - ** el recurso blanco cielo de directorio del ANUNCIO describe Dynamics 365 para la URL raíz de las operaciones. ** ** Nota: No termine este campo con un carácter de la barra diagonal (/). - ** Arrendatario del directorio Azure Active Azure Active - ** el arrendatario blanco cielo de directorio del ANUNCIO utilizado con Dynamics 365 para el servidor de las operaciones: https://login.windows.net/your-AD-tenant-ID&lt;&gt;. Por ejemplo: https://login.windows.net/contosooperations.onmicrosoft.com. 
** ** Nota: No termine este campo con un carácter de la barra diagonal (/). - ** Empresa ** - especifique la entidad jurídica en Dynamics 365 para las operaciones a las que desee que la aplicación para conectar. ![wh-12-app-connection-settings [] (. /media/wh-12-app-connection-settings-169x300.png])(. /media/wh-12-app-connection-settings.png)
4.  Seleccione ** a ** botón en la esquina superior izquierda de la aplicación. La aplicación ahora conectar el Dynamics 365 para el servidor de las operaciones y la pantalla de inicio para el trabajador del almacén se mostrará. ![wh-13-log-in-screen [] (. /media/wh-13-log-in-screen-180x300.png])(. /media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Quitar el acceso de un dispositivo
En caso de un dispositivo perdido o comprometido, debe quitar el acceso a Dynamics 365 para las operaciones del dispositivo. Los siguientes pasos describen el proceso recomendado para quitar acceso.

1.  En Dynamics 365 para las operaciones, vaya ** Administración del sistema ** &gt; ** la configuración ** &gt; ** las aplicaciones Azure Active Directory Azure Active Directory **.
2.  Eliminar la línea que corresponde al dispositivo al que desea eliminar el acceso. Nota de abajo ** identificador del cliente ** utilizado para el dispositivo quitado.
3.  Iniciar sesión el portal clásico blanco cielo en< https://manage.windowsazure.com>.
4.  Haga clic en Active Directory ** ** el icono en el menú izquierdo, haga clic en el directorio deseado.
5.  En el menú superior, haga clic ** aplicaciones **, haga clic en la solicitud que desea configurar. ** Tutorial ** la página aparecerá con el inicio de sesión único y otra información de configuración.
6.  Haga clic en ** configurar ** la ficha, desplace en profundidad y asegúrese que ** identificador del cliente ** de la solicitud es el mismo que en el paso 2 en esta sección.
7.  Haga clic en ** Eliminar ** botón en la barra de comandos.
8.  ** Haga clic en Sí ** en el mensaje de confirmación.




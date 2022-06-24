---
title: Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams
description: Este artículo describe cómo habilitar la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.
author: gvrmohanreddy
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 505e3854818e4d5b73fc1a22724be16036300c3b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872837"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams

[!include [banner](includes/banner.md)]

Este artículo describe cómo habilitar la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.

Para proporcionar a Teams con información de Dynamics 365 Commerce y sincronizar las funciones de administración de tareas entre Teams y la aplicación de punto de venta (PDV), debe habilitar las funciones de integración en la sede de Commerce.

> [!NOTE]
> Cuando habilita la integración de Teams, acepta compartir sus datos con Teams. Los datos que se comparten con Teams pueden residir en un país diferente al de sus datos de Commerce y pueden estar sujetos a diferentes estándares de cumplimiento. Para obtener más información, consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center). Para obtener información sobre las políticas de privacidad de Microsoft, consulte la [Declaración de privacidad de Microsoft](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Habilitar la integración Teams

Antes de que pueda habilitar la integración de Microsoft Teams con Commerce, debe registrar la aplicación Teams con su inquilino en Azure Portal.

Para registrar la aplicación Teams con su inquilino en Azure Portal, siga estos pasos.

1. Siga los pasos en [Inicio rápido: registrar una aplicación en la plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app) para registrar la aplicación de Teams con su inquilino en Azure Portal.
1. En la pestaña **Registro de aplicaciones**, seleccione la aplicación que creó en el paso anterior. Después, en la pestaña **Autenticación**, seleccione **Agregar una plataforma**.
1. En el cuadro de diálogo, seleccione **Web**. Después, en el campo **Redirigir URL**, introduzca una URL en el formato **\<HQUrl\>/oauth**. Sustituya **\<HQUrl\>** con la URL de la sede de Commerce (por ejemplo, `https://hxennugbjtweufmdeo385f47fadb6aa9a0aos.cloudax.int.dynamics.com/oauth`).
1. En la página **Información general** de la aplicación registrada, copie el valor **Id. de aplicación (cliente)**. Tendrá que aprovisionar este valor para habilitar la integración de Teams en la sede de Commerce en la siguiente sección.
1. Siga las instrucciones en [Agregar un secreto de cliente](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) para agregar un secreto de cliente. Luego copie el valor **Valor secreto** para el cliente. Tendrá que aprovisionar este valor para habilitar la integración de Teams en la sede de Commerce en la siguiente sección.
1. Seleccione **Permisos de API** y luego **Agregar un permiso**.
1. En el cuadro de diálogo **Solicitar permisos de API**, seleccione **Microsoft Graph**, **Permisos delegados**, amplíe **Grupo**, seleccione **Group.ReadWrite.All** y luego seleccione **Agregar permisos**.
1. En el cuadro de diálogo **Solicitar permisos de API**, seleccione **Agregar un permiso**, **Microsoft Graph**, **Permisos de aplicación**, amplíe **Grupo**, seleccione **Group.ReadWrite.All** y luego seleccione **Agregar permisos**.
1. En el cuadro de diálogo **Solicitar permisos de API**, seleccione **Agregar un permiso**. En la pestaña **API que usa mi organización**, busque **Microsoft Teams Retail Service** y selecciónelo.
1. Seleccione **Permisos delegados**, amplíe **TaskPublishing**, seleccione **TaskPublising.ReadWrite.All** y luego **Agregar permisos**. Para más información, consulte [Configurar una aplicación cliente para acceder a una API web](/azure/active-directory/develop/quickstart-configure-app-access-web-apis).

Para habilitar la integración de Teams en la sede central de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de integración de Microsoft Teams**.
1. En el panel Acciones, seleccione **Editar**.
1. Establezca la opción **Habilitar integración con Microsoft Teams** a **Sí**.
1. En el campo **Identificación de aplicación**, introduzca el valor **Id. de aplicación (cliente)** que obtuvo cuando registró la aplicación Teams en Azure Portal.
1. En el campo **Clave de aplicación**, introduzca el valor **Valor secreto** que obtuvo cuando agregó un secreto de cliente en Azure Portal.
1. En el panel Acciones, seleccione **Guardar**.

La siguiente ilustración muestra un ejemplo de la configuración de la integración de Teams en la sede de Commerce.

![Configuración de integración de Teams en la sede de Commerce.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a>Deshabilitar la integración Teams

Para deshabilitar la integración de Microsoft Teams en la sede central de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de integración de Microsoft Teams**.
1. En el panel Acciones, seleccione **Editar**.
3. Establezca la opción **Habilitar integración con Microsoft Teams** a **No**.
4. Borre los valores de los campos **Identificación de aplicación** y **Clave de aplicación**.
1. En el panel Acciones, seleccione **Guardar**.

> [!NOTE]
> Después de deshabilitar la integración de Teams con Commerce, los terminales PDV ya no mostrarán las tareas publicadas desde la aplicación Teams.

## <a name="additional-resources"></a>Recursos adicionales

[Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams](commerce-teams-integration.md)

[Aprovisionar Microsoft Teams desde Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV](synchronize-tasks-teams-pos.md)

[Administrar roles de usuario en Microsoft Teams](manage-user-roles-teams.md)

[Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams](map-stores-existing-teams.md)

[Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams](teams-integration-faq.md)

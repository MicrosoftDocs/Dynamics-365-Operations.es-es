---
title: Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams
description: Este tema describe cómo habilitar la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c4d596f27ffe15a97dc04e2ce7e85d21f8e7161f
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908404"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams

[!include [banner](includes/banner.md)]

Este tema describe cómo habilitar la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.

Para proporcionar a Teams con información de Dynamics 365 Commerce y sincronizar las funciones de administración de tareas entre Teams y la aplicación de punto de venta (PDV), debe habilitar las funciones de integración en la sede de Commerce.

> [!NOTE]
> Cuando habilita la integración de Teams, acepta compartir sus datos con Teams. Los datos que se comparten con Teams pueden residir en un país diferente al de sus datos de Commerce y pueden estar sujetos a diferentes estándares de cumplimiento. Para obtener más información, consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center). Para obtener información sobre las políticas de privacidad de Microsoft, consulte la [Declaración de privacidad de Microsoft](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Habilitar la integración Teams

Antes de que pueda habilitar la integración de Microsoft Teams con Commerce, debe registrar la aplicación Teams con su inquilino en Azure Portal.

Para registrar la aplicación Teams con su inquilino en Azure Portal, siga estos pasos.

1. Siga los pasos en [Inicio rápido: registrar una aplicación en la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) para registrar la aplicación de Teams con su inquilino en Azure Portal.
1. Copie el valor **Identificador de aplicación (cliente)** de la página **Visión general** de la aplicación registrada. Utilizará este valor para habilitar la integración de Teams en la sede de Commerce.
1. Copie el valor del certificado que introdujo cuando [agregó un certificado](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) en el paso 1. El certificado también se conoce como clave pública o clave de aplicación. Utilizará este valor para habilitar la integración de Teams en la sede de Commerce.

Para habilitar la integración de Teams en la sede central de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de integración de Microsoft Teams**.
1. En el panel Acciones, seleccione **Editar**.
1. Establezca la opción **Habilitar integración con Microsoft Teams** a **Sí**.
1. En los campos **Identificación de aplicación** y **Clave de aplicación**, introduzca los valores que obtuvo cuando registró la aplicación Teams en Azure Portal.
1. En el panel Acciones, seleccione **Guardar**.

La siguiente ilustración muestra un ejemplo de la configuración de la integración de Teams en la sede de Commerce.

![Configuración de integración de Teams en la sede de Commerce](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

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

---
title: Implementar un inquilino nuevo de comercio electrónico
description: Este tema describe cómo implementar un inquilino nuevo de comercio electrónico mediante Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 00f35b516dbf6ab4d4d9171c84a16b89f6afe832
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533284"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Implementar un inquilino nuevo de comercio electrónico


[!include [banner](includes/banner.md)]

Este tema describe cómo implementar un sitio nuevo de comercio electrónico mediante Microsoft Dynamics Lifecycle Services (LCS).

## <a name="overview"></a>Visión general

Microsoft Dynamics Lifecycle Services (LCS) es un espacio de colaboración basado en la nube que los socios y clientes pueden utilizar para administrar sus proyectos y entornos, ver la información más reciente de los productos y características de Microsoft Dynamics, y crear, realizar un seguimiento y examinar incidentes de soporte. Las características de administración de comercio electrónico están integradas en LCS.

Para obtener más información acerca de LCS, consulte el [Manual del usuario de Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).
    
## <a name="get-started"></a>Introducción

Para poder inicializar el comercio electrónico, debe inicializar un proyecto, un entorno y Retail Cloud Scale Unit (RCSU). Para hacer la inicialización en LCS, debe tener permisos para rol Propietario de proyecto o Administrador de entornos. Se admiten las topologías de entorno de espacio aislado y producción.

Para obtener más información sobre los entornos, consulte [Planificación de entorno](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning). Para obtener más información acerca de RCSU, consulte [Inicializar Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).

## <a name="initialize-e-commerce"></a>Inicializar comercio electrónico

Use este procedimiento para inicializar la característica de comercio electrónico en un entorno existente.

Antes de comenzar, asegúrese de tener la siguiente información necesaria:

- Se usará la RCSU.
- El grupo de seguridad de Microsoft Azure Active Directory que se usará para los administradores del sistema de comercio electrónico.
- El grupo de seguridad de Microsoft Azure Active Directory que se usará para los moderadores de clasificaciones y revisiones.
- Los dominios que se asociarán al entorno.

Además, puede recopilar la siguiente información opcional:

- información de empresa-consumidor (B2C) de Azure AD:

    - Nombre del inquilino.
    - Id. de cliente.
    - Dominio personalizado de inicio de sesión.
    - Dirección URL de respuesta.
    - Id. de directiva de registro e inicio de sesión.
    - Id. de directiva de contraseña de restablecimiento.
    - Id. de directiva de edición de perfil.

> [!NOTE]
> Esta información se puede agregar más adelante, con una solicitud de servicio.

Una vez que haya recopilado la información necesaria, siga estos pasos para inicializar el comercio electrónico.

1. Inicie sesión en [LCS](https://lcs.dynamics.com).
1. Abre el proyecto que contiene el entorno donde desea inicializar el comercio electrónico.
1. En la sección **Entornos**, seleccione el entorno.
1. En **Características del entorno**, seleccione el vínculo **Administración de venta minorista**.
1. En la pestaña **Comercio electrónico**, seleccione **Configuración**. Aparece un cuadro de diálogo, donde debe especificar la información necesaria para el aprovisionamiento.
1. Rellene la información necesaria y, a continuación, vaya a la página siguiente.
1. En la página siguiente, rellene la información necesaria y, a continuación, envíe el formulario. Se le devolverá a la pestaña **Comercio electrónico**, donde debería ver que se ha iniciado la inicialización.
1. Para ver el estado de la inicialización, elija **Actualizar** o vuelva a la pestaña **Comercio electrónico** más adelante.
    
Cuando el comercio electrónico se inicializa desde LCS, el sistema aprovisiona varios componentes necesarios para el comercio electrónico y los asocia al entorno. Una vez que se completa el aprovisionamiento, se actualizará la pestaña **Comercio electrónico** de la página **Administración de Retail** para reflejar el aprovisionamiento. La página muestra las últimas implementaciones de personalización y el estado de cualquier otra implementación en curso. También incluye vínculos al sitio de comercio electrónico y al generador de sitios de comercio electrónico donde se crean los sitios.

## <a name="access-site-builder"></a>Acceder al generador de sitios

Para acceder al generador de sitios, vaya a la pestaña **Comercio electrónico** en la página **Gestión de ventas** en LCS y seleccione el vínculo **herramienta de gestión de sitios de comercio electrónico**. La página de aterrizaje del generador de sitios muestra una vista de nivel de suscriptor. En esta página puede:

- Modificar la configuración de nivel de suscriptor.
- Navegar a cualquier sitio que haya creado y tenga permiso para ver. 
- Acceder a las funciones de Revisiones, como moderación e informes.
- Crear un nuevo sitio. Para obtener más información acerca de cómo crear un sitio nuevo, consulte [Crear un sitio de comercio electrónico](create-ecommerce-site.md). 

## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Asociar un sitio en línea con un canal](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)

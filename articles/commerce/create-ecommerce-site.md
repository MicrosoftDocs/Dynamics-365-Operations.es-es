---
title: Crear un sitio de comercio electrónico
description: En este tema se describen los pasos y la información necesarios para crear un nuevo sitio de comercio electrónico con el generador de sitios de Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7d552f29fd8f52b512a7c21b36b0a814cac50646
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517193"
---
# <a name="create-an-e-commerce-site"></a>Crear un sitio de comercio electrónico

[!include [banner](includes/banner.md)]

En este tema se describen los pasos y la información necesarios para crear un nuevo sitio de comercio electrónico con el generador de sitios de Dynamics 365 Commerce.

Cuando licencia las capacidades de Dynamics 365 Commerce, el creador de sitios contará con un sitio de inicio que puede usar como base para su propio sitio. Sin embargo, si desea comenzar desde cero o si desea establecer un segundo sitio, deberá establecer un nuevo sitio en el entorno de creación del sitio. 

## <a name="set-up-your-site"></a>Configurar su sitio

Para configurar el sitio, haga lo siguiente.

1. Abra el entorno del generador de sitios. Encontrará un vínculo al generador de sitios en Microsoft Lifecycle Services (LCS), en la página de características del entorno para Commerce.
1. En la página principal para el entorno de creación del sitio, seleccione **Nuevo sitio**.
1. En el cuadro de diálogo **Nuevo sitio**, proporcione la siguiente información.

| Campo                               | Descripción |
|-------------------------------------|-------------|
| Nombre del sitio                           | Especifique el nombre para mostrar que se debe usar para el sitio en el entorno de creación del sitio. Este nombre solo es visible en el entorno de creación y no se mostrará a los clientes. |
| Grupo de seguridad del administrador del sitio | Especifique el grupo de seguridad de Microsoft Azure Active Directory (Azure AD) que administra a los usuarios con el rol de administrador de este sitio. |
| Canal predeterminado (número de unidad operativa) | Seleccione la tienda en línea para la que este sitio servirá como el escaparate web. Si desea que su sitio de comercio electrónico admita varias tiendas en línea, debe asociar las tiendas con su sitio en **Valores de configuración de sitio** después de configurar el sitio. |
| Idioma predeterminado                            | Especifique el idioma predeterminado para esta tienda en línea y mercado. Una tienda en línea puede admitir varios idiomas. Si desea admitir varios idiomas para esta tienda en línea u otra tienda en línea, puede configurar dicha compatibilidad en **Valores de configuración de sitio** después de que se configure el sitio.  |
| Dominio                              | Seleccione un nombre de dominio que servirá como el dominio para esta tienda en línea. Si no ha configurado dominios en LCS, puede dejar este campo en blanco. Cuando su dominio se haya configurado en LCS, debe agregarlo a la tienda en línea en **Valores de configuración de sitio**.  |
| Ruta                              | Cuando el sitio admite más de un idioma para un nombre de dominio determinado, use el campo de ruta para crear una dirección URL de sitio única para dicha combinación de dominio e idioma. Si el idioma que ha especificado en el campo **Idioma predeterminado** es el único idioma que admitirá para este dominio, o seguirá siendo el idioma predeterminado después de que haya localizado su sitio en otros idiomas, se recomienda dejar este campo en blanco. |


Una vez creado el sitio, puede comprobar que esté asociado a la tienda en línea seleccionando la pestaña **Productos**. Solo debería ver la selección de productos que se ha asignado a la tienda en línea. Puede usar el menú desplegable en la parte superior izquierda de la página para obtener acceso a los productos asignados por categoría.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Implementar un inquilino nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Asociar un sitio de Dynamics 365 Commerce con un canal en línea](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
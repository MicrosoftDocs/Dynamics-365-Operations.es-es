---
title: Crear un sitio de comercio electrónico
description: Este tema describe las tareas asociadas a la creación de un sitio nuevo de comercio electrónico en Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/31/2019
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
ms.openlocfilehash: 54259d3f5dfd8c8e1ff2caaadfac497cc0e133e0
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945844"
---
# <a name="create-an-e-commerce-site"></a>Crear un sitio de comercio electrónico

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema describe las tareas asociadas a la creación de un sitio nuevo de comercio electrónico en Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Para empezar a desarrollar su sitio de comercio electrónico, primero debe establecer un nuevo sitio en el entorno de creación del sitio. Para poder crear un sitio nuevo, se debe crear al menos una tienda en línea en Dynamics 365 Retail. 

## <a name="set-up-your-site"></a>Configurar su sitio

Para configurar el sitio, haga lo siguiente.

1. En el Microsoft Lifecycle Services (LCS), seleccione el vínculo para el entorno de creación del sitio. 
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

[Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Asociar un sitio en línea con un canal](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)

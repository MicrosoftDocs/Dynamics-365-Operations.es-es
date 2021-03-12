---
title: Módulo selector de sitio
description: En este tema se trata el modulo selector de sitio y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: ed00836c435bd391e5edef1f6a99889c80f45211
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985595"
---
# <a name="site-selector-module"></a>Módulo selector de sitio

[!include [banner](includes/banner.md)]

En este tema se trata el modulo selector de sitio y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Cuando una empresa tiene diferentes sitios en mercados, regiones y locales, los usuarios del sitio necesitan una forma fácil de cambiar entre sitios y seleccionar su sitio de compras preferido. Para hacer posible este escenario, el módulo selector de sitio permite a los usuarios navegar en varios sitios.

El módulo selector de sitio debe configurarse con la lista de sitios (mercados, regiones o locales) que los usuarios del sitio pueden explorar.

> [!NOTE]
> El módulo selector de sitio está disponible en la versión Dynamics 365 Commerce 10.0.14.

La siguiente ilustración muestra un ejemplo de un módulo selector de sitio que aparece en el encabezado de una página de sitio.

![Ejemplo de un módulo selector de sitio en el encabezado de una página de sitio](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a>Propiedades del módulo selector de sitio

| Nombre de la propiedad | Valor                 | Descripción |
|---------------|-----------------------|-------------|
| Cabecera       | Texto                  | El encabezado del módulo. |
| Opciones de sitio  | Nombre, imagen, URL      | Esta propiedad especifica para cada sitio que se incluye en el módulo un nombre, un vínculo a la página de inicio del sitio y una imagen opcional para mostrar. La imagen puede ser una bandera o alguna representación de un mercado, región o localidad. |

## <a name="add-a-site-selector-module-to-a-page"></a>Agregar un módulo selector de sitio a una página

El módulo selector de sitio se puede agregar al [Módulo de encabezado](author-header-module.md) debajo de la ranura del selector de sitio. Una vez agregado, puede definir el encabezado del módulo y las opciones del sitio.

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de navegación](add-breadcrumb.md)

[Módulo de menú de navegación](nav-menu-module.md)

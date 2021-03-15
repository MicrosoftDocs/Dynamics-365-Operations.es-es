---
title: Glosario del modelo de página
description: En este tema se describen varios elementos que se utilizan en las páginas de un sitio de Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f676503691049938fb8b6b7bfcac159e2f61bc6f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972691"
---
# <a name="page-model-glossary"></a>Glosario del modelo de página


[!include [banner](includes/banner.md)]

En este tema se describen varios elementos que se utilizan en las páginas de un sitio de Microsoft Dynamics 365 Commerce.

## <a name="page-element-definitions"></a>Definiciones de elemento de página

En la tabla siguiente se ofrece un resumen de las condiciones con las que debería estar familiarizado al cambiar el aspecto y el contenido de su sitio. Para obtener explicaciones y procedimientos más completos, siga los vínculos.

| Condición | Descripción y notas |
|------|-----------------------|
| [Módulo](work-with-modules.md) | <p>**Definición:** los módulos son bloques de creación que se pueden crear y componer el esqueleto de una página web. Entre los ejemplos se incluyen módulos de encabezado, elemento principal y carrusel.</p><p>**Donde se ha seleccionado:** los módulos implementados se pueden seleccionar y configurar en diversas etapas del flujo de trabajo de la creación de sitios, como las etapas de creación de fragmentos, páginas, diseños y plantillas.</p><p>**Dónde se ha editado:** los módulos personalizados se crean mediante con el kit de desarrollo de software (SDK). A continuación, se cargan en su sitio, donde están disponibles para su selección.</p> |
| Propiedad de módulo | <p>**Definición:** las propiedades de módulos son valores específicos que se han definido por el módulo. Se pueden editar en las herramientas de creación de comercio electrónico. Por ejemplo, las propiedades del módulo se utilizan para establecer el encabezado y la imagen de fondo de un módulo de banner.</p><p>**Donde se ha configurado:** las propiedades del módulo están seleccionadas y configuradas en el panel de propiedades que aparece en los entornos de creación (editores) para la configuración de aplicaciones, plantillas, diseños, páginas y fragmentos.</p> |
| [Plantilla](templates-layouts-overview.md) | <p>**Definición:** las plantillas definen las combinaciones y las opciones de módulo que se deben utilizar para una categoría de páginas (por ejemplo, páginas de marketing, páginas de categorías y páginas de productos).</p><p>**Donde ha seleccionado:** las plantillas se pueden seleccionar durante los flujos de trabajo de creación de páginas o diseños.</p><p>**Donde se ha editado:** las plantillas se crean en el editor de plantillas. No se requiere ningún código para crearlas o modificarlas.</p> |
| [Diseño](templates-layouts-overview.md) | <p>**Definición:** los diseños definen la organización y la selección final de módulos del conjunto de opciones de la plantilla principal. Se puede configurar un diseño para una sola página (*diseño personalizado*) o se puede compartir por varias páginas (*diseño preestablecido*).</p><p>**Donde se ha seleccionado:** los diseños se pueden seleccionar durante la creación de páginas nuevas o cuando se requiere un diseño distinto para una página existente.</p><p>**Donde se ha editado:** los diseños se crean en el editor de diseños. No se requiere ningún código para crearlas o modificarlas.</p> |
| [Instancia de página](modify-existing-page.md) | <p>**Definición:** las instancias de página definen el contenido localizado específico de página final para una página única. Este contenido se obtiene de los valores de las propiedades de módulo.</p><p>**Donde se ha seleccionado:** las páginas se seleccionan cuando se asignan direcciones URL.</p><p>**Donde se ha editado:** las páginas se editan en el editor de páginas. No se requiere ningún código para crearlas o modificarlas.</p> |
| [Tema](select-site-theme.md) | <p>**Definición:** los temas definen la hoja de estilos en cascada (CSS) y determinan el aspecto de los módulos que se representan en una página.</p><p>**Donde se ha seleccionado:** cuando se carga un tema en un sitio mediante Lifecycle Services (LCS) de Microsoft Dynamics, se puede seleccionar como propiedad del módulo de contenedor de páginas.</p><p>**Donde se ha editado:** los temas se crean y editan actualmente con el SDK. A continuación, se cargan en el sitio mediante LCS.</p> |
| [Fragmento](work-with-fragments.md) | <p>**Definición:** los fragmentos son módulos completamente configurados con contenido localizado que se pueden volver a usar y actualizar centralmente entre varias páginas. Por ejemplo, un fragmento que se crea desde un módulo de encabezado se puede usar en todas las plantillas y en todas las páginas del sitio, y actualizarse centralmente en un lugar.</p><p>**Donde se ha seleccionado:** los fragmentos se pueden seleccionar siempre que se puedan seleccionar los módulos. Se pueden sustituir por un módulo para ayudar a aumentar la eficacia a través de la creación centralizada y reutilizable.</p><p>**Donde se ha editado:** los fragmentos se editan en el editor de fragmentos. No se requiere ningún código para crearlas o modificarlas.</p> |
| [URL](create-page-URL.md) | <p>**Definición:** los localizadores uniformes de recursos (URLs) son las direcciones que apuntan a páginas web o a otras direcciones URL.</p><p>**Donde se ha seleccionado:** las direcciones URL se seleccionan si se requieren vínculos entre páginas.</p><p>**Donde se ha editado:** las direcciones URL se editan en el editor de URL. No se requiere ningún código para crearlas o modificarlas.</p> |
| Activo | <p>**Definición:** los activos son binarios de archivos que tienen una extensión como .jpg, .docx, .pdf, o .mpg.</p><p>**Donde se ha seleccionado:** los activos están seleccionados como propiedades de módulo para módulos que los requieren.</p><p>**Donde ha editado:** los activos se cargan y los metadatos asociados se editan en el administrador de activos.</p> |

## <a name="additional-resources"></a>Recursos adicionales

[Métodos para agregar contenido](add-manage-content.md)

[Estados y ciclo de vida de documentos](document-states-overview.md)

[Trabajar con grupos de publicación](publish-groups.md)

[Habilitar y usar el uso compartido entre canales](cross-channel-sharing.md)

[Trabajar con módulos](work-with-modules.md)

[Trabajar con fragmentos](work-with-fragments.md)

[Visión general de plantillas y diseños](templates-layouts-overview.md)

[Personalizar navegación del sitio](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
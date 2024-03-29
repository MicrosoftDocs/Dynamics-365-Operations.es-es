---
title: Agregar un logotipo
description: En este artículo se describe cómo agregar un logotipo a su sitio en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 4bd47907791edfd0ab81282bd1e465ac54172cdf
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278107"
---
# <a name="add-a-logo"></a>Agregar un logotipo

[!include [banner](includes/banner.md)]

En este artículo se describe cómo agregar un logotipo a su sitio en Microsoft Dynamics 365 Commerce.

Cuando crea su sitio, una de las primeras cosas que probablemente hará es agregar el logotipo de su empresa o marca al encabezado del sitio. La biblioteca del módulo de Dynamics 365 Commerce Online proporciona un módulo que facilita esta tarea.

Puede agregar un logotipo directamente a una plantilla, diseño o página. De esta manera, puede cambiar fácilmente el logotipo que aparece en páginas específicas o grupos de páginas. Sin embargo, este artículo cubre el escenario más frecuente, donde agrega su logotipo a un fragmento de encabezado que puede reutilizarse en todas las páginas de su sitio.

## <a name="prerequisites"></a>Requisitos previos

Antes de poder agregar un logotipo a todas las páginas de su sitio, debe completar estas tareas.

1. Cargue su logotipo en la Biblioteca de medios.
1. Crear un fragmento de encabezado. Para obtener más información sobre cómo crear y usar fragmentos, vea [Trabajar con fragmentos](work-with-fragments.md).
1. Incluya el fragmento de encabezado en la plantilla que usan las páginas de su sitio para su diseño y opciones de módulo. Para obtener más información sobre las plantillas, vea [Trabajar con plantillas](work-with-templates.md).

## <a name="add-a-logo-to-a-header-fragment"></a>Agregar un logotipo a un fragmento de encabezado

Para agregar un logotipo al fragmento de encabezado de su sitio, siga estos pasos.

1. En el panel de navegación de la izquierda, seleccione **Fragmentos**.
1. Seleccione el fragmento de encabezado que ha creado y, a continuación, seleccione **Editar**.
1. Expanda el módulo de encabezado.
1. En el panel de propiedades del módulo de encabezado, proporcione una imagen y un vínculo para el logotipo. 
1. Guarde el fragmento de encabezado, termine de editarlo y publíquelo.

Después de publicar el fragmento de encabezado actualizado, todas las páginas del sitio que usan la plantilla que contiene el fragmento de encabezado mostrarán su logotipo.

## <a name="additional-resources"></a>Recursos adicionales

[Seleccionar un tema de sitio](select-site-theme.md)

[Trabajar con archivos de invalidaciones CSS](css-override-files.md)

[Agregar un icono de favoritos](add-favicon.md)

[Agregar un aviso de derechos de autor](add-copyright-notice.md)

[Agregar idiomas al sitio](add-languages-to-site.md)

[Agregar secuencia de comandos a páginas del sitio para admitir telemetría](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]

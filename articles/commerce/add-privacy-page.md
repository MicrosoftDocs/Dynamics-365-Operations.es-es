---
title: Agregar una página de directivas de privacidad
description: En este artículo se describe cómo agregar una página de directiva de privacidad a su sitio en Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f220ee5502f269299d2af253d7790e503668c0ef
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871711"
---
# <a name="add-a-privacy-policy-page"></a>Agregar una página de directivas de privacidad

[!include [banner](includes/banner.md)]

En este artículo se describe cómo agregar una página de directiva de privacidad a su sitio en Microsoft Dynamics 365 Commerce.

El cumplimiento de la privacidad incluye medidas organizativas que informan a los usuarios del sitio sobre cómo se recopilan y manejan sus datos. Los usuarios pueden decidir cómo quieren que se manejen sus datos personales y pueden tomar las medidas adecuadas.

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a>Revisar la declaración de privacidad de Microsoft en Dynamics 365 Commerce

Para revisar la declaración de privacidad de Microsoft mientras está conectado a las herramientas de creación de Dynamics 365 Commerce, seleccione el botón **Ayuda** ( **?**) en la esquina superior derecha y luego seleccione **Privacidad y cookies**. Se abre una nueva pestaña que tiene un enlace a la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="build-a-privacy-policy-page-for-your-site"></a>Crear una página de directiva de privacidad para su sitio

En Dynamics 365 Commerce, hay varias formas de dar a los usuarios de su sitio acceso a su directiva de privacidad. Esta sección muestra cómo crear una página de directiva de privacidad y luego hacer referencia a la página utilizando un fragmento de pie de página.

La guía que sigue es un ejemplo que muestra cómo construir una página de directiva de privacidad genérica para un sitio de Commerce. Usted es responsable de diseñar e implementar la solución de página de directiva de privacidad que mejor cumpla con los requisitos legales de su empresa.

Para comenzar, en las herramientas de creación, vaya al sitio para el que desea crear una página de directiva de privacidad.

### <a name="create-a-template"></a>Crear una plantilla

> [!NOTE]
> Si ya se ha creado una plantilla que se puede utilizar para la página de directiva de privacidad, salte a la sección [Crea una página de directiva de privacidad](#build-a-privacy-policy-page).

Para crear una plantilla, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una plantilla de página.
1. En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, ingrese **Plantilla de banner promocional** y luego seleccione **Aceptar**.
1. En la plantilla, agregue los módulos necesarios a los espacios de página requeridos. Para orientarse, pase el cursor sobre los signos de exclamación rojos. (Por ejemplo, el espacio **Encabezado HTML** puede requerir un módulo **Script externo predeterminado**).
1. En el espacio **Cuerpo**, agregue un módulo de **Página por defecto**.
1. En el módulo **Página predeterminada**, en el espacio **Principal** agregue un módulo **Bloque de contenido enriquecido**.
1. En el módulo **Bloque de contenido enriquecido** módulo, agregue un módulo **Elemento de bloque de contenido enriquecido**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.

### <a name="build-a-privacy-policy-page"></a>Crear una página de directivas de Privacidad

Para crear una página de directiva de privacidad, siga estos pasos.

1. Vaya a **Páginas** y después seleccione **Nuevo** para crear una página.
1. En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla para la página de política de privacidad.
1. Introduzca un nombre y una URL de página y después seleccione **Aceptar**. 
1. En el espacio **Principal** de la nueva página, agregue un módulo de **Bloque de enriquecimiento de contenido**.
1. En el módulo **Bloque de contenido enriquecido** módulo, agregue un módulo **Elemento de bloque de contenido enriquecido**.
1. En el panel de propiedades para el módulo **Bloque de contenido enriquecido**, seleccione **Agregar fuente de datos** y luego seleccione **Contenido de texto enriquecido**.
1. En el editor de texto enriquecido, introduzca el contenido de la página de política de privacidad. Expanda el editor de texto enriquecido al modo de pantalla completa según lo requiera.
1. Cuando haya terminado de introducir contenido, seleccione **Vista previa** para obtener una vista previa de la página en el navegador web.
1. Complete las adiciones restantes a las propiedades de página y módulo.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

Para publicar la URL de la página de directiva de privacidad, siga estos pasos.

1. Vaya a **Direcciones URL** y seleccione la URL de la página de directiva de privacidad.
1. Seleccione **Publicar** para publicar la URL seleccionada.

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a>Crear un enlace a la página de directiva de privacidad en un pie de página

Puede agregar un enlace a la página de directiva de privacidad a un fragmento. De esta manera, puede compartir el enlace y actualizarlo en varias páginas del sitio haciendo referencia al fragmento. Este ejemplo muestra cómo agregar un enlace a la página de directiva de privacidad a un fragmento de pie de página.

Para agregar un enlace a un fragmento de pie de página, siga estos pasos.

1. Vaya a **Fragmentos** y después seleccione **Nuevo** para crear un fragmento de página.
1. En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Pie de página**.
1. En **Nombre del fragmento**, introduzca un nombre para el fragmento y luego seleccione **Aceptar**.
1. En la posición **Categoría de pie de página**, agregue un módulo **Elemento de pie de página**.
1. En el panel de propiedades de la derecha, seleccione **Texto del enlace**.
1. En el cuadro de diálogo **Texto del enlace**, introduzca el texto del enlace y el objetivo del enlace de la página de directiva de privacidad, y luego haga clic en **Aceptar**.
1. Para obtener la URL de la página de directiva de privacidad, vaya a **Páginas**, vaya a la página de directiva de privacidad y copie la URL del panel de propiedades.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.
1. Obtenga una vista previa del fragmento y pruebe el enlace a la página de directiva de privacidad.

Ahora se puede hacer referencia al fragmento en la plantilla para otras páginas del sitio. Cuando se hace referencia a este fragmento en el módulo **Pie de página** de una plantilla, la referencia del enlace aparecerá en cualquier página que se cree utilizando esa plantilla.

## <a name="additional-resources"></a>Recursos adicionales

[Resumen de conformidad](compliance-overview.md)

[Características y funcionalidades de accesibilidad](accessibility.md)

[Cumplimiento de cookies](cookie-compliance.md)

[Reemplazar id. de usuario asociado con cambios de contenido con seguimiento](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Integrar Customer Voice en páginas del sitio de comercio electrónico
description: Este artículo describe cómo integrar Microsoft Dynamics 365 Customer Voice en las páginas de sitios de comercio electrónico de Dynamics 365 Commerce.
author: samjarawan
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: c8c67ecf4950c92fc91c8d119e06e5e8afff0ddf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850339"
---
# <a name="integrate-customer-voice-into-e-commerce-site-pages"></a>Integrar Customer Voice en páginas del sitio de comercio electrónico

[!include [banner](../includes/banner.md)]

Este artículo describe cómo integrar Microsoft Dynamics 365 Customer Voice en las páginas de sitios de comercio electrónico de Dynamics 365 Commerce.

Puede integrar [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) en su sitio de comercio electrónico para recopilar, analizar y realizar un seguimiento de los comentarios de los clientes en tiempo real. Para comenzar con la integración, debe crear una cuenta y seleccionar una plantilla de proyecto de Customer Voice para el tipo de comentarios que desea recopilar.

## <a name="integrate-the-customer-voice-service"></a>Integrar el servicio Customer Voice

Para crear una cuenta de Customer Voice, vaya a [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) y siga las indicaciones.

Después de crear una cuenta de Customer Voice e iniciar sesión, el siguiente paso es seleccionar una plantilla de proyecto para el tipo de comentarios que desea recopilar.

Para seleccionar una plantilla de proyecto de Customer Voice, siga estos pasos.

1. Vaya a la [Página de plantilla de proyecto de Customer Voice](https://customervoice.microsoft.com/Pages/ProjectPage.aspx).
1. Seleccione **Introducción**.
1. Seleccione la plantilla de proyecto para el tipo de comentarios que desea recopilar y, a continuación, seleccione **Siguiente**.
1. En la pestaña **Enviar**, en **Eegir un formato de inserción**, seleccione un formato de inserción. El campo **Código insertado** muestra el código que se debe insertar en el creador de sitios de Commerce.

Los ejemplos en este artículo usan la plantilla de proyecto **Encuesta periódica a clientes** y el formato insertado **Botón**.

La siguiente ilustración de ejemplo muestra la página de plantilla de proyecto **Encuesta periódica a clientes**, donde está seleccionada la opción para el formato insertado **Botón** y el código para insertar aparece en el campo **Código insertado**. Se requieren tres acciones separadas para insertar el código facilitado en las páginas de su sitio, como se describe en las siguientes secciones.

![Página de encuestas periódicas de Customer Voice con la opción Botón seleccionada.](media/customer-voice-integration-1.png)

### <a name="embed-the-external-script-url"></a>Incruste la URL del script externo

En todas las páginas del sitio que deben tener una encuesta de Customer Voice, debe insertar la URL del script externo que Customer Voice proporcionó en el código para insertar. La mejor manera de insertar la secuencia de comandos en varias páginas del sitio es crear un fragmento en el creador del sitio que contenga la URL de la secuencia de comandos externa y luego agregar el fragmento a las plantillas de página adecuadas. Después de publicar una plantilla actualizada, el código del script externo insertado se parecerá al siguiente ejemplo en las páginas afectadas del sitio.

```html
<script src=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.js type="text/javascript"></script>
```

Para obtener más información sobre fragmentos, vea [Trabajar con fragmentos](work-with-fragments.md).

> [!NOTE]
> Solo tiene que añadir la URL al fragmento. El módulo de script externo agregará el otro código de script.

Para insertar la URL del script externo en un fragmento, siga estos pasos.

1. En el creador de sitios, cree un fragmento basado en el [Módulo de script externo](script-module.md).
1. En el nuevo fragmento, seleccione el espacio **Script externo predeterminado**.
1. En el panel de propiedades **Script externo predeterminado**, en el campo **Origen de script**, introduzca la URL del script externo, como se muestra en la siguiente ilustración de ejemplo.

    ![URL del script externo en el campo Origen del script para el nuevo fragmento.](media/customer-voice-integration-2.png)

1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. Para publicar la el fragmento, seleccione **Publicar**.

El nuevo fragmento que contiene el bloque de script externo insertado ahora está listo para agregarse a la plantilla de página adecuada.

### <a name="embed-the-external-style-sheet-code"></a>Incrustar el código de la hoja de estilos externa

A continuación, en todas las páginas del sitio que deben tener una encuesta de Customer Voice, debe insertar el código de la hoja de estilos externa que Customer Voice proporcionó en el código para insertar. Como en la sección anterior, la mejor manera de insertar el código de la hoja de estilos externa en varias páginas del sitio es crear un fragmento en el creador del sitio que contenga el código de la hoja de estilos externa y luego agregar el fragmento a las plantillas de página adecuadas. El código de la hoja de estilos externa insertada se parecerá al siguiente código de ejemplo.

```typescript
<link rel="stylesheet" type="text/css" href=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.css />
```

Para insertar el código de la hoja de estilos externa en un fragmento, siga estos pasos.

1. En el creador de sitios, cree un fragmento basado en el [Módulo de metaetiquetas](metatags-module.md).
1. En el fragmento, seleccione el espacio **Metaetiquetas predeterminadas**.
1. En el panel de propiedades **Metaetiquetas predeterminadas**, en el campo **Metaetiquetas**, introduzca la hoja de estilos externa, como se muestra en la siguiente ilustración de ejemplo.

    ![Código de hoja de estilos externa en el campo Metaetiquetas para el nuevo fragmento.](media/customer-voice-integration-3.png)

1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. Para publicar la el fragmento, seleccione **Publicar**.

El nuevo fragmento que contiene el código de la hoja de estilos externa insertado ahora está listo para agregarse a la plantilla de página adecuada.

### <a name="embed-the-inline-script-code"></a>Incruste el código de script en línea 

A continuación, en todas las páginas del sitio que deben tener una encuesta de Customer Voice, debe insertar el código del script en línea que Customer Voice proporcionó en el código para insertar. Como en las secciones anteriores, la mejor manera de insertar el código de script en línea en varias páginas del sitio es crear un fragmento en el creador del sitio que contenga el código de script en línea y luego agregar el fragmento a las plantillas de página adecuadas.

En el siguiente ejemplo de código de secuencia de comandos en línea, **SURVEY\_KEY** es un marcador de posición. El valor para **SURVEY\_KEY** debe coincidir con la clave de encuesta real que Customer Voice proporcionó en el código para insertar. La última línea llama al código para mostrar el botón de la encuesta después de un segundo, para garantizar que los scripts tengan tiempo suficiente para cargarse. Según la encuesta que haya seleccionado, es posible que también deba agregar o actualizar otros metadatos, como el nombre de la empresa.

```html
function renderSurveyButton() {
    var se = new SurveyEmbed("SURVEY_KEY","https://customervoice.microsoft.com/","https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/","true");

    var context = {
        "First Name":"",
        "Last Name": "",
        "locale": "en-us",
        "companyname": "Adventure Works"
    };
    se.renderButton(context);
}

setTimeout(renderSurveyButton, 4000);
```

Para insertar el código de script en línea en un fragmento, siga estos pasos.

1. En el creador de sitios, cree un fragmento basado en el [Módulo de script en línea](script-module.md).
1. En el nuevo fragmento, seleccione el espacio **Script en línea predeterminado**.
1. En el panel de propiedades **Script externo en línea**, en el campo **Script en línea**, introduzca el código de script en línea, como se muestra en la siguiente ilustración de ejemplo.

    ![Código de script en línea en el campo Script en línea para el nuevo fragmento.](media/customer-voice-integration-4.png)

1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. Para publicar la el fragmento, seleccione **Publicar**.

El nuevo fragmento que contiene el bloque de código de script en línea ahora está listo para agregarse a la plantilla de página adecuada.

## <a name="add-fragments-to-a-template"></a>Agregar fragmentos a una plantilla

Cuando haya terminado de crear los fragmentos que contienen el código insertado de Customer Voice, debe agregarlos a las plantillas de página que están asociadas con las páginas del sitio donde desea usarlos. En la siguiente ilustración de ejemplo, los tres fragmentos de ejemplo se han agregado a una plantilla de página de detalles del producto (PDP).

![Fragmentos de ejemplo agregados a una plantilla PDP.](media/customer-voice-integration-5.png)

Después de que se publique la plantilla actualizada, la encuesta de Customer Voice aparecerá en todas las páginas controladas por la plantilla.

Para obtener información sobre las plantillas, vea [Trabajar con plantillas](work-with-templates.md).

## <a name="configure-content-security-policy"></a>Configurar la directiva de seguridad de contenido

De forma predeterminada, la directiva de seguridad de contenido (CSP) no permite llamadas a otros servicios a menos que se realice una configuración adicional. Por lo tanto, después de publicar las plantillas actualizadas, es probable que la encuesta no se cargue en las páginas del sitio correspondiente. Para ver los errores relacionados con CSP, abra las herramientas de desarrollo de su navegador web (F12) y luego vaya a una página que tenga la encuesta. Los errores relacionados con CSP aparecerán en la salida de la consola.

Para configurar CSP en el creador de sitios para corregir los errores, siga estos pasos.

1. Ir **Configuraciones del sitio \> Extensiones**.
1. En la pestaña **Directiva de seguridad de contenido**, agregue `https://customervoice.microsoft.com/` a la directiva **child-src**.
1. Agregue `https://customervoice.microsoft.com/` a la directiva **frame-src**.
1. Agregue `https://mfpembedcdnmsit.azureedge.net` y **.azureedge.net** a la directiva **img-src**.

Para más información, consulte [Directiva de seguridad de contenido](manage-csp.md).

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de scripts externos](script-module.md)

[Módulo de metaetiquetas](metatags-module.md)

[Módulo de script en línea](script-module.md)

[Directiva de seguridad de contenido](manage-csp.md)

[Trabajar con fragmentos](work-with-fragments.md)

[Trabajar con plantillas](work-with-templates.md)

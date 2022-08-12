---
title: Insertar aplicaciones de terceros
description: Este artículo explica cómo insertar aplicaciones de terceros para aumentar la funcionalidad de producto.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, UserWorkspaceAdd, UserWorkspaceConfigureWebsite
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2021-04-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ef5ed6c3c99d62010643940f3e2f158963ff0dc2
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "9123730"
---
# <a name="embed-third-party-apps"></a>Insertar aplicaciones de terceros

[!include [banner](../includes/banner.md)]

Muchos clientes utilizan diversas aplicaciones para administrar su negocio. Algunas de esas aplicaciones son aplicaciones web de terceros que funcionan junto con aplicaciones de finanzas y operaciones. Para proporcionar una experiencia de usuario más fluida, puede utilizar la característica **Aplicaciones de página completa** para insertar esas aplicaciones de terceros directamente en sus aplicaciones de finanzas y operaciones (siempre que las aplicaciones de terceros permitan insertarlas). De esta manera, los usuarios pueden acceder a los sitios web y aplicaciones que necesitan sin tener que cambiar de pestaña o ventana.

Antes de poder insertar aplicaciones de terceros en el producto, debe activar la característica **Aplicaciones de página completa** en Administración de características. A continuación, puede utilizar uno de los siguientes métodos para insertar una aplicación o un sitio web de terceros. Estos métodos son análogos a los métodos que se utilizan para insertar aplicaciones de lienzo desde Microsoft Power Apps en aplicaciones de finanzas y operaciones.

- Inserte la aplicación o el sitio web en una página existente como una página de pestaña nueva (pestaña dinámica, pestaña desplegable, hoja o sección del espacio de trabajo).
- Cree una nueva experiencia de página completa para la aplicación o el sitio web desde el panel.

## <a name="embed-a-website-on-an-existing-page"></a>Insertar un sitio web en una página existente

Utilice este procedimiento si desea complementar una página existente en el sistema con una aplicación incorporada.

1. Abra la página en la que desee insertar la aplicación.
2. Abra el panel **Agregar una aplicación**:

    1. Seleccione **Configuración** y, a continuación, **Personalizar** para abrir la barra de herramientas **Personalización**.
    2. Seleccione **Más \> Agregar una aplicación**.

3. Seleccione la región de la página donde desee agregar la aplicación. Esta región debe ser un *contenedor de pestañas* para una pestaña dinámica, una pestaña desplegable, una hoja o una sección de espacio de trabajo.
4. Seleccione **Sitio web**.
5. Configurar la aplicación insertada:

    - **Nombre**: introduzca el texto que debe mostrarse para la pestaña que contiene la aplicación insertada. A menudo, querrá que este texto sea el nombre de la aplicación.
    - **URL**: especifique la ubicación de la aplicación.

    > [!IMPORTANT]
    > - Por motivos de seguridad, la URL debe utilizar el protocolo seguro de transferencia de hipertexto (HTTPS).
    > - La aplicación o el sitio web deben configurarse para que se puedan insertar.

6. Seleccione **Guardar** para insertar la aplicación en la página. La aplicación se agrega como la última pestaña o sección del grupo.
7. Confirme que la aplicación aparece como se esperaba. Si la aplicación no se representa, consulte la sección [Solución de problemas](#troubleshooting) más adelante en este artículo.
8. Abra el selector de vista y seleccione **Guardar** (si la aplicación debe estar asociada con la vista actual) o **Guardar como** (para guardar la aplicación en una vista diferente).

    Si la página no tiene un selector de vista (por ejemplo, si la página es un cuadro de diálogo o un espacio de trabajo), puede omitir este paso.

## <a name="embed-a-website-as-a-full-page-experience-from-the-dashboard"></a>Inserte un sitio web como una experiencia de página completa desde el panel

Utilice este procedimiento si la aplicación que desea insertar no está relacionada con una página existente, o si solo desea una experiencia de página completa para la aplicación dentro de la aplicación de finanzas y operaciones.

1. Abra el panel.
2. Seleccione y mantenga presionada (o haga clic con el botón derecho en) el panel de información, seleccione **Personalizar** y, a continuación, seleccione **Agregar una página**.
3. En el panel **Agregar una página**, seleccione **Sitio web**.
4. Configurar la aplicación insertada:

    - **Nombre**: introduzca el texto que debe mostrarse en el mosaico que se agrega para la aplicación insertada en el tablero. A menudo, querrá que este texto sea el nombre de la aplicación.
    - **URL**: especifique la ubicación de la aplicación.

    > [!IMPORTANT]
    > - Por motivos de seguridad, la URL debe utilizar HTTPS.
    > - La aplicación o el sitio web deben configurarse para que se puedan insertar.

5. Seleccione **Guardar** para agregar la aplicación al panel de información como un nuevo mosaico.
6. Seleccione el nuevo mosaico en el panel y confirme que la aplicación aparece como se esperaba. Si la aplicación no se representa, consulte la sección [Solución de problemas](#troubleshooting) más adelante en este artículo.

## <a name="sharing-embedded-apps"></a>Uso compartido de aplicaciones insertadas

Una vez que haya insertado una aplicación mediante uno de los métodos que se describen en las secciones anteriores, es posible que desee compartir la vista con otros usuarios del sistema. Para compartir una aplicación insertada, utilice uno de los siguientes métodos:

- **Publicar la vista (recomendado):** si la aplicación insertada se ha guardado en una vista, la forma recomendada y preferida de compartirla es publicar la vista para los usuarios que tengan los roles de seguridad adecuados en las entidades jurídicas de destino. En este caso, solo los usuarios deseados verán la aplicación insertada en esa página. Para obtener más información sobre cómo publicar una vista, vea [Publicación de vistas](saved-views.md#publishing-views).

    También puede publicar una aplicación que se haya insertado como una experiencia de página completa desde el panel. En el tablero, seleccione y mantenga presionado (o haga clic con el botón derecho) en el mosaico asociado con la aplicación, seleccione **Personalizar** y luego seleccione **Publicar página**. Se muestra una experiencia que se asemeja a la experiencia *Publicar vistas*, y puede seleccionar los roles de seguridad en los que desea publicar. En la actualización 10.0.21 o posterior, si la característica **Compatibilidad mejorada con entidades jurídicas para vistas guardadas** está activada, también puede publicar la aplicación para las entidades jurídicas deseadas.

- **Copiar la personalización:** para las páginas que no admiten vistas (por ejemplo, cuadros de diálogo o áreas de trabajo), o para la experiencia de la aplicación de página completa, puede copiar la personalización a los usuarios adecuados. Para más información, consulte [Compartir personalizaciones](personalize-user-experience.md#sharing-personalizations).

## <a name="viewing-embedded-apps"></a>Vista de aplicaciones insertadas

Para ver una aplicación de lienzo insertada en una página de aplicaciones de finanzas y operaciones, abra la página que tiene la aplicación insertada. Recuerde que, en algunas páginas, se puede acceder a las aplicaciones insertadas mediante el botón **Power Apps** del panel de acciones estándar. Como alternativa, podrían aparecer directamente en la página como nueva pestaña, ficha desplegable u hoja, o como nueva sección en un espacio de trabajo.

## <a name="editing-or-removing-embedded-apps"></a>Editar o eliminar aplicaciones integradas

Una vez que se ha insertado una aplicación en una página, es posible que deba editar su configuración (por ejemplo, cambiando la etiqueta de la sección o la URL). Alternativamente, es posible que deba eliminarlo de la página. Utilice uno de los siguientes procedimientos para editar la configuración de una aplicación insertada o elimínela por completo.

### <a name="apps-that-are-embedded-on-existing-pages"></a>Aplicaciones que están insertadas en páginas existentes

1. Abra la página donde está insertada la aplicación.
2. Seleccione **Configuración** y, a continuación, **Personalizar** para abrir la barra de herramientas **Personalización**.
3. Seleccione la herramienta **Seleccionar** y luego seleccione la aplicación insertada.
4. Para editar la aplicación, realice los cambios necesarios en su configuración y luego seleccione **Guardar**.

    Alternativamente, para eliminar la aplicación, seleccione **Elliminar**.

5. Vuelva a guardar o vuelva a publicar la vista. Tenga en cuenta que si abandona la página sin guardar explícitamente la vista, ninguna de las acciones que realizó en el panel **Editar sitio web** se mantendrán.

### <a name="apps-that-are-embedded-from-the-dashboard"></a>Aplicaciones que están integradas desde el panel

1. Abra el panel.
2. Seleccione y mantenga presionado (o haga clic con el botón derecho) en el mosaico asociado con la aplicación insertada y luego seleccione **Personalizar**.
3. Para editar la aplicación, seleccione **Editar página**. En el panel **Editar sitio web**, realice los cambios necesarios en la configuración de la aplicación y luego seleccione **Guardar**.

    Alternativamente, para quitar la aplicación, seleccione **Quitar página**.

## <a name="appendix"></a>Apéndice

### <a name="troubleshooting"></a>Solución de problemas

Si un sitio web no se representa correctamente después de estar integrado en una aplicación de Finance and Operation, o si recibe un mensaje de error que indica que a la URL se le negó una conexión, es probable que el sitio web esté configurado para evitar que se inserte en un iframe. Siga estos pasos para determinar si el sitio web se puede insertar.

1. Abra las herramientas de desarrollo para el navegador que está utilizando.
2. En la pestaña **Red**, busque y seleccione la respuesta del sitio insertado.
3. En la pestaña **Encabezados**, en **Encabezados de respuesta**, busque **x-frame-options**. Si **x-frame-options** existe en los encabezados de respuesta y tiene un valor de **DENY** o **SAMEORIGIN**, el sitio web no se puede insertar actualmente. Tendrá que trabajar con el propietario de la aplicación para permitir que se inserte de forma segura.

### <a name="developer-modeling-a-website-on-a-form"></a>[Desarrollador] Modelado de un sitio web en un formulario

Aunque este artículo se centra en insertar aplicaciones o sitios web de terceros mediante la personalización, los desarrolladores también pueden insertarlas en un formulario utilizando la experiencia de desarrollo de Visual Studio. Basta con agregar un **WebsiteHostControl** al formulario. Las propiedades de metadatos disponibles en el control brindan las mismas capacidades que la experiencia de personalización.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]


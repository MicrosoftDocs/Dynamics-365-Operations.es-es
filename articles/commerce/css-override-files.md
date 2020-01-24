---
title: Trabajar con archivos de anulación de CSS
description: Este tema describe por qué, cuándo y cómo usar las hojas de estilo en cascada (CSS) para archivos de anulación en Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b5a50fc0c9060117cdddc0875446afc2edc12a11
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915448"
---
# <a name="work-with-css-override-files"></a>Trabajar con archivos de anulación de CSS

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema describe por qué, cuándo y cómo usar las hojas de estilo en cascada (CSS) para archivos de anulación en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Los estilos de sitio permanentes generalmente se deben manejar a través del tema de un sitio. Los temas proporcionan lo fundamental para CSS y las configuraciones de estilo para los módulos en cualquier página de su sitio. Los temas se crean utilizando el kit de desarrollo de software en línea (SDK) de Dynamics 365 Commerce, y se implementan en sus sitios web a través de Microsoft Dynamics Lifecycle Services (LCS). Las capacidades de depuración de temas y las configuraciones de la interfaz del módulo en el SDK ayudan a los desarrolladores del sitio a crear paquetes de diseño del sitio personalizables y coherentes. Cuando estos paquetes de diseño se implementan en un sitio, los autores del sitio pueden centrarse en crear, editar y publicar contenido en lugar de desarrollar el sitio.

Dado el ciclo de vida habitual de un tema, la dependencia de los desarrolladores para realizar cambios de estilo a través de la canalización de implementación de SDK y LCS puede ser prohibitiva en algunos escenarios. Los prototipos o las revisiones del sitio pueden parecer engorrosos si el SDK no está configurado o si no tiene tiempo para esperar una implementación de LCS.

En estos escenarios, los archivos de anulación de CSS pueden ayudar. En las herramientas de autoría de Commerce, los usuarios autenticados pueden cargar un archivo CSS, ver una vista previa y luego activarlo para anular el tema de un sitio. No se requiere la sobrecarga de la implementación de SDK o LCS. Las anulaciones que se especifican en un archivo de anulación de CSS pueden ser tan pequeñas como un cambio en un estilo de texto único o tan amplio como una revisión completa de la marca.

Antes de usar los archivos de anulación de CSS, tenga en cuenta las siguientes limitaciones:

- Solo un archivo de anulación de CSS puede estar activo en un sitio a la vez. Por lo tanto, todas las anulaciones activas deben estar presentes en un único archivo de anulación.
- Aunque puede obtener una vista previa de las anulaciones en las herramientas de autoría de Commerce, no hay características de depuración dedicadas para ayudar a identificar los errores que introducen las anulaciones. En otras palabras, cuando usa archivos de anulación de CSS, no tiene el mismo conjunto de herramientas que el SDK proporciona para la validación de módulos y autoría.

Sin embargo, los archivos de anulación de CSS proporcionan una forma rápida de crear un prototipo de un diseño o implementar una revisión antes de desarrollar e implementar una actualización completa del tema.

## <a name="create-a-css-override-file"></a>Crear un archivo de anulación de CSS

Para crear un archivo de anulación de CSS, puede usar cualquier entorno de desarrollo integrado (IDE), editor de texto o editor de código fuente. Un enfoque típico es utilizar depuradores web estándar en su navegador para identificar selectores de estilo, propiedades y valores en su sitio existente. La mayoría de los navegadores le permiten cambiar valores y obtener una vista previa en el depurador. Después de identificar los cambios que desea realizar, puede guardarlos en su archivo CSS.

## <a name="upload-a-css-override-file"></a>Cargar un archivo de anulación de CSS

Para subir un archivo de CSS a su sitio en Commerce, siga estos pasos.

1. En las herramientas de creación, vaya al sitio.
1. En el panel de navegación de la izquierda, seleccione **Diseño**.

    > [!NOTE]
    > Dependiendo de la versión de las herramientas de creación de Commerce que esté utilizando, es posible que deba expandir **Configuraciones** en el panel de navegación antes de que pueda seleccionar **Diseño**.

1. En la parte superior del panel de diseño principal, seleccione la pestaña **anular CSS**, si aún no está seleccionada.
1. En **Anulaciones CSS disponibles**, seleccione **Cargar archivo CSS**. Aparecerá una ventana del Explorador de archivos.
1. En el Explorador de archivos, busque y seleccione un archivo CSS y luego seleccione **Abrir**. El archivo subido CSS ahora aparece debajo de **Anulaciones CSS disponibles**.

## <a name="preview-a-css-override-file"></a>Vista previa de un archivo de anulación de CSS

Para obtener una vista previa de un archivo de anulación de CSS antes de activarlo en su sitio activo, siga estos pasos.

1. En el panel de navegación a la izquierda, seleccione **Diseño**, y luego, en la pestaña **Anulación CSS**, en **Anulaciones CSS disponibles**, encuentre el archivo CSS del que desea obtener una vista previa.
1. Al lado del nombre del archivo CSS, seleccione **Vista previa del sitio**.
1. En el cuadro de diálogo **Seleccione una URL**, seleccione la URL del sitio en el que desea ver la anulación aplicada y luego seleccione **Aceptar**.
1. Si hay varias variantes para la URL seleccionada, seleccione la variante deseada en el cuadro de diálogo **Vista previa de variaciones** que aparece.

Se abre una nueva pestaña o ventana del navegador, donde puede validar sus anulaciones de estilo en su sitio. Luego puede compartir la URL con otros usuarios de Commerce autenticados para su revisión y comentarios.

## <a name="activate-a-css-override-file-on-your-live-site"></a>Activar un archivo de anulación de CSS en su sitio en activo

Después de haber visto y aprobado el archivo de anulación de CSS, puede activarlo en su sitio en activo.

> [!NOTE]
> Solo un archivo de anulación de CSS puede estar activo en su sitio a la vez. Si activa un nuevo archivo de anulación, el archivo de anulación anterior se desactiva. Por lo tanto, asegúrese de que todas las anulaciones requeridas estén presentes en una solo archivo de anulación de CSS.

Para activar un archivo de anulación de CSS, siga estos pasos.

1. En el panel de navegación a la izquierda, seleccione **Diseño**, y luego, en la pestaña **Anulación CSS**, en **Anulaciones CSS disponibles**, encuentre el archivo CSS que desea activar.
1. En el nombre del archivo CSS, seleccione **Activar**. El archivo de anulación se activa inmediatamente en su sitio activo.

## <a name="deactivate-a-css-override-file-on-your-live-site"></a>Desactivar un archivo de anulación de CSS en su sitio en activo

Para desactivar un archivo de anulación de CSS en su sitio, siga estos pasos.

1. En el panel de navegación a la izquierda, seleccione **Diseño**, y luego, en la pestaña **Anulación CSS**, en **Anulaciones CSS disponibles**, encuentre el archivo CSS que desea desactivar.
1. En el nombre del archivo CSS, seleccione **Desactivar**. El archivo de anulación se desactiva inmediatamente en su sitio activo.

> [!TIP]
> Para acceder a opciones adicionales para los archivos de anulación de CSS, seleccione los puntos suspensivos (**...**) al lado del nombre del archivo CSS. Las opciones **Descargar**, **Renombrar** y **Reemplazar** son útiles para realizar cambios rápidos en un archivo de anulación de CSS.

## <a name="additional-resources"></a>Recursos adicionales

[Agregar un logotipo](add-logo.md)

[Seleccionar un tema de sitio](select-site-theme.md)

[Agregar un icono de favoritos](add-favicon.md)

[Agregar un mensaje de bienvenida](add-welcome-message.md)

[Agregar un aviso de derechos de autor](add-copyright-notice.md)

[Agregar idiomas al sitio](add-languages-to-site.md)

[Agregar secuencia de comandos a páginas del sitio para admitir telemetría](add-telemetry.md)

---
title: Trabajar con preajustes de estilo
description: En este tema se describe cómo trabajar con estilos de sitio preestablecidos en el creador de sitios de Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1bd8f6e31afa300c5e7687a657ae2807995af8d3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006319"
---
# <a name="work-with-style-presets"></a>Trabajar con preajustes de estilo

[!include [banner](includes/banner.md)]

En este tema se describe cómo trabajar con estilos de sitio preestablecidos en el creador de sitios de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Un estilo preestablecido es un conjunto almacenado de todos los valores de estilo autorizables en el tema de un sitio. Se puede usar para cambiar inmediatamente el aspecto de un sitio desde el creador de sitios. Los preajustes de estilo permiten a los creadores de sitios web de Commerce cambiar, previsualizar y activar rápidamente un conjunto de valores de estilo en su sitio, sin tener que usar Hojas de estilo en cascada (CSS) ni desplegar temas. Los estilos de fuente, los estilos de botón y los colores del sitio son ejemplos típicos de variables de estilo que se pueden administrar a través de preajustes de estilo.

El conjunto de variables de estilo que está disponible en un sitio está determinado por el tema y la biblioteca de módulos que se implementa en el inquilino de un sitio. El kit de desarrollo de software en línea (SDK) de Dynamics 365 Commerce permite a los desarrolladores implementar tantas (o tan pocas) variables de estilo autorizables como requieran para un tema determinado. Al habilitar más variables de estilo, un desarrollador de temas puede poner las decisiones finales sobre los estilos de sitio en manos de los autores del creador de sitios. Por lo tanto, los no desarrolladores pueden actualizar y obtener una vista previa de los estilos del sitio mediante el conjunto de herramientas. La capacidad también es útil para cualquier escenario donde los cambios directos de los temas o CSS causarán gastos generales innecesarios.

Los temas en los que se habilitan las variables de estilo autorizables requieren un estilo predeterminado predeterminado. Opcionalmente, pueden incluir opciones preestablecidas adicionales como parte de un paquete de tema implementado. Por ejemplo, se puede implementar un tema que tenga un solo valor predeterminado predeterminado de estilo "luz moderna". Alternativamente, podría incluir opciones de preajuste de estilo adicionales además del preajuste predeterminado, como "oscuridad moderna", "luz vintage" u "oscuridad vintage". Estos ajustes preestablecidos de temas incorporados los crean desarrolladores y pueden usarse como puntos de partida para nuevos diseños de sitios.

En el creador de sitios, los autores pueden seleccionar entre los ajustes preestablecidos integrados de un tema, o pueden crear sus propios ajustes preestablecidos de estilo y personalizaciones utilizando las variables de estilo habilitadas. Un estilo preestablecido se puede previsualizar en el creador de sitios antes de que se active en el sitio en vivo. Después de revisar los cambios de estilo de un autor, el preajuste de estilo se puede establecer en "activo" para el sitio en vivo.

## <a name="preview-a-style-preset"></a>Vista previa de un estilo preestablecido

Para obtener una vista previa de un estilo preestablecido en su sitio en el generador de sitios, siga estos pasos.

1. En el panel de navegación izquierdo de su sitio, vaya a **Configuraciones del sitio \> Diseño**.
1. En la pestaña **Ajustes predeterminados de estilo** de la parte superior del editor de diseño, en la lista **Ajustes predeterminados disponibles**, seleccione un preajuste y luego seleccione **Ver** para ir al editor preestablecido.

    Si actualmente no hay ajustes prestablecidos en la lista **Ajustes prestablecidos**, consulte [Crear un estilo preestablecido personalizado](#create-a-custom-style-preset) para obtener información sobre cómo crear un estilo preestablecido personalizado.

    > [!NOTE]
    > Los preajustes que se incluyeron con el tema se indican mediante un distintivo **Incorporado**. Estos preajustes integrados son de solo lectura. Para copiar un preajuste incorporado como un nuevo preset personalizable, seleccione el botón de puntos suspensivos (**...**) para el preajuste y luego seleccione **Guardar como**.

1. En la barra de comandos, seleccione **Vista previa**.
1. Seleccione una URL de su sitio para usarla para obtener una vista previa del estilo preestablecido y luego seleccione **Aceptar**.
1. Seleccione la variante de URL específica del canal y del entorno local para obtener una vista previa seleccionando el nombre de la variante. Se abre una nueva ventana de vista previa del navegador, donde el estilo predeterminado seleccionado se aplica a la página especificada.

> [!NOTE]
> La URL de vista previa es persistente y autenticada. Por lo tanto, puede copiarla, pegarla y enviarla a otros compañeros de trabajo autenticados para su revisión antes de configurarla como "activa" en su sitio en vivo. La URL de vista previa también es útil para comprobar estilos en diferentes dispositivos, en diferentes navegadores y en diferentes pantallas.

> [!TIP]
> Mientras edita un estilo preestablecido, puede resultarle útil dejar abierta la ventana del navegador de vista previa para que se abra en una ventana separada del navegador, de modo que pueda validar rápidamente sus cambios. Después de guardar los cambios en un ajuste preestablecido, actualice la ventana del navegador de vista previa abierta para validar la experiencia del usuario.

## <a name="create-a-custom-style-preset"></a>Crear un estilo preestablecido personalizado

Para crear un ajuste de estilo personalizado en el generador de sitios, siga estos pasos.

1. En el panel de navegación izquierdo de su sitio, vaya a **Configuraciones del sitio \> Diseño**.
1. En la pestaña **Preajustres de estilo** de la parte superior del editor de diseño, en la barra de comandos, seleccione **Nuevo preajuste**.
1. Introduzca un nombre y una descripción para el nuevo preajuste y luego seleccione **Guardar**. Se crea un nuevo preajuste personalizable que utiliza los valores predeterminados del tema como punto de partida.

> [!NOTE]
> También puede crear un nuevo preajuste de estilo personalizado a partir de cualquier preajuste existente seleccionando el botón de puntos suspensivos (**...**) para ese ajuste predeterminado luego seleccionando **Guardar como**. Alternativamente, seleccione **Guardar como** en la barra de comandos del editor de preajustes.

## <a name="modify-global-and-module-type-style-values"></a>Modificar valores de estilo de tipo global y de módulo

Algunas de las variables de estilo de un tema se comparten entre varios tipos de módulos. Estas variables de estilo se denominan variables de estilo *global*. Como ejemplos pueden citarse colores primarios del sitio, estilos de fuente predeterminados y estilos de botones. Al establecer variables globales, puede cambiar el aspecto en muchos tipos de módulos diferentes.

Algunos valores de estilo pueden ser únicos para un tipo de módulo, o pueden tener que anular opcionalmente un valor global predeterminado. Si el tema de un sitio ha implementado variables de estilo de tipo de módulo, los autores del creador de sitios pueden personalizar el estilo de un tipo de módulo independientemente de la configuración global. Las variables de tipo módulo pueden aumentar o anular las variables de estilo global en un tema.

> [!NOTE]
> La jerarquía de valores de estilo en un sitio se comporta de la siguiente manera. Los valores de estilo que aparecen más a la derecha anulan los valores de estilo a la izquierda de ellos.
>
> Anulación de \< Valores de estilo global \< Valores de estilo de tipo de módulo \< CSS

Para cambiar los valores globales o de tipo de módulo de un preajuste de estilo en el generador de sitios, siga estos pasos.

1. En el panel de navegación izquierdo de su sitio, vaya a **Configuraciones del sitio \> Diseño**.
1. En le pestaña **Preajustes de estilo** de la parte superior del editor de diseño, seleccione **Ver** para que cualquier estilo preestablecido vaya al editor de preajustes.
1. Seleccione **Vista previa** y luego siga los pasos de selección de URL para abrir una vista previa de la ventana completa del navegador para su preajuste. Deje abierta esta ventana del navegador de vista previa.
1. En el editor preestablecido, seleccione **Editar** en la esquina superior derecha.
1. Use los controles de variables de estilo en el editor para cambiar algunos valores de estilo globales.
1. En la parte superior del editor, en la pestaña **Módulos** a la derecha de la pestaña **Global**, seleccione un tipo de módulo que debe tener estilo.
1. Use los controles de estilo para cambiar algunos valores para el tipo de módulo.
1. Cuando esté listo para previsualizar sus cambios, seleccione **Guardar** en la barra de comandos.
1. Vuelva a la ventana abierta del navegador de vista previa y actualícela. La vista previa de la ventana completa del navegador es útil para verificar los cambios de estilo en diferentes puntos de vista, en diferentes navegadores y en diferentes plataformas de dispositivos.
1. Cuando todos los cambios se hayan completado y validado, seleccione **Finalizar edición** en la esquina superior derecha del editor.

> [!NOTE]
> Si está editando el estilo preestablecido que está actualmente activo en su sitio, verá un distintivo azul **Activo** en el editor. Ese distintivo indica que el preajuste está actualmente activo en su sitio web. Si cambia el preajuste activo, seleccione **Publicar** para enviar esos cambios a su sitio en vivo.

## <a name="make-a-new-style-preset-active-on-your-live-site"></a>Active un nuevo estilo preestablecido en su sitio en vivo

Para establecer un estilo preestablecido como el nuevo valor preestablecido activo en su sitio, siga estos pasos.

- Seleccione **Establecer como botón activo** en uno de estos lugares:

    - La barra de comandos del editor de estilos preestablecidos
    - El menú de puntos suspensivos (**...**) para cualquier preajuste disponible en la vista principal de la pestaña **Preajustes de estilo** en **Configuraciones del sitio \> Diseño**

Los valores de estilo del preajuste se activan en su sitio web cara al público.

## <a name="additional-resources"></a>Recursos adicionales

[Agregar un logotipo](add-logo.md)

[Seleccionar un tema de sitio](select-site-theme.md)

[Trabajar con archivos de invalidaciones CSS](css-override-files.md)

[Agregar un icono de favoritos](add-favicon.md)

[Agregar un mensaje de bienvenida](add-welcome-message.md)

[Agregar un aviso de derechos de autor](add-copyright-notice.md)

[Agregar idiomas al sitio](add-languages-to-site.md)

[Agregar secuencia de comandos a páginas del sitio para admitir telemetría](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
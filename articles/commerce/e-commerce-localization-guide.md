---
title: Dynamics 365 Commerce Guía de localización de comercio electrónico
description: En este tema se describe cómo localizar un sitio de comercio electrónico de Microsoft Dynamics 365 Commerce en idiomas adicionales y configurar el sitio para soportar múltiples canales.
author: bicyclingfool
ms.date: 04/29/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1e9d91036ceeb9161dc8ee903532b2cf3ca435e2
ms.sourcegitcommit: 26c726bd0b00935e3d2c31fdc5a3b2ae03a8a2b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661532"
---
# <a name="dynamics-365-commerce-e-commerce-localization-guide"></a>Dynamics 365 Commerce Guía de localización de comercio electrónico

[!include [banner](includes/banner.md)]

En este tema se describe cómo localizar un sitio de comercio electrónico de Microsoft Dynamics 365 Commerce en idiomas adicionales y configurar el sitio para soportar múltiples canales, y también cubre los conceptos y la terminología relacionada con el proceso.

Las capacidades de comercio electrónico en Dynamics 365 Commerce se han diseñado para permitir experiencias en línea que se pueden adaptar a países e idiomas específicos, pero al mismo tiempo permiten la máxima reutilización de plantillas, páginas, contenido y medios. También puede crear un sitio básico y luego expandirse a nuevos mercados agregando soporte para países e idiomas adicionales con el tiempo.

## <a name="definitions"></a>Definiciones

**Configuración regional, identificador de configuración regional** : una configuración regional (también conocida como identificador de configuración regional) define un idioma asociado con un país o una región. Por ejemplo, el identificador de configuración regional "fr-ca" está asociado con el francés canadiense.

**Idioma base** : el idioma en el que desarrolla el contenido de su sitio antes de exportarlo para su localización.

**Canal, tienda en línea** : un canal (también conocido como tienda en línea) define los métodos de pago, grupos de precios, jerarquías de productos, surtidos y productos para una tienda de comercio electrónico en línea.

## <a name="concepts"></a>Conceptos

### <a name="url-driven-experience"></a>Experiencia basada en URL

Dynamics 365 Commerce Los sitios de comercio electrónico brindan experiencias únicas comercializadas y localizadas para los clientes a través de canales e identificadores de configuración regional. Los canales definen los productos, las categorías, las monedas y los métodos de pago exclusivos para un mercado, y los identificadores de configuración regional determinan el idioma del contenido que ven los clientes. Un sitio de comercio electrónico utiliza direcciones URL para diferenciar entre experiencias comercializadas y localizadas. Las direcciones URL del sitio para estas experiencias únicas de canal y configuración regional se definen para un sitio en la página l **Configuración del sitio \> Canales** en el generador de sitios de Dynamics 365 Commerce.

En el generador de sitios, una URL es una combinación de un dominio y una ruta que define el punto de entrada para una combinación única de un canal y una configuración regional. En el siguiente ejemplo, una tienda en línea ficticia llamada Fabrikam Inc. define cuatro combinaciones únicas de un canal y una configuración regional, y asigna cada combinación a una URL única que ofrece contenido a los clientes.

| Dominio                     |  Ruta de acceso      | Canal       |   Configuración regional     |
|------------------------|--------|--------------------------------|--------|
| `https://fabrikam.com` | /      | Tienda en línea ampliada de Fabrikam | es  |
| `https://fabrikam.com` | /es    | Tienda en línea ampliada de Fabrikam | es     |
| `https://fabrikam.ca`  | /      | Tienda en línea Contoso    | fr-ca  |
| `https://fabrikam.ca`  | /en-ca | Tienda en línea Contoso    | en-ca  |

#### <a name="domain"></a>Dominio

Los dominios se establecen cuando configura su sitio de comercio electrónico en Lifecycle Services (LCS) de Microsoft Dynamics. Después de aprovisionar su entorno de comercio electrónico, puede agregar más dominios abriendo una solicitud de servicio. Para obtener más información sobre cómo configurar los dominios para su sitio de comercio electrónico, consulte [Dominios en Dynamics 365 Commerce](domains-commerce.md).

#### <a name="path"></a>Ruta de acceso

- Una ruta es una cadena arbitraria que, en combinación con el dominio, se asigna a una combinación única de un canal y una configuración regional. En el ejemplo anterior, la cadena que se usa como ruta coincide con el identificador de configuración regional al que se asigna la ruta de acceso. Sin embargo, puede utilizar un enfoque diferente.
- Una combinación de un canal y una configuración regional se puede asignar a un dominio y una ruta vacía ("/"). En el ejemplo anterior, los clientes que visitan `https://fabrikam.ca/` obtendrán los productos y surtidos para el mercado canadiense en francés canadiense.
- El generador de sitios de comercio le impide crear combinaciones duplicadas de un dominio y una ruta de acceso. Sin embargo, puede asignar combinaciones duplicadas de un canal y una configuración regional a una combinación diferente de un dominio y una ruta de acceso.

#### <a name="channel"></a>Canal

- Canales (también conocidos como tiendas en línea) definen los métodos de pago, grupos de precios, jerarquías de productos, surtidos y productos para una tienda de comercio electrónico en línea.
- Los canales se definen, configuran y publican en la sede de Dynamics 365 Commerce.
- El generador de sitios puede detectar las tiendas en línea que se configuraron en la sede de Commerce y están disponibles para asignarse a un sitio.

Para obtener más información acerca de los alcances, consulte [Información general de canales](channels-overview.md). Para obtener más información sobre cómo configurar un canal en línea, consulte [Configurar un canal en línea](channel-setup-online.md).

#### <a name="locale"></a>Configuración regional

- La configuración regional es el identificador real que se utiliza cuando entrega archivos de formato de archivo de intercambio de localización XML (XLIFF) para su localización. Las configuraciones regionales se definen y publican para cada canal en la sede de Commerce. Para obtener información sobre cómo configurar idiomas y canales en el generador de sitios, consulte la siguiente sección.
- La misma configuración regional se puede asignar a varios canales. De esta forma, se puede ofrecer un idioma común en múltiples mercados.

## <a name="configure-languages-and-channels-for-your-e-commerce-site"></a>Configure idiomas y canales para su sitio de comercio electrónico

En general, todos los sitios de comercio electrónico de Dynamics 365 Commerce están configurados para usar un solo canal en línea y un solo idioma, independientemente de si comienza con el sitio de demostración de Fabrikam o si crea un nuevo sitio desde cero.

En esta configuración, los clientes y socios suelen desarrollar todos los activos que se utilizarán en todos los países e idiomas. Estos activos incluyen plantillas, páginas, fragmentos, contenidos y medios. Todo el contenido del sitio se desarrolla en el primer idioma que seleccionó para su sitio o, si está utilizando el sitio de demostración de Fabrikam, el contenido del sitio se desarrollará en inglés.

![Sitio de comercio electrónico Dynamics 365 Commerce listo para usar](media/loc-guide-1.png)

> [!NOTE]
> Puede configurar el sitio de demostración de Fabrikam para un idioma adicional para que el desarrollo de contenido se pueda realizar en ese idioma. Para obtener información sobre cómo agregar un nuevo idioma a un sitio y un canal, consulte la sección [Configurar un idioma adicional para su sitio](#configure-an-additional-language-for-your-site) más adelante en este tema.

Sin embargo, el sistema de administración de contenido (CMS) y el modelo de página para sitios de comercio electrónico Dynamics 365 Commerce se han diseñado para permitir la expansión a nuevos mercados y lugares. Por lo tanto, a través de un solo sitio de comercio electrónico, puede administrar los activos de una tienda en línea que abarca múltiples mercados e idiomas.

![Sitio de comercio electrónico de Dynamics 365 Commerce que abarca múltiples mercados e idiomas](media/loc-guide-2.png)

### <a name="configure-an-additional-language-for-your-site"></a>Configurar un idioma adicional para su sitio

El proceso de configuración de un nuevo idioma para un sitio de comercio electrónico consta de tres pasos.

#### <a name="step-1-add-the-language-to-your-channel-online-store-in-commerce-headquarters"></a>Paso 1: Agregue el idioma a su canal (tienda en línea) en la sede de Commerce

1. En la sede de Commerce, vaya al canal al que desea agregar el nuevo idioma. Para encontrar la lista de canales que ha configurado en la sede de Commerce, vaya a **Retail y Commerce \> Canales \> Tiendas en línea**.
1. Abra la tienda en línea que está asignada a su sitio seleccionando su valor de **ID de canal minorista**. Puede verificar la tienda en línea que está asignada a su sitio abriendo la página de configuración del sitio **Canales** en el generador de sitios de Commerce y mirando el nombre de la tienda en línea en la columna **Canales**. 
1. En la ficha desplegable **Idiomas**, seleccione **Agregar**. En el campo **Idioma**, seleccione el código de configuración regional del nuevo idioma. A continuación, seleccione **Guardar**.
1. Vaya a **Retail y Commerce \> Retail y Commerce IT \> Programación de distribución** y ejecute el trabajo **Configuración de canal 1070**. Cuando el trabajo haya terminado de ejecutarse, puede continuar con el paso 2 y agregar el idioma a un canal para su sitio en el generador de sitios.

![Ficha desplegable Idiomas de una tienda online en la sede de Commerce](media/loc-guide-3.png)

#### <a name="step-2-add-the-language-to-a-channel-in-site-builder"></a>Paso 2: Agregue el idioma a un canal en el generador de sitios

Para agregar un idioma a un canal en el generador de sitios, siga estos pasos.

1. En el generador de sitios de Commerce, abra su sitio y luego abra la página **Canales** en la configuración del sitio.
1. Seleccione el nombre del canal al que quiere agregar el idioma.
1. En el panel derecho, seleccione **Agregar una configuración local**.
1. En el cuadro de diálogo **Agregar un lugar**, en **Agregar una configuración regional** seleccione la configuración regional para el idioma que agregó previamente al canal en la sede de Commerce.
1. Seleccione el dominio y la ruta de acceso que los clientes solicitarán para ver su sitio en este canal e idioma.
1. Si desea que el idioma sea el idioma predeterminado para ver, crear y actualizar fragmentos y páginas del generador de sitios, seleccione el cuadro de diálogo **Usar como idioma predeterminado del canal de autorización predeterminado**. 
    > [!NOTE]
    > Esta configuración afecta solo al generador de sitios. No influye en la experiencia del sitio publicado para sus clientes.
1. Seleccione **Aceptar**.
1. Seleccione **Guardar y publicar**.

#### <a name="step-3-localize-your-site-content"></a>Paso 3: Localice el contenido de su sitio

Cuando regrese a la vista **Paginas** en el generador de sitios de Commerce, el nuevo idioma estará disponible en el canal y el selector de configuración regional en la parte superior derecha. Ahora puede crear versiones localizadas de páginas en su idioma base.

El proceso para localizar el contenido de sus páginas y fragmentos está cubierto en la sección [Localizar el contenido del sitio de comercio electrónico](#localize-e-commerce-site-content) más adelante en este tema.

### <a name="configure-a-new-channel-for-your-site"></a>Configurar un nuevo canal para su sitio

Los sitios de comercio electrónico de Dynamics 365 Commerce pueden brindar experiencias que se definen a través de múltiples canales en línea que se configuran en la sede de Commerce. Un sitio utiliza múltiples canales para mostrar a los clientes una configuración única de métodos de pago, grupos de precios, jerarquías de productos, surtidos y un conjunto de productos. Por lo general, se usa un canal para configurar estas dimensiones para que se ajusten a los requisitos y preferencias de la experiencia asociada con países individuales. Sin embargo, este enfoque es una decisión comercial que toma el cliente. No es un requisito.

Los requisitos previos y las tareas asociadas con la configuración de un canal (tienda en línea) están fuera del ámbito de este documento. Para obtener más información sobre cómo configurar un canal en línea en la sede de Commerce, consulte [Fundamentos de la configuración de canales](channels-overview.md#channel-setup-basics). Para obtener información sobre los pasos y requisitos específicos de los canales en línea, consulte [Configurar un canal en línea](channel-setup-online.md).

Para agregar un canal a su sitio en el generador de sitios, siga estos pasos.

1. En el generador de sitios de Commerce, vaya a **Configuración del sitio \> Canales**. 
1. Seleccione **Agregar un canal**.
1. En el cuadro de diálogo **Agregar un canal** en **Canal** seleccione el canal que desea agregar. 
    > [!NOTE]
    > Solo puede agregar canales que aún no se hayan agregado a su sitio.
1. Seleccione la configuración regional predeterminada para el canal. Si agrega nuevos idiomas al canal, puede cambiar el idioma predeterminado a uno de ellos.
1. Especifique el dominio y la ruta de acceso que constituirán la URL que ofrece contenido y experiencias para esta combinación de un canal y un idioma.
1. Seleccione **Aceptar**.
1. Seleccione **Guardar y publicar**.

## <a name="localize-e-commerce-site-content"></a>Localizar el contenido del sitio de comercio electrónico

### <a name="xliff-basics"></a>Conceptos básicos de XLIFF

XLIFF es un formato de archivo estándar de la industria para pasar contenido localizable entre herramientas de administración de contenido. El generador de sitios de comercio utiliza el formato de archivo XLIFF para exportar contenido de metadatos de imágenes, fragmentos y páginas para que pueda localizarse y reimportarse.

Los clientes de Microsoft Dynamics suelen trabajar con proveedores de localización de terceros, como [Translated.com](https://translated.com/welcome) para traducir sus archivos XLIFF a los idiomas que necesitan.

### <a name="localize-assets-in-site-builder"></a>Localizar activos en el generador de sitios

Los siguientes activos del sitio de comercio electrónico se pueden localizar en el generador del sitio:

- Páginas
- Fragmentos
- Activos de medios
- Módulos

Todas las páginas, fragmentos y activos multimedia nuevos se crean en el contexto del canal y el idioma que están seleccionados actualmente en el selector de canal y configuración regional. Este idioma suele ser su "idioma base", siempre que no haya configurado idiomas o canales adicionales. En los sitios donde se configuran varios canales e idiomas, el "idioma base" se define por el canal y la configuración regional que ha establecido como predeterminados en la página **Canales** en la configuración del sitio.

Los pasos para localizar contenido para páginas, fragmentos y recursos multimedia son similares. Las excepciones y diferencias se señalarán en las secciones siguientes. Sin embargo, los pasos para localizar el contenido del módulo difieren. Para obtener más información, consulte la sección [Localizar módulos](#localize-modules) en este tema.

#### <a name="step-1-export-an-xliff-file"></a>Paso 1: Exportar un archivo XLIFF

Para exportar un archivo XLIFF para una página, fragmento o imagen en el constructor de sitios, siga estos pasos.

1. Abra el activo para el que desea exportar el contenido del idioma base, para que pueda localizarse.
1. En la barra de comandos, seleccione **Localización \> Exportar XLIFF**.
    > [!NOTE]
    > La opción **Localización** es visible solo cuando el activo está en un estado **Editar**.

Un archivo XLIFF llamado **\<assetname\> .xlf** se descargará en la carpeta de descargas de su navegador. Este archivo XLIFF es específico del activo que está localizando. Exportará un archivo XLIFF para cada recurso que desee localizar.

#### <a name="step-2-localize-the-xliff-file"></a>Paso 2: localizar el archivo XLIFF

En la mayoría de los casos, trabajará con un proveedor de localización para traducir sus archivos XLIFF. Sin embargo, si está localizando activos internamente, o si solo desea probar el proceso de localización, debe realizar los siguientes cambios en un archivo XLIFF:

- Agregue un atributo de idioma de destino al elemento /xliff/file y establezca el valor en el identificador de configuración regional del idioma al que está localizando. 
    > [!NOTE]
    > Este identificador de configuración regional debe coincidir con el identificador de configuración regional de la página **Canales** en la configuración del sitio.
- Para cada //elemento de origen, agregue un hermano del elemento de destino donde el valor del texto sea la versión localizada del contenido de ese elemento de origen.

Para obtener información sobre el esquema que rige los archivos XLIFF, consulte la [Especificación XLIFF 1.2](http://docs.oasis-open.org/xliff/xliff-core/xliff-core.html).

> [!NOTE]
> Para localizar un activo en varios idiomas, debe crear un archivo XLIFF localizado para cada uno de esos idiomas.

#### <a name="step-3-import-the-localized-xliff-file"></a>Paso 3: Importar el archivo XLIFF localizado

Para importar un archivo XLIFF para un activo, siga estos pasos.

1. En el generador de sitios de Commerce, abra el activo para el que desea importar un archivo XLIFF.
1. En el selector de canal y configuración regional en la parte superior derecha, seleccione el canal y el idioma para el que está importando contenido localizado.
1. En la barra de comandos, seleccione **Localización \> Import XLIFF**. A continuación, busque y seleccione el archivo XLIFF localizado para el recurso y el idioma seleccionados.

Una vez que el archivo XLIFF se importa correctamente, se crea una "variante" de la página, el fragmento o el activo. A partir de ese momento, todos los cambios que se realicen en la variante localizada afectarán solo a esa variante. No afectarán al activo base del que se derivó la variante. Del mismo modo, los cambios en el activo base no afectarán la variante de ese activo. 

Sin embargo, en el caso de las páginas, puede realizar cambios en las variantes modificando la plantilla o el diseño al que están vinculadas esas páginas. Del mismo modo, los cambios en un fragmento afectarán a todas las páginas que dependan de esa variante.

### <a name="images"></a>Imágenes

Las imágenes se pueden representar en una variante de página o módulo solo si los metadatos de contenido asociados con esas imágenes están localizados. Actualmente, los siguientes metadatos en un recurso multimedia son localizables:

- Texto alternativo
- Description
- Título

Actualmente, no puede localizar el binario de un recurso digital, como una imagen o un video. El equipo de producto de Dynamics 365 Commerce está trabajando actualmente en esta capacidad.

### <a name="localize-modules"></a>Localizar módulos

Las cadenas que se representan como parte del propio módulo (por ejemplo, "Anterior" y "Siguiente" en un módulo de carrusel) se localizan por separado del contenido del módulo. Para obtener instrucciones, consulte [Localizar un módulo](e-commerce-extensibility/localize-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Glosario del modelo de página](page-elements-overview.md)

[Uso compartido entre canales](cross-channel-sharing.md)

[Localizar un módulo](e-commerce-extensibility/localize-module.md)

[Archivo de definición de módulo](e-commerce-extensibility/module-definition-file.md)

[Buscar recursos con extensión Commerce y archivos de etiquetas](dev-itpro/extension-resource-localization.md)

[Globalizar módulos mediante la clase CultureInfoFormatter](e-commerce-extensibility/globalize-modules.md)

[Configuración de la aplicación: Temas](e-commerce-extensibility/app-settings.md#themes-section)

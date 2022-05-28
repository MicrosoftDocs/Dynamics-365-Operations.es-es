---
title: Asignar canales a sitios de comercio electrónico
description: Este tema describe algunos de los escenarios de asignación de canales más comunes en Microsoft Dynamics 365 Commerce que se pueden extrapolar para la mayoría de los demás requisitos empresariales.
author: samjarawan
ms.date: 05/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8ce272d63b4a37f99661333a02434708205ea19a
ms.sourcegitcommit: e4cc43b06ef3f0f562849e2c960025cb244d6017
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2022
ms.locfileid: "8743581"
---
# <a name="map-channels-to-e-commerce-sites"></a>Asignar canales a sitios de comercio electrónico

Este tema describe algunos de los escenarios de asignación de canales más comunes en Microsoft Dynamics 365 Commerce que se pueden extrapolar para la mayoría de los demás requisitos empresariales.

Dynamics 365 Commerce admite muchos escenarios empresariales para los [canales en línea](#channels) de asignación que tienen configurado un conjunto de productos, precios y descuentos para las experiencias del [sitio de comercio electrónico](#e-commerce-sites) para los clientes.

Este tema abarca los siguientes escenarios:

- **Un canal de un solo idioma que tiene una experiencia única de sitio de comercio electrónico.** Por ejemplo, este escenario podría implicar un sitio de una sola marca configurado para el mercado inglés de EE. UU.
- **Un canal de varios idiomas que tiene una experiencia única de sitio localizado.** Por ejemplo, este escenario podría implicar un sitio de una sola marca configurado para Canadá con la compatibilidad de idioma inglés y francés. En este escenario, los usuarios que seleccionan diferentes idiomas tienen la misma experiencia en el sitio, pero está localizada en el idioma seleccionado de cada usuario.
- **Un canal de varios idiomas que tiene una experiencia de sitio diferente por idioma.** Por ejemplo, este escenario podría implicar un sitio de una sola marca configurado para Canadá con la compatibilidad de idioma inglés y francés. En este escenario, hay experiencias de sitio únicas para cada idioma.
- **Varios canales (en un solo idioma y/o en varios idiomas) que tienen una única experiencia de sitio localizada.** Por ejemplo, este escenario podría implicar un sitio de una sola marca configurado para Australia y Nueva Zelanda. En este escenario, ambos países comparten la misma experiencia de sitio en inglés, pero cada país está configurado con diferentes productos, moneda, precios, descuentos y modos de envío.
- **Varios canales (en un solo idioma y/o en varios idiomas) que tienen una experiencia de sitio diferente por canal.** Por ejemplo, este escenario podría implicar un sitio de una sola marca configurado para Australia, Canadá y Alemania en varios idiomas. En este escenario, cada país tiene una experiencia de sitio única que está configurada con diferentes productos, moneda, precios, descuentos y modos de envío.

## <a name="channels"></a>Canales

Un canal (también conocido como tienda en línea o canal en línea) representa un escaparate de comercio electrónico en línea que se utiliza para asignar productos, precios, descuentos, idiomas, métodos de pago, modos de entrega, centros de proceso de entrega y otros aspectos de la experiencia en línea que estarán disponibles para sus clientes de comercio electrónico. Los canales se crean y administran en Commerce headquarters y se asignan a una única [entidad jurídica](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json#legal-entities). La entidad jurídica generalmente se basa en un solo país que requiere informes de impuestos para el canal y se puede configurar con una sola moneda.

Para obtener más información acerca de los alcances, consulte [Información general de canales](channels-overview.md). Para obtener más información sobre cómo crear un canal en línea, consulte [Configurar un canal en línea](channel-setup-online.md).

La siguiente ilustración de ejemplo de Commerce headquarters muestra los canales en línea predeterminados que se implementan con Dynamics 365 Commerce si se selecciona la opción de datos de demostración.

![Canales de datos de demostración predeterminados en Commerce headquarters.](media/channel-mapping-1.png)

## <a name="e-commerce-sites"></a>Sitios de comercio electrónico

Un sitio de comercio electrónico contiene un conjunto de páginas de sitio que los clientes utilizan para navegar y comprar. Los sitios de comercio electrónico se administran en el generador de sitios de Commerce.

Para obtener más información sobre cómo crear y administrar sitios en el creador de sitios, consulte [Información general del sitio de comercio electrónico](online-store-overview.md).

## <a name="common-channel-mapping-scenarios"></a>Escenarios comunes de asignación de canales

Dynamics 365 Commerce admite una amplia gama de escenarios de asignación de canales. Los escenarios de asignación de canales que siguen son solo un subconjunto de todos los escenarios posibles de asignación de canales. Están pensados como una guía para ayudarlo a planificar cualquier escenario empresarial único que tenga. La tienda ficticia de artículos deportivos Adventure Works que se incluye con los datos de demostración de Dynamics 365 Commerce se utilizan como ejemplo para cada escenario.

### <a name="single-language-channel-that-has-a-single-e-commerce-site-experience"></a>Canal de un solo idioma que tiene una experiencia única de sitio de comercio electrónico

En el escenario más básico, un solo canal tiene un único idioma para vender en un solo mercado. Un ejemplo de este escenario es una tienda en línea de Adventure Works que está configurada solo para el mercado inglés de EE. UU.

La ilustración de ejemplo siguiente muestra una configuración de canal en Commerce headquarters. En esta configuración, el canal en línea solo admite un único idioma (**en-us**), una única moneda (**USD**), y una única entidad empresarial (**urst**) que se utiliza para la notificación de impuestos.

![Valores de entidad jurídica, moneda e idioma para la tienda en línea Adventure Works resaltados en Commerce headquarters.](media/channel-mapping-3.png)

El único canal en línea se puede asignar a un único sitio de comercio electrónico en el generador de sitios. Para obtener información acerca de cómo crear un nuevo sitio y asignarlo a un canal, consulte la sección [Asignar un canal a un sitio en el generador de sitios](#map-a-channel-to-a-site-in-site-builder) de este tema.

### <a name="multi-language-channel-that-has-a-single-localized-site-experience"></a>Canal de varios idiomas que tiene una experiencia única de sitio localizado

En este escenario, un solo canal admite más de un idioma. Por lo tanto, los nombres, las descripciones y los atributos de los productos se pueden localizar en Commerce headquarters. Para proporcionar una experiencia de sitio localizada completa, el contenido de marketing en el sitio también se puede localizar en el generador de sitios de Commerce.

La limitación de este escenario es que se puede configurar un solo canal con una sola moneda, una entidad jurídica y un conjunto de productos y precios. Esta configuración funciona mejor para países que tienen una sola moneda y varios idiomas (por ejemplo, Canadá, que tiene los idiomas inglés y francés), una sola entidad jurídica y un solo conjunto de productos y precios.

Cada idioma en un canal se puede configurar con su propio nombre de dominio. Por ejemplo, el dominio `www.adventure-works.ca` se puede configurar para la versión en inglés de Canadá, y el dominio `www.adventure-works-fr.ca` se puede configurar para la versión en francés de Canadá. Alternativamente, se pueden configurar diferentes idiomas de un canal en un solo dominio y luego se puede usar una ruta diferente para cada idioma. Por ejemplo, el dominio `www.adventure-works.ca` se puede configurar para la versión en inglés de Canadá y, a continuación, la ruta de acceso a `www.adventure-works.ca/fr` se puede configurar para la versión en francés de Canadá. [Detección geográfica](geo-detection-redirection.md) también se puede habilitar para redirigir automáticamente a un usuario al sitio correcto, según la ubicación del usuario.

Para obtener información sobre cómo permitir que los clientes pasen manualmente de un idioma a otro, consulte la sección [Agregar y configurar el módulo selector de sitios](#add-and-configure-the-site-picker-module) de este tema. Para obtener información acerca de cómo personalizar páginas y fragmentos localizados, consulte la sección [Administrar el contenido del sitio que tiene múltiples canales e idiomas](#manage-site-content-that-has-multiple-channels-and-languages).

### <a name="multi-language-channel-that-has-a-different-site-experience-per-language"></a>Canal de varios idiomas que tiene una experiencia de sitio diferente por idioma

Es posible que prefiera un escenario en el que un solo canal admita más de un idioma, pero se represente una experiencia de sitio completamente diferente para cada idioma. El método recomendado para implementar este escenario es usar [variantes de página](#implement-page-variants-for-each-language) en un solo sitio.

Otro método es crear un nuevo sitio de comercio electrónico para cada idioma en el generador de sitios y luego asignar cada sitio a un solo canal e idioma en línea. El resultado será un único canal en línea que se asigna a varios sitios de comercio electrónico, uno para cada idioma. Este método de sitios múltiples requiere recursos de administración adicionales, porque habrá más de un sitio para administrar en el generador de sitios.

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-single-localized-site-experience"></a>Varios canales (en un solo idioma y/o en varios idiomas) que tienen una única experiencia de sitio localizada.

Un sitio de marca puede requerir varios canales en línea por región para admitir una moneda diferente, un conjunto de productos y un conjunto de precios para cada canal en un solo sitio. Por ejemplo, el sitio de Adventure Works puede tener un canal en línea para el mercado canadiense que tiene varios idiomas, un canal para el mercado estadounidense que tiene un idioma y un canal para el mercado alemán que tiene un idioma. En este escenario, cada canal en línea se configurará para una entidad jurídica específica de la región y puede tener el mismo conjunto de productos que tienen otros canales, un subconjunto de esos productos o un conjunto diferente de productos. Cada canal también tendrá sus propios precios en la moneda regional, impuestos, descuentos y modos de envío.

En este escenario, cada mercado se puede configurar con sus propios nombres de dominio. Por ejemplo, el dominio `www.adventure-works.com` se puede configurar para el mercado de EE. UU., y el dominio `www.adventure-works.de` se puede configurar para el mercado alemán. Como alternativa, cada mercado se puede configurar para usar una ruta diferente. Por ejemplo, el dominio `www.adventure-works.com` se puede configurar para el mercado de EE. UU., y la ruta de acceso de `www.adventure-works.com/de` se puede configurar para el mercado alemán. [Detección geográfica](geo-detection-redirection.md) también se puede habilitar para redirigir automáticamente a los usuarios al sitio correcto, según su ubicación.

También es posible que desee que su sitio proporcione una lista desplegable que permita a los usuarios cambiar manualmente a un mercado específico. Para obtener más información, consulte la sección [Agregar y configurar el módulo selector de sitios](#add-and-configure-the-site-picker-module), de este tema.

Para obtener información sobre cómo configurar varios canales en un solo sitio, consulte la sección [Configurar varios canales en un sitio de comercio electrónico](#configure-multiple-channels-on-an-e-commerce-site).

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-different-site-experience-per-channel"></a>Varios canales (en un solo idioma y/o en varios idiomas) que tienen una experiencia de sitio diferente por canal

Es posible que desee tener varios canales para una sola marca en diferentes regiones y que cada región tenga una experiencia de sitio diferente. Hay dos métodos para implementar este escenario:

- Use [variantes de página](#implement-page-variants-for-each-language).
- Configure un sitio diferente para cada canal en línea en el generador de sitios y luego asigne cada sitio a un canal en línea e idioma diferentes. Este método requiere recursos de administración adicionales, porque habrá más de un sitio para administrar en el generador de sitios.

## <a name="cross-channel-sharing"></a>Uso compartido entre canales

El uso compartido entre canales es útil cuando varios canales en un solo sitio pueden compartir contenido. Por ejemplo, un minorista que tiene varias marcas y escaparates que están agrupados en un solo sitio puede compartir contenido entre algunos o todos los escaparates. El contenido compartido puede incluir páginas de términos y condiciones, condiciones de pago, métodos de envío y preguntas frecuentes (FAQ). Para más información, consulte [Habilitar y usar el uso compartido entre canales](cross-channel-sharing.md).

## <a name="map-a-channel-to-a-site-in-site-builder"></a>Asignar un canal a un sitio en el generador de sitios

Existen múltiples métodos para crear y configurar sitios para usar diferentes canales en línea.

### <a name="create-a-new-site"></a>Crear un nuevo sitio

Puede crear un sitio completamente nuevo en el generador de sitios yendo a la página de lista **Sitios** y seleccionando **Nuevo sitio**. A continuación, en el cuadro de diálogo **Nuevo sitio** que aparece, puede seleccionar el canal en línea predeterminado y el idioma para el sitio, como se muestra en la siguiente ilustración de ejemplo.

![Creación de un nuevo canal en el generador de sitios.](media/channel-mapping-4.png)

El sitio que cree de esta manera estará vacío y no incluirá ninguna página de sitio (por ejemplo, una página de inicio, páginas de categorías y páginas de productos).

Para más información, consulte [Crear un sitio de comercio electrónico](create-ecommerce-site.md).

### <a name="create-a-new-site-by-using-the-site-copy-operation"></a>Crear un nuevo sitio mediante la operación de copia del sitio

En lugar de crear un sitio nuevo y vacío como se describe en la sección anterior, una mejor práctica es comenzar con una copia de uno de los sitios de inicio que se proporcionan en la biblioteca del módulo Commerce, como el sitio de Fabrikam o Adventure Works.

Para copiar un sitio existente, vaya a la página de lista **Sitios** en el generador de sitios y seleccione **Copiar sitio**. A continuación, en el cuadro de diálogo **Copiar sitio** que aparece, puede seleccionar el sitio de origen y especificar el nombre del sitio de destino.

En este momento, aún no puede seleccionar el canal en línea ni el idioma predeterminados para el sitio. Sin embargo, puede configurar esas propiedades después de que se haya completado la operación de copia del sitio. Cuando seleccione el sitio por primera vez en la página de lista **Sitios** en el generador de sitios, aparece el cuadro de diálogo **Configurar el sitio**, donde puede seleccionar el canal y el idioma predeterminados.

Para obtener más información acerca de la operación de copia del sitio, consulte [Copiar un sitio de comercio electrónico](copy-ecommerce-site.md).

### <a name="manage-an-existing-site-channel"></a>Administrar un canal de sitio existente

Después de configurar un sitio con un canal, puede administrar y actualizar el canal desde el sitio seleccionado en el generador de sitios en **Configuración del sitio \> Canales**, como se muestra en la siguiente ilustración de ejemplo.

![Administración de la asignación de canales en el generador de sitios.](media/channel-mapping-7.png)

## <a name="support-multiple-sites-in-a-single-tenant"></a>Admitir varios sitios en un solo inquilino

Muchos sitios de marca pueden coexistir en un solo inquilino. La siguiente ilustración de ejemplo muestra tres sitios de marca diferentes (Adventure Works, Adventure Works Business y Fabrikam), cada uno de los cuales está asignado a un único canal en línea diferente.

![Lista de sitios en el generador de sitios.](media/channel-mapping-8.png)

## <a name="configure-a-single-domain-name-with-paths-for-multiple-sites"></a>Configure un solo nombre de dominio con rutas para múltiples sitios

Se puede usar un solo nombre de dominio para varios sitios, y las rutas se pueden usar para separar sitios o idiomas. Por ejemplo, el dominio de `www.mycompany.com` está configurado para dos sitios de comercio electrónico diferentes: uno para Fabrikam y otro para Adventure Works. En este caso, la ruta predeterminada (`www.mycompany.com`), también conocida como la ruta de acceso en blanco, se puede usar para el sitio de Fabrikam y otra ruta de acceso (por ejemplo, `www.mycompany.com/adventureworks`) se puede utilizar para el sitio de Adventure Works. Otra opción es utilizar una ruta personalizada (por ejemplo, `www.mycompany.com/fabrikam`) en lugar de la ruta predeterminada para el sitio de Fabrikam también.

Alternativamente, se puede usar un nombre de dominio diferente para cada sitio (por ejemplo, `www.adventure-works.com` y `www.fabrikam.com`). Las rutas se pueden usar para diferentes idiomas o regiones (por ejemplo, `www.adventure-works.com/fr-ca` para el francés de Canadá).

## <a name="configure-multiple-languages-on-a-site"></a>Configurar varios idiomas en un sitio

Se pueden configurar idiomas para el sitio de comercio electrónico en el generador de sitios en **Configuración del sitio \> Canales**. En la siguiente ilustración de ejemplo, cada idioma se ha configurado utilizando la configuración regional para la ruta de acceso, de modo que cada idioma tenga una URL única.

![Varios idiomas configurados en un sitio.](media/channel-mapping-10.png)

Para agregar un nuevo idioma de canal, vaya a **Configuración del sitio \> Canales** y seleccione el vínculo del canal. En el panel que aparece a la derecha, seleccione **Agregar una configuración regional** para seleccionar el canal y la configuración regional que desea agregar. Luego especifique la ruta que se usará para el canal seleccionado.

### <a name="add-and-configure-the-site-picker-module"></a>Agregar y configurar el módulo selector de sitios

Una vez haya configurado un sitio con varios idiomas o canales, es posible que desee agregar un selector de idioma al encabezado de la página del sitio, para que los usuarios puedan seleccionar manualmente su idioma o país. La biblioteca de módulos [módulo de encabezado](author-header-module.md) tiene compatibilidad integrada para que los usuarios seleccionen un idioma usando el [módulo selector de sitio](site-selector.md). El módulo de selector de sitios se puede agregar al módulo de encabezado del fragmento de encabezado.

Para obtener más información sobre cómo agregar y configurar el módulo selector de sitios, consulte [Módulo selector de sitios](site-selector.md).

### <a name="implement-page-variants-for-each-language"></a>Implementar variantes de página para cada idioma

En este escenario, solo hay un canal, pero hay varios idiomas. Puede cambiar la apariencia de una página según el idioma seleccionado creando una variante de página para ella. A continuación, puede agregar contenido localizado a la variante.

Cuando tiene una página abierta en el generador de sitios y selecciona el vínculo en la esquina superior derecha que muestra el canal y el idioma actuales, aparece un selector de canal e idioma, como se muestra en la siguiente ilustración de ejemplo. Si desea invalidar la página para el idioma actual, seleccione otra configuración regional y luego seleccione **Cambiar**. También puede cambiar el canal si está [asignando un sitio que tiene varios canales e idiomas](#manage-site-content-that has-multiple-channels-and-languages).

![Cambiar el idioma de una página en el generador de sitios.](media/channel-mapping-14.png)

Si aún no se ha creado la variante para la página o el fragmento seleccionado, recibe un mensaje de advertencia, como se muestra en la siguiente ilustración de ejemplo. En este caso, seleccione el vínculo **Crear variante de página** en el texto del mensaje. El cuadro de diálogo que aparece proporciona opciones que le permiten empezar con una copia de una variante existente o crear una página nueva a partir de una plantilla.

![Solicitud para crear una variante de página en el generador de sitios](media/channel-mapping-16.png)

Si no crea una variante, la página original se representa y muestra el idioma apropiado para las cadenas de módulos y la información del producto de Commerce headquarters. Sin embargo, si el texto, como un título de página u otro contenido de marketing, se ha especificado directamente en los módulos de página predeterminados, las cadenas de ese texto permanecerán en el idioma original.

En lugar de crear manualmente cada página y fragmento, puede exportar cada página y fragmento a un archivo de formato de archivo de intercambio de localización XML (XLIFF) que luego se puede enviar para su localización. Una vez localizado cada XLIFF, se puede importar como una variante de página localizada. Para exportar un archivo XLIFF desde una página o fragmento en el generador de sitios, o para importar un archivo XLIFF a una página o fragmento, seleccione **Localización** en la barra de comandos. A continuación, seleccione **Exportar XLIFF** o **Importar XLIFF**, como se muestra en la siguiente ilustración de ejemplo.

![Importación o exportación de una página o fragmento en formato XLIFF.](media/channel-mapping-18.png)

## <a name="manage-site-content-that-has-multiple-channels-and-languages"></a>Administre el contenido del sitio que tiene varios canales e idiomas

Un sitio que tiene varios canales y/o idiomas almacena una variante única de cada página y fragmento para cada combinación de un canal y un idioma. Este comportamiento permite que las variantes de página contengan datos localizados, pero también le brinda la flexibilidad de cambiar la apariencia de una página para una variante específica.

Para obtener información sobre cómo trabajar con variantes de página, consulte la sección [Implementar variantes de página para cada idioma](#implement-page-variants-for-each-language) de este tema.

## <a name="configure-multiple-channels-on-an-e-commerce-site"></a>Configurar varios canales en un sitio de comercio electrónico

Puede agregar canales a un sitio de comercio electrónico en el generador de sitios yendo a **Configuración del sitio \> Canales** y seleccionando **Agregar un canal**. A continuación, en el cuadro de diálogo **Agregar un canal** que aparece, puede seleccionar el canal en línea y la configuración regional predeterminada.

## <a name="additional-resources"></a>Recursos adicionales

[Información general de canales](channels-overview.md)

[Configurar un canal en línea](channel-setup-online.md)

[Información general de las organizaciones y las jerarquías organizativas](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md)

[Configurar la detección geográfica y la redirección](geo-detection-redirection.md)

[Habilitar y usar el uso compartido entre canales](cross-channel-sharing.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Copiar un sitio de comercio electrónico](copy-ecommerce-site.md)

[Módulo de selector de sitios](site-selector.md)

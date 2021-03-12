---
title: Habilitar y usar el uso compartido entre canales
description: Este tema describe cómo habilitar y usar la función de uso compartido entre canales del generador de sitios de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3990365dda0a0cff7adcc1d97120293d43f6e858
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973140"
---
# <a name="enable-and-use-cross-channel-sharing"></a>Habilitar y usar el uso compartido entre canales

[!include [banner](includes/banner.md)]

Este tema describe cómo habilitar y usar la función de uso compartido entre canales del generador de sitios de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

El intercambio entre canales permite a los minoristas reutilizar y compartir contenido entre varios canales de un sitio. Esta capacidad es útil cuando los canales del sitio tienen un idioma base compatible o cuando tienen numerosos elementos de contenido en común.

El uso compartido entre canales funciona habilitando un canal predeterminado en el que se buscará contenido disponible cuando no se encuentre una versión específica del canal del contenido solicitado. El contenido que se pretende compartir entre canales se crea en el canal predeterminado. Ese contenido se puede localizar para cualquier configuración regional que se utilice en cualquier canal del sitio.

## <a name="when-to-use-cross-channel-sharing"></a>Cuándo usar el uso compartido entre canales

El uso compartido entre canales es útil cuando varios canales en un solo sitio pueden compartir contenido. Por ejemplo, un minorista que tiene varias marcas y escaparates que están agrupados en un solo sitio puede compartir contenido entre algunos o todos los escaparates. Este contenido compartido puede incluir páginas de términos y condiciones, condiciones de pago, métodos de envío y preguntas frecuentes (FAQ).

El uso compartido entre canales también admite fragmentos. Por lo tanto, se puede crear una página de contenido que contenga fragmentos específicos del canal como contenido multicanal. En este caso, aunque la mayor parte del contenido se compartirá entre canales, los fragmentos específicos del canal en una página de varios canales se mostrarán solo cuando se soliciten desde el canal de la tienda correspondiente.

Los sitios que tienen un solo canal, o los sitios que tienen varios canales que no pueden compartir contenido, no se beneficiarán del uso compartido entre canales.

## <a name="enable-cross-channel-sharing"></a>Habilitar el uso compartido entre canales

El uso compartido entre canales está habilitado a nivel de sitio. Esta operación es unidireccional. En otras palabras, una vez que se habilita el uso compartido entre canales, no se puede deshabilitar.

Para habilitar el uso compartido entre canales en el creador de sitios de Commerce, siga estos pasos.

1. Vaya a **Configuraciones del sitio \> Características**.
1. Configure la opción para la característica **Canal transversal** en **Activado**.

    ![Opción de canal cruzado establecida en Activado en el creador de sitios de comercio](./media/enabling-cross-channel-sharing.png)

Después de habilitar el uso compartido entre canales, la información entre canales aparecerá en la sección **Canales** de **Configuración del sitio \> Caracteristicas**, como muestra el ejemplo de la siguiente ilustración.

![Información de canales visible después de habilitar el uso compartido entre canales](./media/channels-cross-channel.png)

Además, después de habilitar el uso compartido entre canales, el campo **Canal** en la parte superior derecha del creador de sitios de comercio incluirá una opción **Tienda online multicanal** que puede usar para administrar contenido multicanal, como se muestra en la siguiente ilustración.

![Opción Tienda en línea entre canales en el campo Canales después de que se habilita el uso compartido entre canales](./media/cross-channel-dropdown.png)

## <a name="create-and-use-cross-channel-content"></a>Crear y usar contenido entre canales

Puede crear y utilizar contenido multicanal de varias formas. Por ejemplo, puede crear fragmentos multicanal, crear páginas multicanal que utilicen contenido multicanal y específico del canal, y anular fragmentos multicanal con versiones de fragmentos específicas del canal.

### <a name="create-a-cross-channel-fragment"></a>Crear un fragmento de canales cruzados

Para crear un fragmento entre canales en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.
1. En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Banner promocional** y, en **Nombre del fragmento**, escriba un nombre (por ejemplo, **Banner transcanal**). A continuación seleccione **Aceptar**.
1. En el panel de propiedades del módulo **Banner promocional**, seleccione **Agregar mensaje** y luego seleccione **Mensaje**.
1. En el cuadro de diálogo **Mensaje**, debajo de **Texto**, introduzca **Canal cruzado** y seleccione **Aceptar**. 
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

Este fragmento de canal cruzado se puede utilizar en páginas de canal cruzado o específicas de canal que se crean en cualquier canal del sitio.

### <a name="create-a-cross-channel-page-that-uses-cross-channel-content"></a>Cree una página multicanal que utilice contenido multicanal.

Las páginas multicanal se pueden utilizar en cualquier canal de su sitio. Por lo tanto, puede crear una página de contenido compartido una vez y realizar actualizaciones posteriores en un solo lugar. Por ejemplo, una página de **Términos y Condiciones** de un canal cruzado que tiene la URL `/toc` se puede compartir entre todos los canales de un sitio. Si las URL base de los canales del sitio son `www.fabrikam.com/brand1` y `www.fabrikam.com/brand2`, el mismo canal cruzado, compartido **Términos y Condiciones** estará disponible en las URL de canal de ambos sitios, en `www.fabrikam.com/brand1/toc` y `www.fabrikam.com/brand2/toc`, respectivamente. Si la página **Términos y Condiciones** debe actualizarse más tarde, debe actualizar solo la página única compartida.

Para crear una página multicanal en el creador de sitios de Commerce que utilice contenido multicanal, siga estos pasos.

1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Elegir una plantilla**, seleccione una plantilla, como **Marketing**.
1. En **Nombre de página**, especifique un nombre de página (por ejemplo, **Página entre canales**).
1. Debajo de **URL de la página**, ingrese la URL de una página (por ejemplo, **examplepage**) y luego seleccione **Aceptar**.
1. En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar fragmento**.
1. En el cuadro de diálogo **Agregar fragmento**, seleccione el fragmento transcanal que creó anteriormente y que tiene un banner promocional. A continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. Debería ver el banner promocional que dice "Multicanal".
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

### <a name="create-a-channel-specific-page-that-uses-cross-channel-content"></a>Cree una página específica del icanal que utilice contenido multicanal.

Al utilizar contenido multicanal en páginas específicas del canal, puede crear un fragmento de contenido compartido una vez y luego usarlo en páginas específicas del canal. Este "suministro único" es útil para contenido compartido, como términos y condiciones, condiciones de pago o información de contacto.

Para crear una página específica del icanal en el creador de sitios de Commerce que utilice contenido multicanal, siga estos pasos.

1. Desde dentro de un canal específico, como **Tienda online ampliada Fabrikam**, vaya a **Páginas** y luego seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Elegir una plantilla**, seleccione una plantilla, como **Marketing**.
1. En **Nombre de página**, especifique un nombre de página (por ejemplo, **Página específica del canal**).
1. Debajo de **URL de la página**, ingrese la URL de una página (por ejemplo, **channelspecificpage**) y luego seleccione **Aceptar**.
1. En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar fragmento**.
1. En el cuadro de diálogo **Agregar fragmento**, en **Canal**, seleccione **Tienda online transcanal**. El fragmento de canal cruzado que creó anteriormente debería aparecer en la lista. Selecciónelo y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. Debería ver el banner promocional que dice "Multicanal".
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

### <a name="create-a-channel-specific-version-of-a-cross-channel-page"></a>Crear una versión específica del canal que utilice una página multicanal.

El uso compartido entre canales admite la anulación del contenido entre canales. Por ejemplo, todos menos uno de los canales de su sitio comparten el mismo contenido. Ese canal de un sitio requiere contenido diferente. Para implementar el contenido diferente para él, anula el contenido de varios canales con contenido específico del canal creando una versión específica del canal de la página de varios canales.

Para crear una versión específica del canal de una página multicanal en el creador de sitios de Commerce, siga estos pasos.

1. En el campo **Canal** en la parte superior derecha, seleccione **Tienda online multicanal**.
1. Abra la página multicanal que creó anteriormente.
1. En el campo **Canal** en la parte superior derecha, seleccione el canal que debe tener contenido específico. El editor de página muestra un mensaje que le solicita que cree una nueva variante de página.
1. Seleccione **Crear variante de página**.
1. En el espacio **Principal** de la variante de página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Banner promocional** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo **Banner promocional**, seleccione **Agregar mensaje** y luego seleccione **Mensaje**.
1. En el cuadro de diálogo **Mensaje**, debajo de **Texto**, introduzca **Específico del canal** y seleccione **Aceptar**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. Debería ver el banner promocional que dice "Específico del canal".
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

Ahora, si usa la URL base del canal y va a la URL de la página multicanal en ese sitio, verá el contenido específico del canal en lugar del contenido multicanal.

## <a name="additional-resources"></a>Recursos adicionales

[Métodos para agregar contenido](add-manage-content.md)

[Glosario del modelo de página](page-elements-overview.md)

[Estados y ciclo de vida de documentos](document-states-overview.md)

[Trabajar con grupos de publicación](publish-groups.md)

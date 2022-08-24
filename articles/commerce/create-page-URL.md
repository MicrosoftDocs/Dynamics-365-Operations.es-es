---
title: Crear una URL de página
description: En este artículo se tratan los conceptos básicos y los procedimientos para crear una dirección URL de página en el sitio.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 8718a3a2854ecdc7aec0853569dcba9e26a86d67
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270164"
---
# <a name="create-a-page-url"></a>Crear una URL de página

[!include [banner](includes/banner.md)]

En este artículo se tratan los conceptos básicos y los procedimientos para crear una dirección URL de página en el sitio.

La dirección URL completa, o absoluta, que apunta a una página en el sitio consta de distintas partes. Por ejemplo, la dirección URL `https://www.contoso.com/en-us/contactus` tiene las siguientes partes:

- `https://www.contoso.com`: el protocolo HTTP y el dominio del sitio.
- `/en-us`: la ruta de acceso del idioma del sitio.
- `/contactus`: la dirección URL relativa para la página **Ponerse en contacto con nosotros**. Una dirección URL relativa también se conoce como *slug* de URL.

Establezca el dominio del sitio y la ruta de acceso de idioma opcional al configurar el sitio. Puede agregar más dominios y rutas de acceso de idioma al sitio a través de la página de tiendas en línea en la configuración del sitio.

El slug de URL para una página existe como entidad independiente en el entorno de creación del sitio. Una dirección URL de página consta de dos partes: un nombre que representa el slug de URL, y un puntero a una página en el sitio o un sitio externo. Una dirección URL de página también se puede configurar para actuar como una redirección en su sitio o un sitio externo.

## <a name="create-a-page-url"></a>Crear un URL de página

Hay dos maneras de crear direcciones URL de página:

- Automáticamente, al crear una página
- Manualmente, desde la página **Direcciones URL**

### <a name="create-a-page-url-when-you-create-a-page"></a>Crear una dirección URL de página al crear una página

Si proporciona un nombre en el campo **Dirección URL** al crear una nueva página, se crea automáticamente una dirección URL que apunta a esa página en la página **Direcciones URL**. Tras publicar la dirección URL y la página a la que apunta, los usuarios del sitio (sus clientes) pueden tener acceso a la página que está asociada a la dirección URL.

> [!NOTE]
> Si publica una dirección URL sin publicar la página a la que apunta, los usuarios del sitio reciben un error 404 al intentar tener acceso a la página. Si publica una página sin publicar la dirección URL a la que apunta, no se podrá tener acceso a la página con una dirección URL.

### <a name="manually-create-a-page-url"></a>Crear manualmente una URL de página

Al crear páginas nuevas, no es necesario especificar una dirección URL de página. Si dejas en blanco el campo de la dirección URL, la página se crea en un estado desvinculado. En este caso, los clientes no podrán tener acceso a la página, aunque se publique. Para que la página sea accesible, debe crear manualmente la dirección URL y vincularla a la página.

Para crear manualmente la dirección URL de página para una página, siga estos pasos.

1. En la página **Direcciones URL**, seleccione **Nuevo**.
1. Seleccione la página del sitio a la que desea asociar la dirección URL.
1. Especifique el slug de URL y, a continuación, seleccione **Aceptar**.

En este punto, la dirección URL se encuentra en un estado de borrador. Debe estar publicada antes de que los usuarios del sitio puedan tener acceso a la página asociada.

## <a name="update-a-page-url"></a>Actualizar una URL de página

Para actualizar la página de destino de una dirección URL de página, siga estos pasos.

1. En la página **Direcciones URL**, seleccione la URL que se actualizará.
1. En el panel de propiedades de la derecha, seleccione los puntos suspensivos (**...**) situados junto al campo de página de destino.
1. En el cuadro de diálogo, seleccione una página diferente y **Aceptar**.
1. Guarde y publique la URL.

## <a name="redirect-a-page-url"></a>Redireccionar una URL de página

A veces, es posible que desee que los clientes ver una página diferente al solicitar una dirección URL específica. En estos casos, el mejor enfoque, y el más sencillo, es a menudo cambiar la página a la que apunta la dirección URL de página. Sin embargo, puede que tenga motivos legítimos para usar redirecciones HTTP 301 o 3023 para redirigir las solicitudes para una dirección URL a otra dirección URL.

Para redirigir una dirección URL a otra dirección URL, siga estos pasos.

1. En la página **Direcciones URL**, seleccione la URL que se actualizará.
1. En el panel de propiedades de la derecha, seleccione **Redirigir**.
1. Seleccione un destino para la redirección.

    - Para apuntar a otra página del sitio, seleccione **Dirección URL interna**, seleccione los puntos suspensivos (**...**) y, a continuación, la URL a la que redirigir.
    - Para apuntar a una página de un sitio externo, seleccione **Dirección URL externa** y, a continuación, indique la URL completa de esa página. Asegúrese de incluir el protocolo. Por ejemplo, escriba `https://domain.com/new/page`. Si la dirección URL redirige a una dirección URL interna, debe seleccionar **Borrar selección** para poder especificar una dirección URL externa.

1. Seleccione un tipo de redirección:

    - **Redirección permanente (301)**: seleccione esta opción cuando sepa que su contenido se está moviendo permanentemente y que no revertirá a su dirección URL anterior. Los motores de búsqueda asignarán el valor de la optimización de motor de búsqueda (SEO) de la dirección URL de redireccionamiento a la dirección URL a la que se está redirigiendo y actualizará su registro para mostrar la nueva dirección URL. 
    - **Redirección temporal (302)**: seleccione esta opción para redirigir tráfico sin actualizar motores de búsqueda. Este enfoque se suele usar si el contenido se revertirá pronto a su dirección URL anterior.

1. Cuando esté listo para implementar la redirección, guarde y publique la dirección URL.

## <a name="additional-resources"></a>Recursos adicionales

[Personalizar navegación del sitio](customize-site-navigation.md)

[Agregar una página de sitio nueva](add-new-page.md)

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Agregar idiomas al sitio](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

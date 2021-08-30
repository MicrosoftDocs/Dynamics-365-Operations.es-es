---
title: Visión general de creación de páginas
description: Este tema proporciona una visión general de la página de creación en Microsoft Dynamics 365 Commerce.
author: brendans
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application USer
ms.reviewer: v-chgri
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: brendans
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c837b018bddfeb28311c630a7558c09274ced2c1cfce7405587bd1be78d72a96
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719971"
---
# <a name="authoring-page-overview"></a>Información general de creación de páginas

  
 [!include [banner](includes/banner.md)]

Este tema proporciona una visión general de la página de creación en Microsoft Dynamics 365 Commerce.

Las páginas web se pueden crear para admitir diversas necesidades empresariales. Pueden representar un negocio completo, ofrecer un canal único del negocio o tener como objetivo un público específico o un segmento de un público. Por ejemplo, es posible que un fabricante de ropa pueda tener un sitio web que muestre todas las marcas que posee. El mismo fabricante de ropa puede tener entonces un sitio web independiente para cada una de esas marcas, y también un conjunto de sitios web que ofrezcan moda de lujo, moda de actividades de exterior y moda de niños.

Dynamics 365 Commerce admite la creación y la administración de varias sitios web, y cada sitio web puede tener su propio aspecto y contenido. La página de creación sirve como punto de acceso común para estos sitio web. Puede usarla para iniciar y cerrar sesión del sistema, y para crear nuevos sitios web.

Actualmente, la página de la creación consta de las siguientes secciones.

- **Barra superior**: la barra superior aparece en la parte superior de la página de creación. Proporciona fácil acceso a herramientas de comercio electrónico, notificaciones, vínculos de soporte e inicio de sesión de usuario.
- **Barra de comandos**: la barra de comandos aparecer debajo de la barra de superior. Se puede usar para crear nuevos sitios web.
- **Lista de sitios**: la lista de sitios rellena todo el espacio que se encuentra debajo de la barra de comandos. Ofrece una lista completa de sitios web y los dominios que están asociados a ellos.

La ilustración siguiente muestra la página de creación.

![Página de creación de Dynamics 365 Commerce.](../commerce/media/authoring_tools_01.png)

## <a name="use-the-home-button-to-select-a-tool"></a>Usar el botón Inicio para seleccionar una herramienta

El botón **Inicio** se encuentra en la esquina superior izquierda de la página de creación. Proporciona fácil acceso a otras herramientas de comercio electrónico. Al seleccionar este botón, se abre un menú de las herramientas que puede usar. Al seleccionar una herramienta, se cierra el menú y se carga la herramienta seleccionada en el explorador.

## <a name="view-and-clear-notifications"></a>Ver y borrar notificaciones

El botón **Notificaciones** es uno de los botones de la esquina superior derecha de la página de creación. Parece una campana. Al seleccionar este botón, puede ver todas las notificaciones que se te han enviado.

Las notificaciones se utilizan a través de la herramienta de configuración para informarle de cuándo se han completado las acciones. Por ejemplo, una notificación puede indicar “Se ha publicado su página” para informarle de que una acción de publicación fue correcta.

Las notificaciones también pueden informarle de errores que se encontraron mientras se estaba realizando una acción. Seleccione la notificación de error para abrir su mensaje. La información de este mensaje puede ayudarle a resolver el error.

Puede borrar notificaciones del menú de notificación seleccionando **Eliminar** en la parte inferior del mensaje de notificación. Para borrar notificaciones en grandes cantidades, seleccione **Eliminar todo** en la parte inferior del menú de notificación.

## <a name="get-help-with-the-authoring-tool"></a>Obtener ayuda con la herramienta de creación

El botón **Ayuda** es otro botón de la esquina superior derecha de la página de creación. Se parece a un signo de interrogación. Al seleccionar este botón, se abre un menú de las siguientes opciones predefinidas:

- **Ayuda de desarrollo del sitio**: si selecciona esta opción, se abre la documentación para crear un nuevo sitio web en una nueva pestaña de explorador.
- **Comentarios y soporte**: seleccione esta opción para abrir un canal de Microsoft Yammer donde puede dejar comentarios acerca de la herramienta de creación o solicitar soporte.
- **Privacidad y cookies**: si selecciona esta opción, la Declaración de privacidad de Microsoft se abre en una nueva pestaña del explorador.
- **Acerca de**: seleccione esta opción para abrir un cuadro de mensaje que contiene información sobre la herramienta de creación y la versión que está utilizando actualmente.

## <a name="sign-in-to-and-out-of-the-authoring-tool"></a>Iniciar o cerrar sesión de la herramienta de creación

El botón **Mi cuenta** es otro botón de la esquina superior derecha de la página de creación. Parece un círculo coloreado. Al seleccionar este botón, puede ver qué cuenta ha usado para iniciar sesión, y también puede cerrar sesión de esa cuenta según sea necesario.

Para iniciar o cerrar sesión de la herramienta de creación, siga uno de estos pasos.

- Si aún no ha iniciado sesión en la herramienta de creación, seleccione **Mi cuenta** \> **Iniciar sesión** para iniciar sesión.
- Si ya ha iniciado sesión y desea cerrarla, seleccione **Mi cuenta** \> **Cerrar sesión**.

## <a name="change-the-display-language-of-the-authoring-tool"></a>Cambie el idioma de visualización de la herramienta de creación

También puede usar el botón **Mi cuenta** para cambiar el idioma de las cadenas de texto que aparecen en la herramienta de creación.

Para cambiar el idioma de visualización, siga estos pasos.

1. Seleccione **Mi cuenta** \> **Cambiar idioma**. Aparece un cuadro de diálogo.
1. Seleccione uno de los idiomas de usuario y, a continuación, **Guardar**.

## <a name="create-a-new-website"></a>Crear un nuevo sitio web

Dynamics 365 Commerce admite la creación y la administración de varias sitios web, y cada sitio web puede tener su propio aspecto y contenido.

Para crear un nueva sitio web, siga estos pasos.

1. En la barra de comandos, seleccione **Nuevo sitio web**. Aparece un cuadro de diálogo.
2. Especifique la siguiente información necesaria para el nuevo sitio web:

    - **Nombre del sitio**: especifique el nombre del sitio web. Este nombre no se muestra a los clientes del sitio web. En su lugar, se utiliza en la lista de sitios y otros lugares de la herramienta de creación.
    - **Grupo de seguridad de administradores del sitio**: permite especificar el nombre completo del grupo de seguridad de Microsoft Azure Active Directory (Azure AD) que contiene los usuarios que deben tener acceso administrativo al sitio web. El nombre del grupo de administradores, junto con los demás permisos para el sitio web, se puede modificar después de crear el sitio web.
    - **Canal predeterminado**: permite especificar el canal de comercialización predeterminado que se debe asociar al sitio web. El canal predeterminado determina los productos que se pueden vender a través del sitio web.
    - **Idioma predeterminado**: después de especificar el canal predeterminado, seleccione el idioma predeterminado para el canal. El canal predeterminado define el idioma en el que se muestran los productos si el cliente no especifica un idioma preferido.
    - **Mercado predeterminado**: especifique el mercado predeterminado para el sitio web. El mercado predeterminado define el mercado que se muestra si el cliente no especifica un mercado preferido.
    - **Dominio**: seleccione el dominio web que se debe asociar al sitio web. Este dominio es el dominio al que irán los clientes del sitio web en su explorador.

1. Seleccione **Aceptar**. Se crea el nuevo sitio web.

> [!NOTE]
> La creación de un nueva sitio web puede tardar hasta 60 segundos. Una vez se ha completado el proceso, aparece una notificación en el área de notificación. Además, el sitio web aparece en la lista de sitios y tiene el nombre del sitio especificado.

## <a name="select-a-website-to-author"></a>Seleccionar un sitio web para autor

La lista de sitios ofrece una lista completa de los sitios web que están asociados al sistema de comercio electrónico. Los sitios web aparecen en orden alfabético. También se muestra el dominio que está asociado a cada sitio web. Para ver el contenido de un sitio web y empezar a crear páginas, seleccione el nombre del sitio web. Se cargan la herramienta de creación y el contenido del sitio web.

Una vez que se carga la herramienta de creación, puede seleccionar **Página principal** para volver a la página de creación.

## <a name="additional-resources"></a>Recursos adicionales

[Administrar usuarios y roles de comercio electrónico](manage-ecommerce-users-roles.md)

[Consideraciones de optimización de motor de búsqueda (SEO) para su sitio](search-engine-optimization-considerations.md)

[Gestionar la directiva de seguridad de contenido (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

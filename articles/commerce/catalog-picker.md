---
title: Módulo de selector de catálogos
description: Este artículo cubre los módulos de selector de catálogos y describe cómo agregarlos a sitios de comercio electrónico de empresa a empresa (B2B) de Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-04-21
ms.openlocfilehash: 642319eea7e40415fd32898f6ec07bfc86f3b1b1
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136950"
---
# <a name="catalog-picker-module"></a>Módulo de selector de catálogos

[!include [banner](includes/banner.md)]

Este artículo cubre los módulos de selector de catálogos y describe cómo agregarlos a sitios de comercio electrónico de empresa a empresa (B2B) de Microsoft Dynamics 365 Commerce.

Un módulo de selector de catálogos es un contenedor especial que se utiliza para enumerar todos los catálogos de productos que están disponibles para que compren los usuarios del sitio B2B. Actualmente, solo se admiten varios catálogos para sitios B2B.

En la ilustración siguiente se muestra un ejemplo de módulo de selector de catálogos.

![Ejemplo de módulo de selector de catálogos que enumera tres catálogos de productos.](./media/Catalog-picker-sample.png)

## <a name="add-a-catalog-picker-module-to-your-site"></a>Agregar un módulo de selector de catálogos al sitio

Para agregar un módulo de selector de catálogos a su sitio en el generador de sitios de Commerce, siga estos pasos.

### <a name="create-a-catalog-picker-page"></a>Crear una página de selector de catálogos

Primero, cree una página de selector de catálogos.

1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Crear nueva página**, en **Nombre de página**, introduzca **Selector de catálogos**.
1. En **URL de página**, introduzca un URL para la página y después seleccione **Siguiente**.

    ![Cree un cuadro de diálogo de nueva página.](./media/Create-catalog-picker-page.png)

1. En **Elegir plantilla**, seleccione **Contenido general** y luego seleccione **Siguiente**.
1. En **Elegir un diseño**, seleccione **Diseño flexible** y luego seleccione **Siguiente**.
1. En **Revisar y terminar**, revise la configuración de la página. Si debe editar la información de la página, seleccione **Atrás**. Si la información de la página es correcta, seleccione **Crear página**.
1. En **Selector de catálogos**, seleccione **Franja principal**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.

    ![Agregar un módulo a la franja principal en el selector de catálogos.](./media/Author-web-page-catalog-picker-1.png)

1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. Seleccione el **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Selector de catálogos** y, a continuación, **Aceptar**.
1. En el panel de propiedades del **Selector de catálogos**, en **Encabezado**, seleccione **Catálogos** y, a continuación, introduzca un encabezado para la página del selector de catálogos.
1. Debajo de **Nivel de título**, seleccione el nivel de título y luego seleccione **Aceptar**.
1. En **Texto enriquecido**, introduzca texto que aparecerá en la parte superior de la página del selector de catálogos.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

### <a name="add-a-link-on-your-account-page"></a>Agregue un enlace en la página de su cuenta

A continuación, agregue una referencia a su página de selector de catálogos en su página **Mi cuenta**.

1. Vaya a **Páginas**, busque y seleccione la página **Mi cuenta** del sitio y, a continuación, seleccione **Editar**.
1. En la franja **Principal** de la página, seleccione la franja **Icono genérico de cuenta**. 
1. En el panel de propiedades de **Icono genérico de cuenta**, en **Enlaces**, seleccione **Agregar enlace de acción** y luego seleccione **Enlace de acción**.
1. En el cuadro de diálogo **Enlace de acción**, en **Texto del enlace**, introduzca el texto del enlace para el enlace a su página de selector de catálogos.
1. En **Destino del enlace**, seleccione **Agregar un enlace**.
1. En el cuadro de diálogo **Agregar un enlace**, seleccione **Página personalizada** y luego seleccione **Siguiente**.
1. En **Nombre**, seleccione su página del selector de catálogos, seleccione **Aplicar** y luego seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

La siguiente ilustración muestra un ejemplo de una página de cuentas con una referencia a la página del catálogo.

![Página de mis cuentas con enlace al catálogo.](./media/my-accounts.png)

### <a name="add-a-link-from-the-header"></a>Agregar un enlace desde el encabezado

Finalmente, agregue un enlace desde el encabezado de su sitio a sus catálogos.

1. Vaya a **Fragmentos**, busque y seleccione el fragmento de encabezado de su sitio y, a continuación, seleccione **Editar**.
1. Seleccione la franja **Encabezado**. 
1. En el panel de propiedades de **Encabezado**, en **Vínculos de Mi cuenta**, seleccione **Agregar enlace de acción** y luego seleccione **Enlace de acción**.
1. En el cuadro de diálogo **Enlace de acción**, en **Texto del enlace**, introduzca el texto del enlace para el enlace a su página de selector de catálogos.
1. En **Destino del enlace**, seleccione **Agregar un enlace**.
1. En el cuadro de diálogo **Agregar un enlace**, seleccione **Página personalizada** y luego seleccione **Siguiente**.
1. En **Nombre**, seleccione su página del selector de catálogos, seleccione **Aplicar** y luego seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento de encabezado y luego seleccione **Publicar** para publicarlo.

La siguiente ilustración muestra un ejemplo de un encabezado del sitio web de comercio electrónico con un enlace al catálogo B2B.

![Encabezado del sitio web de comercio electrónico con enlace desplegable al catálogo.](./media/catalog-in-header.png)


## <a name="additional-resources"></a>Recursos adicionales 

[Crear catálogos de Commerce para sitios B2B](catalogs-b2b-sites.md)

[Impacto de extensibilidad de los catálogos de Commerce para personalizaciones B2B](catalogs-b2b-sites-dev.md)

[Catálogos comerciales para preguntas frecuentes B2B](catalogs-b2b-sites-FAQ.md)

[Módulos y páginas de gestión de cuentas](account-management.md)

[Módulo de encabezado](author-header-module.md)

---
title: Administrar clasificaciones y revisiones
description: En este tema se explica cómo administrar clasificaciones y revisiones mediante la herramienta de moderación de clasificaciones y revisiones de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a7fa2ae3124a0a68b3890987c5dce2730e5c2183
ms.sourcegitcommit: 1e6c8163da5818196769eb278afb3a2335d0cbe3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027251"
---
# <a name="manage-ratings-and-reviews"></a>Administrar clasificaciones y revisiones

[!include [banner](includes/banner.md)]

En este tema se explica cómo administrar clasificaciones y revisiones mediante la herramienta de moderación de clasificaciones y revisiones de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Dynamics 365 Commerce uses Microsoft Azure Cognitive Service para moderar automáticamente el texto de revisión redactando palabras profanas. Además, los moderadores pueden usar la herramienta de moderación de clasificaciones y revisiones para las siguientes tareas manuales:

- Moderar revisiones respondiendo a ellas o quitándolas.
- Eliminar la revisión de un cliente en la solicitud del cliente.
- Realizar la importación masiva de datos de clasificaciones y revisiones para todos los productos en una plantilla de Microsoft Power BI, para poder analizar las tendencias para las clasificaciones y revisiones.

## <a name="access-ratings-and-reviews-moderation-features"></a>Acceder a características de moderación de clasificaciones y revisiones

Para acceder a las características de moderación de clasificaciones y revisiones en la herramienta de administración del sitio de comercio electrónico, siga estos pasos.

1. Inicie sesión en [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).
1. Abre el proyecto que contiene el entorno donde desea inicializar el comercio electrónico.
1. En la sección **Entornos**, seleccione el entorno.
1. En **Características del entorno**, seleccione **Administración de venta minorista**.
1. En la pestaña **Comercio electrónico** debajo de **Vínculos**, seleccione **Herramienta de administración del sitio de comercio electrónico**.

## <a name="read-a-review"></a>Leer una revisión 

1. Vaya a **Inicio \> Revisiones \> Moderación**.
1. Use el campo de búsqueda de la parte superior derecha de la página para filtrar las revisiones que se muestran por id. de producto, nombre del producto o texto de la revisión.

Los filtros adicionales le permiten limitar las revisiones por período, calificación, canal o estado de preocupación (retirado, respondido o notificado).

![Página principal de moderación](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a>Respuesta a una revisión 

A veces, los clientes que compraron un producto expresan su satisfacción, o descontento o no entienden cómo utilizar el producto. Como moderador, puede registrar una respuesta en una revisión. Esta respuesta aparece junto con la revisión en el sitio. 

Para responder a una revisión, siga estos pasos.

1. Vaya a **Inicio \> Revisiones \> Moderación**.
1. Busque y seleccione la revisión que requiere una respuesta.
1. En el panel de propiedades de la derecha, seleccione **Agregar una respuesta**.
1. Escriba el texto de la respuesta y el nombre que se debe mostrar para el respondedor. El nombre predeterminado del respondedor es **Moderador**.
1. Cuando haya terminado, seleccione **Publicar respuesta**.

![Respuesta a una revisión](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a>Retirar una revisión 

A veces, hay una justificación comercial para que los moderadores retiren revisiones del cliente. 

Para retirar una revisión, siga estos pasos.

1. Vaya a **Inicio \> Revisiones \> Moderación**.
1. Busque y seleccione la revisión que se debe retirar.
1. En el panel de las propiedades de la derecha, seleccione un motivo de retirada y, a continuación, **Retirar**.
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a>Eliminar la revisión de un cliente en la solicitud del cliente 

A veces, los clientes desean que los datos de clasificaciones y revisiones se eliminen de manera permanente de un sitio web de comercio electrónico. Un moderador que recibe una solicitud de eliminación de un cliente puede quitar los datos del cliente mediante la característica de eliminación de revisión. Para buscar y eliminar los datos de un cliente, el moderador requiere la dirección de correo electrónico que el cliente utilizaba para iniciar sesión y proporcionar revisiones. 

Para buscar y eliminar datos del cliente, siga estos pasos.

1. Vaya a **Inicio \> Revisiones \> Eliminar**.
1. En el campo **Buscar usuarios por dirección de correo electrónico**, escriba la dirección de correo electrónico del cliente y, a continuación, seleccione **Buscar**.
1. Si el cliente tiene algún actividad de revisión (por ejemplo, envíos de revisión, votos acerca la utilidad de revisiones de las revisiones de otro cliente, o comentarios sobre la revisión de otro cliente), se muestran los resultados. Para cada artículo, hay un botón **Eliminar**.
1. Para cada artículo que se debe eliminar, seleccione **Eliminar**. Cuando se le pida confirmación, seleccione **Sí**. 
    
![Eliminación de los datos de clientes](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - Se pueden tardar hasta siete días en que los datos se eliminen por completo del sistema. Los moderadores deben notificar a los clientes acerca de este retraso.
> - Si los clientes han cambiado su nombre en la configuración de la cuenta, varios artículos pueden aparecen en los resultados de la búsqueda. En este caso, para eliminar por completo los datos del cliente, el moderador debe seleccionar **Eliminar** para cada artículo. 

## <a name="download-ratings-and-reviews-data"></a>Descargar datos de clasificaciones y revisiones

La herramientas de evaluaciones y revisiones permite a los moderadores importar datos de clasificaciones y revisiones de manera masiva, de modo que puedan analizar tendencias. Hay disponible una plantilla de Power BI que incluye métrica básica. Los moderadores pueden utilizar esta plantilla para conectar datos importados de manera masiva y ver un panel. No tienen que crear un panel personalizado. Los moderadores también pueden personalizar la plantilla de Power BI para satisfacer sus necesidades específicas. 

Para descargar los datos de clasificaciones y revisiones, siga estos pasos.

1. Vaya a **Inicio \> Revisiones \> Informes**.
1. Seleccione **Descargar datos de revisiones** para descargar datos de clasificaciones y revisiones de manera masiva en el formato de valores separados por comas (CSV).

## <a name="view-ratings-and-reviews-trends"></a>Ver tendencias de clasificaciones y revisiones

Los moderadores pueden descargar la plantilla de Power BI de modo que puedan ver tendencias en un panel.

Para ver tendencias de clasificaciones y revisiones, siga estos pasos.

1. Vaya a **Inicio \> Revisiones \> Informes**.
1. Seleccione **Plantilla de PowerBI** para descargar la plantilla.

    ![Descarga de la plantilla de Power BI](media/rnr-moderation-reports.png) 

1. Abra la plantilla descargada mediante la aplicación Power BI. Cierre el cuadro de diálogo **Acceso al contenido web** que aparece y cierre el mensaje de error “Actualización” que aparece.
1. Vaya a **Inicio**, seleccione **Editar consultas** y **Configuración del origen de datos**.
1. En el cuadro de diálogo **Configuración de origen de datos**, seleccione **Cambiar origen**.
1. En el campo **Dirección URL**, especifique la ruta de los datos de revisiones que ha descargado en el procedimiento anterior (por ejemplo, **c:\\reviews\\ReviewsData.csv**).

    ![Campo de dirección URL en el cuadro de diálogo Valores separados por comas](media/rnr-powerbi-datasource-settings.png) 

1. Seleccione **Aceptar** y, a continuación, **Aplicar cambios**. Se tardará de uno a dos minutos en aplicar los cambios al origen de datos.
1. Seleccione **Hoja de tendencias** para ver las tendencias de clasificaciones y revisiones.

    ![Tendencias de clasificaciones y revisiones](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a>Recursos adicionales

[Visión general de clasificaciones y revisiones](ratings-reviews-overview.md)

[Optar por usar clasificaciones y revisiones de usuario](opt-in-ratings-reviews.md)

[Configurar clasificaciones y revisiones](configure-ratings-reviews.md)

[Sincronizar clasificaciones de productos en Dynamics 365 Retail](sync-product-ratings.md)

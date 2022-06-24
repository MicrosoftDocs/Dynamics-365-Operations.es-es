---
title: Habilitar recomendaciones de producto
description: Este artículo explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial y aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3dceec9e8e994a81b43cd5d1bd13970f2d246f40
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892080"
---
# <a name="enable-product-recommendations"></a>Habilitar recomendaciones de producto

[!include [banner](includes/banner.md)]

Este artículo explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial y aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce. Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Recomendaciones previas a la comprobación

1. Asegúrese de tener una Licencia de recomendaciones de Dynamics 365 Commerce válida.
1. Asegúrese de que la tienda Entity esté conectada a una cuenta de Azure Data Lake Storage Gen2 propiedad del cliente. Para más información, consulte [Asegurarse de que Azure Data Lake Storage se haya comprado y verificado con éxito en el entorno](enable-ADLS-environment.md).
1. Confirme que la configuración de Azure AD Identity contiene una entrada para Recomendaciones. A continuación se encuentra más información sobre cómo hacer esta acción.
1. Asegúrese de que se ha programado la actualización diaria de al tienda de entidades en Azure Data Lake Storage Gen2. Para más información, ver [Asegúrese de que la actualización de la tienda Entity se haya automatizado](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
1. Habilite las medidas de RetailSale para el almacén de entidades. Para obtener más información sobre la configruación de este proceso, consulte [Trabajar con medidas](/dynamics365/ai/customer-insights/pm-measures).

Una vez que se hayan completado los pasos anteriores, estará listo para habilitar las recomendaciones.

## <a name="azure-ad-identity-configuration"></a>Configuración de Azure AD Identity

Este paso solo es necesario para los clientes que ejecutan una configuración de infraestructura como servicio (IaaS). La configuración de la identidad de Azure AD es automática para los clientes que ejecutan Azure Service Fabric, pero se recomienda que verifique que la configuración esté configurada como se esperaba.

### <a name="setup"></a>Configurar

1. En la sede de Comercio, busque la página de **aplicaciones de Azure Active Directory**.
1. Compruebe que existe una entrada para **RecommendationSystemApplication-1**. Si no existe una entrada, cree una con la siguiente información:

    - **Id. de cliente**: d37b07e8-dd1c-4514-835d-8b918e6f9727
    - **Nombre**: RecommendationSystemApplication-1
    - **Id. de usuario**: RetailServiceAccount

1. Guarde y cierre la página. 

## <a name="turn-on-recommendations"></a>Activar recomendaciones

Para activar recomendaciones de productos, siga estos pasos.

1. En la central de Commerce, busque **Gestión de funciones**.
1. Seleccione **Todas** para ver una lista de funciones disponibles. 
1. En el cuadro de búsqueda, introduzca **Recomendaciones**.
1. Seleccione la característica **Recomendaciones de productos**.
1. En el panel de propiedades **Recomendaciones de productos**, seleccione **Habilitar ahora**.

![Activar las recomendaciones.](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> - El procedimiento anterior inicia el proceso de generar listas de recomendaciones de productos. Es posible que se requieran varias horas antes de que las listas estén disponibles y puedan verse en el punto de venta (PDV) o en Dynamics 365 Commerce.
> - Esta configuración no habilita todas las funciones de recomendaciones. Las funciones avanzadas como las recomendaciones personalizadas, "comprar looks similares" y "comprar una descripción similar" están controladas por entradas dedicadas a la gestión de funciones. Para obtener información sobre cómo habilitar estas funciones en la sede de Commerce, consulte [Habilitar recomendaciones personalizadas](personalized-recommendations.md), [Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md) y [Habilitar recomendaciones de "comprar descripción similar"](shop-similar-description.md).

## <a name="configure-recommendation-list-parameters"></a>Configurar parámetros de la lista de recomendaciones

De forma predeterminada, la lista de recomendaciones de productos según AI-ML ofrece valores sugeridos. Puede cambiar los valores sugeridos predeterminados para adaptarlos al flujo de su negocio. Para obtener más información acerca de cómo cambiar los parámetros predeterminados, vaya a [Administrar resultados de recomendaciones de producto basadas en AI-ML](modify-product-recommendation-results.md).

## <a name="include-recommendations-in-e-commerce-experiences"></a>Incluir recomendaciones en experiencias de comercio electrónico

Después de habilitar las recomendaciones en la sede de Comercio, los módulos de Comercio que se utilizan para mostrar los resultados de las recomendaciones para las experiencias de comercio electrónico están listos para configurarse. Para obtener más información, consulte [Módulos de colecciones de productos](product-collection-module-overview.md).

## <a name="show-recommendations-on-pos-devices"></a>Mostrar recomendaciones en dispositivos PDV

Tras habilitar recomendaciones en Commerce Headquarters, el panel de recomendaciones se debe agregar a la pantalla de PDV de control mediante la herramienta de diseño. Para conocer este proceso, consulte [Agregar un control de recomendaciones a la pantalla de transacciones en dispositivos de PDV](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Habilitar recomendaciones personalizadas

En Dynamics 365 Commerce, los minoristas pueden hacer que estén disponibles recomendaciones de productos personalizadas (lo que también se conoce como personalización). De esta manera, se pueden incorporar recomendaciones personalizadas en la experiencia del cliente en línea y en el punto de venta. Cuando se activa la funcionalidad de personalización, el sistema puede asociar la compra de un usuario y la información del producto para generar recomendaciones de productos individualizadas.

Para obtener más información recomendaciones personalizadas, consulte [Habilitar recomendaciones personalizadas](personalized-recommendations.md).

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]

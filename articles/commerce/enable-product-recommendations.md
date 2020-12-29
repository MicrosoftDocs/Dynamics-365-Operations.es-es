---
title: Habilitar recomendaciones de producto
description: Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b201e5481cfaf5bb6cd64a89cdb6b5a91f31447f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415418"
---
# <a name="enable-product-recommendations"></a>Habilitar recomendaciones de producto

[!include [banner](includes/banner.md)]

Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce. Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Recomendaciones previas a la comprobación

Antes de habilitar, tenga en cuenta que las recomendaciones de productos solo se admiten para clientes de Commerce que han migrado su almacenamiento para usar Azure Data Lake Storage. 

Las siguientes configuraciones deben estar habilitadas en el back office antes de habilitar las recomendaciones:

1. Asegúrese de que Azure Data Lake Storage se haya comprado y verificado con éxito en el entorno. Para más información, consulte [Asegurarse de que Azure Data Lake Storage se haya comprado y verificado con éxito en el entorno](enable-ADLS-environment.md).
2. Asegúrese de que la actualización de la tienda de la entidad se haya automatizado. Para más información, ver [Asegúrese de que la actualización de la tienda Entity se haya automatizado](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).
3. Confirme que la configuración de Azure AD Identity contiene una entrada para Recomendaciones. A continuación se encuentra más información sobre cómo hacer esta acción.

Además, asegúrese de que se han habilitado las medidas de RetailSale. Para obtener más información sobre este proceso de configuración, consulte [Trabajar con medidas](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).

## <a name="azure-ad-identity-configuration"></a>Configuración de Azure AD Identity

Este paso es necesario para todos los clientes que ejecutan una configuración de infraestructura como servicio (IaaS). Para los clientes que se ejecutan en Service Fabric (SF), este paso debe ser automático y recomendamos verificar que la configuración esté configurada como se esperaba.

### <a name="setup"></a>Configurar

1. Desde el back office, busque la página **aplicaciones Azure Active Directory**.
2. Verifique si existe una entrada para "RecommendationSystemApplication-1".

Si la entrada no existe, agregue una nueva entrada con la siguiente información:

- **Id. de cliente** - d37b07e8-dd1c-4514-835d-8b918e6f9727
- **Nombre** - RecommendationSystemApplication-1
- **Id. de usuario** - RetailServiceAccount

Guarde y cierre la página. 

## <a name="turn-on-recommendations"></a>Activar recomendaciones

Para activar recomendaciones de productos, siga estos pasos.

1. En la central de Commerce, busque **Gestión de funciones**.
1. Seleccione **Todas** para ver una lista de funciones disponibles. 
1. En el cuadro de búsqueda, introduzca **Recomendaciones**.
1. Seleccione la característica **Recomendaciones de productos**.
1. En el panel de propiedades **Recomendaciones de productos**, seleccione **Habilitar ahora**.

![Activar las recomendaciones](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> Este procedimiento inicia el proceso de generar listas de recomendaciones de productos. Es posible que se requieran varias horas antes de que las listas estén disponibles y puedan verse en el punto de venta (PDV) o en Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configurar parámetros de la lista de recomendaciones

De forma predeterminada, la lista de recomendaciones de productos según AI-ML ofrece valores sugeridos. Puede cambiar los valores sugeridos predeterminados para adaptarlos al flujo de su negocio. Para obtener más información acerca de cómo cambiar los parámetros predeterminados, vaya a [Administrar resultados de recomendaciones de producto basadas en AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Mostrar recomendaciones en dispositivos PDV

Tras habilitar recomendaciones en la oficina administrativa de Commerce, el panel de recomendaciones se debe agregar a la pantalla de PDV de control mediante la herramienta de diseño. Para conocer este proceso, consulte [Agregar un control de recomendaciones a la pantalla de transacciones en dispositivos de PDV](add-recommendations-control-pos-screen.md). 

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


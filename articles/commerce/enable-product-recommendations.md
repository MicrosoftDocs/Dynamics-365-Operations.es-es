---
title: Habilitar recomendaciones de producto
description: Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
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
ms.openlocfilehash: d8a579be5df3c5e7718a6fb4720341f3bd01a64c
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154422"
---
# <a name="enable-product-recommendations"></a>Habilitar recomendaciones de producto

[!include [banner](includes/banner.md)]

Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce. Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Recomendaciones previas a la comprobación

Antes de habilitar, tenga en cuenta que las recomendaciones de productos solo se admiten para clientes de Commerce que han migrado su almacenamiento para usar Azure Data Lake Storage (ADLS). 

Para conocer los pasos para habilitar ADLS, vea [Cómo habilitar ADLS en un entorno de Dynamics 365](enable-ADLS-environment.md).

Además, asegúrese de que se han habilitado las medidas de RetailSale. Para obtener más información acerca de este proceso de configuración, vaya [aquí.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Activar recomendaciones

Para activar recomendaciones de productos, siga estos pasos.

1. Vaya a **Retail y Commerce &gt; Recomendaciones de producto &gt; Parámetros de recomendaciones**.
1. En la lista de parámetros compartidos, seleccione **Listas de recomendaciones**.
1. Establezca la opción **Habilitar recomendaciones** en **Sí**.

![habilitar recomendaciones de producto](./media/enableproductrecommendations.png)

> [!NOTE]
> Este procedimiento inicia el proceso de generar listas de recomendaciones de productos. Es posible que se requieran varias horas antes de que las listas estén disponibles y puedan verse en el punto de venta (PDV) o en Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configurar parámetros de la lista de recomendaciones

De forma predeterminada, la lista de recomendaciones de productos según AI-ML ofrece valores sugeridos. Puede cambiar los valores sugeridos predeterminados para adaptarlos al flujo de su negocio. Para obtener más información acerca de cómo cambiar los parámetros predeterminados, vaya a [Administrar resultados de recomendaciones de producto basadas en AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Mostrar recomendaciones en dispositivos PDV

Tras habilitar recomendaciones en la oficina administrativa de Commerce, el panel de recomendaciones se debe agregar a la pantalla de PDV de control mediante la herramienta de diseño. Para conocer este proceso, vea [Agregar un control de recomendaciones a la pantalla de transacciones en dispositivos de PDV](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Habilitar recomendaciones personalizadas

Para obtener más información sobre cómo recibir recomendaciones personalizadas, consulte [Habilitar recomendaciones personalizadas](personalized-recommendations.md).

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar ADLS en un entorno de Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)


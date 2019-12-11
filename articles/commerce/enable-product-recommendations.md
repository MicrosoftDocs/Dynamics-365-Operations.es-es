---
title: Habilitar recomendaciones de producto
description: Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770148"
---
# <a name="enable-product-recommendations"></a>Habilitar recomendaciones de producto

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce. Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Recomendaciones previas a la comprobación
Antes de habilitar, tenga en cuenta que las recomendaciones de productos solo se admiten para clientes de F&O que admiten la compilación 10.0.6 y han migrado su almacenamiento para usar BDL. 

Además, asegúrese de que se han habilitado las medidas de RetailSale. Para obtener más información acerca de este proceso de configuración, vaya [aquí.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Activar recomendaciones

Para activar recomendaciones de productos, siga estos pasos.

1. Vaya a **Retail** &gt; **Recomendaciones de producto** &gt; **Parámetros de recomendaciones**.
1. En la lista de parámetros compartidos comerciales, seleccione **Listas de recomendaciones**.
1. Establezca la opción **Habilitar recomendaciones** en **Sí**.

![habilitar recomendaciones de producto](./media/enableproductrecommendations.png)

> [!NOTE]
> Este procedimiento inicia el proceso de generar listas de recomendaciones de productos. Es posible que se requieran varias horas antes de que las listas estén disponibles y puedan verse en el punto de venta (PDV) o en Dynamics 365 for Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configurar parámetros de la lista de recomendaciones
De forma predeterminada, la lista de recomendaciones de productos según AI-ML ofrece valores sugeridos. Puede cambiar los valores sugeridos predeterminados para adaptarlos al flujo de su negocio. Para obtener más información acerca de cómo cambiar los parámetros predeterminados, vaya a [Administrar resultados de recomendaciones de producto basadas en AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Mostrar recomendaciones en dispositivos PDV
Tras habilitar recomendaciones en la oficina administrativa, el panel de recomendaciones se debe agregar a la pantalla de PDV de control mediante la herramienta de diseño. Para obtener información acerca de este proceso, vaya [aquí.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Agregar listas de recomendaciones a páginas](add-reco-list-to-page.md)

[Para agregar el panel de recomendaciones a dispositivos de PDV](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


